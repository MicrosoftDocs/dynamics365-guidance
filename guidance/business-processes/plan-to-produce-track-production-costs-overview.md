---
title: Overview of the track production operations business process area
description: Get an overview of the business process area for tracking production cost in the plan to produce end-to-end business process in Dynamics 365 solutions.
ms.date: 11/24/2023
ms.topic: conceptual
author: edupont04
ms.author: annekrupke
---

# Overview of the track production operations business process area

***Applies to: Dynamics 365 Finance, Dynamics 365 Supply Chain Management***

This article describes the *track production costs* business process area. It describes the process flow of this area and explains the benefits of using Dynamics 365 to support this process area.

The *track production costs* business process area encompasses defining the costing strategy for produced items, estimating production costs, and recording the actual costs based on production activities. Tracking production costs requires coordination and communication among many departments, including Engineering, Operations, Quality, Sales, Planning, and Procurement.

The base components of production costs are typically categorized into the following four groups: direct material costs, resource or direct labor costs, subcontracting costs, and indirect or overhead production costs. Some organizations include all four groups of components in their Dynamics 365 Supply Chain Management implementation. Other organizations track only material costs, for example, especially when material costs represent most of the total cost.

Because the *track production costs* business process area is fundamental for any manufacturing company, you should define it when you first begin to implement Dynamics 365 Supply Chain Management. Production costing strategies can be updated as required as the business evolves. However, many decisions must be made up front because of their impact on the rest of the *plan to produce* process.

## Stakeholders

Many people in an organization should contribute to the decision-making process and design of the *track production costs* area. The list includes the following contributors:

- **Production stakeholders** – Examples: Production manager and Production scheduler
- **Engineering stakeholders** – Examples: Product owner and Engineering manager
- **Costing stakeholders** – Examples: Cost accountant and Controller
- **Quality stakeholders** – Examples: Quality manager and Quality technician
- **Finance stakeholders** – Examples: Inventory accounting and CFO

## Track production costs process flow

The following diagram shows the high-level flow of the *track production costs* business process area. [!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/plan-to-produce-track-production-cost-flow.svg" alt-text="Flow diagram for the track production costs business process area, which is explained in the next paragraphs." lightbox="media/plan-to-produce-track-production-cost-flow.svg":::

The following steps are illustrated in the *track production costs* business process flow diagram.

1. Start

    1. A parallel branch from 1. Start includes the *Plan to produce* end-to-end process.

        1. *Define production strategies* business process area

            1. *Define production costs* business process

        1. *Plan production operations* business process area

            1. *Estimate the cost of production* business process

        1. *Run production operations* business process area

            1. *Record costs in production* business process

        1. Record cost of quality business process

            1. *Record costs in production* business process

        1. Outsource production resources business process area

            1. *Record costs in production* business process

1. *Design to retire* end-to-end process

    Learn more at TODOADDLINK.

1. *Define product costing* business process area
1. *Track production costs* business process area (this article)
1. *Define production costs* business process
1. *Estimate the cost of production* business process
1. *Record costs in production* business process
1. *Finalize costs for production orders* business process

    1. *Manage inventory costs* business process, which is a child of the *Inventory to deliver* end-to-end process
    1. *Record and control costs* business process, which is a child of the *Inventory to deliver* end-to-end process
    1. *Record financial transactions* business process, which is a child of the *Record to report* end-to-end process

1. *Analyze production costs*

    1. *Report and analyze financials and cash flow* business process, which is a child of the *Record to report* end-to-end process

1. End

## Track production costs benefits

There are many key benefits to using Dynamics 365 to support the *track production costs* business process area. The following sections outline the key benefits that an organization might monitor and measure for *track production costs*.

### Improved production data quality

Tracking of actual costs can point to inaccurate data in bills of materials (BOMs) and routes. For example, consistent variance on a route step for a product might indicate that the route itself must be adjusted so that the length is correct. As a result, the process supports more accurate timing in the production schedule and leads to a better on time and in full (OTIF) percentage.

### Increased visibility into process improvement

When organizations use standard costing in Dynamics 365, they can more easily analyze variances, because they can track cost changes in the general ledger. Regardless of the costing methodology, analysis of variances can help organizations detect when there is a problem in the process, or a shift in the market or supply chain. Variance can be the result of equipment that doesn't operate efficiently, changes in workers and work behavior, changes in material costs, and many other factors. When businesses can analyze and react to variances, they can work to reduce production costs and variances. Therefore, they can improve their profit margins.

### Improved product margins

Without true production cost tracking, organizations must rely on assumptions or heuristics to understand the cost of their produced items. This situation can lead to incorrect decisions about which products to offer or promote. When organizations take steps to build more accurate BOMs and routes in Dynamics 365 Supply Chain Management, they can more accurately define the expected costs for a produced item and then monitor the variances. As a result, they can potentially reduce costs and increase margins.

## Next steps

If you want to implement Dynamics 365 solutions to help with your *track production costs* business processes, use the following resources and steps to learn more.

1. [Define product costing overview](design-to-retire-define-product-costing-overview.md)  

2. [Define production strategies](plan-to-produce-define-production-strategies.md)

3. [Plan production operations](plan-to-produce-plan-production-operations-overview.md)

4. [Run production operations overview](plan-to-produce-execute-production-operations-overview.md)

5. [Outsource production operations](plan-to-produce-track-production-costs-overview.md)

6. [Control production quality](plan-to-produce-control-production-quality-overview.md)

7. *Track production costs* (the article that you're currently reading)

Return to the overview of business process areas at [Plan to produce business process areas](plan-to-produce-areas.md).

## Related information

You can use the following resources to learn more about the *track production costs* process in Dynamics 365.

- [TechTalk – Manufacturing Accounting in Dynamics 365 Supply Chain Management](https://community.dynamics.com/blogs/post/?postid=3e44201b-72e9-4db2-99bb-13e03b3514ae)
- [TechTalk – Production Variance Analysis in Dynamics 365 Supply Chain Management](https://community.dynamics.com/blogs/post/?postid=2f04e0a8-4345-493c-96e6-29f8fb34e8c9)
- [Cost management home page - Supply Chain Management](/dynamics365/supply-chain/cost-management/cost-management-home-page)
- [Cost accounting home page - Finance](/dynamics365/finance/cost-accounting/cost-accounting-home-page?context=%2Fdynamics365%2Fcontext%2Fsupply-chain)
- [Work with the costing sheet in Dynamics 365 Supply Chain Management (training)](/training/modules/work-costing-sheet-dyn365-supply-chain-mgmt/)
- [Exam MB-335: Microsoft Dynamics 365 Supply Chain Management Functional Consultant Expert (beta)](/certifications/exams/mb-335)
- [Dynamics 365 Supply Chain Management Community Forum](https://community.dynamics.com/forums/thread/?discussionforumid=bd2c77d7-890b-4a36-87a4-8afbddbca6a6)

<!-- ## Tags

*Industries:* Mining, Construction, Manufacturing, Wholesale trade, Retail trade

*Stakeholders:* Functional consultant, Business analyst, Production lead, Supply chain lead, Inventory lead, Costing lead

*Products:* Dynamics 365 Supply Chain Management, Dynamics 365 Finance -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Anne Krupke](https://www.linkedin.com/in/annekrupke/) \| FastTrack Solution Architect

Other contributors:

- [Rachel Profitt](https://www.linkedin.com/in/rachelprofitt/) \| FastTrack Solution Architect
- [Alejandra Cabrales](https://www.linkedin.com/in/alejandra-cabrales/) \| FastTrack Solution Architect
