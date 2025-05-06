---
title: Assess process changes in implementation projects
description: Find guidance about how to identify changes in a Dynamics 365 implementation project, including overviews on defining how changes affect users.
author: taksatoms
ms.author: edupont
ms.date: 06/19/2023
ms.topic: concept-article
---

# Assess business process changes in Dynamics 365 implementation projects

Most change management practices start with an element of assessment: assessment of the organization, assessment of stakeholders, assessment of risk, and assessment of that way that expected outcomes are defined and agreed upon. With [Success by Design](success-by-design.md), we believe that we established good practices. We don't do a detailed dive into those practices in this article. Instead, we highlight the important outcomes and actionable items that should come out of the assessments.

An important aspect of these assessments should be to define what changes and the impact of those changes.

## Define what changes

In the article [Process Focused Solution](process-focused-solution.md), we discuss the importance of defining business processes. We highlight what the team should document in a process diagram or process catalog. In change management, we add an extra dimension to this point. We must understand not only what technology and operational processes change, and how they change, but also what users and roles are directly and indirectly affected by the process changes. We must also document this information, so that we can apply our change management effort to the affected areas.

We achieve a definition by looking at each business process and determining the level of change that is expected in it. Here is an example:

*An organization is upgrading to Dynamics 365 from an earlier on-premises version of Dynamics. With the implementation project, the company has set goals around reaching 95 percent inventory accuracy by the end of year 1. To help achieve this goal, advanced warehousing is introduced. As a result, the processes for receiving raw materials and shipping finished goods change significantly. For put-away and picking functions, users must now follow directives from the system on a handheld device.*

|  Process |  User Group |  Change |  Impact 1-5 |
|---|---|---|---|
|  Receiving | Inbound Dock  |  Registration Process |  3 |
|  Quality |  Inbound Dock |  Quarantine & Quality Control |  2 |
|  Packing & Shipping |  Outbound Dock |  Pick by reservation as directed by device |  2 |

The outcome of this exercise might be an addendum to the process diagram or catalog, where you include information about what the key changes are from a process or technology perspective, what user groups the changes affect, and how impactful the changes are.

In the impact assessment, you might even go deeper, and identify major gains and drawbacks to the affected user groups. This approach supports, for example, the identification of potential enthusiasts who might become change champions and help construct a plan for managing resistance. Resistance management is a key area of change management. Learn more in [Pay attention to high-risk user groups/processes](change-management-get-ready.md#pay-attention-to-high-risk-user-groupsprocesses).

## Determine what users or user groups are affected

| User Group / Role | Impact of changes |
|-------------------|-------------------|
|Inbound Dock | 5 |
| Outbound Dock | 2 |

After we define the key changes, the affected user groups, and the impact on them, we add up the cross-process change impact for each affected user group. We can then establish a matrix as shown in the preceding illustration.

We must have clarity about the impact that a change has on each user group. In this way, the change manager can apply change management focus and activities proportionally to the areas that need it the most.

> [!TIP]
> The artifacts are only examples. The implementation team can use the toolset that is already in place for process documentation. Azure DevOps, Excel, or any other tool is sufficient, provided that it produces the documentation that is needed for decision making. The team can also use templates that are provided by the change management practice.

## Avoid single-point-of-failure scenarios

During this exercise, it's important to identify any single point of failure. For example, this point of failure might be a process that a single knowledgeable individual is capable of defining or performing. Highlight such cases as high-risk areas, because the project can be severely affected if such a pivotal individual leaves the organization. During the planning for the future process in these areas, it's important to spread these "islands" or "silos" of knowledge to a wider group.

## Next steps

- Review the change management [overview](change-management.md).
- Learn about the importance of [project goals and readiness](change-management-project-goals-readiness.md).
- Find ways to affect change by understanding the [project organization](change-management-project-organization.md).
- Learn ways to do proper assessment and [solution overview](change-management-solution-overiew.md).
- Incorporate change management activities into the [project plan](change-management-project-plan.md).
- Understand the importance of [setting the ground rules](change-management-set-ground-rules.md).
- Review key challenges for [managing expectations](change-management-manage-expectations.md).
- Understand key elements of change management: [progress, obstacles, and planning](change-management-progress-obstacles-planning.md).
- Understand how change management can affect [testing of the solution](change-management-test-solution.md).
- Understand timing and focus in [getting ready](change-management-get-ready.md) to deploy.
- Set the stage for proper [transition and handover](change-management-transition-handover.md).
- Review the change management [checklist](change-management-checklist.md).
- Read the [case study](change-management-case-study.md) to understand the positive impact of proper change management practice.
