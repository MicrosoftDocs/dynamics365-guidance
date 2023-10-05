---
title: Plan the tests
description: Learn how to build a test plan that accounts for scope, the right types of tests, and the most important business processes in a Dynamics 365 solution.
ms.date: 05/17/2023
ms.topic: conceptual
author: edupont04
ms.author: veneva
---

# Plan the tests in a Dynamics 365 implementation project

Planning for testing is a fundamental part of the testing strategy. This article describes the minimal components you need to define a recommended testing plan. This strategy can be used to implement almost any business application.  

In this article, we build provide guidance on how to build a test plan that reflects the scope of the testing that you already defined. In the related articles, you learn how to build a common understanding in the project team about different [test types](testing-strategy-test-types.md). Before you can build a test plan, you must work with the business to understand their view about which business processes and areas of test scope are risky or critical to them.

With this valuable information, we can determine how to build a test plan that accounts for these aspects accordingly.

During the planning stage of the testing, you must answer and provide clarity for the following questions. They help you define and design the frequency of the testing based on the necessary iterations or test cycles to secure a high-quality solution.

- When do you need to start testing?

- How do you control the versions of the solution to be tested based on the progressive readiness of it?

- How do you document the outcome of the testing?

- Who participates in the testing?

- Where does the testing happen in terms of environments and type?

- How is the ownership of the outcome defined?

- How deeply will you test?

- What types of testing should you run, based on the project needs and solution complexity?

Answers to these questions help you plan the quality control portions of the solution. Build the plan at the start of the **Initiate** phase of the project.

The plan for testing must be documented and signed off on by the business team prior to its execution. It's important because it leads into other types of planning, such as the environments the solution requires, which  determines where the test is done.

## Create a test plan of the right size

The test plan is the blueprint for executing your tests. It establishes the guard rails to stay on track in terms of quality assurance for the solution, schedule of testing, and resources needed, and it contains the scope of the testing.

Depending on the complexity of the project, the implementation team can develop this artifact. In larger, more complex organizations, it's prepared with an independent quality assurance team to make sure that biases that the implementation team might hold don't detract from the veracity of the testing.

> [!NOTE]
> The testing effort and attention of testing should be proportional to business risk and business impact.

Always create a test plan for your project regardless of if your implementation is simple, complex, or if you're implementing a standard solution or extending the solution.

The duration of the respective test phases and iterations should be sized right. Not only solution complexity must be taken into account. Other important factors play a role here, such as industry standards, company internal standards and policies, regulatory standards for compliance and other legal aspects. For example, you're implementing a low complexity finance scope in the private sector. In this example, the testing phases have a different duration compared to an implementation of a high complexity manufacturing scope in the pharmaceutical industry. Test plans should be more intense and have higher test coverage for processes with critical importance to your business.

The test plan brings transparency and helps keep your goals and objectives on securing a quality solution. It contains important information that guides the team on how to conduct the testing. Formal test planning also serves to ensure that the team has an accurate view of the time and resources that are required to conduct testing.

The following figure provides an overview about high level test plan components.

:::image type="content" source="media/testing-strategy-components.png" alt-text="Shows tiles for schedule, test cycles, versions, roles, ownership, resources, and documentation.":::

> [!NOTE]
> Always create a test plan at implementation and obtain sign off by business stakeholders.

## Plan the right tests at the right test phases

The test phases in your test plan are closely coupled with the test types appropriate for your implementation project. Following good practice to derive your test scope from project scope, ensures your overall test strategy is consistent.

Test plans are living documents that keep evolving since project needs can change in terms of adding new test cycles or test types. For example,  business needs might change, or there's a need to increase the quality due to factors that were unknown at the start of the project. For the most important test types, such as user acceptance testing or performance testing, you must create specific test plans. Alternatively, keep enhancing your master test plan while always bringing enough details to provide clarity for each of them.  

Learn more at [Test types](testing-strategy-test-types.md).

## Schedule the tests

When should you test the solution? It's simple: Testing should start as early as possible. Your entire test strategy must be defined early on in your implementation project if you want to set up the project for success. Testing is an essential component of your overall project execution. Your testing cycles are incremental in terms of scope.

The following figure shows when we recommend you run the most common test types across the different [Success by Design](success-by-design.md) implementation phases. As mentioned earlier, there are factors that influence the relevance of a specific test type to your specific project phases and scope.

:::image type="content" source="media/testing-strategy-phases.png" alt-text="Shows the various tests running across implementation phases." lightbox="media/testing-strategy-phases.png":::

