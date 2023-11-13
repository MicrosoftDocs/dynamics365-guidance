---
title: Define a strategy for deployment and release
description: Find guidance for how to develop a strategy for deploying your Dynamics 365 implementation.
ms.date: 04/27/2023
ms.topic: conceptual
author: edupont04
ms.author: veneva
---

# Define a strategy for deployment and release

A deployment and release strategy describes how the Enterprise is going to deploy the application and release to their end users. The strategy chosen is based on business objectives, risk propensity, budget, resources, and time availability, and its complexity varies depending on each implementation's unique scenarios.

## Deployment strategy

One of the architectural decisions for the deployment of the solution is the *environment strategy*. The environment strategy refers to the point of having one environment versus multiple environments to deploy the solutions built on Dynamics 365 apps. It's a vital point to consider for complex enterprise implementations with multiple business groups and cross-functional scenarios. Learn more at [Environment strategy](environment-strategy-overview.md).  

## Release strategy

The release strategy defines the release plan, and the lifecycle of updates to the solution. The release strategy should take into consideration the release cycles of Dynamics 365 apps, platform, custom solution development cycles, and the various maintenance windows.

There are several key factors to consider prior to choosing any of the Release approaches detailed below.

- What is the MVP needed for faster value to customers and then later plan for continued enhancements? Learn more at [Drive app value](drive-app-value.md).

- Is this project a multi-country/region rollout or single-country/region rollout?

- Is there a need to consider pilot rollouts prior to wider team rollouts?

- What are the localization requirements, especially in scenarios of multi-org or multi-region rollouts?

- Do we need to phase out the incumbent system of applications by a certain key timeline or can it be run in parallel?

- What is the extent of impact on end users' day-to-day productivity?

- What training needs do end users have?

- What is the complexity of integrations during the rollout?

Taking these factors into consideration, you should define a Release strategy that helps the organization deploy the application in the most effective manner.

The following are some typical Release strategy models:

### Big-bang

In the big-bang approach, as the name suggests, the final software solution is deployed to the production and the old system is retired. All users start using the new system on the go-live date. The term *big-bang* generally describes the approach of taking a large scope of work live for the entire user base at the same time.

The benefit of a big-bang approach is that it concentrates on a shorter rollout period compared to a phased rollout, and all users onboard at the same time.

An example of a big-bang rollout is when an organization that was using a legacy system for all its finance teams tells all users to stop using the old system and start using Dynamics 365 Finance on the go-live date.

Some of the risks associated with big-bang releases are:

- As a large number of users are onboarded with the transformation of all business processes at one go, you risk a failure of user acceptance, adoption, and change management.

- With such large changes happening at one go, there's a potential for issues to arise post go-live and falling back on the older system is hard, if even possible. It's critical to ensure proper contingency planning for business continuity, and support mechanisms to deal with post-go-live issues.

- The delivery of finished software to production takes up a longer timeline, there's more to organize during transition. If the final rollout runs into challenges, the wider user community is impacted due to the resulting delays

Big-bang releases aren't ideal in cloud implementations as the cloud service updates at regular intervals (weeks, months). It doesn't yield a good ROI for big-bang releases.

For large and complex implementations, big-bang projects can require many months or even years to complete. Given the pace of change in most industries, it may not be feasible to wait that long for implementation. That's especially true when the business that was analyzed for requirements has different needs and priorities a year later.

The following table outlines the benefits and potential drawbacks.

|Pro  |Con  |
|---------|---------|
|Shorter, condensed deployment times that minimize disruption for the organization.|  May not accommodate for rapidly changing market scenarios and product capabilities, leaving a lack of solution alignment at deployment, causing a negative impact for business users.|
|Lower costs from a quick rollout with no loss of overall work but with a need to account for resource costs to manage the complexity.|Daily task delays from users learning to adapt to the new application without earlier experience.|
|Same go-live date for all users.|Transitioning back to legacy systems can be costly and difficult, even when possible.|
|Reduced investment in temporary interfaces.|Any failures during the rollout have a high impact on maximum users.|
||Heightened probability of risks emerging from introducing large changes for large groups of users.|
||Heightened probability of issues coming up in go-live.|
||No opportunity to learn from early launches to change things.|
||Costs of ramping up a large rollout team for a short period of time.|

