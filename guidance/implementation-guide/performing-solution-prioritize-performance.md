---
title:  Prioritize performance
description: Learn how to prioritize performance early on to ensure successful Dynamics 365 implementations and user acceptance.
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

# Prioritize performance

Performance issues in Dynamics 365 projects are commonly analyzed, understood, and fixed at a solution level, often against tight deadlines and high visibility. It's fair to say that the most common cause of unexpected performance issues is a failure to properly prioritize performance from the beginning of a project.

## An ounce of prevention

Too often, organizations implement a Dynamics 365 solution, get it to a point where it's functionally correct, and only then think about the system's performance. This approach might seem logical under the pressure of delivery. However, the inevitable performance issues place extra stress on the team during the most difficult parts of the project, and they add work during the buildup to go-live.

:::image type="content" source="media/performance-fix-issues-early.png" alt-text="A picture showing phases of an implementation project and indicating to address performance issues early.":::

For instance, changes that are needed to resolve performance issues after functional testing is completed come with a high risk of introducing bugs. It essentially invalidates the functional testing, since a regression testing cycle is required to make sure performance fixes haven't broken previously tested functionality. This wastes time at a critical stage in the project.

Why do many Dynamics 365 implementations fail to prioritize performance? Sometimes project teams lack experience with the specific products. Performance issues can be complex. It's often difficult to foresee them without extensive knowledge of the platforms and associated patterns and anti-patterns gained over years of experience.

Sometimes projects intentionally don't include performance testing in an attempt to save on budget, or time constraints force performance activities to take a lower priority. These approaches are shortsighted. The best way to avoid performance problems is to be proactive and seek out and address risks early to minimize their impact. It's a more productive approach than reactively responding to problems as they occur. When it comes to avoiding performance issues, an ounce of prevention really is worth a pound of cure.

## Performance doesn't just happen

Performance in any software project isn't guaranteed. It requires careful planning, expectation management, open communication, and dedicated time and resources. This is especially true for projects that feature integrations, data migrations, and extensions on top of the base product, all of which are common in Dynamics 365 implementations. Anything that's added to the core Dynamics 365 app has the potential to negatively affect performance, so the impact needs to be understood and managed to ensure performance remains acceptable.

Performance influences decisions in many areas of the project:

- Data strategy: Is the volume of data that must be stored likely to cause performance issues for users?
- Integration strategy: Are real-time integrations feasible given users' performance expectations? Can overnight batch integrations complete within a given timeframe?
- Data modeling: Do we need to denormalize for performance reasons?
- Security modeling: Will our security model work at scale? Are there bottlenecks?
- Environment strategy: Is a performance test environment available? Is our performance test environment representative of production? Have we budgeted for performance testing?
- Design and implementation of customizations: Are the developers building to meet specific performance goals? Do user expectations align with what's technically feasible? Do we need to use patterns, such as asynchronous or synchronous, or batch jobs, such as background processes?
- Testing design and approach: What's acceptable? What's considered a pass or fail? Is our testing representative of user behavior? Are we testing based only on today's business requirements or keeping future expansions in mind?
- User acceptance and adoption: Is performance measurable? Are user expectations realistic?

These aren't the types of questions the delivery team should be asking when a performance issue surfaces, especially as the go-live deadline approaches. A successful project has answers to these questions early on. At the least, the delivery team should identify risks and seek possible resolutions in the early stages of delivery. This effort might lead to proof-of-concept work to test performance.

Let's look at performance in the context of our [street design example](performing-solution.md) and consider the questions that should have been asked and answered at the beginning of the project. For instance, how many residents live in the city? What's the projected population growth? How much traffic is expected to be on the roads? Will traffic lights be installed? If so, how many, and how will that affect traffic? What's the speed limit and are there risks associated with it? Knowing the answers to questions like these helps city planners determine the best street design before they even start the project.

## Resource expectations

