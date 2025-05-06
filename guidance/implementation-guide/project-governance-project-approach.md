---
title: How to approach a Dynamics 365 implementation project
description: Learn how to choose and adapt a project approach that suits your Dynamics 365 implementation project and addresses the key processes and controls you need.
author: TimoGossen
ms.author: timogoss
ms.date: 01/23/2024
ms.topic: how-to
ms.custom:
  - ai-seo-date: 01/23/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# How to approach a Dynamics 365 implementation project

Your project approach is more than just your [project implementation methodology](implementation-strategy-choose-methodology.md). It's the set of processes and controls that define how you manage your project scope, resources, changes, tasks, and outcomes. Your project approach should suit the nature and needs of your Dynamics 365 implementation project. It should also address any gaps or risks in your chosen methodology.

## The customer's responsibilities

If you're the customer in the implementation project, you need to consider the wider set of processes required to support your Dynamics 365 implementation. You should identify the areas that are your responsibility to manage and confirm that you have a clear approach and adequate governance for each one.

The areas that are typically excluded from the implementation partner's responsibility vary, but they often include:

- Defining the scope of the project (the to-be business process and system requirements)

- Managing internal project resources and working with wider business teams

- Managing the participation of all relevant business units and roles

- Managing the source data quality for data migration

- Training the internal project team and users

- Validating data, system, and process by nonproject business users, such as user acceptance testing (UAT)

- Defining and validating security and access

- Considering implications on the wider IT enterprise architecture and business processes

- Applying and validating requirements related to relevant regulatory bodies

- Managing cutover

- Managing non-Dynamics 365 systems involved in system integrations

- Communicating within the business and with customers and suppliers

- Managing budget

- Managing business and organizational change

- Addressing nonfunctional requirements such as performance management, system security, and business continuity planning

- Transitioning to an operating support model and other post-operational duties

This list isn't exhaustive. It's an indicator that your project approach needs to cover more functions than what a typical implementation methodology or a commercial contract might cover. Some projects define their overall approach in a project charter or similar document. You should check if your project approach covers all the areas that aren't included in your implementation methodology.

## Waterfall versus agile approaches

One of the common debates about project approach is whether to use waterfall or agile methodologies. Both have their pros and cons. [Learn more at about implementation strategy](implementation-strategy.md). Whichever methodology (or hybrid) you choose, you should identify and record the specific risks that come with it and have a mitigation plan for each one.

For example, if your methodology doesn't include early analysis or a solution blueprint that reflects the whole design scope, your project might struggle, designing and redesigning the solution from sprint to sprint. You might find that the designs in later sprints can't build on the previous sprints because you didn't analyze and consider the high-level design for the whole end-to-end process. This is a risk we see in many agile projects.

Similarly, if your methodology is strictly linear and document-based, you might spend too much time and effort in analysis, design, and coding phases with little exposure to the working solution and feedback on how it performs in the system. This is a risk we see in many waterfall projects.

You need to identify such risks in your chosen methodology and address them in your project approach.

## The right methodology for your project

Sometimes, people assume that a methodology that works well for a custom software development project also works well for a highly configurable Dynamics 365 implementation. Similarly, methodologies that suited on-premises business application implementation with long durations might not suit today's cloud world.

You should consider the different circumstances of a modern business application implementation with Dynamics 365 online:

- You're implementing a cloud-based, packaged software application.

- Most of the activities aren't coding&mdash;they're things like business process design, setup, configuration, data migration, and validation.

- Some critical activities for a Dynamics 365 implementation, such as extracting a fit gap report from a fit-to-standard analysis, aren't covered by generic software development methodologies.

- Dynamics 365 has ever-increasing functionality with powerful configuration options or low-code/no-code options and the ability to use Power Platform in citizen-developer and professional developer modes.

- A significant part of the implementation process involves understanding and configuring business processes and working closely with business users throughout the project lifecycle. Your methodology should support that.

- Although Dynamics 365 allows custom development, your development process should build on or extend the standard business process flows designed in the system.

- Dynamics 365 is a cloud-based business application with regular updates that you should recognize as part of the new way of working.

All these factors (and more) mean that your implementation methodology should be relevant to your Dynamics 365 project.

When you determine what your project approach should address, consider all aspects of your solution build lifecycle. Make any additions, adjustments, or highlights to your standard methodology. Confirm that you have adequate coverage from your project approach for key processes and controls such as:

- Scope definition and solution blueprint
- Testing strategy
- Regular and appropriate reviews by project teams and the business
- Project status analysis and reporting

You might want to define a set of critical processes, deliverables, and controls to ensure you have proper governance for your project&mdash;just as you would for functional and technical requirements.

Once you start implementing your project, it's easy to lose sight of the governance model you agreed on at the start. You should establish regular checkpoints to compare how you're working on the project with what you planned, and take corrective actions as needed.

For example, analyze how a feature or requirement progressed through its lifecycle or how a scope change item was handled. Did they follow the expected process and did your governance model help deliver a fast and good quality result? Taking a regular pulse of the actual implementation of the processes and controls helps keep your project approach relevant and reduces risk.

## Next steps

- Learn how to evaluate and improve the effectiveness of [classic governance structures](project-governance-classic-structures.md), such as change management, risk management, and issue management
- Learn how to apply good governance processes to [key project areas](project-governance-key-project-areas.md)
- Learn how to create a well-structured [project plan](project-governance-project-plan.md) that helps you track and improve your project progress and outcomes
- [Review the main points and takeaways](project-governance-conclusion.md) from this section
- Use the Success by Design [checklist](project-governance-checklist.md) to assess and improve your project governance model and processes
- Read a [case study](project-governance-case-study.md) of how a customer implemented Dynamics 365 with effective project governance
