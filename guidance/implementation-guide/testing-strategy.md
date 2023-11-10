---
title:  Testing strategy
description: Learn how the value of having a solid testing strategy in place early on for your implementation and how to build a testing strategy that works for you. We explain the importance of testing your solution before it goes live to discover any defects in the process as early as possible, allowing time to address them.
author: edupont04
ms.author: veneva
ms.date: 06/21/2023
ms.topic: conceptual

---

# Testing strategy in Dynamics 365 implementation projects

During implementation projects, a fundamental expectation is that the solution meets the business needs so that the organization can run their business successfully. A crucial process to meet this objective is to test the solution by performing multiple business execution rehearsals before the system goes into production and business operations are conducted in the system.

It's imperative that proper testing of the solution is completed before deployment to production. This helps avoid costly challenges that could delay the adoption, create negative perception of the final product quality, and reduce the confidence to run the business on the new solution.

The overall goal of testing is to ensure the business can operate safely and efficiently. Detection of defects is important in order to ready the solution, processes, and people to operate the business in production efficiently and accurately as soon as possible. Proper testing executed at the right time allows us to detect defects in a systematic way as early as possible in this process.

This article explores the following areas:

- The value of testing

- Types of testing

- Defining a test strategy

- Planning to test at the right time with clear scope

You can also find recommended practices for run the testing process, how to deal with the outcomes, and reaching the sign-off that confirms the readiness of the solution.

In the subsequent sections of this article, we explore the key components of a recommended test strategy.

Defining a comprehensive test strategy for your implementation is a combination of considering the project scope, testing planning with a test plan and test cycle schedule in combination with the phases and solution versions availability, and selecting all the relevant test types and how to execute them.

- Define scope of testing based on your functional and nonfunctional business requirements

- Select the required test types for your project

- Create a test plan with right-sized test cycles

- Execute on your test plan, document, and take action on outcomes

## Focus on quality and scope

Testing should be considered as a continuous activity within the application lifecycle management strategy. Not only is it critical during the implementation of the solution, but also during the Operation phase. It's a continuous cycle that supports fixes to bugs and extensions of features over time. In the beginning testing is completed manually, but over time with automation we can make the process far more efficient. Our objective is to ensure the quality of the solution continues to meet customer expectations.

## The approach for testing

Depending on the [methodology](implementation-strategy-choose-methodology.md) you apply, the testing frequency differs for each iteration. In all cases, you must look for a high-quality testing approach to confirm readiness.

As part of your implementation methodology, you need to have a clear strategy for testing. This strategy is composed of the following items:

- A clear testing scope defined by your business processes and requirements.

- A comprehensive plan that brings clarity to when, why, who, how much, and where to test.

- The different types of testing with clear objectives, source documents, and entry/exit criteria for each test type.

- A comprehensive tracking mechanism that allows you to monitor overall progress, pass/fail rates, ownership, and issues tied to specific test cases.

- A clearly defined process for adding or modifying test cases during each individual test pass.

Explore each component to define the testing strategy for your Dynamics 365 implementation.

## Defining the testing strategy

At Microsoft, we've observed thousands of Dynamics 365 implementations. Our learning shows that the more successful implementations have a thorough definition of the test strategy, the quality, and the depth of testing. They also have the right business stakeholder involvement throughout test execution.

In general, the approach of defining a good strategy doesn't change between implementations. What changes is the specific definition of the strategy framework that is applied to a specific implementation based on the particular business objectives, business constraints, and project scope and requirements. For example, the process to define the scope can be the same across projects, but the scope itself differs. Investing in a good strategy and making sure the implementation teams use it consistently increases the quality of the project outcome.

## Testing scope

The testing scope is defined early in the project after defining the solution, and it's refined as the solution blueprint takes shape. What changes throughout the project is the type of testing that comes into focus as you move through the implementation lifecycle and the ability to actually test the solution increases.

