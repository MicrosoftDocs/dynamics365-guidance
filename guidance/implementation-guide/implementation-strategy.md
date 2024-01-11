---
title: Plan an implementation strategy
description: Learn how to define a clear and effective implementation strategy for Dynamics 365 that aligns with your vision, business drivers, success metrics, roles, budget, and methodology.
author: edupont04
ms.author: veneva
ms.date: 01/05/2024
ms.topic: conceptual
ms.custom:
  - ai-seo-date:01/05/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: 
  - AI-contribution
---

# Plan an implementation strategy

If you're embarking on a digital transformation journey, implementing business applications is a key milestone for your success. To turn your vision into reality, you need an implementation strategy that acts as a framework for planning and delivering predictable outcomes. An implementation strategy defines the strategic choices and decisions you make when you design, test, deploy, and operate Dynamics 365 applications.

Implementing new technology also involves substantial changes to your business processes. You need to choose a process-focused, user-centric implementation strategy and methodology that supports digital transformation and drives change management and user adoption. These factors are critical for making your implementation successful.

In this article, we explore common industry methodologies and look at deployment strategies, change management strategies, and key concepts for defining a successful implementation strategy.

## Key concepts

Understanding the following key concepts will help you define a successful implementation strategy:

- Understand the vision and business drivers
- Agree on key success metrics
- Identify roles and responsibilities
- Identify and allocate the right resources
- Allocate budget and funds
- Choose a methodology
- Define the deployment and release management
- Change management

### Understand vision and business drivers

Your project team should know the stakeholders' vision and strategic intent to help them stay aligned with the vision and understand the main reasons and challenges behind the implementation.

Senior management and project sponsors must be clear about the *business requirements* and help *establish the scope and expected outcomes* of the project. These goals help drive any decisions that may be needed during the implementation cycle, such as prioritizing certain features over others.

It's also important to map the default capabilities of Dynamics 365 to the business requirements to help minimize customizations and make future updates easier without much rework.

At this stage, it's also crucial that senior management make sure that both business and IT teams collaborate on the implementation from the start. The business teams own and design the process flows and can articulate their vision for the new solution. The IT team helps organize the technical teams, project coordination, and solution delivery. Without collaboration across these teams, there's a high chance of misalignment, wrong expectations, and a solution that doesn't deliver the full return on investment. Business requirements must be clear and agreed on by both teams.

Another example where collaboration is vital is planning for deployments. While the business team can define and prioritize the requirements in the Minimum Viable Product (MVP), the IT team can plan for the subsequent rollouts, including the features, timelines, and logistics.

This kind of collaboration helps deliver a solution that meets business needs and enables successful change management and user adoption.

### Agree on key success metrics

After establishing a common understanding of the business challenges and priorities, it's equally important to agree on the key performance indicators (KPIs) that measure success. The KPIs should be tangible metrics; for example, opportunity conversion rate or average call handling time.

Understanding and identifying the KPIs is critical to ensuring the scope you deliver is aligned with the expectations of the business stakeholders and generates a tangible return on your investment in Dynamics 365.

Here are some examples of success metrics or KPIs:

- Improve the opportunity conversion rate from X% to Y% over Z period.
- Reduce sales cycle from X days to Y days over Z period.
- Increase net new customer adds from X to Y over Z period.
- Reduce average call handling time from X minutes to Y minutes over Z period.
- Improve service request turnaround time from X days to Y days over Z period.

The KPIs mentioned above aren't exhaustive. Each organization has specific KPIs that cater to its business scenarios. Each KPI that you identify and prioritize has a direct impact on how you implement the final business solution. So, having a definitive list of metrics helps you prioritize the right use cases and allows stakeholders to gauge the project's success in a tangible way.

### Identify roles and responsibilities

The customer and partner/system integrator teams should have clear views on the exact roles and responsibilities shared between their teams. We often hear stories where the statement of work (SoW) or contract mentions high-level activities and doesn't go into enough details, resulting in confusion and finger-pointing during the project. Some activities might be overlooked or underestimated, and others might have unwritten assumptions. The customer might assume their implementation partner will handle an activity, while the partner assumes their customer will handle that activity. This misalignment can be a rude shock to the teams later on.

> [!IMPORTANT]
> Make sure the SoW or contract focuses on the detailed activities with clear definitions of assumptions, roles, and responsibilities. Also mention considerations that are out of scope. This upfront and timely effort will save expensive and time-consuming rework during the implementation stages.

The list of activities includes but isn't limited to:

- Business process modeling, documentation, and management
- User interface (UI) and user experience (UX)
- Data migration, including sourcing, cleansing, mapping, transforming, and importing
- Integration with other line of business applications and external systems
- Test strategy, planning, and execution
- Management and orchestration of user acceptance tests (UAT)
- Security design and role assignment
- Configuration management
- Analytics and business intelligence reporting strategy, tools, and design
- Cutover planning and execution
- Adoption and change management

### Identify and allocate the right resources

Setting up a productive team structure is critical for the success of the project. Identify the stakeholders, the owners of business processes, the team that delivers the projects, and the business users who can be engaged from the beginning of the project lifecycle.

The key roles required for all projects can often be grouped into two types of team structures.

