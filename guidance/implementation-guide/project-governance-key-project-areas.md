---
title: Key project areas
description: Read about application lifecycle management, test strategies, data migration, integration, cutover, and training strategies as key areas of project governance in Dynamics 365 implementations.
author: TimoGossen
ms.author: timogoss
ms.date: 06/27/2023
ms.topic: conceptual
---

# Key project areas in Dynamics 365 implementation projects

Project governance is often confined to [the classic structures](project-governance-classic-structures.md) of steering groups and reporting. But in Dynamics 365 implementations, we should consider the key activities that must also have governance processes embedded. At Microsoft, we see many projects where the strategies for the project delivery areas have their own processes and disciplines that don't always work in concert with the project approach. We also see projects where the strategies for the more specialized project areas don't benefit the overall project. Often, these areas are managed and driven by specialists with their own processes and internal goals.

It's worth considering what governance is appropriate for these areas to ensure the project (and hence the business) derives the best value. In this article, we discuss the key areas of application lifecycle management (ALM), test strategies, data migration, integration, cutover, and training strategies.

## Application lifecycle management

Does the defined application lifecycle match the project methodology? For example, how will you analyze, define, approve, secure, manage, and distribute the configuration data to the different environments? Is this process also governed by the requirements of the project approach, and will it be designed to meet the expectations of the project timetable? The risks here are that ALM processes are sometimes considered as a technical subject and not rolled into the overall project governance. As a result, there's a mismatch of delivery and project planning.

The build process (configuration, data, code) in a business application can be presented as a complex, technical, and jargon-filled process. Business stakeholders may retreat and let specialists take complete oversight. However, project leadership can get meaningful insight into the (necessarily technical) build process by devising a layer of governance that provides the necessary understanding and helps keep the project on track. For example, ask the following questions:

- Are the build requirements directly mapped onto the end-to-end business processes, so that any discussions related to the requirement can be well understood in that context by nontechnical stakeholders?

- Are the right controls in place so that progress can be tracked and reported in a way that is meaningful outside of the technical teams?

- Do controls exist to make sure the project applies the right quality, standards, and compliance needs?

- Does the project have a practical and efficient method to raise business process questions with the business area owners. Does it have a way for the business to understand the system delivery of a business process?

Learn more about the ALM and build process at [Application lifecycle management](application-lifecycle-management.md).  

## Test strategy

A well-defined test strategy is a key enabler for project success. A high level of governance is required to ensure that the right test strategy is created and implemented, because multiple cross-workstream parties, business departments, IT departments, and disciplines are involved. When evaluating the suitability of the test strategy, in addition to the technical angles, consider how well some governance areas are covered:

- Does the right level of governance exist to ensure that the testing strategy is mapped to, and proportionate with, the project scope and the business risks?

- Is the business sufficiently involved in the test coverage, test case development, and approval of the testing outcomes?

- Is the project approach in line with the test strategy and test planning?

- Does the right governance exist to make sure the business processes are tested end to end?

- Is the data to be used in the various testing phases and test types sufficiently representative to fulfill the test objectives?

- Is the test coverage across the functional and nonfunctional scope adequate to help assure the business of safe and efficient operation in production use?

More details on defining a successful test strategy are in Chapter 14, "Testing strategy."

## Data migration

For data migration, examine the related governance coverage to ensure that this process is well understood at a business level:

- Do you have the right level of business ownership and oversight on the types and quality of data being selected for migration?

- Is a data stewardship process in place to make sure that the cleansed and migrated data is kept clean during the project and in operational use?

- Will the data from the existing source systems be faithfully transformed so that it's still meaningful and fit for purpose in Dynamics 365?

- Will the data strategy and plan provide the right type, quantity, and quality of data to the project at the right time for key milestones such as testing, training, mock cutovers, and other data-dependent tasks throughout the project lifecycle?

- Does the data migration strategy adequately reflect the go live cutover strategy, so the mock cutovers or migration dry runs closely reflect the process for data migration at go live?

Review the data migration strategy from a governance view to ensure the workstream is delivering to the needs of the project and the business and isn't becoming a silo with only technical oversight.

## Integration

