---
title:  Global deployment scenarios
description: This section focuses on two common app-deployment models that can help you find the best option for your Dynamics 365 deployment. The article covers the tradeoffs, pros, and cons when choosing one approach over the other.
author: abunduc-ms
ms.author: abunduc
ms.date: 04/12/2023
ms.topic: conceptual

---

# Global deployment scenarios

This article focuses on two common app-deployment models that can help you find the best option for your deployment of a solution with Dynamics 365. The article covers the tradeoffs, pros, and cons when choosing one approach over the other.  

We're discussing global deployment scenarios in the context of a single-app deployment. If you're deploying more than one customer engagement app, you must carefully consider these factors in coordination with the multiple-app and per-app environment strategies. Learn more in the [Environment app strategy](environment-strategy-guidance-product.md#environment-app-strategy) section.

## Global single-environment implementation

A global single-environment implementation is just one environment with an app that users access across the globe. All the data, processes, code, customizations reside in a single environment. Based on the app's security requirements and regional data-sharing policies, your organization will have to manage access via security roles. It's the most common approach, because it enables strong global collaboration and a unified view of data and processes across different regions, business units, and legal entities.

A global single-environment implementation simplifies deployment and maintenance of the solution. However, you need centralized process governance to ensure that different regions conform to a unified process, with deviations kept to a minimum. If processes aren't unified globally, handling region-specific requirements will require a complex solution, likely with poor performance, which ultimately will affect usage and adoption.

Your organization might have to adjust the security model for each region to meet local regulations and accommodate cultural differences around sharing and collaboration.

Let's examine some of the pros and cons of a global single environment.

### Pros of a global single-environment implementation

- Data unification across regions and countries enables greater collaboration and helps standardize processes

- Settings, updates, configurations, and application lifecycle management (ALM) are easier to manage

- Costs of storage and integrations are reduced by avoiding duplication

- Intelligence and reporting architecture are simplified, including master data management  

### Cons of a global single-environment implementation

- Change management and governance could be harder when trying to make a process work for everyone while avoiding political challenges

- Poor adoption is possible in regions where users aren't engaged or if their requirements aren't prioritized

- Security model configuration could become complex, as each persona might have a different regional flavor

- Some regulatory and data-residency requirements would be hard to meet in a global single environment, and could slow down change and business agility if the effort isn't well coordinated

- High network latency for users in different countries or regions can affect performance and adoption

- Maintenance schedules and downtime are difficult to manage

## Global multiple-environment implementation

Multiple-environment scenarios support different business units, departments, teams, countries/regions, or other structures inside an organization.

Each environment has its own database, and data isn't shared across environments. This way, we build a physical security aspect on top of logical, out-of-the-box security based on security roles. In separating environments by region or country, solutions included in each environment can support local business and compliance requirements.

If users are distributed over large distances, particularly for global deployments, multiple environments may be more suitable because of the implications (such as latency) associated with the connection infrastructure, which can significantly affect the user experience. Distributing environments to provide users with more local access can reduce or overcome network-related issues, as the access occurs over shorter network connections. For example, with [Dynamics 365 Commerce](/dynamics365/commerce/commerce-architecture), organizations can deploy regional Commerce Cloud Scale Units to provide better latency to store and e-commerce users. Cloud Scale Units also enable elastic scale and easier ALM processes.

In terms of ALM, the solution-release process can be unique for each environment, which will support specific business units, departments, and countries/regions. However, it will increase the number of environments needed to support development, testing, and training activities, as each production environment needs its own environment to support the solution-release process.

Because the data isn't unified in a global multiple-environment setup, the reporting and analytics strategy is more complex, and typically there needs to be a data-consolidation exercise for reporting on key performance indicators (KPIs) and insights about the overall business.

This approach is common when companies have different requirements across subsidiaries, business units, or countries/regions. By creating multiple production environments, it's possible to easily implement specific business requirements and have different teams delivering the solution within different time frames. Each subsidiary, business unit, or country/region operation has control over its own environment.

This model makes it easier for local operations to run and maintain their solutions, but it also increases the costs, and may lead to siloed work and deployment.

Let's examine some of the pros and cons of a global multiple-environment implementation.

### Pros of a global multiple-environment implementation

- Individual environments are only responsible for fulfilling their own requirements, making them simpler and smaller

- Local administration minimizes language and time-zone barriers

- Local environments may perform better when closer to the end user, reducing latency

- Compliance with local requirements is easier

- Data can be physically separated, and there's flexibility in managing data residency

- Maintenance time windows are easier to adjust

### Cons of a global multiple-environment implementation

- Data may need to be unified in a central repository for reporting and analytics

- Data may not be updated across environments or may become specific to each environment

- It's more costly

- Users may need to access different environments for different purposes, affecting the user experience

- Multiple instances must be managed

<!-- Not applicable anymore>
### Hub-and-spoke model

A hub-and-spoke model (Figure 9-7) depicts the company's core unified business solution as the hub. The core is then distributed and extended by the subsidiaries, business units, or country/region operations, which are depicted as spokes.

The hub-and-spoke model could be a variation of the multiple-environment model where each of the regions have an independent environment, but share the core data model.

Alternatively, this could also be achieved with multiple apps in a single environment, where each region is able to independently manage the variations.
<!-->

## Next steps

- Review recommendations for Azure Active Directory at [Tenant strategy](environment-strategy-tenant-strategy.md)  
- Find a checklist at [Environment strategy checklist](environment-strategy-checklist.md)  
- Get an overview at [Environment strategy](environment-strategy-overview.md)  
