---
title: Prepare for go-live
description: Learn how to prepare for a successful go-live of a Microsoft Dynamics 365 solution by assessing the readiness of the people, processes, and systems for deployment.
author: vaniusca
ms.author: vaniaf
ms.date: 06/06/2023
ms.topic: conceptual
ms.custom:
 - ai-gen-docs-bap
 - ai-gen-desc
 - ai-seo-date:08/23/2023
 - bap-template
---

# Prepare for go-live

Go-live is a critical milestone in the process of deploying a business solution to production. After a successful go-live, the new solution is operational.

At go-live, all the parts of the implementation project come together and are tested and validated to make sure everything works as expected, not just on their own, but as a whole.

The go-live process covers getting the production environment ready and deploying the solution. It includes the following activities:

- Migrating and validating data
- Creating a communication plan
- Finalizing testing
- Signing off on the solution
- Onboarding and training users

A good go-live plan helps ensure a successful go-live by minimizing unforeseen issues and risks that weren't identified during previous phases. It has processes in place to handle the unexpected, which makes for a more resilient project.

When you're rolling out a solution in phases, the go-live plan should consider future deployments in advance. It's important to keep refining the plan with learnings from each rollout.

[Go-live readiness](#go-live-readiness) includes key activities to make sure the go-live plan is completed and that all parts of the solution&mdash;people, processes, and system&mdash;are in place for a smooth deployment.

When a solution goes live, there's often a transition period, also known as *cutover*. The cutover process follows a [cutover plan](prepare-go-live-cutover-strategy.md) that details the activities that are critical in transitioning to the new solution.

## Go-live readiness

All the tasks and efforts that are undertaken during an implementation project are preparation for the project's biggest milestone: go-live. In the [Success by Design framework](success-by-design.md), completion of these tasks is when the project reaches the Prepare phase. At this point, if you followed all the guidance and recommended practices, the solution should be ready to go live.

At a high level, the project is ready to go live when the following conditions are true:

- The go-live strategy is aligned with best practices.
- The requirements for going live have been met, including testing, code, and configurations.
- A concise and agreed-on [cutover plan](prepare-go-live-cutover-strategy.md) is in place, detailing the next actions required for the transition to the new system.

At a more detailed level, the following requirements must be met before the solution can go live:

- System integration, user acceptance, and performance testing are completed and signed off on.
- Code is complete and deployable packages are prepared to move to production.
- A data migration plan is in place.
- A cutover plan is in place and signed off on.
- User training is complete and users have the correct security roles.
- The correct number of licenses are available and assigned.
- A production support plan is in place and signed off on.
- Any critical open issues from the Solution Blueprint Review or other previous implementation reviews are mitigated.

When you've verified the successful completion of the most important project tasks, you can perform the cutover activities.

The following diagram illustrates the [Success by Design](success-by-design.md) implementation phases and when go-live occurs:

:::image type="content" source="media/prep-golive-sdb-implementation-phases.png" alt-text="Diagram illustrating the Success by Design implementation phases." lightbox="media/prep-golive-sdb-implementation-phases.png":::<!-- EDITOR'S NOTE: Please change "go live" to "go-live" in the diagram. -->

### Assess go-live readiness

While there's no such thing as zero risk for go-live, the go-live readiness review is a qualitative method to determine how well prepared the new solution is to run your business. You should evaluate the preparedness of the people and processes as well to make sure no critical details have been overlooked.

The implementation team should assess go-live readiness early and often. These assessments provide clarity on the status, readiness, completeness, and maturity of each activity and help project stakeholders and the steering committee make a well-informed go/no-go decision.

When the project moves to the Prepare phase, the implementation team evaluates the preparedness of the solution, which serves as a quality gate for deployment. This evaluation is done during the go-live readiness review.

### Go-live readiness review

Success by Design encourages teams to use the go-live readiness review to assess the go-live readiness of a project. The go-live readiness review is a deep dive into the project's status. Another way to describe it is as a holistic view of the implementation project: looking back on completed activities that are required for going live, looking at solution preparations, and looking forward to the plan to roll out and maintain the new solution.

The go-live readiness review can be performed as a workshop. It has several critical functions:

- It determines whether the solution meets the organization's needs and expectations, both functionally and nonfunctionally.
- It validates the plan that has been established to ensure a smooth transition in the available cutover window and avoid surprises during and after go-live.
- It uncovers potential risks and issues that could imperil go-live and provides recommendations and actions to mitigate them.
- It summarizes all the tasks that have been completed and covered in previous reviews.

Start early to prepare for the go-live readiness review. Schedule time to conduct the review and complete the go-live checklist. Be sure to account for time needed to mitigate possible risks and issues, especially go-live blockers. Keep in mind as well the time it takes to prepare the production environment.

Starting the review just a few days away from the go-live date risks a delay. However, starting the review too early can also be detrimental to the process. The project might not be mature enough, or you might not have enough information, to complete the readiness review with reliable results to properly identify potential risks.

To conduct the go-live readiness review, complete all required activities and have the business stakeholders sign off on them.

The following diagram illustrates the [Success by Design](success-by-design.md) implementation phases and when the go-live readiness review occurs:

:::image type="content" source="media/prep-golive-sdb-implementation-phases2.png" alt-text="Diagram illustrating the Success by Design implementation phases, with the go-live review highlighted." lightbox="media/prep-golive-sdb-implementation-phases2.png":::<!-- EDITOR'S NOTE: Please change "go live" to "go-live" in the diagram. -->

Use the [go-live checklist](prepare-go-live-checklist.md) as you conduct the review. Make sure you understand the responses on the checklist. If something isn't clear, ask questions and confirm the answers.

Identify all the possible risks and issues in each key area and get recommendations. Create a mitigation plan with actions to address identified issues and risks and assign an owner for each action. Follow up on the mitigation of identified issues for critical activities.

Identify workarounds for any go-live blockers.

Keep stakeholders informed about the results of the go-live review and any mitigation actions.

After the review is complete, the implementation team determines whether the go-live date is feasible.

## Next steps

- Determine the [go-live check list](prepare-go-live-checklist.md).
- [Prepare your production environment](prepare-go-live-production-environment-readiness.md) for go-live.
- Review the [cutover process](prepare-go-live-cutover-strategy.md).
- Review specific guidelines for [finance and operations apps](prepare-go-live-finance-and-operations-apps.md) and [customer engagement apps](prepare-go-live-dynamics-365-customer-engagement.md).
