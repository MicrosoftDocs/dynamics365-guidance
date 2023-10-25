---
title: Case study for tests 
description: In this article, we explore a case study that shows how an implementation team build their test plan for their Dynamics 365 solution.  
ms.date: 05/15/2023
ms.topic: conceptual
author: edupont04
ms.author: veneva
---

# Case study for tests in Dynamics 365 implementation projects

To illustrate the importance of a healthy test strategy for an implementaiton project, we've chosen a true story that could have had the title **The right environment for the right test: A missed opportunity**.

## The setup

An organization in the manufacturing industry manufactures recreational vehicles. They're implementing Dynamics 365 Supply Chain Management and have created a testing strategy. The test strategy includes four testing cycles, including user acceptance testing.

The team includes the most common test types except [performance testing](testing-strategy-test-types.md#performance-testing). They assume that the first rollout won't require performance testing since the project just implements the manufacturing business unit with few extensions to it. The next rollouts will include the servicing business, including the warranty management of recreational vehicles plus other operations. The servicing operations continue to be executed as a third-party solution for now and their dealership network will be using this system to order parts and honor warranties.

Soon, during the first testing cycle, the team started to test across the first wave of the solution where there were no integrations, so completing testing was satisfactory in terms of the cycle performance.

## Second round of tests

As the team get ready for their second wave of testing, they introduce some of the integrations as part of the scope for the test cycle. However, the integrations are emulated with made-up data and a bit of migrated data. The integrations work for test purposes, and the volume of migrated data was small.

## Third round of tests

For their third testing cycle, things look great. The team is ready to do a more comprehensive testing by using end-to-end testing, this time with real integrations and real volumes of data migration.

Unexpectedly, the team runs into major blockers. We now know that they've run tests that combines a larger number of users and integrations with the size of operations that they expect for production. The solution couldn't keep up with the needs of the test cycle, and they weren't even in production. The first reaction from the team is that the cloud infrastructure for the test environment wasn't performing well enough. This outcome of the test cycle raises concerns with the business stakeholders.

The team is ready to prepare for user acceptance testing, and they continue to expect that thisthe performance problems won't be an issue in production due to that environment having higher specs. They assume the production environment can solve this performance challenge, so they decided to continue, complete UAT, and move to production. The organization signs off and prepares to move to the next stage and go live in production.

## Going live

Finally, the day comes when all departments switch to new solution. The first day is pretty normal, and everything works great. The implementation team decides to switch on integrations for the servicing solution on the second day. On the second day, they switch on the connection with the service department, and integrations started to flow into Dynamics 365.  

Now they run into their first business stopper: They have a sudden decrease in performance. Users can't transact in Dynamics 365, service departments from the dealerships can't connect effectively, shipments start to slow down, and the shop floor is having a hard time trying to keep inventory moving to production.  

The implementation team provides hyper-focused care. Immediately, they start to check for what could be blocking the operation, and they find the problem. The integration was creating a bottleneck by making important OData calls to check inventory, creating sales orders, and invoicing while connected to the dealership's partners using the servicing solution. They stop the integration and things go back to normal. But it's clear that the integration was the cause.

## Finding the right solution

The team found a solution after troubleshooting, but it will require a change to the integration design pattern and fast movement to solve it and keep operating. Part of the revenue from the recreational vehicle business comes from servicing and providing parts to the dealerships. The team works hard for days to keep things working during this painful first week, which impacts the perception of the organization in the solution.  

In retrospect, validating designs for integrations with a volume of data was key to preventing this scenario and the issue they had during real operation. The team's morale was affected after working hard during the implementation season, all because they missed one important test; the performance test. The team thought emulating early and validating in production would be OK, but the cost of that decision was high.

## Conclusions

This team learned that including performance testing as early as possible, with actual volumes in the right environments that perform at the same volumes expected in production, would help to detect a design problem and correct it in time. The team also learned that "testing" in production for the first time, and with the real volumes, wasn't the best idea. The time available to make any fixes was reduced due to the live operations and correcting as they go introduced bigger risks. The assumption of the team that they were implementing almost standard functionality led them to think that the solution would perform fine, but the actual challenge made the solution unique, which requires extensive testing.

For the next phases, this organization included performance testing. They dedicated an environment to stress test the solution with their own business needs and they executed these tests earlier with more scenarios and UAT that included parallel processing of people testing and integrations running. They were able to have second go live to include their accessories manufacturing business and it was a breeze in comparison.

It's never too early to start testing and do so according to the project needs. The later the testing, the bigger the risk.

## Next steps

Go back to the overview at [Testing strategy](testing-strategy.md)
