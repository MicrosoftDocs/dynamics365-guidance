---
title:  Go live with customer engagement apps
description: Learn how to prepare for go-live with customer engagement apps by reviewing key activities for go-live readiness, best practices, tips, and common pitfalls to ensure a successful deployment.
ms.date: 06/06/2023
ms.topic: conceptual
author: vaniusca
ms.author: vaniaf
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:08/23/2023
  - bap-template
---

# Go live with customer engagement apps
<!-- EDITOR'S NOTE: Is this article needed? Most of what it claims to cover is covered in greater detail in the general guidance for preparing to go live. Things that are covered here but not in the general guidance could easily be added there. I don't see any information that would apply more to customer engagement apps than to any other Dynamics 365 apps or cloud solutions. Also, there seems to be information in prepare-go-live-finance-and-operations-apps.md that could be useful here (or in the general guidance). -->
Go-live is a critical milestone during a deployment. It's the phase in which every plan and test is validated.

The general process of [readying your production environment](prepare-go-live-production-environment-readiness.md), [preparing to go live](prepare-to-go-live.md), and [developing a cutover strategy and plan](prepare-go-live-cutover-strategy.md) are the same, regardless of the solution you're implementing. In this article, we focus on solutions that include customer engagement apps. We summarize the key activities for go-live readiness, their purpose, important takeaways, best practices, and tips and tricks, and common pitfalls that can happen during this phase and their impact on how business users receive and adopt the new solution.

## Planning

Planning ahead and preparing for the unexpected are key to avoiding issues that can delay deployment. All resources must be available in time for activities to be executed and completed. Environments must be created, configured, and operational on time.

## Go-live readiness review

Before you go live with a solution that includes one or more customer engagement apps, key stakeholders and the implementation team should perform a go-live readiness review. The review consists of making sure all activities have been completed and that recommendations and best practices are being followed, and helps the team anticipate unforeseen issues during the last sprint.

The Microsoft FastTrack for Dynamics 365 team conducts a go-live readiness review in a workshop format with all parties. You can also perform your own [go-live readiness review](prepare-to-go-live.md).

## Test and acceptance

In the [Prepare phase](prepare-to-go-live.md), the code for solution functionalities should be complete, integrations with all external systems should be tested, and a high-level deployment execution plan should be in place. Solution test and acceptance activities should include validating nonfunctional requirements that stakeholders agreed to and signed off on, such as form load times, search performance, and integration performance under a realistic production load.

To help with testing automation, <!-- Regression testing refactoring > try [Easy Repro](https://github.com/microsoft/EasyRepro), an open-source library that facilitates automated UI testing. --> use [automation testing solutions](testing-regression-tooling.md).

## Training and adoption

Use the built-in [guided help functionalities](/powerapps/maker/model-driven-apps/create-guided-help-learning-path) to give your users a custom, in-app help experience that's tailored to their specific usage and business processes.

The easy-to-follow guidance in the [Dynamics 365 adoption guide](/dynamics365/get-started/adoption/adoption-guide) offers more tips to help you successfully roll out Dynamics 365 to your organization.

## Solution management

A strong monitoring and communication plan has a major impact on user adoption and confidence in the solution. All critical platform and application components should have a logging mechanism with a well-defined process to monitor the system. Set up alerts so that the operations team can take necessary actions and notify users when issues occur.

Monitor the solution as it grows and uses more storage capacity. Using storage above the limits has an impact on demand, restoring backups, and other features.

Monitor API limits, too. After go-live, integrations or bulk operations might cause peaks in usage that could result in API limit errors.

## Data migration

Whether you use out-of-the-box, independent software vendor (ISV), or custom-built tools to migrate data, it's important to follow [best practices](data-management-configuration-data-migration.md) and include them as part of your migration strategy.

Several factors can affect your data migration activities, including [service protection API limits](/powerapps/developer/data-platform/api-limits) and [API request limits and allocations](/power-platform/admin/api-request-limits-allocations). Keep these factors in mind when you're estimating the throughput and performing testing and final migration activities.

Data migration can be complex. Realistic goals and good throughput are important to make sure there are no issues that might affect the go-live date and that all tasks are executed according to the data migration plan.

## External dependencies

The implementation team should coordinate closely with external dependencies to make sure that expectations are aligned and requirements are met. Any external dependencies must work as expected with the current version of the solution and platform and be aligned to the roadmap.

## Production environment readiness

In solutions with customer engagement apps, you can prepare the production environments at any time. Make sure the apps in production are the same version as the apps in your development and test environments to avoid issues that might affect the release process.

The following tools can help you prepare for go-live:

- [Power Apps checker](/powerapps/maker/data-platform/use-powerapps-checker) helps validate model-driven apps and canvas apps and should be used throughout the implementation.

- [Microsoft Dataverse analytics](/power-platform/admin/analytics-common-data-service) provides metrics that help you monitor the solution, especially during the operations phase.

## Support readiness

Support during cutover and go-live is as essential as it is after go-live. It's crucial to have resources available to mitigate any issues so that tasks can complete on time or with as little delay as possible. A poor support strategy will affect the success of the rollout.

You should have a plan for transitioning knowledge from the implementation team to the support team. It's important to create a list of responsibilities for the first, second, and third lines of support and an escalation path. Make sure there's coverage outside traditional working hours and on weekends for critical situations.

## Continuous updates

[In the words of](https://cloudblogs.microsoft.com/dynamics365/bdm/2018/07/06/modernizing-the-way-we-update-dynamics-365) Mo Osborne, Corporate Vice President and Chief Operating Officer, Microsoft Business Applications & Platform, "To enable businesses everywhere to accelerate their digital transformation, we're continuously enhancing Dynamics 365 with new capabilities."

We release two major service updates per year. They're backward-compatible so that apps and customizations continue to work after you update. The [release schedule](/dynamics365/get-started/release-schedule), release plans, and early access are documented and available well in advance. Use early access to validate upcoming features and capabilities before you turn them on in your production environments.

## Change management

Have a robust process in place to manage changes after the solution is deployed and becomes operational. The process should be able to manage service updates and new versions of an ISV solution. It should include a plan to prepare users for changes and assist them in adopting new features and capabilities.

## Next steps

- Review specific guidelines for [finance and operations apps](prepare-go-live-finance-and-operations-apps.md).
- Review the [go-live checklist](prepare-go-live-checklist.md).

## References

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