During the implementation, the number of test cases in the test scope keeps increasing as you progress in building the solution. After go-live, the scope focuses on maintaining the quality as you update the solution. However, testing can increase if you continue to expand.

Consider the testing journey as an incremental process, as illustrated in the following illustration.  

:::image type="content" source="media/testing-strategy-scope.png" alt-text="Illustrates the testing strategy that is defined by processes and test cases.":::

Regardless of the timeline, you need to keep two things in mind:

- A clear view of the end-to-end business processes.

- A clear definition of the depth and detail of the test case design, but also the variations of testing, for example edge cases and negative testing.

> [!NOTE]
> Make sure that every implementation you execute has a clear and solid testing strategy.

## Project scope mapped to testing scope

In order to strive towards a solid test strategy, it's crucial to map your project scope to your testing scope. It's essential to define how you test against each relevant project scope area. The following figure shows a sample of project scope areas with typical questions that can help you through this mapping exercise. For each area, you should have an idea how to test it.  

:::image type="content" source="media/testing-strategy-areas.png" alt-text="Shows project scope areas across functional requirements, test scope, and nonfunctional requirements.":::

### Functional requirements

|Area  |Questions  |
|---------|---------|
|Business processes  |What are the business processes in scope and how are they identified, prioritized and planned to be explicitly validated (including end-to-end) and not just as a set of fit/gap requirements?|
|Business requirements| What are the business requirements in scope and how are they identified, prioritized, and planned to be explicitly validated?   |
|Design requirements|How will you identify and prioritize the design requirements? How will you validate them across all the various design areas, such as functional, integrations, reporting, and so on?|
|Data| What are the data requirements for the project, defined as key data entities for performing project transactions? These requirements impact data migration, integrations, reporting and business intelligence, and so on. How will you validate these points?|
|Geography  |Are there specific geographical requirements (language, local market, regulations, and so on)?|
|High risk areas|What are the business requirement areas that need special attention (for example crucial business areas, customized areas, highly regulated areas, and so on)?|
|Security    |How are the key internal application security requirements and any external security requirements going to be validated?|
|Regulatory requirements|How have the specific regulatory requirements both internal (organizational policies, and so on) and external (such as financial, compliance, and so on) been identified for validation?|
|Overall project goals|How are the overall project goals or project success criteria mapped to specific requirements and how are they going to be validated?|

###  Nonfunctional requirements

|Area|Questions |
|--|--|
| Performance | How are key performance goals and expectations identified, prioritized, and planned to be explicitly validated? |
| Usability | How are the usability requirements defined, prioritized, and planned to be validated? |
| Operability | How are the requirements for the operability of the system(s) identified and validated? |
| Maintainability | Are the maintainability requirements defined? How will they be validated? |
| Disaster Recovery | How will the disaster recovery requirements/policies be validated? |
| Business Continuity | How will the business continuity requirements/policies be identified, prioritized, and validated? |

The table demonstrates that there's more to testing than simply validating if functional requirements have been satisfied. To progressively build your solution, you must determine the implementation processes and the requirements connected to each of them. Learn more at [Process-focused solution](process-focused-solution.md). As we build the solution and make it ready for validation, the scope of the testing increases as we add more test cases to reach optimum test coverage. During the project progression, we utilize different test types. From a simple unit test to end-to-end process tests used during user acceptance testing (UAT).  

> [!NOTE]
> Never forget the initial mapping of test scope to project scope, that ensures the right test coverage and business process focus.

Business involvement throughout solution validation provides the opportunity to build user acceptance gradually throughout the implementation and avoids identifying costly mistakes late in the process.

In the context of business applications, testing isn't an artifact of the development process; it's an artifact of the business process. Functional testing should always be in the context of business processes. The overall scope of testing should include processes that are contained in the new solution, and also those processes that are upstream and downstream from the solution.

> [!TIP]
> Connect the test to the process being validated. This facilitates tracking, reporting, and final sign off on readiness by the business team.

Get an overview of the different types of tests at [Test types](testing-strategy-test-types.md).  

