---
title: Classic structures
description: Read about structures that are part of successful implementation projects with Dynamics 365 apps.
author: TimoGossen
ms.author: timogoss
ms.date: 06/27/2023
ms.topic: conceptual
---


# Classic structures in project governance

Most, if not all, business application projects have the common, classic governance structures in place. This section doesn't give a general overview of historically well-known disciplines around these common governance areas; instead we look at how to assess the true effectiveness of these processes and controls in practice. The mere presence of these classic governance structures such as steering groups, program boards, or risk registers can sometimes deceive projects into thinking that they have adequate active governance. Let's dig deeper into these areas to explore how we can get better insight into their function and evaluate their effectiveness.

## Steering groups

Most projects have some form of steering group in which the project sponsor, senior business stakeholders, and project leaders meet regularly to discuss and review the project. A lesson learned from participating in multiple such steering groups across multiple projects is that the effectiveness of these meetings varies hugely. When the purpose of steering group meetings is diluted or unclear, it can impact the effectiveness of the steering group. The same is true when project status reporting isn't easily understood, accurate, or actionable.

:::image type="content" source="media/projectgovernancesteercopurpose.png" alt-text="Steerco purpose":::

### Steering group meetings

Steering group meetings can negatively influence project success. For example, if the project manager presents the status and the steering group just checks in with little understanding of the details of the project, no direct engagement, and a lack of knowledge to challenge and explore issues more deeply. Steering groups that rely entirely on project status updates with only a perfunctory amount of independent analysis or review are often surprised by a sudden crisis, resulting in delays and dissatisfaction.

An efficient and effective steering group has leadership team participants that understand and perform their primary function of steering the project. They're required to invest the time to understand the content of the project at a sufficient depth. As a result, they can read between the lines of the project status report, ask the right questions to understand how and where they can help, and proactively direct the project.

Apply similar, regular assessments of the effectiveness of other such boards, like the change control board or the design authority board.

## Project status reporting

Accurate, meaningful, and actionable identification and reporting of the project status is the lifeblood of a project. Business application implementations often involve complex, multiple strands of work, all of which need to come together seamlessly and on time. Multiple parties are often involved in the project delivery, including the following roles:  

- Business SMEs  
- Business IT department  
- Business project managers, and their equivalent roles from the implementation partner, and other third parties  

In addition to the main functional and technical delivery, there are multiple other disciplines, like data migration and security. All these roles have their own specialist tasks to perform, and managing and monitoring all these different types of tasks to provide a coherent project status isn't easy.

Additionally, specialist teams may provide an overly technical view of the status in terms that only that team understands. Often, project-level status reporting is driven by fit gap progress, which isn't necessarily the critical part of the project. Consider the following questions when you look for effective project status reporting to the steering group.

- **Is the project status meaningful and actionable for the intended audience?**

  For example, when presenting internally to your own specialist team, a detailed and technical view is appropriate. However, when presenting the status to a steering group or to nonproject team members, consider how to express the status in terms that are well-understood and actionable. Consider how the status can be communicated in business terms to the steering group, and avoid unnecessary jargon that should be translated into more meaningful terms.

- **Is there evidence to believe that the project status is accurate?**

  Consider how the project status data has been gathered, analyzed, summarized, and presented. Understand the level of uncertainty associated with the data. Is there a history of the project status data and related estimates versus actuals that can provide some idea of certainty? Steering groups must consider the degree of uncertainty associated with the status when they assess risks and make critical decisions on moving or adding resources, approving budgets, and setting or relying on timelines. This means testing the accuracy of the status by looking at it from multiple angles to ensure that it provides robust and actionable data.

- **Is there a comparison between the planned and actual status?**

  Project status reports only have meaning when they show an easily understood comparison between the planned status and the actual progress. The report must be able to answer questions like "Are we on track?" "What is the size of the remaining work to completion?" "What do we, as the steering group, need to do to get the project on track and keep it on track?" The absence of a comparison of planned work to actual and remaining work doesn't allow the steering group to take necessary actions to help recover.

## Risk register

Most projects have some form of a risk register. When used well, this register is a good way to communicate risks and help teams focus their attention on removing barriers to success. The following are examples of ineffective use of risk registers:

- Risks that are of little practical value to the project are being used to shrug responsibility or provide cover against blame in the future.

- Risks remain on the register for a long time with new comments and updates being added weekly at each risk review meeting, but with no resolution. This implies that either the risk isn't getting the attention it deserves or it's difficult to resolve and consuming more resources without results. In any case, you should either treat risks stuck in this loop urgently with focus or accept them with a mitigation so they don't drain the project over time.

- Risk priorities don't reflect the project priority at that stage of the project. You should take care to ensure that the risk register doesn't create a parallel project effort with its own priority and path. Risks and issue resolution should be incorporated as part of the priority assessment within the main project delivery.

