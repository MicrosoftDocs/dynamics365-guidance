---
title: Case study in performance testing and optimization
description: Learn how a corporate travel company avoided performance issues by testing its Dynamics 365 Customer Service solution before deployment.
author: TimoGossen
ms.author: timogoss
ms.date: 01/29/2024
ms.topic: overview
ms.custom:
 - bap-template
 - ai-seo-date: 01/29/2024
 - ai-gen-docs-bap
 - ai-gen-title
 - ai-gen-desc
content_well_notification: AI-contribution
---

# Case study in performance testing and optimization

A global corporate travel company wanted to transform its call center with Dynamics 365 Customer Service, but its solution was complex. It had many process flows that integrated with legacy systems, some with high transaction volumes. It needed to customize some functionality that wasn't available out of the box. And it expected its solution to support 4,000 users at scale. It had to plan carefully to deliver optimal performance.

## The problem: No budget for performance testing

Company leadership decided that performance testing was out of scope because of budget constraints. They assumed that Microsoft would take care of the performance since Dynamics 365 is a cloud service.

But the project team knew better. They used the best practices from the Success by Design framework and their own experiences to show the risks of skipping performance testing. They warned about possible negative outcomes if they didn't consider performance:

- Users wouldn't adopt the system if it slowed down their work.
- Costs would be higher if they had to fix performance issues later.

The project architect explained to the company's stakeholders who owned what. Dynamics 365 is a cloud service, but factors like customizations, data volumes, and network latencies also affect how a solution performs.

The project team summarized their recommendations like this:

- Review the application design and code for scalability.

- Establish baselines and review the areas that need optimization, including network configurations.

  - Set a baseline for form load times to measure performance and align a new solution.

  - Make sure that integrated systems perform as expected.

  - Agree on realistic key performance indicators for the business.

  - Assess current end-to-end connectivity to determine network performance and latency.

Leadership agreed with the recommendations and asked the project steering committee to approve adding performance testing to the test cycle.

## The solution: Performance testing and optimization

The company's architect worked with the implementation partner's architect to plan for performance testing. They:

- Defined the key criteria for testing, including integration scenarios.
- Assessed the concurrent user loads and peak usage.
- Examined the data volumes.
- Established the tools for testing.

Performance testing helped the team find several gaps before deploying the solution to production. They also:

- Optimized their network configuration.
- Identified sync calls that were blocking resources and changed the design accordingly.
- Applied basic patterns (such as retrieving only the required attributes) across their code components.

Performance testing ensured optimal performance and stakeholder alignment before the system was ready for users. For overall success and higher adoption, a performance plan is essential throughout an application's lifecycle.
