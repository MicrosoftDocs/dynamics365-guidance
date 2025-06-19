---
title: Create a support strategy for your Dynamics 365 solution
description: Learn how to plan, design, and run a support model for your Dynamics 365 solution by defining the scope, team, processes, and tools.
author: taksatoms
ms.author: edupont
ms.date: 01/31/2024
ms.topic: concept-article
ms.custom:
  - evergreen
  - ai-seo-date: 01/31/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Create a support strategy for your Dynamics 365 solution

When you launch a new system in your organization, you need to think about how to transition it from a project to a solution. A solution is something that your users rely on and that requires ongoing support&mdash;and providing support requires a support strategy. A support strategy helps you prepare, design, and run a support model for your solution. Organizations that have a support strategy for their Dynamics 365 solutions tend to have happier users, higher adoption rates, and better business outcomes.

If this is your first Dynamics 365 solution, you might not know how to set up an organization, infrastructure, and procedures to support a business application. If you've used Dynamics 365 before, you might have learned some lessons from previous projects. Either way, this article can help you with the key aspects of a support strategy and help you avoid some common pitfalls. It covers how to create a support model through three categories: support scope, support team, and support operations.

## Support scope

The [scope of your support operations](transition-to-support-scope.md) defines what's supported, who supports it, when they support it, and how they support it. You need to answer these questions for every aspect of your solution. This way, you can turn your enterprise architecture, business and IT policies, and business continuity requirements into practical procedures with clear steps that the support team can follow.

You should also document the areas that are specific to Dynamics 365 and your business process requirements in the support organization charter or terms of reference. Include detailed tasks, roles, and standards that are needed to keep the system running well and safely. You should also include how the Dynamics 365 solution can stay updated and evolve with new and improved features. This is important so that the support team can keep the system running smoothly while they work on the next update.

## Support team

Use your support scope to determine the size and shape of the [support organization](transition-to-support-team.md) and build a [support model](transition-to-support-models.md).

We recommend that you check the readiness of your support team and your support processes before the project goes live. Create guidelines to help make sure that the project team hands over the solution to the support team gradually and with practical experience of the system during implementation.

## Support operations

The [support operations](transition-to-support-operations.md) are the tasks that you need to do to support your solution and your business. Some common considerations are:

- **Routine maintenance and service operations.** Consider creating a shared calendar of regular tasks to help make sure that you do them on time and make them visible across the team.

- **Service hours, language, and geography.** Determine the normal hours of operation and consider how to handle service outside these hours, especially for urgent problems, seasonal peaks, and special events like company acquisitions. If your organization is large or multinational, you might have employees who speak different languages and live in different time zones. Consider how to provide a consistent level of service across languages and time zones.

- **SLAs, priorities, and escalations.** Your support team needs to provide some kind of service level agreement (SLA) for different types of support requests. If your SLAs are based on real business needs, they can help you prioritize the right things. Having a formal escalation process with clear criteria helps prevent frustration on slow cases and reduce the impact of any that escalate beyond their true business importance.

- **Tools and access.** Most support teams use some kind of helpdesk software to manage support requests. Many use their existing helpdesk for Dynamics 365 applications. Partner support teams and independent software vendors (ISVs) have their own helpdesk systems. You should consider new internal and external sources of help.

  When a problem is likely to be with standard Dynamics 365, we recommend that you report it to Microsoft using the in-app process. Tracking a support request across multiple technologies and especially across partner organizations requires some planning and possible system configuration so that the internal helpdesk can follow it from start to finish.

  You should define policies and processes to control when partner resources can access your systems and data. Having these policies in place before you need to deal with a high-priority problem avoids delays while leaders review access requests. For example, if your policy allows partners to view only anonymous customer data, have an automated process to copy a version of your production system without customer data to speed up troubleshooting or testing.

## Next steps

- Learn why it's important to define the [support scope](transition-to-support-scope.md)
- Understand key aspects when choosing [support models](transition-to-support-models.md)
- Discover the requirements for [support operations](transition-to-support-operations.md)
- Understand the roles and responsibilities of the [support team](transition-to-support-team.md)
- Review a [checklist](transition-to-support-checklist.md) for implementing your support model
- Read the [case study](service-solution-case-study.md) to understand why you need to develop and audit your support strategy in the cloud world
