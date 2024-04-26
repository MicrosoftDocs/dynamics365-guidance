---
title: Create a test plan for your implementation projects
description: Learn how to design a test plan for your Dynamics 365 solution that covers the scope, types, cycles, and outcomes of testing.
ms.date: 01/23/2024
ms.topic: conceptual
author: edupont04
ms.author: veneva
ms.custom:
  - ai-seo-date: 01/23/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Create a test plan

Testing is a crucial part of any Dynamics 365 implementation project. It helps you verify that your solution meets the business requirements and works as expected. To conduct effective testing, you need a test plan that defines the scope, types, cycles, and outcomes of testing. This article explains how to create a test plan that suits your project needs and follows the best practices for testing.

You should start planning for testing in the **Initiate** phase of the project. You should also document your test plan and get approval from the business team before you execute it. Your test plan should align with your overall test strategy, which is based on your project scope and objectives.

In this article, you'll learn how to:

- Create a test plan that reflects the scope of testing
- Choose the right types of tests for each phase of the project
- Schedule the tests and test cycles
- Define the test cases and expected outcomes
- Align the test plan with the solution versions
- Assign ownership and accountability for the test outcomes
- Use the right environments for testing
- Document and report the test results
- Involve the right roles in testing

## Define the scope of testing

The scope of testing determines what you need to test, how deeply you need to test it, and how often you need to test it. The scope of testing depends on several factors, such as:

- The complexity and size of your solution
- The industry standards and regulations that apply to your solution
- The internal standards and policies of your organization
- The risk and impact of your solution on the business processes and operations
- The feedback and expectations of the business stakeholders and users

You should define the scope of testing based on the business processes and requirements that your solution covers. You should also consider the different areas of test scope, such as functionality, performance, security, usability, integration, and data migration.

The scope of testing should be proportional to the business risk and impact. For example, if you're implementing a low-complexity finance solution in the private sector, you might need less testing than if you're implementing a high-complexity manufacturing solution in the pharmaceutical industry. Test plans should be more thorough and have higher test coverage for processes that are critical or risky for your business.

The scope of testing should also be flexible and adaptable to changes in the project needs and the solution design. You might need to add, remove, or modify test cases, test cycles, or test types as you discover new requirements, issues, or opportunities during the project.

## Choose the right types of tests

The types of tests you need to run depend on the nature and purpose of your solution. Different types of tests can help you validate different aspects of your solution, such as functionality, performance, security, usability, integration, and data migration.

Some of the most common types of tests for Dynamics 365 solutions are:

- Unit testing: Testing individual components or units of code to verify that they work as intended.
- Integration testing: Testing how different components or units of code interact with each other and with external systems or services.
- System testing: Testing the entire system or solution as a whole to verify that it meets the functional and nonfunctional requirements.
- User acceptance testing: Testing the solution from the perspective of the users to verify that it meets their needs and expectations.
- Performance testing: Testing the speed, scalability, reliability, and resource consumption of the solution under different workloads and conditions.
- Security testing: Testing the security features and controls of the solution to verify that it protects the data and resources from unauthorized access or misuse.
- Usability testing: Testing the user interface and user experience of the solution to verify that it's easy to use, understand, and navigate.
- Data migration testing: Testing the process and outcome of moving data from the source system to the target system to verify that the data is accurate, complete, and consistent.

You might not need to run all these types of tests for your solution. You should select the types of tests that are relevant and appropriate for your project scope and objectives. You should also consider the cost, time, and resources required for each type of test.

[Learn about each type of test](testing-strategy-test-types.md).

## Schedule the tests and test cycles

When should you start testing your solution? The answer is simple: as early as possible. Testing should be an integral part of your project execution from the beginning to the end. Testing early and often can help you identify and fix issues before they become costly or risky.

You should schedule your tests and test cycles according to the phases of the project and the readiness of the solution. A test cycle is a comprehensive testing event that covers a specific scope and version of the solution. A test cycle can also be called a conference room pilot, a testing iteration, or a testing milestone. Each test cycle should represent a mini go-live, where you rehearse the business operation with the solution.

You should align your test cycles with your project phases and solution versions. For example, you might run unit testing and integration testing in the **Design** phase, system testing and performance testing in the **Build** phase, user acceptance testing and security testing in the **Deploy** phase, and data migration testing and usability testing in the **Operate** phase.

The following figure shows an example of how to schedule the most common types of tests across the different [Success by Design](success-by-design.md) implementation phases. You might need to adjust this schedule based on your project needs and solution complexity.

:::image type="content" source="media/testing-strategy-phases.png" alt-text="A Gantt chart or table showing the various tests running across implementation phases." lightbox="media/testing-strategy-phases.png":::

You should avoid testing too late in the project or too close to the go-live date. This can increase the risk of finding issues that are hard to fix in a short time or that affect the quality and performance of the solution. You should also avoid testing in the production environment, except for a mock cutover test before the go-live. The production environment is meant to run the real business operations, not the tests.

## Define the test cases and expected outcomes

A test case is a set of instructions that guides the tester to execute a test and verify the expected outcome. A test case should reflect the actual business execution in the system and represent how the user operates the solution.

A test case should include, at a minimum, the following elements:

- The process and requirements that the test case covers
- The prerequisite or entry criteria to execute the test, such as data or configuration dependencies
- The reproduction steps to perform the test
- The expected outcome or exit criteria to validate the test result