- **Steering committee**: A group of senior stakeholders with the authority to ensure that the project team stays in alignment with KPIs. As they monitor progress, they can help make decisions that have an impact on the overall strategy, including budget, costs, and expected business functionality. Steering committees usually consist of members of senior management and leaders of business groups that are part of the identified rollouts.

- **Core implementation team**: Does the actual execution of the project. For any Dynamics 365 implementation project, core implementation teams should include the following roles:

  - Project managers
  - Business subject matter experts
  - Solution architects
  - Functional and technical consultants
  - Developers
  - Testers
  - Trainers
  - Adoption and change management advisors
  - User champions

The engagement of process owners is critical to ensure a complete understanding of business processes. Their input is required if any process changes result from alignment with built-in features. User representation should also be planned properly to adequately cover all the personas. Lack of availability of any of these roles may result in delays, incomplete understanding of processes, and poor user adoption. The involvement of process owners and users can be staggered depending on the implementation phase. Plan early on to allow business teams to make the required changes to their schedules and be able to contribute efficiently during the project lifecycle.

The project may require more roles depending on the scope and methodology. Some roles may need to join temporarily during the project lifecycle to meet specific needs for that period.

Learn more about team setup considerations at [Introduction to Success by Design](success-by-design.md) and [Project governance](project-governance.md).

### Allocate budget and funds

Planning a budget for Dynamics 365 cloud applications typically includes costs like these:

- Subscription
- Storage
- Implementation lifecycle activities, such as design, testing, deployment of the solution, migration from incumbent systems, training, change management, and continuous improvements.

Dynamics 365 follows a periodic release pattern with weekly fixes, monthly, and six-month release waves. We highly recommend allocating budget towards building strong DevOps, CI/CD (Continuous Integration/Continuous Delivery) pipelines with sufficient test automation of functional scenarios and business processes in place that help improve the test regressions.

Project lifecycles require constant assessments with careful considerations and actions for the variance between budgets and actual costs.

A common decision that most teams face is finding the right balance between delivering a high-value solution faster by using the built-in capabilities versus extending the product capabilities to implement the business requirements and needs. Extending the Dynamics 365 applications not only requires initial development costs but also maintenance and support costs. It's an area where implementation teams should carefully revisit the cost impact. In the cloud world with rapid availability of new features and capabilities, rethink the investments required for extending the application. Learn more about [assessing the impact of extending your solution](extend-your-solution.md).

Project management teams should give weight to areas that help them stay aligned with the overall project goals and objectives. As project scope and timelines change, activities that fall towards the end of the project lifecycle are often cut from scope to meet budget constraints. These activities can include performance testing, data validation testing, training, and change management, and can affect the quality and success of the implementation significantly. Revisit the project goals and success factors that you defined during the initial stages, and carefully revise the scope and timelines without compromising on overall quality and a user-centric approach.

We recommend an approach that helps you define the total impact by identifying the cost, benefit, flexibility, and risk factors that affect the investment decision. Such an approach can help you improve your overall business goals of winning, serving, and retaining customers.

Forrester's Total Economic Impact (TEI) of deploying various Dynamics 365 apps is a good way to assess the costs and benefits associated with Dynamics 365 implementation:

- [The Total Economic Impact of Microsoft Dynamics 365 Finance And Supply Chain Management](https://info.microsoft.com/ww-Landing-Forrester-Total-Economic-Report.html)
- [The Total Economic Impact of Microsoft Dynamics 365 Field Service](https://info.microsoft.com/ww-Landing-TEI-of-D365-for-Field-Service-eBook.html?Lcid=En-US)
- [The Total Economic Impact of Microsoft Dynamics 365 Customer Service](https://info.microsoft.com/ww-landing-TEI-of-D365-customer-service.html?lcid=en-us)

## Conclusion

When you define an implementation strategy, you set clear expectations and guidelines for the team and the wider business on how to achieve the project goals. It helps you translate your business goals into a structured implementation plan.

A well-rounded implementation strategy:

- Builds a common understanding of vision and success metrics.
- Includes both business and IT teams from the start of the project.
- Has a clear understanding of roles and responsibilities between customers and partners.
- Identifies the methodology based on the specific factors that drive the implementation.
- Follows the tried and tested approach that the methodology defines. Don't leave activities out just for convenience.
- Takes feedback early in the implementation journey by doing a "show and tell" after each sprint or phase, depending on the chosen methodology.
- Considers the organizational culture when choosing a methodology. Organizations that have followed a traditional approach such as Waterfall may need more change management planning to embark on a modern approach such as Agile or Hybrid.
- Considers the industry practices that may also have a bearing on the methodology. Some industries may have their own tailored approach and that needs to be taken into account.
- Formulates a focused approach towards user adoption by creating a change management plan.
- Plans an approach for communicating to various stakeholders, including leadership and users.
- Continues to improve throughout the process. Solicit user feedback and act!

## Next steps

- [Choose a methodology for the Dynamics 365 implementation project](implementation-strategy-choose-methodology.md)
- [Define a strategy for deployment and release](implementation-strategy-define-strategy-deployment-release.md)
- [Define a strategy for adoption and change management](implementation-strategy-define-strategy-adoption-change-management.md)
