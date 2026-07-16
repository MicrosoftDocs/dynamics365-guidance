---
title: Sample queries and dashboards for conversation diagnostics
description: Use these sample queries to analyze conversation diagnostics in Dynamics 365 Contact Center with Application Insights, and start troubleshooting faster today.
author: neeranelli
ms.author: nenellim
ms.reviewer: nenellim
ms.topic: concept-article
ms.collection:
ms.date: 07/15/2026
ms.custom:
  - bap-template
  - O25-Service
---

# Sample queries and dashboards for conversation diagnostics

Use these custom queries to investigate conversation diagnostics in Dynamics 365 Contact Center by using Application Insights. It covers key routing and assignment scenarios, such as fallback queues, conversation orchestration, bullseye routing, overflow handling, rejected assignments, delayed assignment, transfers, consults, and unsuccessful conversations. You can trace issues end to end and find root causes faster. It also shows how to use Azure Data Explorer dashboards to visualize telemetry, monitor trends, and support ongoing troubleshooting at scale.

## Fallback queues

Use the following query to diagnose the number of work items routed to fallback queues.

```kusto

let _endTime = datetime(2024-11-21T22:29:53Z);  
let _startTime = datetime(2024-09-22T21:29:53Z);  

Traces  
| where timestamp >= _startTime and timestamp <= _endTime  
| extend customDim = parse_json(customDimensions)  
| extend conversationId = tostring(customDim["powerplatform.analytics.resource.id"]),   
         subscenario = tostring(customDim["powerplatform.analytics.subscenario"]),  
         queueResult = parse_json(tostring(customDim["omnichannel.result"])).DisplayName
| extend scenario = tostring(customDim["powerplatform.analytics.scenario"])  
| where scenario == "ConversationDiagnosticsScenario"  
| where subscenario == "RouteToQueue" and queueResult == "[Insert Your Fallback queue name]"   
| project timestamp, conversationId, queueResult  
```

## Conversation orchestration

