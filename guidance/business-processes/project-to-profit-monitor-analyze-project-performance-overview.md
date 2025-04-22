---
title: Overview of the Analyze project performance business process area
description: Learn how you can use Dynamics 365 products to support the organization's business processes for monitoring and analyzing project performance.
ms.date: 04/15/2025
ms.topic: conceptual
author: edupont04
ms.author: lalithac
---

# Overview of the Analyze project performance business process area within the Project to profit end-to-end scenario

***Applies to: Dynamics 365 Business Central, Dynamics 365 Finance, Dynamics 365 Project Operations***

This article describes how you can use Dynamics 365 products to support organization's requirements to Analyze project performance. The business process area has been renamed, and we're still in process of updating the article.

## Introduction to Analyze project performance

The *Analyze project performance* business process area focuses on systematically monitoring, assessing, and evaluating various project elements, including the following list:

- How much of the project scope is already delivered?
- What remains?
- What are the project costs and revenue?
- Are there any risks?
- Which issues prevent the project from progressing as planned and meeting its objectives?

By monitoring project performance and conducting in-depth analysis, project managers and stakeholders can gain valuable insights, make informed decisions, and take any corrective action that is required.

The process of monitoring and analyzing project performance should be established at the onset of the project. As soon as the project objectives, scope, and resources are defined, it's imperative to set up a monitoring and analysis mechanism. In this way, you ensure that a system for gauging progress, measuring performance, and implementing course corrections is in place from the earliest stages. Early incorporation of this business process area also ensures that data collection is consistent throughout the project, so that insights for analysis are more accurate.

## Stakeholders

Many people across the organization should contribute to the decision-making process and design of the *Analyze project performance* area. The following list provides examples of such stakeholders:

- **Project managers**: Responsible for monitoring project progress.
- **Steering committee**: Responsible for making decisions based on an analysis of project performance.
- **Project sponsor**: Responsible for reviewing the reports and assessing their effect.
- **Finance controller**: Responsible for project budgeting, costing, and analysis of financial data.

## Analyze project performance process flow 

The following diagram illustrates the *Analyze project performance* business process area.

:::image type="content" source="media/project-to-profit-monitor-analyze-project-performance-flow.svg" alt-text="Flow diagram for the business process area, which is explained in the paragraphs after the image." lightbox="media/project-to-profit-monitor-analyze-project-performance-flow.svg":::

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

The *Analyze project performance* business process area flow diagram covers the following steps.

1. Start
1. *Project to profit* end-to-end process

    A parallel branch of this end-to-end process is end-to-end process 3. *Record to report*.

    1. *Govern projects*

        Parallel branches of this subprocess are the *Manage project contracts*, *Manage project resources and schedules*, *Manage project delivery*, and *Manage project financials* subprocesses.

    1. *Analyze project performance*

        1. Define project metrics
        1. Define baseline for project metrics
        1. Measure or calculate project metrics
        1. Compare metrics to baselines
        1. Communicate performance to stakeholders
        1. Corrective action?

            1. A branch for **Yes** leads to the downstream *Govern projects* subprocess.
            2. A parallel branch for **No** leads to *Project done?*

        1. Project done?

            1. A branch for **Yes** leads to 4. *End*.
            1. A parallel branch for **No** leads back to *Measure/Calculate project metrics*.

      If the scope, schedule, or budgets change, the following subprocesses are downstream: *Manage project resources and schedules*, *Determine project scope and schedule*, and *Manage project financials*. *Manage project budgets* leads back to *Define baseline for project metrics*.

1. *Record to report* end-to-end process

    1. *Record financial transactions*
    1. *Report and analyze financials and cash flow*

1. End

## Analyze project performance benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the *Analyze project performance* business process area. The following sections outline the key benefits that an organization might monitor and measure for *Analyze project performance*. 

### Intelligent project analytics

Dynamics 365 includes project management capabilities that support intelligent analytics and reporting. The insights that are derived provide a detailed view of project performance. Details include information about completed work, a comparison of forecast and actuals, a review of cost and revenue metrics, and an analysis of Earned Value Management. By using the out-of-box inquiries and dashboards, project managers get a complete overview that helps them make informed decisions.

Learn more at [Dynamics 365 Project Operations](/dynamics365/project-operations/) and [Project management in Dynamics 365 Business Central](/dynamics365/business-central/projects-manage-projects).

### Integrated resource management and financials view

In solutions with Dynamics 365 Project Operations and Dynamics 365 Finance, the ability to track and monitor project progress from opportunity to delivery gives an end-to-end view of the project. Through [integration with the Microsoft Project client](/dynamics365/project-operations/prod-pma/project-integration), you can open, manage, and monitor a [work breakdown structure](/dynamics365/project-operations/prod-pma/work-breakdown-structures) (WBS) for the project. The project manager can publish any changes back to Dynamics 365. The project manager gets a thorough perspective on employee workload and capacity. In this way, they can ensure that deadlines and quality standards are met. The project manager also has clear budget tracking and adherence during the project's full span. In addition, data consistency is considered throughout the process.

### Proactive risk management

Project monitoring and analytics help the project team recognize project issues and misalignments before they become critical, so that it can act immediately. Proactive risk management is essential. It lays the foundation for effective and successful project execution, and helps prevent both financial and time impact.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *Analyze project performance* business processes, you can use the following resources and steps to learn more.

1. [Develop project strategy](project-to-profit-develop-project-strategy-overview.md)

2. [Manage project contracts](project-to-profit-manage-project-contracts-overview.md)

3. [Plan projects](project-to-profit-plan-projects-overview.md)

4. [Manage project delivery](project-to-profit-deliver-project-work.md)

5. [Manage project financials](project-to-profit-manage-project-financials-overview.md)

6. *Analyze project performance* (the article that you're currently reading)

## Related information

You can use the following resources to learn more about the *Analyze project performance* process in Dynamics 365.

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

- Martin Walker \| FastTrack Solution Architect
- Lalitha Chintamaneni \| FastTrack Solution Architect
- Rachel Profitt \| FastTrack Solution Architect
- Milda Beinaryte \| FastTrack Solution Architect
- Satish Panwar \| FastTrack Solution Architect
- Marc De Deygere \| FastTrack Solution Architect
