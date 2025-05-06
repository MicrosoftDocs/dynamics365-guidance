---
title: Telemetry insights overview
description: Learn how to use Telemetry insights to identify proactive optimization opportunities for your Dynamics 365 environments in the Dynamics 365 Implementation Portal. This article provides an overview on capabilities.
author: meesposi
ms.author: meesposi
ms.topic: concept-article
ms.date: 04/07/2025
---
# Telemetry insights overview


In the Dynamics 365 Implementation Portal, **Telemetry insights** detects optimization opportunities and provides actionable guidance based on usage patterns in your Dynamics 365 environments. Results are grouped by tenant and ranked by impact. The ranking by impact helps you prioritize where to take action.

Learn how to set up telemetry insights at [Set up telemetry insights](telemetry-insights-set-up.md).  

## Telemetry recommendations

The **Telemetry recommendations** page displays various results for all environments that have been set up and approved for telemetry insights.
> [!NOTE]
> Once you complete the setup of telemetry, results start showing up based on the purpose of the environment. Recommendations for production environments show up about 1 hour later. Recommendations for nonproduction environments start showing up about 24 hours after you completed the setup.

The results are grouped by **result** and **tenant**. Search can easily narrow down results by impact, category, rule name, or description. The number of rules that run for an environment display the entire library. 

| Column | Description |
|------|-------------|
| **Impact** | Shows a suggested priority for a user to take action based on the category of rule and the associated severity of the result.|
| **Category** | Provides a logical grouping of rule types. |
| **Scope**| Provides the Dynamics 365 app context. |
| **Dismiss**| Giuves you the option to hide or filter certain results from view. |

## Telemetry guidance and details

Select any result to view recommendations and next-step guidance. A table of results shows up to 30 days of data that you can filter on or export to analyze the data further. You can apply filters to focus on results by environment and purpose. Results are specific to an environment, and they're marked with a severity indicator. Provide feedback on specific results by choosing the thumbs-up or thumbs-down buttons.
 
## Rule examples by category

The following table describes some of the most popular performance-related rules. They're designed to enhance your environment's efficiency.

| Rule Name | Category | Scope | Description |
|--|--|--|--|
|*Identify Percentage of Slow Network Users* | Performance | Customer engagement apps |This rule evaluates the overall percentage of users experiencing slow network performance.|
| *Identification of Network Latency and Throughput by Country*| Performance | Customer engagement apps | This rule identifies the count of users and their associated bandwidth and latency for network connections. |
|*Evaluate Sync Call Impact*| Performance | Customer engagement apps |This rule detects the impact of sync calls on all form loads. Detail for the source of the sync calls is found in the results of the rules **Identify the source of OnLoad Sync calls**, **Identify the source of Role calls**. |
| *Identify the source of OnLoad Sync calls*  | Performance| Customer engagement apps |This rule identifies the origins of synchronous calls triggered by form onload scripts. |
| *Evaluate Timeouts from Async Ribbon Rule Evaluations*| Performance | Customer engagement apps |This rule identifies all method names where the **Ribbon Rule Evaluation** code fails to resolve or results in a timeout.<!--When promises in the **Ribbon Rule Evaluation** code are not properly resolved or rejected, the calling code continues to wait, leading to a timeout and adversely affecting form load times.--> |
|*Identify the source of Role calls* | Performance | Customer engagement apps |This rule identifies the origin of synchronous calls made specifically to retrieve the assigned roles for a user. |
|*Identify Save Form call on Loading of Form* | Performance | Customer engagement apps |This rule identifies and quantifies form loads affected by the unnecessary triggering of a *Save* operation during the form load process. |
|*Detection of slow forms*| Performance | Customer engagement apps | This rule detects slow performing forms within CE apps across a 24 hour period. |
|*Plugin sync*| Performance | Customer engagement apps | This rule identifies synchronous plugins taking more than two seconds. |
|*Evaluate size of AsyncOperationBase*| Storage | Customer engagement apps| This rule detects growth on the table used to store history of asynchronous system jobs. |
|*Evaluate size of PrincipalObjectAccess table*| Storage | Customer engagement apps | This rule detects growth on the table used to store history of user shared records and their permissions. |
|*Detection of slow forms*| Performance | Finance and operations apps | This rule detects slow performing forms in Dynamics 365 across a 24 hour period. |
|*Frequency of Real-time integrations*| Performance | Finance and operations apps | This rule detects the over-use of Real-time integrations. |
|*General journal performance check*| Performance | Finance and operations apps | This rule detects opportunities to improve General journal posting performance. |
|*Custom batch jobs not implementing retries*| Performance | Finance and operations apps | This rule identifies any custom batch jobs that are missing retry logic. |
|*Evaluate size of EventCUD table*| Storage | Finance and operations apps | This rule detects growth on the EventCUD table that can impact performance. |




> [!TIP]
> Sign in to Dynamics 365 Implementation Portal  and access the **Recommendations** page where you can view a full list of the rule library.

## Related information

- [Set up telemetry insights](telemetry-insights-set-up.md)
- [Give or get consent to data sharing](data-sharing-consent.md)  
- [Manage projects in Dynamics 365 Implementation Portal](manage-projects.md)  
- [Dynamics 365 Implementation Portal](overview.md)  
- [Overview of capabilities for analytics in Dynamics 365 Customer Service](../resources/analytics-capabilities.md)  
- [Application lifecycle management for analytics on data model customizations](../resources/analytics-alm-custom-reports.md)  
- [Monitor and optimize your Dynamics 365 environments](../implementation-guide/service-solution-monitor-service-health.md)  
- [Create or join a project in the Implementation Portal](onboard-project.md)  
