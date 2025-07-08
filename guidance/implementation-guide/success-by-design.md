---
title: Introduction to the Success by Design framework
description: Learn about the Success by Design framework with best practices from Microsoft to help project teams implement solutions with Dynamics 365.
ms.date: 12/02/2024
ms.topic: concept-article
author: edupont04
ms.author: veneva
ms.reviewer: edupont
ms.custom:
  - evergreen
---

# Introduction to Success by Design

> *One of the primary goals of the implementation guide is to democratize the practice of Success by Design by making it available to the entire community of Dynamics 365 implementers.*

Success by Design is a framework and practice created by Microsoft to help project teams implement Dynamics 365.

Based on thousands of real-world customer projects, Success by Design is the sum of our Dynamics 365 implementation experience. It offers topic-specific reviews and prescriptive guidance (approaches and recommended practices), which provide a reliable path to project success. Success by Design is intended to be used by Dynamics 365 system integrators, independent software development companies, and customers as a means to better architect, build, test, and deploy Dynamics 365 solutions.

Microsoft recognizes that Success by Design doesn't guarantee implementation outcomes for our customers. But we're confident that it will help you achieve your project's goals while enabling the desired digital transformation for your organization.

For our partners, Microsoft is confident that Success by Design, coupled with your implementation methodology and skilled resources, will increase your team's effectiveness in delivering successful Dynamics 365 projects to your customers.

This article focuses on the fundamentals and practice of Success by Design and its desired result: Dynamics 365 projects whose technical and project risks are proactively addressed, solutions that are roadmap aligned, and project teams that are successful in maximizing their organization's investment in Dynamics 365 cloud services.

## Success by Design history

As demand for Dynamics 365 cloud services increased across the enterprise, Microsoft identified the clear need to change the way we thought about evolving our services and our responsibility to customers and partners. We recognized that it wasn't enough to design a platform containing a set of features. We needed to also understand what it takes to deliver a fully functioning, end-to-end solution that runs the mission-critical processes of our customers' businesses. From this need, Success by Design was born.

Microsoft believes that customer success is the precursor to every Dynamics 365 product development decision. As a result, questions fundamental to product development now challenge our engineers at every step of the process:

- In what way must each product feature be delivered to ensure customer success?

- How do we make Dynamics 365 apps valuable, durable, reliable, and performant?

- What aspects of the product should be jettisoned because they don't meet fundamental customer success criteria?

Such questions have led to the successful transition of 100 percent of Microsoft Dynamics 365 online customers to run on one version for the first time in decades. And there are more benefits, such as the following items:

- A dependable and safe deployment process
- A steady and coherent feature release cadence (including many overdue feature deprecations)  
- A reliable and performant platform that delivers customer value  

But product is only one half of the customer success equation. Over the past few years, Microsoft has put equal emphasis on two needs that we must provide:

- Prescriptive guidance and recommended practices to ensure a smooth implementation project  
- A properly designed and built Dynamics 365 solution that successfully transforms business operations  

This push has also resulted in the transformation of Microsoft's FastTrack for Dynamics 365 service. The goal is that our community of Dynamics 365 implementers, customers, and partners, has access to Success by Design.  

## Make Success by Design your own

Enabling Dynamics 365 project teams to practice Success by Design means an ongoing commitment by Microsoft to provide the community of implementers, customers, and partners, best-in-class business applications, along with the latest in Success by Design project resources.

It also means project team willingness to incorporate the practice of Success by Design into their overall project approach, regardless of implementation methodology or the Dynamics 365 product being implemented. At its best, Success by Design fortifies a project team's chosen implementation methodology with a model for product-aligned project governance.

No matter where you find yourself in your Dynamics 365 implementation, it's critical that the project teams remain focused. The common pressures of time, budget, and resources can prevent the teams from pausing to understand and address technical and project risks before it's too late in the project lifecycle.

To this end, the sections in this article define the following items:

- What Success by Design is  
- Which benefits it can bring to implementations  
- How project teams can use it to accelerate customer success throughout the implementation of Dynamics 365  

