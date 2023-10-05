---
title: Design for performance
description: Learn how to design for performance in Dynamics 365 projects by considering the right tool for the job, scalability, and responsiveness.
author: TimoGossen
ms.author: timogoss
ms.date: 06/19/2023
ms.topic: conceptual
ms.custom:
 - ai-gen-docs-bap
 - ai-gen-desc
 - ai-seo-date:08/25/2023
 - bap-template
---

# Design for performance

A common cause of poor performance in Dynamics 365 projects is incorrect use of the applications&mdash;in other words, uses that don't align with what the software is intended to do, usually due to poor solution design. Recall our [street design example](performing-solution.md). City planners have many ways to manage traffic. For example, they could design the streets to have 10 lanes in each direction. That would certainly meet the city's needs now and into the foreseeable future. But that approach creates complications. Does the city have land that supports that infrastructure? How easy is it for residents to cross the street? How long will a traffic light need to be red for them to cross, and how does that affect the flow of cross-traffic? Starting from the wrong approach adds complexity without necessarily solving the original problem.

Let's look at the architectural and design considerations during the early stages of an implementation project that help the solution perform as expected.

## Use the right tool for the job

Dynamics 365 products can be customized to suit the needs of many businesses and business processes. But just because you can adapt the products to achieve something functionally doesn't guarantee they do it well.

For example, the "xRM" concept, which became popular around the release of Dynamics CRM 2011, spawned systems that were designed to manage any type of relationship in the CRM, not just the customer relationship. The product's ease of basic data access, built-in user interface and security model, and rich extensibility features made it a popular starting point for custom xRM systems. Although it proved successful in many projects, many others ran into trouble because they used the product in a way that wasn't suited to its strengths.

Along with understanding what the products do now, keep the Dynamics 365 roadmap in mind. It's worthwhile to explore newer features because they often bring performance enhancements compared to older approaches.

## Design for scalability

Whether you're designing a solution for the first time or redesigning one to address issues, keep performance in mind from the beginning. The following recommendations will help you build a highly scalable solution:

- Design for parallelism and multi-threading for high-volume scenarios.
- Use set-based operations, RetrieveMultiple, insert\_recordset, and update\_recordset, as appropriate.
- Build multiple lightweight processes that are connected to each other.
- Design shorter transactions to reduce lock escalations and increase user concurrency.

## Design for responsiveness

Response time is an important factor in the success of your solution. The following recommendations will help you build a highly responsive solution:

- Consider whether to design for synchronous, asynchronous, or background (batch) processing.
- Consider data growth over time. Rapid increases in the volume of data flowing through the system require a lot of tuning to keep the same response times.
- Design for aggressive caching in Finance and Operations apps as appropriate.

Users typically assess performance by whether it's in line with their expectations, not by some objective, arbitrary measurement. That means you can consider performance improvements that don't actually speed up anything. For example, executing a task asynchronously doesn't make the task execute any faster; however, it does make sure the user interface isn't busy executing the task, preventing the user from working. As long as the user doesn't need the result of the task in real time, it could be an acceptable approach.

## Consider location

Cloud solutions remove many of the infrastructure considerations that are necessary in other software development projects. However, one key decision that still needs to be made is choosing a data center&mdash;that is, where in the world you deploy the solution physically. It's not solely a performance consideration, and it's covered in detail when we discuss [environment strategy](environment-strategy-overview.md), but one significant factor in your decision is the impact of latency.

Latency is the time it takes for data to pass from one point on a network to another. In the context of a Dynamics 365 solution, latency affects every request that's sent from a user's browser or any other component of the solution, such as integrations. It depends on the physical distance between the user and the data center and on the quality of the underlying network.

From a performance standpoint, it's desirable to keep latency to a minimum because it's an overhead on every single client request. High latency can have a considerable impact on response times and ultimately on the user experience. The optimal data center location minimizes latency.

If users are located in the same geographic area, the optimal data center is likely to be the one that's physically closest to them. Many Dynamics 365 solutions are implemented for organizations that have users around the world, making the decision more complex. It might require some users to have less than optimal, but still acceptable, latency.

For example, consider a business that operates in Europe and Australia. Its users have similar workloads and are split evenly between the two locations. Choosing a data center in either region is likely to have a detrimental effect on the users in the other region. The best answer may be to choose a location somewhere in the middle.

On the other hand, what if the users' workloads are different and the users in Australia aren't performance-critical? In that case, the best answer may be to choose a data center in Europe to optimize latency for the users who are based there and accept the higher latency for the Australian users.

Performance is just one of the factors to consider as part of your [environment strategy](environment-strategy-overview.md).

## Data migrations and integrations

Many performance issues that are related to data migration and integration are the result of unreasonable expectations of the platform, specifically around data volumes. A good data strategy can avoid this issue by making sure the solution presents only the data that's required for users to complete their day-to-day operations.