Don't wait too long to start testing-don't postpone the tests  until you think you have built the entire solution at the end of the implementation project. For example, it's a common pitfall to start certain test phases too close to [user acceptance testing](testing-strategy-test-types.md#user-acceptance-testing) (UAT). That might lead to late identification of a high number of bugs that can significantly undermine the business's confidence in the solution. If you test late in the project, you add risks to your implementation that you find  issues and gaps that are hard to fix in a short period of time. This becomes a constraint, especially when you have reduced time available for time sensitive projects tasks like preparing to go live. Always plan to avoid testing close to your go live date since it leaves no time to resolve issues. Poor planning or no testing can ruin a project.

## Test in cycles or iterations

Test cycles act as comprehensive testing milestones. The successful outcome of the test cycle confirms the readiness of the solution to meet the requirements of the business. There are different terms used to describe this testing event. For example *conference room pilots*, *testing iterations*, *testing cycle*, and so on. The important message here is that the testing event is comprehensive.

To implement Dynamics 365, we recommended that the scope in each testing cycle is aligned to your overall test strategy. The strategy should be based on a mapping to your project scope areas, such as business processes and requirements. Test cycles by application module, or organizational department in isolation, risk losing the big picture and thereby limit the effectiveness of the test.

**Every testing cycle represents a key milestone in building the solution**. Consider every test cycle to be a mini go live, where you're rehearsing the business operation at every test.

## Define test cases

An important part of the scope is defining the test. Proper test documentation is key, and test cases (or test scripts) are the primary artifact that achieves it. The nature of a test case varies depending on the test type. Clear and detailed test cases guide the tester to validate the expected outcomes with certainty and repeatability. They do align to the scope of the solution.

Writing a good test case requires a series of tools and tasks that help you validate the outcome. Dynamics 365 provides some of the tools to build test cases faster. For example, with the [task recorder](/dynamics365/fin-ops-core/dev-itpro/user-interface/task-recorder) in finance and operations apps, you can dynamically capture the steps for a task in the app.

Test cases should reflect the actual business execution in the system and represent how the end user ultimately operates the system, as illustrated in this figure:

:::image type="content" source="media/testing-strategy-test-cases-components.png" alt-text="Shows that What plus Get ready plus How plus Quality check form the test case.":::

Test cases should be composed of, at minimum, the following:

- The process and requirements that the test case is covering.

- The prerequisite, or entry, criteria to execute the test, which can be dependent on other tests or necessary data to produce the expected outcome.

- The reproduction steps.

- The expected outcome, or exit criteria, that helps confirm the readiness.

Finally, when you design your test cases, design for what you expect to happen based on the process objective but also on what it shouldn't do. Plan for tests that can break the process. This figure depicts a sample test case:

:::image type="content" source="media/testing-strategy-test-case.png" alt-text="Example of test case.":::

### Use Azure DevOps

[Azure DevOps](/azure/devops/?view=azure-devops&preserve-view=true) is great tool for documenting test cases and connecting them to the solution development lifecycle. When you define [test cases in Azure DevOps](/azure/devops/test/overview?view=azure-devops&preserve-view=true), you can track any bugs that are caught with specific test cases. You can both monitor the state of the solution as it rolls up to processes and process areas, and plan subsequent testing activities based on remediation of those bugs.

## Align to solution versions

We discussed the importance of planning the testing cycles process as part of the scope, this scope also triggers the readiness of the code and data that supports the test cases connected to those processes. After determining the planned scope of the test cycle, you should plan your development efforts to cover those processes and the readiness of the required data in terms of master data and configurations.

Your solution version needs to be controlled at every test cycle so you can have a clearly defined milestone. For every new milestone, the solution keeps expanding in scope and complexity.

The solution version is a combination of the version of the following components:

- Code

- Configuration

- Master data

- Migrated data

Different teams need to coordinate and plan how to combine their efforts to prepare for the testing cycle.

Each component of the solution version is important, and all of them need to come together as part of the solution. It's especially important with data. The earlier you bring migrated data into the mix the better. One of the most common causes of errors during the first days of operation is poorly migrated data.

Align your solution version to the testing cycles and coordinate the readiness of all the dependent parties to provide their own artifacts. Missing one necessary artifact can cause delays in the implementation, introducing risk.

## Define ownership

Having clear expectations of who takes ownership of the testing outcome is key. Testing can result in bugs, but also it can result in discovering configuration issues, gaps, or new opportunities where improvements can be applied in future cycles or solution releases. Based on the type of outcome, we need to define who takes ownership of the fix and what test plan is needed to account for that.

- Bugs go back to developers for resolution.

- Configuration issues go to the consultant connected to the test case.

- Gaps go to the project manager for further discussion with the stakeholders and implementation team.

