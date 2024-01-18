---
title: Transition to support
description: Learn how to prepare, define, and operate a support model for your Dynamics 365 solution.
author: taksatoms
ms.author: tsato
ms.date: 04/12/2023
ms.topic: conceptual
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:12/11/2023
---

# Transition to support

Before you introduce a new system into your organization, think through all the things that influence how it transitions from being a "project" to becoming a solution that your users depend on and that needs ongoing support. In other words, think about creating a strategy to help you prepare, define, and operate a support model for your solution. Organizations that spend the time and energy to create a support strategy for their Dynamics 365 solutions tend to have happier users, higher adoption rates, and higher-quality business outcomes.

If this is the first Dynamics 365 solution your company has implemented, you might not have experience in setting up an organization, infrastructure, and procedures to support a business application. If you've implemented Dynamics 365 before, you might have learned some lessons about what works and what doesn't. Either way, this article can help you think through the key aspects of a support strategy and help you avoid some common pitfalls. It's organized to explore the process of preparing, defining, and operating a support model through the categories of support scope, support models, and support operations.

## Support scope

Defining the [scope of your support operations](transition-to-support-scope.md) requires answering five questions&mdash;"what," "what in detail," "who," "when," and "how"&dash;for every aspect of your solution. With these answers, you can convert your enterprise architecture, business and IT policies, and business continuity requirements into practical, detailed procedures with reliably repeatable steps that the support team can follow.

You should convert areas that are specific to Dynamics 365 and your business process requirements into the support organization charter or terms of reference. Add detailed definitions of tasks, responsible roles, and expected standards that are needed to keep the system running safely and efficiently. Your definitions should include the means by which the Dynamics 365 solution can stay updated and evolve with additional and improved features. This is important to make sure that the support organization can keep the system running optimally while they work in parallel on the next update.

## Support models

Use your definition of the support scope to determine the shape and size of the [support organization](transition-to-support-team.md) and build a [support model](transition-to-support-models.md).

We encourage you to validate the readiness of your support organization and your support processes before the project goes live. Create guidelines to help make sure that the transition from project to support happens incrementally and through practical experience of the system during implementation.

## Support operations

The kinds of tasks to include in your [support operations](transition-to-support-operations.md) should depend on the solution that you're supporting and the business that it supports. The following sections describe some common considerations.

### Routine maintenance and service operations

Consider creating a shared calendar of regular, periodic tasks to help make sure the tasks are performed when needed and are visible across the team.

### Service hours, language, and geography

Determine the normal hours of operation and consider how to handle out-of-hours service, especially for urgent problems, during seasonal peaks, and during period-end or one-off events like company acquisitions.

Larger organizations, especially multinational ones, might have employees who speak different languages and live in different time zones. Consider how to provide a consistent level of service across the different languages and time zones.

### SLAs, priorities, and escalations

Your support organization needs to provide some form of service level agreement (SLA) for different types of support requests. If your SLAs are based on genuine business criticality, they can help drive the right prioritization.

Establishing a formal escalation procedure with defined criteria helps prevent frustration on slow-moving cases and mitigate the effect of any that escalate beyond their true business impact.

### Tools and access

Most support organizations use some type of helpdesk software to manage support requests. Many continue to use their existing helpdesk for Dynamics 365 applications. Third parties such as partner support organizations and independent software vendors (ISVs) have their own helpdesk systems. You should consider new internal and external resolving authorities.

When a problem is diagnosed as likely to be with standard Dynamics 365, we recommend that you report it to Microsoft using the in-application process. Tracing a support request across multiple technologies and especially across third-party organizations requires some deliberate planning and possible system configuration so that the internal helpdesk can reference it from start to finish.

You should define policies and processes to control when partner resources can access your systems and data. Having these policies in place before you need to deal with a high-priority problem eliminates delays while leaders review requests for access. For example, if your policy allows partners to view only anonymized customer data, have an automated process to copy an anonymized version of your production system to reduce delays in troubleshooting or testing.

## Next steps

- Learn about the importance of defining the [support scope](transition-to-support-scope.md).
- Understand key aspects when deciding on [support models](transition-to-support-models.md).
- Discover the requirements related to [support operations](transition-to-support-operations.md).
- Review a [checklist](transition-to-support-checklist.md) for implementing your support model.
- Read the [case study](service-solution-case-study.md) to understand the need to develop and continually audit your support strategy in the cloud world.
