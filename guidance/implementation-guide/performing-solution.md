---
title: Explore how Dynamics 365 products can improve performance
description: Learn why prioritizing performance matters to your solution and how you can use Dynamics 365 products and tools to improve performance.
author: TimoGossen
ms.author: timogoss
ms.date: 06/19/2023
ms.update-cycle: 1095-days
ms.topic: overview
ms.custom:
  - evergreen
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:08/25/2023
  - bap-template
---

# Explore how Dynamics 365 products and tools can improve performance

When a new Dynamics 365 implementation is delivered, users typically expect an improvement in system performance. Although Dynamics 365 products are scalable and powerful, achieving a high-performance solution depends on many factors, not just the platform, apps, and services that make up your solution. This section covers why prioritizing performance matters to your solution and introduces key concepts:

- How to define your performance requirements and goals
- How to design and architect your solution for better performance
- How customization can affect performance
- What good performance testing looks like
- How to address performance issues and structure your approach to resolving them

You'll also learn more about the FastTrack performance workshop and explore how Dynamics 365 products and tools can improve performance.

## Why performance matters

The performance of a new solution can pose challenges as go-live approaches. These challenges are typically due to a failure to properly prioritize performance in earlier phases of the project.

As an example of the importance of thinking about performance from the start, consider city planning&mdash;specifically, street design. People use streets to get into and out of a city. City planners might design a basic two-lane road that could be perfectly acceptable when the city is new and the population is small. But cities tend to grow. What happens when 1,000 cars are on that two-lane road at the same time, or 10,000? What happens if an accident occurs? Eventually drivers get to their destinations, but the trip takes longer than they expect it should.

People expect superior response times and a smooth experience from the organizations they choose to provide products and services. If customers don't get it, they tend to look elsewhere. Let's return to our street design example. People might decide the city is too difficult to drive in and choose not to move there or visit it. Residents might elect different leadership. The takeaway is that system performance affects people in numerous ways and can have serious consequences.

## Customer experience is key

Dynamics 365 products support a wide range of business functions related to customer interaction and are an opportunity to either delight or disappoint. Customers might use integrated applications with a direct dependency on Dynamics 365 apps&mdash;for example, on a sales website. Poor performance can quickly turn into lost sales as customers, frustrated by the slow experience, abandon the site to shop elsewhere.

Often, customers interact with systems indirectly&mdash;for example, through a call center when a customer reports a faulty product. These types of interactions can be challenging for a business to resolve in a positive way, and they're only made more challenging if an agent can't access information in a timely manner.

System performance is key to making sure the customer experience is positive, regardless of whether the customer interacts with the system directly or indirectly.

## System success factors

Businesses everywhere are being asked to "do more with less": sell more products or serve more customers, all with reductions in budgets, people, time, and effort, at all levels of the organization. Employees must work in the most efficient way possible. They can't waste time waiting for a system to perform an action. Business users tend not to tolerate poor performance. It can be detrimental to user adoption and the system's reputation.

### User adoption

User adoption is a critical factor in the success of any software project. Any business case&mdash;and projected return on investment&mdash;depends on the system being used as intended. Poor performance directly drives user dissatisfaction and can make user adoption incredibly challenging.

Users are keen to adopt systems that increase their productivity, which essentially means minimizing wasted time. If the impact of poor performance on users' time is significant enough, they're likely to find more efficient ways of working on their own. These workarounds ultimately serve the interests of specific users rather than the business. Poor performance might eventually lead to a situation in which the system no longer serves its purpose, doesn't deliver a return on investment, and ultimately fails.

### System reputation

Performance can help or hinder user adoption even before go-live. During the development phase, the application is typically presented to key users in different areas of the business to collect feedback. As these users talk to colleagues about their experience, the application's reputation spreads long before most users touch the system. Performance impressions tend to spread quickly. For example, if a demonstration goes well, a wave of excitement might flow through the company. The anticipated improvement in productivity can help increase user adoption.

If performance issues are discovered in the buildup to go-live or shortly after, it causes a great deal of stress for the project team. The team already works long hours to deliver a functional system in a timely manner. The realization that the system doesn't perform well can quickly force a change in priorities and derail progress. These issues are often visible at the most senior levels and tend to escalate quickly.