When you're planning a data migration, it's important to understand the business requirements for the data you're migrating. Implementation teams sometimes migrate far more data than users require, and then run into performance issues due to the size of the data set. For example, it takes a great deal of time to import the previous 10 years of unconverted leads into a business's sales system. Rather than try to make the data load faster, you should question whether you should be loading 10 years of stale data at all.

If you have high-volume integrations, consider when and how often they run. Heavy processing can place a strain on the application. If that happens at the same time that users are interacting with it, performance issues are likely. Global businesses especially should consider this aspect, since their systems might be in almost continuous use.

It's also important to be aware of platform limitations when you're designing any high-volume or processor-intensive operations, which are common in data migration and integration scenarios. For example, your designs for customer engagement apps need to account for [throttling limits](/powerapps/developer/data-platform/api-limits) to make sure the performance of the underlying platform remains acceptable. As another example, the Finance and Operations apps OData endpoint has a page size limit of 10,000 records and isn't designed for high-volume integrations. Other approaches, such as Data Management Framework, are better suited for these types of integrations.

[Learn more about designing integrations, integration patterns, and anti-patterns in Dynamics 365](integrate-other-solutions.md).

## Prepare for implementation

In this section, we discuss the design decisions the team should make before proceeding with the implementation.

### Environment planning

Your [environment strategy](environment-strategy-overview.md) should consider the following performance factors as the team moves toward implementation:

- Latency adds overhead to every operation. Minimize overhead by making sure applications are located as close to each other as possible.

- Performance testing typically occupies an environment for a significant amount of time, so we advise you to use a separate environment.

- Choose a performance test environment that's representative of the production environment whenever possible. For example, for Finance and Operations apps, the implementation team should recommend the appropriate environment tier based on expected load and volume.

- If performance issues arise in scaled-down development or test environments, don't assume performance improves in an environment with more resources. Without understanding the root cause of a performance issue, it's impossible to determine whether more infrastructure helps at all. So it's crucial to understand and address performance issues early in the development process rather than assume they go away in production.

### User personas

The organization should have enough user licenses to be able to realistically model the system's anticipated behavior during performance testing. Teams also need an understanding of the user personas for testing expected usage. Keep the following aspects of user personas in mind:

- Users' locations
- Users' security configurations
- The data that's typically associated with each type of user
- The expected number of concurrent users divided by persona

### Proof-of-concept development

Teams sometimes run an initial proof-of-concept project before implementing the main project to prove out ideas and gain understanding of product suitability. Custom functionality that's built during proof-of-concept projects is often carried over into the main project.

This approach can significantly accelerate development during the main project. However, it's worth bearing in mind that proof-of-concept projects often have little developmental governance. They're usually undertaken without any performance requirements or considerations in place. These projects can therefore become a source of performance problems unless the team takes the time to review the outcomes along with any new requirements prior to further implementation.

## Customization and performance

The extensibility of Dynamics 365 applications provides a powerful ability to tailor software to meet individual business needs. It also introduces risk. Performance issues commonly involve product customizations and integrations, particularly ones that involve code. This section discusses these issues and provides guidance on how to avoid common problems.

### Just write fast code?

Many performance issues are due to custom code. The fix inevitably involves reworking the code to remove bottlenecks. Project teams often question why custom code wasn't written correctly to begin with. The truth is that software development is difficult. Developers regularly wrestle with complex and abstract processes, vague and changing requirements, competing priorities, and tight deadlines. The most productive developers tend to focus on what's necessary and disregard anything that isn't in the requirements. If a requirement is missing key criteria, developers aren't aware of it and they implement based on the information they're given.

Requirements often lack performance criteria. Performance isn't top of mind for developers and it often isn't part of the sign-off criteria. It's also uncommon for developers to deeply understand the business context of the system for which they're developing code. They likely haven't experienced the time-pressured environment of a call center or order fulfillment center, so they can't judge the need for performance.

Therefore, specific performance requirements should be mapped to functional requirements where appropriate. That way, developers have visibility to performance constraints on the functionality that they're responsible for.

### Bad design leads to bad code

When you dig deeper, you often find that performance issues that are related to code aren't due to the code itself but rather to a flaw in the design. Poor decisions during the design phase can result in situations in which developers can't write code to perform an operation efficiently. Even when they carefully follow best practices, the constraints placed on the solution by its design result in poorly performing code.

### Retrofitted performance

Sometimes developers focus on getting code to work correctly before getting it to work quickly. Although this approach is reasonable, pressing deadlines often prevent optimization planned for later from getting done, leading to technical debt and the need for rework. A better approach is to be clear on any performance constraints from the start, and then implement the solution accordingly.

### Connected components