A common area missing governance is the management and ownership of non-Dynamics 365 systems involved in the integrations, partly because they tend to be managed by those outside of the project.

Make sure that the business impact on either side of the integration is understood and managed. Confirm that the data exchange contracts are defined with the business needs in mind. Examine if the security and technology implications for the non-Dynamics 365 systems are properly accounted for.

You also need project-level governance on the definition and management of nonfunctional requirements, such as expected volumes and performance, and clear processes to resolve issues that may stem from the other systems in the integration.

## Cutover

The cutover from the previous system to the new Dynamics 365 system is a time-critical and multi-faceted process. It requires coordination from multiple teams for the related tasks to all come together for a go live. You almost certainly need to include business teams that aren't directly part of the project. Therefore, cutover must be shepherded with a deep understanding of the impact on the wider business. Preparation for the cutover needs to start early in the project, and the governance layer ensures that the cutover is a business-driven process and not a purely technical data migration process. For example, early definition and agreement on the related business calendar sets the right milestones for the data migration to work with.

The window for shutting down the legacy systems is typically short, perhaps over a weekend. For some cutover migrations, that window may be too short to complete all the cutover activities, including data migration. In such cases, the project team may perform the data migration as a staggered, incremental migration, starting with slow-moving primary data and frozen transactional data. This leaves a smaller, more manageable remainder to address during the shutdown. This needs careful governance, and the strategy needs to be decided early because the data migration engine needs to be able to deliver incremental data loads. You should also carefully consider what business activities you may need to throttle or perform differently to reduce the number and complexity of changes between the first migration and the final cutover. The changes need to be meticulously recorded and registered (automatically or manually) so that they can be reflected in the final cutover.

## Reporting and business intelligence

Getting meaningful insights from the data in your business applications tends to be one of the primary objectives of such implementations. We often see attention paid to the ambitions on architectural and technical aspects, but less so to the project implementation processes and related governance that would deliver the business needs. During the *Initiate* phase, consider how you design and deliver the specific reporting and BI needs as part of the implementation. Assuming that reporting will somehow be managed towards the end of the *Implement* phase, may result in late discovery of gaps and delays to the project go live. Instead, ensure that the reporting requirements are defined as part of the business process mapping. During the *Implement* phase, make sure that the reporting requirements are being delivered as part of the incremental completion of the related end to end business process. Don't leave the reporting elements to some other phase/stage. When planning your testing cycles, ensure that you include the reporting requirements from the earliest cycles, not just in UAT.

## Training strategy

Most projects have plans to train at least the project team members and business users. All too often though, training is seen as a lower priority. If any project delays put pressure on timelines or budget, training can be one of the first areas to be compromised.

This trade-off between respecting the go-live date and completing the full training plan can be easier for the implementation team to rationalize because the team is aiming for a go live and the risk of poor training can be seen (without sufficient evidence) as manageable. The worst consequences of poor user training are felt in the operational phase.

You can mitigate this (mostly unintentional) unbalanced trade-off with the following actions:

- Clearly defining and communicating the implications on project success in operational use of poor training delivery.

- Ensure that the business approval of the solution includes an assessment of people readiness. This check should be part of the entry criteria into user acceptance testing and the results evaluated as part of the UAT exit criteria and be a meaningful part of the go/no go criteria for production use.

The test for people readiness needs to be meaningful; it should be an evaluation of the effectiveness of the training, and not just that it was made available. The test should be equivalent to assessing whether enough people in key roles can conduct their critical day-to-day business process safely and efficiently using the Dynamics 365 application and related systems.

Find more details on how to put together a good training strategy at [Training strategy](training-strategy.md).

## Next steps

- [Project goals](project-governance-project-goals.md)  
- [Project organization](project-governance-project-organization.md)  
- [Project approach](project-governance-project-approach.md)  
- [Classic structures](project-governance-classic-structures.md)  
- [Project plan](project-governance-project-plan.md)  
- [Conclusion](project-governance-conclusion.md)  
- [Checklist: Project Governance](project-governance-checklist.md)  
- [Case study](project-governance-case-study.md)  
- [Project governance for Dynamics 365 implementation projects](project-governance.md)  
