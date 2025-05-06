---
title: TechTalk - Project management and time entry with Dynamics 365 Project Operations
description: Get a summary of a TechTalk video about how to manage projects and time with Dynamics 365 Project Operations.
ms.date: 11/07/2024
ms.topic: concept-article
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Project management and time entry with Dynamics 365 Project Operations

Dynamics 365 Project Operations offers a robust set of tools to help you handle project contracts, execution, time tracking, and invoicing. This article provides an in-depth look at the essential elements of project management and time entry in Dynamics 365 Project Operations. It guides you through contract setup, time tracking, approvals, and more.

We based this article on [a TechTalk](https://youtu.be/aZSIIxIxQU8) that you can find online in the Dynamics 365 channel on YouTube.

:::image type="content" source="media/po-proj-man-time-entry-slide.svg" alt-text="Thumbnail of the title slide for the 'Dynamics 365 Project Operations - Project Management, Time Entry, Approvals, and Actuals' presentation." link="https://youtu.be/aZSIIxIxQU8":::

## Overview of project management in Dynamics 365 Project Operations

Dynamics 365 Project Operations provides tools that businesses can use to streamline project management and enhance efficiency. Whether your projects are internal or customer-facing, the app facilitates contract creation, task assignment, and the tracking of actuals (costs, time, and resources) throughout the project lifecycle.

:::image type="content" source="media/po-proj-man-time-entry-contracts.svg" alt-text="Diagram that shows the concepts that make up the header, lines, and line details of a contract." lightbox="media/po-proj-man-time-entry-contracts.svg":::

One of the standout features of Dynamics 365 Project Operations is its ability to manage complex project contracts and time entries with ease. Whether you're dealing with time-and-materials or fixed-price billing models, the app gives you flexibility in the way that you structure your projects. Additionally, through its integration with other Dynamics 365 apps, such as Dynamics 365 Finance and Dataverse, it allows for seamless collaboration across teams and accurate project accounting.

## Project contracts and billing models

In Dynamics 365 Project Operations, project contracts are created to define the work scope, billing models, and timelines. You can configure contract lines to represent discrete components of the work that will be invoiced. Each component can have its own billing method, such as *fixed price* or *time and materials*. For example, a project might include a fixed price for some expenses, whereas time is billed as time and materials.

Contracts can also define multiple stages: *draft*, *on-hold*, and *confirmed*. Each stage has its own role in project execution. When a contract reaches the *confirmed* stage, it becomes read-only to ensure that no further revisions can be made. If your organization requires frequent updates or revisions, we recommend that you keep the contract in a stage that allows for changes.

## Set up projects and tasks

The process of creating a project in Dynamics 365 Project Operations is straightforward. After you define the project contract, you can set up tasks by using Project for the Web. Project for the Web provides desktop-like controls, including an easy-to-use grid where you assign tasks to specific roles, set durations, and classify tasks into buckets, such as *presales*, *design*, or *delivery*.

You can visualize the project plan by using a Gantt chart. In this way, you can track dependencies and project progress. As time is entered against tasks, the system automatically updates completion rates and effort tracking.

## Time entry and approval process

Time entry is a critical feature in Dynamics 365 Project Operations, because users must be able to log the hours that they worked on specific tasks in a project. The easy-to-use time entry interface gives users the flexibility to select projects, roles, and associated tasks for each time entry.

When time is entered, it goes through an approval process. If the time is project-specific, it's routed to project approvers. Non-project-related time (for example, vacation or general admin time) is routed to the user's manager. After time is approved, actuals are automatically created and reflect the cost and sales transactions for the time that was entered.

In Dynamics 365 Project Operations, users can also recall time entries before they are invoiced. This capability is useful if a user must correct or adjust their time entries after they submit them for approval.

## Configure billing and chargeable tasks

Dynamics 365 Project Operations offers extensive configurability for billing and chargeable tasks. Users can define which tasks are billable and link them to specific contract lines. For example, in a prototype phase, expenses might be billed as a fixed price, whereas time is charged based on time and materials.

Chargeable tasks can also be associated with different roles to ensure that only relevant costs are billed to the customer. This flexibility allows for detailed financial tracking and ensures accurate billing according to the contract terms.

## Integrate with Microsoft Teams

Collaboration on projects is enhanced through the integration of Dynamics 365 Project Operations with Microsoft Teams. Project teams can communicate directly within the app, create dedicated channels for specific projects, and even run the app within Teams. This feature allows for seamless interaction between project managers and team members. Therefore, it helps ensure that everyone stays on track with project timelines and deliverables.

## Time entry flow and tracking

The time entry flow in Dynamics 365 follows a clear process, from draft to submission, approval, and the creation of actuals. As users enter their time, the system creates journal lines to track both the cost and sales that are related to the time entries. After the time entries are approved through the straightforward approval process, they contribute to the project's actuals. This flow ensures that the project's financial tracking remains accurate.

:::image type="content" source="media/po-proj-man-time-entry-time-entry-flow.svg" alt-text="Diagram that shows the process flow for time entry, starting from the point where a user creates a time entry." lightbox="media/po-proj-man-time-entry-time-entry-flow.svg":::

If changes must be made to submitted time entries, users have the option to recall and edit their entries before they are invoiced. This feature provides flexibility in time management and ensures accuracy in reporting and billing.

## Conclusion

Dynamics 365 Project Operations is an essential tool for managing complex projects. It offers robust capabilities for time entry, task management, and contract billing. Its integration with Microsoft Teams and other Dynamics 365 apps, such as Dynamics 365 Finance, makes it a powerful platform for any organization that is looking for ways to streamline project management workflows and improve collaboration across teams.

Regardless of whether you're setting up a simple project or managing a large, multiphase contract, Dynamics 365 Project Operations provides the necessary flexibility and control to ensure project success.

For more information, you can explore the [Microsoft Dynamics 365 Implementation Guide](https://aka.ms/D365implementationguide). This guide contains comprehensive insights into best practices and strategies for successful Dynamics 365 implementations.

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [Time overview](/dynamics365/project-operations/time/time-entry-overview)
- [Dynamics 365 Project Operations documentation](/dynamics365/project-operations/)
- [Implementation guide](../implementation-guide/introduction.md)
- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
