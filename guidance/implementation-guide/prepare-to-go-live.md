---
title: Prepare for go-live by getting your production environment ready and deploying your solutions
description: Learn how to prepare for a successful go-live of a Microsoft Dynamics 365 solution by assessing the readiness of the people, processes, and systems for deployment.
author: vaniusca
ms.author: vaniaf
ms.date: 06/06/2023
ms.topic: conceptual
ms.custom:
 - ai-gen-docs-bap
 - ai-gen-desc
 - ai-seo-date:08/23/2023
 - bap-template
---

# Prepare for go-live by getting your production environment ready and deploying your solutions

Go-live is a critical milestone in the process of deploying a business solution to production. At go-live, all parts of the implementation project come together and are tested and validated to make sure everything works as expected, not just on their own, but as a whole. After a successful go-live, the new solution is operational.

The go-live process covers getting the production environment ready and then deploying the solution. It includes the following activities:

- Migrating and validating data
- Creating a communication plan
- Finalizing testing
- Signing off on the solution
- Onboarding and training users

Planning ahead and preparing for the unexpected are key to avoiding issues that can delay deployment. A good go-live plan helps to minimize unforeseen issues and risks that weren't identified during previous phases. It has processes in place to handle the unexpected, which makes for a more resilient and successful project. 

When you roll out a solution in phases, the go-live plan should consider future deployments in advance. It's important to keep refining the plan with learnings from each rollout.

