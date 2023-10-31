---
title: Manage project delivery overview
description: Learn how you can use Dynamics 365 products to support the organization's business processes to track that the project is worked on.
ms.date: 10/31/2023
ms.topic: conceptual
author: edupont04
ms.author: abunduc
# CustomerIntent: As a functional consultant, I want learn about this business process area so that the implementation runs better. 
---

# Manage project delivery overview

***Applies to: Dynamics 365 Project Operations, Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Field Service, Dynamics 365 Human Resources***

This article describes how you can use Dynamics 365 products to support your organization's business processes to deliver work on a project.

The *manage project delivery* business process area is key to capture the work that is delivered on a given project. It helps make sure that the final outcomes are provided to stakeholders, diligently and in a timely fashion. All the tasks, activities, and milestones outlined in the project plan are run and completed during this phase. Depending on the nature of the project, work might include various activities, such as the examples in the following list:

- Design  
- Development  
- Testing  
- Documentation  
- Quality assurance  

We recommend that you track, record, and manage the effort invested in these activities by team members and resources in a structured approach. This way, you gain valuable insights into project progress and meeting project objectives.  

This business process area also covers the evaluation of project performance, estimation of task completion times, and identification of potential bottlenecks. Furthermore, it facilitates the assessment of resource allocation, aiding in optimizing workforce utilization and enhancing project efficiency. Through the systematic capture of project time, organizations elevate their ability to deliver projects on schedule, allocate resources effectively, and bolster overall productivity.

The structure of the *manage project delivery* business process is ideally defined in the early stages of project implementation. As project parameters, timelines, and resource allocation are established, outlining the *manage project delivery* process ensures that accurate data collection begins from the project's inception. The process might naturally evolve as the project progresses, but it's important to lay its foundation before the project work is initiated.

## Stakeholders 

Many people across the organization should contribute to the decision-making process and design of the *manage project delivery* area. The following list provides examples of such stakeholders:

- Project management stakeholders – Examples: Program managers, Portfolio managers, Project managers, and Resource managers

- Executive stakeholders – Examples: Executive sponsor

- Finance department

## Manage project delivery process flow 

The following diagram illustrates the *manage project delivery* business process area.

:::image type="content" source="media/project-to-profit-deliver-project-work-flow.svg" alt-text="Flow diagram for the business process area, which is explained in the paragraphs after the image." lightbox="media/project-to-profit-deliver-project-work-flow.svg":::

[!INCLUDE [daf-business-process-flow-def](../includes/daf-business-process-flow-def.md)]
The flow diagram covers the following steps.

1. Start

2. *Project to profit* end-to-end process

3. *Manage project scope and schedule* business process area as an upstream process

    1. *Plan project scope and schedule*

4. *Resource a project* business process area as an upstream process

5. *Manage project delivery* business process

    1. Execute project task

    2. Enter time

    3. Time entry need adjustments?

        1. A parallel branch for *Yes* leads to *Correct time*

        2. *No* leads to *Submit time*

    4. Approve time?

        1. A parallel branch for *Yes* leads to *Approve time*

        2. *No* leads to *Reject time*

    5. A parallel branch from *Approve time leads* to

        1. *Recall time* takes place if a user needs to recall an already approved time entry

        2. *Estimate task effort* takes place if tasks need further updating.

6. *Manage project scope and schedule* business process area as a downstream process

    1. *Revise project scope and schedule*

7. End

## Manage project delivery benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the *manage project delivery*. The following sections outline the key benefits that an organization might monitor and measure for *manage project delivery*. 

### Accurate project tracking

With Dynamics 365 Project Operations, you can track time spent on various tasks and activities within projects high great precision. This real-time data empowers project managers and stakeholders to have a comprehensive view of project progress, helping them make informed decisions and adjustments as needed.

### Optimized resource allocation

By aligning project time data with resource availability, managers can make sure that resources are allocated efficiently, preventing overbooking and underutilization.

### Accurate cost estimation and budget management

Dynamics 365 Project Operations links time data with resource costs, which can help with accurate cost estimation and budget management. This integration helps organizations maintain tight control over project budgets and expenses.

### More transparency

Dynamics 365 Project Operations promotes transparency because project stakeholders can access real-time data on the project's progress and use of resources. This transparency fosters accountability among team members, and it instills trust in project management.

### Increased efficiency

Delivering project work facilitates streamlined communication and progress tracking for both team members and project managers. By centralizing task updates in one location, users can swiftly report their dedicated efforts towards project tasks. As a result, project managers can efficiently review and either approve or reject the submitted work, allowing for prompt updates on project progress.

Furthermore, you can create [pro forma invoices](glossary.md#pro-forma-invoice) from time that is submitted and approved for the project. This way, you decrease the time and coordination effort to invoice for work done on projects.

### Increased reliability

By delivering project work through Dynamics 365 Project Operations, time entry and reporting processes are streamlined and standardized. This approach increases the reliability of the data and processes, which in turn can help you to avoid duplication, mismatch, or omission of data.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *manage project delivery* business processes, use the following resources and steps to learn more. Links are added when articles become available. 

1. [Govern projects](project-to-profit-govern-projects-overview.md)  
2. Manage project contracts
3. [Manage project resources and schedule](project-to-profit-manage-project-scope-schedule-overview.md)  
4. *Manage project delivery* (the article you're currently reading)
5. [Manage project financials](project-to-profit-manage-project-financials-overview.md)  
6. [Monitor and analyze project performance](project-to-profit-monitor-analyze-project-performance-overview.md)  

## Related resources

You can use the following resources to learn more about the *manage project delivery* process in Dynamics 365.

- [Dynamics 365 Project Operations - Project Management and Time Entry (Dynamics 365 Community Blog)](https://community.dynamics.com/blogs/post/?postid=d9613dbe-cb51-4cb3-b29a-8464034d7fdb)
- [Time overview](/dynamics365/project-operations/time/time-entry-overview)
- [Time entry UI behavior](/dynamics365/project-operations/time/ui-behavior-time)

    - [Extending time entries](/dynamics365/project-operations/time/customize-weekly-time-entry-grid)
- [Project effort tracking](/dynamics365/project-operations/project-management/project-tracking-overview)
- Find definitions of terminology used in content for *manage project delivery* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article, including the following terms:

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
