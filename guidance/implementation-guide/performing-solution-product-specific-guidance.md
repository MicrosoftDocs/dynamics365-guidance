---
title:  Product-specific guidance for performance optimizations
description: Learn how to optimize the performance of your Dynamics 365 solutions depending on the apps that are part of the implementation. 
author: TimoGossen
ms.author: timogoss
ms.date: 06/19/2023
ms.topic: conceptual
ms.custom: bap-template
---

# Product-specific guidance for performance optimizations

This article provides guidance for optimizing the performance of your Dynamics 365 solutions depending on the apps that are part of the implementation.

## Finance and operations apps

The following recommendations can help you achieve optimal performance in your finance and operations apps solutions:

- Use Tier-2 or higher environments based on business objectives. Don't use a Tier-1 environment. Learn more at [Cloud deployment overview](/dynamics365/fin-ops-core/dev-itpro/deployment/cloud-deployment-overview).  
- Keep the solution up to date with hotfixes, platform updates, and quality updates. Learn more at [Apply updates to cloud environments
](/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system).  
- Identify and maintain a log of performance-related risks.
- Use [the Dynamics 365 migration framework](/dynamics365/get-started/migration/migration-overview), not OData, to import and export large volumes of data. OData isn't natively built to handle large payloads.
- Use set-based data entities and parallelism to import and export large volumes.
- Build your own data entities to avoid potential performance issues with standard entities, which contain columns and tables that you might not need for your implementation.
- Configure a batch framework including batch groups, priority, and threads.
- Define batch groups and assign a batch server to each batch group to balance batch load across Application Object Servers (AOS) servers.  
- Design heavy batch processes to run in parallel.
- Use preferable noncontinuous number sequences with preallocation.
- [Clean up routines and jobs](/dynamics365/fin-ops-core/dev-itpro/sysadmin/cleanuproutines) regularly.
- Avoid record-by-record operations. Use set-based operations such as insert\_recordset and update\_recordset where applicable.
- Be aware of the implications of security on performance. An administrator role, for instance, has better performance than a user with limited access. Execute performance tests with users who have appropriately configured security settings.
- Use the *Optimization advisor* workspace to identify business processes to be optimized.
- Be aware of *Priority-based throttling introducing service protection* settings that prevent the over-utilization of resources to preserve the system's responsiveness. These settings also make sure of consistent availability and performance for environments running finance and operations apps.
- Configure priorities for the OData and custom service-based integrations, depending on your business-critical need for them.

### Performance tools

- Trace Parser: Diagnoses performance issues and errors and visualizes execution of X++ methods and the execution call tree.
- Lifecycle Services Environment Monitoring: Monitors server health metrics and monitors performance using the SQL insights dashboard
- Query Store: Reviews expensive SQL queries during defined intervals and analyzes the index used in queries
- PerfSDK and Visual Studio load testing: Simulates single-user and multi-user loads and performs comprehensive performance benchmarking
- Performance timer: Helps determine why a system is slow
- Optimization advisor: Suggests best practices for module configuration and identifies obsolete or incorrect business data

## Customer engagement apps

The following recommendations can help you achieve optimal performance in your customer engagement apps solutions:

- Configure before customizing. Achieve a goal by configuring standard application components if possible. Customizations such as plug-ins and JavaScript are useful, but they can carry a performance overhead and can also make future upgrades more challenging.
- Avoid OptionSet attributes in a Quick Find search.
- Stay current on deprecation announcements to align with the product roadmap.
- Reduce form load JavaScript for a better form load experience.
- Display the minimum required number of fields required in the forms.
- Design forms and pages to display the most important information at the top.
- Minimize the number of controls in the command bar or ribbon.
- Use collapsed tabs to defer loading content.
- Avoid unsupported customizations such as direct Document Object Model manipulation.

Use the [Solution Checker](/powerapps/maker/data-platform/use-powerapps-checker) to detect potential performance issues in code and configuration.

In high-throughput scenarios, such as data migrations, follow the guidance in the [Service Protection API Limits documentation](/powerapps/developer/data-platform/api-limits#how-to-maximize-throughput) to maximize throughput.

## Conclusion

The articles in this section discussed why performance is expected and critical for user adoption, the customer experience, and project success. Although Dynamics 365 projects are built to perform well at scale, their flexibility means it's crucial that implementation teams consider performance as an iterative process throughout the solution lifecycle.

Performance often involves tradeoffs, so project teams need to work closely with users and business stakeholders to determine and align performance expectations.

Good solution performance starts with good design. Use Dynamics 365 products for their intended purposes and fully consider the performance implications of design decisions early in the process. Many performance issues occur due to poor customization, configuration, and design choices. It's important to proactively work to avoid such issues by clarifying requirements and implementing best practices.

Performance testing is crucial to ensure performance expectations are achieved during implementation. However, performance tests are valuable only if they're meaningful and provide a clear indication of how the system performs in the real world.

Performance issues are difficult to resolve and place unnecessary strain on the implementation team during the most critical points of the project. With the right prioritization and planning, performance can be baked into the implementation strategy, leading to a much more confident launch with greater project success.

## Related resources

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

- [Performance overview](performing-solution.md)
- [Prioritize performance](performing-solution-prioritize-performance.md)
- [Design for performance](performing-solution-design-for-performance.md)
- [Test for performance](performing-solution-performance-testing-approach.md)
- [Address performance issues](performing-solution-address-performance-issues.md)
- [FastTrack performance workshop](performing-solution-workshop-strategy.md)
- [Checklist: Performance focus](performing-solution-product-checklist.md)
- [Case study](performing-solution-product-case-study.md)