[Go-live readiness](#go-live-readiness) includes key activities to make sure the go-live plan is completed and that all parts of the solution&mdash;people, processes, and system&mdash;are in place for a smooth deployment. All resources must be available in time for activities to be executed and completed. Environments must be created, configured, and operational on time.

When a solution goes live, there's often a transition period, also known as *cutover*. The cutover process follows a [cutover plan](prepare-go-live-cutover-strategy.md) that details the activities that are critical in transitioning to the new solution.

## Go-live readiness

All the tasks and efforts that are undertaken during an implementation project are preparation for the project's biggest milestone: go-live. In the [Success by Design framework](success-by-design.md), these tasks are completed when the project reaches the Prepare phase. At this point, if you followed all the guidance and recommended practices, the solution should be ready to go live.

At a high level, the project is ready to go live when the following conditions are true:

- The go-live strategy is aligned with best practices.
- The requirements for going live have been met, including testing, code, and configurations.
- A concise and agreed-on [cutover plan](prepare-go-live-cutover-strategy.md) is in place, detailing the next actions required for the transition to the new system.

At a more detailed level, the following requirements must be met before the solution can go live:

- System integration, user acceptance, and performance testing are completed and signed off on.
- Code is complete and deployable packages are prepared to move to production.
- A data migration plan is in place.
- A cutover plan is in place and signed off on.
- User training is complete and users have the correct security roles.
- The correct number of licenses are available and assigned.
- A production support plan is in place and signed off on.
- Any critical open issues from the Solution Blueprint Review or other previous implementation reviews are mitigated.

When you've verified the successful completion of the most important project tasks, you can perform the cutover activities.

### Assess go-live readiness

While there's no such thing as zero risk for go-live, the go-live readiness review is a qualitative method to determine how well prepared the new solution is to run your business. You should evaluate the preparedness of the people and processes as well to make sure no critical details have been overlooked.

The implementation team should assess go-live readiness early and often. These assessments provide clarity on the status, readiness, completeness, and maturity of each activity and help project stakeholders and the steering committee make a well-informed go/no-go decision.

When the project moves to the Prepare phase, the implementation team evaluates the preparedness of the solution, which serves as a quality gate for deployment. This evaluation is done during the go-live readiness review.

### Go-live readiness review

Before you go live with a solution, key stakeholders and the implementation team should perform a go-live readiness review. Success by Design encourages teams to use the go-live readiness review to assess the go-live readiness of a project. The go-live readiness review is a deep dive into the project's status. The review is a way to make sure all activities have been completed and that recommendations and best practices are being followed which helps the team anticipate unforeseen issues during the last sprint. Another way to describe it is as a holistic view of the implementation project: looking back on completed activities that are required for going live, looking at solution preparations, and looking forward to the plan to roll out and maintain the new solution.

The Microsoft FastTrack for Dynamics 365 team conducts a go-live readiness review in a workshop format with all parties and has several critical functions:

- It determines whether the solution meets the organization's needs and expectations, both functionally and nonfunctionally.
- It validates the plan that has been established to ensure a smooth transition in the available cutover window and avoid surprises during and after go-live.
- It uncovers potential risks and issues that could imperil go-live and provides recommendations and actions to mitigate them.
- It summarizes all the tasks that have been completed and covered in previous reviews.

Start early to prepare for the go-live readiness review. Schedule time to conduct the review and complete the go-live checklist. Be sure to account for time needed to mitigate possible risks and issues, especially go-live blockers. Keep in mind as well the time it takes to prepare the production environment. Starting the review just a few days away from the go-live date risks a delay. However, starting the review too early can also be detrimental to the process. The project might not be mature enough, or you might not have enough information, to complete the readiness review with reliable results to properly identify potential risks.

You can also perform your own go-live readiness review, by completing all required activities and have the business stakeholders sign off on them.

The following diagram illustrates the [Success by Design](success-by-design.md) implementation phases and when the go-live readiness review occurs:

:::image type="content" source="media/prep-golive-sdb-implementation-phases2.png" alt-text="Diagram illustrating the Success by Design implementation phases, with the go-live review highlighted." lightbox="media/prep-golive-sdb-implementation-phases2.png":::<!-- EDITOR'S NOTE: Please change "go live" to "go-live" in the diagram. -->

Use the [go-live checklist](prepare-go-live-checklist.md) as you conduct the review. Make sure you understand the responses on the checklist. If something isn't clear, ask questions and confirm the answers.

Identify all the possible risks and issues in each key area and get recommendations. Create a mitigation plan with actions to address identified issues and risks and assign an owner for each action. Follow up on the mitigation of identified issues for critical activities.

Identify workarounds for any go-live blockers.

Keep stakeholders informed about the results of the go-live review and any mitigation actions.

After the review is complete, the implementation team determines whether the go-live date is feasible.

## Go live with Customer engagement apps
If you will be including Customer engagement apps in your implementation, make sure to include the following information in your go-live process. 

### Test and acceptance

In the [Prepare phase](prepare-to-go-live.md), the code for solution functionalities should be complete, integrations with all external systems should be tested, and a high-level deployment execution plan should be in place. Solution test and acceptance activities should include validating nonfunctional requirements that stakeholders agreed to and signed off on, such as form load times, search performance, and integration performance under a realistic production load.

To help with testing automation, <!-- Regression testing refactoring > try [Easy Repro](https://github.com/microsoft/EasyRepro), an open-source library that facilitates automated UI testing. --> use [automation testing solutions](testing-regression-tooling.md).

### Training and adoption

Use the built-in [guided help functionalities](/powerapps/maker/model-driven-apps/create-guided-help-learning-path) to give your users a custom, in-app help experience that's tailored to their specific usage and business processes.

The easy-to-follow guidance in the [Dynamics 365 adoption guide](/dynamics365/get-started/adoption/adoption-guide) offers more tips to help you successfully roll out Dynamics 365 to your organization.

### Solution management

A strong monitoring and communication plan has a major impact on user adoption and confidence in the solution. All critical platform and application components should have a logging mechanism with a well-defined process to monitor the system. Set up alerts so that the operations team can take necessary actions and notify users when issues occur.

Monitor the solution as it grows and uses more storage capacity. Using storage above the limits has an impact on demand, restoring backups, and other features.

Monitor API limits, too. After go-live, integrations or bulk operations might cause peaks in usage that could result in API limit errors.

### Data migration

Whether you use out-of-the-box, independent software vendor (ISV), or custom-built tools to migrate data, it's important to follow [best practices](data-management-configuration-data-migration.md) and include them as part of your migration strategy.

Several factors can affect your data migration activities, including [service protection API limits](/powerapps/developer/data-platform/api-limits) and [API request limits and allocations](/power-platform/admin/api-request-limits-allocations). Keep these factors in mind when you're estimating the throughput and performing testing and final migration activities.

Data migration can be complex. Realistic goals and good throughput are important to make sure there are no issues that might affect the go-live date and that all tasks are executed according to the data migration plan.

### External dependencies

The implementation team should coordinate closely with external dependencies to make sure that expectations are aligned and requirements are met. Any external dependencies must work as expected with the current version of the solution and platform and be aligned to the roadmap.

### Production environment readiness

In solutions with customer engagement apps, you can prepare the production environments at any time. Make sure the apps in production are the same version as the apps in your development and test environments to avoid issues that might affect the release process.

The following tools can help you prepare for go-live:

- [Power Apps checker](/powerapps/maker/data-platform/use-powerapps-checker) helps validate model-driven apps and canvas apps and should be used throughout the implementation.

- [Microsoft Dataverse analytics](/power-platform/admin/analytics-common-data-service) provides metrics that help you monitor the solution, especially during the operations phase.

### Support readiness

Support during cutover and go-live is as essential as it is after go-live. It's crucial to have resources available to mitigate any issues so that tasks can complete on time or with as little delay as possible. A poor support strategy will affect the success of the rollout.

You should have a plan for transitioning knowledge from the implementation team to the support team. It's important to create a list of responsibilities for the first, second, and third lines of support and an escalation path. Make sure there's coverage outside traditional working hours and on weekends for critical situations.

### Continuous updates

We release two major service updates per year. They're backward-compatible so that apps and customizations continue to work after you update. The [release schedule](/dynamics365/get-started/release-schedule), release plans, and early access are documented and available well in advance. Use early access to validate upcoming features and capabilities before you turn them on in your production environments.

### Change management

Have a robust process in place to manage changes after the solution is deployed and becomes operational. The process should be able to manage service updates and new versions of an ISV solution. It should include a plan to prepare users for changes and assist them in adopting new features and capabilities.

## Go live with finance and operations apps
If you will be including finance and operations spps in your implementation, make sure to include the following information in your go-live process. 

### Lifecycle Services

Lifecycle Services is the workspace where you manage all aspects of your operations project, including milestones, environments, updates, deployments, support, and administration. As part of the go-live readiness review, make sure the workspace has the correct configuration and information, such as milestone dates and project users and accounts.

Be familiar with Lifecycle Services functionalities for go-live, including deploying a package, requesting a database refresh, and requesting your production environment.

Create [the Subscription estimator](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/subscription-estimator) for sizing the production environment.  

Lifecycle Services also includes tools to [monitor, diagnose, and analyze](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/monitoring-diagnostics) the health of the environment and troubleshoot issues that occur.

### Continuous updates

Make sure your environments comply with the [One Version policy](/dynamics365/fin-ops-core/fin-ops/get-started/one-version?toc=/dynamics365/commerce/toc.json). The policy specifies that to be supported an environment must be on an in-service version. Set your update settings in Lifecycle Services for continuous updates.

Review the [Targeted release schedule](/dynamics365/fin-ops-core/dev-itpro/get-started/public-preview-releases#targeted-release-schedule-dates-subject-to-change) article to verify that your environment version hasn't reached its end of service date. If you're about to deploy your production environment, confirm that the version complies with the release schedule. Only the most recent service updates can be selected for deployment.

Conduct regression testing when you update or deploy fixes or make changes to the solution. Use <!-- Regression testing refactoring> the Microsoft [Regression Suite Automation Tool](https://community.dynamics.com/blogs/post/?postid=d278adc9-4d09-4fad-a485-6ab7bb0a5429) --> [automated regression testing solutions](testing-regression-tooling.md) to automate a set of test cases that can help uncover any regressions due to continuous updates.

### Upgrades

For solutions with Dynamics 365 finance and operations apps, upgrades from Dynamics AX 2012 are common. It's important to include in your readiness assessment the following specific requirements for upgrading your solution:

- Use the collation `(SQL\_Latin\_General\_CP1\_CI\_AS)` because it's the one supported by the kernel/runtime.

- Run and execute all pre-upgrade checklist steps on the source system before beginning any database upgrade activity.

- Store documents and attachments in Microsoft Azure Blob Storage.

- Freeze all code and application configuration changes in the AX 2012 environment.

- If you're using a mobile solution in the warehouse to interact with Dynamics 365, such as the Warehouse Mobile Devices Portal platform in Dynamics AX 2012, move to the Dynamics 365 Warehouse Management mobile app.

## Next steps

- Determine the [go-live check list](prepare-go-live-checklist.md).
- [Prepare your production environment](prepare-go-live-production-environment-readiness.md) for go-live.
- Review the [cutover process](prepare-go-live-cutover-strategy.md).
