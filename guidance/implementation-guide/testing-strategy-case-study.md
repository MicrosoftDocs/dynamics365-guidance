---
title: Case study in testing strategy for Dynamics 365 projects
description: Read a real-life story of how an implementation team learned the hard way why testing is essential for a successful Dynamics 365 project.
ms.date: 01/23/2024
ms.topic: concept-article
author: edupont04
ms.author: veneva
ms.custom:
  - evergreen
  - ai-seo-date: 01/23/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Case study in testing strategy

Testing is a vital part of any Dynamics 365 project. You need to test your solution to make sure it meets your requirements, works as expected, and doesn't cause any problems. Testing also helps you prepare your users, processes, and data for the new solution. But testing can be challenging and time-consuming&mdash;and easy to overlook or postpone.

To show you why testing is so important, we've chosen a true story that could have been titled **The right environment for the right test: A missed opportunity**.

## The setup

A manufacturing company that makes recreational vehicles was implementing Dynamics 365 Supply Chain Management. It had created a testing strategy that included four testing cycles, including user acceptance testing.

The team had included most of the common test types except [performance testing](testing-strategy-test-types.md#performance-testing). They thought that performance testing wasn't necessary for the first rollout, since they were only implementing the manufacturing business unit with few extensions. They planned to add the servicing business, the warranty management, and other operations in the next rollouts. For now, they were using a partner solution for servicing, and their dealership network used it to order parts and honor warranties.

The first testing cycle went smoothly. The team tested the first wave of the solution without any integrations, and they were satisfied with the performance.

## Second round of tests

For the second wave of testing, the team introduced some of the integrations as part of the scope for the test cycle. However, they used made-up data and a small amount of migrated data to emulate the integrations. The integrations worked well for testing purposes, and the data volume was low.

## Third round of tests

For the third testing cycle, things looked great. The team was ready to do a more comprehensive end-to-end test with real integrations and real data migration.

But then they ran into major problems. They were testing with a larger number of users and integrations and with the data volume they expected for production. The solution couldn't handle the load. It slowed down significantly. The team blamed the cloud infrastructure for the test environment not performing well. This outcome raised concerns among the business stakeholders.

The team decided to proceed with user acceptance testing. They thought that since the production environment would have higher specifications, the performance issues would disappear. The organization signed off and prepared to go live.

## Going live

The first day of the go-live was normal, and everything worked fine. The implementation team decided to switch on the integrations for the servicing solution on the second day.

Performance dropped dramatically. Users couldn't transact in Dynamics 365, service departments from the dealerships couldn't connect effectively, shipments started to slow down, and the shop floor had trouble moving inventory to production.

The implementation team provided urgent support. They quickly found out that the integration was creating a bottleneck by making frequent OData calls to check inventory, create sales orders, and invoice while connected to the dealership partners using the servicing solution. They stopped the integration and things went back to normal. It was clear that the integration was the culprit.

## Finding the right solution

The team found a solution after troubleshooting, but it required a change to the integration design pattern and fast action to fix it and keep operating. The team worked hard for days to keep things working during this painful first week, which affected the organization's perception of the solution.

In hindsight, they realized that they should have validated the designs for integrations with real data volumes earlier. They also realized that testing in production for the first time with real volumes was a bad idea. They had less time and more risk to make any fixes while running live operations. They had assumed that their solution was almost standard and would perform well, but they had overlooked the unique challenge of their integrations.

For the next phases, the organization included performance testing in a dedicated environment to stress test the solution. They executed these tests earlier, with more scenarios and UAT that included parallel processing of people testing and integrations running. They were able to have a second go-live to include the company's accessories manufacturing business, and it was much easier.

The organization learned the hard way that it's never too early to start testing according to the project needs. The later the testing, the bigger the risk.
