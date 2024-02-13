---
title: Drive expansion of business applications to create greater business impact
description: Learn how expansion can help the business-focused digital transformation.
author: taksatoms
ms.author: tsato
ms.date: 01/11/2024
ms.topic: conceptual
ms.custom:
  - ai-seo-date: 01/11/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
ai-usage: ai-assisted
---

# Drive expansion of business application in business-focused digital transformations

In previous articles, we showed you how to create a digital transformation roadmap for your business applications. You learned how to apply different approaches and techniques in the *Initiate* phase. But you can also use them later to expand your applications. In this article, we focus on how to grow the usage and scope of your business applications in various areas to achieve more business value and impact. We look at how expansion affects these aspects:

- Security and compliance
- Application lifecycle management (ALM)
- Administration and governance
- User readiness and change management
- Environment strategy
- Limits and capacity
- Data and integrations

## Users

One of the most common ways to expand a business solution is to add more users. This might happen when you bring new regions or countries to the same application. Adding users might seem simple, but it can have some challenges. For example, you might need to migrate data on a live system, meet different security and compliance requirements based on the region, or deal with other impacts.

| Security and compliance | ALM | Admin and governance | User readiness and change management | Environment strategy | Limits and capacity | Data and integrations |
|------------------------|------|----------------------|--------------------|-----------------------------------------|---------------------|----------------------------|
| High | Low | Low | Medium-high | Low | Low | Medium
| Potentially high impact based on regional regulations | If the solution remains the same, impact on ALM is minimal | Based on the environment strategy and the creation of additional production environments, you could see medium impact | Full-fledged user change management and readiness effort is required | Creation of a new production environment impacts the environment strategy | Although each user usually comes with their own capacity integration API, capacity, and storage could be impacted | Usually, data migration can be complex on a live system and in case of additional environments, integrations might have to be replicated across environments

## Mobile

Giving users access to multiple devices with offline capabilities can help with adoption. Sometimes, mobile access is part of the initial release; for instance, warehousing systems where workers need to scan goods when they pick them up. Other times, it might be a later update. Most built-in capabilities work in mobile apps, with more optimizations to support the mobile experience. For example, a sales mobile app offers the core features of the sales app with a mobile-friendly interface for field sellers.

| Security and compliance | ALM | Admin and governance | User readiness and change management | Environment strategy | Limits and capacity | Data and integrations |
|------------------------|------|----------------------|--------------------|-----------------------------------------|---------------------|----------------------------|
| High | Low | Low | Medium-high | Low | Low | Medium |
| Potentially high impact based on the regulations and need for mobile device management or mobile application management features | If the solutions remains the same, impact on ALM in minimal | Additional device policies could have an impact | User readiness effort is required to ensure adoption on mobile and account for any variations | Should not have any signficant impact | It should not have any significant impact on user capacity | Custom embedded integrations might require work to make them responsive for mobile consumption |

## Incremental changes

Incremental changes are mainly driven by feedback and change requests from users and the business. These changes help ensure that the application meets the expectations of ongoing improvement and builds on the initial minimum viable product (MVP) to stay relevant. It's still important to evaluate these requests based on the business value and transformation goals.

| Security and compliance | ALM | Admin and governance | User readiness and change management | Environment strategy | Limits and capacity | Data and integrations |
|------------------------|------|----------------------|--------------------|-----------------------------------------|---------------------|----------------------------|
| Low | Low | Low | Medium | Low | Low | Low
| Changes within the approved SaaS service boundaries and data loss prevention policies should have limited security and compliance implications | No major impacts if the solution doesn't have new PaaS components | No expected impact as long as the data boundaries don't change | User readiness effort is required | Usually remains unchanged | Additional integration and app workloads could have some impact | Assuming no integration changes, impact is minimal |

## Feature adoption

As we discussed when talking about change streams, cloud products invest a lot in researching and implementing business capabilities that customers can easily turn on. It's a key benefit of the cloud, and it can play a major role in getting value from your investments. With continuous updates in Dynamics 365, new features are available to customers. A key business as usual activity is to analyze the new features and their technical impact on the existing solution and customizations. You must do this activity with key stakeholders. Most of these feature improvements are available to customers at no extra cost and can help move your application to the innovative or differentiator quadrant.

