---
title: Transition to new solutions successfully with the cutover process
description: Learn how to plan and execute a successful cutover to transition to a new Microsoft Dynamics 365 solution with minimal disruption.
ms.date: 06/06/2023
ms.topic: conceptual
author: vaniusca
ms.author: vaniaf
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:08/22/2023
  - bap-template
---

# Transition to new solutions successfully with the cutover process

The cutover is the last mile before going live with a new Dynamics 365 implementation. It marks the transition from the legacy system to the new solution. Cutover entails the execution of tasks that are required to successfully go live with a well-defined scope in a production environment.

In the past, a "big bang" go-live after a multi-year implementation period was common. Now, businesses often follow a more agile approach. For example, a company might plan an initial go-live in a small country/region or just for the core financial processes, and complete the rollout to other countries/regions or more complex functionality later. A cutover process needs to be defined and executed for each rollout.

Most businesses have only a short time to complete cutover activities. During cutover, users can't use the old system any longer and the new one isn't ready yet. The cutover period is often referred to as the "cutover weekend" because it's usually less than 48 hours. For businesses that must operate all the time, it might be even shorter.

The cutover process involves several steps that you must plan, conduct, monitor, and complete to transition successfully to the new solution. They include strategy, planning, execution, monitoring, and control.

:::image type="content" source="media/prep-golive-cutover.png" alt-text="Example of the cutover phases" lightbox="media/prep-golive-cutover.png":::

## Develop a cutover strategy

Developing a cutover strategy begins early in project planning. It's refined throughout the project and completed before the cutover plan is created. The cutover strategy ensures the cutover plan aligns with organizational objectives. It includes the following factors:

- Timing, market conditions, and other environmental considerations
- Organizational readiness requirements for competencies and resources
- Setting up the communication plan
- Defining roles and responsibilities

### Timing

It's challenging to set a realistic go-live date early in implementation planning. It's always important to leave some buffer time when planning milestone dates, but it's especially true for the go-live date.

Consider the time you need to complete testing and resolve any issues that might arise. Factor in how long it will take to prepare the production environment and complete each cutover activity.

Ideally, plan to go live during a natural ebb in business activities. For example, a seasonal retailer might choose the season when sales are slow to reduce any negative impact on the business. Avoid going live during busy times like month- or quarter-end. Take holidays and typical vacation schedules into account. It's important to make sure that all team members and users are fully available during the cutover period.

Also consider system release schedules. Microsoft continually makes improvements in its systems to deliver a better product. Established release dates usually entail a mandatory update. Decide whether to set the go-live date before or after a release. This consideration also applies to any other external applications you might be integrating with your new solution.

External factors might also affect your project timelines. Long-running projects risk unforeseen events, such as supply chain shocks caused by global pandemics, emergency business reorganizations, or significant changes in regulations. External factors are part of the risk management of your project. It's important to create a list of possible mitigation plans for unforeseen events.

Finally, add some buffer time. Bear in mind that it's expected that you'll need to adjust dates and resources along the way because of delays, unforeseen events, loss and replacement of resources, and external or internal dependencies that don't complete on time.

### Resources and competencies

When program stakeholders define the cutover strategy, they should identify which roles and competencies are required for the activities in the cutover plan and assign ownership of each activity. They should verify that all necessary resources are available not only for the requested duration of the cutover plan, but also to support the solution after go-live.

These resources might need to be requested from external companies if they're not internally available for the project team.

### Communication plan

The communication plan is an essential part of the cutover strategy. It provides visibility into who the stakeholders are, at what point in time they should send or receive communications, and who the points of contact are. It should include at least one communication channel. The communication plan should also identify and document the different communications required for go-live, who is responsible for triggering them, and the individuals or distribution lists who should receive them.

### Roles and responsibility

Effective delegation of tasks is key for a successful cutover. It's important to define and assign the roles that are needed, based on the activities, skills, and responsibilities that are required. Assign an owner to each cutover activity and make sure all owners understand what's required of them during execution.

Knowing the skills and responsibilities that are necessary helps you define which roles need to exist and whom to assign them to. It's important that people who have a role know what to do and how to do it, and that they have a clear definition of when the task is considered complete. Make sure these steps are practiced multiple times for repeatability and reliability.

## Develop a cutover plan

Cutover is a critical and complex process that must be planned and practiced in advance. The center of the cutover process is the cutover plan. It lists in detail every step that must be completed to prepare the production environment to execute business processes after the cutover. The cutover plan is a living document that's updated throughout the project as the solution evolves.

