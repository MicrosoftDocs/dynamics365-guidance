---
title: Prioritize performance in your Dynamics 365 implementations
description: Learn how to plan ahead for performance in your Dynamics 365 projects and avoid common pitfalls that can affect user satisfaction.
author: TimoGossen
ms.author: timogoss
ms.date: 01/29/2024
ms.topic: concept-article
ms.custom:
  - evergreen
  - ai-seo-date: 01/29/2024
  - ai-gen-docs-bap
  - ai-gen-desc
  - bap-template
---

# Prioritize performance in your Dynamics 365 implementations

You want your Dynamics 365 projects to be fast and reliable. But performance issues can&mdash;and almost certainly will&mdash;happen if you don't think about performance from the start of your project. They can cause stress, delays, bugs, wasted money and effort, and worst of all, unhappy users. It's better to prevent performance issues than to cure them. In this article, we'll discuss how to do that.

## Plan for performance

Performance isn't something that just happens. You need to plan for it, just like any other requirement. You need to set clear goals, manage expectations, communicate well, and allocate time and resources.

This is especially true if you have integrations, data migrations, or customizations in your project. These things can slow down your system if you don't handle them carefully.

Performance affects many aspects of your project:

- Data strategy: How much data do you need to store? Will it affect how fast users can access it?

- Integration strategy: Can you do real-time integrations without slowing down the system? Can you do batch integrations within a certain time?

- Data modeling: Do you need to simplify your data structure for faster queries?

- Security modeling: Will your security rules work well with a lot of users and data? Are there any bottlenecks?

- Environment strategy: Do you have a test environment for performance testing? Is it similar to the production environment? Have you budgeted for performance testing?

- Design and implementation of customizations: Are the developers following performance best practices? Are they meeting specific performance goals? Do users know what's possible and what's not?

- Testing design and approach: How do you measure performance? What's good enough and what's not? Are you testing with realistic scenarios and data? Are you testing for current and future needs?

- User acceptance and adoption: How do you track performance? Are users' expectations realistic?

You should ask&mdash;and answer&mdash;these questions early in the project. Don't wait until you run into problems. If you're not sure about something, do a proof-of-concept to test it out.

## Plan your resources

Performance needs time, money, effort, and people. You should plan for these resources from the start of your project. For example, you'll need a test environment and testers for performance testing. You'll also need more time and developers for code optimization.

Performance isn't a one-time activity. You need to keep working on it throughout the project. You'll need to test and optimize your system several times, not just once. That's because any changes you make can affect performance. This is especially true if you use agile methods, where requirements can change a lot.

You also need someone to lead the performance work. This person should drive performance planning and fixing performance issues across the development teams in all phases of the project.

## Set achievable goals

You want your system to be fast. But what does "fast" mean? Different users might have different opinions. The project's stakeholders need to agree on what "fast" means and how to measure it.

Don't ask users for their performance requirements. They'll say they want the system to be as fast as possible. That's not very helpful. Instead, ask them what they think is too slow. Then work backwards from there. This way, you'll get more realistic requirements.

The implementation team and stakeholders also need to agree on what an "acceptable" solution looks like. What are the consequences of poor performance and the limitations of your system? Give clear guidance to your developers on how to build a fast and reliable system. Test your system with realistic scenarios and data, and measure whether you've met whatever goals define "acceptable" for your project. You should also identify any areas where you need to improve performance.

Also, consider the different tasks that users do with the system. Some tasks are more important than others for performance. For example, a salesperson who needs to look up a customer's information quickly has a higher performance need than an accountant who runs a monthly report. Focus on the tasks that are critical for performance and make sure they meet the requirements. For each critical task, talk to users about how long they think it should take. Be specific and focus on one task at a time. You'll end up with different requirements for different tasks, which makes sense.

Think about how many users will use the system at the same time, and when. This will help you understand the peak load and the minimum load on the system. You can use this information to plan your performance testing and optimize your system resources.

Finally, think about the future. How will your system usage change over time? Will you have more users, more data, more features? Plan for growth and scalability in your performance requirements.

## Get user input

Users are the ones who will use the system every day. Their perception of performance matters a lot. It can affect their engagement, satisfaction, and adoption.

That's why you should involve users in your performance planning. Get their feedback on what matters to them and why. Explain to them that performance comes with a cost, and that you need to balance their needs with the project budget and timeline.

Don't make decisions about performance without user input. You might end up with a system that doesn't meet their expectations or needs.

## Document everything

Performance requirements are just like any other requirements. You need to document them clearly and track them throughout the project.

Documenting your performance requirements helps you:

- Align expectations with users and stakeholders.
- Understand the business impact of poor performance.
- Design your system for optimal performance.
- Test your system with meaningful metrics and scenarios.
- Assess whether you've met your performance goals.
- Identify gaps and areas for improvement.

You should also document any performance risks that you find during your planning. Add them to your project risk register so that you can monitor and mitigate them.

With clear performance requirements, you can move on to building a system that performs well and makes your users happy.

## Next steps

- Follow the best practices to [design for performance](performing-solution-design-for-performance.md) and avoid common pitfalls
- Understand the [performance testing approach](performing-solution-performance-testing-approach.md) and tools that you can use to measure and improve your solution performance
- Find out how to [address performance issues](performing-solution-address-performance-issues.md) that you encounter during testing or production
- Explore the [product-specific guidance for performance optimizations](performing-solution-product-specific-guidance.md) for different Microsoft products and services
- Request a [FastTrack performance workshop](performing-solution-workshop-strategy.md) to get expert help and guidance on your solution performance
- Use the [checklist: Performance focus](performing-solution-product-checklist.md) to review your solution design and implementation for performance considerations
- Read the [case study](performing-solution-product-case-study.md) of how a customer improved their solution performance with FastTrack support
