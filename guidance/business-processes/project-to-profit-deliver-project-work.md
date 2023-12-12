---
title: Manage project delivery overview
description: Learn how you can use Dynamics 365 products to support the organization's business processes for tracking the work that is done on a project.
ms.date: 10/31/2023
ms.topic: conceptual
author: edupont04
ms.author: abunduc
# CustomerIntent: As a functional consultant, I want learn about this business process area so that the implementation runs better.
---

# Manage project delivery overview

***Applies to: Dynamics 365 Project Operations, Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Field Service, Dynamics 365 Human Resources***

This article describes how you can use Dynamics 365 products to support your organization's business processes for delivering work on a project.

The *manage project delivery* business process area is key to tracking the work that is delivered on a project. It helps ensure that the final outcomes are provided to stakeholders in a diligent and timely manner. During this phase, all the tasks, activities, and milestones that are outlined in the project plan are performed and completed. Depending on the nature of the project, work might include various activities, such as the examples in the following list:

- Design
- Development
- Testing
- Documentation
- Quality assurance

We recommend that you use a structured approach to track, record, and manage the effort that team members and resources invest in these activities. In this way, you gain valuable insights into how the project is progressing and how project objectives are being met.

This business process area also covers the evaluation of project performance, estimation of task completion times, and identification of potential bottlenecks. In addition, it facilitates the assessment of resource allocation, and therefore helps optimize workforce utilization and enhance project efficiency. Through the systematic capture of project time, organizations enhance their ability to deliver projects on schedule, allocate resources effectively, and boost overall productivity.

Ideally, the structure of the *manage project delivery* business process is defined during the early stages of project implementation. By outlining the *manage project delivery* process as project parameters, timelines, and resource allocation are being established, you ensure that accurate data collection begins from the project's inception. Although the process might naturally evolve as the project progresses, it's important to lay its foundation before the project work begins.

## Stakeholders 

Many people across the organization should contribute to the decision-making process and design of the *manage project delivery* area. The following list provides examples of such stakeholders:

- **Project management stakeholders** – Examples: Program managers, Portfolio managers, Project managers, and Resource managers
- **Executive stakeholders** – Example: Executive sponsor
- **Finance department**

## Manage project delivery process flow 

The following diagram illustrates the *manage project delivery* business process area.

:::image type="content" source="media/project-to-profit-deliver-project-work-flow.svg" alt-text="Flow diagram for the business process area, which is explained in the paragraphs after the image." lightbox="media/project-to-profit-deliver-project-work-flow.svg":::

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

The flow diagram covers the following steps.

1. Start
1. *Project to profit* end-to-end process
1. *Manage project scope and schedule* business process area as an upstream process

    1. *Plan project scope and schedule*

1. *Resource a project* business process area as an upstream process
1. *Manage project delivery* business process

    1. Execute project task
    1. Enter time
    1. Time entry need adjustments?

        1. A parallel branch for *Yes* leads to *Correct time*.
        1. *No* leads to *Submit time*.

    1. Approve time?

        1. A parallel branch for *Yes* leads to *Approve time*.
        1. *No* leads to *Reject time*.

    1. A parallel branch from *Approve time* leads to:

        1. *Recall time* if a user must recall a previously approved time entry.
        1. *Estimate task effort* if tasks require further update.

1. *Manage project scope and schedule* business process area as a downstream process

    1. *Revise project scope and schedule*

1. End

## Manage project delivery benefits

Many key benefits can be used to monitor and measure the success of implementing technology to support the *manage project delivery* business process area. The following sections outline the key benefits that an organization might monitor and measure for *manage project delivery*.

### Accurate project tracking

In Dynamics 365 Project Operations, you can track, with a high degree of precision, the time that is spent on various tasks and activities in projects. The real-time data gives project managers and stakeholders a comprehensive view of project progress. Therefore, it helps them make informed decisions and any adjustments that are required.

### Optimized resource allocation

By aligning project time data with resource availability, managers can ensure that resources are efficiently allocated. Therefore, they can prevent overbooking and underutilization.

### Accurate cost estimation and budget management

Dynamics 365 Project Operations helps with accurate cost estimation and budget management by linking time data with resource costs. This integration helps organizations maintain tight control over project budgets and expenses.

### More transparency

Dynamics 365 Project Operations promotes transparency, because project stakeholders can access real-time data about the project's progress and use of resources. This transparency fosters accountability among team members and instills trust in project management.

### Increased efficiency

The delivery of project work facilitates streamlined communication and progress tracking for both team members and project managers. Because task updates are centralized in one location, users can quickly report their dedicated efforts toward project tasks. Project managers can then efficiently review the submitted work, and either approve or reject it. Therefore, this approach allows for prompt updates about project progress.

In addition, you can create [pro forma invoices](glossary.md#pro-forma-invoice) from time that is submitted and approved for the project. In this way, you decrease the time and coordination effort that are required to invoice for work that is done on projects.

### Increased reliability

The delivery of project work through Dynamics 365 Project Operations streamlines and standardizes time entry and reporting processes. This approach increases the reliability of data and processes, and therefore helps prevent duplication, mismatch, or omission of data.

## Next steps

If you want to implement Dynamics 365 solutions to help with your *manage project delivery* business processes, use the following resources and steps to learn more. Links are added when articles become available.

1. [Govern projects](project-to-profit-govern-projects-overview.md)
1. Manage project contracts
1. [Manage project resources and schedule](project-to-profit-manage-project-scope-schedule-overview.md)
1. *Manage project delivery* (the article that you're currently reading)
1. [Manage project financials](project-to-profit-manage-project-financials-overview.md)
1. [Monitor and analyze project performance](project-to-profit-monitor-analyze-project-performance-overview.md)

## Related resources

You can use the following resources to learn more about the *manage project delivery* process in Dynamics 365.

- [Dynamics 365 Project Operations - Project Management and Time Entry (Dynamics 365 Community Blog)](https://community.dynamics.com/blogs/post/?postid=d9613dbe-cb51-4cb3-b29a-8464034d7fdb)
- [Time overview](/dynamics365/project-operations/time/time-entry-overview)
- [Time entry UI behavior](/dynamics365/project-operations/time/ui-behavior-time)

    - [Extending time entries](/dynamics365/project-operations/time/customize-weekly-time-entry-grid)

- [Project effort tracking](/dynamics365/project-operations/project-management/project-tracking-overview)
- Find definitions of terminology that is used in content for *manage project delivery* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article. For example, this glossary includes the following terms:

    - [Project task](glossary.md#project-delivery)
    - [Project delivery](glossary.md#project-delivery)
    - [Time entry](glossary.md#time-entry)
    - [Billable hours](glossary.md#billable-hours)
    - [Non-billable hours](glossary.md#non-billable-hours)

<!-- ## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Program manager, Project manager, Resource manager, Executive sponsor, Finance department

*Products:* Dynamics 365 Project Operations, Dynamics 365 Finance, Dynamics 365 Field Service, Dynamics 365 Supply Chain Management, Dynamics 365 Human Resources -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal authors:

- [Tim Horgan](https://www.linkedin.com/in/tim-horgan-a8127043/) \| Technical Specialist
- [Andreea Bunduc](https://www.linkedin.com/in/andreeabunduc/) \| FastTrack Solution Architect
