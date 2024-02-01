---
title: Govern key project areas
description: Learn how to apply good governance processes to key project areas of Dynamics 365 implementations, such as application lifecycle management, test strategies, data migration, integration, cutover, and training strategies.
author: TimoGossen
ms.author: timogoss
ms.date: 01/23/2024
ms.topic: conceptual
ms.custom:
  - ai-seo-date: 01/23/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Govern key project areas

Project governance isn't just about [the classic structures](project-governance-classic-structures.md) of steering groups and reporting. It's also about the key activities that need governance processes in Dynamics 365 implementations. These include application lifecycle management (ALM), test strategies, data migration, integration, cutover, and training strategies.

In this article, we'll discuss each of these key project areas and show you how to apply good governance processes to them. We'll also explain how to align these processes with your project approach and goals.

## Application lifecycle management

Application lifecycle management (ALM) is the process of managing the configuration, data, code, and deployment of your solution across different environments. ALM should match your project methodology and timetable. Otherwise, you might face risks such as mismatched delivery and planning, poor quality and communication between technical and business teams, and delays.

To make your ALM more effective, you should:

- Map your build requirements onto your end-to-end business processes so that nontechnical stakeholders can understand them.
- Track and report your progress in a meaningful way for different audiences.
- Have a clear process for raising and resolving business process questions with the business owners.
- Define and follow best practices for securing and managing your configuration data across environments.

[Learn more about application lifecycle management](application-lifecycle-management.md).

## Test strategy

A test strategy is a plan that defines how you'll test your solution to ensure that it meets the business requirements and quality standards. A test strategy requires a high level of governance because it involves multiple parties, workstreams,
and disciplines. When evaluating your test strategy, consider the following aspects:

- Is your testing strategy proportionate with your project scope and business risks?
- Is the business sufficiently involved in defining the test coverage, cases, and outcomes?
- Is your test strategy aligned with your project approach and plan?
- Are you testing your business processes end-to-end?
- Are you using representative data for different testing phases and types?

[Learn more about testing strategies](testing-strategy.md).

## Data migration

Data migration is the process of moving data from your existing systems to Dynamics 365. Data migration requires governance to ensure that the data is fit for purpose, clean, secure, and timely. When evaluating your data migration strategy, consider the following aspects:

- Do you have the right level of business ownership and oversight on the types and quality of data being selected for migration?
- Do you have a data stewardship process to keep your data clean during and after the project?
- Will your data be transformed correctly so that it's meaningful and useful in Dynamics 365?
- Will your data strategy and plan provide the right type, quantity, and quality of data to the project at the right time for key milestones such as testing, training, mock cutovers, and other data-dependent tasks?
- Does your data migration strategy reflect your cutover strategy so that the mock cutovers or migration dry runs closely resemble the process for data migration at go-live?

Review your data migration strategy from a governance perspective to ensure that it meets the needs of the project and the business.

## Integration

Integration is the process of connecting Dynamics 365 with other systems or applications. Integration requires governance to ensure that the integration is secure, reliable, efficient, and consistent. When evaluating your integration strategy, consider the following aspects:

- Do you understand and manage the business impact on both sides of the integration?
- Have you defined clear contracts for the data exchange with the business needs in mind?
- Have you considered the security and technology implications for the non-Dynamics 365 systems involved in the integration?
- Have you defined and managed nonfunctional requirements such as expected volumes and performance?
- Do you have clear processes to resolve issues that might arise from the other systems in the integration?

## Cutover

Cutover is the process of switching from your previous system to Dynamics 365. Cutover is a time-critical and multi-faceted process that requires coordination from multiple teams. Cutover also requires governance to ensure that it's a business-driven process and not just a technical data migration process. To make your cutover more effective, you should:

- Start preparing for cutover early in your project.
- Define and agree on a related business calendar that sets the right milestones for cutover.
- Consider using an incremental migration approach if you have a short window for shutting down your legacy systems.
- Record and register any changes between the first migration and final cutover.
- Communicate clearly with all stakeholders involved in cutover.

## Reporting and business intelligence

Reporting and business intelligence (BI) are processes that help you get meaningful insights from the data in Dynamics 365. Reporting and BI require governance to ensure that they meet the business needs and expectations. To make your reporting and BI more effective, you should:

- Define your reporting requirements as part of your business process mapping.
- Deliver your reporting requirements as part of the incremental completion of related end-to-end business processes.
- Include reporting requirements in your testing cycles from the earliest stages, not just in user acceptance testing.
- Communicate clearly with all stakeholders involved in reporting.

## Training strategy

Most projects have plans to train at least the project team members and business users. All too often though, training is seen as a lower priority. If any project delays put pressure on timelines or budget, training can be one of the first areas to be compromised. This trade-off between respecting the go-live date and completing the full training plan can be easier to rationalize because the risk of poor training can be seen (without sufficient evidence) as manageable. The worst consequences of poor user training are felt in the operational phase.

To can mitigate this (mostly unintentional) unbalanced trade-off, you should:

- Define and communicate the implications of poor training on project success and operational use.
- Include an assessment of people readiness as part of your business approval of the solution.
- Evaluate the effectiveness of your training, not just its availability.
- Test whether enough people in key roles can perform their critical day-to-day business processes using Dynamics 365.

[Learn how to put together a good training strategy](training-strategy.md).

## Next steps

- Learn how to create a well-structured [project plan](project-governance-project-plan.md) that helps you track and improve your project progress and outcomes
- [Review the main points and takeaways](project-governance-conclusion.md) from this section
- Use the Success by Design [checklist](project-governance-checklist.md) to assess and improve your project governance model
and processes
- Read a [case study](project-governance-case-study.md) of how a customer implemented Dynamics 365 with effective project governance
