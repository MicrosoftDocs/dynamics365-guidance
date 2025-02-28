---
title: Sample queries and dashboards for conversation diagnostics (preview)
description: Use sample queries to retrieve conversation diagnostics from Application Insights.
author: neeranelli
ms.author: nenellim
ms.reviewer: nenellim
ms.topic: conceptual
ms.collection:
ms.date: 02/28/2025
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:02/28/2025
  - O25-Service
# CustomerIntent: As an admin, I want to track how our copilot is used.
---

# Sample queries and dashboards in conversation diagnostics (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Learn about the queries that you can use to retrieve the diagnostics data for unified routing from Application Insights.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/preview-note-d365.md)]

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
| where subscenario == "RTQ" and queueResult == "[Insert Your Fallback queue name]"   
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
| where subscenario == "AgentReject"  
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
Traces  
| where timestamp >= _startTime and timestamp <= _endTime  
| extend customDim = parse_json(customDimensions)  
| extend conversationId = tostring(customDim["powerplatform.analytics.resource.id"]),   
         subscenario = tostring(customDim["powerplatform.analytics.subscenario"]),  
         agentId = tostring(customDim["omnichannel.target_agent.id"]) // Extract representative ID from custom dimensions  
| where subscenario == "AgentReject"  
| summarize agentRejectionCount = count() by conversationId, agentId // Count rejections per representative per conversation  
| summarize rejectionCount = sum(agentRejectionCount),   
            agentRejectionDetails = make_list(pack('agentId', agentId, 'rejectionCount', agentRejectionCount))   
    by conversationId // Aggregate results by conversation  
| where rejectionCount > 1 // Filter conversations with more than one rejection  
| project conversationId, rejectionCount, agentRejectionDetails  
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
| where subscenario in ("RTQ", "AgentAccept")  
| project timestamp, conversationId, subscenario;  
// Find the latest RTQ before each AgentAccept  
let latestRTQsBeforeAgentAccept = subscenarios  
| where subscenario == "RTQ"  
| join kind=inner (  
    subscenarios  
    | where subscenario == "AgentAccept"  
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

## Using Azure Data Explorer dashboards with Application Insights queries

In addition to using Kusto queries directly within the Azure portal, you can use Azure Data Explorer Dashboards to visualize the results of these queries and create interactive, real-time reports. It's a powerful way to monitor and analyze the telemetry data from your Dynamics 365 Customer Service, Contact Center environment at a glance. We created a dashboard that you can directly import into your Azure Data Explorer environment.  

The dashboard file and the instructions to link it to your ApplicationInsights subscription are in the GitHub repo at [https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/ComponentLibrary/AppInsights-Telemetry/ConversationDiagnostics).  

The following image illustrates the layout of the dashboard based on sample data.

:::image type="content" source="media/conversation-diagnostics/Dashboard.png" alt-text="Screenshot of the Azure Data Expleror sample Dashboard." lightbox="media/cs-dataverse-appinsights/Dashboard.png":::

Once your dashboard is ready, you can take the following steps  

- Share the dashboard with anyone in your organization by granting them access to view or edit the dashboard in Azure Data Explorer.  
- Alternatively, embed the dashboard into your own portal or website using the embedding features provided by Azure.  

By integrating your telemetry data into an Azure Data Explorer dashboard, you can continuously monitor your Dynamics 365 Customer Service, Contact Center environments.


### Related information

[Configure conversation diagnostics](/dynamics365/customer-service/administer/configure-conversation-diagnostics)  
[Subscenarios in conversation diagnostics](/dynamics365/customer-service/administer/conversation-diagnostics-subscenarios)  