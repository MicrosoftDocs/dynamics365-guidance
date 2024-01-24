---
title: Performance testing and optimization case study
description: Learn how an organization found its way to a performance-focused Dynamics 365 solution.
author: TimoGossen
ms.author: timogoss
ms.date: 06/19/2023
ms.topic: overview
ms.custom: bap-template
---

# Performance testing and optimization case study

**A corporate travel company learns that testing is critical to measure and optimize performance**

A global corporate travel company was implementing Dynamics 365 Customer Service to transform its call center. Several process flows required integration with legacy systems, many with high transaction volumes. A specific business requirement couldn't be achieved using out-of-the-box functionality and needed to be customized. This complex solution was projected to support 4,000 users at scale and needed careful planning to deliver optimal performance.

Despite the complex customizations and integrations, leadership had decided performance testing was out of scope due to budget constraints. They assumed that, because Dynamics 365 is a cloud service, Microsoft is responsible for its performance.

While still in the design stage, the project team decided to use the best practices from the Success by Design framework and their own experiences to highlight the risks of skipping performance testing. The team pointed out potential negative outcomes if performance wasn't considered:

- Users wouldn't adopt the system if its performance affected their productivity.
- Costs would be higher if reactive measures were required to address performance issues later.

The project architect worked with the company's stakeholders to explain ownerships. Although Dynamics 365 is a cloud service, factors like customizations, data volumes, and network latencies all play a role in a solution's performance.

The project team summarized their recommendations as follows:

- Review the application design and code for scalability.
- Establish baselines and review the areas that need to be optimized, including network configurations.
  - Formulate a baseline for form load times to understand performance and align a new solution.
  - Make sure performance with integrated systems meets the company's expectations.
  - Agree on realistic key performance indicators for the business.
  - Assess current end-to-end connectivity to determine network performance and latency.

Leadership agreed with the recommendations and advised the project steering committee to approve adding performance testing to the test cycle.

The company's architect worked with the implementation partner's architect to plan for performance testing by:

- Defining the key criteria for testing, including integration scenarios.
- Assessing the concurrent user loads and peak usage.
- Examining the data volumes.
- Establishing the tools for testing.

Performance testing helped the team identify several gaps before deploying the solution to production. In addition, the team:

- Optimized their network configuration.
- Identified sync calls that were blocking resources and made the necessary design changes.
- Reinforced and incorporated basic patterns (such as retrieving only the required attributes) across their code components.

As mentioned in the section [An ounce of prevention](performing-solution-prioritize-performance.md#an-ounce-of-prevention), performance testing ensured optimal performance and stakeholder alignment before the system was made available for users. For overall success and higher levels of adoption, a performance plan is fundamental throughout an application's lifecycle.
