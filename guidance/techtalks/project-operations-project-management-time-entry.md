---
title: TechTalk Project management and time entry with Dynamics 365 Project Operations
description: Summary of TechTalk video that talks about how to manage projects and time with Dynamics 365 Project Operations.
ms.date: 11/07/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Project management and time entry with Dynamics 365 Project Operations

Welcome to an in-depth look at project management and time entry in Dynamics 365 Project Operations. This platform offers a robust set of tools for handling project contracts, execution, time tracking, and invoicing. This article delves into the essential elements of managing projects and time entry, guiding you through contract setups, time tracking, approvals, and more.  

We based this article on [a TechTalk](https://youtu.be/aZSIIxIxQU8) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/po-proj-man-time-entry-slide.svg" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/aZSIIxIxQU8":::

## Overview of Dynamics 365 Project Operations

Dynamics 365 Project Operations provides businesses with tools to streamline project management and enhance efficiency. Whether your projects are internal or customer-facing, this platform facilitates contract creation, task assignment, and the tracking of actuals—costs, time, and resources—throughout the project lifecycle.

:::image type="content" source="media/po-proj-man-time-entry-contracts.svg" alt-text="Slide with three boxes for header, lines, and line details." lightbox="media/po-proj-man-time-entry-contracts.svg":::

One of the standout features of Dynamics 365 Project Operations is its ability to manage complex project contracts and time entries with ease. Whether you're dealing with time-and-material or fixed-price billing models, the platform provides flexibility in structuring your projects. It integrates with other Dynamics 365 modules like Finance and Dataverse, enabling seamless collaboration across teams and accurate project accounting.

## Project contracts and billing models

In Dynamics 365 Project Operations, project contracts are created to define the work scope, billing models, and timelines. You can configure contract lines to represent discrete components of the work that will be invoiced, each with its own billing method (for example, fixed price or time and material). For instance, a project might include a fixed price for certain expenses while billing time as time and material.

Contracts can also define multiple stages—draft, on-hold, and confirmed—each with its own role in project execution. Once a contract reaches the confirmed stage, it becomes read-only, ensuring no further revisions can be made. If your organization requires frequent updates or revisions, it's advisable to keep the contract in a stage that allows for changes.

## Setting up projects and tasks

Creating a project within Dynamics 365 Project Operations is straightforward. After defining the project contract, you can set up tasks using Project for the Web, which allows for desktop-like controls. This setup provides an easy-to-use grid where tasks are assigned to specific roles, durations are set, and tasks can be classified into buckets like presales, design, or delivery.

The project plan can be visualized using a Gantt chart, allowing you to track dependencies and project progress. As time is entered against tasks, the system automatically updates completion rates and effort tracking.

## Time entry and approval process

Time entry is one of the critical features in Dynamics 365 Project Operations, allowing users to log the hours worked on specific tasks within a project. The time entry interface is user-friendly, offering flexibility to select projects, roles, and the associated tasks for each time entry.

Once time is entered, it goes through an approval process. If the time is project-specific, it's routed to project approvers, while non-project-related time (for example, vacation or general admin time) is routed to the user's manager. After approval, actuals are automatically created, reflecting the cost and sales transactions for the time entered.

The platform also allows users to recall time entries before they're invoiced. This is useful if a user needs to correct or adjust their time entries after submitting them for approval.

## Configuring billing and chargeable tasks

Dynamics 365 Project Operations offers extensive configurability for billing and chargeable tasks. Users can define which tasks are billable and link them to specific contract lines. For example, in a prototype phase, expenses might be billed as a fixed price, while time is charged based on time and materials.

Chargeable tasks can also be associated with different roles, ensuring that only relevant costs are billed to the customer. This flexibility allows for detailed financial tracking and ensures accurate billing according to the contract terms.

## Integrating with Microsoft Teams

Collaboration on projects is enhanced through the integration of Dynamics 365 Project Operations with Microsoft Teams. This allows project teams to communicate directly within the platform, create dedicated channels for specific projects, and even run the Project Operations app within Teams. This feature enables seamless interaction between project managers and team members, helping ensure everyone stays on track with project timelines and deliverables.

## Time entry flow and tracking

The time entry flow in Dynamics 365 follows a clear process, from draft to submission, approval, and actuals creation. As users enter their time, the system creates journal lines, tracking both the cost and sales related to the time entries. The approval process is straightforward, and once approved, the time entries contribute to the project's actuals, ensuring the project's financial tracking remains accurate.

:::image type="content" source="media/po-proj-man-time-entry-time-entry-flow.svg" alt-text="Flow diagram that starts when a user creates a time entry." lightbox="media/po-proj-man-time-entry-time-entry-flow.svg":::

If changes need to be made to submitted time entries, users have the option to recall and edit their entries before they're invoiced. This feature supports flexibility in time management, ensuring accuracy in reporting and billing.

## Conclusion

Dynamics 365 Project Operations is an essential tool for managing complex projects, offering robust capabilities for time entry, task management, and contract billing. Its integration with Microsoft Teams and other Dynamics 365 modules like Finance makes it a powerful platform for any organization looking to streamline project management workflows and improve collaboration across teams.

Whether you're setting up a simple project or managing a large, multi-phase contract, Dynamics 365 Project Operations provides the flexibility and control needed to ensure project success.

For further information, you can explore the Dynamics 365 implementation guide available at [aka.ms/D365implementationguide](https://aka.ms/D365implementationguide). This resource contains comprehensive insights on best practices and strategies for successful Dynamics 365 implementations.

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [Time overview](/dynamics365/project-operations/time/time-entry-overview)  
- [Dynamics 365 Project Operations documentation](/dynamics365/project-operations/)  
- [Implementation guide](../implementation-guide/introduction.md)  
- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
