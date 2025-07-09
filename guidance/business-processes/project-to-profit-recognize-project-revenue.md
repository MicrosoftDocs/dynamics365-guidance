---
title: Recognize Project Revenue in Dynamics 365  
description: Learn how to set up, configure, and manage revenue recognition in Dynamics 365 Project Operations and Dynamics 365 Finance.  
author: edupont04  
contributors:  
ms.topic: concept-article  
ms.date: 04/22/2025
ms.author: edupont  
ms.reviewer: edupont  
---
# Recognize project revenue

***Applies to: Dynamics 365 Finance, Dynamics 365 Project Operations***

This article describes the setup, configuration, and design considerations for creating and managing revenue recognition in Dynamics 365 Project Operations and Dynamics 365 Finance. The article reflects a business process in the [Manage project financials](project-to-profit-manage-project-financials-overview.md) business process area within the [Project to profit](project-to-profit-overview.md) end-to-end scenario.

Revenue recognition and invoicing are independent of each other. Organizations follow different approaches to arrive at percentage of revenue to recognize, including but not limited to the approaches in the following list:

- straight-line method where revenue is recognized on a prorated basis over the project duration
- based on progress shown in the work breakdown structure
- percentage of actual cost compared to total budgeted cost
- percentage of actual hours compared to total budgeted hours
- any other method as project manager deems appropriate