Cutover activities include system configuration, data migration, data validation, and, when applicable, decommissioning of legacy systems. These steps must be precisely orchestrated to minimize disruption and ensure a successful deployment.

Cutover activities are performed as part of go-live, but planning for the cutover should start early in the project. All project stakeholders should be involved in each planned activity and should sign off on them, with a commitment that all necessary resources are available for the requested duration.

When you're creating the cutover plan, consider and document all dependencies and list each task that needs to be completed. Include the timing of each task down to the minute, who's responsible and accountable for each one, instructions, verification steps, and any other information that's associated with a task.

The implementation team should practice all the steps in the cutover plan multiple times.  Perform mock cutovers or dress rehearsals, simulating the activities of the real cutover in sandbox environments. Thorough rehearsal makes sure the cutover strategy and communication plan are ready, increases the predictability of the outcome, and allows the team to make backup plans, confirm the duration of each activity, and identify and correct any issues with the plan.

A cutover plan is successful when there are zero or few disruptions during the execution of the cutover and a plan is in place to mitigate any breakdowns.

### Components of a cutover plan

A successful cutover always begins with a detailed and well-defined cutover plan. The plan should detail the actions that are required to cut over to the new system, the timelines for completing them, who owns each one, and the criteria that define successful completion of each task.

It should also include a rollback plan. Planning a rollback is especially important to make sure the business isn't affected if the cutover isn't successful. A backup plan should be in place to retry the cutover at another time.

The following illustration shows an example of a cutover plan with a detailed list of activities:

:::image type="content" source="media/prep-golive-cutover-plan.png" alt-text="Table of activities in a sample cutover plan." lightbox="media/prep-golive-cutover-plan.png":::

All key stakeholders should attend go/no-go meetings with the implementation team. During these meetings, the team should review any open issues, risks, and unresolved defects and collectively decide whether the solution is ready for production. The decision should be made according to the success criteria defined in the cutover plan. For example, one of the go/no-go decision criteria might be the number of blockers or high-impact bugs identified during user acceptance testing (UAT).

The cutover plan should specify workarounds to issues that might delay go-live, if a workaround is acceptable. For example, if UAT identifies a blocking issue but a workaround can be implemented until a permanent fix can be applied, and stakeholders accept such a temporary solution, the plan should note it. When you're considering workarounds, also consider how they affect users. Users judge a solution by how well they can use it, regardless of whether there's a workaround. This is another reason why all key stakeholders need to participate, not only to define the success criteria, but also to make the final go/no-go decision.

## Execute the cutover plan

Executing the cutover plan includes the following activities:

- Communicate activities, milestones, and results to stakeholders in accordance with the communication plan.

- Execute, monitor, and complete all planned cutover activities.

- Address any unforeseen issues or determine they can be addressed after go-live.

- Communicate any issues to stakeholders and document their acknowledgment.

### Entrance criteria

Complete the following activities before you execute the cutover:

1. Make sure the data migration and validation plans, internal and external communication plan, go-live support plan, training plan, and cutover plan are completed and business stakeholders have signed off.

1. Complete performance testing, system integration testing, and UAT with exit criteria satisfied.

1. Build and test the data migration strategy, including configuration data.

1. Identify all mock cutover and cutover resources.

1. Verify the production environment is ready.

1. Schedule user training to complete by go-live.

### Exit criteria

Complete the following activities to execute the cutover:

- Perform all cutover steps in sequence.

- Make sure the steps fit in the time window established for the cutover.

- Document any failures and issues and resolve or identify solutions to resolve them.

- Execute the data validation plan.

- Obtain stakeholder sign-off at the cutover go/no-go checkpoint.

When you execute a mock cutover, it's crucial to verify the sequence and length of each task to create a realistic plan for the actual cutover. It also helps you identify the need for mitigation plans and whether you need to run more mock cutovers.

## Successful go-live and transition to support

After the cutover is complete, the new solution is released to users. At this point, the solution is operational. To ensure a smooth handover to the operations teams, follow your [operational support plan](prepare-go-live-checklist.md#operational-support-readiness).

## Next steps

- Review specific guidelines for [finance and operations apps](prepare-go-live-finance-and-operations-apps.md) and [customer engagement apps](prepare-go-live-dynamics-365-customer-engagement.md).
- Review the [go-live checklist](prepare-go-live-checklist.md).