> [!NOTE]
> [FastTrack for Dynamics 365](https://dynamics.microsoft.com/fasttrack/) is a customer success program run by Microsoft's Dynamics 365 product engineering team that helps customers implement Dynamics 365 apps and realize business value faster. The practice of Success by Design is fundamental to FastTrack's approach, but the Success by Design framework is available for use on any Dynamics 365 implementation project.

## Success by Design objectives

Success by Design is prescriptive guidance (approaches and recommended practices) for successfully architecting, building, testing, and deploying Dynamics 365 solutions. Success by Design derives from the experience of Microsoft's FastTrack program, which has helped our customers and partners deliver thousands of Microsoft's most complex Dynamics 365 cloud deployments.

In Success by Design, reviews are exercises in reflection, discovery (observation), and alignment (matching to known patterns). Project teams can use reviews to assess whether their implementation project is following recommended patterns and practices. Reviews also help project teams to identify (and address) issues and risks that may derail the project.

Success by Design should be used as an adjunct to the project team's chosen implementation methodology for the following benefits:

- Reduced risk due to early detection of problems

- Alignment to recommended practices

The result is a roadmap aligned solution architecture that is performant, scalable, and future-proof. (Acknowledging the possibility that feature deprecations or other changes to product roadmap in compliance with Microsoft policy may occur.)

For interested customers, Microsoft recommends that project leaders team up with their implementation partner to enable Success by Design within their project. In addition to the guidance that we provide here on Microsoft Learn, it's highly recommended that project teams ready themselves by enrolling in the [Success by Design training](/learn/modules/success-by-design/).

> [!TIP]
> Across Dynamics 365 guidance content, we use the term *finance and operations apps* to cover Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce, Dynamics 365 Human Resources, and Dynamics 365 Project Operations.

## Success by Design phases

Success by Design maps the Dynamic 365 implementation lifecycle into four methodology-agnostic phases: Initiate, Implement, Prepare, and Operate. In this section and the following sections, we outline the Success by Design phases, their relationship to Success by Design reviews, and the desired outputs and outcomes.
<!--  Commenting out until we can have an illustration with the 5 stages.
:::image type="content" source="media/success-by-design-phases.png" alt-text="Four bubbles to represent the four phases, Initiate, Implement, Prepare, Operate." lightbox="media/success-by-design-phases.png"::: -->

## Strategize

In the **Strategize phase**, the project team is in discovery mode, gathering and validating business requirements, finalizing the high-level solution approach. All implementations should have a well-rounded implementation strategy that delivers on the promise of digital transformation. The section also covers the environment strategy, and the organizational strategy.

### Initiate

In the **Initiate phase**, the project team makes inroads to define all in-scope workstreams, and updating the project plan to reflect these updates. When the project team has produced the high-level solution design (in the *Strategize** phase) and the related project workstreams are more or less defined, Success by Design begins with the *Solution Blueprint Review*. Learn more in the section [Success by Design reviews](#success-by-design-reviews).  

### Implement

In the **Implement phase**, the project team is focused on building the solution per the agreed upon solution design and scope. This phases introduces *Implementation Reviews* that come from the findings and recommendations of the Solution Blueprint Review. As we learn in the section [Success by Design reviews](#success-by-design-reviews) section, Implementation Reviews help you more deeply address questions related to the specific aspects of the solution design (data model, security, and integration) and implementation practices (ALM, testing strategy). Implementation Reviews are meant to fully address the risks identified during or after the Solution Blueprint Review but before the solution build is too far along.

### Prepare

By the **Prepare phase**, the solution has been built and tested and the project team is preparing for the final round of user acceptance testing (UAT) and training. Additionally, all necessary customer approvals have been granted, information security reviews completed, the cutover plan defined (including go/no-go criteria), mock go-lives scheduled, the support model ready, and the deployment runbook completed with tasks, owners, durations, and dependencies defined. At this point, the project team uses the Success by Design Go live Readiness Review to identify any remaining gaps or issues.

### Operate

In the **Operate phase**, the customer solution is live. The goal of this phase is stabilization and a shift in focus towards functionality and enhancements that are earmarked for the next phase of the project.

## Success by Design reviews

With a high-level understanding of Success by Design phases, we now turn to Success by Design reviews, which are also sometimes referred to as Success by Design workshops.

Each review raises questions that serve as points of reflection that project teams can use to generate important discussion, assess risk, and confirm that best practices are being followed.

The **Solution Blueprint Review** serves as the starting point of Success by Design. We suggest the Solution Blueprint Review to be a mandatory review for the project because findings that come from it lead to **Implementation Reviews**, which offer project teams the opportunity to drill down into topic-specific areas where deeper dives are deemed necessary for further understanding project and solution risk. Finally, the **Go live Readiness Review**, which we also suggest as a mandatory review, is the last stop for assessing any remaining risks before go live.

The following image illustrates that Success by Design reviews aren't to be conducted as abstract exercises separated from the project. Rather, the scheduling and implementation of each review relies on the availability of key project artifacts and the readiness of the project team to discuss them.

> [!TIP]
> The image predates the change to Success by Design that added an earlier stage with some of the elements from the *Initiate* phase. Read the image so that the *Initiate* column covers the *Strategize* and *Initiate* phases.

:::image type="content" source="media/success-by-design-outputs.png" alt-text="Diagram with outputs for each Success by Design phase." lightbox="media/success-by-design-outputs.png":::

> [!NOTE]
> Other implementation articles address elements of Success by Design, but for the most comprehensive coverage of Success by Design framework, please refer to the [Success by Design training](/learn/modules/success-by-design/) on Microsoft Learn. Taken together, the guidance in the Methodology guide, used alongside the Success by Design framework, should equip project teams for better, more successful project outcomes.

## Success by Design outputs

With a basic understanding of Success by Design's objectives, phases, and review flow, it's important to pause to understand the makeup of review outputs and their purpose, findings, and recommendations.

As described in the section [Success by Design reviews](#success-by-design-reviews), reviews include project artifacts that the project team produce, and other information such as formal or informal project touchpoints. The availability of such information points to the readiness of the team to schedule and conduct Success by Design reviews. Additionally, project teams may rely on Microsoft for telemetry and other tools to inform review discussions and generate review outputs.

The primary review outputs fall into two related categories: findings and recommendations.

**Findings** come in three types:

- **Assertions** - Findings that capture noteworthy aspects of the solution or approach. Assertions highlight what the project team is doing right, typically in line with best practices.

- **Risks** - Findings that could potentially influence the implementation negatively if not mitigated.

- **Issues** - Findings that are currently impacting implementation negatively or will do so if not resolved.

Findings should include as much detail as possible and be matched to known patterns. Findings matched to known patterns often yield insights that lead to recommendations or actions necessary to resolve the issues identified.

:::image type="content" source="media/success-by-design-findings.png" alt-text="Three boxes with arrows to illustrate that findings are matched to known patterns that then lead to recommendations." lightbox="media/success-by-design-findings.png":::

To better illustrate this point, consider this customer example:

A global corporate travel company is implementing Dynamics 365 Customer Service to drive its call center transformation. As the project team digs into the business's requirements, they learn that the Dynamics 365 solution must account for integration with multiple legacy systems (many with high transaction volumes). Additionally, the requirements point to a business-mandated customization that the project team agreed couldn't be achieved using out-of-the-box functionality.

In preparation for the Solution Blueprint Review, the project team parses these and other details. They must also confirm that solution performance testing was purposely left out of the project scope on the assumption that Microsoft's Dynamics 365 cloud service should be performant on its own.  

> [!TIP]
> It's true that Microsoft is responsible for delivering a reliable and performant cloud service to its customers. But it's our experience that solution design and the resulting configurations, customizations, and partner solutions to achieve that design may play a role in impacting overall Dynamics 365 solution performance.

In this example, the Dynamics 365 solution is projected to support 4,000 users at scale, including the multiple integrations and a key customization mandated by the business. So the project team's findings are clear: keeping solution performance testing out of scope is a risk that negatively impacts the project. Among other findings and recommendations not covered in this example, the project team's architect (who led the Solution Blueprint Review) recommends that the project Steering Committee approves adding solution performance testing into the test cycle.

The architect's findings are summarized as follows:

- The solution requires custom development to meet its business requirements.

- Performance testing isn't included in the test cycle.

- Following best practices, solution performance testing should be added to the test cycle  

  If necessary, the solution performance workshop should be scheduled to further explore the risk and report any other findings back to the project Steering Committee.

The architect's findings and recommendations are based on careful review that calls out the lack of solution performance testing as a risk, which the project team must address to avoid downstream impact on the project.

:::image type="content" source="media/success-by-design-measures.png" alt-text="Extends previous illustration with success measures for the recommendations that are based on review and findings. The success measures are risks, assertions, and issues." lightbox="media/success-by-design-measures.png":::

In Success by Design, findings link observations to known patterns that invite actions necessary to address project risks and issues.

## Track success measures

One more step remains in the Success by Design process: tracking success measures. After completing Success by Design training, you may decide to create your own success measure tracking template or make use of FastTrack's template. Otherwise, project teams can use Success by Design tooling (as served by FastTrack or your implementation partner) to track success measures for their project.  

### What are success measures?

By its very nature, Success by Design is a project specific endeavor. For anyone practicing Success by Design across one or many Dynamics 365 projects, the question arose: How do we measure the health of just one of those many projects? Success measures allow us to do just that.

Success by Design empowers project teams to track the health of projects across seven categories and over 30 success measures. The figure below highlights these categories and related success measures.

:::image type="content" source="media/success-by-design-tracking-measures.png" alt-text="Illustrates how you can track success measures across architecture, key areas, implementation, product features, fit for purpose, project governance, competency, and support." lightbox="media/success-by-design-tracking-measures.png":::

Tracking success measures is simple: After a Success by Design review or other compelling project event, your FastTrack Solution Architect or partner architect will access Microsoft's Success by Design tooling and update the relevant success measures for the project. Success measure updates are either red, yellow, or green, and include project-related details relevant to the success measure.

### Why are success measures important?

Success measures are important because they provide access to micro and macro project health trends. Tracking success measures for a single project allows stakeholders to assess the overall health of the project at a glance. Similarly, the benefit of tracking success measures over 10, 20, or 100 projects is that Microsoft, the partner, or the customer project team can see patterns that may be impacting them. For example, macro-level tracking may yield an application lifecycle management (ALM) problem. Access to this data allows Microsoft or the partner to understand whether it's a project or product problem, and gain insights on how to fix it.

## Conclusion

Success by Design equips project teams with a model for technical and project governance that invites questions and reflection, which leads to critical understanding of risks that might otherwise go unnoticed until too late in the project.

Considering the pace of cloud solutions and the investment that organizations make in Dynamics 365 software and implementation costs, even the most experienced customers and partners with the best methodologies will benefit by incorporating Success by Design into their projects.

Microsoft believes that every business is in the business of creating great customer experiences. To achieve that, business applications must do more than just separately run your back office, marketing, supply chain, or even field operations. They must give you the agility to remove every barrier in your way. When this happens, business applications become more than just operational solutions. They become resilient solutions that enable the digital feedback loop and adapt to customer demands, delivering stronger, more engaging experiences around the products you make and services you provide.

## Success by Design evolution

From the moment that FastTrack for Dynamics 365 was born, Microsoft began to ask itself: How can we change the FastTrack approach so that our solution architects can address technical and project risks of a project before they manifest as problems impacting our customer's investment in Dynamics 365? Our internal process evolve, team members learn and share their knowledge, and Success by Design evolves over time. Get [an inside look](success-by-design-story.md) into how we developed the Success by Design framework. Otherwise, check the links in the next section.  

## Next steps

- [Implement cloud solutions](implementing-cloud-solutions.md)  
- [Drive app value](drive-app-value.md)  
- [Implementation strategy](implementation-strategy.md)  
- [Solution architecture design pillars](solution-architecture-design-pillars.md)  
- [Process-focused solution](process-focused-solution.md)  
- [Project governance](project-governance.md)  
- [Define the organizational structure in Dynamics 365](../organizational-strategy/define-organizational-strategy.md)  
- [Bring successful solutions to customers with application lifecycle management (ALM) strategies](application-lifecycle-management.md)  
- [Test your Dynamics 365 solution before deployment](testing-strategy.md)  
