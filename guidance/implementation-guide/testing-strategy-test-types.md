---
title: Types of tests
description: Learn about the different types of tests that you can use for your Dynamics 365 implementation project and how to combine them in your testing strategy.
author: edupont04
ms.author: veneva
ms.topic: conceptual
ms.collection: 
ms.date: 01/23/2024
ms.custom: 
  - bap-template
  - ai-seo-date: 01/23/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Types of tests

Testing is a key part of implementing a Dynamics 365 solution successfully. You can use many types of tests, each with its own purpose, scope, and method. You should select the types of tests that are relevant for your project and plan them accordingly.

This article explains the following types of tests that most Dynamics 365 implementation projects use:

- [Unit tests](#unit-testing): Testing individual components or units of the solution
- [Functional tests](#functional-tests): Testing the configuration or customization of the solution
- [Process tests](#process-testing): Testing the business processes that the solution supports
- [End-to-end tests](#end-to-end-testing): Testing the entire solution as a whole
- [User acceptance tests](#user-acceptance-testing): Testing the solution from the user's perspective
- [Regression tests](#regression-testing): Testing the solution after changes or updates
- Nonfunctional tests, including [performance tests](#performance-testing): Testing how the solution performs, operates, and maintains
- [Mock cutover](#mock-cutover): Testing the deployment process in a production environment

Each type of test represents an incremental testing approach. Some are required for any implementation and others depend on the specific implementation circumstances, such as the complexity of the solution, performance, and security requirements. Some types of test are especially relevant for specific stages in the implementation, and others can run for the lifecycle of the solution.

## Unit testing

Unit testing is the first type of test that you do when you develop your solution. It focuses on testing individual components or units of the solution, such as forms, fields, and workflows. It's done by developers in a development environment.

The purpose of unit testing is to verify that each component meets its requirements, functions correctly, has a good design, and doesn't have any defects. It's a fast and iterative process that helps you improve the quality of your solution from the start. You should do unit testing during the implementation or during any bug fixing.

Unit testing is required if you're customizing or extending your solution. It's also recommended if you're configuring your solution. At this point, you should also check the performance and security of each component.

### Unit testing example

Let's say you're building a solution for a customer that ships goods and uses a specialized transportation system that's part of the solution. You need to test specific validations during a sales order confirmation and connect with the transportation system using Power Automate. You write and execute unit tests for each validation requirement and interface in this scenario.

## Functional tests

Functional tests are the next type of test that you do after you develop your solution. They can be either manual or automated. They're done by functional consultants, subject matter experts (SMEs), or testers in a test or development environment.

The purpose of functional tests is to verify that the configuration or customization of the solution matches the design specifications and meets the business requirements. It's the first type of test that involves consultants and customer SMEs. We recommend that consultants do the functional tests first, to make sure the solution is stable before the business users see it.

Functional tests should be mapped to the business processes and requirements. Test cases should be detailed and linked to the process flow. The data used for testing should be realistic and reflect the customer's data.

Functional testing starts during the **Implement** phase of the [Success by Design framework](success-by-design.md). This is also a good time to introduce test automation, which can help you save time and resources in future testing cycles.

### Functional testing example

Let's continue with the sales order scenario from the unit testing example. Now you need to test the configuration and setup of the interface with the transportation system. You test customer data, products, pricing, warehouse setup, payment processing, and other module-related configuration and parameters.

## Process testing

Process testing is the type of test that connects multiple functional tests into a business process flow. It can be manual or automated. It's done by consultants who prepare and guide the test cycle, but mainly by business users, SMEs, and testers in a test environment.

The purpose of process testing is to verify that the solution supports all the business scenarios and variations that are in scope for your project. It's an opportunity to go beyond testing individual functions or modules and test how they work together as a process. It also involves different roles and personas who hand over their outcomes from one test case to another.

Process testing requires role-based security to make sure each user can access and perform their tasks as expected in production. It also includes negative testing, which looks for unexpected outcomes or errors in the process.

Process testing starts during the **Implement** phase of Success by Design and continues through the **Prepare** phase. It's an iterative process that helps you build user acceptance and trust in the solution.

Process testing should be tracked and reported using a tool or system, such as Azure DevOps. This helps you monitor your testing progress and quality. It also helps you identify and prioritize the actions that you need to take to resolve any issues or defects.

### Process testing example

Let's build on the sales order scenario from the functional testing example. Now you want to test how the sales order works with other test cases that precede and follow the process. For example, you might test the following process: *prospect to cash*. This means you test how you generate leads, qualify prospects, create orders, ship goods, invoice customers, and collect payments. You involve other workstreams in the implementation team that handle different parts of the process. You also validate that you can generate reports and analytics for this process.

## End-to-end testing

End-to-end testing is the type of test that connects all the business processes that are in scope for your project. It can be manual or automated. It's done by consultants who prepare and guide the test cycle, but mainly by business users, SMEs, and testers in an integrated test environment.

The purpose of end-to-end testing is to verify that the entire solution works as a whole and integrates with other systems that are part of your business operation. It's the most comprehensive type of test that simulates a real-life operation.

End-to-end testing requires a full set of migrated data from legacy systems, which might have different data patterns than demo or test data. It also requires the latest solution version and updates.

End-to-end testing starts in the **Implement** phase of Success by Design and continues through the **Prepare** phase. It's an iterative process that helps you confirm readiness for go-live.

You should plan for multiple cycles of end-to-end testing. Planning only one cycle at the end of the solution build is risky, because it leaves less time to react to final fixes.

End-to-end testing should be tracked and reported using a tool or system, such as Azure DevOps.

### End-to-end testing example

Let's continue with the sales order scenario from the process testing example. Now you want to test how this process works with other processes that depend on it or affect it. For example, you might test how this process connects with accounting, inventory management, product development, customer service, marketing, and other business streams. You also test how this process integrates with other systems, such as your transportation system, your customer relationship management system, and your enterprise resource planning system. In this stage, you can combine different Dynamics 365 apps and see them work together.

## User acceptance testing

User acceptance testing (UAT) is the final type of test that you do before you deploy your solution to production. It's always a manual test, and it's done by business users in a dedicated and integrated test environment.

The purpose of UAT is to get sign-off and approval from the business stakeholders that the solution meets their needs and expectations. It's also an opportunity to manage organizational change and to get feedback from the users who will use the solution daily.

UAT requires customer data, including migrated data, and the latest solution version and updates. It's the closest test to running live operations.

UAT is done during the **Prepare** phase of Success by Design and it happens before the **Cutover** phase. It's a prerequisite to reach the go-live milestone. [Learn how to prepare for go-live](prepare-to-go-live.md).

The business users who do UAT should be trained on the solution and the new processes before they start testing. This helps them avoid errors due to lack of understanding or familiarity with the new system.

At the end of a successful UAT, the business users should be confident and comfortable with using the new solution for their daily tasks. They should also confirm that the solution supports their business operations and goals.

The final iteration of UAT requires the business to sign off and accept the solution before you move to deployment.

### UAT example

Let's continue with the sales order scenario from the end-to-end testing example. Now you need to get approval from the business stakeholders that the solution works for them. You invite a select group of people who run the operation, such as order processors, accountants, and shippers. They run a real-life operation simulation using customer data and scenarios. They test all the processes and variations that are in scope for their roles and tasks. They also provide feedback and suggestions for improvement.

## Regression testing

Regression testing is the type of test that you do after you make any changes or updates to your solution. It can be manual or automated. It's done by testers, developers, and users in a preproduction, test, or development environment.

The purpose of regression testing is to make sure that your solution still performs as expected after a change, and that the changes didn't introduce any issues or defects. It's a quality check that helps you keep your solution healthy and up-to-date.

Regression testing should be done whenever you have changes in code, configuration, or data that can affect different processes or functions in your solution. It should also be done before you introduce any change to your production environment.

Regression testing can be time-consuming and labor-intensive if you do it manually. You should consider automating this type of testing as soon as possible. It's an investment that pays off over time. [Learn more about regression testing tooling](testing-regression-tooling.md).

### Testing techniques for regression testing

You can use several different techniques for regression testing.

You can test almost 100% of the processes. This gives you comprehensive coverage, but it's expensive to run and maintain, especially without automation.

You can prioritize the test based on business impact. This gives you coverage of the processes that are mission critical for the operation. It's also a more affordable approach, but it doesn't guarantee a solution that's free of regression.

You can focus on the areas that are affected by the change. This is a targeted approach that requires less effort, but it can't confirm that other areas are free of regressions.

You can combine all the previous techniques, making sure you test critical business processes and target more testing on the features that are being changed.

Always keep in mind that bugs discovered late in the implementation process have a lifecycle to get fixed and retested. By testing early and often, you catch those bugs sooner and avoid costly rework or delays. If you find bugs late in the process, think twice about the value of fixing them versus the risk of not being able to do proper regression testing. The fix might be more costly or risky than waiting and doing a proper regression testing or delaying the deployment.

Every time you test successfully, you build trust and confidence in your solution. Every time you have a failed test or fail to test properly, you lose trust and confidence in your solution. This is especially true for regression testing, because it's the last line of defense before you deploy to production.

Again, automation is key for regression testing. Your solution is alive and ever evolving, so change is constant, not just from the application updates, but from your business needs as well. Automation brings the benefits of testing faster, having better testing coverage, and providing repeatability for your tests. It also helps you reduce the cost of testing and the risk of human error.

Start building your automated testing progressively, focusing first on key business processes then expanding over time. Do it as early as possible during the implementation process and always test after a change and before production deployment.

Finally, keep in mind that finding bugs during regression testing could be due to changes in the solution design, standard product updates, or bug fixes that redefine how the solution works. These changes might require recreating or updating your test cases.

### Regression testing example

Let's continue with the sales order scenario from the UAT example. Microsoft has released new functionality that enriches the order processing feature in Dynamics 365 finance and operations apps. When the new update becomes available, you need to do regression testing to make sure it doesn't break any of your existing processes or functions. You run an automated test for key business processes connected to the new feature to confirm the solution produces the expected outcomes.

## Performance testing

Performance testing is a type of nonfunctional test that measures how well your solution performs under different conditions and scenarios. It's done by developers, functional consultants, customer SMEs, and testers in a dedicated performance testing environment.

The purpose of performance testing is to ensure that your solution can handle the expected operational volumes, peaks, loads, and growth of your business. It also helps you identify and optimize any bottlenecks or issues that affect your solution performance.

Performance testing is required, especially if you have concerns over high-volume transactions, complex integration scenarios, or specific performance goals and expectations. It's one of the most dominant risk factors in implementation projects, because it's often overlooked or underestimated.

[Performance testing isn't only about infrastructure](performing-solution.md). It's also about data, code, configuration, and design. Microsoft, our partners, and our customers all play important roles in ensuring a performing solution. But we rely on the implementation teams to test and validate performance beyond infrastructure and at the right time of the implementation.

Performance testing should start as early as possible during the unit testing phase, so developers can influence proactive improvement of performance. It should continue throughout the implementation lifecycle, as new features or updates are added to the solution.

Performance testing needs to be planned and agreed on from the start of the implementation. It requires setting clear performance objectives and criteria, and preparing proper environment resources to run the tests.

Don't delay performance testing until the end of the implementation. This test can reveal important challenges that can require fundamental architectural changes or fixes. Doing it late in the implementation puts the entire solution at risk of wasting important resources or missing deadlines.

It's important to mention that the infrastructure required to execute this test type, especially when you need a higher-spec environment, doesn't need to be available during all the implementation. You can bring in a needed environment or repurpose ones for other test types during the lifetime of the project. It doesn't mean you shouldn't log performance issues observed during other test types at any time.

Remember, you're not just testing the standard product in this test type&mdash;you're testing the solution that you're implementing in combination with your business operation needs. Some basic implementations can justify not doing a full-blown performance test.

### Performance testing example

Let's continue with the sales order scenario from the regression testing example. Now you want to test how your solution performs under different conditions and scenarios. For example, you might test how your solution handles:

- A high volume of orders during peak seasons
- A large number of concurrent users accessing the system
- A complex integration with your transportation system
- A long-running batch process for invoicing
- A slow network connection or a power outage

## Mock cutover

Mock cutover is a special type of test that simulates the deployment process in a production environment. It's done by consultants who prepare and guide the test cycle, but mainly by business users, SMEs, and testers in a production environment.

The purpose of mock cutover is to validate aspects like connectivity, stability, access, integration, security, network, and devices. It also helps you confirm the estimated times and sequence of activities for your deployment plan and make adjustments if needed.

Mock cutover is done just before the **Cutover** phase of Success by Design. [Learn more about preparing for go-live](prepare-to-go-live.md).

We recommend that you always plan for a mock cutover test. It helps you avoid surprises and risks during the actual deployment.

### Mock cutover example

Let's continue with the sales order scenario from the performance testing example. Now you're ready to deploy your solution to production. You want to test your cutover plan in terms of sequence of activities, timing, and production environment stability. You run the cutover plan by rehearsing and documenting every step, so you can tune it as needed. After the mock cutover, you find that the time to load data and sequence it conflicts with other cutover tasks. You adjust that sequence and confirm the readiness to run the updated cutover plan.

## Other types of testing

We described the incremental approach for testing through the different types of tests, scale needs, and continuous validation of the solution. But other types of tests might be needed, based on the design of the solution, such as:

- **Smoke tests**: Confirming that basic functions work as expected, so that the component can continue to test further with other test types.
- **Data acceptance tests**: Confirming that the migrated data goes into the target environment correctly and is usable for actual operation.
- **Interface tests**: Confirming that your interfaces work as intended.
- **Environment testing**: Confirming that the new environment is fit for the purpose.
- **Reporting testing and business intelligence testing**: Confirming that reporting and business intelligence can be executed and operate properly with the expected outcome and performance.
- **Device testing**: Confirming that devices such as RFID readers, scales, and other warehouse devices are operational, connect, and perform as expected.
- **Network/infrastructure testing**: Confirming that the underlying network infrastructure, such as firewalls, Wi-Fi, and printers, are configured and working properly.

Some projects are too small to justify separate planning to run some of these types of tests. However, you should fold the concept and meaning of these tests into other types of testing.

## Next steps

- Learn how to [create and use a test plan](testing-strategy-planning.md) for your testing activities
- Learn how to [run your tests and handle the outcomes](testing-strategy-run-tests.md)
- Learn how to [test your solution after changes or updates](testing-regression-tooling.md)
- Review the Success by Design [checklist](testing-strategy-checklist.md) of the key steps and tasks for your testing process
- Read a [case study](testing-strategy-case-study.md) of how an organization implemented a testing strategy for its Dynamics 365 solution
