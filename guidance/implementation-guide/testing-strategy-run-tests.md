---
title: Run the tests for an implementation project
description: Find guidance for how you can run the tests you need for a Dynamics 365 implementation project.
ms.date: 05/17/2023
ms.topic: conceptual
author: edupont04
ms.author: veneva
---

# Run the tests for a Dynamics 365 implementation project

In this article, we explore the minimum components you need to run the tests throughout an implementation project with Dynamics 365.

The prerequisites required to move to execution are having a test plan, test cases, and clear testing cycles that are defined according to the progressive readiness of the solution.

Now we focus on the tactical components for prepping the execution, what to keep in mind to communicate the scope, and how to track the progress and outcome.

## Communicate the plan for the test cycle

Align the teams before they run their tests. This way, everybody stays focused on the expected outcome of the test cycle. It's especially important when you test with several people involved, like process testing or functional testing.

In your communication, you share the test plan for the test cycle. Communicate the following information to the team during testing.

- **Test objectives**  

  Here you explain the purpose of the testing cycle.

- **Scope**  

  Before you start testing, you describe the scope and purpose of the testing cycle. You share the processes, requirements, and tests cases in this test cycle. Every new testing cycle requires detail on how the iteration has been designed in terms of incremental testing, and what the team must test. The scope of the test cycle is aligned to the solution version being used.

- **Schedule**  

  The time expected to be used to run the test cycle.

- **Roles**  

  Who tests what, and how are the test cases distributed? How do they report test case execution so dependent teams can continue the testing? Who is the orchestrator of the test? Who resolves questions on test cases per area?

- **Resolution process**  

  One of the objectives to test is to identify any defect in the solution. The communication plan needs to specify how those bugs are reported but also how to document the feedback from the tester.

- **Progress**  

  How is the progress recorded and communicated so everybody can see the current state of the testing cycle?

- **Resources**  

  The communication needs to specify where the testing happens and how to access the apps. It determines any extra equipment needed for testing, for example printers, bar scanners, network requirement, etc.

- **Test sequence**  

  Especially on process test, end-to-end test, and user acceptance test types. You need define and align how the different teams interact.

> [!TIP]
> Part of a successful test cycle is to set the expectations with the participants, so everyone keeps the focus on the objective. Consider the test cycle like a mini go live for the scope in place for the cycle.

## Track during testing

Detecting bugs and properly documenting them is key. It facilitates the resolution. But before reporting bugs, the tester needs to understand the scope and objective of what the test is. Building the solution is progressive. It's easy to report issues where the scope of the test doesn't include a solution for that and is part of future iterations. Keep the focus with the team testing.

Tracking captures the outcome and performance of the test cycle; it's how the development team and consultants understand the quality of the test cycle. We recommend that you use Azure DevOps for this tracking. Azure DevOps integrates into the entire application lifecycle management. All bugs are visible to the team that needs to fix it. You can also see what is or isn't working in general.

Let us explore some tactical components of the tracking of issues discovered during testing.

### Keep track of changes in configuration

It's likely some tests result in tuning configurations as you test. Adjustments to the solution in configurations can change the behavior of the app, and those changes can happen during tests. This brings flexibility into the resolution, but also raises the risk of the team not documenting those changes. Keep in mind that the data can be reset for the next test cycle. If you don't document and make sure those changes aren't reflected in your golden configurations, you lose the important opportunity of what you fixed during testing. In the end, you don't want to repeat the same research over and over, so document the configuration update.

> [!NOTE]
> Making configuration changes can invalidate previous test cases connected to those changes. Those changes need to be handled much like it's a production change to make sure those changes don't negatively impact tests that passed. Track and execute regression testing.

### Keep record of the progress

At every test cycle, you provide a scope. Depending on the type of test, you have some dependencies. The team must know when they should start testing each type of testing. A testing heatmap can help you to show the progress of testing by process, test cases, and its statuses. For example, in the scenario used to explain [the test types](testing-strategy-test-types.md), we used the analogy of testing a *prospect to cash* process.

A meaningful process test type makes sure the process being tested has continuity, from the order to the invoice and shipment and later to the collection. If you're testing a sequence of processes, you don't go ahead of the game and straight to the collections part. If you do, you lose the opportunity to properly test the larger process sequence.

### Keep record of the bugs

Every bug identified during testing should be documented. Concise documentation that follows an agreed given structure is key. Rich documentation including test case and test step reference, repro-steps, screenshots, videos, and more builds a solid foundation to efficient troubleshooting and bug fixing.

Have a centralized repository that is available to the entire project team. Use that repository to track bugs and issues that are found throughout the project and while performing tests. If you can't track bugs and issues through their resolution, you risk missing bugs and issues. Potentially, some issues aren't identified until after go live. Additionally, without the ability to track the bugs and issues there isn't an ability to track progression in the stabilization of the solution.

### Bugs versus gaps

One common issue during bug reporting is that we can mix up a bug with a required feature or gap. Stick to the test case, if you identify a gap, great! Just make sure the feedback is properly classified. We don't want to lose the opportunity to capture that great idea or finding, we just need to funnel it properly to the right tracking system.

## Deal with the outcomes

Finishing the test cycle requires reporting the results and maintaining the bugs discovered during the testing, but also funneling the feedback received. In the end, all these outcomes add onto the top of the next wave of processes or features to be introduced in future test cycles, as shown in the following illustration:  

:::image type="content" source="media/testing-strategy-cycle.png" alt-text="Illustrates that the scope of a test cycle results in both failed and passed tests.":::

Reporting the outcome measures the performance of the test cycle. It helps you identify areas of opportunity for the implementation team, because it triggers clear actions to improve the quality. As a result, the next test cycle provides better performance.

For the next test cycle, we start over, as even passing test cases during this cycle need to be retested in the next one.

> [!NOTE]
> Software will never be 100 percent bug free. Issues identified must be clearly documented and triaged. A crucial milestone to reach is a formal business sign off on the overall pass of the final test cycle. This is a required step prior to executing cutover preparation for go live as it creates accountability on the acceptance of the solution by business.

## Next steps

- [Checklist](testing-strategy-checklist.md)  
- [Case study](testing-strategy-case-study.md)  