- The risk register has a large number of risks, many of which are stagnant. Consider how many risks the project can realistically work on at any given time and trim the register according to real project priority.

## Stage gates

Stage gates or milestone-driven planning and reviews are a common feature of most business application projects, including more agile projects. These milestones are regarded as important checkpoints spread throughout the project timeline, which the project can only pass through if they have met certain criteria. The reality of many projects is that the checkpoints don't always perform their intended function. There may be several reasons for this, and projects should examine if they suffer from the following limitations:

- **Criteria for the milestone are unclear**  

  You should strive to create explicit criteria for entering and exiting a milestone. If the criteria are difficult to measure, it's difficult to take unequivocal decisions based on data.

- **Exit and entry criteria aren't respected**  

  Projects are typically under great pressure to get past one milestone and move into the next phase. Maybe they suffer from resource usability or commercial payment triggers. Maybe the project optimistically believes that it will somehow catch up with the overdue tasks that didn't meet the milestone criteria. Sometimes a project is also pressured to move to the next phase because it implies progress. This self-delusion can create more risks in the project; uncontrolled disturbances in project deliverables can delay the ultimate goal of a successful go live. The debt incurred by skipping the criteria has to be paid back at some point; the later it's resolved, the higher the cost. When considering allowing a milestone to pass when it hasn't met all its criteria, project leadership should strongly consider the following aspects:

  - The nature and size of the incomplete tasks  
  - Precisely how to address these tasks  
  - How do the lagging tasks affect on dependent tasks  

  This allows for a managed transition between milestones with the risks fully understood and a clear and realistic action plan for the stragglers.

- **Milestones don't reflect true dependency**  

  From a project lifecycle perspective, a milestone should have the primary purpose of confirming that the project has satisfactorily completed the precursor tasks so that it's safe, efficient, and meaningful to start the tasks of the next stage. There may be other perspectives, such as commercial ones to trigger stage payments or just periodic points for the project to review progress or cost burndown. But here, we focus on a project lifecycle point of view. Some common examples of stage gate criteria are as follows:

  - **To-be business processes defined**  

    An approval step from the business to confirm the business process scope helps ensure that prior to spending much effort on detailed requirements and design, the process scope has been well established and agreed upon.

  - **Solution blueprint defined**  

    The solution blueprint helps ensure that the requirements have been analyzed and understood sufficiently well to be able to define an overall, high-level design that is confirmed as feasible. Additionally, the key design interrelationships and dependencies are established before working on the individual detailed designs.

  - **Formal user acceptance testing start agreed**  

    Starting formal UAT with business users tends to be the final, full formal test phase before go-live, with the expectation that go-live is imminent and achievable. Prior to starting this phase, it makes sense to validate the readiness of all the elements to ensure that this test phase can complete within the allocated time period and meet the necessary quality bar.

Consider the various milestones that help with a true understanding of readiness, especially those that help you better understand when to start dependent tasks, such as feature complete, code complete, code frozen, business data validated in Dynamics 365, or solution ready for user acceptance testing, and determine what entry and exit criteria would help.

## Design and change boards

A project with multiple parties involved in the design and delivery tend to have some form of design review board that ensures compliance with the enterprise IT policies and standards. This board also ensures that the proposed designs from the project (and especially design changes) are fit for purpose.

Effective design review boards (also called architecture review boards or design change boards) tend to have a good grasp of the overall solution blueprint. In addition to reviewing any individual design, they can ensure new designs and changes operate within the boundaries of the solution blueprint and won't adversely affect other designs.

The design review board should also have representatives, not just from the project, but also from the wider business and IT, to help ensure the business case for the design is sound and the impact on related systems (integrations) and overall enterprise architecture are considered. Another characteristic of a successful design review board is that they have minimum bureaucracy and their focus is on helping the project to move as securely and as fast as possible.

The process by which a design review board actually functions is as important as its constituents and roles and responsibilities. Design review boards should communicate the solution blueprint boundaries and design standards expected so projects can proactively make sure that they're working within the expectations.

For the best project velocity, you should set an expectation that the reviews will be interactive and expected to be resolved within a single iteration. This requires the design review board to be pragmatic and well prepared. It also requires the project to have the discipline to provide sufficiently detailed proposed design information. This process needs to be organized and communicated as part of the project governance in the Initiate phase so you're not trying to establish these practices during the intensive pressures of a running project implementation.

## Next steps

- [Project goals](project-governance-project-goals.md)  
- [Project organization](project-governance-project-organization.md)  
- [Project approach](project-governance-project-approach.md)  
- [Key project areas](project-governance-key-project-areas.md)  
- [Project plan](project-governance-project-plan.md)  
- [Conclusion](project-governance-conclusion.md)  
- [Checklist: Project Governance](project-governance-checklist.md)  
- [Case study](project-governance-case-study.md)  
- [Project governance for Dynamics 365 implementation projects](project-governance.md)  
