---
title: Choose a global deployment model for Dynamics 365
description: Learn how to choose between a global single-environment or a global multiple-environment deployment model for your Dynamics 365 solution.
author: abunduc-ms
ms.author: abunduc
ms.date: 01/16/2024
ms.topic: concept-article
ms.custom:
  - evergreen
  - ai-seo-date: 01/16/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Choose a global deployment model for Dynamics 365

If you want to deploy a Dynamics 365 solution to users in different locations, you need to choose a global deployment model. A global deployment model is a way of organizing and managing your environments and data across the globe. Two common models are global single-environment and global multiple-environment. Each model has its own benefits and challenges, depending on your requirements and preferences. This article helps you compare and choose the best option for your solution.

We're discussing global deployment models in the context of a single-app deployment. If you're deploying more than one customer engagement app, you must also consider the multiple-app and per-app environment strategies. [Learn more about environment strategy](environment-strategy-guidance-product.md#environment-app-strategy).

## Global single-environment deployment

In a global single-environment deployment, you use one environment with one app that users access from anywhere in the world. All the data, processes, code, and customizations are in one environment. You can manage the access and security of your data based on roles and policies. This is the most common approach, because it enables strong global collaboration and a unified view of data and processes across different regions, business units, and legal entities.

A global single-environment implementation simplifies the deployment and maintenance of your solution. However, you need centralized process governance to ensure that different regions follow a unified process, with minimal deviations. If your processes aren't unified globally, you might need a complex solution that could affect performance and adoption.

You might also need to adjust the security model for each region to meet local regulations and cultural differences around data sharing and collaboration.

Here are some of the pros and cons of a global single-environment deployment.

Pros of a global single-environment deployment:

- Data unification across regions and countries enables greater collaboration and helps standardize processes.
- Settings, updates, configurations, and application lifecycle management (ALM) are easier to manage.
- Costs of storage and integrations are reduced by avoiding duplication.
- Intelligence and reporting architecture are simplified, including master data management.

Cons of a global single-environment deployment:

- Change management and governance could be harder when trying to make a process work for everyone while avoiding political challenges.
- Poor adoption is possible in regions where users aren't engaged or if their requirements aren't prioritized.
- Security model configuration could become complex, as each persona might have a different regional flavor.
- Some regulatory and data residency requirements would be hard to meet in a global single environment, and could slow down change and business agility if the effort isn't well coordinated.
- High network latency for users in different countries or regions can affect performance and adoption.
- Maintenance schedules and downtime are difficult to manage.

## Global multiple-environment deployment

In a global multiple-environment deployment, you use several environments with one app each that users access from different locations. Each environment has its own database, and data isn't shared across environments. This way, you build a physical security layer on top of the logical security layer based on roles and policies. You can separate your environments by region/country, business unit, or other criteria. You can also customize your solutions to meet the local business and compliance requirements of each environment.

If your users are distributed over large distances, especially for global deployments, multiple environments might be more suitable because of network issues, such as latency, that can affect the user experience. Latency is the delay between a user's action and the system's response. High latency can reduce user satisfaction and productivity. By distributing your environments to provide users with more local access, you can reduce or overcome network-related issues, because the access occurs over shorter network connections.

In terms of ALM, you can have a unique solution-release process for each environment, which can support specific business units, departments, and countries/regions. However, this increases the number of environments you need to support the development, testing, and training activities, as each production environment needs its own environment to support the solution-release process.

Because the data isn't unified in a global multiple-environment deployment, the reporting and analytics strategy is more complex. You might need to consolidate your data in a central repository for reporting on key performance indicators (KPIs) and insights about the overall business.

This approach is common when companies have different requirements across subsidiaries, business units, or countries/regions. By creating multiple production environments, you can easily implement specific business requirements and have different teams delivering the solution within different time frames. Each subsidiary, business unit, or country/region operation has control over its own environment.

This model makes it easier for local operations to run and maintain their solutions, but it also increases the costs and might lead to siloed work and deployment.

Here are some of the pros and cons of a global multiple-environment deployment.

Pros of a global multiple-environment deployment:

- Individual environments are only responsible for fulfilling their own requirements, making them simpler and smaller.
- Local administration minimizes language and time-zone barriers.
- Local environments might perform better when closer to the user, reducing latency.
- Compliance with local requirements is easier.
- Data can be physically separated, and there's flexibility in managing data residency.
- Maintenance time windows are easier to adjust.

Cons of a global multiple-environment deployment:

- Data might need to be unified in a central repository for reporting and analytics.
- Data might not be updated across environments or might become specific to each environment.
- It's more costly.
- Users might need to access different environments for different purposes, affecting the user experience.
- Multiple instances must be managed.

## Next steps

- Learn about [environment lifecycle scenarios](environment-strategy-lifecycle-scenarios.md)
- Get [product-specific guidance](environment-strategy-guidance-product.md)
- Follow the [environment strategy checklist](environment-strategy-checklist.md)
- Read a [case study](environment-strategy-case-study.md) of a company that learned the importance of a good environment strategy
