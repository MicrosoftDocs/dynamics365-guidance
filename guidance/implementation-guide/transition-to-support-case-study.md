---
title: Transition to support - Case study
description: This article provides a case study for how to transition to support at the end of an implementation of Dynamics 365.
author: taksatoms
ms.author: tsato
ms.date: 04/11/2023
ms.topic: conceptual
---

# Case study for transitioning to support

This article is a story in two acts. Over the last few years, IT project implementation methodologies have been changing to try to keep pace with the speed of innovation of software in the cloud, especially Dynamics 365 applications. IT organizations within businesses have similarly been evolving as the cloud is changing the role and areas of responsibility for IT.

The following case study is an illustration of the dangers of assuming that an existing, well-functioning support model will continue to perform well in a different architecture and with changed business processes in new applications, without deliberate planning and action. This is doubly true in a cloud world.

## Act I: The journey of learning

This is a story of a medium-sized organization (fewer than 1,000 employees) with multiple offices across three European countries/regions and their corporate headquarters in the UK. Their core business includes professional services, field services, and bulk distribution from their own warehouses.

The group was undergoing rapid business growth. To support and accelerate this growth, they chose to replace several specialist local applications and multiple on-premises ERP and CRM systems with Dynamics 365 Finance, Dynamics 365 Supply Chain Management, and Dynamics 365 customer engagement apps applications across the enterprise. They planned their first rollout to locations in two countries/regions that had significant interdependency (accounting for approximately 15 percent of their business) and to the other businesses incrementally, as part of the next phases of the project. Subsequent phases would also include additional functionality related to Human Resources, Payroll, the Customer Service Center, and shared services on contract management.

The existing support teams were fragmented across various systems, and sometimes also by business unit. These multiple support teams were planned to be organized under a unitary structure in IT before the transition to Dynamics 365. All support activities and teams were planned to be managed by a director of support services, and who would report to the CIO.

The project was planned to go live approximately 10 months after project initiation. At the exit criteria review of the Initiate phase, they identified the following:

- The to-be end-to-end business process flow diagrams and description were adequate in most areas.

- The solution blueprint document was judged to be sufficiently well-defined to confirm the scope of the overall design.

- Budgets and project resources to complete the project were revised and approved in light of the latest solution blueprint and project plan. The project scope and go-live date had been reviewed and reconfirmed by the steering group.

- In readiness for the implementation of enterprise-wide Dynamics 365 applications, the ambition was for the support team to be reorganized by main business areas: Finance, Sales and Marketing, Operations, Field Service, Warehouse and Shipping, IT business application, and IT servicing, rather than by legacy system. However, in reality, the teams continued to be tied to the legacy systems they had existing expertise in supporting.

There was an informal understanding that the support team would be trained during the project. However, during the Implement phase, the project team stated that they were behind schedule and too focused on project delivery to help educate the support team. The mitigation plan was for the support team to be part of an extended, one-week training and hand-off period after UAT was complete.

As the implementation progressed, the support organization continued to focus on the day-to-day needs of the currently operating legacy systems. There was a general feeling in the project and in the support organization leadership that the risk was low because the existing support team was experienced and some of the project's SMEs would join the support team, thereby seeding knowledge into the team. The underlying assumption was that the support team would be able to pick up the new duties without too much fuss, given that they had been working in a support role for a few years.

During the Prepare phase, when some members of the support team were asked to assist with the testing, the team didn't feel ready to participate until they had been through the training, which was scheduled after the testing. The project SMEs didn't feel they could conduct the internal training because they also had very little hands-on experience in the working system.

When UAT was complete, the project team had other unplanned activities that were considered to be higher priority, and so the training and handover to the support team was reduced to two days.

The go live went ahead on schedule, but the support team struggled to adequately support the business. The initial assumptions that the support team would just pick up the new system support were found to be mistaken, because the underlying processes had also undergone significant changes. The support team hadn't been informed about all the business process decisions and weren't familiar with the new control and approval requirements configured in the Dynamics 365 application. The shortened training and handover were conducted without reference to the significantly changed business processes or to the new enterprise architecture, so didn't provide the necessary context to support a production system.

The support operating model had been revised, in theory, from the distributed, system-level team structure to be more business process and enterprise IT-based, but it wasn't exercised during the Implement or Prepare phase; the gaps and deficiencies were only exposed once the teams had to operate in production. The new operating model had also not adequately considered the implications of changed requirements of the new business processes, architecture, and policies.

In the previous support operating model, all queries and issues came directly (and with little structure) to an individual support team member, and the full lifecycle of the issue was performed with little external visibility. In the enterprise-level support, even with the first limited rollout, the support team was receiving large numbers of administrative queries, which reduced time to address the more business-critical tickets.

The team was also forced to revise IT servicing procedures to reflect the new technology implications in a cloud-based SaaS model. They had to revise policies related to data retention and backups because processes based on the legacy, bespoke on-premises processes weren't reviewed and updated for the new cloud-based SaaS architecture.

The project team had planned to start working full-time on the next phase of the project after only two weeks of hypercare. The budget hours for the implementation partner hypercare support were planned to last four to six weeks, but were exhausted within two weeks or so because the support team needed far more of their time. Many SLAs were missed in the early weeks, and the business was forced to formally extend the hypercare period for both the project team and the implementation partner because trying to get the timely attention of the implementation teams was difficult given that they had other planned priorities for the next project phase.

After the P1 and P2 support tickets were resolved and the volume of new tickets was down to a manageable level, the post-go live retrospective review made the following key recommendations to be enacted as soon as possible, to improve the support outcomes during the next rollout phase:

- The scope of the activities, tasks, and actions expected from the support team should be explicitly defined, in the context of the new system, processes, people, and architecture.

- The support operating model needs to have a more formal definition of the different level of support and a clearer agreement on the expectations from third parties. For example, using tools such as Microsoft Teams channels where super users can help address the higher-volume, simpler questions quickly. The super users would also help to better formulate issues and questions that needed to be addressed by the next support level.

- The support team needs to be formally allocated time to be involved in the implementation project to ensure their learning is sufficiently deep and is embedded in the new process and architectural context to be usable in production. The transition should not rely solely on a last-minute, half-hearted handover.

- The transition should be formally planned within the project plan with specific tasks (such as process design reviews and test case preparation) so the team has sustained and multiple opportunities to have hands-on experience of the developing system.

## Act II: Fewer problems = shorter story

These recommendations were approved by the stakeholders and enacted over the following months. Even though the next rollout (six months later) had a much larger user base, it was a much smoother operation with a shorter hypercare period, higher user satisfaction, and markedly less cost than the first go live.

This story exemplifies the adage "Poor service is always more expensive than good service."
