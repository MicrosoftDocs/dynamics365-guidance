---
title: Improve performance with smart design choices
description: Learn how to design Dynamics 365 solutions that perform well by using the right tools. Learn how to avoid common mistakes and how to scale for demand.
author: TimoGossen
ms.author: timogoss
ms.date: 01/30/2024
ms.topic: concept-article
ms.custom:
 - ai-seo-date: 01/29/2024
 - ai-gen-docs-bap
 - ai-gen-desc
 - ai-gen-title
 - bap-template
content_well_notification: AI-contribution
---

# Improve performance with smart design choices

Performance is a key factor in the success of any Dynamics 365 project. Poor performance can frustrate users, reduce productivity, and increase costs. To avoid these problems, you need to design your solutions with performance in mind from the start.

In this article, you'll learn how to:

- Use the right tool for the job
- Design for scalability and responsiveness
- Consider location and latency
- Plan data migrations and integrations
- Prepare for implementation
- Customize without compromising performance

## Use the right tool for the job

Dynamics 365 products are flexible and customizable. You can adapt them to suit many business needs and processes. But that doesn't mean you should use them for everything. Sometimes, using a product in a way that doesn't match its intended purpose can cause performance issues.

For example, some people used Dynamics CRM 2011 to create custom "xRM" systems that managed any type of relationship, not just customer relationships. They liked the product's easy data access, user interface, security model, and extensibility features. But this approach didn't work well for some projects because it didn't take advantage of the product's strengths.

To avoid this mistake, you need to understand what each product does best and how it fits into your solution architecture. You also need to keep up with the Dynamics 365 roadmap. New features often bring performance enhancements compared to older approaches.

## Design for scalability and responsiveness

Scalability and responsiveness are two aspects of performance that affect user satisfaction and efficiency. Scalability means how well your solution can handle increasing demand or workload. Responsiveness means how fast your solution can respond to user requests or actions.

To design for scalability, you should:

- Use parallelism and multi-threading for high-volume scenarios. This means splitting a task into smaller parts that can run at the same time on different processors or threads.

- Use set-based operations, RetrieveMultiple, insert\_recordset, and update\_recordset, as appropriate. These are methods that let you work with multiple records at once, instead of one by one.

- Build multiple lightweight processes that are connected to each other. This means breaking down a complex process into simpler steps that can run independently or in sequence.

- Design shorter transactions to reduce lock escalations and increase user concurrency. A transaction is a group of operations that must succeed or fail together. A lock escalation is when the database locks a larger portion of data to prevent conflicts. User concurrency is the number of users who can access the data at the same time.

To design for responsiveness, you should:

- Consider whether to design for synchronous, asynchronous, or background (batch) processing.

- Consider data growth over time. As more data flows through your system, you might need to tune it to maintain the same response times.

- Design for aggressive caching in finance and operations apps as appropriate so that data can be accessed faster.

Remember that users judge performance by their expectations, not by objective measures. You can improve perceived performance by using techniques that don't actually speed up anything but make the user experience smoother. For example, using asynchronous processing doesn't make a task faster, but it frees up the user interface so that the user can do other things.

## Consider location and latency

When you deploy your solution in the cloud, you need to choose a datacenter location&mdash;that is, where your solution's physical servers and databases are located. Your choice affects performance because of latency.

Latency is the time it takes for data to travel from one point on a network to another. It depends on the physical distance between the points and the quality of the network. Latency adds overhead to every request that your solution sends or receives.

To minimize latency, you should choose a datacenter location that's close to your users and other components of your solution, such as integrations. But this decision isn't only about performance. You also need to consider other factors, such as:

- Data sovereignty and compliance regulations
- Availability and reliability of services
- Cost and capacity of resources
- Disaster recovery and backup options

If you have users in different parts of the world, you might need to compromise on latency for some of them. You should analyze your user personas and workloads to find the optimal balance.

Choosing a datacenter location is part of your [environment strategy](environment-strategy-overview.md).

## Plan data migrations and integrations

Data migration and integration are common tasks in Dynamics 365 projects. They can also cause performance issues if you don't plan them carefully. Here are some tips to help you avoid problems:

- Understand the business requirements for the data you're migrating. Don't migrate more data than users need. For example, you probably don't need to import 10 years of old leads into your sales system.

- Consider when and how often your integrations run. Avoid running heavy processes when users are interacting with the system. Schedule them for off-peak hours or use asynchronous processing.

- Be aware of platform limitations and best practices when you design your integrations. For example, use the Data Management Framework for high-volume integrations in finance and operations apps, and respect the [throttling limits](/powerapps/developer/data-platform/api-limits) in customer engagement apps.

[Learn more about designing integrations, integration patterns, and anti-patterns in Dynamics 365](integrate-other-solutions.md).

## Prepare for implementation

Before you start implementing your solution, you should prepare aspects that affect performance, such as:

- [Environment planning](environment-strategy-overview.md): Decide how many environments you need, what tier or size they should be, and where they should be located. Make sure your environments are representative of your production environment as much as possible. Use a separate environment for performance testing.

- User personas: Define the types of users who will use your solution, their locations, security configurations, data sets, and expected number of concurrent users. You'll need this information to model realistic scenarios for performance testing.

- Proof-of-concept development: If you do a proof-of-concept project before the main project, make sure you review the outcomes and requirements before carrying over any custom functionality. Proof-of-concept projects often have low governance and performance standards, so they might introduce issues into the main project.

## Customize without compromising performance

One of the main benefits of Dynamics 365 products is their extensibility. You can customize them to meet specific business needs that aren't covered by the out-of-the-box features. But customization introduces risk. Many performance issues are related to custom code or configuration that isn't optimized or tested properly.

To avoid these issues, you should follow these guidelines:

- Include performance criteria in your functional requirements. Make sure developers know what level of performance is expected for each feature they implement.

- Review your design decisions before writing code. Make sure your design is suitable for the requirements and doesn't create unnecessary complexity or overhead.

- Write fast and efficient code. Minimize round trips between components, retrieve only the data you need, use appropriate methods and tools, and avoid loops or nested loops whenever possible.

- Test your code in different environments and scenarios. Make sure your code works well with other components and doesn't run accidentally or multiple times.

- Use synchronous events sparingly. Synchronous events block the user interface until they finish executing. Use asynchronous or background events instead whenever possible.

For more technical guidance on how to write performant code, see [Solution Checker](/powerapps/maker/data-platform/use-powerapps-checker) for customer engagement apps and the [Customization Analysis Report](/dynamics365/fin-ops-core/dev-itpro/dev-tools/customization-analysis-report) for finance and operations apps.

## Next steps

- Understand the [performance testing approach](performing-solution-performance-testing-approach.md) and tools that you can use to measure and improve your solution performance
- Find out how to [address performance issues](performing-solution-address-performance-issues.md) that you encounter during testing or production
- Explore the [product-specific guidance for performance optimizations](performing-solution-product-specific-guidance.md) for different Microsoft products and services
- Request a [FastTrack performance workshop](performing-solution-workshop-strategy.md) to get expert help and guidance on your solution performance
- Use the [checklist: Performance focus](performing-solution-product-checklist.md) to review your solution design and implementation for performance considerations
- Read the [case study](performing-solution-product-case-study.md) of how a customer improved their solution performance with FastTrack support