| Security and compliance | ALM | Admin and governance | User readiness and change management | Environment strategy | Limits and capacity | Data and integrations |
|------------------------|------|----------------------|--------------------|-----------------------------------------|---------------------|----------------------------|
| High | Low | Low | Medium | Low | Low | Medium
| Usually no impact except when connecting to external data sources | No major impact expected | No expected impact as long as the data boundaries don't change | User readiness effort is required to use the new features | No impact | Usually no impact, sometimes features might require additional storage and capacity | Features might generate additional data but shouldn't impact integrations |

## New workloads

Dynamics 365 provides several business applications that are built on the same scalable Power Platform. As users adopt your application, you might find more opportunities to add related workloads that can help eliminate data silos by enabling stronger collaboration and data sharing. For example, if you add a marketing workload to your sales app, the sales team can see which nurture programs their customers are in and invite them to marketing events. Similarly, the accounts payable team can expand and move to a centralized accounts payable processing system. However, new workloads can have a significant impact.

| Security and compliance | ALM | Admin and governance | User readiness and change management | Environment strategy | Limits and capacity | Data and integrations |
|------------------------|------|----------------------|--------------------|-----------------------------------------|---------------------|----------------------------|
| Low-medium | Low-medium | Low-medium | Medium-high | Low-medium | Low-medium | Medium-high |
| This could be medium impact based on the app; core Dynamics 365 apps might have been already approved | App-specific ALM requirements can impact your release and build pipelines | Some apps could require additional admin tasks | User readiness effort is required, but existing users will benefit from a familiar UI | New apps on existing environments won't have a major impact | Additional apps can impact storage and tenant API capacity | Data and integration needs for the new app can have an impact |

## Satellite applications

When you deploy your business application, it covers core use cases and scenarios. Some of them might be relevant only to a specific team, region, or role. In such cases, you can deliver those targeted capabilities through a satellite application. Satellite apps are a good opportunity for user-developed apps and automations that use the data model of the core app. You can also use these apps for testing before adding them to the core app. Regarding the areas of impact, it's important to have strong governance around the data model and avoid creating more data stores that can lead to data fragmentation.

| Security and compliance | ALM | Admin and governance | User readiness and change management | Environment strategy | Limits and capacity | Data and integrations |
|------------------------|------|----------------------|--------------------|-----------------------------------------|---------------------|----------------------------|
| Low-medium | Medium | Medium-high | Medium | Medium-high | Low-medium | Medium |
| If the data flows in accordance with data loss prevention policies, impact should be low | Managing the lifecycle of satellite apps requires changes to existing ALM processes | As the satellite apps grow organically, the appropriate governance policies need to be in place to manage them | User readiness effort is low for citizen-developed community apps, but might require readiness effort if they're adopted more broadly | Depending on the ALM and citizen development strategy, the environment strategy is impacted | Potential impact to capacity; you maya lso need icneses to support the makers and consumers if they're not already covered by existing licenses | You should avoid fragmenting the data with additional apps using their own data stores, but it may be required in some cases

## Integrations

Integrations can play a key role in eliminating data duplication and improving data quality. Most importantly, they reduce the need for users to switch between multiple applications, which prevents context switching. The core integrations should be part of the initial phases and not left to future expansion phases. Even the built-in integrations with productivity applications like Microsoft 365 can boost adoption and make the information seamlessly available across apps while enabling stronger collaboration. However, you need to be careful. Integration can also cause performance issues and increase the overall complexity and cost of maintenance, so you need to use the right patterns and practices.

| Security and compliance | ALM | Admin and governance | User readiness and change management | Environment strategy | Limits and capacity | Data and integrations |
|------------------------|------|----------------------|--------------------|-----------------------------------------|---------------------|----------------------------|
| Medium-high | Medium-high | Medium-high | Low-medium | Low-medium | Medium-high | High |
| Depending on the data flows, additional security approvals may be needed for integration pattern | ALM process could be impacted depending on complexity | Additional monitoring and integration telemetry is needed to support reconciliation of failures | Depending on frontend versus backend integration, the impact and readiness effort could vary | You may need to have stubs or downstream integration environments | Potential impact to API consumption | Expect impact on data movement and make efforts to ensure integrations are built to standard | 

