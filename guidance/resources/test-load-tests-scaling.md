---
title: Scale load tests with horizontal scaling and vertical scaling in Dynamics 365 implementations
description: Learn about some scaling patterns that can help maintain load tests in Dynamics 365 implementation projects.
ms.date: 10/30/2023
ms.topic: conceptual
author: edupont04
ms.author: zacolson
---

# Scale load tests with horizontal scaling and vertical scaling in Dynamics 365 implementations

***Applies to: Dynamics 365 Customer Service***

This article describes some scaling patterns that you can use to maintain the consistency and reliability of a load test in a Dynamics 365 implementation project.

*Scaling* is the process of increasing the capacity of a machine or instance to handle a workload, ensure stability, and improve performance. There are two scaling methods:

- **Horizontal scaling**: This method, which is also known as *scale-out*, adds nodes to your infrastructure to meet the required demands. An example is the addition of machines to load-balance a workload.
- **Vertical scaling**: This method, which is also known as *scale-up*, adds more resources to a single node. An example is the addition of RAM or CPU resources to a server to increase its processing power.

*Virtual users* are a key concept of load testing. A virtual user is the equivalent of an independent test run. You typically configure multiple virtual users to simulate concurrent test runs. Apache JMeter refers to virtual users as *threads*.

## Test users

When you test components of Microsoft Power Platform at a high scale, we recommend that you *scale out* the volume of traffic that virtual users generate across a collection of *test users*. A test user is a Microsoft Entra ID user that is configured to run the virtual user traffic when you test at scale. You configure the user accounts specifically for testing purposes.

Test users must meet the following requirements:

- The accounts are appropriately licensed.
- The accounts don't have multifactor authentication.
- The accounts follow a persona or a specific security role configuration.

The creation of multiple test users is a method of scaling your test. Test users enable you to test the impact of your security model and overcome service protection limits that might cause errors while a test is running.

Your testing should accurately reflect your security model. The impact that different security configurations have on performance can depend on the privileges that are assigned to a user.

Any tests that are run in the context of a user that has the system administrator security role have better performance. No role-based security filtering is applied to the information that is returned to a user that has the system administrator security role.

As a best practice, you should configure enough test users to cover the personas that are tested in your load test. For high-transaction scenarios, you might configure multiple test users that have the same personas. In this way, you can distribute the transaction volume and avoid throttling.

## Examples of test users

- **Test user 1**:

    - Role: *Customer Service Agent*
    - Tables used: `Case`, `Account`, and `Contact`
    - Security role: *Customer Service*:

        - Organization-level read privileges to the `Account` and `Contact` tables
        - User-level update privileges to the `Case` table

- **Test user 2**:

    - Role: *Customer Service Manager*
    - Tables used: `Case`, `Account`, and `Contact`
    - Security role: *Customer Service Manager*:

        - Organization-level read privileges to the `Case`, `Account`, and `Contact` tables
        - Organization-level update privileges to the `Case`, `Account`, and `Contact` tables

- **Test user 3**:

    - Role: *Quality Control*
    - Security role: *Case Report*:

        - Organization-level read privileges to the `Case`, `Account`, and `Contact` tables

### Test user example scenario

The Customer Service team consists of the following users:

- 100 customer service agents
- Seven customer service managers

Some managers also fulfill quality control responsibilities.

The team of customer service agents handles an average of 250 cases during peak hours. Customer service managers review and update case information based on specific metrics. Each manager handles an average of one case during peak hours. Quality control runs one report per day to analyze the previous day's case metrics.

In the preceding example, agent transaction volume exceeds manager or quality control volume. Because of the higher volume at peak usage, the customer service agent scenario requires multiple test users to distribute the virtual user volume and avoid throttling.

## Azure Load Testing load test engines

Azure Load Testing runs a load test by using *test engines*. A test engine abstracts the required infrastructure for running a high-scale load test. The test engines run the Apache JMeter script to simulate a scenario where virtual users (threads) simultaneously access your application endpoints.

Azure Load Testing recommends that you keep the number of threads in a script below a maximum of 250. If your testing must exceed 250 threads, you can configure the load test in Azure Load Testing by increasing the number of test engine instances that run the test. Test engines run in parallel.

Consider the following formula for the number of virtual users in a load test:

*Number of virtual users* = *Number of threads* &times; *Number of test engine instances*

For example, if your load test calls for a simulation of user traffic from 1,000 virtual users, the following formula can be used:

1,000 (virtual users) = 250 (threads) &times; 4 (test engine instances)

## Service protection API limits

To ensure consistent availability and performance for everyone, Dataverse applies limits to API usage. These limits are Service protection API limits, and their purpose is to detect when client applications are making extraordinary demands on server resources. They should not affect a typical user's day-to-day use of model-driven apps, canvas apps, or Power Pages. They provide a level of protection from random and unexpected increases in request volume that might affect the availability and performance of the platform.

Service protection API limits are enforced on each user individually, per web server. They are based on three metrics.

| Metric | Description | Limit per web server |
|---|---|---|
| Number of requests | The cumulative number of requests that the user sends | 6,000 within the five-minute sliding window |
| Execution time | The combined execution time of all requests that the user sends | 20 minutes (1,200 seconds) within the five-minute sliding window |
| Number of concurrent requests | The number of concurrent requests that the user sends | 52 or more |

If the platform detects a pattern that exceeds the threshold for one of the limits, it throws an error. The error indicates that too many requests have been made:

- With the Web API, a "429 Too Many Requests" error is returned.
- With the Dataverse software development kit (SDK) for .NET, you receive an `OrganizationServiceFault` error that has one of three specific errors. Learn more in [Service protection API limit errors returned](/power-apps/developer/data-platform/api-limits?tabs=sdk#service-protection-api-limit-errors-returned).

## Next steps

Use the following resources to learn more about the subjects that are discussed in this article:

- [Load test the Dynamics 365 solution](test-scale-dynamics-365-solution.md)
- [Security roles (Power Platform)](/power-platform/admin/security-roles-privileges)
- [Service Protection API Limits (Power Platform)](/power-apps/developer/data-platform/api-limits?tabs=sdk)
- [Microsoft Dataverse API Limits (Power Platform)](/power-apps/maker/data-platform/api-limits-overview)
- [Azure Load Testing](/azure/load-testing/overview-what-is-azure-load-testing)
- [High-scale load testing (Azure Load Testing)](/azure/load-testing/how-to-high-scale-load)

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Zach Olson](https://www.linkedin.com/in/zach-olson-b966b524/) | Senior Program Manager, FastTrack for Dynamics 365

<!--## Tags

*Products:* Dynamics 365 Customer Service-->