Considering performance from the early stages of a project also helps set correct expectations for time, money, effort, and people. For example, a dedicated test environment is needed for performance testing, as well as people to do the testing. Business stakeholders might need more time with the delivery team to understand, agree with, and document performance requirements. It might be necessary to allocate more development time and resources for code optimization.

It's important to consider performance management as an ongoing subject rather than a one-time activity at a particular point in the implementation. For example, projects typically require multiple iterations of testing and optimizing, rather than a single performance test, because the effect of any changes that are made to optimize performance must be validated. This is especially relevant in more agile implementations, where evolving requirements can lead to significant changes in functionality over time.

Projects that prioritize performance successfully have people dedicated to performance-related activities. A single owner should be identified to drive performance planning and remediations across the development teams during all phases of the project.

## Achievable goals

Acceptable performance is the goal of every project, but "acceptable" is often defined vaguely, if at all. Successful projects are clear on what that means and are able to track progress against performance goals.

If you ask users for their performance requirements, they'll tell you the system needs to be fast. "Fast" is an ambiguous term. People have different expectations of what it looks like, which makes understanding whether you've achieved acceptable performance nearly impossible. A better approach is for the implementation team and stakeholders to establish a common understanding about performance, which allows them to:

- Align expectations of the definition of "acceptable."
- Understand the business impact of not achieving "acceptable."
- Understand constraints during the design process.
- Provide clear instructions to developers during implementation.
- Test in a meaningful way with behavior models representative of expected usage.
- Determine whether "acceptable" has been achieved.
- Assess gaps between what's been achieved and what's acceptable.

The same approach applies to other system requirements. It's vital that you consider performance just like other requirements that you gather in the initial stages of implementation.

Specifically for performance, it's also important to know when to stop optimizing. Any optimization of tested code comes with some risk of regression issues. Without a clear understanding of when enough is enough, it's difficult to gauge what level of optimization is sufficient and when further optimization is unnecessary.

The implementation team should review performance requirements along with other system requirements as early as possible to assess the impact to the organization. Some performance requirements might significantly affect design decisions, so you should be aware of them as soon as possible.

Occasionally, a requirement might not be achievable with the available software. If any doubt exists, run a small proof-of-concept pilot project. Understanding feasibility as early as possible minimizes the risk of accepting requirements that are impossible to achieve. Discuss any requirements that are unachievable with the business. Such discussions are more positive in the early stages of the project than during user acceptance testing or immediately before going live.

## Performance-critical tasks

People use a system to perform tasks. Some tasks have higher performance needs than others. For example, for a call center agent who's attempting to access customer data at the start of a conversation, every second counts. Time spent waiting for a form to load is time wasted for both the agent and the customer. On the other hand, an accountant who's preparing month- or year-end financial statements might expect to wait a little while for a report to run. Performance is still important. But it's more difficult to justify the business case for investing time, effort, and money in improving performance for activities that occur infrequently.

For example, business users might offer justifications like the following when they ask for a performance improvement:

|:::image type="content" source="media/rabbits.png" alt-text="A picture of a rabbit.":::|:::image type="content" source="media/conveyerbelt.png" alt-text="A picture of a conveyor belt.":::|:::image type="content" source="media/timetasks.png" alt-text="A picture of a list of tasks and an hourglass.":::|:::image type="content" source="media/cloudupload.png" alt-text="A picture of a building with an arrow pointing at the moon.":::|
|:----:|:----:|:----:|:----:|
|*"I need to load this record quickly for a customer on the phone or I might lose the sale."*|*"I need to load the products into the delivery truck to meet my shipment schedule."*|*"I have to do this task quickly to meet a service-level agreement."*|*"This overnight process needs to happen within the time window or users can't get their work done."*|

Spend time with users to understand the activities for which performance plays a critical role. Agree on these areas with project stakeholders and then focus performance-related work on these activities to maximize the value of the team's efforts. Consider performance testing for each system area, including functional processes, background operations like batch jobs and workflows, integrations, data migration, and reporting and analytics.

