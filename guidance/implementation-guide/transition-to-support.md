---
title:  Transition to support
description: This article is organized to reflect the journey of preparing, defining, and operating support through the categories of support scope, support models, and support operations.
author: taksatoms
ms.author: tsato
ms.date: 04/12/2023
ms.topic: conceptual
---

# Transition to support

When introducing a new system into an organization, we need to think through the various areas that will influence how the project transitions from project mode to support mode.

In this section, we discuss how to construct a strategy to help you prepare, define, and operate a support model.

Organizations that spend the necessary time and energy to construct a strategy that explicitly addresses how to create a fit-for-purpose support organization for their Dynamics 365 application tend to have better user satisfaction, better adoption of the system, and therefore higher-quality outcomes for the business.

If this is the first Dynamics 365 business application for your company, you may not have experience in setting up the support organization, support infrastructure, and support procedures for this application. Establishing a support organization for a new system (for example, Dynamics 365) needs more due diligence and may require a different perspective that better reflects the new technologies and new ways of working that come with it.

This article is organized to reflect the journey of preparing, defining, and operating support through the categories of support scope, support models, and support operations.

During operational use of the Dynamics 365 system, the support operations are expected to function efficiently and evolve alongside the expanding use of the system. For that to happen smoothly, the preparation and definition of the support operating model are essential precursors.

## Support scope

The sections in [this article](transition-to-support-scope.md) are designed to help define the potential scope of support operations; you need to convert each of the areas covered from the "what" to the "what in detail," "who," "when," and "how."

You should convert the enterprise architecture alongside the business and IT policies and business continuity requirements into practical reference architecture and detailed procedures with reliably repeatable steps that the support team can implement day to day.

You should convert the Dynamics 365-specific areas and business process requirements into the support organization charter or terms of reference with a further detailed definition of the tasks, the roles responsible, and the standards expected to keep the system operating safely and efficiently.

Use the system update cycles section, including managing new requirements and changes, to define the means by which the Dynamics solution can stay updated and evolve with the additional and improved features. This should deliver a detailed definition of the tasks, the roles responsible, and the standards expected to continuously improve the business value from the Dynamics 365 system. This is important to ensure that the support organization can keep the current operational system functioning optimally while also working in parallel on the next update.

## Support models

The sections discussing [the support model](transition-to-support-models.md) and [support organization](transition-to-support-team.md) should help take the definition of the support operations scope and use the chosen support model to create the shape and size of the support organization. This resulting design should be a good fit for the requirements of support operations.

Finally, transition guidelines can help you make sure that the transition from project to support happens incrementally and through practical experience of the system during implementation. We also encourage you to validate the readiness of your support processes and organization prior to go live.

## Support operations

The nature and details of the support tasks are influenced by the specifics of the business application because they are so embedded in the core business. The details of the [support operations](transition-to-support-operations.md) are further affected by the details of the circumstances of the business being supported. We discuss some of the circumstances next.

### Routine maintenance and service operations

Consider defining a support and servicing shared calendar that lists the regular, periodic tasks. This can help make sure those tasks are reliably implemented and have the right visibility across the team.

### Service hours, language, and geography

In addition to defining the normal hours of operation, consider how to define out-of-hours service, especially for urgent issues.

Some larger organizations, especially multi-national ones, may need to provide support in multiple languages and across multiple time zones based on the geography of the users.

Furthermore, consider business-critical periods when support may need to provide out-of-hours support; for example, during seasonal peaks or period-end or one-off events such as company acquisitions.

All of these topics have a bearing on the operational patterns that the team needs to support.

### SLAs, priorities, and escalations

Support organizations need to provide some form of SLA for the different types of support request, if these terms are based on genuine business criticality, they will help drive the right prioritization.

Establishing a formal escalation procedure with defined criteria will also help prevent frustration on slow-moving cases and help mitigate the impact of those that escalate issues beyond their true business impact.

### Tools and access

Most support organizations have some type of internal helpdesk software that is used to manage support requests across all IT services. Most continue using their existing helpdesk for Dynamics 365 applications but need to consider new internal and external resolving authorities. Third parties such as partner support organizations and ISVs have their own helpdesk systems. When the issue is diagnosed as likely to be in standard Dynamics 365, the recommended method of registering the issue with Microsoft is to use the in-application process: Dynamics 365 Finance and Supply Chain Management Support and Dynamics 365 CE Power Platform Support. Tracing a support request across multiple technologies and especially across third-party organizations requires some deliberate planning and possible configuration so that the internal helpdesk has a reference from start to finish of any ticket.

Policies on access for partner resources to the customer systems and customer data need to be defined as part of the support organization so that there are no delays in the middle of dealing with high-priority issues while policies are reviewed, and special approvals are obtained.

For example, if the policy only allows for partners to view anonymized customer data, having an automated way to copy the production system that includes anonymization will help reduce delays when troubleshooting or testing.

## Next steps

- Learn about the importance of defining the [support scope](transition-to-support-scope.md)
- Understand key aspects when deciding on [support models](transition-to-support-models.md)
- Uncover the requirements related to [support operations](transition-to-support-operations.md)
- Review the [checklist](transition-to-support-checklist.md) to help with implementing your support model
- Read the [case study](service-solution-case-study.md) to understand the need to develop and continually audit an organization's support strategy in the cloud world  
