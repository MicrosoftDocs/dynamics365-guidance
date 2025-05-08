---
title: Develop a performance testing strategy
description: Learn how to define a performance testing strategy that simulates realistic system usage and meets your performance goals for your Dynamics 365 solutions.
author: TimoGossen
ms.author: timogoss
ms.date: 01/30/2024
ms.topic: concept-article
ms.custom:
 - ai-seo-date: 01/29/2024
 - ai-gen-docs-bap
 - ai-gen-desc
 - ai-gen-title
 - bap-template
content_well_notification: AI-contribution
---

# Develop a performance testing strategy

Performance testing is a way to measure how well your Dynamics 365 solution works under different conditions. It helps you make sure that your solution meets the requirements of your project team, business stakeholders, and users.

In this article, you'll learn how to:

- Define what makes a good performance test
- Plan your performance testing scenarios and goals
- Document your performance testing results

## What makes a good performance test?

A good performance test should simulate how users will use your solution in real life. It should also help you check whether your solution meets your performance goals.

To create a good performance test, follow these principles:

### Be realistic

Don't try to push your solution to its breaking point. Instead, try to model the expected usage of your solution as closely as possible. To do this, you need to:

- Understand the number and types of users who will use your solution at the same time. Define user personas that represent different roles, locations, security configurations, data sets, and activities.

- Define day-in-the-life scenarios that reflect the actions that users perform on a typical day. Include peak load and normal load scenarios.

- Use realistic data volumes for each scenario. Don't use more or less data than users need.

- Use realistic client infrastructure for each scenario. For example, if your users will access your solution from mobile devices with poor connectivity, test your solution under those conditions.

- Use realistic system configurations for each scenario. Make sure that your testing environment matches your production environment as much as possible. Use the same security settings, data sources, integrations, and reports.

### Be isolated

Use a dedicated environment for performance testing. This will help you avoid interference from other activities or processes that might affect your results. It will also help you avoid disrupting other testing activities, such as user acceptance testing (UAT).

### Be repeatable with low effort

You might need to run your performance test more than once. For example, you might need to test different versions of your solution, or test after making some changes or optimizations. To make this easier, you should:

- Automate your performance test as much as possible. Use tools that can run your test scenarios with a single click or on a schedule.

- Use the same data and settings for each test run. Make sure you have a consistent baseline to compare your results.

- Use the same tools and methods for each test run. Make sure you measure and report your results in the same way.

### Be functionally correct

Your performance test results are meaningful only if your solution works correctly. If any errors occur during your test, you should fix them and run the test again before analyzing the results. Otherwise, you might get inaccurate or misleading results.

### Document results

You should document your performance test results clearly and consistently. Your documentation should show:

- Whether your solution meets your performance goals for each scenario
- When and how you ran each test
- What version of your solution you tested
- Any errors or issues that occurred during the test
- Any changes or optimizations that you made after the test

## Plan performance tests

Before you run your performance tests, you should plan your testing strategy and document it. Your testing strategy should include the following elements:

- Performance testing scenarios: These are the day-in-the-life scenarios that simulate how users will use your solution. You should include key user activities, background or batch processes, integrations, and reports for each scenario.

- Data volumes: These are the amounts of data that users will work with in each scenario. You should include normal and peak data volumes.

- Response time targets: These are the times that users expect or accept for each scenario. You should include ideal and maximum targets.

- Workload: This is how many users will use your solution at the same time in each scenario. You should include normal and peak workload.

- Data preparation: These are the tasks that you need to do to get the data ready for each scenario. For example, you might need to import data from a file or create data in the system.

- Testing environment: This is where you'll run your performance tests. You should choose an environment that matches your production environment as closely as possible.

- Testing iterations: These are how many times you'll run your performance tests. You should plan for at least two rounds of testing: one before making any changes or optimizations, and one after.

- Testing tools: These are the tools that you'll use to run and monitor your performance tests. You should choose tools that can automate and measure your test scenarios.

- Documentation tools: These are the tools that you'll use to document and report your performance test results. You should choose tools that can capture and display your results clearly and consistently.

- User profiles: These are the types of users who will use your solution. You should define user personas that include their roles, locations, security configurations, data sets, and activities.

- Investigation and fixing workflow: This is how you'll identify and resolve any performance issues that occur during your testing. You should define the guidelines and steps for troubleshooting and optimizing your solution.

- Risks: These are the potential problems or challenges that might affect your performance testing. You should identify the risks and how to mitigate them. For example, you might face delays or budget constraints due to performance testing.

## Network conditions during testing

You should also consider the network conditions during your testing. Network conditions can affect the performance of your solution, especially if you have users or components in different parts of the world.

To test the best possible performance of your solution, you should make sure that your testing environment is located in the same Azure region as your production environment. This will minimize the latency between your solution and your users or integrations.

To test the actual performance of your solution, you should also test it under different network conditions that reflect how users will access it in real life. For example, you might need to test it with different bandwidths, latencies, or devices.

## Next steps

- Find out how to [address performance issues](performing-solution-address-performance-issues.md) that you encounter during testing or production
- Explore the [product-specific guidance for performance optimizations](performing-solution-product-specific-guidance.md) for different Microsoft products and services
- Request a [FastTrack performance workshop](performing-solution-workshop-strategy.md) to get expert help and guidance on your solution performance
- Use the [checklist: Performance focus](performing-solution-product-checklist.md) to review your solution design and implementation for performance considerations
- Read the [case study](performing-solution-product-case-study.md) of how a customer improved their solution performance with FastTrack support