Use the following query to view conversation-level diagnostics for [dynamic prioritization](/dynamics365/customer-service/administer/assignment-methods#how-dynamic-prioritization-works-preview) and [overflow scenarios](/dynamics365/customer-service/administer/manage-overflow) that you can configure by using [conversation orchestration](/dynamics365/contact-center/administer/configure-conversation-orchestration).

```kusto
traces
| extend cd = parse_json(customDimensions)                                                                         
| extend
      Rule            = tostring(parse_json(tostring(cd["omnichannel.additional_info"])).Rule),
      Scenario        = tostring(parse_json(tostring(cd["omnichannel.additional_info"])).Scenario),
      Prompt          = tostring(parse_json(tostring(cd["omnichannel.additional_info"])).Prompt),
      Type            = tostring(cd["type"]),
      SubScenario     = tostring(cd["powerplatform.analytics.subscenario"]),
      Description     = tostring(cd["omnichannel.description"]),
      Action          = tostring(cd["omnichannel.action"]),
      Event           = tostring(cd["omnichannel.event"]),
      OrgId           = tostring(cd["powerplatform.analytics.resource.organization.id"]),
      ConversationId  = tostring(cd["powerplatform.analytics.resource.id"]),
      Timestamp       = todatetime(cd["omnichannel.timestamp"])
| where Type == "AgCDDiagnosticsEvent"
| project Timestamp, Type, AnalyticsScenario, SubScenario, Event, Action, Rule, Scenario, Prompt, Description,
  OrgId, ConversationId

//You can add filters on the basis of Scenario, Event, Action, Conversation to name a few
//Add => | where <`column_name`> == "<`value`>" for filter additions
```

**Scenario**: Assign to a previous or preferred expert by using conversation orchestration  
**Purpose**: To view logs for conversation assignment to a previous or preferred expert done by using conversation orchestration  
**Query**

```kusto
traces 
| extend cd = parse_json(customDimensions) 
| extend 
      Rule            = tostring(parse_json(tostring(cd["omnichannel.additional_info"])).Rule), 
      Scenario        = tostring(parse_json(tostring(cd["omnichannel.additional_info"])).Scenario), 
      Prompt          = tostring(parse_json(tostring(cd["omnichannel.additional_info"])).Prompt), 
      Type            = tostring(cd["type"]), 
      SubScenario     = tostring(cd["powerplatform.analytics.subscenario"]), 
      AnalyticsScenario = tostring(cd["powerplatform.analytics.scenario"]), 
      Description     = tostring(cd["omnichannel.description"]), 
      Action          = tostring(cd["omnichannel.action"]), 
      Event           = tostring(cd["omnichannel.event"]), 
      OrgId           = tostring(cd["powerplatform.analytics.resource.organization.id"]), 
      ConversationId  = tostring(cd["powerplatform.analytics.resource.id"]), 
      Timestamp       = todatetime(cd["omnichannel.timestamp"]) 
| where Type == "AgCDDiagnosticsEvent" 
| where Event == "AssignToPreviousOrPreferredExpert" 
| project Timestamp, Type, AnalyticsScenario, SubScenario, Event, Action, Rule, Scenario, Prompt, Description, 
  OrgId, ConversationId
```

## Bullseye routing

Run the following custom query to view the conversation-level diagnostics for [bullseye routing](/dynamics365/contact-center/administer/configure-bullseye-routing) that you can configure through conversation orchestration.

```kusto
// Paste into the conversation's Application Insights -> Logs.
// Set `lwi` to the conversation (Live Work Item) id and adjust `lookback`.
//
// Row model (one row per STEP, not per raw event):
//   - Ring expansion  : the pool widened to a level and no agent was available yet
//   - Assignment      : an agent was OFFERED the work; the row's Outcome merges the
//                       result -> accepted / rejected / no response (timed out)
//   - Fallback        : all ring levels exhausted (keep retrying / any queue member)
//   - Transfer / Consult / Supervisor / Voicemail / Callback / Overflow: lifecycle steps
//
// Columns:
//   T+ (s)           seconds since the conversation entered the queue (Level 0 anchor)
//   Stage            category of the step
//   Outcome          what happened (for Assignment: "Offered to <agent> -> <result>")
//   Expanded level   how far the ring had expanded at this step (MaxRingExpanded)
//   Assigned level   the ring level the assigned agent's user group belongs to
//                    (so "Expanded Level 1 / Assigned Level 0" means the pool had
//                     widened to 1 but the matched agent came from level 0)
//   EligibleUserGroups  CUMULATIVE user groups eligible at this level, as  name (id)
//   Queue            current/target queue, as  name (id)
//   Assignment method   strategy used on the assignment row (e.g. LeastActive)
//   Agent            the agent involved, as  name (id)
//
// Name resolution (purely from App Insights telemetry):
//   - agent/user id -> name : AgentNameConfig (omnichannel.data id->name bag)
//   - user-group id -> name : harvested from agents' UserGroups in assignment status
//   - queue id -> name      : QueueConfigurationDetails
//   Ids with no name available in telemetry (e.g. unstaffed groups, queues not seen
//   in config in the window) are shown as the raw GUID.
//
// Notes:
//   - EligibleUserGroups is cumulative (telemetry logs only each level's own groups).
//   - Voicemail/Callback key the conversation under a different field, so the
//     multi-key match below is required.
// ============================================================================

let lwi = "<CONVERSATION_ID>";   // <-- conversation / live work item id
let lookback = 7d;               // <-- widen if the conversation is older
let namelb = 30d;                // window for id->name lookups
// ---- id -> name lookups
traces
let ugMap = toscalar(
    traces | where timestamp > ago(namelb) | extend cd=parse_json(customDimensions)
    | where tostring(cd["powerplatform.analytics.subscenario"])=="CSRAssignment"
    | extend ugs=parse_json(tostring(cd["omnichannel.assignment.status"]))["AgentDetails"]["UserGroups"]
    | mv-expand ug=ugs | extend ugId=tostring(ug.Id), ugName=tostring(ug.Name)
    | where isnotempty(ugId) and isnotempty(ugName) | summarize make_bag(pack(ugId,ugName)));
let agentMap = toscalar(
    traces | where timestamp > ago(namelb) | extend cd=parse_json(customDimensions)
    | where tostring(cd["powerplatform.analytics.subscenario"])=="AgentNameConfig"
    | extend data=parse_json(tostring(cd["omnichannel.data"])) | mv-expand k=bag_keys(data)
    | extend aid=tostring(k), anm=tostring(data[tostring(k)]) | summarize make_bag(pack(aid,anm)));
let queueMap = toscalar(
    traces | where timestamp > ago(namelb) | extend cd=parse_json(customDimensions)
    | where tostring(cd["powerplatform.analytics.subscenario"])=="QueueConfigurationDetails"
    | extend qqid=tostring(cd["omnichannel.queue.id"]), qn=tostring(cd["omnichannel.queue.name"])
    | where isnotempty(qqid) and isnotempty(qn) | summarize make_bag(pack(qqid,qn)));
// ---- all events for this conversation (multi-key match + normalized fields)
let evts = traces | where timestamp > ago(lookback) | extend cd=parse_json(customDimensions)
  | where tostring(cd["powerplatform.analytics.resource.id"])==lwi
       or tostring(cd["powerplatform.analytics.omnichannel.conversation.id"])==lwi
       or tostring(cd["omnichannel.conversation.id"])==lwi
       or tostring(cd["omnichannel.live_work_item.id"])==lwi
  | extend sub=tostring(cd["powerplatform.analytics.subscenario"])
  | extend wid=parse_json(tostring(cd["omnichannel.work_item.details"])), st=parse_json(tostring(cd["omnichannel.assignment.status"])), ai=parse_json(tostring(cd["omnichannel.additional_info"])), act=tostring(cd["omnichannel.action"])
  | extend ts=todatetime(coalesce(tostring(cd["omnichannel.timestamp"]), tostring(cd["powerplatform.analytics.omnichannel.timestamp"]))),
           descr=coalesce(tostring(cd["omnichannel.description"]), tostring(cd["powerplatform.analytics.omnichannel.description"]))
  | extend isAssigned=tostring(st.IsAgentAssigned)=="true", rLvl=toint(wid.RingLevel), aLvl=toint(wid.AssignedRingLevel), maxR=toint(wid.MaxRingExpanded),
           reason=tostring(wid.AssignReason), pbFb=tostring(ai.FallbackType), agentId=tostring(st.AgentDetails.AgentId), tgt=tostring(cd["omnichannel.target_agent.id"]),
           assignMethod=tostring(cd["omnichannel.assignment.method"]), qid=tostring(wid.QueueId), tqid=tostring(cd["omnichannel.target_queue.id"]),
           vmStatus=tostring(cd["VoicemailStatus"]), cbStatus=tostring(cd["CallbackStatus"]), ovr=ai["OverflowInfo"];
let t0 = toscalar(evts | summarize min(ts));
// ---- per-level own UG ids -> cumulative ids per level (bag keyed by level)
let lvlOwn = evts | where sub=="CSRAssignment"
  | extend lvl = toint(case(isnotnull(rLvl), rLvl, reason=="InitChat" and isnull(rLvl), 0, isnotnull(aLvl), aLvl, int(null)))
  | where isnotnull(lvl) | mv-expand g=wid.UserGroupIds to typeof(string) | where isnotempty(g) | distinct lvl, g;
let cumBag = toscalar((lvlOwn | distinct lvl | extend kk=1 | join kind=inner (lvlOwn | extend kk=1) on kk
  | where lvl1 <= lvl | summarize cumIds=make_set(g) by lvl) | summarize make_bag(pack(tostring(lvl), cumIds)));
// ---- terminal agent actions (to merge into the offer row)
let terminals = evts | where sub in ("CSRAccepted","CSRRejected","CSRNotificationTimeout") | project oTs=ts, oAgent=tgt, oType=sub;
// ---- Ring-expansion rows (pool widened, no agent yet)
let expRows = evts | where sub=="CSRAssignment" and not(isAssigned) and (reason=="InitChat" or isnotnull(rLvl))
  | extend lvl = toint(iff(reason=="InitChat" and isnull(rLvl), 0, rLvl))
  | summarize ts=min(ts), qid=take_any(qid) by lvl
  | extend Stage="Ring expansion", Outcome=iff(lvl==0,"No agent available in initial pool","No agent available - pool expanded"),
           ExpandedLevel=toint(lvl), AssignedLevel=toint(int(null)), agentId="", method="", ugLvl=toint(lvl);
// ---- Assignment rows (agent offered + merged outcome)
let offers0 = evts | where sub=="CSRAssignment" and isAssigned
  | summarize maxR=max(maxR), aLvl=max(aLvl), method=take_any(assignMethod), qid=take_any(qid) by ts, agentId;
let offerRows = offers0
  | join kind=leftouter (terminals) on $left.agentId == $right.oAgent
  | extend cand = iff(isnotnull(oTs) and oTs>=ts, oTs, datetime(9999-12-31))
  | summarize arg_min(cand, oType, maxR, aLvl, method, qid) by ts, agentId
  | extend oType = iff(cand==datetime(9999-12-31), "", oType)
  | extend Stage="Assignment", Outcome="", ExpandedLevel=toint(maxR), AssignedLevel=toint(aLvl), ugLvl=toint(maxR);
// ---- Fallback rows
let fbRows = evts | where sub=="PlaybookExecuted" and act=="FallbackTriggered"
  | summarize ts=min(ts), maxR=max(maxR) by pbFb
  | extend Stage="Fallback", Outcome=strcat("All levels exhausted - ", pbFb),
           ExpandedLevel=toint(maxR), AssignedLevel=toint(int(null)), agentId="", method="", qid="", ugLvl=toint(int(null));
// ---- Transfer / consult / supervisor / voicemail / callback / overflow rows
let otherRows = evts
  | where sub in ("TransferToQueue","TransferAssignment","TransferToExternalInitiated","SupervisorInitiatedTransfer",
                  "QueueConsult","ConsultToCSRInitiated","ConsultToExternalInitiated","CancelQueueConsult",
                  "SupervisorAssignedToCSR","SupervisorAssignedToQueue","CopilotAgentEscalationToCSR","Voicemail","CallbackRequested")
       or (sub=="RouteToQueue" and isnotempty(tostring(ovr)))
  | extend Stage=case(sub=="TransferToQueue","Transfer to queue", sub=="TransferAssignment","Transfer - new assignment",
                      sub=="TransferToExternalInitiated","Transfer to external", sub=="SupervisorInitiatedTransfer","Supervisor transfer",
                      sub=="QueueConsult","Consult to queue", sub=="ConsultToCSRInitiated","Consult to agent",
                      sub=="ConsultToExternalInitiated","Consult to external", sub=="CancelQueueConsult","Consult cancelled",
                      sub=="SupervisorAssignedToCSR","Supervisor assigned to agent", sub=="SupervisorAssignedToQueue","Supervisor assigned to queue",
                      sub=="CopilotAgentEscalationToCSR","Bot escalated to agent", sub=="Voicemail","Voicemail", sub=="CallbackRequested","Callback", "Overflow")
  | extend Outcome=case(sub=="Voicemail", strcat("Voicemail ", vmStatus), sub=="CallbackRequested", strcat("Callback ", cbStatus),
                        sub=="RouteToQueue", strcat("Overflow: ", tostring(ovr["OverflowTrigger"]), " -> ", tostring(ovr["OverflowAction"])), descr)
  | extend agentId=tgt, method="", qid=coalesce(qid, tqid), ExpandedLevel=toint(int(null)), AssignedLevel=toint(int(null)), ugLvl=toint(int(null)), oType=""
  | project ts, Stage, Outcome, ExpandedLevel, AssignedLevel, agentId, method, qid, ugLvl, oType;
union
  (expRows  | project ts, Stage, Outcome, ExpandedLevel, AssignedLevel, agentId, method, qid, ugLvl),
  (offerRows| project ts, Stage, Outcome, ExpandedLevel, AssignedLevel, agentId, method, qid, ugLvl, oType),
  (fbRows   | project ts, Stage, Outcome, ExpandedLevel, AssignedLevel, agentId, method, qid, ugLvl),
  (otherRows)
| extend agentNm=tostring(agentMap[agentId])
| extend Agent=iff(isempty(agentId), "", iff(isempty(agentNm), agentId, strcat(agentNm, " (", agentId, ")")))
| extend ExpNote=iff(Stage=="Assignment" and ExpandedLevel>0, strcat("Expanded to Level ", tostring(ExpandedLevel), "; "), "")
| extend Outcome=case(
    Stage=="Assignment" and oType=="CSRAccepted",            strcat(ExpNote, "Offered to ", Agent, " -> accepted"),
    Stage=="Assignment" and oType=="CSRRejected",            strcat(ExpNote, "Offered to ", Agent, " -> rejected"),
    Stage=="Assignment" and oType=="CSRNotificationTimeout", strcat(ExpNote, "Offered to ", Agent, " -> no response (timed out)"),
    Stage=="Assignment",                                     strcat(ExpNote, "Offered to ", Agent, " -> assigned (active)"),
    Outcome)
| extend cg = todynamic(cumBag[tostring(ugLvl)])
| extend cgDisp = iff(isnotnull(ugLvl) and array_length(cg)>0, cg, dynamic([""]))
| mv-apply x=cgDisp on (
    extend i=tostring(x) | extend nm=tostring(ugMap[i])
    | extend disp=iff(isempty(i),"",iff(isempty(nm), i, strcat(nm, " (", i, ")")))
    | summarize EligibleUserGroups=strcat_array(make_list(disp), ", "))
| extend qn=tostring(queueMap[qid])
| extend Queue=iff(isempty(qid),"",iff(isempty(qn),qid,strcat(qn," (",qid,")")))
| extend ExpLvl=iff(isnotnull(ExpandedLevel), strcat("Level ", tostring(ExpandedLevel)), "")
| extend AsgLvl=iff(isnotnull(AssignedLevel), strcat("Level ", tostring(AssignedLevel)), "")
| distinct ts, Stage, Outcome, ExpLvl, AsgLvl, EligibleUserGroups, Queue, method, Agent
| order by ts asc
| project ["T+ (s)"]=datetime_diff('second', ts, t0), Stage, Outcome,
          ["Expanded level"]=ExpLvl, ["Assigned level"]=AsgLvl,
          EligibleUserGroups, Queue, ["Assignment method"]=method, Agent
```

## Overflow handling

Use the following query to diagnose the number of work items handled where overflow is the trigger.  

```kusto

Traces  
| extend customDim = parse_json(customDimensions)  
| extend conversationId = tostring(customDim["powerplatform.analytics.resource.id"]),  
         subscenario = tostring(customDim["powerplatform.analytics.subscenario"])  
| extend omnichannelAdditionalInfo = tostring((customDim["omnichannel.additional_info"]))
| extend scenario = tostring(customDim["powerplatform.analytics.scenario"])  
| where scenario == "ConversationDiagnosticsScenario"  
| where omnichannelAdditionalInfo contains "OverflowTrigger"  
| project timestamp, conversationId, subscenario, omnichannelAdditionalInfo  
```

## Representatives who reject new assignments

Use the following query to view the customer service representatives (service representatives or representatives) who rejected new assignments (by conversationId).

```kusto
let _endTime = datetime(2024-11-21T22:32:51Z);  
let _startTime = datetime(2024-09-22T21:32:51Z);  
Traces  
| where timestamp >= _startTime and timestamp <= _endTime  
| extend customDim = parse_json(customDimensions)  
| extend conversationId = tostring(customDim["powerplatform.analytics.resource.id"]),   
         subscenario = tostring(customDim["powerplatform.analytics.subscenario"]),  
         agentId = tostring(customDim["omnichannel.target_agent.id"]) // Extract representative ID from custom dimensions  
| extend scenario = tostring(customDim["powerplatform.analytics.scenario"])  
| where scenario == "ConversationDiagnosticsScenario"  
| where subscenario == "CSRRejected"  
| summarize agentRejectionCount = count() by conversationId, agentId // Count rejections per representative per conversation  
| summarize rejectionCount = sum(agentRejectionCount),   
            agentRejectionDetails = make_list(pack('agentId', agentId, 'rejectionCount', agentRejectionCount))   
    by conversationId // Aggregate results by conversation  
| where rejectionCount > 1 // Filter conversations with more than one rejection  
| project conversationId, rejectionCount, agentRejectionDetails  
```

View the information about representatives who reject new assignments (by representatives).  

```kusto
let _endTime = datetime(2024-11-21T22:33:55Z);  
let _startTime = datetime(2024-09-22T21:33:55Z);  
traces  
| where timestamp >= _startTime and timestamp <= _endTime  
| extend customDim = parse_json(customDimensions)  
| extend agentId = tostring(customDim["omnichannel.target_agent.id"]), // Extract agent ID from custom dimensions  
         subscenario = tostring(customDim["powerplatform.analytics.subscenario"])  
| extend scenario = tostring(customDim["powerplatform.analytics.scenario"])  
| where scenario == "ConversationDiagnosticsScenario"  
| where subscenario == "CSRRejected"  
| summarize totalRejections = count() by agentId // Count total rejections for each agent  
| sort by totalRejections desc // Sort by rejection count in descending order  
| top 20 by totalRejections // Select top 20 agents  
| project agentId, totalRejections // Project relevant columns  
```
  
## Representative assignment took longer than two minutes

Use the following query to view and diagnose conversations where representative assignment took longer than two minutes.

```kusto
let _endTime = datetime(2024-11-21T22:35:56Z);  
let _startTime = datetime(2024-09-22T21:35:56Z);  
// Extract relevant subscenarios  
let subscenarios = traces  
| where timestamp >= _startTime and timestamp <= _endTime  
| extend customDim = parse_json(customDimensions)  
| extend conversationId = tostring(customDim["powerplatform.analytics.resource.id"]),  
         subscenario = tostring(customDim["powerplatform.analytics.subscenario"])  
| where subscenario in ("RouteToQueue", "CSRAccepted")  
| project timestamp, conversationId, subscenario;  
// Find the latest RTQ before each AgentAccept  
let latestRTQsBeforeAgentAccept = subscenarios  
| where subscenario == "RouteToQueue"  
| join kind=inner (  
    subscenarios  
    | where subscenario == "CSRAccepted"  
    | project agentAcceptTime = timestamp, conversationId  
) on conversationId  
| where timestamp < agentAcceptTime // Ensure RTQ is before AgentAccept  
| summarize latestRTQTime = max(timestamp) by conversationId, agentAcceptTime;  
// Calculate assignment time  
latestRTQsBeforeAgentAccept  
| extend assignmentTime = agentAcceptTime - latestRTQTime  
| where assignmentTime > 2min   
| project conversationId, assignmentTime  
```

## Why a conversation wasn’t assigned to any representative until now

Use the following steps to determine why the conversation isn't assigned.

1. Get the conversation lifecycle using the following query.

    ```kusto

    traces
    | extend customDim = parse_json(customDimensions)
    | extend lwiid = tostring(customDim["powerplatform.analytics.resource.id"])
    | extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])
    | where lwiid == "a4921f6b-f6a7-4a67-b851-cfee318c2403" // Fill in the conversation id
    | project timestamp, lwiid, subscenario, customDim
    | order by timestamp asc
    ```

1. Use the results to identify the last assignment attempt event and make a note of the **timestamp (UTC)** within the **CSRAssignment** subscenario.

1. Identify the assignment rules used to assign an agent, using the ruleset details inside the **CustomDim** section.

1. Identify the work item details, like queue ID, Allowed presences and required capacity, from the **omnichannel.work_item.details** field inside the **CustomDim** section column.

1. Identify representatives present in the queue and their corresponding presence, unit capacity, capacity profiles, and skills at the time of assignment.

    > [!IMPORTANT]
    > This is a resource-intensive query. We recommend that you use it based on concrete needs. If you need specific details about a service representative, such as their presence, capacity, or skill, you can use the individual component queries.

    ```Kusto
    
    let assignmentAttemptTime = now();  // Fill in timestamp of assignment attempt  
    let lwiQueueId = "05a59008-f63a-f011-b4cb-6045bd070c8e"; // Fill in queue id of the work item   
    let agentConfigsTemp = traces   
    | extend customDim = parse_json(customDimensions)   
    | extend agentid = tostring(customDim["powerplatform.analytics.resource.id"])   
    | extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])   
    | extend agentQueues = tostring(customDim["omnichannel.queue.ids"])   
    | where subscenario == "AgentConfiguration"  or subscenario == 'CSRConfigurationDetails' 
    | where agentQueues contains lwiQueueId   
    | where timestamp < assignmentAttemptTime   
    | project agentConfigRecordedTime = timestamp, agentid, subscenario, agentConfig = customDim   
    | order by agentConfigRecordedTime desc   
    | summarize arg_max(agentConfigRecordedTime, *) by agentid;   
    let agentids = agentConfigsTemp 
    | project agentid;  
    let latestagentConfig=traces  
    | extend customDim = parse_json(customDimensions)  
    | extend agentid = tostring(customDim["powerplatform.analytics.resource.id"])  
    | extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])  
    | extend agentQueues = tostring(customDim["omnichannel.queue.ids"])  
    | extend agentProfiles = tostring(customDim["omnichannel.capacity_profile.ids"])  
    | where subscenario == "AgentConfiguration" or subscenario == 'CSRConfigurationDetails' 
    | where timestamp < assignmentAttemptTime  
    | where agentid in (agentids)  
    | project agentConfigRecordedTime = timestamp, agentid, subscenario, agentConfig = customDim,agentQueues,agentProfiles  
    | order by agentConfigRecordedTime desc  
    | summarize arg_max(agentConfigRecordedTime, *) by agentid;  
    let agentConfigs = traces  
    | extend customDim = parse_json(customDimensions)  
    | extend agentid = tostring(customDim["powerplatform.analytics.resource.id"])  
    | extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])  
    | where subscenario == "AgentConfiguration" or subscenario == 'CSRConfigurationDetails' 
    | join kind=inner latestagentConfig on agentid 
    | extend agentProfiles = tostring(customDim["omnichannel.capacity_profile.ids"])  
    | mv-expand profileIds = parse_json(agentProfiles) 
    | where timestamp < assignmentAttemptTime  
    | project agentConfigRecordedTime = timestamp, profileIds, agentProfiles, agentid, subscenario, agentConfig = customDim  
    | order by agentConfigRecordedTime desc  
    | summarize arg_max(agentConfigRecordedTime, *) by agentid;  
    let capacityprofiles1 = agentConfigs  
    | mv-expand profileIds = parse_json(agentProfiles)  
    | project agentid, capacityProfileId = tostring(profileIds);  
    let statusCapacityHistoryRecords = traces  
    | extend customDim = parse_json(customDimensions)  
    | where timestamp < assignmentAttemptTime  
    | extend agentid = tostring(customDim["powerplatform.analytics.resource.id"])  
    | extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])  
    | extend cpparsed = parse_json(tostring(customDim["omnichannel.capacity_profile"]))  
    | extend capacityProfileId = tostring(cpparsed["CapacityProfileId"])  
    | where subscenario in ("AgentStatusAndCapacity", "CSRStatusandCapacityDetails")  
    | project timestamp, agentid, capacityProfileId, subscenario, customDim, cpparsed 
    | join kind=inner ( 
        capacityprofiles1 
    ) on agentid, capacityProfileId 
    | project statusCapacityHistoryRecordedTime = timestamp, agentid, subscenario, agentStatusAndCapacity = customDim, capacityProfileId, cpparsed 
    | order by statusCapacityHistoryRecordedTime desc 
    | summarize arg_max(statusCapacityHistoryRecordedTime, *) by agentid, capacityProfileId; 
    let unitbasedTable = traces   
    | where timestamp < assignmentAttemptTime   
    | extend customDim = parse_json(customDimensions)   
    | extend agentid = tostring(customDim["powerplatform.analytics.resource.id"])   
    | extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])   
    | where subscenario == "AgentStatusAndCapacity" or subscenario == 'CSRStatusandCapacityDetails' 
    | extend cpparsed = parse_json( tostring(customDim["omnichannel.capacity_profile"])) 
    | where cpparsed == "" 
    | extend UnitAvailableCapacity = tostring(customDim["omnichannel.available_capacity.units"]) 
    | join kind=inner latestagentConfig on agentid 
    | project statusCapacityHistoryRecordedTime = timestamp, agentid, subscenario, agentConfig = customDim, UnitAvailableCapacity 
    | summarize arg_max(statusCapacityHistoryRecordedTime, *) by agentid 
    | order by statusCapacityHistoryRecordedTime desc ; 
    let presenceTable = traces   
    | where timestamp < assignmentAttemptTime   
    | extend customDim = parse_json(customDimensions)   
    | extend agentid = tostring(customDim["powerplatform.analytics.resource.id"])   
    | extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])   
    | where subscenario == "AgentStatusAndCapacity" or subscenario == 'CSRStatusandCapacityDetails' 
    | extend cpparsed = parse_json( tostring(customDim["omnichannel.capacity_profile"])) 
    | where cpparsed == "" 
    | extend BasePresenceStatus = tostring(customDim["omnichannel.current_base_presence"]) 
    | extend PresenceId = tostring(customDim["omnichannel.current_presence_id"]) 
    | join kind=inner latestagentConfig on agentid 
    | project statusCapacityHistoryRecordedTime = timestamp, agentid, subscenario, agentConfig = customDim, BasePresenceStatus, PresenceId 
    | summarize arg_max(statusCapacityHistoryRecordedTime, *) by agentid 
    | order by statusCapacityHistoryRecordedTime desc ; 
    let agentQueuesAndSkills = traces   
    | extend customDim = parse_json(customDimensions)   
    | extend agentid = tostring(customDim["powerplatform.analytics.resource.id"])   
    | extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])   
    | extend skillData = parse_json(tostring(customDim["omnichannel.associated_skills"]) ) 
    | extend agentQueues = tostring(customDim["omnichannel.queue.ids"])  
    | where subscenario == "AgentConfiguration" or subscenario == 'CSRConfigurationDetails' 
    | join kind=inner latestagentConfig on agentid 
    | where timestamp < assignmentAttemptTime   
    | project agentConfigRecordedTime = timestamp, agentid, subscenario, agentConfig = customDim, skillData, agentQueues 
    | order by agentConfigRecordedTime desc 
    | summarize arg_max(agentConfigRecordedTime, *) by agentid;  
    let agentNames = traces  
    | where timestamp > ago(2d)  
    | extend customDim = parse_json(customDimensions)  
    | extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])  
    | where subscenario == "AgentNameConfig" or subscenario == 'CSRConfigurationDetails' 
    | extend agentInfo = tostring(customDim["omnichannel.data"])  
    | extend agentInfoParsed = parse_json(agentInfo)  
    | mv-expand keyValue = bag_keys(agentInfoParsed)  
    | project agentid = tostring(keyValue), agentName = tostring(agentInfoParsed[tostring(keyValue)]), timestamp  
    | summarize arg_max(timestamp, *) by agentid; 
    let cpListTable = statusCapacityHistoryRecords 
    | summarize capacitprofiles = make_list(cpparsed) by agentid; 
    cpListTable 
    | join kind=leftouter agentNames on agentid 
    | join kind=inner unitbasedTable on agentid 
    | join kind=inner presenceTable on agentid 
    | join kind=inner agentQueuesAndSkills on agentid 
    | project agentid, agentName, UnitAvailableCapacity, BasePresenceStatus, PresenceId, capacitprofiles, skillData, agentQueues;
    
    ```

## Why is the work item assigned to service representative X instead of service representative Y


1. Get the conversation’s lifecycle using the following query.

    **Query**:

    ```Kusto
    
    traces
    | extend customDim = parse_json(customDimensions)
    | extend lwiid = tostring(customDim["powerplatform.analytics.resource.id"]) // Fill in the conversation id
    | extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])
    | where lwiid == "ac467bad-5d3f-4288-94f9-dc51d17c862f"
    | project timestamp, lwiid, subscenario, customDim
    | order by timestamp asc
    ```

1. Find the last assignment attempt that's marked by the "CSRAssignment" sub-scenario.

1. Get the IDs of the representatives to check. For example, to check why the conversation was assigned to the service representative with the ID `8874e390-9ecc-ef11-a72f-000d3a3652d6` instead of the service representative with the ID `92a1375c-e9dc-ef11-a72f-000d3a3ad269` or the service representative with the ID `7ac24088-a804-f011-bae2-000d3a3172e5`.

1. Identify the assignment rules used to assign the conversation, the conversation queue and the conversation requirements.

1. Identify the presence, unit capacity, capacity profiles, and skills of the representatives shortlisted from Step 3 at the time of assignment.

    **Query**:

    ```Kusto
    
    let assignmentAttemptTime = now();  // Fill in timestamp of assignment attempt  
    let agentids = dynamic(["92a1375c-e9dc-ef11-a72f-000d3a3ad269", "8874e390-9ecc-ef11-a72f-000d3a3652d6", "fc19139b-facd-ef11-a72e-0022480aa3fe"]); //Fill in system user IDs of service representatives
    let latestagentConfig=traces  
    | extend customDim = parse_json(customDimensions)  
    | extend agentid = tostring(customDim["powerplatform.analytics.resource.id"])  
    | extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])  
    | extend agentQueues = tostring(customDim["omnichannel.queue.ids"])  
    | extend agentProfiles = tostring(customDim["omnichannel.capacity_profile.ids"])  
    | where subscenario == "AgentConfiguration" or subscenario == 'CSRConfigurationDetails' 
    | where timestamp < assignmentAttemptTime  
    | where agentid in (agentids)  
    | project agentConfigRecordedTime = timestamp, agentid, subscenario, agentConfig = customDim,agentQueues,agentProfiles  
    | order by agentConfigRecordedTime desc  
    | summarize arg_max(agentConfigRecordedTime, *) by agentid;  
    let agentConfigs = traces  
    | extend customDim = parse_json(customDimensions)  
    | extend agentid = tostring(customDim["powerplatform.analytics.resource.id"])  
    | extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])  
    | where subscenario == "AgentConfiguration" or subscenario == 'CSRConfigurationDetails' 
    | join kind=inner latestagentConfig on agentid 
    | extend agentProfiles = tostring(customDim["omnichannel.capacity_profile.ids"])  
    | mv-expand profileIds = parse_json(agentProfiles) 
    | where timestamp < assignmentAttemptTime  
    | project agentConfigRecordedTime = timestamp, profileIds, agentProfiles, agentid, subscenario, agentConfig = customDim  
    | order by agentConfigRecordedTime desc  
    | summarize arg_max(agentConfigRecordedTime, *) by agentid;  
    let capacityprofiles1 = agentConfigs  
    | mv-expand profileIds = parse_json(agentProfiles)  
    | project agentid, capacityProfileId = tostring(profileIds);  
    let statusCapacityHistoryRecords = traces  
    | extend customDim = parse_json(customDimensions)  
    | where timestamp < assignmentAttemptTime  
    | extend agentid = tostring(customDim["powerplatform.analytics.resource.id"])  
    | extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])  
    | extend cpparsed = parse_json(tostring(customDim["omnichannel.capacity_profile"]))  
    | extend capacityProfileId = tostring(cpparsed["CapacityProfileId"])  
    | where subscenario in ("AgentStatusAndCapacity", "CSRStatusandCapacityDetails")  
    | project timestamp, agentid, capacityProfileId, subscenario, customDim, cpparsed 
    | join kind=inner ( 
        capacityprofiles1 
    ) on agentid, capacityProfileId 
    | project statusCapacityHistoryRecordedTime = timestamp, agentid, subscenario, agentStatusAndCapacity = customDim, capacityProfileId, cpparsed 
    | order by statusCapacityHistoryRecordedTime desc 
    | summarize arg_max(statusCapacityHistoryRecordedTime, *) by agentid, capacityProfileId; 
    let unitbasedTable = traces   
    | where timestamp < assignmentAttemptTime   
    | extend customDim = parse_json(customDimensions)   
    | extend agentid = tostring(customDim["powerplatform.analytics.resource.id"])   
    | extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])   
    | where subscenario == "AgentStatusAndCapacity" or subscenario == 'CSRStatusandCapacityDetails' 
    | extend cpparsed = parse_json( tostring(customDim["omnichannel.capacity_profile"])) 
    | where cpparsed == "" 
    | extend UnitAvailableCapacity = tostring(customDim["omnichannel.available_capacity.units"]) 
    | join kind=inner latestagentConfig on agentid 
    | project statusCapacityHistoryRecordedTime = timestamp, agentid, subscenario, agentConfig = customDim, UnitAvailableCapacity 
    | summarize arg_max(statusCapacityHistoryRecordedTime, *) by agentid 
    | order by statusCapacityHistoryRecordedTime desc ; 
    let presenceTable = traces   
    | where timestamp < assignmentAttemptTime   
    | extend customDim = parse_json(customDimensions)   
    | extend agentid = tostring(customDim["powerplatform.analytics.resource.id"])   
    | extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])   
    | where subscenario == "AgentStatusAndCapacity" or subscenario == 'CSRStatusandCapacityDetails' 
    | extend cpparsed = parse_json( tostring(customDim["omnichannel.capacity_profile"])) 
    | where cpparsed == "" 
    | extend BasePresenceStatus = tostring(customDim["omnichannel.current_base_presence"]) 
    | extend PresenceId = tostring(customDim["omnichannel.current_presence_id"]) 
    | join kind=inner latestagentConfig on agentid 
    | project statusCapacityHistoryRecordedTime = timestamp, agentid, subscenario, agentConfig = customDim, BasePresenceStatus, PresenceId 
    | summarize arg_max(statusCapacityHistoryRecordedTime, *) by agentid 
    | order by statusCapacityHistoryRecordedTime desc ; 
    let agentQueuesAndSkills = traces   
    | extend customDim = parse_json(customDimensions)   
    | extend agentid = tostring(customDim["powerplatform.analytics.resource.id"])   
    | extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])   
    | extend skillData = parse_json(tostring(customDim["omnichannel.associated_skills"]) ) 
    | extend agentQueues = tostring(customDim["omnichannel.queue.ids"])  
    | where subscenario == "AgentConfiguration" or subscenario == 'CSRConfigurationDetails' 
    | join kind=inner latestagentConfig on agentid 
    | where timestamp < assignmentAttemptTime   
    | project agentConfigRecordedTime = timestamp, agentid, subscenario, agentConfig = customDim, skillData, agentQueues 
    | order by agentConfigRecordedTime desc 
    | summarize arg_max(agentConfigRecordedTime, *) by agentid;  
    let agentNames = traces  
    | where timestamp > ago(2d)  
    | extend customDim = parse_json(customDimensions)  
    | extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])  
    | where subscenario == "AgentNameConfig" or subscenario == 'CSRConfigurationDetails' 
    | extend agentInfo = tostring(customDim["omnichannel.data"])  
    | extend agentInfoParsed = parse_json(agentInfo)  
    | mv-expand keyValue = bag_keys(agentInfoParsed)  
    | project agentid = tostring(keyValue), agentName = tostring(agentInfoParsed[tostring(keyValue)]), timestamp  
    | summarize arg_max(timestamp, *) by agentid; 
    let cpListTable = statusCapacityHistoryRecords 
    | summarize capacitprofiles = make_list(cpparsed) by agentid; 
    cpListTable 
    | join kind=leftouter agentNames on agentid 
    | join kind=inner unitbasedTable on agentid 
    | join kind=inner presenceTable on agentid 
    | join kind=inner agentQueuesAndSkills on agentid 
    | project agentid, agentName, UnitAvailableCapacity, BasePresenceStatus, PresenceId, capacitprofiles, skillData, agentQueues;
    ```

## Individual queries for quick diagnosis

Use the following query to determine the presence status of service representatives at a point in time.

```Kusto

let assignmentAttemptTime = now();  // Fill in the timestamp   
let agentId = '92a1375c-e9dc-ef11-a72f-000d3a3ad269'; // Fill in the System User Id of the agent 
let statusCapacityHistoryRecords = traces   
| where timestamp < assignmentAttemptTime   
| extend customDim = parse_json(customDimensions)   
| extend agentid = tostring(customDim["powerplatform.analytics.resource.id"])   
| extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])   
| where subscenario == "AgentStatusAndCapacity" or subscenario == 'CSRStatusandCapacityDetails' 
| extend cpparsed = parse_json( tostring(customDim["omnichannel.capacity_profile"])) 
| where cpparsed == "" 
| extend BasePresenceStatus = tostring(customDim["omnichannel.current_base_presence"]) 
| extend PresenceId = tostring(customDim["omnichannel.current_presence_id"]) 
| where agentid == agentId 
| project statusCapacityHistoryRecordedTime = timestamp, agentid, subscenario, agentConfig = customDim, BasePresenceStatus, PresenceId 
| summarize arg_max(statusCapacityHistoryRecordedTime, *) by agentid 
| order by statusCapacityHistoryRecordedTime desc ; 
let agentNames = traces  
| where timestamp > ago(2d)  
| extend customDim = parse_json(customDimensions)  
| extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])  
| where subscenario == "AgentNameConfig" 
| extend agentInfo = tostring(customDim["omnichannel.data"])  
| extend agentInfoParsed = parse_json(agentInfo)  
| mv-expand keyValue = bag_keys(agentInfoParsed)  
| project agentid = tostring(keyValue), agentName = tostring(agentInfoParsed[tostring(keyValue)]), timestamp 
| summarize arg_max(timestamp, *) by agentid; 
statusCapacityHistoryRecords 
| join kind=leftouter agentNames on agentid 
| project statusCapacityHistoryRecordedTime, agentid, agentName, BasePresenceStatus, PresenceId
```

Use the following query to determine the unit capacity of service representatives at a point in time.

```kusto

let assignmentAttemptTime = now();  // Fill in the timestamp   
let agentId = '92a1375c-e9dc-ef11-a72f-000d3a3ad269'; // Fill in the System User Id of the agent 
let statusCapacityHistoryRecords = traces   
| where timestamp < assignmentAttemptTime   
| extend customDim = parse_json(customDimensions)   
| extend agentid = tostring(customDim["powerplatform.analytics.resource.id"])   
| extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])   
| where subscenario == "AgentStatusAndCapacity" or subscenario == 'CSRStatusandCapacityDetails' 
| extend cpparsed = parse_json( tostring(customDim["omnichannel.capacity_profile"])) 
| where cpparsed == "" 
| extend UnitAvailableCapacity = tostring(customDim["omnichannel.available_capacity.units"]) 
| where agentid == agentId 
| project statusCapacityHistoryRecordedTime = timestamp, agentid, subscenario, agentConfig = customDim, UnitAvailableCapacity 
| summarize arg_max(statusCapacityHistoryRecordedTime, *) by agentid 
| order by statusCapacityHistoryRecordedTime desc ; 
let agentNames = traces  
| where timestamp > ago(2d)  
| extend customDim = parse_json(customDimensions)  
| extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])  
| where subscenario == "AgentNameConfig" 
| extend agentInfo = tostring(customDim["omnichannel.data"])  
| extend agentInfoParsed = parse_json(agentInfo)  
| mv-expand keyValue = bag_keys(agentInfoParsed)  
| project agentid = tostring(keyValue), agentName = tostring(agentInfoParsed[tostring(keyValue)]), timestamp 
| summarize arg_max(timestamp, *) by agentid; 
statusCapacityHistoryRecords 
| join kind=leftouter agentNames on agentid 
| project statusCapacityHistoryRecordedTime, agentid, agentName, UnitAvailableCapacity
```

Use the following query to list all service representatives in a queue at a point in time.

```kusto

let assignmentAttemptTime = now() ;  // Fill in the timestamp   
let lwiQueueId = "05a59008-f63a-f011-b4cb-6045bd070c8e"; // Fill in queue id of the work item   
let agentConfigs = traces   
| extend customDim = parse_json(customDimensions)   
| extend agentid = tostring(customDim["powerplatform.analytics.resource.id"])   
| extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])   
| extend agentQueues = tostring(customDim["omnichannel.queue.ids"])   
| where subscenario == "AgentConfiguration"  or subscenario == 'CSRConfigurationDetails' 
| where agentQueues contains lwiQueueId   
| where timestamp < assignmentAttemptTime   
| project agentConfigRecordedTime = timestamp, agentid, subscenario, agentConfig = customDim   
| order by agentConfigRecordedTime desc   
| summarize arg_max(agentConfigRecordedTime, *) by agentid;   
let agentids = agentConfigs  
| project agentid;  
let latestagentConfig=traces  
| extend customDim = parse_json(customDimensions)  
| extend agentid = tostring(customDim["powerplatform.analytics.resource.id"])  
| extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])  
| extend agentQueues = tostring(customDim["omnichannel.queue.ids"])  
| extend agentProfiles = tostring(customDim["omnichannel.capacity_profile.ids"])  
| where subscenario == "AgentConfiguration" or subscenario == 'CSRConfigurationDetails' 
| where timestamp < assignmentAttemptTime  
| where agentid in (agentids)  
| project agentConfigRecordedTime = timestamp, agentid, subscenario, agentConfig = customDim,agentQueues,agentProfiles  
| order by agentConfigRecordedTime desc  
| summarize arg_max(agentConfigRecordedTime, *) by agentid;  
let agentNames = traces  
| where timestamp > ago(2d)  
| extend customDim = parse_json(customDimensions)  
| extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])  
| where subscenario == "AgentNameConfig" 
| extend agentInfo = tostring(customDim["omnichannel.data"])  
| extend agentInfoParsed = parse_json(agentInfo)  
| mv-expand keyValue = bag_keys(agentInfoParsed)  
| project agentid = tostring(keyValue), agentName = tostring(agentInfoParsed[tostring(keyValue)]), timestamp  
| summarize arg_max(timestamp, *) by agentid; 
let latestagentConfigInQueue = latestagentConfig  
| join kind=leftouter agentNames on agentid 
| where agentQueues contains lwiQueueId  
| project agentConfigRecordedTime , agentid, agentName; 
latestagentConfigInQueue

```

Use the following query to list the capacity profiles of service representatives at a point in time.

```kusto

let assignmentAttemptTime = now(); // Fill in timestamp of assignment attempt  
let agentId = '92a1375c-e9dc-ef11-a72f-000d3a3ad269'; // Fill in the System User Id of the agent 
let agentConfigs = traces  
| extend customDim = parse_json(customDimensions)  
| extend agentid = tostring(customDim["powerplatform.analytics.resource.id"])  
| extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])  
| where subscenario == "AgentConfiguration" or subscenario == 'CSRConfigurationDetails' 
| where agentid == agentId 
| extend agentProfiles = tostring(customDim["omnichannel.capacity_profile.ids"])  
| mv-expand profileIds = parse_json(agentProfiles) 
| where timestamp < assignmentAttemptTime  
| project agentConfigRecordedTime = timestamp, profileIds, agentProfiles, agentid, subscenario, agentConfig = customDim  
| order by agentConfigRecordedTime desc  
| summarize arg_max(agentConfigRecordedTime, *) by agentid;  
let capacityprofiles1 = agentConfigs  
| mv-expand profileIds = parse_json(agentProfiles)  
| project profileIds;  
let statusCapacityHistoryRecords = traces  
| extend customDim = parse_json(customDimensions)  
| extend agentid = tostring(customDim["powerplatform.analytics.resource.id"])  
| extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])  
| extend cpparsed = parse_json( tostring(customDim["omnichannel.capacity_profile"])) 
| extend capacityProfileId = tostring( cpparsed["CapacityProfileId"] )  
| extend TotalCapacity = tostring( cpparsed["AvailableCapacity"] )  
| extend AvailableCapacity = tostring( cpparsed["DefaultMaxCapacity"] )  
| where subscenario == "AgentStatusAndCapacity" or subscenario == 'CSRStatusandCapacityDetails' 
| where agentid == agentId 
| where capacityProfileId in (capacityprofiles1)  
| where timestamp < assignmentAttemptTime  
| project statusCapacityHistoryRecordedTime = timestamp, agentid, TotalCapacity, AvailableCapacity, subscenario, agentStatusAndCapacity = customDim, capacityProfileId  
| order by statusCapacityHistoryRecordedTime desc  
| summarize arg_max(statusCapacityHistoryRecordedTime, *) by agentid, capacityProfileId;  
let agentNames = traces  
| where timestamp > ago(2d)  
| extend customDim = parse_json(customDimensions)  
| extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])  
| where subscenario == "AgentNameConfig"
| extend agentInfo = tostring(customDim["omnichannel.data"])  
| extend agentInfoParsed = parse_json(agentInfo)  
| mv-expand keyValue = bag_keys(agentInfoParsed)  
| project agentid = tostring(keyValue), agentName = tostring(agentInfoParsed[tostring(keyValue)]), timestamp  
| summarize arg_max(timestamp, *) by agentid; 
statusCapacityHistoryRecords  
| join kind=leftouter agentNames on agentid 
| project statusCapacityHistoryRecordedTime, agentName, agentid, capacityProfileId, TotalCapacity, AvailableCapacity
```

Use the following query to list the skills of service representatives at a point in time.

```Kusto

let assignmentAttemptTime = now();// Fill in timestamp of assignment attempt   
let agentId = '92a1375c-e9dc-ef11-a72f-000d3a3ad269'; // Fill in the System User Id of the agent   
let agentConfigs = traces   
| extend customDim = parse_json(customDimensions)   
| extend agentid = tostring(customDim["powerplatform.analytics.resource.id"])   
| extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])   
| extend skillData = parse_json(tostring(customDim["omnichannel.associated_skills"]) ) 
| where subscenario == "AgentConfiguration" or subscenario == 'CSRConfigurationDetails' 
| where agentid == agentId 
| where timestamp < assignmentAttemptTime   
| project agentConfigRecordedTime = timestamp, agentid, subscenario, agentConfig = customDim, skillData 
| order by agentConfigRecordedTime desc 
| summarize arg_max(agentConfigRecordedTime, *) by agentid;  
let agentNames = traces  
| where timestamp > ago(2d)  
| extend customDim = parse_json(customDimensions)  
| extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])  
| where subscenario == "AgentNameConfig" or subscenario == 'CSRConfigurationDetails' 
| extend agentInfo = tostring(customDim["omnichannel.data"])  
| extend agentInfoParsed = parse_json(agentInfo)  
| mv-expand keyValue = bag_keys(agentInfoParsed)  
| project agentid = tostring(keyValue), agentName = tostring(agentInfoParsed[tostring(keyValue)]), timestamp  
| summarize arg_max(timestamp, *) by agentid; 
agentConfigs 
| mv-expand skillEntry = skillData 
| extend  
    CharacteristicId = tostring(skillEntry.CharacteristicId), 
    RatingValue = toint(skillEntry.RatingValue), 
    SkillType = toint(skillEntry.SkillType), 
    RatingModelMin = toint(skillEntry.RatingModelMin), 
    RatingModelMax = toint(skillEntry.RatingModelMax) 
| join kind=leftouter agentNames on agentid 
| project agentid, agentName, CharacteristicId, RatingValue, SkillType, RatingModelMin, RatingModelMax
```

## Track manual assignments, consult, and transfers for a work item

Use the following query to list the manual assignments of a work item with the automated attempts.

```kusto
traces
| extend customDim = parse_json(customDimensions)
| extend lwiid = tostring(customDim["powerplatform.analytics.resource.id"])
| extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])
| where subscenario == "CSRAssignment" or subscenario == "ManualAssignment"
//| where lwiid == "ee19abec-6e9c-4c42-9040-df6db34e1072" // Fill in the conversation id
| extend isAgentAssigned = tostring(parse_json(tostring(customDim["omnichannel.assignment.status"]))["IsAgentAssigned"])
| project timestamp, lwiid, subscenario, isAgentAssigned, customDim
| order by timestamp asc
```

## Transfer attempts and transfers with other assignment attempts

Use the following query to view how many work items were attempted for transfer and assignment.

```kusto
traces
| extend customDim = parse_json(customDimensions)
| extend lwiid = tostring(customDim["powerplatform.analytics.resource.id"])
| extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])
| where lwiid == "9df2b1b5-ade8-4c59-964b-056ef2e5d6a5" // Fill in the conversation id
| project timestamp, lwiid, subscenario, customDim
| order by timestamp asc
```

## Consults with other assignment attempts

Use the following query to view consult attempts of representatives with other representatives.

```kusto

traces
| extend customDim = parse_json(customDimensions)
| extend lwiid = tostring(customDim["powerplatform.analytics.resource.id"])
| extend subscenario = tostring(customDim["powerplatform.analytics.subscenario"])
| where lwiid == "ee19abec-6e9c-4c42-9040-df6db34e1072" // Fill in the conversation id
| project timestamp, lwiid, subscenario, customDim
| order by timestamp asc
```

## Conversations that ended unsuccessfully

Use the following query to determine the conversations that ended unsuccessfully.

```kusto
Traces
| extend customDim = parse_json(customDimensions)
| extend eventType    = tostring(customDim["type"])
| extend workitem     = tostring(customDim["powerplatform.analytics.resource.id"])
| extend routingStage = tostring(customDim["powerplatform.analytics.subscenario"])
| extend channelType  = coalesce(tostring(customDim["omnichannel.channel.type"]), tostring(customDim["ChannelType"]))
| extend callId       = tostring(customDim["omnichannel.call.id"])
| extend callStatus   = toint(customDim["CallStatusCode"])
| where eventType == "CallEndDiagnosticEvent"
| where callStatus != 0 and isnotnull(callStatus)
| project timestamp, eventType, workitem, callId, routingStage, channelType, callStatus, customDimensions
```

## End-to-end conversation tracing

Use the following query to track the events that occur across the course of a conversation.

```kusto
Traces 
| extend customDim = parse_json(customDimensions) 
| extend conversationId = tostring(customDim["powerplatform.analytics.resource.id"]) 
| extend routingStage = tostring(customDim["powerplatform.analytics.subscenario"]) 
| extend channelType = coalesce(tostring(customDim["omnichannel.channel.type"]), tostring(customDim["ChannelType"])) 
| extend callId = tostring(customDim["omnichannel.call.id"]) 
| where conversationId == [Insert Your Work Item ID] 
| project timestamp, conversationId, callId, routingStage, channelType, customDimensions 
```

## Use Azure Data Explorer dashboards with Application Insights queries

Apart from using Kusto queries directly within the Azure portal, you can use Azure Data Explorer Dashboards to visualize the results of these queries and create interactive, real-time reports. It's a powerful way to monitor and analyze the telemetry data from your Dynamics 365 Customer Service, Contact Center environment at a glance. We created a dashboard that you can directly import into your Azure Data Explorer environment.  

The dashboard file and the instructions to link it to your ApplicationInsights subscription are in the GitHub repo at [https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/Customer%20Service/ComponentLibrary/AppInsights-Telemetry/ConversationDiagnostics).  

The dashboard includes the **Conversation diagnostics** page and the **Unified routing diagnostics** page as outlined in the following list:
 
- **Conversation diagnostics page**: This page displays diagnostics for a range of scenarios, including the following list:
    - Conversation state flow for different conversation IDs.
    - Fallback queue routing.
    - Conversations that triggered overflow.
    - Conversations rejected by multiple agents.
    - Top Agent IDs with high reject count.
    - Conversations where agent assignment took more than two minutes.
    - Conversations where agent handle time was more than five minutes.

The following image illustrates the layout of the page based on sample data.

   :::image type="content" source="media/conversation-diagnostics/Dashboard.png" alt-text="Screenshot of the Azure Data Explorer sample Dashboard." lightbox="media/conversation-diagnostics/Dashboard.png":::

- **Unified routing diagnostics page**: This page displays diagnostics for a range of scenarios over time. You can select a work item, and then, through the context menu, you can set a cross-filter option for all tiles to load the diagnostics data for the work item.

The following image illustrates the layout of the page based on sample data.

   :::image type="content" source="media/conversation-diagnostics/unified-routing-dashboard.png" alt-text="Screenshot of the work items in unified routing in the Azure Data Explorer sample dashboard." lightbox="media/conversation-diagnostics/unified-routing-dashboard.png":::

After your dashboard is ready, you can do one of the following:

- Share the dashboard with anyone in your organization by granting them access to view or edit the dashboard in Azure Data Explorer.  
- Alternatively, embed the dashboard into your own portal or website using the embedding features provided by Azure.  

By integrating your analytics and insights data into an Azure Data Explorer dashboard, you can continuously monitor your Dynamics 365 Customer Service and Dynamics 365 Contact Center environments.

### Related information

[Configure conversation diagnostics](/dynamics365/customer-service/administer/configure-conversation-diagnostics)  
[Subscenarios in conversation diagnostics](/dynamics365/customer-service/administer/conversation-diagnostics-subscenarios)  
[Diagnose contact center health](/dynamics365/contact-center/use/diagnose-dashboard)  
