---
title:  Overview of types of tests
description: Learn how you can combine the different types of tests in your  test strategy for a Dynamics 365 implementation project.
author: edupont04
ms.author: veneva
ms.topic: conceptual
ms.collection: 
ms.date: 09/08/2023
ms.custom: bap-template #Required; don't change.
---

# Overview of types of tests for a Dynamics 365 implementation project

In this article, we go through various types of tests  that can help you  implement Dynamics 365 in alignment with the Success by Design framework.

The following list shows key test types that most Dynamics implementation projects use:

- [Unit tests](#unit-testing)

- [Functional tests](#functional-tests)

- [Process tests](#process-testing)

- [End-to-end tests](#end-to-end-testing)

- [User acceptance tests](#user-acceptance-testing)

- [Regression tests](#regression-testing)

- Nonfunctional tests, including [performance tests](#performance-testing)

- [Mock cutover](#mock-cutover)

Each test type represents an incremental testing approach. Some are required for any implementation and others depend on the specific implementation circumstances including the complexity of the solution, performance, and security requirements. Some test types are especially relevant for specific stages in the implementation and others can run for the lifecycle of the solution. There are certain test cases that heavily rely on a high-quality data set and are migrated data early in the project lifecycle.

> [!TIP]
> Test types need to be planned with consideration to the complexity of the solution. Non-functional requirements like performance, and security, and should be executed during specific times throughout the implementation lifecycle.

## Unit testing

This test type focuses on individual function, code, and configuration testing. It's done by developers and is the lowest level component of the testing. In this test type, the developer verifies the requirements, validates the function, improves the code design, and finds and fixes defects.

This testing happens in a development environment. You're expected torun unit tests during the implementation, or during any bug fixing. It's a fast, iterative process. This test type can be used with configurations, but is required if you're customizing or extending your solution and is one of the first opportunities to introduce a quality check in the solution. At this point, you should validate the performance behavior of the individual components in addition to keeping security in scope. Being diligent from the start with this test type can save you time during implementation by avoiding rework or bug fixes for issues that should be detected during this test.

### See unit tests in action

Let us assume we're building a solution for a customer that ships goods and uses a specialized transportation system that is part of the final solution. For this example, we use unit testing to test specific validations during a sales order confirmation and interface with the transportation system using Power Automate. The unit tests are written and executed for each validation requirement and interface in this scenario.

## Functional tests

Functional tests can be either a manual test or an automated one. They're done by the functional consultants, subject matter experts (SMEs), or testers. The purpose of functional tests is to verify the configurations of the solution or any custom code. The primary objective is to validate the design according to the requirements. It's done in a test or developer environment during the **Implement** phase of the Success by Design framework. At this point, testing automation can also be introduced.

This test type is the first test to be done by consultants and customer SMEs. We recommend that consultants run the functional tests first. This way, the functionality is more stable before the business users get to see it. These SMEs often have less familiarity with the new system.  

At this point, the consultants must map the test to the requirements and processes. Test cases are detailed. The link with process is agreed upon with the business so the test case isn't focused only on the gap, but also to fit in the whole picture of the solution.

The data used to test beyond this point needs to keep evolving continuously using customer data and should reflect the reality of the operation.

### See functional tests in action

Let's again pick up the example with validaiton of the sales order. Now, the functional testing of the interface with the transportation system validates the configuration and setup. You'll test customer data, products, pricing, warehouse setup, the dependencies with payment processing, and other module-related configuration and parameters.  

## Process testing

The solution continues to be built, with unit testing being done by developers and functional testing by consultant and customer SMEs. The work from the development team is validated, and bugs and corrections are completed while the test is mapped to the process.

This is the point at which running connected test cases is ideal. The point where we raise the bar in our testing approach by connecting a collection of test cases that are all connected to our process.

Process tests can be manual or automated. The business has visibility and is actively participating in this testing. It's our first opportunity to go beyond testing that focuses on just functionality or modules. This stage gives different people the opportunity to start playing an important role in the test by handing over the outcome from one test case to another. This should be your first comprehensive testing cycle, and starts during the **Implement** phase of Success by Design.

The objective is to verify that the solution allows us to operate business scenarios, and the testing needs to be done in a test environment.

Tracking the outcome becomes more critical at this point, so bugs and other design change requests must be tracked. During this time, tracking tools like Azure DevOps become crucial as part of your application lifecycle management.

For this test type, role security becomes crucial. We want to make sure we have the right segregation of duties and that the different personas can operate as they should when they're running the solution in production.

This testing should look for unexpected outcomes of the process, commonly known as negative testing, and not just the happy path.

The performance of the solution becomes more evident with this test type because more testers are involved. Now, you're also touching more areas of the solution, so there's a risk that the solution gets stressed by parallel functions. Observe the nonfunctional requirements, such as whether batch processing jobs are properly configured.

### See process tests in action

At this point, we know how our sales order function works. Now we want to test how the sales order works with test cases preceding and following the process. Let us call this process *prospect to cash*. We want to test the collection of money after the shipment of goods. We involve other workstreams in the implementation team that handles that part of the process. We also validate that we can generate the invoice and collect money while closing the cycle. From the business point of view, the organization will confirm they can sell, ship, invoice, and collect the money, so the process works.

## End-to-end testing

After validating all the individual processes, it's time to connect all of them and increase their complexity with new process variations. It's the first test cycle that looks like a complete operation.

You can run the end-to-end tests manually. However, automation helps you prepare for future iterations, regression testing, and system maintenance. Remember that there are continuous solution updates even after go-live.

The test is done by the functional consultants who prepared the cycle and guide the team. However, the overall cycle is mainly done by business users, SMEs, and testers.

The main objective of this test type is validation of all business processes in scope. Run the tests in an integrated test environment, since now the solution now connects to other systems. It's an iterative process, and a prerequisite to being able to run your user acceptance test (UAT).

This test type starts in the **Implement** phase. It continues through the **Prepare** phase of the Success by Design framework.

It's important to plan for multiple cycles of end-to-end testing. Planning only one at the end of the build of the solution isn't recommended since it adds risks to confirming readiness by having less time to react to final fixes.

Another important aspect is that you run this test with a full set of migrated data from legacy systems. Migrated data is likely to present data patterns that haven't been accounted for in demo or test data.

This test is key to validating that the entire solution works with other systems that are part of the business. It also tests the role-based access control in a real end-to-end test.

> [!NOTE]
> Plan for this test by making sure to have a full set of migrated data available for this test.

### See end-to-end tests in action

On previous test cycles, we were able to collect the cash from our sale. Now we want to connect other processes that depend on this one. Examples include the following list:

- The accounting process to report taxes  
- The process for updating and interacting with other systems, such as the transportation system  
- The process for optimizing inventory and introducing new products  

In this stage, we can combine different Dynamics 365 apps and see them work together.

## User acceptance testing

We're now getting ready for prime time. Our solution works in its entirety, it performs, and it's ready for final validation by the actual people that execute the business, our end users. User acceptance tests (UAT) are the final opportunity for the business to assess and determine readiness for go live.

This test is manually executed, never automated. It's executed with customer data, including migrated data, and with the latest solution version. This test is the closest to being like running live operations, it's an actual business operation simulation.

The objective is obtaining business sign-off of the solution, collecting end user feedback, helping to manage organizational change, and it's done in a dedicated and integrated test environment.

UAT is done during the Prepare phase of the Success by Design framework and it happens prior to preparing for go live, which is a prerequisite to reach this milestone. Learn more at [Prepare for go-live](prepare-to-go-live.md).  

This test type must be run by users from the business. The implementation team is just a facilitator. The business team is the main owner of this test, failing to fully participate or test thoroughly is a risk.

The business users must be trained prior to UAT, not just on the solution but also on how the pending process works once the solution is deployed to production. Failure to train the users involved in UAT may generate errors due to a lack of understanding of how familiar tasks work in the new system.

At the end of the successful test, the business user connects the new solution to the reality of their daily tasks. They confirm the readiness of the solution, but also their own readiness at being familiar with the new system after being trained. If successful, the new solution fulfills the business operation need.

> [!NOTE]
> The final iteration of this test type requires the business sign off on acceptance.

We describe the importance of this step in later sections in this article.<!--TODO: add links-->

This is one of the most important milestones in terms of testing types. This test happens at the end of the implementation and prior to the go live. It's the entry criteria to prepare for operations. UAT is an end-to-end testing approach where all the processes in scope are tested and it requires sign off on the acceptance by the business stakeholders.

### Add automation

User acceptance testing (UAT) can be a great opportunity to start automating tests. By recording the tests, you get repeatability on the tests. Automation sets the path for regression testing and optimization of the investments to build that automation.

UAT is the last comprehensive test before going live. Every test case reflects actual tasks that business users will use the solution for. That makes UAT a good first step toward automation.

### See UAT in action

The business team now brings in a select group of people who run the operation. This group consists of order processors, the accounting team, the accounts receivable team, shippers, and others. The selected group of people run a real-life operation simulation. All the processes are executed in parallel and in-sync between teams. The team tests all the variations of the processes in scope.

> [!NOTE]
> You are required to plan for the UAT milestone and to have business stakeholders sign off on the acceptance of the complete, satisfactory results of this test prior to final preparations to operate (go live).

## Regression testing

Now we need to look at how to scale our future testing cycles, but also to make sure prior positive test results continue as you keep evolving the solution.

Regression testing repeats previously run tests. This way, you catch changes or updates to the solution, and the tests help you keep it healthy. Remember that the solution is dynamic, new capabilities are added, or new processes are required. Running regression tests manually can work, but it can be time and labor intensive. Therefore, it's also important that you consider the need to prepare to automate this type of testing as soon as possible. It's an investment that pays off with time.

The objective is to ensure the solution still performs as expected after a change and that it does so in a preproduction environment, test environment, or development environment.

A regression test should be conducted whenever you have changes in the code, or any configuration or new solution pattern that can impact different processes. This test type is done by testers, developers, and end users.

It's important to perform this test type before change is introduced to the production environment.

As we realize that this necessary quality gate is needed, there are tools available to help you to automate. Learn more at [What are the options for regression testing?](testing-regression-tooling.md).

### Testing techniques

There are different techniques you can follow to run your regression test.

You can opt to test almost 100 percent of the processes. That provides you comprehensive coverage. However, it's expensive to run and maintain, especially without automation.

You can prioritize the test based on business impact. This technique gives you coverage of the processes that are mission critical for the operation. It's also a more affordable approach. The only risk is that you can't guarantee a solution 100 percent free of regression.

Another technique is to focus on the areas that you expect to be impacted based on the change. This technique is targeted where the change is happening and requires less effort, but it has the limitation of not being able to confirm that you're free of regressions and the impact can't be visible on the direct change itself, but instead downstream on other processes.

You can also combine all the previous techniques, making sure you test critical business processes, and you can target more testing on the features being changed.

Always keep in mind that bugs discovered late in the implementation process have a lifecycle to get fixed but also require testing. By testing, you catch those bugs early. If the bugs are detected late in the process, think twice on the value of the fix versus the risk it introduces with not being able to do proper regression testing. The fix can be more costly at that point, being so close to go live, than waiting and doing a proper regression testing or delaying the go live.

Every time you test successfully, you put money in a trust. Every time you have a failed test or fail to properly test, you deduct money from that trust leaving a debt in the solution completeness. At the end, you need to reach the end goal with the trust full of money.

Again, automation is key, and you should plan for testing automation. Your solution is alive and ever evolving so change is a constant, not just coming from the application, but from the customer business needs.

Start building your automated testing progressively, focusing first on key business processes then expanding further over time. Do it as early as possible during the implementation process and always test it after a change and prior to production deployment.

Regression is important but it can be costly, especially if you don't automate in the long term. Automation brings the benefit of testing faster, having better testing coverage, and providing repeatability of the test. Automation takes as much planning as was needed for the manual testing planning, but it's a long-term investment that pays itself off with time.

Finally, keep in mind that finding bugs during regression testing could be due the change of the solution design, a standard product update, or just the resolution of previous bugs redefining how the solution works, which can require recreating the test case.

### See regression tests in action

Microsoft has released new functionality that enriches the order processing feature in Dynamics 365 finance and operations apps. When the new update becomes available, teams can execute regression testing to key business processes connected to this new feature. Testing the order and warehouse processes following a new configuration change is done because it can impact the picking process. Once the update is done in the test environment, the team runs an automated test to confirm the solution produces the expected outcomes.

## Performance testing

Every implementation project comes with a set of nonfunctional requirements that include data, security, usability, operability, maintainability, disaster recovery, throughput, response time, and business continuity. Usability is one nonfunctional requirement that is becoming increasingly important in the world. The demographics change, and the expectations of people using your solution is ever increasing. However, performance is the most dominant requirement understated and not properly addressed as a test type in implementations projects.

It's key to take into consideration that successful testing isn't complete until we not only make sure we can run the business on top of the solution, but also that we can do it at scale. We're implementing Dynamics 365 both for today and for the future, and we need a solution that lasts and performs.

Performance testing is required, especially if there's concern over operational volumes, peaks in transactional load, variety of high-volume integration scenarios, and so on. In this section, we focus on some of the considerations you should keep in mind for performance tests. But learn more at [A performing solution, beyond infrastructure](performing-solution.md).  

We put special emphasis on this test type since there are many misconceptions defining whether this test needs to be executed. Our experience has shown that performance is one of the most dominant risk aspects in implementation projects, since teams often miss this test when it's needed.

In the end, a performing solution is a combination of data, code, configuration, and infrastructure. Microsoft, our partners, and our customers play important roles for this test type. But we look to the implementation teams to play their important role on validating performance beyond infrastructure and at the right time of the implementation, so plan for it.

Key people in this test are developers, functional consultants, customer SMEs, and testers.

The objective of this test is to ensure the solution performs while focusing on critical processes that require scaling with load and growth. Not all the processes are involved in this test.

This test is completed in a dedicated performance testing environment. The basic version of performance testing starts during unit testing so developers can influence proactive improvement of performance. Regular dedicated test environments can also be used depending on the load to be tested.

Performance testing happens as soon as the critical processes are available to be tested throughout the implementation.

Performance testing needs to be visible at the start of the implementation and be part of the test plan. It requires agreement on the performance test objectives, and it can require proper environment planning to provide the necessary resources.

Don't delay performance testing till the end of the implementation. This test can bring to surface important challenges that can require fundamental architectural fixes, so doing it late in the implementation puts the entire solution at risk of wasting important resources.

It's important to mention that the infrastructure required to execute this test type, especially when the plan requires a higher spec environment, doesn't need to be available during all the implementation. You bring them a needed environment or repurpose ones for other test types during the lifetime of the project. It doesn't mean you shouldn't log performance bugs observed during other test types at any time.

Remember, you aren't just testing the standard product in this test type; you're testing the solution that you're implementing in combination with your business operation needs. Some basic implementations can justify not executing a full-blown performance test. Learn more at [A performing solution, beyond infrastructure](performing-solution.md).  

### See performance tests in action

In the previous example, we involved invoicing and the integration with the transportation system. Now, we'll test if we can process the operational peaks caused by the seasonality of the business. The posting of invoices is a crucial process that gives you almost real-time interaction with the transportation system according to the business needs. So we test a day in the life with relative volumes across key business processes, not just *prospect to cash*.

## Mock cutover

This is a special test that's run in a special environment, the production environment.

It's a temporary use of the production environment to do testing activities, and it runs just before the **Cutover** phase. Learn more at [Prepare for go-live](prepare-to-go-live.md).  

This test brings important value because it helps to validate aspects like connectivity, stability of the access by users and data, integration end points configuration, device connectivity, security, network, and many of the test cases in your processes may be environment dependent.

During this test, you're able to validate confirmation of the estimated times between environment preparation for production for all the planned tasks during go live. It's a confirmation that all the planned activities run smoothly once you do the actual final execution.

We recommend you always plan for a mock cutover test type.

### See mock cutovers in action

Let's continue from the earlier examples in this article. The team has tested the entire solution, and they're ready to move forward. The team wants to confirm the cutover plan in terms of sequence of activities, timing, and production environment stability. They run the cutover plan by rehearsing and documenting every step so that they can tune it as needed. After the mock cutover, they find that the time to load data and sequence it conflicts with other cutover tasks. The team adjusts that sequence. then, they confirm the readiness to run the updated Cutover plan, knowing it works without surprises.

## Other types of testing

We have described the incremental approach for testing through the different test types, scale needs, and continuous validation of the solution. But there are other types of tests that can be unique for every implementation based on the design of the solution. The following list shows examples of such test types.

- **Smoke tests**  

  Here you test if basic functions work as expected so you can confirm the component can continue to test further with other test types.

- **Data acceptance tests**  

  You validate if the migrated data goes into the target environment correctly, and if it's usable for actual operation.

- **Interface tests**  

  Here you confirm if your interfaces can be used as intended.

- **Environment testing**  

  In this test type, you validate if the new environment is fit for the purpose.

- **Reporting testing and business intelligence testing**  

  Validates that reporting and Business Intelligence can be executed and operate properly with the expected outcome and performance.

- **Device testing**  

  Focused on validating devices are operational, connect, and perform as expected, for example, RFID readers, scales, and warehouse devices, and so on

- **Network/infrastructure testing**  

  Validation of relevant underlying networking, firewalls configuration, Wi-Fi, printers, and so on

Some projects are too small to justify separate planning to run some of these types of testing. However, the concept and meaning of the tests should be folded into other types of testing.

## Next steps

- [Plan the tests](testing-strategy-planning.md)  
- [Run the implementation tests](testing-strategy-run-tests.md)  
