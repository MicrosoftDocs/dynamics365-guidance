---
title:  Address performance issues
description: Learn how to deal with performance issues in your Dynamics 365 solutions by analyzing root causes, identifying problematic customizations, and taking a risk-averse approach to optimization.
author: TimoGossen
ms.author: timogoss
ms.date: 06/19/2023
ms.topic: conceptual
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:08/28/2023
  - bap-template
---

# Address performance issues

Analyzing and mitigating specific performance problems is beyond the scope of this guidance. However, some broad considerations might help you structure an approach to resolving issues.

## Root cause analysis

When faced with a performance problem, implementation teams sometimes blame certain parts of the system or look for a magical quick fix. This approach often causes more problems than it solves. Teams might make significant changes based on instinct, which degrade performance further or cause regression bugs. It's crucial to understand the root cause of a performance issue in detail before making any changes. It's a time-consuming but necessary process to make sure any optimizations are meaningful. Ideally, the team understands the issue in enough detail to have a reasonably accurate expectation of the differences in performance prior to testing the change.

### Expectations

Performance issues rarely have a single cause. Suboptimal performance is commonly the result of many factors working together, so a single fix is unrealistic. Generally, mitigating a performance issue is an iterative process of applying incremental improvements.

Also, a performance issue in a Dynamics 365 solution doesn't necessarily imply a performance issue in the standard Dynamics 365 application or its underlying infrastructure. Microsoft support teams are available to help with performance issues. However, when a performance issue is isolated to a single environment, investigations typically start by examining anything unique in that environment, such as customizations, rather than the application code or infrastructure.

### Knowledge

Performance issues can be complex and difficult to resolve. It's vital that the implementation team has sufficient knowledge to ask the right questions and analyze issues meaningfully before the solution is deployed.

Since issues can surface after go-live and expiration of any warranty period, it's crucial to transfer knowledge from the implementation team to "business as usual" teams to resolve performance issues.

### Problematic customizations

To identify the source of a performance issue, we recommend that you first assess whether the issue occurs in a specific customization. Many Dynamics 365 customization options can be enabled and disabled. Strategically disabling customizations often helps identify whether the issue is related to a customization, and if so, which one is the source of the issue.

## Proceed with caution

When you identify the root cause of an issue, it's important to take a risk-averse approach to optimization. Performance tweaks can involve complex code changes and have significant risk of regression issues, so it's crucial to proceed with caution.

### Cheap wins

Identify smaller opportunities for performance gains rather than reworking large and complex areas of the system. In some situations, it might be advisable to make many low-risk tweaks. In others, it might be better to make a more complex change and manage the risk. Which approach to take depends entirely on the situation, but it's important that the team agrees on the approach and that the changes are managed carefully.

### One change at a time

Assess the impact of a change as soon as it's made. If multiple optimizations are made at the same time, it's impossible to understand the effect of each change after a performance test run. For example, if two changes are made, and one increases the performance by 10 percent and the other decreases it by 10 percent, the net result is no performance change. By testing the same changes individually, the team can use the performance test results to reject one change and accept the other one.

## Next steps

- [Performance overview](performing-solution.md)  
- [Prioritize performance](performing-solution-prioritize-performance.md)  
- [Design for performance](performing-solution-design-for-performance.md)  
- [Test for performance](performing-solution-performance-testing-approach.md)  
- [Product-specific guidance for performance optimizations](performing-solution-product-specific-guidance.md)  
- [FastTrack performance workshop](performing-solution-workshop-strategy.md)  
- [Checklist: Performance focus](performing-solution-product-checklist.md)  
- [Case study](performing-solution-product-case-study.md)  
