---
title: Plan your solution deployment and release
description: Learn how to plan the deployment and release of your Dynamics 365 solution, based on your business goals and needs.
ms.date: 04/27/2023
ms.topic: conceptual
author: edupont04
ms.author: veneva
ms.custom:
  - ai-seo-date: 
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
ai-usage: ai-assisted
---

# Plan your deployment and release

When you implement a Dynamics 365 solution, you need a deployment and release strategy, the plan that tells you how you'll deploy your solution and release it to your users. Your strategy should match your business objectives, risk appetite, budget, resources, and time availability. Your strategy might be different depending on how large and complex your implementation is.

## Deployment strategy

One of the key decisions for your deployment strategy is the *environment strategy*. The environment strategy defines the environments you'll use to deploy your solution. An environment is a space where you can create, test, and run your solution. You might need one or more environments to deploy your solution, depending on your organization's size and needs. For example, you might need separate environments for development, testing, and production. Learn more at [Environment strategy](environment-strategy-overview.md).  

## Release strategy

The release strategy defines the release plan, or how you'll release and update your solution. The release strategy should consider the release cycles of Dynamics 365 apps, platform, custom solution development cycles, and maintenance windows.

Consider these factors before you choose a release strategy:

- What is the minimum viable product (MVP) that you need to deliver value to your customers quickly, and how will you plan for future enhancements? Learn more at [Drive app value](drive-app-value.md).

- Is your project a single-country/region rollout or a multi-country/region rollout?

- Do you need to do pilot rollouts before rolling out to a wider audience?

- What are the localization requirements, especially for multi-org or multi-region rollouts?

- Do you need to phase out the existing system by a certain deadline or can you run it in parallel?

- How will the release affect users' daily productivity?

- What are users' training needs?

- How complex are the integrations during the rollout?

Based on these factors, you should define a release strategy that helps you deploy your solution in the best way.

Following are some common release strategy models:

### Big bang

In the "big bang" approach, you deploy the final solution to the production environment and retire the old system. All users start using the new system on the go-live date. The term *big bang* means that you release a large scope of work for the entire user base at the same time.

The benefit of a big bang approach is that it focuses on a shorter rollout period compared to a phased rollout, and all users get on board at the same time. It's a good approach for small and simple implementations, where you can deliver the solution in a short time. It's also a good approach for organizations that have a high risk appetite and can tolerate a lot of change at once.

Some of the risks associated with big bang releases are:

- You might face challenges with user acceptance, adoption, and change management, as you introduce a lot of changes for a lot of users at once.

- You might have issues after the go-live, as you make such large changes at once. It might be hard or impossible to go back to the old system. You should have a backup plan for business continuity, and a support plan to deal with post&ndash;go-live issues.

- It might take a long time to deliver the solution to the production environment, and there's more to organize during the transition. If the rollout runs into problems, the whole user community is affected by the delays.

Big bang releases aren't ideal for cloud implementations, as the cloud service updates regularly (every few weeks or months). You don't need to wait for a big bang release when you can benefit from frequent updates.

For large and complex implementations, big bang projects can take many months or even years to complete. The business needs and priorities that you analyzed at the beginning might be different by the time you finish, as the market and the product change quickly.

The following table summarizes the pros and cons of the big bang approach.

| Pro  | Con |
| --------- | --------- |
| Shorter, condensed deployment time that minimizes disruption for the organization. | You might not keep up with the changing market scenarios and product capabilities, resulting in a misalignment between the solution and the business needs at the time of deployment. |
| Lower costs from a quick rollout with no loss of overall work, but with a need to account for resource costs to manage the complexity. | Users might have delays in their daily tasks, as they learn to adapt to the new system without prior experience. |
| Same go-live date for all users. | It might be difficult and costly to go back to the old system, if it's even possible. |
| Reduced investment in temporary interfaces. | Any failures during the rollout have a high impact on many users. |
|  | You might have a lot of risks and issues from introducing large changes for large groups of users. |
|  | You might have a lot of issues after the go-live. |
|  | You don't have a chance to learn from early launches and make improvements. |
|  | You have to ramp up a large rollout team for a short period of time. |

### Phased rollout

In a phased rollout approach, you roll out the solution in phases or releases. The phases can be planned in different ways, such as by modules, business priority, business units, or geographies. One approach is to release an initial set of features in the first phase, and then build on that by releasing the rest of the features in subsequent phases. When you release the first phase for a business unit or module, you expect the relevant users to stop using the old system and move to the new one. You might still need temporary interfaces to connect the new system with the old systems until all phases are rolled out.

For example, you can start the implementation with one business unit. Once the implementation is complete, you move on to implement the next business unit. As you gain experience and learn from past mistakes, the subsequent rollouts become smoother. This approach reduces risk and increases user adoption.

The following table summarizes the pros and cons of the phased rollout approach.

| Pro  | Con |
| --------- | --------- |
| You can prioritize the features that deliver the most business value or have the lowest complexity, and release them first. | You have a longer implementation and deployment time due to multiple go-live events. |
| You can introduce new features gradually and let users get used to the new system. | You have a more complex data migration from the old system to the new system, as it must be planned in a staggered way. |
| You can optimize the later phases by incorporating the lessons learned from the earlier ones. | You have to plan for continuous disruption over longer periods of time, such as parallel efforts to support deployments and to work on future phases. |
| You have a lower risk of disrupting the business. Errors found in the initial phase are limited to specific business areas and users, and the rest of the business isn't affected. | You might have employee morale issues from change fatigue. Phased projects require a lot of focus and coordination, and the team might lose momentum after the first few phases. These projects don't have the benefit of focused intensity that the big bang approach has. The change management team must monitor employee morale and plan initiatives to keep their interest alive. |
| You can have a faster time to value when phases are based on features rather than modules, geography, or business unit. | You might need temporary interfaces to connect the new and the old systems until the new system is fully rolled out. |
| You have a lower level of investment and resources needed to ramp up for each deployment, compared to a big bang approach. | You might have scope creep as project timelines are stretched out. You might have a tendency to incorporate changes and rework, which can affect the work for subsequent phases and their timelines. |

### Parallel rollout

In a parallel rollout approach, which is a variation of the phased rollout approach, you keep the old system alive along with the new system. It's more of a validation technique than a rollout approach, as it allows users to learn, test, and get comfortable with the new system. Typically, for a few months, both systems are actively used and users must enter information in both systems.

With a parallel rollout:

- Users have more work to do, as they must enter information twice.

- It might be preferred for projects where the business risk is high and can't be easily mitigated by testing. But you should also make sure that the team doesn't cut corners on testing and training efforts.

- It's less popular due to the extra effort and cost involved in maintaining two systems.

The release strategy goes hand-in-hand with the change management strategy, as many activities of change management are key to a successful rollout.

The following table summarizes the pros and cons of the parallel rollout approach.

| Pro  | Con |
| --------- | --------- |
| Lower risk | Higher effort and cost |
| Users can take their time to migrate to the new system | Data duplication can get complicated. You should have a clear exit plan that's based on time or workload, such as closing all existing cases in the old system. |
|  | This approach can hide poor training and testing efforts. |

## Next steps

- [Implementation strategy](implementation-strategy.md)  
- [Choose a methodology for your Dynamics 365 project](implementation-strategy-choose-methodology.md)  
- [Define a strategy for adoption and change management](implementation-strategy-define-strategy-adoption-change-management.md)
