---
title: Overview of the monitor and analyze project performance business process area
description: Learn how you can use Dynamics 365 products to support the organization's business processes to monitor and analyze project performance overview.
ms.date: 11/17/2023
ms.topic: conceptual
author: edupont04
ms.author: lalithac
---

# Monitor and evaluate project elements with the monitor and analyze project performance process area

***Applies to: Dynamics 365 Business Central, Dynamics 365 Finance, Dynamics 365 Project Operations***

This article describes how you can use Dynamics 365 products to support organization's requirements to monitor and analyze project performance.

## Introduction to monitor and analyze project performance

The *monitor and analyze project performance* business process area focuses on systematically monitoring, assessing, and evaluating various project elements, including the following list:

- How much of the project scope is already delivered?  
- What's remaining?    
- What are the project costs and revenue?  
- Are there any risks?  
- Which issues prevent that the project is progressing as planned and meeting its objectives?  
 
By monitoring project performance and conducting in-depth analysis, project managers and stakeholders can gain valuable insights, make informed decisions, and take necessary corrective actions.

The process of monitoring and analyzing project performance should be established at the onset of the project. As soon as the project objectives, scope, and resources are defined, it's imperative to set up a monitoring and analysis mechanism. This way, you make sure that right from the beginning stages, there's a system in place to gauge progress, measure performance, and implement course corrections if necessary. Incorporating this business process area early also ensures that data collection is consistent throughout the project, providing more accurate insights for analysis.

## Stakeholders 

Many people across the organization should contribute to the decision-making process and design of the monitor and analyze project performance area. The following list provides examples of such stakeholders:

- **Project managers** - responsible for monitoring the project progress.

- **Steering committee** - responsible for making decisions based on project performance analysis.

- **Project sponsor** - responsible for reviewing the reports and assessing their effect.

- **Finance controller** - responsible for project budgeting, costing and analyzing financial data.

## Monitor and analyze project performance process flow 

The following diagram illustrates the *monitor and analyze project performance* business process area.

:::image type="content" source="media/project-to-profit-monitor-analyze-project-performance-flow.svg" alt-text="Flow diagram for the business process area, which is explained in the paragraphs after the image." lightbox="media/project-to-profit-monitor-analyze-project-performance-flow.svg":::

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

The *monitor and analyze project performance* business process area flow diagram covers the following steps:

1. Start

2. *Project to profit* end-to-end process

    Parallel branch of this end-to-end process is *3.Record to report* end-to-end process

    1. *Govern projects*

        Parallel branches of this sub-process are sub-processes *Manage project contracts*, *Manage project resources and schedules*, *Manage project delivery*, and *Manage project financials*

    2. *Monitor and analyze project performance*

        1. Define project metrics

        2. Define baseline for project metrics

        3. Measure or calculate project metrics

        4. Compare metrics to baselines

        5. Communicate performance to stakeholders

        6. Corrective action?

            1. Branch **Yes** leads to the downstream subprocess *Govern projects*

            2. A parallel branch for **No** leads to *Project done?*

        7. Project done?

            1. Branch **Yes** leads to 4. *End*

          2. A parallel branch for **No** leads back to  *Measure/Calculate project metrics*

      If the scope, schedule, or budgets change, the following subprocesses are downstream: *Manage project resources and schedules*, *Determine project scope and schedule*, and *Manage project financials*. *Manage project budgets* leads back to *Define baseline for project metrics*.  

3. *Record to report* end-to-end process

    1. *Record financial transactions*

    2. *Report and analyze financials and cash flow*

4. End

## Monitor and analyze project performance benefits

There are many key benefits to monitoring and measuring the success of implementing technology as part of the *monitor and analyze project performance* business process area. The following sections outline the key benefits that an organization might monitor and measure for monitor and analyze project performance. 

### Intelligent project analytics

Dynamics 365 includes project management capabilities that support intelligent analytics and reporting. Such insights gives a detailed view on the project performance, such as information about completed work, comparing forecast versus actuals, cost and revenue metrics review, and Earned Value Management analysis. When project managers use the out-of-the-box inquiries and dashboards, they get a complete overview that allows informed decisions to be made.  

Learn more at [Dynamics 365 Project Operations](/dynamics365/project-operations/) and [Project management in Dynamics 365 Business Central](/dynamics365/business-central/projects-manage-projects), respectively.  

### Integrated recourse management and financials view

In solutions with Dynamics 365 Project Operations and Dynamics 365 Finance, the ability to track and monitor project progress from opportunity to delivery gives an end-to-end view of the project. Through [integration with Microsoft Project client](/dynamics365/project-operations/prod-pma/project-integration), you can open, manage, and monitor a [work breakdown structure](/dynamics365/project-operations/prod-pma/work-breakdown-structures) for the project. The project manager can publish any changes back to Dynamics 365. The project manager gets a thorough perspective on employee workload and capacity. This way, they can make sure that deadlines and quality standards are met. The project manager also has clear budget tracking and adherence during the project's full span. In addition, data consistency is considered through the process.

### Proactive risk management

With project monitoring and analytics, the project team can recognize project issues and misalignments before they become critical, and act immediately. It's essential in laying off the foundation for effective and successful project execution and prevents financial as well as time impact.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *monitor and analyze project performance* business processes, you can use the following resources and steps to learn more.

1. [Govern projects](project-to-profit-govern-projects-overview.md)
2. [Manage project contracts](project-to-profit-manage-project-contracts-overview.md)  
3. [Manage project resources and schedules](project-to-profit-manage-project-scope-schedule-overview.md)  
4. [Manage project delivery](project-to-profit-deliver-project-work.md)  
5. [Manage project financials](project-to-profit-manage-project-financials-overview.md)  
6. *Monitor and analyze project performance*. (the article you're currently reading)  

## Related resources

You can use the following resources to learn more about the monitor and analyze project performance process in Dynamics 365.

- [Project management and accounting overview](/dynamics365/project-operations/prod-pma/overview-project-management-accounting#analyze-the-project)  
- [Microsoft Dynamics 365 Project Operations Overview Video](https://community.dynamics.com/videos/post/?postid=86ea94cd-2914-ee11-8f6e-00224827eb85)
- [Explore project cost tracking capabilities](/training/modules/explore-project-planning-execution-capabilities/6-explore-project-cost-tracking-capabilities)
- [Project forecasts and budgets](/dynamics365/project-operations/prod-pma/project-forecasts-budgets)
- [Allocate a project budget or budget revision across periods](/dynamics365/project-operations/prod-pma/tasks/allocate-project)
- [Create forecast models for project budgets](/dynamics365/project-operations/prod-pma/create-forecast-models-project-budgets)
- [Project management in Dynamics 365 Business Central](/dynamics365/business-central/projects-manage-projects)  
- [Performance Measurement Baseline: Definition \| Example \| 6-Step Guide - Project-Management.info](https://project-management.info/performance-measurement-baseline/)
<!-- 
## Tags

*Stakeholders:* Project Managers, steering committee, Project sponsor, Finance controller

*Products:* Dynamics 365 Business Central, Dynamics 365 Finance, Dynamics 365 Project Operations -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Other contributors:

- Martin Walker \|FastTrack Solution Architect\|

- Lalitha Chintamaneni \|FastTrack Solution Architect\|

- Rachel Profitt \|FastTrack Solution Architect\|

- Milda Beinaryte \|FastTrack Solution Architect\|

- Satish Panwar \|FastTrack Solution Architect\|

- Marc De Deygere \|FastTrack Solution Architect\|
