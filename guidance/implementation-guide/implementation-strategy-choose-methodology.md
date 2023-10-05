---
title: Choose a methodology
description: Find guidance for how to choose the right methodology to manage the Dynamics 365 implementation project. 
ms.date: 04/17/2023
ms.topic: conceptual
author: edupont04
ms.author: veneva
---

# Choose a methodology for the Dynamics 365 implementation project

Before we discuss choosing a methodology for your Dynamics 365 project, we need to understand why a methodology is important for Dynamics 365 projects.

## Why methodology is important

A methodology is a prescriptive definition of activities to be undertaken for a given project or engagement. It describes the use of a collection of methods to achieve predictable outcomes.

Methodology is the core of project execution that allows the team to take the right path towards:

- Improved consistency and predictable outcomes.

- Setting clear definitions of project phases, milestones, deliverables, and entry and exit criteria to each phase.

- Setting clear definitions of roles and responsibilities required for the project.

- Reducing risks of missing critical activities required for a successful outcome.

Following a methodology is akin to taking a planned journey. The roadmap to success involves the following actions:

- **Plan ahead**  

  Ensure you have clearly defined the destination (project scope), and have all the right tools (resources, governance, and methodology) and checklists (project monitoring) before starting this journey.

- **Know the road**  

  Define the route, or solution blueprint, to set clear expectations on start and end dates for milestones. This way, you can meaningfully monitor progress, and the team understands what is expected from them.

- **Avoid pitfalls**  

  Follow proven best practices to minimize risks, costs, and scope creep.

- **Get there faster**  

  Take advantage of strategies that help you save time and money. Plan, action, and regularly monitor and adjust to ensure you're taking the most efficient route to your destination.

- **No surprise**  

  Delight users by delivering a user centric solution and business stakeholders by delivering results on-time and within budget.

:::image type="content" source="media/impl-strategy-roadmap-to-success.png" alt-text="Illustrates the five steps on the roadmap to success outlined before the illustration.":::

> [!NOTE]
> Be wary of external factors that can derail the planning. Important to consider the mitigation plans to accommodate such unexpected factors that may be beyond the project team's control.

### Choose an implementation methodology

Let us take a look at the specific methodologies that can be used for a successful Dynamics 365 implementation.

We often see three types of models used to implement Dynamics 365 Business Applications projects.

- **Waterfall model**  

  A delivery execution model based on a sequential series of phases that flow steadily from conception through initiation, analysis, design, development, testing, deployment, and operations, to maintenance.  

- **Agile model**  

  Agile development isn't a methodology in itself, but an umbrella term that describes several methodologies. Some of the industry known methodologies are Scrum, XP, DSDM, Sure Step for Agile (for Business Applications).

  - **Scrum methodology**  

    A delivery execution methodology based on agile principles where requirements are in flux or unknown prior to beginning a sprint. Sprints involve requirements analysis, design, build, test, and user review. Sprints are a fixed duration (such as 30 days), as illustrated below.

    :::image type="content" source="media/impl-strategy-scrum.png" alt-text="A product backlog leads to a sprint backlog that leads to a sprint with 30 days of 24 hours that then generates working increments of the software.":::

- **Hybrid model**  

  A delivery execution model based on agile principles. You define, analyze, and prioritize requirements in the context of business processes, and you generate an overview design solution blueprint before you begin the sprints. Sprints involve refining designs, build, test, and user reviews. Sprints can be of varying durations.

> [!NOTE]
> Iteration and sprint is a timeframe in which teams deliver incremental value in the form of working tested software. Iterative approaches use the term iterations while Scrum approaches use the term sprints.

> [!NOTE]
> The Success by Design framework is methodology agnostic. It supports proactive guidance and predictable outcomes irrespective of chosen methodology. Learn more at [Introduction to Success by Design](success-by-design.md).  

Now let's take a deeper look at each of these methodologies.

### Agile

An agile implementation is an iterative approach that uses iterations or sprints.

In Dynamics 365 implementation projects, many requirements are covered by out-of-the-box capabilities. There are specific challenges and tasks that you must manage and mitigate as part of the project methodology with a backlog of user stories. You carve out plans from that backlog. With the plans, you define iterations or sprints for development and testing. Each sprint covers a number of user stories that outline the requirements.

Agile promotes a collaborative process between the resources that own and specify the requirements for the solution and the resources responsible for the development and rollout of the solution.

The idea is to release software faster, take early and regular feedback, adapt, and release again. This cycle continues until all the requirements are met or the backlog is cleared.

An example of agile practices using the methodology prescribed by "Sure Step for Agile" is shown in the following complex diagram:

:::image type="content" source="media/impl-strategy-agile.png" alt-text="Agile preparation with stages for analysis, design, development, deployment and operation leads to agile execution with 30-day sprint cycles and daily sprint cycles.":::

### Waterfall

The waterfall approach to solution delivery is a sequential process. It depicts a linear flow of activities from one phase to another, and it culminates with the solution being promoted to production and then into operation.

It's a traditional methodology for implementing on-premises business applications. It-s a linear, noniterative approach of implementing and delivering projects.

The phases, milestones, and deliverables are clearly defined, and you only move to the next phase when a prior phase is completed.

In the modern cloud world, early stakeholder buy-in is critical, which requires delivering quicker results making the waterfall technique not suitable.

An example of the Waterfall model as prescribed in Sure Step Methodology is depicted in the figure below.

:::image type="content" source="media/impl-strategy-waterfall.png" alt-text="Table with five columns for analysis, design, develop, stabilization, and deploy, and rows for organization, solution, and technology.":::

### Hybrid

In the current landscape of rapidly changing business needs and changing technology trends, projects commonly adopt a hybrid approach. It's a combination of waterfall and agile practices that implementation teams use to meet their project needs. This way, teams can tailor an approach for a successful implementation of Dynamics 365. The hybrid approach is our recommended approach for Dynamics 365 engagements.

The figure below shows an example of a hybrid approach, based on Dynamics Sure Step 365.

:::image type="content" source="media/impl-strategy-hybrid.png" alt-text="Process goes through stages for mobilization, initiation, solution modeling, build, solution testing, deployment, support transition, and operation.":::

With this approach, we can manage initial activities such as initiation and solution modeling. It also supports final activities in a noniterative way, such as system integration tests, user acceptance tests, and the release to production. The build activities, such as requirement detailing, design, development, and testing, are completed with an iterative approach.

The hybrid approach helps provide early visibility into the solution. It allows the team to take corrective actions early on in the overall cycle. This approach is considered to use the best of both waterfall and agile approaches, and it's a win-win for most sizes of implementation.

In the hybrid approach, the focus is on a regular cadence of iterative and incremental releases of software features.

> [!NOTE]
> We recommend that stakeholders participate in the process, especially in the business validation reviews that happen after each sprint cycle. These reviews are placed at regular intervals during the project schedule. They allow for faster valuation and better stakeholder buy-in.

Through these reviews, stakeholders get an opportunity to see working software, have discussions with the team, and provide early feedback. The readiness of business processes is validated for production use by business users. They're shown the incrementally improving readiness across all the components in the system as working software, like design, data configuration, data migration, and so on.

The idea is to get early feedback and validation from the business team on the business requirements scope and understanding. With this approach, the project can showcase working solutions faster than other methodologies, and it achieves a higher rate of implementation success.

## Next steps

Check the following articles to learn more:

- [Implementation strategy](implementation-strategy.md)  
- [Define a strategy for deployment and release](implementation-strategy-define-strategy-deployment-release.md)  
- [Define a strategy for adoption and change management](implementation-strategy-define-strategy-adoption-change-management.md)  