### Phased rollout

In a phased rollout approach, we release the software in phases or releases. The phases can be planned in several ways, and they can be based on modules, business priority, business units, or geographies. One approach is to release an initial set of capabilities in the first phase. You would then build on that by releasing the rest of the requirements in subsequent phases. At the release of the first phase for a business unit or module, expect the relevant business users to stop using the legacy system and move to the new one. There could still be temporary scaffolding integrations set up to integrate the new system with the incumbent systems until all phases are rolled out.

For example, a team can start the implementation with one business unit. Once implementation is complete, they move on to implement the next business unit. As the team gains experience and learns from past mistakes, the subsequent rollouts become smoother. This approach leads to less risk and more employee adoption.

The following table outlines the benefits and potential drawbacks.

|Pro  |Con  |
|---------|---------|
|Higher business value features can be prioritized. The implementation team can choose to prioritize lower complexity features to adapt to the new capabilities.|Longer implementation and deployment timeline due to multiple go-live events.|
|Unlike big-bang, phased rollout releases can bring new use cases gradually, allowing for more buy-in frm business users as they get used to the new system.|Complexity of data migration from legacy solution to the target solution increases as it must be planned in a staggered approach.|
|Project teams can optimize later phases by incorporating the learnings from earlier ones.|The organization must plan for continuous disruption over longer periods of time, such as parallel efforts to support deployments while working on implementing future phases.|
|Risk of disrupting business is less as errors found in the initial phase are limited to the specific business areas and users, and the rest of the business isn't affected.|Employee morale may suffer as they face change fatigue. Phased projects require much focus and coordination as the team might lose momentum after the first few phases. These projects don't have the benefit of focused intensity that the big-bang approach has. The change management team must keep tabs on employee morale and plan initiatives to keep their interest alive.|
|When phases are based on functionality rather than modules, geography, or business unit, the result is often a faster time to value.|Temporary scaffolding solutions are needed to manage the integration between the new and the legacy systems until the new solution is fully rolled out.|
|Large implementations have a reduced level of the investments and resources that are needed to ramp up for each deployment, compared to a big-bang approach. |Scope creep can occur since project timelines are drawn out. There might be a tendency to incorporate changes and rework, which can affect the work for subsequent phases and their timelines.|

### Parallel rollout

In a variant of phased rollout approach, parallel rollout, the incumbent system isn't discarded but kept alive along with the new system. More than a rollout approach, it's a validation technique allowing users an opportunity to learn, test, and get comfortable with the new system. Typically, for a few months both systems are actively used and users are required to key in information in both systems.

With a parallel rollout:

- There is more effort required from the users as they double key information.

- It may be preferred by projects where the business risk is high and can't be easily mitigated by testing. At the same time, we need to be mindful of making sure the team isn't cutting corners on testing and training efforts.

- It's less and less popular due to the extra efforts and costs involved in keeping two systems.

Release strategy goes hand-in-hand with change management strategy as several activities of change management play a key input to successful rollout.

|Pro  |Con  |
|---------|---------|
|Less risk|High efforts and high costs|
|Users take their time to gradually plan to migrate to the new system|Needs for data duplication can get complicated. We recommend having a clear exit plan that is based on time or workload, such as closing all existing cases in the old system.|
||This approach can mask poor training and testing efforts.|

## Next steps

Check the following articles to learn more:

- [Implementation strategy](implementation-strategy.md)  
- [Choose a methodology for the Dynamics 365 implementation project](implementation-strategy-choose-methodology.md)  
- [Define a strategy for adoption and change management](implementation-strategy-define-strategy-adoption-change-management.md)  