## Solution acceptance and operation

Finally, the last test cycle takes the main objective of why you started implementing the solution to confirm the readiness to run the business using the new solution.

We described the importance of reporting the outcome of the test cycles for user acceptance test types, this report helps to determine the readiness to prepare for go live and is the foundation of the go or no-go decision by the stakeholders. The performance should be high at this point, and if not? Then the solution isn't ready.

This confirms the readiness of the solution but also the readiness of the production environment if you run a mock cutover test. It's important that for any final test the business team signs off and confirms they can operate the business with the new solution.

Accepting the solution doesn't mean it's 100 percent free of bugs. You need to assess the value to bring a fix, at this point if the issue is low risk for the operation, it's often better to go live with known nonblocking bugs and fix them later than to introduce risk by making an unnecessary rushed fix and not having time to retest properly.

From here, you move to the maintenance mode of the solution if you're implementing only one phase, or you continue adding new workloads or expanding the solution. Keep the discipline for testing and scale using the tools for automation. Testing is a continuous practice, the difference is the frequency, scope, and tools used to test.

## Conclusion

Testing is about quality, it's used to confirm the effectiveness of the path taken by the implementation team to solve the challenge of how to operate the business with the new solution, it confirms the initial vision by putting it into action. It's a required step in the process to implement Dynamics 365, regardless of how simple or complex your solution is, or if you're implementing standard functionality or extending or customizing it. If you run into a large number of quality related issues after you're live, it's often attributed to ineffective testing.

Testing during implementation is the step that builds the trust for the business to run their operation. Always test and do so as early as possible. It's never too early to start testing.

## Reference material

- Finance and operations apps

  - [Test Strategy TechTalk](https://community.dynamics.com/blogs/post/?postid=05707484-1079-48b0-982b-88fe9215eaf1)<!--(https://community.dynamics.com/365/b/techtalks/posts/test-strategy-for-finance-and-operations-implementations-october-21-2020)-->
  - [Performance benchmark](https://community.dynamics.com/blogs/post/?postid=fcc3526c-5f83-4645-8fa2-e01de47df387)<!--(https://community.dynamics.com/365/b/techtalks/posts/finance-and-operations-performance-benchmark-for-dynamics-365-1-30-19)-->
  <!-- [Performance patterns and antipatterns](https://community.dynamics.com/365/b/techtalks/posts/finance-and-operations-performance-key-patterns-and-anti-patterns-for-dynamics-365-1-15-19)-->
  - [Performance troubleshooting tools](https://community.dynamics.com/blogs/post/?postid=037d2f4a-1745-4cfb-93e9-530741294f39)<!--(https://community.dynamics.com/365/b/techtalks/posts/finance-and-operations-performance-troubleshooting-tools-for-dynamics-365-12-14-18)-->
<!--  - [Performance testing approach](https://community.dynamics.com/365/b/techtalks/posts/performance-testing-approach-april-30-2018)-->
<!--  - [Regression suite automation tool](/dynamics365/fin-ops-core/dev-itpro/perf-test/rsat/rsat-overview)-->

- Customer engagement apps

  - [FastTrack automated testing in a day workshop offering](https://www.microsoftevents.com/profile/web/index.cfm?PKwebID=0x1661342abcd)
  - [Automated and manual testing with Azure Test plan in Azure DevOps](https://www.youtube.com/watch?v=LF0hmSysWCg)
  - [Build end-to-end UI tests for your canvas app using Test Studio](/powerapps/maker/canvas-apps/test-studio)
  <!--- [EasyRepro – Getting started](https://community.dynamics.com/blogs/post/?postid=95889af6-b561-42f5-b2bd-ade35180e545)
  - [EasyRepro in 60 Seconds](http://xrmenterprise.com/2020/03/easyrepro-in-60-seconds/)-->

## Next steps

- [Overview of the different types of tests](testing-strategy-test-types.md)  
- [Plan the tests](testing-strategy-planning.md)  