Even when developers write fast, efficient code, performance issues can still occur. In larger projects that involve several developers working in isolation, performance issues sometimes aren't discovered until components are put together. This risk should be identified during design activities. It can be mitigated using a code review process during which team members can consider the impact of the implemented pieces of code running together.

### Requirement evolution

Another reason for customization-related performance problems is changing functional requirements. Developers decide how to implement code based on the requirements they're given at a specific point in time. A change in requirements might invalidate some or all of these decisions and cause the implementation to become unsuitable.

## Common mistakes

Code can perform poorly for many reasons. Specific guidance is beyond the scope of this section. However, some common factors are involved in most performance challenges.

Some of the content in this section discusses technical concepts. The technical details aren't essential to understand, but we recommend that you understand the concepts enough to avoid them during implementation. Free tools to help you learn more about these concepts include [Solution Checker](/powerapps/maker/data-platform/use-powerapps-checker) for customer engagement apps and the [Customization Analysis Report](/dynamics365/fin-ops-core/dev-itpro/dev-tools/customization-analysis-report) for finance and operations apps.

### Chatty code

One of the most common causes of code-related performance issues is excessive round trips. Whether between the client and server or between the application and database, an excessive number of requests for an operation can significantly slow it down. Every request carries latency and processing time overhead, and it's important to keep them to a minimum.

Round trip issues are sometimes due to poor control of variables. A process might be so complex that it's easier for a developer to retrieve the same data multiple times than to structure the code to minimize the calls. We recommend that developers avoid this practice and that the code review process identifies such problems.

Round trip issues are also sometimes due to executing queries inside a loop, or worse, a nested loop. The code structure works for the developer, but the parameters of the loop can add a significant number of calls to the process, which in turn results in a significant performance issue.

Consider the following pseudocode example, triggered manually by the selection of a button in the user interface.

```csharp
foreach (var a in collection1)
{ 
  foreach (var b in collection2)
  {
    ExecuteRequest ();
  }
}
```

| Size: collection1 | Size: collection2 | Total requests | Total execution time |
|---------|---------|---------|---------|
| 2 | 2 | 4 | 0.2 second |
| 5 | 5 | 25 | 1.25 seconds |
| 10 | 10 | 100 | 5 seconds |
| 50 | 50 | **2500** | **2 minutes, 5 seconds** |

If `ExecuteRequest()` sends a single request to the server, the total number of requests is the product of the sizes of `collection1` and `collection2`. Assume each request takes an average of 50 milliseconds.

It's common for developers to write logic that iterates across collections of data that are dynamic in size, due to the data-driven nature of code in Dynamics 365 implementations. It's also common for developers to work with low volumes of data in development environments. For these reasons, these types of issues often aren't identified until the latter project stages, which start to introduce meaningful data volumes. The following themes help avoid low data collection:

- Prioritize minimal data retrieval during code design
- Retrieve each piece of data only once
- Identify any deviations from these steps as part of a code review process

### Too much data

Another common performance-related issue is caused by retrieving more data than necessary, often in columns. For example, the practice of selecting all the columns in Dynamics 365 apps to avoid specifying individual columns can cause performance issues. The number of joins that are executed on the database server to provide lookup names and option set values can be a significant overhead, particularly when querying large volumes.

The same principle applies to rows. Be mindful of the amount of data that's being retrieved because it takes time to query, download, and process the volume of records even before the code is able to interact with them.

Broadly speaking, retrieve only the data that's required by a process. Anything more is simply a waste of resources.

### Synchronous events

Many events in Dynamics 365 products can be customized. If the customization executes synchronously, it adds overhead directly to the user's experience. For example, if you run a customization on `RetrieveMultiple` in customer engagement apps or an event insert or preinsert in finance and operations apps, users have to wait for the customization to execute while they watch a spinning icon. This approach isn't recommended, but when it's necessary, exercise extreme caution to make sure the impact on performance is minimal.

### Unintended execution

Performance issues sometimes happen because customizations are executed accidentally or multiple times in error, such as duplicate plug-in steps or duplicate method calls. Project teams should make sure that developers are aware of exactly how their customizations are triggered and mindful of circumstances that might inadvertently trigger their code. The recurrence of background processes or batch jobs should be set according to business needs.

## Next steps

- [Performance overview](performing-solution.md)
- [Prioritize performance](performing-solution-prioritize-performance.md)
- [Performance testing approach](performing-solution-performance-testing-approach.md)
- [Address performance issues](performing-solution-address-performance-issues.md)
- [Product-specific guidance for performance optimizations](performing-solution-product-specific-guidance.md)
- [FastTrack performance workshop](performing-solution-workshop-strategy.md)
- [Checklist: Performance focus](performing-solution-product-checklist.md)
- [Case study](performing-solution-product-case-study.md)