## Aggregation

Aggregation can help consolidate multiple business applications that have a lot of overlap in data and processes into a single application. Aggregation is different from integration. It completely replaces the application and brings the core features into an existing application instead of exchanging or embedding information. For example, a commercial banking sales system could become an aggregator for all nonpersonal banking sales systems.

The cutover approach for old applications is critical. Make sure to avoid parallel usage that can lead to data fragmentation and other aftereffects.

| Security and compliance | ALM | Admin and governance | User readiness and change management | Environment strategy | Limits and capacity | Data and integrations |
|------------------------|------|----------------------|--------------------|-----------------------------------------|---------------------|----------------------------|
| Medium-high | Medium-high | Medium-high | Medium-high | Low | Medium-high | Medium-high
| Level of impact depends on data classification | Existing ALM processes are changed | Admin processes are consolidated | User readiness is required | This will have impact on environment strategy, requiring a potential merge | Additional users and increased data volumes impact capacity | High impact with respect to data alignment and integration consolidation |

## Application standardization

This type of growth is driven by creating a generic application that isn't targeted at a specific process but a host of similar processes. The application could even provide a framework that lets the business onboard itself. This can achieve hyper-scale, where you can broadly categorize hundreds of processes or applications that serve more than one business process.

A general-purpose application allows scale, but it can require more training and user readiness, so you need to do it thoughtfully to be successful.

For example, consider a generic case management system that can handle hundreds of different case processes from different internal business functions that broadly involve similar steps. The business can create a team of resolvers, configure service-level agreements (SLAs), provide email notification templates, and create Microsoft Word or Excel templates to capture nonstandard data. But they can still use the generic app for core case management capabilities. All these actions have important considerations.

| Security and compliance | ALM | Admin and governance | User readiness and change management | Environment strategy | Limits and capacity | Data and integrations |
|------------------------|------|----------------------|--------------------|-----------------------------------------|---------------------|----------------------------|
| Medium-high | Medium -high | Medium-high | Medium-high | Low | Medium-high | Medium-high |
| Once approved for approppriate data classification, more processes shouldn't have an impact | Existing ALM processes shouldn't change for a specific template | There could be process-specific configurations required for each new workload on the template | User readiness is required for each new process | Should have minimal impact | Additional users and increased data volumes impact capacity | There could be an increase in the data generated by each process |

## Pivot

Pivots aren't necessarily expansion, but they can trigger major changes to an application, which could fundamentally change and broaden its scope. For example, a targeted Power Apps app used by a small team could go viral in an organization, and you need to pivot to make it an organization-wide application.

| Security and compliance | ALM | Admin and governance | User readiness and change management | Environment strategy | Limits and capacity | Data and integrations |
|------------------------|------|----------------------|--------------------|-----------------------------------------|---------------------|----------------------------|
| Medium-high | Medium-high | Medium-high | Medium-high | Low | Medium-high | Medium-high |
| Application will need to undergo further scrutiny | Existing ALM processes will potentially change | Admin and governance scope will need to be reevaluated | User readiness might be required | Potential changes to the overall environment strategy | Additional users and increased data volumes will impact capacity | Expect high impact to data and integration based on the pivot |

## Next steps

- To understand the importance of driving app value, review the [overview](drive-app-value.md)
- Learn how Success By Design plays a major role in defining the [approach to digital transformation](drive-app-value-approach-to-digital-transformation.md)
- Embrace the mindset of constant change and learn about considerations for [change streams](drive-app-value-change-streams.md)
- Understand how product features and changes align with strategy by understanding the [transformation map](drive-app-value-transformation-map.md)
- Find out how [phases and increments](drive-app-value-phases-increments.md) play a role in driving app value
- Understand the [minimum viable product strategy](drive-app-value-minimal-viable-product-strategy.md)
- Review the [checklist](drive-app-value-checklist.md) for driving app value
- Read the [case study](drive-app-value-case-study.md) to understand a real customer scenario for driving app value
