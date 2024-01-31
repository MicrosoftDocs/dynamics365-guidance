---
title: Use the go-live checklist to make sure your solution is ready for go-live
description: Learn how to use the go-live checklist to ensure that your Microsoft Dynamics 365 solution meets your business needs and works as expected before you launch it.
ms.date: 01/30/2024
ms.topic: conceptual
author: vaniusca
ms.author: vaniaf
ms.custom:
 - ai-seo-date: 01/30/2024
 - ai-gen-docs-bap
 - ai-gen-title
 - ai-gen-desc
 - bap-template
content_well_notification: AI-contribution
---

# Use the go-live checklist to make sure your solution is ready for go-live

Before you launch your Microsoft Dynamics 365 solution, you need to make sure that it meets your business needs and works as expected. The go-live checklist helps you assess the readiness, completeness, and quality of your solution and make informed decisions about going live.

The checklist covers the following areas:

- [Go-live readiness](#go-live-readiness)
- [Cutover](#cutover)
- [Solution scope review](#solution-scope-review)
- [Solution acceptance review](#solution-acceptance-review)
- [User acceptance test completion](#user-acceptance-test-completion)
- [Performance testing completion](#performance-testing-completion)
- [System integration testing completion](#system-integration-testing-completion)
- [Data migration readiness and validation](#data-migration-readiness-and-validation)
- [Confirmation of external dependencies](#confirmation-of-external-dependencies)
- [Change management for initial operations readiness](#change-management-for-initial-operations-readiness)
- [Operational support readiness](#operational-support-readiness)

## Go-live readiness

| Done? | Task |
| :---: | --- |
| &check; | Align the solution scope with the solution that's going live, share it with stakeholders, and get their agreement. |
| &check; | Complete all test cycles with exit criteria met and signed off by the business stakeholders. The recommended test cycles include system integration, performance, user acceptance, and other tests. |
| &check; | Test and sign off on all scripts and processes that are planned for the cutover migration. |
| &check; | Align external dependencies, such as partner systems and services, with the timelines and scope for go-live. |
| &check; | Plan and implement all change management activities from the **Initiate** through the **Prepare** phases, such as training, user support, user engagement, and communication. |
| &check; | Have a plan for monitoring and maintenance for production and for transitioning to support teams. |
| &check; | Prepare the production environment and train administrators and IT on monitoring, troubleshooting procedures, and support options. |
| &check; | Create a cutover plan that considers all dependencies, the timing of activities, roles and responsibilities, instructions, verification steps, and any other documentation that's associated with each activity. |

## Cutover

| Done? | Task |
| :---: | --- |
| &check; | Complete all activities in sequence. |
| &check; | Meet the exit criteria. |
| &check; | Get sign-off from stakeholders at the cutover go/no-go checkpoint. |

## Solution scope review

| Done? | Task |
| :---: | --- |
| &check; | Explain the scope of the project to business stakeholders in terms of the business processes that the solution supports. |
| &check; | Consider the following items: <ul><li>The business processes that the solution supports</li><li>The applications and solutions that are used in the solution</li><li>Whether the solution contains customizations and ISV solutions</li><li>The type and volume of integrations</li><li>The number of go-lives or rollouts</li><li>The number of users at go-live and in future rollouts</li></ul> |
| &check; | Get sign-off from business stakeholders on the solution scope. |

The solution scope review helps you confirm that the solution you're going to launch meets your business needs and expectations. The expected outcome is that the solution scope matches the solution that's going live, you've shared it with stakeholders, and they agree that it covers their expectations. The risks of not reaching this outcome are delays, dissatisfaction, and project failure.

## Solution acceptance review

| Done? | Task |
| :---: | --- |
| &check; | Test all aspects of your complete solution. |
| &check; | Complete end-to-end unit testing successfully. |
| &check; | Get sign-off from business stakeholders on the solution acceptance. |

The solution acceptance review helps you confirm that the solution you're going to launch works as expected and meets your business needs. The expected outcome is that you've completed end-to-end unit testing successfully and business stakeholders have signed off on the results. The risks of not reaching this outcome are operational difficulties, technical issues, and project failure. To avoid problems with solution acceptance, follow the testing strategy best practices and perform several types of tests before going live, especially user acceptance testing (UAT), performance testing, and system integration testing (SIT).

## User acceptance test completion

| Done? | Task |
| :---: | --- |
| &check; | Test all requirements in scope, both "happy path" and edge scenarios. |
| &check; | Test with migrated data to validate how data behaves in real life. |
| &check; | Assign correct security roles to users. Don't use a general security role or assign the System Admin role to all users. |
| &check; | Comply with regulatory requirements specific to your company, industry, or country/region. Document all features and testing results. |
| &check; | Run UAT in an environment in a Microsoft apps subscription so that it approximates your production environment as much as possible. |
| &check; | Get sign-off from business stakeholders on UAT. |

UAT helps you validate that the solution you're going to launch supports all the expected business processes and meets user needs. The expected outcome is that you've tested all requirements in scope, used migrated data, assigned correct security roles, complied with regulatory requirements, and conducted UAT in an environment that approximates production. The risks of not reaching this outcome are delays, difficulties, and project failure. Address any items identified during UAT with an owner and a completion date for each.

## Performance testing completion

| Done? | Task |
| :---: | --- |
| &check; | Test load times with peak volumes of transactions. |
| &check; | Test data search performance. |
| &check; | Test end-to-end processes and specific business processes. |
| &check; | Test performance on different devices, browsers, and virtualized environments. |
| &check; | Test integrations. |
| &check; | Test in representative environments, data, and test cases that can reliably predict performance in production. |
| &check; | Get sign-off from stakeholders on performance testing. |

Performance testing helps you ensure that the solution you're going to launch can handle the expected load and speed of your business processes. The expected outcome is that the solution performs as expected and meets the business performance criteria. The risks of not reaching this outcome are issues with the system's performance after go-live that can be difficult or expensive to fix. Do performance testing in parallel with UAT in a test environment before going live and address any issues with an owner and a completion date.

## System integration testing completion

| Done? | Task |
| :---: | --- |
| &check; | Test with expected peak volumes. |
| &check; | Simulate external systems that are down and how those scenarios are communicated and affect the user experience. |
| &check; | Get sign-off from stakeholders on SIT. |

SIT helps you validate that the solution you're going to launch works well with other applications and external systems. The expected outcome is that the solution and its integrations work as expected and you have a plan for handling unexpected situations. The risks of not reaching this outcome are issues with the integrations after go-live. Do SIT before UAT in a test environment before going live and choose the right integration pattern for your solution.

## Data migration readiness and validation

| Done? | Task |
| :---: | --- |
| &check; | Test data migration several times before cutover. |
| &check; | Validate your strategy and processes, identify and address issues of data corruption or duplication, and make sure performance fits in the cutover time window. |
| &check; | Test and sign off on all scripts and processes planned for cutover migration by the business. |
| &check; | Log any migration issues and risks and make a mitigation plan. |

Data migration readiness helps you ensure that the data you're going to use in your solution is accurate, complete, and available. The expected outcome is that you've tested data migration several times before cutover, validated your strategy and processes, addressed any issues or risks with the data migration, and got sign-off from the business. The risks of not reaching this outcome are delays or difficulties in go-live migration, inaccurate or corrupted data in your solution, and reduced user and customer confidence. Prepare a migration plan and execute multiple dry runs, prepare configuration data, master data, security configurations, open transactions, and balances in advance, and follow recommended practices for data management.

## Confirmation of external dependencies

| Done? | Task |
| :---: | --- |
| &check; | Align any external dependencies, such as ISV solutions and partner systems and services, with your timelines and scope for go-live. |
| &check; | Coordinate with providers to make sure expectations are aligned, their solutions match the roadmap timelines, and all requirements are met. |

Checking external dependencies helps you ensure that the solutions, systems, or services you need for your project are compatible and reliable. The expected outcome is that the dependencies and their interactions work as planned and you have a strategy for dealing with potential problems. The risks of not reaching this outcome are delays or failures in your project due to dependency issues. To avoid problems with external dependencies, coordinate with the providers of the dependencies, align your expectations, timelines, and requirements with them, and have regular meetings to review their status and resolve any conflicts.

## Change management for initial operations readiness

| Done? | Task |
| :---: | --- |
| &check; | Assess change readiness early in the project and reassess throughout. |
| &check; | Deliver effective training to users on how to use the new solution. |
| &check; | Engage users with the solution and get their input and feedback. |
| &check; | Communicate the value of the new solution with business sponsorship. |
| &check; | Create a community of super-users and provide resources for user support. |

Change management readiness helps you ensure that your organization adopts and engages with the new business solution you're launching. The expected outcome is that you assess and address the needs and concerns of the users throughout the project, and provide them with training, communication, sponsorship, and support. The following key elements help drive change management close to go-live:

- **Training**: Teach users how to use the new solution effectively and efficiently before they start working with it.
- **User engagement strategy**: Involve users in the design, testing, and feedback of the solution, and keep them informed and excited about the benefits.
- **Business sponsorship**: Get a trusted and influential leader to champion the solution and communicate its value to the organization.
- **User support**: Create a community of super-users and provide resources and service notifications to help users after go-live.

The risks of not reaching this outcome are poor execution, low confidence, and resistance to the new solution. To avoid problems with change readiness, reassess the change management plan throughout the implementation project.

## Operational support readiness

| Done? | Task |
| :---: | --- |
| &check; | Have a system monitoring and maintenance plan for the production environment. |
| &check; | Have a plan for [transitioning operational support](transition-to-support.md) from the implementation team to a support team. |
| &check; | Train support teams on the solution and give them the resources, tools, and access they need. |
| &check; | Have a help desk and ticket management process in place. |
| &check; | Notify stakeholders and users when the system is ready to go into production and provide them with a support contact. |

Support readiness helps you ensure that your solution works well and meets the needs of the users after it's live. The expected outcome is that you have a plan to transition support from the implementation team to the support team, and that the support team has the resources, tools, access, and training they need to provide help. The following items should be included in the operational support and maintenance plan:

- **Continuous deployment plan**: Stay updated on the latest version of the system and incorporate new features and fixes as soon as possible.
- **Monitoring**: Track performance issues, errors, feature usage, and adoption to manage and report on the post-go-live process.
- **Hypercare**: Provide an elevated level of support right after go-live to ensure smooth adoption.

The risks of not reaching this outcome are poor communication, delayed resolution, and unexpected updates that might affect system operations. Plan to transition support before go-live and share the plan with all parties involved.

## Next steps

- Learn about the activities that happen before go-live in the [**Prepare** phase](prepare-to-go-live.md)
- [Get your production environment ready for go-live](prepare-go-live-production-environment-readiness.md)
- [Plan your cutover to the new solution](prepare-go-live-cutover-strategy.md)
- Read the [case study](prepare-go-live-case-study.md) for an example of a successful go-live project