It's worth considering any planned customizations in combination with the key performance-critical areas that users identify. Customizations can introduce a performance overhead and need to be carefully managed to make sure performance remains acceptable. Understanding how customizations map to performance-critical activities makes sure special attention is given to performance during design and implementation.

For each critical task you identify, have discussions with users about what they think is reasonable performance. It's important to discuss each task separately and focus on that specific task when you're discussing acceptability with users. You end up with different requirements for different tasks, which is a more granular, actionable, and sensible outcome than having broad, systemwide requirements.

Also consider the different experiences that these two types of users have:

- User A has exclusive access to Dynamics 365
- User B uses the system only during peak hours, along with thousands of other concurrent users, or while an intensive background process runs

## Performance now and in the future

We recommend that you estimate predicted system usage throughout the day, week, and month. That helps you understand the volumes of users, data, and actions at these times to spot potential performance issues. Document the anticipated transaction volumes across all workloads by time of day early in the project. This activity is helpful in several ways:

- Understanding the real-world conditions under which performance metrics must be achieved guides you in setting performance requirements.
- It informs the design of performance testing so that the tests simulate real system usage.
- It identifies the times of peak load, when the potential for performance issues is higher, and areas to prioritize during performance testing.
- It identifies the times of minimal load, when it may be suitable for running integration or background jobs, with the aim of distributing load more evenly across the day.

Estimates don't need to be exact. Having an approximate understanding of the order of magnitude of transactions is sufficient at this stage. From a performance standpoint, the difference between 50 or 60 transactions an hour is likely to be negligible. On the other hand, the difference between 50 and 50,000 is significant.

The usual measurement of performance is time taken. Requirements should be based on what users and stakeholders can agree is an acceptable time to perform a specific action, in a way that can be measured. However, it's often easier to ask users what unacceptable performance looks like and work backwards. This approach tends to lead to more realistic requirements, although they might be aggressive. Take the time to understand the business impact and risk of unacceptable performance in these scenarios.

Recall the example of city planners [designing streets](performing-solution.md). The two-lane road that's acceptable when the city is new quickly becomes inadequate as the city's population grows. When you're discussing performance requirements with users and business stakeholders, consider the business roadmap and make sure requirements account for future demand on the system. Plan also for seasonality in the system load&mdash;for example, at the end of the year.

## User input

It's important to keep users in mind during the implementation of the project. Performance is always linked to perception. It can affect users' engagement during testing and ultimately help or hinder user adoption at launch. Projects that prioritize performance early on tend to present better-performing solutions during implementation. Early planning helps reassure users that they're receiving a solution that makes them more productive, and leads to better engagement and adoption overall.

Any discussion about what is and isn't acceptable should include representatives of the system's users. Decisions that are made without their input risk rejection in the later stages of the project. This doesn't mean users are solely responsible for deciding performance requirements. It's important to be clear that performance comes with an associated cost, and business stakeholders need to assess users' requests in the context of the wider project. They should understand the underlying need for each performance requirement and be prepared to consider compromises where they make sense. Performance for the sake of performance is expensive and unnecessary. Communicate this to users and take a pragmatic approach to focus on what specific performance requirements are important.

## Documentation

It's crucial that you document performance requirements just like other system requirements. Documenting requirements provides visibility to all parties about expectations for the new solution and clear goals for the implementation team. Make sure that any performance risks that are identified during discussions with users are documented in the project risk register so that they're tracked and mitigated as much as possible.

With clear performance criteria established, accepted, and documented, the project team can move confidently on to implementing a system that performs within expectations.

## Next steps

- [Design for performance](performing-solution-design-for-performance.md)
- [Performance testing approach](performing-solution-performance-testing-approach.md)
- [Address performance issues](performing-solution-address-performance-issues.md)
- [Product-specific guidance for performance optimizations](performing-solution-product-specific-guidance.md)
- [FastTrack performance workshop](performing-solution-workshop-strategy.md)
- [Checklist: Performance focus](performing-solution-product-checklist.md)
- [Case study](performing-solution-product-case-study.md)
- [Performance overview](performing-solution.md)
