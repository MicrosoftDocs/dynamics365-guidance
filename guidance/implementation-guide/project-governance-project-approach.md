---
title: Project approach 
description: Find best practices for how to approach an implementation project with Dynamics 365 apps.
author: TimoGossen
ms.author: timogoss
ms.date: 06/27/2023
ms.topic: conceptual
---
# Project approach for Dynamics 365 implementation projects

When we talk about project approach, we risk making it sound like it's the same as the [project implementation methodology](implementation-strategy-choose-methodology.md). It's a risk of a vacuum in the processes that must be defined outside of the implementation methodology. It's especially true if the implementation partner provides a limited, technical implementation methodology.  

## The customer's responsibilities

If you're the customer in the implementation project, consider the wider set of processes required to define your project scope, manage your resources, and manage the changes, tasks, and processes. Prioritize areas that aren't directly covered by the partner but are necessary for every business to perform in support of a business application implementation. You should explicitly identify areas that would be the responsibility of the customer to manage. Then confirm that you have adequate definition of the approach and the right level of governance planned for each of these areas.

The areas excluded from the implementation partner's responsibility varies. The following areas are typically involved:

- Defining the scope of the project (the to-be business process and system requirements)

- Managing internal project resources and liaising with wider business teams

- Managing the process for the proper participation of all the relevant business units and roles

- Managing the source data quality for data migration

- Training the internal project team and the end users

- Data, system, and process validation by the nonproject business users, such as user acceptance testing (UAT)

- Security and access definition and validation

- Implications on the wider IT enterprise architecture and wider business processes

- Interpreting, applying, and validating the requirements related to relevant regulatory bodies

- Cutover management

- Managing the non-Dynamics 365 systems involved in system integrations

- Managing communication within the business and with customers and suppliers

- Budget management

- Business and organizational change management

- Nonfunctional requirements such as performance management, system security, and business continuity planning

- Transitioning and operating the support model and other post-operational duties

This list isn't intended as an exhaustive list. It's an indicator that the overall project approach needs to consider a wider set of functions than what may be covered by a typical implementation methodology or a commercial contract. Some projects define the overall approach in a project charter or similar document. You should examine if the project approach adequately covers the missing areas from the implementation methodology.

## Waterfall and agile approaches

One of the discussions that regularly occurs about project approach is the debate on waterfall versus agile. Methodologies based on either of these principles have their advantages and disadvantages. Learn more at [Implementation strategy](implementation-strategy.md). From a project approach perspective, whichever methodology (or hybrid) you adopt, you must identify and record the specific risks that emerge from that methodology and have a mitigation plan for each one.

For example, let's say your chosen methodology doesn't include early analysis, nor a solution blueprint that reflects the whole design scope. In that case, the project may stumble from sprint to sprint, designing and redesigning the solution. Maybe you find that the designs in later sprints can't be built on the previous sprints because you didn't analyze and consider the high-level design for the whole end-to-end process. At Microsoft, we've seen projects fail because the methodology was purely agile and didn't include a solution design blueprint.

Similarly, if the chosen methodology is strictly linear and mostly document-based, you risk spending an enormous amount of time and effort in analysis, design, and coding phases with little exposure to the working solution and limited feedback on how the solution performs in the system. This is a risk we see in many pure waterfall projects. You need to identify such risks in your chosen methodology so you can discuss, accept, understand, and specifically address them in the project approach.

## The right methodology for the specific project

Sometimes, people assume that a methodology that works well for a bespoke software development project also applies to a highly configurable Dynamics 365 implementation. Similarly, methodologies that suited the old world of on-premises business application implementation with long implementation durations aren't best adapted to today's more rapidly evolving cloud world.  

Consider the different circumstances of a modern business application implementation with Dynamics 365 online:

- The implementation is for a cloud-based, packaged software application

- A significant (if not a majority) of the activities aren't coding, but business process design, setup, configuration, data migration, validation, and more

- Some critical activities for a Dynamics 365 application implementation (such as extracting a fit gap report from a fit-to-standard analysis) aren't covered by more generic software development implementation methodologies

- There's ever-increasing functionality in the Dynamics 365 business application of powerful configuration options or low-code/no-code options and the ability to use the Dynamics 365 Power Platform in citizen-developer and professional developer modes

- A significant part of the implementation process revolves around the understanding and configuration of business processes and working closely with business users throughout the project lifecycle. The methodology must support that fact.  

- Although Dynamics 365 applications provide a platform for custom development, the chosen methodology must address the fact that the development process is building on, or extending, the standard business process flows designed in the system

- Dynamics 365 applications are cloud-based business applications with a regular update rhythm that you should recognize as part of the new way of working

All of these factors (and more) mean that the implementation methodology needs to be directly relevant to the nature and needs of a Dynamics 365 business application project.

When looking to determine what the overall project approach should address, consider the specifics of your whole project solution build lifecycle. Make any additions, adjustments, or highlights to the standard methodology. Confirm that the key processes and controls you expect are adequately addressed as part of the governance of the project:

- Does the methodology and approach enable a good definition of the scope and a solution blueprint?

- Is the testing strategy fit for purpose?

- Do controls such as regular and appropriate reviews by the project team and the business exist?

- Is a good process for project status analysis and reporting in place?

You may want to define a set of critical processes, deliverables, and controls to ensure you have the right coverage from the project approach (just as you would for functional and technical requirements).

Once you are in project implementation mode, and the focus is on day-to-day tasks, it's easy to lose sight of the ideals agreed in the governance model at the start of the project. You should establish regular checkpoints to go through the formal discipline of honestly comparing the actual ways of working on the project with the governance model and taking corrective actions as necessary.

For example, analyze a random sample of how a given feature, requirement, or user story actually progressed through the lifecycle. Alternatively, trace how a scope change item was handled to resolution. Did they progress through their lifecycle as you expected, and did your governance model help deliver a fast and good quality result? Taking a (preferably independent) regular pulse of the real, practical implementation of the processes and controls helps keep the project approach relevant and reduces risk.

## Next steps

- [Project goals](project-governance-project-goals.md)  
- [Project organization](project-governance-project-organization.md)  
- [Classic structures](project-governance-classic-structures.md)  
- [Key project areas](project-governance-key-project-areas.md)  
- [Project plan](project-governance-project-plan.md)  
- [Conclusion](project-governance-conclusion.md)  
- [Checklist: Project Governance](project-governance-checklist.md)  
- [Case study](project-governance-case-study.md)  
- [Project governance for Dynamics 365 implementation projects](project-governance.md)  
