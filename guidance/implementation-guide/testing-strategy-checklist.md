---
title:  Checklist for the test strategy
description: Get a list of things to remember as part of the test strategy for a Dynamics 365 implementation project.
ms.date: 05/17/2023
ms.topic: conceptual
author: edupont04
ms.author: veneva
---

# Checklist for the test strategy

This article provides a list of things to remember as part of the test strategy for a Dynamics 365 implementation project.  

## Planning

- Plan the test case creation, forecast the resource requirements (people, hardware, environments, devices), and implement the test cycles in accordance with the processes in scope.

- Have a tracking mechanism that monitors the overall progress, pass or fail rates, ownership, and issues tied to specific test cases. Also have a process defined for remediation, retesting, and deployment when errors are found and corrected.

## Implementation

- Make sure the Software Development Lifecycle (SDLC) includes unit testing by the developer in a development environment, with focus on function, code, and configuration of all extensions and integrations.

- Make sure the functional testing is performed by functional consultants or SMEs in a test or developer environment with the primary objective to validate the design against the requirements.

- Make sure process testing is performed by SMEs in a test environment, running multiple processes consecutively, focusing on testing whether the solution allows business operations and monitoring for unintended outcomes.

- Carry out performance testing throughout the Implement and Prepare phases on critical processes to ensure the solution performs while focusing on scaling with realistic load and growth.

- Throughout the **Implement** and **Prepare** phases, perform iterative and cumulative end-to-end testing of all full business processes in scope and connected integrations and solutions in a test environment with increasingly "real" migrated data.

- Perform UAT in a test environment during the **Prepare** phase to test the preparedness of users, processes, and the solution to operate the business.

- Consider automation for functional, process, end-to-end, performance, and regression testing.

- Establish a test communication plan with clear scope and objectives, specifying the schedule, sequence, roles involved, and issue resolution process.

- Perform regression testing in a test environment, or development environment for updates, throughout the **Implement** and **Prepare** phases and post-go live to ensure the solution performs as expected after a change.

## Go live

- Plan a [mock cutover](testing-strategy-test-types.md#mock-cutover) in the new production environment. This test validates and hopefully confirms the estimated times for all the required tasks during the go-live stage.

## Next steps

Review the [Case study](testing-strategy-case-study.md) or return to the overview at [Testing strategy](testing-strategy.md)  