- Standard product issues go to Microsoft Support or any other third-party solution provider connected to the issue.

- Conceptual design issues go to the architects on the implementation team.

- Process improvements go to the business Subject Matter Experts (SMEs).

Documenting the outcome of the test cycle and assigning clear ownership for the fix facilitates tracking and resolution. Plan for testing thoroughly, even if you're implementing the standard product.

The right role has to take accountability for the outcomes of a given test type so that the right actions are generated and completed.

One common pattern for implementations of standard functionality is the project team challenging the need to thoroughly test when the application hasn't been modified. The reality is that implementation teams are testing the specific business solution being implemented, not the standard software.  

> [!NOTE]
> You are not just testing software, you are testing the people being trained, the processes that represent the operation, the data that keeps the business alive, and finally the technology.

## Assign owners to test types and outcome

Now we need to connect this ownership role to the test types. In other words, we must define who takes accountability to drive the resolution of the outcome derived from testing based on the test type. It's important we have clear ownership to avoid defects bouncing around with unclear roles driving the actions, even though the fix can come from different roles. As an example, unit testing outcomes are often owned by technical architects or dev leads. User acceptance testing outcomes tend to be owned by customer steering groups devolved to the lead SME or PM.

When you define your test plan, define ownership for the type of fixes but also who is accountable to drive the necessary actions based on the outcomes for that test type.

## Use the right environment for the right type of test

Where to test is dependent on the type of test being executed and this definition impacts the [environment planning](environment-strategy-overview.md). Our focus here is on the environments where you can do proper testing based on the test type.

This environment can be a different variation of a development or test environment, but it's important that you never complete or plan for regular testing in production environments.

Production environments are meant to run the real business operations. Doing tests, or making changes to it without being tested first, is a high risk for the stability of the solution because of the unknown variables it can bring. **The only test type that can be executed in a production environment is a mock cutover test**, and this test happens for a limited period before the solution is live.

You can require testing be done in an environment different than Dynamics 365 environments, such as integrations. Plan for the availability of testing instances of third-party systems that integrate with Dynamics 365; integrations or other dependencies must be validated. This is a commonly missed opportunity during implementation.

Plan for extra hardware required to emulate the real operation like scanners, printers, handhelds, and so on. These resource needs are dictated by the test case.

Plan for non-Dynamics 365 testing environments where you have a dependency in the solution that requires validation.

Planning to document the results of your testing cycles helps to highlight the wins, but also the bugs and patterns. This report determines the next course of action and can impact future milestones. It allows stakeholders to make decisions to correct the direction if necessary.

Use Azure DevOps to build dashboards that can help to report progress and quality of the testing.

## Document the tests

Documenting testing has two primary aspects, the test cases and tracking the outcome of the test.

Having a model to document the outcome of a test case and test cycle allows the implementation team to validate the performance of the test cycle. Preparing to document and report the outcome highlights other challenges as well, though not necessarily ones connected to the test cases itself. These issues can be solution performance, connectivity issues, usability, continuity of the transaction, gaps in the product, and so on

Other important benefits of documenting the outcome are that it tracks the progress of the testing and keeps the big picture in sight. It allows us to detect and build the backlog for new non-high-priority opportunities that are discovered during the testing. It can also trigger a change of the statement of work when the newly discovered requirements are critical.

## The different roles involved in testing

The type of testing being done determines the people involved. For example, performance testing types require more technical roles and consultants familiar with that type of testing. User acceptance testing types require business users.

Testers can be developers, functional consultants, customer subject matter experts, quality assurance testers, or end users.

It's important to plan for the resources required for building your solution and for the different types of tests that require special skills. Consider the volume of test cases involved and the business areas impacted so you have good representation of the business.

Roles for testing are determined by who to involve in tests depending on the following variables:

- Test preparation (system, data, test cases, training, and so on)

- Test execution

- Test administrator or manager

- Test results triage

- Test reporting

- Test defect fixes

The business team involvement during testing is critical, they own the solution and plan for enough time to allow for proper testing by the key business users. One common pattern of failure is poor involvement from this group of testers.

## The bottom line on defining a test strategy

Defining a test strategy for your implementation is a combination of considering the project scope, testing planning with a test plan and test cycle schedule in combination with the phases and solution versions availability, and selecting all the test types and how you execute them.

Testing is iterative and incremental; it grows as you progress in the implementation and it's a permanent activity once you're live based on the regression testing technique you select.

Always test under the umbrella of the processes. In the end, the processes are the language of the business and the testing is proof that the solution "can speak" that language.

## Next steps

- [Test types](testing-strategy-test-types.md)  
- [Run the implementation tests](testing-strategy-run-tests.md)  