## But it's in the cloud

Having established that performance matters, surely you can just deploy the fastest computers available to run the solution, right? Well, not quite.

Dynamics 365 is a cloud-based software as a service (SaaS) solution. Cloud solutions entail different challenges from on-premises deployments. For example, several years ago, Dynamics 365 deployments were commonly hosted on infrastructure that was physically located close to the users. Today, solutions are deployed across the world on a range of devices with different network infrastructures. Project teams need to build solutions that accommodate various hardware, increased network latency, and a range of network quality.

Because Dynamics 365 is a SaaS application, it means that Microsoft maintains the infrastructure that the solution runs on. Other than a few predefined configuration options, the infrastructure is outside a customer's control. This transfer of control offers benefits in setup cost and ongoing maintenance responsibilities, but limits options to change performance.

But the performance of an application involves more than the infrastructure. A correlation exists between the performance of software and the quality of its underlying infrastructure. However, the on-premises mindset&mdash;fixing software problems with more, better, or faster hardware&mdash;is expensive and only a temporary fix. Let's recall our city planning example. Turning a two-lane road into a privately operated toll road or highway doesn't necessarily mean drivers arrive at their destinations any faster.

Most performance issues are best solved ahead of time, by avoiding them in the first place through correct implementation decisions, not by adding hardware. Moreover, performance isn't guaranteed simply because the software is running in the cloud. It's still the responsibility of the project team to deliver a well-performing solution.

## Project team roles

Many factors contribute to the performance of a system. It's important to understand the roles on a project team and the responsibilities of each one in making sure the solution as a whole performs acceptably. Performance is a shared responsibility.

| Role | Task | Decription |
|--|--|--|
| Customer | Owns the solution | <ul><li>Clearly describe the business goals and predict transactional volumes</li><li>Complete the usage profile based on the licenses purchased</li><li>Whenever applicable, optimize the business operations to maximize the efficiency of the solution</li><li>Plan performance testing and allocate resources</li></ul> |
| Partner | Builds the solution | <ul><li>Understand and document the customer processes</li><li>Capture the performance nonfunctional requirements</li><li>Build a solution that's optimized, fit for purpose, and doesn't disrupt the scalability of the Dynamics 365 product</li><li>Provide the expertise to educate the customer on performance testing</li><li>Support the customer in performance testing</li></ul> |
| Microsoft | Manages the platform | <ul><li>Makes sure the core platform components have sufficient resources to deliver acceptable performance, when used reasonably</li><li>Deliver solutions to performance issues within our scope (for example, index, product hotfix, infrastructure)</li><li>Support investigations into performance issues outside our scope (for example, customization fixes)</li></ul> |

## Conclusion

Solution performance is essential for delivering a positive user experience and achieving business outcomes. To create a high-performing solution, you need to have clear goals, realistic expectations, and the right software. You also need to be mindful of the effect of customizations and plan ahead to avoid performance issues. Performance testing should reflect real-world scenarios and help you identify areas for improvement. Performance optimization is an ongoing process that requires continuous monitoring and refinement.

## Next steps

- Learn how to [prioritize performance](performing-solution-prioritize-performance.md) in your solution development process
- Follow the best practices to [design for performance](performing-solution-design-for-performance.md) and avoid common pitfalls
- Understand the [performance testing approach](performing-solution-performance-testing-approach.md) and tools that you can use to measure and improve your solution performance
- Find out how to [address performance issues](performing-solution-address-performance-issues.md) that you encounter during testing or production
- Explore the [product-specific guidance for performance optimizations](performing-solution-product-specific-guidance.md) for different Microsoft products and services
- Request a [FastTrack performance workshop](performing-solution-workshop-strategy.md) to get expert help and guidance on your solution performance
- Use the [checklist: Performance focus](performing-solution-product-checklist.md) to review your solution design and implementation for performance considerations
- Read the [case study](performing-solution-product-case-study.md) of how a customer improved their solution performance with FastTrack support
