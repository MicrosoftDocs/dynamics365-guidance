---
title: Implementation strategy
description: Find guidance on the key aspects of a well-rounded implementation strategy that delivers on the promise of digital transformation. We define business drivers and quantifiable metrics to measure a successful implementation.
author: edupont04
ms.author: veneva
ms.date: 04/27/2023
ms.topic: conceptual
---

# Implementation strategy

Organizations embarking on a digital transformation journey consider implementing business applications as key critical milestones for their business success. **The journey from a business vision to a successful implementation of it requires the business and IT owners to define an overarching strategy that acts as a framework to plan for predictable outcomes.** An implementation strategy defines these strategic choices and decisions made in planning, implementing, and deploying Dynamics 365 applications.

Along with new technology comes substantial change to a company's business processes. It's critical to choose a process-focused, user-centric implementation strategy and methodology that not only supports digital transformation but also helps drive change management and user adoption. All of these factors are critical to making an implementation successful.

In this article, we explore common industry methodologies and look at common deployment strategies and high-level views on change management strategy.

## Key concepts

Key concepts that will help in defining a successful implementation strategy.

- Understand the Vision and Business drivers

- Agree on Key Success metrics

- Identify Roles and Responsibilities

- Identify and allocate right resources

- Allocate budget and funds

- Choose a Methodology

- Define the Deployment and Release management

- Change management

## Implementation strategy foundation

The foundation of a successful implementation begins with planning for key factors that define the overall implementation strategy. Let us explore these key considerations.

### Understand vision and business drivers

Project teams should be aware of the vision and strategic intent of the stakeholders. It helps the project team stay aligned on the project's vision if they have a clear grasp of the key reasons behind the implementation and a collective understanding of significant business challenges.

> [!TIP]
> Senior management and project sponsors must be clear about the *business requirements* and help *establish the scope and expected outcomes* of the project. These goals help drive any decisions that may be needed during the implementation cycle, such as prioritizing the delivery of certain functional features over others.

> [!TIP]
> It's equally important to map the default capabilities of Dynamics 365 to the business requirements. This way helps minimize customizations, and it makes the future updates easier without much rework.

At this stage, it's also crucial that senior management make sure that **both business and IT teams collaborate** on the implementation at the outset. The business teams own and design the process flows and can articulate their vision for the new solution. The IT team will help organize the technical teams, project coordination and ultimately deliver the solution. Without collaboration across such teams, there's high chances of misalignment, wrong expectation setting and solution not delivering full return on investment. Business requirements must be articulated and frozen with both teams in agreement. Another example of collaboration is planning for deployments. While Business can define and prioritize the requirements in the Minimum Viable Product (MVP), IT team can plan for the subsequent rollouts including the released features, timelines and the logistics.

This collaboration helps deliver a solution aligned with business needs and enables successful change management and a higher user adoption.

### Agree on key success metrics

After establishing a common understanding of the business challenges and priorities, it's equally important to have an agreement on what the **key performance indicators (KPIs) that measure success** look like. The KPIs should be tangible metrics, for example opportunity conversion rate, or average call handling time.

Understanding and identifying the KPIs is critical to ensuring the scope being delivered is aligned with the expectations from the business stakeholders and generates a tangible return on investment on the Dynamics 365 investments.

Some of the examples of success metrics/KPIs include:

- Improve the opportunity conversion rate from X % to Y % over Z period.

- Reduce sales cycle from X days to Y days over Z period.

- Increase net new customer adds from X to Y over Z period.

- Reduce average call handling time from X minutes to Y minutes over Z period.

- Improve service request turnaround time from X days to Y days over Z period.

The KPIs mentioned above aren't exhaustive. Each organization has specific KPIs that cater to their business scenarios. Each KPI that the organization identifies and prioritizes has a direct impact on the way that the final business solution is implemented. So, having a definitive list of metrics enables prioritization of the right use cases and allows stakeholders to gauge the project success in a tangible way.

### Identify roles and responsibilities

The customer and partner/system integrator teams should have clear views on exact roles and responsibilities shared between their teams. We often hear stories where the statement of work (SoW) or contract mentions high-level activities and doesn't go into enough details, resulting in confusion and finger-pointing during the project. There might be activities that are overlooked or underestimated, and activities with unwritten assumptions. The customer might assume their implementation partner will handle an activity, while the partner assumes their customer will handle that activity. This misalignment comes as a rude shock to the teams later on.

> [!IMPORTANT]
> Have the SoW or contract focus on the detailed activities with clear defintions of assumptions, roles, and responsibilities. Also mention considerations that are out of scope. This upfront and timely effort will save expensive and time consuming rework during the implementation stages.

The list of activities includes and isn't limited to:

- Business process modeling, documentation, and management

- User Interface (UI) and User Experience (UX)

- Data migration including sourcing, cleansing, mapping, transforming and importing

- Integration with other line of business applications and external systems

- Test strategy, planning, and execution

- Management and orchestration of user acceptance tests (UAT)

- Security design and role assignment

- Configuration management

- Analytics and BI reporting strategy, tools and design

- Cutover planning and execution

- Adoption and Change management

### Identify and allocate right resources

Setting up a productive team structure is critical to the success of the project. Identify the stakeholders, the owners of business processes, the team that delivers the projects, and the business users who can be engaged from the beginning of the project lifecycle.

The key roles required for all projects can often be grouped into two types of team structures.

- **Steering committee**  

  A group of senior stakeholders with the authority to ensure that the project team stays in alignment with KPIs. As they monitor progress, they can help make decisions that have an impact on the overall strategy, including budget, costs, and expected business functionality. Steering committees usually consist of members of senior management and leaders of business groups that are part of the identified rollouts.