Generally, revenue is recognized monthly. It is a transactional activity that organizations run in [the *operate* phase](../implementation-guide/success-by-design.md#operate) of an implementation project.

## Stakeholders

Many people in an organization should contribute to the decision-making process and design of the *recognize project revenue* business process in Dynamics 365. Stakeholders include, but are not limited to, the following list:

- Finance stakeholders – examples: CFO, accounting manager
- Operations stakeholders – examples: project manager

Finance stakeholders are responsible for recognizing revenue. Operations stakeholders are responsible for maintaining margins and revising estimates as needed.

## Recognize project revenue process flow

The following diagram illustrates the business process for both project operations that are of any deployment type, including [Project Operations Integrated with ERP](/dynamics365/project-operations/environment/project-operations-integrated-deployment-overview) and [Project Operations for manufacturing](/dynamics365/project-operations/prod-pma/project-operations-prod-order-deployment-overview).

:::image type="content" source="media/project-to-profit-recognize-project-revenue-flow.svg" alt-text="Flow diagram for the business process, which is explained in the paragraphs after the image." lightbox="media/project-to-profit-recognize-project-revenue-flow.svg":::

The *recognize project revenue* business process flow diagram covers the following steps for the *finance manager* role.

1. Start
1. *Identify revenue streams*.
1. *Calculate revenue*.
1. *Review revenue calculations*.
1. *Approve revenue*.

    1. If the revenue is approved, then *record revenue*.
    1. If the revenue is not approved, then *revise revenue calculations*, and then *approve revenue* again.
1. End
<!-- Removing because these steps do not match the February 2025 version of the business process.
1. Define a cost template.  
2. Define a period code.  
3. Define project groups for stocked deployments or project cost and revenue profile rules for non-stocked deployments.  
4. Define the ledger posting setup.  
5. Define milestones for non-stocked deployments in project operations within customer engagement environments. For stocked deployments in Dynamics 365 Finance, define on-account transactions.  
6. Enter hour, expense, and item estimates for non-stocked deployments in project operations CE environments. Enter hour, expense, and item estimates for stocked deployments in Dynamics 365 Finance.  
7. Recognize revenue based on the completion method selected in the cost template.  
8. Eliminate the revenue project after fully recognizing revenue.

The project manager and accounting manager complete all steps in Dynamics 365 Finance.   -->

## Implement the business process

The primary difference between the two deployment versions regarding revenue recognition is that in stocked or production-based deployment, the progress percentage in the effort tracking view is also used to recognize revenue.

### Implementation in non-stocked deployments of project operations

In Dynamics 365 Project Operations, projects can be deployed as non-stocked deployments. This type of deployment does not support inventoriable materials to be consumed.

[!INCLUDE [bus-proc-config-table-explained](../includes/bus-proc-config-table-explained.md)]

| Process step | Process stage | Process modifier | Application: Navigation and Entity |
|--------------|---------------|------------------|-------------------------------------|
| [Period types](/dynamics365/project-operations/project-accounting/period-types) | Initialize; Fundamental; Configuration | Gold | **FIN:** Organization administration > Setup > Calendars > Period types<br>**DMF:** Project periods; Project period lines |
| [Set up cost templates](/dynamics365/project-operations/revenue-recognition/rev-rec-cost-templates) | Initialize; Fundamental; Configuration | Gold | **FIN:** Project management and accounting > Setup Estimates > Cost template<br>**DMF:** Project cost template; Project cost template lines; Project cost template line categories |
| [Configure accounting for billable projects](/dynamics365/project-operations/project-accounting/configure-accounting-billable-projects) | Initialize; Fundamental; Configuration | Gold | **FIN:** Project management and accounting > Setup > Posting > Project cost and revenue profiles<br>**DMF:** Project cost and revenue profiles |
| [Configure project categories](/dynamics365/project-operations/project-accounting/configure-project-categories) | Initialize; Fundamental; Configuration | Gold; more than one required. | **FIN:** Project management and accounting > Setup > Categories > Shared categories<br>**PROJOPS:** Settings > General > Transaction categories<br>**DMF:** Shared categories |
| [Ledger posting setup](/dynamics365/project-operations/project-accounting/configure-accounting-billable-projects) | Initialize; Fundamental; Configuration | Gold | **FIN:** Project management and accounting > Setup > Posting > Ledger posting setup<br>**DMF:** Project ledger posting definition |
| [Revenue recognition](/dynamics365/project-operations/revenue-recognition/revenue-recognition-overview) | Initialize; Fundamental; Configuration | Gold | **FIN:** Project management and accounting > Setup > Posting > Project cost and revenue profiles<br>**DMF:** Project cost and revenue profiles |
| [Contract line-based revenue recognition with Project operations](/dynamics365/project-operations/revenue-recognition/revenuerecogntionforcontractlines) | Initialize; Fundamental; Configuration | Gold | **FIN:** Project management and accounting > Projects > Fixed price revenue estimate projects<br>**DMF:** NA |
| [Cost to complete methods](/dynamics365/project-operations/revenue-recognition/cost-complete-methods) | Initialize; Fundamental; Configuration | Gold | **FIN:** Project management and accounting > Projects > Fixed price revenue estimate projects<br>**DMF:** NA |
| [Fixed price revenue estimate projects](/dynamics365/project-operations/revenue-recognition/rev-rec-percentage-completion-method) | Operate; Optional; Operational | Continuous | **FIN:** Project management and accounting > Projects > Fixed price revenue estimate projects<br>**DMF:** NA |
| [Manage revenue estimates](/dynamics365/project-operations/revenue-recognition/rev-rec-completed-contract-method) | Operate; Optional; Operational | Continuous | **FIN:** Project management and accounting > Projects > Fixed price revenue estimate projects<br>**DMF:** NA |

### Implementation in stocked deployments of project operations

In Dynamics 365 Finance, projects can be deployed as stocked deployments. This type of deployment also supports the consumption of inventoriable materials.

[!INCLUDE [bus-proc-config-table-explained](../includes/bus-proc-config-table-explained.md)]

| Process step | Process stage | Process modifier | Application: Navigation and Entity |
|--------------|---------------|------------------|-------------------------------------|
| [Period types](/dynamics365/project-operations/project-accounting/period-types) | Initialize; Fundamental; Configuration | Gold | **FIN:** Organization administration > Setup > Calendars > Period types<br>**DMF:** Project Periods; Project period lines |
| [Set up cost templates](/dynamics365/project-operations/revenue-recognition/rev-rec-cost-templates) | Initialize; Fundamental; Configuration | Gold | **FIN:** Project management and accounting > Setup > Estimates > Cost template<br>**DMF:** ProjectCostTemplate; ProjectCostTemplateLines |
| [Forecast model](/dynamics365/project-operations/prod-pma/create-forecast-models-project-budgets) | Initialize; Fundamental; Configuration | Gold | **FIN:** Project management and accounting > Setup > Forecasts > Forecast models<br>**DMF:** Forecast models |
| [Configure project categories](/dynamics365/project-operations/project-accounting/configure-project-categories) | Initialize; Fundamental; Configuration | Gold; More than one required. | **FIN:** Project Management and Accounting > Setup > Categories > Project Categories<br>**DMF:** Project Category Group; Shared category; Project Category |
| [Ledger posting setup](/dynamics365/project-operations/project-accounting/configure-accounting-billable-projects) | Initialize; Fundamental; Configuration | Gold | **FIN:** Project management and accounting > Setup > Posting > Ledger posting setup<br>**DMF:** Project ledger posting definition |
| [Revenue recognition](/dynamics365/project-operations/revenue-recognition/revenue-recognition-overview) | Initialize; Fundamental; Configuration | Gold | **FIN:** Project management and accounting > Periodic > Revenue recognition > Create revenue recognition;<br>Project management and accounting > Periodic > Revenue recognition > Calculate revenue recognition;<br>Project management and accounting > Periodic > Revenue recognition > Post revenue recognition<br>**DMF:** NA |
| [Cost to complete methods](/dynamics365/project-operations/revenue-recognition/cost-complete-methods) | Initialize; Fundamental; Configuration | Gold | **FIN:** Project management and accounting > Periodic > Revenue recognition > Create revenue recognition;<br>**DMF:** NA |
| [Manage revenue estimates](/dynamics365/project-operations/revenue-recognition/rev-rec-completed-contract-method) | Operate; Optional; Operational | Continuous | **FIN:** Project management and accounting > Periodic > Revenue recognition > Create revenue recognition;<br>Project management and accounting > Periodic > Revenue recognition > Calculate revenue recognition;<br>Project management and accounting > Periodic > Revenue recognition > Post revenue recognition<br>**DMF:** NA |

## Next steps

To implement Dynamics 365 solutions to assist with your *recognize project revenue* business processes, use the following resources and steps to learn more. (Links are added when the articles are ready.)

1. [Develop project strategy](project-to-profit-develop-project-strategy-overview.md)  
1. [Manage project contracts](project-to-profit-manage-project-contracts-overview.md)
1. [Plan projects](project-to-profit-manage-project-scope-schedule-overview.md)  
1. [Manage project delivery](project-to-profit-deliver-project-work.md)
1. [Manage project financials](project-to-profit-manage-project-financials-overview.md)  

    1. *Correct project transactions*
    1. *Convert projects to fixed assets*
    1. *Invoice project milestones*
    1. *Invoice project transactions*
    1. *Recognize project revenue* (the article that you're currently reading)
1. [Analyze project performance](project-to-profit-monitor-analyze-project-performance-overview.md)

<!-- ## Related patterns

The following patterns are available to help guide your implementation of the recognize project revenue business process.

- <span class="mark">Pattern link 1</span>  
- <span class="mark">Pattern link 2</span>  
- <span class="mark">Pattern link n…</span>   -->

## Related resources

You can use the following resources to learn more about the *recognize project revenue* process in Dynamics 365.

- [Dynamics 365 Project Operations Demonstration - TechTalk (youtube.com)](https://www.youtube.com/watch?v=grtEq39RNt0&t=22s)
- [Revenue recognition overview - Dynamics 365 Project Operations](/dynamics365/project-operations/revenue-recognition/revenue-recognition-overview)  
- [Manage project financials business process area](project-to-profit-manage-project-financials-overview.md)  
- [Project to profit end-to-end scenario](project-to-profit-overview.md)  
<!-- ## Tags

**Industries:** Services (70-89)  

**Stakeholders:** Finance, Operations, Project Management, Sales  

**Products:** Dynamics 365 Finance, Dynamics 365 Project Operations   -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Ruchi Gupta](https://www.linkedin.com/in/caruchigupta11/) \| Deputy Manager at Protiviti India Member Firm

Other contributors:

- Satya Teki \| Senior FastTrack Solution Architect
