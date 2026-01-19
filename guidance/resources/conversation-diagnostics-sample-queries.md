---
title: Sample queries and dashboards for conversation diagnostics
description: Use sample queries to retrieve conversation diagnostics for Dynamics 365 Contact Center from Application Insights.
author: neeranelli
ms.author: nenellim
ms.reviewer: nenellim
ms.topic: concept-article
ms.collection:
ms.date: 01/19/2026
ms.custom:
  - bap-template
  - O25-Service
---

# Sample queries and dashboards for conversation diagnostics

Learn about the queries that you can use to retrieve the diagnostics data for unified routing from Application Insights.

## Fallback queues

**Purpose**: Diagnose number of work items routed to fallback queues.  

**Query**

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

## Overflow handling

**Purpose**: Diagnose number of work items where overflow is trigger.  

**Query**

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

**Purpose**: Diagnose customer service representatives (service representatives or representatives) who reject new assignments (by conversationId).  

**Query**

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

**Purpose**: Diagnose representatives who reject new assignments (by representatives).  

**Query**

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

**Purpose**: Diagnose conversations where representative assignment took longer than two minutes.  

**Query**

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

**Purpose**: Determine why the conversation isn't assigned.

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

1. Identify the last assignment attempt that is denoted by "CSRAssignment" sub-scenario.

1. Get the IDs of the representative whom we want to check. Let’s say we want to check why this conversation was assigned to Service representative with id 8874e390-9ecc-ef11-a72f-000d3a3652d6 instead of Service representative with id 92a1375c-e9dc-ef11-a72f-000d3a3ad269 or Service representative with id 7ac24088-a804-f011-bae2-000d3a3172e5.

1. Identify the assignment rules used to assign the conversation, the conversation queue and the conversation requirements.

1. Identify the presence, unit capacity, capacity profiles, and skills of the representatives shortlisted from Step 3 at the time of assignment.

    **Query**:

    ```Kusto
    
    let assignmentAttemptTime = now();  // Fill in timestamp of assignment attempt  
    let agentids = dynamic(["92a1375c-e9dc-ef11-a72f-000d3a3ad269", "8874e390-9ecc-ef11-a72f-000d3a3652d6", "fc19139b-facd-ef11-a72e-0022480aa3fe"]); //Fill in system user ids of Customer Service Representatives
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

**Purpose**: Presence of service representatives at a point in time.

**Query**

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

**Purpose**: Unit capacity of service representatives at a point in time.

**Query**

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

**Purpose**: List all service representatives in a queue at a point in time.

**Query**

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

**Purpose**: Capacity profiles of service representatives at a point in time.

**Query**

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

**Purpose**: Skills of service representatives at a point in time.

**Query**

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

**Purpose**: Manual assignments of work item with the automated attempts.

**Query**

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

**Purpose**: Transfer of work item and assignment attemps.

**Query**

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

**Purpose**: View consult attempts with other representatives.

**Query**

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

**Purpose**: Determine the conversations that ended unsuccessfully.

**Query**

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

**Purpose**: Track the events that occur across the course of a conversation.

**Query**

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

The dashboard file and the instructions to link it to your ApplicationInsights subscription are in the GitHub repo at [https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/ComponentLibrary/AppInsights-Telemetry/ConversationDiagnostics).  

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