You should write clear and detailed test cases that help the tester confirm the outcome with certainty and repeatability. You should also design test cases for both positive and negative scenarios, that is, what should happen and what shouldn't happen.

You can use tools like [Azure DevOps](/azure/devops/?view=azure-devops&preserve-view=true) or [Task recorder](/dynamics365/fin-ops-core/dev-itpro/user-interface/task-recorder) to create and manage your test cases. These tools can help you track and connect your test cases to your solution development lifecycle and your project scope.

The following figure shows an example of a test case:

:::image type="content" source="media/testing-strategy-test-case.png" alt-text="Example of a test case, showing the process to test, requirements and prerequisites, steps, data, and expected versus actual results." lightbox="media/testing-strategy-test-case.png":::

## Align the test plan with the solution versions

The solution version is a combination of the code, configuration, master data, and migrated data that supports the test cases. The solution version should be controlled and consistent for each test cycle. For each new test cycle, the solution version should expand in scope and complexity.

You should plan your development efforts to prepare the solution version for each test cycle. You should also coordinate with the teams and parties involved in the solution's development, such as developers, consultants, customers, Microsoft Support, or partner providers. Missing one necessary component of the solution version can cause delays or issues in the testing.

You should also plan for testing environments where you can run your tests safely and effectively. You might need different environments for different types of tests, such as integration testing or performance testing. You might also need testing instances of partner systems or services that integrate with your solution. You should never use the production environment for regular testing, only for a mock cutover test before the go-live.

## Assign ownership and accountability for the test outcomes

The test outcomes are the results and feedback that you get from running your tests. The test outcomes can include bugs, issues, gaps, opportunities, or improvements. Based on the type and severity of the test outcome, you need to define who takes ownership of the fix and what actions are needed to resolve it.

- Bugs go back to developers for resolution.
- Configuration issues go to consultants for adjustment.
- Gaps go to project managers for discussion with stakeholders and the implementation team.
- Standard product issues go to Microsoft Support or any other solution provider involved.
- Conceptual design issues go to architects on the implementation team.
- Process improvements go to business subject matter experts (SMEs).

You should document and track the test outcomes and assign clear ownership and responsibility for the fixes. You should also define who is accountable for driving the resolution of the test outcomes based on the type of test. For example, unit testing outcomes are often owned by technical architects or dev leads, while user acceptance testing outcomes are often owned by customer steering groups or lead SMEs.

When you define your test plan, you should specify the ownership and accountability for each type of test outcome and test type.

## Use the right environments for testing

The environment where you run your tests is an important factor for the quality and performance of your solution. The environment should match the conditions and requirements of the type of test you're running. For example, you might need a sandbox environment for integration testing, a load testing environment for performance testing, or a staging environment for user acceptance testing.

You should plan and provision the environments you need for testing in advance. You should also ensure that the environments are isolated, secure, and consistent with the solution version. **You should never use the production environment for regular testing, only for a mock cutover test before the go-live.**

You might also need to test your solution in environments that aren't part of Dynamics 365, such as partner systems or services that integrate with your solution. You should plan for the availability and access of these testing environments and coordinate with the providers or owners of these systems or services.

You should also plan for the hardware and software resources that you need to emulate the real operation of your solution, such as scanners, printers, handhelds, and so on. These resource needs are dictated by the test cases and the expected user scenarios.

## Document and report the test results

Documenting and reporting the test results is essential for tracking and improving the quality and performance of your solution. The test results can help you highlight the wins, issues, patterns, and opportunities that emerge from your testing. They can also help you make decisions and take actions to correct or enhance your solution.

You should document and report the test results for each test case, test cycle, and test type. You should include information such as:

- The test scope and objectives
- The test date and duration
- The test environment and version
- The test participants and roles
- The test steps and outcomes
- The test issues and fixes
- The test feedback and recommendations

You can use tools like [Azure DevOps](/azure/devops/?view=azure-devops&preserve-view=true) or [Power BI](https://powerbi.microsoft.com/) to create and manage your test documentation and reports. These tools can help you build dashboards and visualizations that can show the progress and quality of your testing.

## Involve the right roles in testing

The roles involved in testing can vary depending on the type and scope of the test. The roles can include developers, consultants, customers, SMEs, quality assurance testers, users, or partner providers.

You should plan and allocate the resources and time required for each role to participate in testing. You should also ensure that the roles have the necessary skills, knowledge, and access to perform the tests. You should provide training and guidance to the roles as needed.

The involvement of the business team in testing is critical. They own the solution and they know the business processes and expectations better than anyone else. One common cause of failure is poor involvement or feedback from this group of testers.

## Summary

Creating a test plan for your Dynamics 365 solution is a key step to ensure its quality and performance. A test plan helps you define and design the scope, types, cycles, and outcomes of testing. A test plan also helps you coordinate and communicate with the different roles and parties involved in testing.

Testing is an iterative and incremental process that grows as you progress in the project. Testing is also a permanent activity that continues after you go live, based on the regression testing technique you choose.

Always test your solution from the perspective of the business processes. The processes are the language of the business and the testing is the proof that your solution can speak that language.

## Next steps

- Learn how to [run your tests and handle the outcomes](testing-strategy-run-tests.md)
- Learn how to [test your solution after changes or updates](testing-regression-tooling.md)
- Review the Success by Design [checklist](testing-strategy-checklist.md) of the key steps and tasks for your testing process
- Read a [case study](testing-strategy-case-study.md) of how an organization implemented a testing strategy for its Dynamics 365 solution
