---
title: Checklist for your test strategy plans
description: Follow this checklist to make sure you cover all the important aspects of your test strategy for your Dynamics 365 project.
ms.date: 01/23/2024
ms.topic: checklist
author: edupont04
ms.author: veneva
ms.custom:
  - ai-seo-date: 01/23/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Checklist for your test strategy

## Planning

| Done? | Task |
| :---: | --- |
| &check; | Plan how you'll create, run, and manage your test cases. Estimate how many resources (people, hardware, environments, devices) you'll need for each test cycle. Align your test cycles with the processes that are in scope for your project. |
| &check; | Set up a tracking system that monitors the progress, results, ownership, and issues of each test case. Define a process for fixing, retesting, and deploying corrections for any errors that you find during testing. |

## Implementation

| Done? | Task |
| :---: | --- |
| &check; | Make sure your developers do unit testing in a development environment. Unit testing checks the function, code, and configuration of all extensions and integrations that you add to your solution. |
| &check; | Make sure your functional consultants or subject matter experts (SMEs) do functional testing in a test or development environment. Functional testing validates the design of your solution against the requirements. |
| &check; | Make sure your SMEs do process testing in a test environment. Process testing runs multiple processes consecutively and checks whether your solution supports your business operations. It also looks for any unintended outcomes or side effects. |
| &check; | Do performance testing on critical processes throughout the **Implement** and **Prepare** phases. Performance testing measures how well your solution performs under realistic load and growth conditions. |
| &check; | Do end-to-end testing throughout the **Implement** and **Prepare** phases in a test environment. End-to-end testing covers all the full business processes in scope and all the connected integrations and solutions. Use increasingly realistic migrated data for each test cycle. |
| &check; | Do user acceptance testing (UAT) in a test environment during the **Prepare** phase. UAT tests how ready your users, processes, and solution are to operate the business in the new environment. |
| &check; | Do regression testing in a test environment, or in a development environment for updates, throughout the **Implement** and **Prepare** phases and after go-live. Regression testing makes sure that the solution performs as expected after a change. |
| &check; | Consider using automation for functional, process, end-to-end, performance, and regression testing. Automation can save you time and effort by running repetitive or complex tests faster and more accurately. |
| &check; | Create a test communication plan with clear scope and objectives. Specify the schedule, sequence, roles, and issue resolution process for each test cycle. Communicate the plan to all the stakeholders and participants involved in testing. |

## Go-live

| Done? | Task |
| :---: | --- |
| &check; | Plan a [mock cutover](testing-strategy-test-types.md#mock-cutover) in the new production environment. A mock cutover tests and confirms the estimated time and steps for all the tasks that you need to do during the go-live stage. |

## Next steps

- Learn about the [different types of testing](testing-strategy-test-types.md) that you can use for your Dynamics 365 solution
- Learn how to [create and use a test plan](testing-strategy-planning.md) for your testing activities
- Learn how to [run your tests and handle the outcomes](testing-strategy-run-tests.md)
- Learn how to [test your solution after changes or updates](testing-regression-tooling.md)
- Read a [case study](testing-strategy-case-study.md) of how an organization implemented a testing strategy for its Dynamics 365 solution
