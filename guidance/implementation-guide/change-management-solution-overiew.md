---
title: Provide overviews of projects and solutions during projects
description: Read about the change manager's tasks for catching and providing the overview of the project and the solution during a Dynamics 365 implementation project.
author: taksatoms
ms.author: edupont
ms.date: 06/20/2023
ms.topic: conceptual
---

# Provide overviews of projects and solutions during Dynamics 365 implementation projects

For business application projects, it's common for the implementation project to start before [the project organization](change-management-project-organization.md) has been started. Often, [assessments](change-management-assessing-business-process-change.md) are done as part of the selection process. In addition, high-level scope, risks, and problem areas might have been identified during the sales cycle or the discovery phase of the project.

This situation isn't an issue. In most cases, the artifacts and documents can fit directly into the project's body of knowledge.

## Establish solution guiding principles

Every project has a set of foundational guiding principles. These principles might include a strategy for handling gaps, define how trade-off decisions are made, and establish the stakeholder charter.

The guiding principles are often derived from the vision and goals that are set by the business. However, in many projects, they are unspoken rules. Unless they are formalized, they can cause friction, confusion, and scope creep.

Here are some examples of guiding principles for an implementation project:

- We won't replicate legacy processes. Change is expected.
- We change the business process instead of customizing or extending the solution.
- No features in the transformed solution should add headcount.

Regardless of what the principles are, it's beneficial to define them and measure them against the business goals.

In the article [Implement cloud solutions](implementing-cloud-solutions.md), we discuss how an implementation project should aim higher than reconstruction of the legacy system. In fact, a fundamental recommendation is, "Don't mimic your existing system." Therefore, we don't recommend using terms that imply such an approach (for example, "lift-and-shift" or "like-for-like") in guiding principles. Although these terms might seem like convenient ways to shortcut the process mapping and scoping process, they often lead some user groups to expect that nothing really changes at all. Therefore, there is a risk of friction around scoping and interpretation throughout the project.

There are often differences between the legacy architecture or features and the cloud solution, and these differences make it undesirable to use a lift-and-shift or like-for-like approach for legacy functionality.

Likewise, during upgrades from earlier versions of Dynamics 365 apps, deprecated and new capabilities often make it undesirable to do a lift-and-shift of the legacy functionality. Instead, it's more attractive to adopt new, more scalable processes.

In many cases, it's more costly to re-create deprecated or overly customized legacy processes than to adopt the modern version of similar processes that are now readily available in the apps.

## Establish a mutual understanding of project scope

From a change management perspective, the kick-off of a project also represents a reset or common starting point for expectations on the part of everyone who is involved.

Friction often arises when there are discrepancies between what was discussed during presales demos and meetings and the final contract or statement of work that outlines the scope, roles, and responsibilities for project deliveries. This friction can exist between the end customer and partner, or between stakeholders within the implementing organization. It might be a result of cutting scope during negotiations, or it might just be a result of misaligned expectations.

An early actionable item is to schedule a walkthrough of the contract, statement of work, or any other document that defines the scope of the project. The goal is to align stakeholder expectations.

## Define and follow a change request procedure

During a transformational business application project, there are often changes in scope. Given the flexibility of the apps and the fact that many methodologies have an element of agility, it's highly likely that such changes affect processes, technology, and people outside the narrow definition of the added or changed scope.

Whenever there are changes in the project scope, the affected stakeholders should be informed about the decisions that are made. In this way, the expectations that were set at the start of the project are kept up to date as the transformation occurs.

The implementing partner often has a methodology that includes a change request process. We recommend that the project organization works with a proven methodology of this type instead of inventing its own.

The change manager should take on the mission of appending this process. They should enforce proper documentation of the change requests and the related feedback loop. They should also make sure that requests are thoroughly acknowledged, triaged, and qualified, and that decisions are made for rejection or approval.

Dynamics 365 implementation projects have strong advantages here, thanks to the tooling with Azure DevOps. Azure DevOps hosts the important project documentation. Therefore, because there might be turnover in business application project teams, you can reverse-engineer change decisions.

## Explain limitations of demos or proofs of concept

A common pitfall is that the implementation partner's demos are based on limited knowledge of the organization and the actual processes, and might be made with demo data that resembles the organization's real data.

The result can be overly high expectations about the final outcomes if the demo simplifies process steps. Alternatively, the result can be a negative impression on the part of stakeholders if the demo misses the mark because of misunderstanding or confusion about the demo data or the actual requirement.

To preserve trust in the product, partner, and project, follow this rule: Every time a demo is made, the presenter or the project manager should make it clear to the stakeholders what shortcuts and assumptions are used. They should also ensure a level of transparency about the limitations that exist.

## Take note of challenges identified during presales

Even during the presales process, there is often some awareness of challenges and key processes that could pose a risk. System integrators (SIs) or partners often make proofs of concept (POCs) or mock-ups of solutions. It's important to document decisions that are made, any trade-offs, and solution proposals that were accepted or rejected.

It's highly likely that some stakeholders who took part in early discussions or demos aren't present in the later negotiations about whether processes are in scope.

The change manager should make a point of noting these challenges and revisiting them. They are highly likely to cause friction later in the project if they aren't properly addressed. It's also important to uncover whether important processes "fell out of scope" as part of presales negotiations, or whether they were pushed out for later decision but are, in fact, needed for go-live.

## Next steps

- Review the change management [overview](change-management.md).
- Understand where to get started by [assessing business process change](change-management-assessing-business-process-change.md).
- Learn about the importance of [project goals and readiness](change-management-project-goals-readiness.md).
- Find ways to affect change by understanding the [project organization](change-management-project-organization.md).
- Incorporate change management activities into the [project plan](change-management-project-plan.md).
- Understand the importance of [setting the ground rules](change-management-set-ground-rules.md).
- Review key challenges for [managing expectations](change-management-manage-expectations.md).
- Understand key elements of change management: [progress, obstacles, and planning](change-management-progress-obstacles-planning.md).
- Understand how change management can affect [testing of the solution](change-management-test-solution.md).
- Understand timing and focus in [getting ready](change-management-get-ready.md) to deploy.
- Set the stage for proper [transition and handover](change-management-transition-handover.md).
- Review the change management [checklist](change-management-checklist.md).
- Read the [case study](change-management-case-study.md) to understand the positive impact of proper change management practice.
