---
title: Transition to new solutions successfully with the cutover process
description: Learn how to plan and execute a successful cutover to transition to a new Microsoft Dynamics 365 solution with minimal disruption.
ms.date: 01/30/2024
ms.update-cycle: 1095-days
ms.topic: how-to
author: vaniusca
ms.author: vaniaf
ms.custom:
  - evergreen
  - ai-seo-date: 01/30/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
  - bap-template
content_well_notification: AI-contribution
---

# Transition to new solutions successfully with the cutover process

Cutover is the last step before you launch your new Dynamics 365 solution. It's when you switch from your old system to the new one. You need to complete some tasks to make sure that your new solution works well in the production environment.

Cutover can be tricky because you have a short time window to finish everything. During cutover, you can't use your old system or your new one. People often call this time the "cutover weekend" because it's usually less than 48 hours. For some businesses, it might be even shorter.

A successful cutover involves several steps:

1. Develop a cutover strategy that outlines your goals, resources, timing, and communication.
1. Develop a cutover plan that lists all the tasks that you'll do during the cutover and how you'll verify and sign off on them.
1. Practice the cutover plan in a test environment until you're confident that everything works well.
1. Execute the cutover plan in the production environment and solve any problems that arise.
1. Go live and transition to support your new solution.

## Develop a cutover strategy

Your cutover strategy is your big-picture plan for how you'll do the cutover. You should start working on it early in your project and update it as you go along. Your cutover strategy should include these factors:

- When you'll do the cutover
- Who will do what during the cutover
- How you'll communicate with everyone involved in the cutover
- What roles and responsibilities you'll assign

### When you'll do the cutover

Choosing the right time for your cutover is important. It's always important to leave some buffer time when planning milestone dates, but it's especially true for the go-live date. You want to avoid any delays or problems that could affect your business.

Think about how long it will take to test your solution, fix any issues, set up your production environment, and do all the tasks in your cutover plan.

Try to pick a time when your business is less busy. For example, if you sell seasonal products, you might want to do the cutover when sales are slow. Don't do the cutover when you have to close your books or report your results. Consider holidays and vacations, too. You need everyone to be available during the cutover.

Also think about system release schedules. Microsoft updates its applications often to deliver a better product. Sometimes, you have to update your system, too. Decide if you want to do the cutover before or after a release. This also applies to any other apps that you integrate with your solution.

Sometimes, things happen that you can't control, like a pandemic, a reorganization, or a change in regulations. These things can affect your project timeline. You should have a plan for how to deal with them if they happen.

Finally, add some extra time for unexpected situations. You might have to change your dates or resources because of delays, events, changes, or dependencies.

### Who will do what during the cutover

You need to make sure that you have enough people with the right skills and knowledge for the cutover. You might need to ask for help from outside your team or company.

You also need to make sure that everyone knows what they have to do and how to do it. You should assign an owner for each task and check that they understand their role.

### How you'll communicate with everyone involved in the cutover

Communication is key for a successful cutover. You need to keep everyone informed about what's happening, what's next, and what's done.

You should have a communication plan that shows who the stakeholders are, when and how they'll get or send messages, and who they can contact if they have questions or issues.

You should also decide what kind of messages you'll send for different situations, like starting the cutover, finishing a task, finding a problem, or going live.

### What roles and responsibilities you'll assign

You need to define and assign the roles that are needed for the cutover, based on the tasks, skills, and responsibilities that are required. For example, you might need someone to manage the data migration, someone to verify the data quality, someone to monitor the system performance, and someone to troubleshoot any issues.

You should also decide who will make the final decision about whether your solution is ready for production. This is called the go/no-go decision. You should have some criteria for making this decision, like how many bugs or issues are acceptable and how they can be fixed or worked around.

## Develop a cutover plan

Your cutover plan is your detailed list of tasks that you'll do during the cutover. It should show every step that's needed to get your solution ready for production.

Your cutover plan should include these components:

- The order and timing of each task
- The owner and backup owner of each task
- The instructions and tools for each task
- The verification and sign-off steps for each task
- A rollback plan in case something goes wrong

The following illustration shows an example of a cutover plan with a list of tasks:

:::image type="content" source="media/prep-golive-cutover-plan.png" alt-text="Table of tasks in a sample cutover plan." lightbox="media/prep-golive-cutover-plan.png":::

You should involve all the project stakeholders in making and approving the cutover plan. They should agree on the tasks, the resources, and the success criteria.

## Practice the cutover plan

Before you do the real cutover, you should practice your cutover plan in a test environment. This is called a mock cutover or a dress rehearsal. It helps you make sure that your plan works, your team is ready, and your solution is stable.

You should do the mock cutover as close as possible to the real one. You should use the same data, tools, and people. You should follow the same steps and timing.

You should do the mock cutover several times until you're confident that everything goes smoothly. You should check for any errors or issues and fix them before the real cutover. You should also update your plan with any changes or improvements.

## Execute the cutover plan

Before you start the cutover, you should make sure that:

- Your data migration and validation plans, communication plan, support plan, training plan, and cutover plan are completed and approved by the business stakeholders.
- Your testing is done and any issues are fixed or accepted.
- Your data migration strategy is ready and tested, including configuration data.
- You have all the people and resources you need for the cutover.
- Your production environment is set up and working.
- Your user training is scheduled to finish by go-live.

When these entrance criteria are satisfied, then you're ready to start the real cutover:

- Send messages to everyone involved in the cutover according to your communication plan.
- Do all the tasks in your cutover plan in order and on time.
- Solve any problems that come up or decide if they can wait until after go-live.
- Tell everyone about any problems and get their agreement on how to handle them.
- Check that your solution works as expected in production.
- Get approval from the stakeholders at the go/no-go meeting.

After you finish the cutover, you should make sure that:

- You did all the tasks in your cutover plan correctly.
- You finished everything within your time window for the cutover.
- You recorded any failures or issues and resolved them or found solutions for them.
- You verified that your data is accurate and complete in production.
- You got sign-off from the stakeholders at the go/no-go meeting.

## Go live and transition to support

After you finish the cutover, you can launch your new solution to your users. Your solution is now operational.

To make sure that everything goes well after go-live, you should follow your [operational support plan](prepare-go-live-checklist.md#operational-support-readiness). This plan shows how you'll monitor, maintain, and improve your solution.

## Next steps

- Use the Success by Design [go-live checklist](prepare-go-live-checklist.md) to make sure that you don't miss any important tasks for go-live
- Read the [case study](prepare-go-live-case-study.md) for an example of a successful go-live project
