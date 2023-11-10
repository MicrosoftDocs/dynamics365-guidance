---
title:  Scenarios for load tests in Dynamics 365 implementation projects
description: Review the steps and patterns that simulate complex and realistic user volume in load tests for Dynamics 365 implementations.
ms.date: 06/26/2023
ms.topic: conceptual
author: edupont04
ms.author: zacolson
---

# Scenarios for load tests in Dynamics 365 implementation projects

***Applies to: Dynamics 365, Dynamics 365 Customer Service***

This article describes steps and patterns that simulate complex and realistic user volume. Use the scenarios and associated samples to build a collection of load tests for your Dynamics 365 implementation project.

Apache JMeter refers to load testing scenarios as *test plans*. A test plan consists of one or more components, as the following list outlines:

- Thread groups
- Logic controllers
- Sample generating controllers
- Listeners
- Timers
- Assertions
- Configuration elements

Learn more in [Elements of a Test Plan](https://jmeter.apache.org/usermanual/test_plan.html) on the Apache JMeter website.

We use thread groups to configure tests with realistic and complex business transactions. The thread group configuration includes the number of virtual users (which Apache JMeter refers to as *threads*), ramp-up period, and duration elements that the test runs against an application.

## Prerequisites

- [Get the samples and tools](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/Testing/At%20Scale/Samples).

## Scenarios

In a production situation, different people interact with the system at the same time. For example, a client uses a chat channel to interact with an agent. During the chat, the agent uses a model-driven app to add notes to the client's case. If the agent can't answer the client's questions, they might apply routing logic to get the case to the appropriate agent, who can then make a follow-up call. You must consider this factor in your testing strategy.

The [load test samples](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/Testing/At%20Scale/Samples) simulate Customer Service scenarios against an out-of-box configuration.

> [!NOTE]
> The samples that are provided might require additional configuration to run in a concrete Dynamics 365 implementation solution. In actual implementation projects, we recommend that you define additional testing scenarios to cover the scope of that solution.

## Tests

The HTTP sampler elements inside a thread group define an individual test that runs realistic business transactions against an application. Each test consists of a series of steps that simulate the actions that users must perform to accomplish a task. Each step is an interaction that the user has with the platform. Examples of interactions include navigation of the user interface, searches for data, and updates.

Let's look at a test that simulates the steps that a user takes to create a case record. In this example, the test simulates the following actions:

1. Start from a dashboard or home table.

    This step simulates a user accessing Customer Service.

2. Navigate to the **Case** table.

    This step simulates the user navigating to the list of cases or a similar form that is based on this table.

3. Search against the table.

    This step simulates the user searching the list.

4. Open a new record that has the required data.

    This step simulates the user opening a new case and filling in required fields.

5. Save and close the new case.

For testing purposes, each interaction can consist of one or more HTTP requests to the platform. Typically, a business transaction consists of five to 10 commands to the platform. The commands can take from one to 60 seconds to run.

## Ramp-up period

A thread group element controls the number of threads (virtual users) that Apache JMeter uses to run the test. The *ramp-up period* configuration on a thread group tells Apache JMeter how long it should take to gradually increase the number of threads (virtual users) to the configured number of threads.

The ramp-up period configuration is a duration that is measured in seconds. The duration should be long enough to avoid a sudden and unexpected surge of traffic at the start of a test. The following formula can help calculate the duration in seconds between the start of successive threads:

*Ramp-up duration* &divide; *Number of threads* = *Duration between threads*

For example, you simulate the traffic of 150 users in a test, and you use a ramp-up period of 15 minutes (= 900 seconds). In this case, the formula determines that a new thread starts every six seconds:

900 (seconds) &divide; 150 (threads) = 6 (seconds between new threads)

There is no prescriptive guidance for the length of a ramp-up period. Apache JMeter recommends that the duration between threads is short enough that the last threads start to run before the first thread has finished running. The best practice is a ramp-up period of about 15 minutes.

## Pacing

By default, Apache JMeter runs iterations of a test in immediate succession. For Dynamics 365, that scenario isn't realistic, because business users don't typically repeat a task in a rapid-fire pattern.

Load test *pacing* is a configured delay between the iterations of your tests. Pacing helps you control the requests that are sent to an application and generate a realistic usage pattern. In this way, the load test can better simulate the time gap between two sessions and create real-world scenarios that reflect user behavior.

Apache JMeter doesn't natively pace based on the number of tests per user. Instead, you use an element of the **Constant Throughput Timer**, **Constant Timer**, or **Flow Control Action** type.

- A **Constant Throughput Timer** element sets the **Target Throughput** property to your desired rate of samples per minute.
- A **Constant Timer** element runs in the context of a sampler. The timer delays the sampler by a fixed value in milliseconds. When a constant timer is used, the duration is the sum of the configured delay and the execution time of the sampler. `WhoAmI()` is a great request to run with a constant timer.
- A **Flow Control Action** element can run the context of a transaction controller. The pause that is configured in the flow control action isn't dependent on any sampler and is therefore static.

Use the [Pacing Worksheet.xlsx](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Customer%20Service/Testing/At%20Scale/Documentation/Pacing%20Worksheet.xlsx) file to help determine the appropriate pacing between test iterations and the number of tests per thread (virtual user) to run over the course of the test. Both elements can pause a thread by a fixed value in milliseconds.

To achieve the appropriate pacing in your test, you can also use other methods that use think time or third-party plugins for Apache JMeter.

## External interfaces

Integrations with other systems require consideration in a load testing scenario. Often, the scope of load testing scenarios doesn't directly evaluate the performance of integrations under load.

For example, [Digital Contact Center Platform](/digital-contact-center-platform/) depends on communication channels that give customers the choice to connect in ways that work best for them. Engagement channels include the following list:

- Voice and telephony
- Chat
- Email
- Virtual assistants
- Text messages (SMS)
- Social messaging

These channels integrate with the platform, but they are based on their own architecture and APIs that help customers integrate communication into their applications.

The best practice is to activate any integration that is involved in the user scenarios that are being load tested. In this way, your test simulates a realistic load on the integrated systems and checks their performance and scalability. You can apply the test to any non-Dataverse connector or interface that is external to Microsoft Power Platform. By indirectly testing external services, you're a step closer to avoiding bottlenecks and failures that might occur when the integrations are exposed to high volume and concurrency.

Also consider the fact that you're working with test data. Be cautious about sending load test data to production integration endpoints. For example, think carefully before you send load test emails to customers, validate fake addresses, or send text messages to real customers during a load test.

## Related resources

Use the following resources to learn more about test configuration and engagement channels in Dynamics 365:

- [Load test the Dynamics 365 solution](test-scale-dynamics-365-solution.md)
- [Scale load tests in Dynamics 365 implementations](test-load-tests-scaling.md)
- [Omnichannel Channels](/dynamics365/customer-service/channels)
- [Azure Communication Services](https://azure.microsoft.com/products/communication-services/)
- [The Elements of a Test Plan (JMeter)](https://jmeter.apache.org/usermanual/test_plan.html)

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Zach Olson](https://www.linkedin.com/in/zach-olson-b966b524/) | Senior Program Manager, FastTrack for Dynamics 365

<!--## Tags

*Products:* Dynamics 365 Customer Service-->
