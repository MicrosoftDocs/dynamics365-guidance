---
title: Resource a project overview
description: Learn how you can use Dynamics 365 products to support the organization's business processes to resource projects.
ms.date: 07/25/2023
ms.topic: conceptual
author: edupont04
ms.author: abunduc
---

# Resource a project overview

***Applies to: Dynamics 365 Field Service, Dynamics 365 Project Operations, Dynamics 365 Finance***

This article describes how you can use Dynamics 365 products to define and manage your resources, and how you can assign these resources to your projects.

Resources serve as the most vital asset for project-driven organizations. The ability to find the right resources at the appropriate time, book them for projects, and effectively utilize them helps organizations meet revenue targets and customer satisfaction goals. Finding the right resources entails accurately identifying and capturing their characteristics, ensuring a proper match with the project requirements.

This business process area focuses on ensuring that projects have the necessary resources to be completed successfully, including equipment, materials, and personnel. It involves identifying resource requirements, securing the necessary resources, and managing them throughout the project lifecycle.

The *resource a project* process should be defined and incorporated into the overall implementation during the project planning phase. This phase typically occurs at the beginning of a project's lifecycle and involves establishing project goals, defining project scope, and developing a detailed project plan. Learn more at [Project governance for Dynamics 365 implementation projects](../implementation-guide/project-governance.md).

## Stakeholders 

Many people across the organization should contribute to the decision-making process and design of the *resource a project* area. The list includes but isn't limited to the following roles:

- Project manager ([view definition](glossary.md#project-manager))  

- Resource manager ([view definition](glossary.md#resource-manager))  

- HR department

- Finance department

- Executive sponsor

- IT department

## Resource a project process flow 

The following diagram illustrates the *resource a project* business process area.

:::image type="content" source="media/project-to-profit-resource-project-flow.svg" alt-text="Flow diagram for the business process area, process project invoices, which is explained in the paragraph after the image." lightbox="media/project-to-profit-resource-project-flow.svg":::

The *resource a project* business process flow covers the following steps:

1.  Start

2.  *Project to profit* end-to-end process

3.  *Manage project scope and schedule* business process area as an upstream process

    1.  Plan project scope and schedule

    2.  Define the project and related project tasks

4.  *Resource a project* business process area

    1.  Define the company's resources

    2.  Define the characteristics of these resources, including the associated calendars

    3.  Define resource requirements per task (this step depends on the project tasks being defined – point 2b)

    4.  If the resource booking process isn't [centralized](glossary.md#centralized-resource-allocation), the resource can be assigned directly to the project. Otherwise, it must go through a flow:

    - A parallel branch when the process isn't centralized leads to identifying and booking a resource directly

    - A parallel branch when the process is centralized:

      1.  Request a resource

      2.  Identify a resource based on characteristics of the task and the resource

      3.  Propose a resource

      4.  Decide if the proposed resource is well matched:

          1.  Yes: Book the resource

          2.  No: Return to the first step of this branch and request an alternative resource

5. *Manage project scope and schedule* business process area as a downstream process

    1.  Revise project scope and schedule

6. End

## Benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the *resource a project* business process area. The following sections outline the key benefits that an organization might monitor and measure for resourcing a project.

### Optimal resource utilization

Dynamics 365 Project Operations provides advanced resource management features that enable organizations to effectively manage project resources. Learn more at [Project resourcing](/dynamics365/project-operations/prod-pma/project-resourcing). With the integrated resource planning and scheduling capabilities, organizations can gain real-time visibility into resource availability, skills, and utilization. This insight helps them make informed decisions about resource allocation, maximizing productivity, and achieving cost savings.

### Improved project scheduling and execution

By allocating resources appropriately, project managers can develop realistic schedules and timelines. This approach helps avoid bottlenecks, prevent resource conflicts, and maintain a smooth flow of work through the project lifecycle. As a result, projects are more likely to be completed on time, enhancing customer satisfaction and profitability. With the powerful scheduling capabilities available in Dynamics 365, resource and project managers can easily allocate the right resources to their projects.

### Streamlined productivity and efficiency

By using features such as resource management, task management, and collaboration tools, Dynamics 365 Project Operations enables teams to seamlessly coordinate and execute tasks. Real-time visibility into resource capabilities and resource allocation helps eliminate resourcing bottlenecks to ensure a smooth project execution, leading to enhanced productivity and efficiency.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *resource a project* business processes, use the following resources and steps to learn more (links to be added as business processes are published).

1. [Manage project opportunities](project-to-profit-manage-project-opportunities-overview.md)   

2. Manage project quotations

3. Manage project contracts

4. Govern projects

5. [Manage project scope and schedule](project-to-profit-manage-project-scope-schedule-overview.md)  

6. Resource a project (the article you're currently reading)  

7. [Deliver project work](project-to-profit-deliver-project-work.md)  

8. [Manage project supply chain](project-to-profit-manage-project-supply-chain-overview.md)  

9. [Capture project expenses](project-to-profit-capture-project-expenses-overview.md)

10. [Process project invoices](project-to-profit-process-project-invoices-overview.md)  

11. [Recognize project revenue](project-to-profit-recognize-project-revenue.md)  

12. Make adjustments to project transactions

13. Manage project budgets

14. Monitor and analyze project performance

15. Return to the overview of business process areas at [Project to profit business process areas](project-to-profit-areas.md)   

## Related resources

You can use the following resources to learn more about the *resource a project* process in Dynamics 365.

- [TechTalk: Dynamics 365 Project Operations - Resource management](https://community.dynamics.com/blogs/post/?postid=fdaa2beb-cb26-48ec-b13f-a618feba595e)  

- [Resource management key concepts](/dynamics365/project-operations/resource-management/resource-management-key-concepts)  

- [Get started with resource management in Dynamics 365 Project Operations (training)](/training/modules/get-started-project-resource-management/)  

- [Bookings versus assignments](/dynamics365/project-operations/resource-management/booking-vs-assignment)  

- [Dynamics 365 Project Operations TechTalk series](https://community.dynamics.com/blogs/post/?postid=a18d2afb-428f-420d-829b-2fd5820132a6)  

- [Project Operations](https://dynamics.microsoft.com/en-us/project-operations/overview/)  

- [Project to profit introduction](/dynamics365/guidance/business-processes/project-to-profit-introduction)  

<!-- ## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Executive Sponsor, Finance, Human Resources, IT, Project Management

*Products:* Dynamics 365 Field Service, Dynamics 365 Project Operations, Dynamics 365 Finance -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Andreea Bunduc](https://www.linkedin.com/in/andreeabunduc/) | FastTrack Solution Architect

Other contributors:

- Lalitha Chintamaneni | FastTrack Solution Architect
