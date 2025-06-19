---
title: Product-specific guidance for optimizing performance
description: Learn how to optimize the performance of your Dynamics 365 solutions depending on the apps that are part of the implementation.
author: TimoGossen
ms.author: timogoss
ms.date: 01/29/2024
ms.topic: concept-article
ms.custom:
  - evergreen
  - bap-template
  - ai-seo-date: 01/29/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Product-specific guidance for optimizing performance

You want your Dynamics 365 solutions to run fast and smooth. That's good for you, your customers, and your project success. In this article, you'll learn how to boost the performance of your solutions based on the products you use.

## Make finance and operations apps faster

Here are some ways to get more speed from your finance and operations apps solutions:

- Use Tier-2 or higher environments. Tier-1 environments are too slow. [Learn more about environments in cloud deployment](/dynamics365/fin-ops-core/dev-itpro/deployment/cloud-deployment-overview).

- Keep your solution updated with hotfixes, platform updates, and quality updates. They can fix performance issues and errors. [Learn how to apply updates to cloud environments](/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system).

- Log any performance risks and check them often.

- Use the Dynamics 365 migration framework to import and export large datasets. OData can't handle large volumes of data well. Learn more at [Migrate to Dynamics 365 online from Dynamics on-premises products](../migrate/overview.md).

- Use set-based data entities and parallelism to move large datasets faster.

- Build your own data entities to avoid extra columns and tables that might slow down your solution.

- Set up a batch framework with batch groups, priority, and threads.

- Assign a batch server to each batch group to spread the load across servers.

- Run heavy batch processes in parallel to save time.

- Use noncontinuous number sequences with preallocation to avoid locking issues.

- Run [cleanup routines and jobs](/dynamics365/fin-ops-core/dev-itpro/sysadmin/cleanuproutines) often to free up space and resources.

- Avoid record-by-record operations. Use set-based operations such as insert\_recordset and update\_recordset where you can.

- Consider how security affects performance. For example, an administrator role performs better than a user with limited access. Test your solution with users who have realistic security settings.

- Use the *Optimization advisor* workspace to find and fix business processes that need improvement.

- Understand how *Priority-based throttling introducing service protection* settings prevent overuse of resources and ensure consistent availability and performance for your solution.

- Prioritize your OData and custom service-based integrations based on your business needs.

### Tools to help you diagnose and improve performance

You can use these tools to find and fix performance issues in your solution:

- Trace Parser: Shows the execution of X++ methods and the call tree, and helps you find performance issues and errors.

- Lifecycle Services Environment Monitoring: Tracks server health metrics and SQL insights.

- Query Store: Reviews expensive SQL queries over time and analyzes the indexes used in queries.

- PerfSDK and Visual Studio load testing: Simulates single-user and multi-user loads and measures performance benchmarks.

- Performance timer: Helps you find out what makes your system slow.

- Optimization advisor: Suggests best practices for module configuration and data cleanup.

## Make customer engagement apps faster

Here are some ways to get more speed from your customer engagement apps solutions:

- Configure before customizing. Use standard application components if you can. Customizations such as plug-ins and JavaScript can affect performance and make upgrades harder.

- Avoid OptionSet attributes in Quick Find searches. They can slow down the search results.

- Stay updated on deprecation announcements to align with the product roadmap.

- Reduce form load JavaScript for a faster form load experience.

- Display only the fields you need in the forms. Too many fields can clutter the user interface and affect performance.

- Design forms and pages to show the most important information first.

- Minimize the number of controls in the command bar or ribbon. Too many controls can affect performance and usability.

- Use collapsed tabs to delay loading content until needed.

- Avoid unsupported customizations such as direct manipulation of the Document Object Model. They can cause errors and compatibility issues.

Use the [Solution Checker](/powerapps/maker/data-platform/use-powerapps-checker) to find and fix potential performance issues in your code and configuration.

In high-throughput scenarios, such as data migrations, follow the guidance in the [Service Protection API Limits documentation](/powerapps/developer/data-platform/api-limits#how-to-maximize-throughput) to increase your throughput.

## What's next?

You've learned why performance optimization is important for your Dynamics 365 solutions and how to apply best practices based on your products. Performance is an ongoing process that requires planning, testing, and monitoring throughout the solution lifecycle. Performance involves tradeoffs, so work closely with your users and stakeholders to understand and meet their expectations.

Good performance starts with good design. Use Dynamics 365 products for their intended purposes and think about the performance implications of your design choices early on. Many performance issues are caused by poor customization, configuration, and design choices. Avoid them by clarifying your requirements and following best practices.

Performance testing is crucial to ensure your solution meets your performance goals during implementation. But performance tests are only useful if they reflect how your solution works in the real world.

Performance issues are hard to solve and can stress your implementation team at critical moments of the project. With the right priority and planning, you can make performance part of your implementation strategy, leading to a more confident launch and greater project success.

## Related information

- [Monitoring and diagnostics tools in Lifecycle Services](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/monitoring-diagnostics)
- [Performance troubleshooting using tools in Lifecycle Services](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/performancetroubleshooting)
- [Work with performance and monitoring tools in finance and operations apps (training)](/learn/modules/performance-monitoring-finance-operations/)
- [Query cookbook](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/querycookbook)
- [Take traces by using Trace parser](/dynamics365/fin-ops-core/dev-itpro/perf-test/trace-trace-tutorial)
- [Diagnose issues and analyze performance by using Trace parser](/dynamics365/fin-ops-core/dev-itpro/perf-test/trace-parser)
- [Performance timer](/dynamics365/fin-ops-core/dev-itpro/perf-test/performance-timer)
- [Query Store Usage Scenarios](/sql/relational-databases/performance/query-store-usage-scenarios)
- [Monitoring performance using the Query Store](/sql/relational-databases/performance/monitoring-performance-by-using-the-query-store)
- [Optimization advisor overview](/dynamics365/fin-ops-core/dev-itpro/sysadmin/optimization-advisor-overview)
- [Cleanup routines in Dynamics 365 Finance and Dynamics 365 Supply Chain Management](/dynamics365/fin-ops-core/dev-itpro/sysadmin/cleanuproutines)
- [Throttling prioritization](/dynamics365/fin-ops-core/dev-itpro/data-entities/priority-based-throttling)
- [Priority-based throttling FAQ](/dynamics365/fin-ops-core/dev-itpro/data-entities/throttling-faq)
- [Performance tuning and optimization](/power-platform/admin/performance-tuning-and-optimization)
- [Optimize model-driven app form performance](/powerapps/maker/model-driven-apps/optimize-form-performance)
- [Tips and best practices to improve canvas app performance](/powerapps/maker/canvas-apps/performance-tips)
- [Introducing Monitor to debug apps and improve performance with Power Apps](https://powerapps.microsoft.com/blog/introducing-monitor-to-debug-apps-and-improve-performance/)
- [Performance considerations with Power Apps](https://powerapps.microsoft.com/blog/performance-considerations-with-powerapps/)

## Next steps

- Request a [FastTrack performance workshop](performing-solution-workshop-strategy.md) to get expert help and guidance on your solution performance
- Use the [checklist: Performance focus](performing-solution-product-checklist.md) to review your solution design and implementation for performance considerations
- Read the [case study](performing-solution-product-case-study.md) of how a customer improved their solution performance with FastTrack support