- **Core implementation team**  

  This team does the actual execution of the project. For any Dynamics 365 implementation project, core implementation teams should include roles such as the following list:

  - Project managers  
  - Business subject matter experts  
  - Solution architects  
  - Functional and technical consultants  
  - Developers  
  - Testers  
  - Trainers  
  - Adoption and change management advisors  
  - User champions  

The engagement of process owners is critical to ensure complete understanding of business processes. Their understanding is required if any process changes result from alignment with built-in features. User representation should also be planned properly to adequately cover all the personas. Lack of availability of any of such roles may result in delays and/or incomplete understanding of processes and also impact user adoption. The involvement of process owners and users can be staggered depending on the implementation phase. Plan early on to allow business teams to make the required changes to their schedules and be able to contribute efficiently during the project lifecycle.

The project may require more roles depending on the scope and methodology. Some roles may need to join temporarily during the project lifecycle to meet specific needs for that period.

Learn more about team setup considerations at [Introduction to Success by Design](success-by-design.md) and [Project governance](project-governance.md).  

### Allocate budget and funds

Planning a budget for Dynamics 365 cloud applications typically includes costs such as the following list:

- Subscription  
- Storage  
- Implementation lifecycle activities including the following list:

  - Design  
  - Testing  
  - Deployment of the solution  
  - Migration from incumbent systems  
  - Training  
  - Change management  
  - Continuous improvements  

> [!NOTE]
> Dynamics 365 follows a periodic release pattern with weekly fixes, monthly, and six-month release waves. It is highly recommended to allocate budget towards building strong DevOps, CI/CD (Continuous Integration/Continuous Delivery) pipelines with sufficient test automation of functional scenarios/business processes in place that help in improving the Test regressions.

Project lifecycles require constant assessments with careful considerations and actions for the variance between budgets versus actual costs.

A common decision that most teams face is finding the right balance between delivering a high value solution faster by using the built-in capabilities versus extending the product capabilities to implement the business requirements and needs. Extending the Dynamics 365 applications not only requires initial development costs but also maintainability and supportability costs in the end. It's an area where implementation teams should carefully revisit the cost impact. In the cloud world with rapid availability of new features and capabilities, there's a need to rethink the investments required for extending the application. Learn more about assessing this impact at [Extend your solution](extend-your-solution.md).  

Project management teams should give weight to areas that help them stay aligned with the overall project goals and objectives. As project scope and timelines change, activities that fall towards the end of the project lifecycle are often cut from scope to meet budget constraints. These activities can include performance testing, data validation testing, training, and change management. When compromised, such activities can significantly reduce the quality and success of the implementation. Revisit the project goals and success factors that are defined during the initial stages, and carefully revise the scope and timelines without compromising on overall quality and user centric approach.

We recommend an overall approach since it helps define the total impact by identifying the cost, benefit, flexibility, and risk factors that affect the investment decision. Such an approach can help  organizations improve their overall business goals of winning, serving, and retaining customers.

> [!TIP]
> Forrester's Total Economic Impact (TEI) of deploying various Dynamics 365 apps is a good recommendation to assess the costs and benefits associated with Dynamics 365 Implementation.

Some of the exclusive TEI deliverables by Forrester are:

- [The Total Economic Impact of Microsoft Dynamics 365 Finance And Supply Chain Management](https://info.microsoft.com/ww-Landing-Forrester-Total-Economic-Report.html)

- [The Total Economic Impact of Microsoft Dynamics 365 Field Service](https://info.microsoft.com/ww-Landing-TEI-of-D365-for-Field-Service-eBook.html?Lcid=En-US)

- [The Total Economic Impact of Microsoft Dynamics 365 Customer Service](https://info.microsoft.com/ww-landing-TEI-of-D365-customer-service.html?lcid=en-us)

## Conclusion

When a team defines an implementation strategy, they set clear expectations and guidelines for the team and wider business on how the project goals are going to be attained. It helps define a clear translation of business goals into a structured implementation plan.

To summarize, a well-rounded implementation strategy includes the following items.

- Builds a common understanding of vision and success metrics.

- Includes both business and IT teams right from the start of the project.

- Has a clear understanding of roles and responsibilities between customers and partners.

- Identifies the methodology based on the specific factors that are driving the implementation.

- Follows the tried and tested approach that the methodology defines. Don't leave activities out just for convenience.

- Helps to take feedback early in the implementation journey by doing a "show and tell" after each sprint/phase depending on the chosen methodology.

- Keeps organizational culture under consideration while choosing a methodology. Organizations that have followed a traditional approach such as Waterfall may need more change management planning to embark on a modern approach such as Agile or Hybrid.

- Considers which industry practices may also have a bearing on methodology. Some industries may have their own tailored approach and that needs to be kept into consideration.

- Formulates a focused approach towards user adoption by creating a change management plan.

- Plans an approach of communicating to various stakeholders, including leadership and end users.

- Continues to improve throughout the process—solicit end-user sentiment and act!

## Next steps

Check the following articles to learn more:

- [Choose a methodology for the Dynamics 365 implementation project](implementation-strategy-choose-methodology.md)  
- [Define a strategy for deployment and release](implementation-strategy-define-strategy-deployment-release.md)  
- [Define a strategy for adoption and change management](implementation-strategy-define-strategy-adoption-change-management.md)  

<!--
## Quick links

- Access the chapter in the book > [Implementation strategy](https://aka.ms/d365-chapter-implementation-strategy)

- Access the implementation guide > [Implementation guide](https://aka.ms/D365ImplementationGuide)-->
