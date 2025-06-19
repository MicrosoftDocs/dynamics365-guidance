---
title: Run the tests for your Dynamics 365 solution
description: Learn how to execute and track your tests throughout your Dynamics 365 implementation project, including an outline on communicating test plans for test cycles.
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

# Run the tests for your Dynamics 365 solution

Testing your Dynamics 365 solution helps you verify that your solution works as expected and meets the business needs. To conduct effective testing, you need to execute and track your tests according to your test plan.

In this article, you'll learn how to:

- Communicate the test plan for each test cycle.
- Track the progress and results of testing.
- Handle the outcomes and feedback of testing.

## Communicate the test plan for each test cycle

Before you run your tests, you should communicate the test plan to the team involved in testing. This way, everyone knows what to expect and what to focus on during the test cycle.

Your communication should include the following information for each test cycle:

- **Test objectives**: The purpose and goals of the test cycle.
- **Scope**: The processes, requirements, and test cases that are covered by the test cycle. The scope of the test cycle should match the readiness and complexity of the solution version.
- **Schedule**: The time frame and duration of the test cycle.
- **Roles**: The roles and responsibilities of the testers, such as who tests what, how they report their results, who coordinates the test, and who resolves questions or issues.
- **Resolution process**: The process and criteria for reporting and fixing bugs, issues, gaps, or opportunities that are found during the test.
- **Progress**: The method and frequency of tracking and communicating the status of the test cycle.
- **Resources**: The resources and tools that are needed for testing, such as the test environment and access to the apps, hardware, software, or partner systems or services.
- **Test sequence**: The order and dependencies of the test cases, especially for process testing, end-to-end testing, or user acceptance testing.

Part of a successful test cycle is to set clear expectations with the participants, so everyone stays focused on the objective. Consider the test cycle as a mini go-live for the scope in place for the cycle.

## Track the progress and results of testing

Tracking the progress and results of testing is essential for measuring and improving the quality and performance of your solution. Tracking can help you identify and document the issues, patterns, and opportunities that emerge from your testing. It can also help you make decisions and take actions to correct or enhance your solution.

But before reporting bugs, the tester needs to understand the scope and objective of the test. Building the solution is progressive. It's easy to report issues where the scope of the test doesn't include a solution for that and is part of future iterations.

Tracking captures the outcome and performance of the test cycle. It's how the development team and consultants understand the quality of the test cycle. We recommend that you use Azure DevOps for this. It integrates into the entire application lifecycle. All bugs are visible to the teams that need to fix them, and you can see what is or isn't working in general.

### Track the changes in configuration

Some tests might result in changes or adjustments in the configuration of your solution. These changes can affect the behavior and performance of your solution, so you should document and track them carefully. You should also make sure that these changes are reflected in your golden configurations, which are the baseline configurations that you use for testing and deployment.

Making configuration changes can invalidate previous test cases that depend on those changes. You should treat these changes as if they were production changes and make sure they don't negatively affect the tests that passed. You should also plan and execute regression testing to verify that the changes don't introduce new issues.

### Track the bugs

You should document and track every bug that you find during testing. You should provide concise and consistent documentation that follows an agreed structure. You should also include rich information such as test case and test step reference, reproduction steps, screenshots, videos, and so on. This can help the team that needs to fix the bug troubleshoot and resolve it faster and easier.

You should use a centralized repository that's available to the entire project team to track bugs and issues that you find throughout the project and while performing tests. If you can't track bugs and issues through their resolution, you risk missing or forgetting them. This can lead to some issues being discovered only after you go live. Additionally, without the ability to track bugs and issues, you can't track the progression of your solution's stability.

### Distinguish bugs from gaps

A gap is a difference or discrepancy between the expected and actual behavior or outcome of your solution. A gap can be caused by a missing or incomplete feature, a change in the requirements, or a new opportunity for improvement. You should document and track gaps as well, but you should distinguish them from bugs. Bugs are defects that need to be fixed, while gaps are enhancements that need to be discussed and prioritized.

You should stick to the test case when you report bugs or gaps. If you find a gap, make sure the feedback is properly classified and funneled to the right tracking system. You don't want to lose the opportunity to capture a great idea or finding, but you also don't want to confuse it with a bug.

## Handle the outcomes and feedback of testing

Finishing the test cycle requires reporting the results and handling the outcomes and feedback of testing. You should document and track these outcomes and feedback and assign clear ownership and responsibility for them. You should also define the actions and steps needed to resolve or address them.

The outcomes and feedback of testing can affect the next wave of processes or features to be introduced in future test cycles. For example, you might need to add new test cases or update existing ones. You might also need to adjust the scope of the test cycle or the schedule of the next one.

Reporting the results can help you evaluate the performance and quality of the test cycle. It can also help you identify areas of opportunity for the implementation team, because it triggers clear actions to improve the solution. As a result, the next test cycle can provide better results.

For the next test cycle, you should start over, because even passing test cases during this cycle need to be retested in the next one.

## Next steps

- Learn how to [test your solution after changes or updates](testing-regression-tooling.md)
- Review the Success by Design [checklist](testing-strategy-checklist.md) of the key steps and tasks for your testing process
- Read a [case study](testing-strategy-case-study.md) of how an organization implemented a testing strategy for its Dynamics 365 solution
