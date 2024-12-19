---
title: Telemetry insights overview (preview) 
description: Learn how to use telemetry insights to analyze the performance of a project in the Dynamics 365 Implementation Portal. This article provides an overview on capabilities and rules.
author: dereklh77
ms.author: meesposi
ms.topic: conceptual
ms.date: 12/18/2024
---
# Telemetry insights overview (preview)
<!--[This article is prerelease documentation and is subject to change.]-->

> [!IMPORTANT]
> Telemetry insights in the Dynamics 365 Implementation Portal is in public preview. Capabilities that are in preview aren't meant for production use and can have limited functionality. These features are available before an official release so that our customers can get early access and provide feedback.
> By accessing or using telemetry insights, you accept the [Microsoft Preview Terms of Service](https://go.microsoft.com/fwlink/?linkid=2242556).

**Telemetry insights** detects optimization opportunities and provides actionable guidance based on usage patterns in environments. Results surface with severity indicators as they require attention.

Learn how to set up telemetry insights at [Set up telemetry insights (preview)](telemetry-insights-set-up.md).  

## Performance-related rules

The following table describes some of the most popular performance-related rules. They're designed to enhance your environment's efficiency.

| Rule Name | Description |
|--|--|
|*Identify Percentage of Slow Network Users* |This rule evaluates the overall percentage of users experiencing slow network performance.|
| *Identification of Network Latency and Throughput by Country*| This rule identifies the count of users and their associated bandwidth and latency for network connections. |
| *Evaluate Timeouts from Async Ribbon Rule Evaluations*|This rule identifies all method names where the **Ribbon Rule Evaluation** code either fails to resolve or times out.  When promises in the **Ribbon Rule Evaluation** code are not properly resolved or rejected, the calling code continues to wait, leading to a timeout and adversely affecting form load times. |
| *Identify the source of OnLoad Sync calls*  |This rule identifies the origins of synchronous calls triggered by form onload scripts. |
| *Identify the source of Role calls* |This rule identifies the origin of synchronous calls made specifically to retrieve the assigned roles for a user. |
| *Identify Save Form call on Loading of Form* |This rule identifies and quantifies form loads affected by the unnecessary triggering of a 'Save' operation during the form load process. |

> [!TIP]
> The Dynamics 365 Implementation Portal includes a page with the number of active rules and some info about the rules.

## Telemetry recommendations

The **Telemetry recommendations** page displays various results for all environments that have been configured and approved for telemetry insights.

> [!NOTE]
> Once you've completed the setup of telemetry, results start showing up, based on the purpose of the environment. Recommendations for production environments show up about 15 minutes later. Recommendations for nonproduction environments start showing up about 24 hours after you completed the setup.

The results are grouped by **result** and **environment**.  

| Column | Description |
|------|-------------|
| **Last updated** | Shows the last time an optimization opportunity was detected for the specified environment and returned an actionable result.|
| **History** | Provides a view into the last seven actionable results generated for the environment with visual severity indicators. |
| **Read more**| Expands the result to display actionable guidance based on the associated result. Further detail is provided with selectable history dates that will adjust the guidance based on that date's specific results. By selecting a date and selecting **View details**, a new view opens providing additional technical details that vary based on each result.|

Choose the **Ideas** button to provide feedback on the telemetry insights. Alternatively, provide feedback on specific results by choosing the thumbs-up or thumbs-down buttons.

You can apply filters to narrow down results by tenant, environment, and purpose. Search can locate result names and descriptions.  

## Related information

- [Give or get consent to data sharing](data-sharing-consent.md)  
- [Manage projects in Dynamics 365 Implementation Portal](manage-projects.md)  
- [Dynamics 365 Implementation Portal](overview.md)  
- [Overview of capabilities for analytics in Dynamics 365 Customer Service](../resources/analytics-capabilities.md)  
- [Application lifecycle management for analytics on data model customizations](../resources/analytics-alm-custom-reports.md)  
- [Monitor and optimize your Dynamics 365 environments](../implementation-guide/service-solution-monitor-service-health.md)  
- [Create or join a project in the Implementation Portal](onboard-project.md)  
