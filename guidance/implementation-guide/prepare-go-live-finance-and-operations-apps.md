---
title: Go live with finance and operations apps
description: Learn how to prepare for go-live with finance and operations apps by reviewing key activities for go-live readiness, best practices, tips, and common pitfalls to ensure a successful deployment.
ms.date: 10/02/2023
ms.topic: conceptual
author: vaniusca
ms.author: vaniaf
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:08/23/2023
  - bap-template
---

# Go live with finance and operations apps

Go-live is a critical milestone during an implementation project. It's the phase where you validate every plan and test.

The general process of [readying your production environment](prepare-go-live-production-environment-readiness.md), [preparing to go live](prepare-to-go-live.md), and [developing a cutover strategy and plan](prepare-go-live-cutover-strategy.md) are the same, regardless of the solution you're implementing. In this article, we focus on solutions that include finance and operations apps. We summarize the key activities for go-live readiness, their purpose, important takeaways, best practices, and tips and tricks, and common pitfalls that can happen during this phase and their impact on how business users receive and adopt the new solution.

## Go-live readiness review

Before you go live with a solution that includes one or more customer engagement apps, key stakeholders and the implementation team should perform a go-live readiness review. The review consists of making sure all activities have been completed and that recommendations and best practices are being followed, and helps the team anticipate unforeseen issues during the last sprint. It acts as the quality gate and prerequisite for deploying the production environment.

The Microsoft FastTrack for Dynamics 365 team conducts a go-live readiness review in a workshop format with all parties. You can also perform your own [go-live readiness review](prepare-to-go-live.md).

Your review should cover the following topics.

## Lifecycle Services

Lifecycle Services is the workspace where you manage all aspects of your operations project, including milestones, environments, updates, deployments, support, and administration. As part of the go-live readiness review, make sure the workspace has the correct configuration and information, such as milestone dates and project users and accounts.

Be familiar with Lifecycle Services functionalities for go-live, including deploying a package, requesting a database refresh, and requesting your production environment.

Create [the Subscription estimator](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/subscription-estimator) for sizing the production environment.  

Lifecycle Services also includes tools to [monitor, diagnose, and analyze](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/monitoring-diagnostics) the health of the environment and troubleshoot issues that occur.

## Continuous updates

Make sure your environments comply with the [One Version policy](/dynamics365/fin-ops-core/fin-ops/get-started/one-version?toc=/dynamics365/commerce/toc.json). The policy specifies that to be supported an environment must be on an in-service version. Set your update settings in Lifecycle Services for continuous updates.

Review the [Targeted release schedule](/dynamics365/fin-ops-core/dev-itpro/get-started/public-preview-releases#targeted-release-schedule-dates-subject-to-change) article to verify that your environment version hasn't reached its end of service date. If you're about to deploy your production environment, confirm that the version complies with the release schedule. Only the most recent service updates can be selected for deployment.

Conduct regression testing when you update or deploy fixes or make changes to the solution. Use <!-- Regression testing refactoring> the Microsoft [Regression Suite Automation Tool](https://community.dynamics.com/blogs/post/?postid=d278adc9-4d09-4fad-a485-6ab7bb0a5429) --> [automated regression testing solutions](testing-regression-tooling.md) to automate a set of test cases that can help uncover any regressions due to continuous updates.

## Upgrades

For solutions with Dynamics 365 finance and operations apps, upgrades from Dynamics AX 2012 are common. It's important to include in your readiness assessment the following specific requirements for upgrading your solution:

- Use the collation `(SQL\_Latin\_General\_CP1\_CI\_AS)` because it's the one supported by the kernel/runtime.

- Run and execute all pre-upgrade checklist steps on the source system before beginning any database upgrade activity.

- Store documents and attachments in Microsoft Azure Blob Storage.

- Freeze all code and application configuration changes in the AX 2012 environment.

- If you're using a mobile solution in the warehouse to interact with Dynamics 365, such as the Warehouse Mobile Devices Portal platform in Dynamics AX 2012, move to the Dynamics 365 Warehouse Management mobile app.

## Cutover

Here's an example of the ideal cutover sequence for bringing data into the production environment of an operations solution and then validating the data.

:::image type="content" source="media/prep-golive-fno-guidelines.png" alt-text="Example of the cutover sequence for an operations solution." lightbox="media/prep-golive-fno-guidelines.png":::

## Next steps

- Review specific guidelines for [customer engagement apps](prepare-go-live-dynamics-365-customer-engagement.md).
- Review the [go-live checklist](prepare-go-live-checklist.md).

## References

[GitHub - Microsoft/EasyRepro: Automated UI testing API for Dynamics 365](https://github.com/microsoft/EasyRepro)

[Microsoft Dynamics 365](/learn/dynamics365/)

[Dynamics 365 Adoption guide](/dynamics365/get-started/adoption/adoption-guide)

[Accelerate Dynamics 365 Adoption checklist](/dynamics365/adoption/adoption-checklist)

[Build a champion program](/dynamics365/adoption/champions-guide)

[Dynamics 365 release schedule and early access](/dynamics365/get-started/release-schedule)

[Prepare for go live](/dynamics365/fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live)

[Report production outage](/business-applications-release-notes/april18/dynamics365-finance-operations/report-production-outage)

[Targeted release schedule (dates subject to change)](/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-releases?toc=/dynamics365/commerce/toc.json#targeted-release-schedule-dates-subject-to-change)

[One Version service updates FAQ](/dynamics365/fin-ops-core/fin-ops/get-started/one-version?toc=/dynamics365/commerce/toc.json)

[Monitoring and diagnostics tools in Lifecycle Services (Lifecycle Services)](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/monitoring-diagnostics)  
