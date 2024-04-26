---
title: Prepare your production environment to go live
description: Learn how to prepare your production environment, deploy your solution, and avoid issues when your Dynamics 365 projects go live.
author: vaniusca
ms.author: vaniaf
ms.date: 01/30/2024
ms.topic: conceptual
ms.custom:
 - ai-seo-date: 01/30/2024
 - ai-gen-docs-bap
 - ai-gen-title
 - ai-gen-desc
 - bap-template
content_well_notification: AI-contribution
---

# Prepare to go live

Go-live is a critical milestone in the deployment of a business solution to production. It's when you test and validate that everything works as expected, not just on their own, but as a whole. After a successful go-live, the new solution is operational.

The go-live process has two main activities:

- Prepare the production environment.
- Deploy the solution.

To avoid issues that can delay deployment, plan ahead and prepare for the unexpected. A good go-live plan helps you minimize unforeseen issues and risks that weren't identified during previous phases. It also has processes to handle the unexpected, which makes for a more resilient and successful project.

When you roll out a solution in phases, consider future deployments in advance. Keep refining the plan with learnings from each rollout.

This article explains how to prepare for a successful go-live of a Microsoft Dynamics 365 solution. It covers the following topics:

- [Go-live readiness](#go-live-readiness)
- [Go live with customer engagement apps](#go-live-with-customer-engagement-apps)
- [Go live with finance and operations apps](#go-live-with-finance-and-operations-apps)

## Go-live readiness

All the tasks and efforts that you do during an implementation project are preparation for the project's biggest milestone: go-live. In the [Success by Design framework](success-by-design.md), you complete these tasks when the project reaches the **Prepare** phase. At this point, if you followed all the guidance and recommended practices, the solution should be ready to go live.

Make sure that the following tasks are part of your go-live readiness plan:

- Complete and sign off on system integration, user acceptance, and performance testing.
- Complete code and prepare deployable packages to move to production.
- Create a data migration plan.
- Create and sign off on a cutover plan.
- Complete user training and assign the correct security roles to users.
- Make sure the correct number of licenses are available and assigned.
- Create and sign off on a production support plan.
- Mitigate any critical open issues from the Solution Blueprint Review or other previous implementation reviews.

The implementation team should assess go-live readiness early and often. These assessments show the status, readiness, completeness, and maturity of each activity. They also help project stakeholders and the steering committee make a well-informed go/no-go decision.

When the project moves to the **Prepare** phase, the implementation team evaluates the readiness of the solution. This evaluation is a quality gate for deployment. You do it during the go-live readiness review.

### Go-live readiness review

Before you go live with a solution, key stakeholders and the implementation team should do a go-live readiness review. Success by Design encourages teams to use this review to assess the go-live readiness of a project. The review is a deep dive into the project's status. It helps you make sure that all activities are done and that you follow recommendations and best practices. This way, you can anticipate unforeseen issues during the last sprint. You can also think of it as a holistic view of the implementation project: looking back on completed activities that are required for going live, looking at solution preparations, and looking forward to the plan to roll out and maintain the new solution.

The Microsoft FastTrack for Dynamics 365 team does a go-live readiness review in a workshop format with all parties. The review has several critical functions:

- It checks whether the solution meets the organization's needs and expectations, both functionally and nonfunctionally.
- It validates the plan that you have to ensure a smooth transition in the available cutover window and avoid surprises during and after go-live.
- It uncovers potential risks and issues that could endanger go-live and provides recommendations and actions to mitigate them.
- It summarizes all the tasks that you have done and covered in previous reviews.

Start early to prepare for the go-live readiness review. Schedule time to do the review and complete the go-live checklist. Allow time to mitigate possible risks and issues, especially go-live blockers. Consider also the time it takes to prepare the production environment. Starting the review just a few days away from the go-live date risks a delay. But starting too early can also hurt the process. The project might not be mature enough, or you might not have enough information, to do the readiness review with reliable results.

You can also do your own go-live readiness review by completing all required activities and having
the business stakeholders sign off on them.

Use the [go-live checklist](prepare-go-live-checklist.md) as you do the review. Make sure you understand the responses on the checklist. If something isn't clear, ask questions and confirm the answers.

Identify all the possible risks and issues in each key area and get recommendations. Create a mitigation plan with actions to address identified issues and risks and assign an owner for each action. Follow up on the mitigation of identified issues for critical activities.

Identify workarounds for any go-live blockers.

Keep stakeholders informed about the results of the go-live review and any mitigation actions.

After the review is done, the implementation team decides whether the go-live date is feasible.

## Go live with customer engagement apps

If your solution includes customer engagement apps, make sure to include the following information in your go-live process.

### Test and acceptance

In the **Prepare** phase, the code for solution functionalities should be done, integrations with all external systems should be tested, and you should have a high-level deployment execution plan. Solution test and acceptance activities should include checking nonfunctional requirements that stakeholders agreed to and signed off on, such as form load times, search performance, and integration performance under a realistic production load.

To help with testing, use [automation testing solutions](testing-regression-tooling.md).

### Training and adoption

Use the built-in [guided help functionalities](/powerapps/maker/model-driven-apps/create-guided-help-learning-path) to give your users a custom, in-app help experience that's tailored to their specific usage and business processes.

The easy-to-follow guidance in the [Dynamics 365 adoption guide](/dynamics365/get-started/adoption/adoption-guide) offers more tips to help you successfully roll out Dynamics 365 to your organization.

### Solution management

A strong monitoring and communication plan has a major effect on user adoption and confidence in the solution. All critical platform and application components should have a logging mechanism with a well-defined process to monitor the system. Set up alerts so that the operations team can take necessary actions and notify users when issues occur.

Monitor the solution as it grows and uses more storage capacity. Using storage above the limits affects demand, restoring backups, and other features.

Monitor API limits, too. After go-live, integrations or bulk operations might cause peaks in usage that could result in API limit errors.

### Data migration

Whether you use out-of-the-box, independent software vendor (ISV), or custom-built tools to migrate data, it's important to follow [data migration best practices](data-management-configuration-data-migration.md) and include them as part of your migration strategy.

Several factors can affect your data migration activities, including [service protection API limits](/powerapps/developer/data-platform/api-limits) and [API request limits and allocations](/power-platform/admin/api-request-limits-allocations). Keep these factors in mind when you're estimating the throughput and doing testing and final migration activities.

Data migration can be complex. Realistic goals and good throughput are important to make sure that there are no issues that might affect the go-live date and that all tasks are done according to the data migration plan.

### External dependencies

The implementation team should coordinate closely with external dependencies to make sure that expectations are aligned and requirements are met. Any external dependencies must work as expected with the current version of the solution and platform and be aligned to the roadmap.

### Production environment readiness

In solutions with customer engagement apps, you can prepare the production environments at any time. Make sure the apps in production are the same version as the apps in your development and test environments to avoid issues that might affect the release process.

The following tools can help you prepare for go-live:

- [Power Apps checker](/powerapps/maker/data-platform/use-powerapps-checker) helps validate model-driven apps and canvas apps and should be used throughout the implementation.

- [Microsoft Dataverse analytics](/power-platform/admin/analytics-common-data-service) provides metrics that help you monitor the solution.

### Support readiness

Support during cutover and go-live is as essential as it is after go-live. It's crucial to have resources available to mitigate any issues so that tasks can finish on time or with as little delay as possible. A poor support strategy will affect the success of the rollout.

You should have a plan for transitioning knowledge from the implementation team to the support team. It's important to create a list of responsibilities for the first, second, and third lines of support and an escalation path. Make sure that there's coverage outside traditional working hours and on weekends for critical situations.

### Continuous updates for customer engagement apps

We release two major service updates per year. They're backward-compatible so that apps and customizations continue to work after you update. The [release schedule](/dynamics365/get-started/release-schedule), release plans, and early access are documented and available well in advance. Use early access to validate upcoming features and capabilities before you turn them on in your production environments.

### Change management

Have a robust process in place to manage changes after the solution is deployed and becomes operational. The process should be able to manage service updates and new versions of an ISV solution. It should include a plan to prepare users for changes and assist them in adopting new features and capabilities.

### References for going live with customer engagement apps

[GitHub - Microsoft/EasyRepro: Automated UI testing API for Dynamics 365](https://github.com/microsoft/EasyRepro)

[Use solution checker to validate your model-driven apps in Power Apps](/powerapps/maker/data-platform/use-powerapps-checker)

[Microsoft Dataverse analytics](/power-platform/admin/analytics-common-data-service)

[Microsoft Dynamics 365](/learn/dynamics365/)

[Create guided help for your Unified Interface app](/powerapps/maker/data-platform/create-custom-help-pages)

[Dynamics 365 Adoption guide](/dynamics365/get-started/adoption/adoption-guide)

[Accelerate Dynamics 365 Adoption checklist](/dynamics365/adoption/adoption-checklist)

[Build a champion program](/dynamics365/adoption/champions-guide)

[Dynamics 365 release schedule and early access](/dynamics365/get-started/release-schedule)

[Evaluate go-live readiness for customer engagement apps (training)](/learn/modules/go-live-readiness/)

## Go live with finance and operations apps

If your solution includes finance and operations apps, make sure to include the following information in your go-live process.

### Lifecycle Services

Lifecycle Services is the workspace where you manage all aspects of your operations project, including milestones, environments, updates, deployments, support, and administration. As part of the go-live readiness review, make sure that the workspace has the correct configuration and information, such as milestone dates and project users and accounts.

Be familiar with Lifecycle Services functionalities for go-live, including deploying a package, requesting a database refresh, and requesting your production environment.

Use [the subscription estimator](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/subscription-estimator) to help ensure the production environment has the required capacity.

Lifecycle Services also includes tools to [monitor, diagnose, and analyze](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/monitoring-diagnostics) the health of the environment and troubleshoot issues.

### Continuous updates for finance and operations apps

Make sure that your environments comply with the [One Version policy](/dynamics365/fin-ops-core/fin-ops/get-started/one-version?toc=/dynamics365/commerce/toc.json). The policy specifies that to be supported, an environment must be on an in-service version. Set your update settings in Lifecycle Services for continuous updates.

Review the [targeted release schedule](/dynamics365/fin-ops-core/dev-itpro/get-started/public-preview-releases#targeted-release-schedule-dates-subject-to-change) to make sure that your environment version hasn't reached its end of service date. If you're about to deploy your production environment, confirm that the version complies with the release schedule. Only the most recent service updates can be selected for deployment.

Do regression testing when you update or deploy fixes or make changes to the solution. Use [automated regression testing solutions](testing-regression-tooling.md) to automate a set of test cases that can help uncover any regressions caused by an update.

### Upgrades from Dynamics AX 2012

If your solution is an upgrade from Dynamics AX 2012, it's important to include the following specific requirements in your readiness assessment:

- Use the collation `(SQL\_Latin\_General\_CP1\_CI\_AS)` because it's the one supported by the kernel or runtime.

- Run and do all pre-upgrade checklist steps on the source system before you start upgrading the database.

- Store documents and attachments in Microsoft Azure Blob Storage.

- Freeze all code and application configuration changes in the Dynamics AX 2012 environment.

- If you're using a mobile solution in the warehouse to interact with Dynamics 365, such as the Warehouse Mobile Devices Portal platform in Dynamics AX 2012, move to the Dynamics 365 Warehouse Management mobile app.

### References for going live with finance and operations apps

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

## Next steps

- [Get your production environment ready for go-live](prepare-go-live-production-environment-readiness.md)
- [Plan your cutover to the new solution](prepare-go-live-cutover-strategy.md)
- Use the Success by Design [go-live checklist](prepare-go-live-checklist.md) to make sure you don't miss any important tasks for go-live
- Read the [case study](prepare-go-live-case-study.md) for an example of a successful go-live project
