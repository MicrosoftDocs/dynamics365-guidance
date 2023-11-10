---
title:  Manage expectations
description: Read about the change manager's tasks for managing expectations during a Dynamics 365 implementation project.
author: taksatoms
ms.author: tsato
ms.date: 06/19/2023
ms.topic: conceptual
---

# Managing expectations

A key challenge for change managers throughout the Implement phase is management of expectations.

## Create awareness of the project and coming changes

Now is when the communication plan and the sponsor roadmap come into play. For methodologies where there are real phase milestones, you should make an event out of reaching one. For agile projects, a similar event can be scheduled when the project reaches a predefined state.

The beginning of the Implement phase is an exciting time to highlight the project and its purpose, and to demystify the upcoming activities. Think of it when the project is about 20 percent completed, and people have had a chance to settle into the daily rhythm of the project.

It's a good practice to have the project sponsor or senior management explain to the organization what the vision, business goals, and objectives are for the project, what is going on now, how they are represented, how they can contribute, and what they should expect in the future.

It's also a good practice to reiterate the messaging throughout the implementation project, especially if goals and objectives change.

## Explain the limitations of non-production environments

It's a common practice, as described throughout this section, for the project team to use non-production environments to perform layers of testing and other interactions with the apps that are being implemented. A typical cause of misconception, and a source of concern, is when stakeholders experience their business processes in a developer or test environment without setting proper expectations.

Non-production environments are mostly scaled down versions of the production environments. They don't have the same "muscle power" or capabilities for cold-start scenarios.

Earlier in this section, we recommend setting clear expectations around demo data and related limitations. The same pitfalls exist in demo, test, and training environments during the implementation project. In fact, we recommend that you don't expose user groups and processes that are identified as high risk, or the wider user community, to the solution until you're sure that the environment is performing well, is appropriately configured, and has meaningful datasets.

## Explain cloud behavior and user experience

A related area that can cause concern is when a legacy system is an older on-premises client-server or mainframe architecture. Although these systems might be long past their end of life, they often have two sets of characteristics that can be a barrier to ready acceptance of new solutions by longtime users:

- They are often tailored to a user base that has experience with the system, sometimes for decades. Therefore, they are customized into a series of single screens where the user interacts with function keys and key combinations to do what they need to do from one place.
- They often react *instantly* to user input.

Modern business apps are much more focused on making a user experience that is friendly, intuitive, and easier to learn. Therefore, users have to learn to navigate to the specific module or area of the app that they must interact with.

Additionally, modern apps, whether they are mobile apps or web-based apps, generally respond quickly to user interaction. However, after an action is invoked, there is sometimes a slight lag before the required data has made a round trip to the application service back end. Similarly, an occasional wait circle can occur when the app must transfer fairly large amounts of data through a mobile connection. These delays might be very distracting to users who are used to the instant gratification of older technologies.

As cloud-focused implementors and IT professionals, we tend to take these characteristics for granted. However, it's important that we set expectations clearly and, sometimes, repeatedly with stakeholders. If stakeholders are preoccupied with concerns about what they perceive as a sluggish system, they find it difficult to absorb essential information that they need to make decisions about solution features/functions.

## Next steps

- Review the change management [overview](change-management.md).
- Understand where to get started by [assessing business process change](change-management-assessing-business-process-change.md).
- Learn about the importance of [project goals and readiness](change-management-project-goals-readiness.md).
- Find ways to affect change by understanding the [project organization](change-management-project-organization.md).
- Learn ways to do proper assessment and [solution overview](change-management-solution-overiew.md).
- Incorporate change management activities into the [project plan](change-management-project-plan.md).
- Understand the importance of [setting the ground rules](change-management-set-ground-rules.md).
- Understand key elements of change management: [progress, obstacles, and planning](change-management-progress-obstacles-planning.md).
- Understand how change management can affect [testing of the solution](change-management-test-solution.md).
- Understand timing and focus in [getting ready](change-management-get-ready.md) to deploy.
- Set the stage for proper [transition and handover](change-management-transition-handover.md).
- Review the change management [checklist](change-management-checklist.md).
- Read the [case study](change-management-case-study.md) to understand the positive impact of proper change management practice.
