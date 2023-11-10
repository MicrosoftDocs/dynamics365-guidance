---
title:  Transition to support - support operations
description: This article discusses strategy and consideration when transitioning into the support plan developed by the organization for Dynamics 365 implementation projects.
author: taksatoms
ms.author: tsato
ms.date: 03/30/2023
ms.topic: conceptual
---


# Support operations

The preparation and design work allows you to provide the level of support expected by the business. There are many aspects to consider when planning for the practicalities of operating the support services. Preparation for support is necessary, but not sufficient. The support team also needs to learn and practice to ensure they are ready for the extra pressures of the period immediately following a go live. The next section explores this in more detail.

## Transition

Support organizations for business applications are rarely just appear fully formed on the first day of go live. You normally have a transition period from project mode to support mode. However, the transition period often starts later than it ideally should, and the quality of the transition is often not sufficient to provide the level of service that is expected. This results in poor user experience, frustration from the support team, and a drag on the project team that is called into support requests long after the transition is supposed to be complete.

### What is a good time to start the transition?

Learning a new business application system, even one that is as user-friendly as Dynamics 365, can take time, and actively using the system is one of the best methods. For the business process-related support roles, if the SMEs are expected to move into the support role at go live, training happens naturally as part of the project, assuming the project approach includes a significant amount of hands-on system involvement by the SMEs. It's important that the business process experts don't just become consultants to drive business requirements and have very little exposure to how the system design meets the requirements.

If, however, the existing SMEs supporting the legacy system are expected to support the new system, consider formalizing their involvement in the project during the Implement phase, from the early build steps and especially in shadowing the business functional leaders at critical points in design and software playbacks.

Furthermore, consider involving the support business process roles in the formal testing phases as authors of some of the test cases or in conducting the testing. Other opportunities to get the team to directly experience using the new system can come from creating task recordings and task guides in Dynamics 365 Finance and Supply Chain Management applications, or other forms of training documents.

You can apply a similar approach to the technical roles, they can be involved in shadowing the project team at critical points and be given project tasks to complete (under the supervision of the project team).

Consider setting intermediate targets for transition readiness throughout the project so it doesn't become a last-minute process. It may help to exercise the whole support organization prior to go live and to review the effectiveness of the readiness for supporting the production system. Consider using the formal support processes during the later stages of formal testing (such as UAT) to review readiness. This way, a representative sample of issues raised during this test period can be recorded, triaged, and resolved through the support organization tools and procedures. The project team will be expected to participate as resolving authorities to help train the support team and ensure that issues are addressed in a timely fashion. The learning from this type of exercise can help make the transition more effective than last-minute handover training sessions.

Most organizations run lean support teams, which doesn't offer many opportunities for the team to participate in the transition activities we described without explicitly planning these activities so that the support team gets time away from their day-to-day operational duties to participate fully during the project implementation.

> [!TIP]
> If the SMEs aren't being exposed regularly and extensively to the system during its build, a gap will likely appear in their understanding and ability to support, which means increased reliance on the partner functional consultants for support (and testing).

## Requirements management

When the application is in production, it doesn't mean that the system solution can now be considered static for the next few years. The solution will need to deal with new requirements for several reasons:

- Some projects implement a minimum viable product (MVP) on their first go live with the goal to incrementally add the lower-priority requirements over time

- Some projects have planned multiple rollouts that may impact the already live areas

- Some changes to Dynamics 365 are driven by changes in connected systems in the enterprise

- Businesses need to react to the changing world around them

- In a modern cloud SaaS world, incremental functional and technical updates from Microsoft and ISVs help keep the customer's solution secure and updated

Some organizations will continue to have a project team that is responsible for reviewing, prioritizing, and delivering the backlog, but many won't have a standing project team, or the project team will be purely focused on the next rollout.

In such cases, the support organization needs to have the resources and means to keep the solution up to date for the users currently using the live system.

In any case, the support teams are often at the front line of the feedback and requests for new requirements. At the very least, they need a way to capture and channel the new and emerging requirements to the right parties.

## Change management

We saw in the previous section that the solution is unlikely to remain static for long, and the solution functionality can change because of new and backlog requirements.

However, support teams may need to accommodate other sources of change in the production system, such as the following:

- Core data changes (new customers, suppliers, items as part of normal business operations)

- System parameter changes (such as in response to the growing volume of data)

- Configuration changes (such as in response to regulatory changes)

- Approval process changes in the system (such as in response to internal policy changes)

- Bug fixes

Some of these changes can be made within the agreed change control process enforced and facilitated by the system itself. In other cases, proposed changes need to be reviewed, prioritized, and approved by business or IT stakeholders and any other relevant parties.

This process should be considered as part of defining the scope of the support teams' responsibilities. It should also prompt the organization to create the appropriate change management boards for changes to the system in operational mode.

## Hypercare

Most projects define a short period of time after go live in which additional resources and extraordinary attention are given to supporting the business. This hypercare period is necessary to ensure that the business can operate within acceptable thresholds while addressing any initial growing pains with a new system and new business processes.

The role of the support team during this period is critical, and it's important that the expectations are clearly set out and agreed with all parties:

- Define a clear exit strategy for the end of the hypercare period based on meeting explicit criteria. For example, criteria might include no open P1 issues without an acceptable action plan, key business processes are operating at an acceptable efficiency rate, over 90 percent SLA targets being met for P1 and P2 support requests, or the support team can resolve over 95 percent of support requests without using resources reserved for hypercare only.

- Decide on an end date for the hypercare period and have an action plan in place to meet the exit criteria.

- Define expectations and an explicit plan for the project team (and partner resources) during the hypercare period so you can get reliable help from the team. Otherwise, you may find that the project team is committed to working on the next phase of the project and will resist being drawn into support issues.

- Make sure the support team gets the necessary documentation and top-up training from the project team and implementation partner during the hypercare period.

## Next steps

- Review how to construct a strategy to help you prepare, define, and operate a support model in the section [overview](transition-to-support.md)
- Learn about the importance of defining the [support scope](transition-to-support-scope.md)
- Understand key aspects when deciding on [support models](transition-to-support-models.md)
- Review the [checklist](transition-to-support-checklist.md) to help with implementing your support model
- Read the [case study](service-solution-case-study.md) to understand the need to develop and continually audit an organization's support strategy in the cloud world