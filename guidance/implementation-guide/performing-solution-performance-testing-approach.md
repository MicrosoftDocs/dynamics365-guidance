---
title:  Test for performance
description: Learn how to develop and document a performance testing strategy to model expected system usage and achieve the defined performance goals of your Dynamics 365 solutions.
author: TimoGossen
ms.author: timogoss
ms.date: 06/19/2023
ms.topic: conceptual
ms.custom:
 - ai-gen-docs-bap
 - ai-gen-desc
 - ai-seo-date:08/28/2023
 - bap-template
---

# Test for performance

The project team, business stakeholders, and users need to be confident that requirements they identified are achieved when the system is implemented. A performance testing strategy makes sure system performance is measurable and provides a clear indication of whether performance is acceptable.

## What makes a performance test good?

A common approach to performance testing is to try to push the system to the breaking point to learn whether it can handle the demand. However, this approach typically provides little value, particularly in Dynamics 365 apps. The best approach is to model or simulate the expected system usage, both peak load and day-in-the-life business scenarios, to make sure the solution can achieve its defined performance goals.

### Realistic

Be realistic. Understand the number and user personas of the people who use the system at a given time. Also define day-in-the-life activity profiles for the personas to understand the actions they perform. If the performance test incorrectly assumes that all users run the most complex processes concurrently, the projected demand is far higher than the reality. Strive to model usage accurately to get the most meaningful results from the test.

It's important to understand the difference between testing the system's functionality and testing the system as a user would use it. *Functional testing* often involves invoking specific logic and measuring the outcome, such as an API call. In contrast, *user testing* models the actual behavior of a user. Testers often create a suite of functional tests pointed at a web service, execute them with a large number of concurrent users, and call it a performance test. That approach provides misleading results. It pushes certain functionality more than the usage that's expected when the features are live, creating false performance issues. It also bypasses other functionality entirely, such as the user interface. The result is that genuine performance issues can slip through testing unidentified.

Keep in mind that users' interaction with the application is fairly slow. They don't typically select buttons as quickly as they can. They take time to think between actions. You can incorporate that aspect into a performance test as a think-time variable. It varies from user to user, but an average value is sufficient to model behavior. The key point here is to develop a performance test that represents many users working concurrently and place a realistic amount of demand on the system.

Developing a reliable performance test also includes realistically modeling client infrastructure. For example, there's little value in performance testing your Dynamics 365 Field Service mobile application from the office if your technicians will use it primarily in areas of poor connectivity.

The configuration of the system should also be realistic and based on the expected infrastructure and configuration of the production environment, use real security configurations for the test users, and work with the anticipated volumes of data in production.

### Isolated

A dedicated performance testing environment is recommended for two main reasons:

- Performance test results are meaningful only if testers are aware of the activities that occur in the system during the test. A performance test is worthless if an unaccounted-for process places extra demand on the system while the test is running.

- It's common for performance testing to occur around the same time as user acceptance testing (UAT). Performance testing can take a substantial amount of time to execute and push the system to its limits, disrupting any manual user testing activities. A dedicated performance testing environment ensures that performance testing can happen in parallel with other testing.

### Business data

Key to good performance testing is using the configurations and data that will ultimately go live in production. All the data preparation activities must be ready in advance. For example, data from 100,000 customers or sales orders should be available in an import file.

### Repeatable with low effort

Ideally, you execute a performance test once and use the results to make sure the criteria that are specified in the requirements are achieved. However, performance testing is rarely a one-time activity. Often, it's an iterative process. It happens for various reasons; for example, functional changes might occur during UAT that risk a change in performance. Similarly, if performance testing demonstrates an unacceptable level, you must retest the optimizations when the solution is implemented.

If a low-effort performance testing approach isn't available, it can be tempting to skip performance test iterations. But that makes it difficult to assess the effect of any changes you make between runs. Conversely, a fully automated process, potentially including environment provisioning and data setup, can be executed frequently with minimal effort, providing a clear picture of variations in performance in response to specific changes.

### Functionally correct

A performance test result is meaningful only if the system functions correctly. It's tempting to focus on the performance metrics of successful tests. However, if errors occur, they should be corrected and the test should be executed again before any analysis is performed on the results. Deviations in behavior between test runs can significantly skew a performance test result and make any comparison meaningless.

### Document results

The output of performance testing activities should be documented clearly so that interpretation is straightforward. The results should be mappable to performance testing criteria. The team should be able to quickly assess whether the requirements were achieved or whether there are gaps between requirements and results. It should also be possible to identify when the performance test was executed and against which version of code if applicable.

Finally, it's important that the information in the documented report of results remains consistent with the defined template. The team might need to compare various performance test run results as changes are made.

## Plan performance tests

Document your performance testing strategy and include the following tasks:

- Performance testing scenarios including key user activities, background or batch processes, integrations, and reports
- Normal and peak data volumes for each scenario
- Ideal target and maximum acceptable target response time for each scenario
- Day-in-the-life workload to simulate in the most realistic manner, especially at peak hours
- Data preparation activities for each scenario; for example, existing master data or transaction data in the system or creation of a file to import
- Environment for performance testing
- Iterations of performance testing (plan for two or more rounds)
- Performance testing tools
- Test results documentation tool
- Number and profile of concurrent users, including security configurations
- Guidelines and workflow for investigating and fixing performance issues
- Risks such as delays and budget related to performance testing

We recommend investing the time and effort to automate this process as much as possible. For example, with relatively little effort, you can set up performance tests to run through Azure DevOps release pipelines, providing a way to execute test runs with a single click of a button, or automatically after a deployment. You can even run them overnight.

## Network conditions during testing

Be aware of network conditions during testing. Performance tests are often conducted in isolated environments with the best network conditions, so they usually show favorable results. However, when the solution is moved to real-world use, performance issues might arise due to actual network conditions and the solution being implemented at scale.

To benchmark what's feasible for the solution when all network conditions are favorable, make sure that the performance testing environment is located in the same Azure region where you plan to deploy the production environment. minimizing testing latency can help identify potential location network issues if the test results vary with the location testing.

## Next steps

- [Performance overview](performing-solution.md)
- [Prioritize performance](performing-solution-prioritize-performance.md)
- [Design for performance](performing-solution-design-for-performance.md)
- [Address performance issues](performing-solution-address-performance-issues.md)
- [Product-specific guidance for performance optimizations](performing-solution-product-specific-guidance.md)
- [FastTrack performance workshop](performing-solution-workshop-strategy.md)
- [Checklist: Performance focus](performing-solution-product-checklist.md)
- [Case study](performing-solution-product-case-study.md)
