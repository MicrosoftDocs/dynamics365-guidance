---
title: Track production costs overview
description: Get an overview of the business process area for tracking production cost in the plan to produce end-to-end business process in Dynamics 365 solutions.
ms.date: 07/25/2023
ms.topic: conceptual
author: edupont04
ms.author: annekrupke
---

# Track production costs overview

***Applies to: Dynamics 365 Finance, Dynamics 365 Supply Chain Management***

This article describes the business process area *track production costs*. It describes the process flow of this area and explains the benefits of using Dynamics 365 to support this process area.

The track production costs business process area encompasses defining the costing strategy for produced items, estimating production costs, and recording the actual costs based on production activities. Tracking production costs also requires coordination and communication between many departments, including engineering, operations, quality, sales, planning, and procurement.

The base components of production costs are typically categorized in the four following groups: direct material costs, resource or direct labor costs, subcontracting costs, and indirect or overhead production costs. Some organizations choose to include all four components in their Dynamics 365 Supply Chain Management implementation. Other organizations choose to only track material costs, for example, especially when material costs represent most of the total cost.  

This business process area should be defined at the beginning of implementing Dynamics 365 Supply Chain Management, as it's a foundational process for any manufacturing company. Production costing strategies can be updated as needed as the business evolves. However, many decisions must be made up-front due to the impact on how the rest of the *plan to produce* process works.

## Stakeholders

Many people in an organization should contribute to the decision-making process and design of the *track production costs* area. Contributors include the following list:

- **Production stakeholders** – examples: Production manager, Production scheduler

- **Engineering stakeholders** - examples: Product owner, Engineering manager

- **Costing stakeholders** - examples: Cost accountant, Controller

- **Quality stakeholders** – examples: Quality manager, Quality technician

- **Finance stakeholders** – examples: Inventory accounting, CFO

## Track production costs process flow

The following diagram shows the high-level flow of the *track production costs* business process area.  

[!INCLUDE [daf-business-process-flow-def](../includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/plan-to-produce-track-production-cost-flow.svg" alt-text="Flow diagram for the business process are, track production costs, which is explained in the paragraph after the image." lightbox="media/plan-to-produce-track-production-cost-flow.svg":::

The following steps are illustrated in the *track production costs* business process flow diagram.

1. Start

    1. A parallel branch from 1. Start includes the *Plan to produce* end to end process

        1. *Define production strategies* business process area

            1. *Define production costs* business process

        2. *Plan production operations* business process area

            1. *Estimate the cost of production* business process

        3. *Run production operations* business process area

            1. *Record costs in production* business process

        4. Record cost of quality business process

            1. *Record costs in production* business process

        5. Outsource production resources business process area

            1. *Record costs in production* business process

2. *Product and service lifecycle management* end-to-end process

    Learn more at [Product and service lifecycle management end-to-end overview](product-service-lifecycle-management-overview.md)  

3. *Define product and service* costing business process area

4. *Track production costs* business process area (this article)

5. *Define production costs* business process

6. *Estimate the cost of production* business process

7. *Record costs in production* business process

8. *Finalize costs for production orders* business process

    1. *Manage inventory costs* business process, which is a child of the *Inventory to deliver* end to end process

    2. *Record and control costs* business process, which is a child of the *Inventory to deliver* end to end process

    3. *Record financial transactions* business process, which is a child of the *Record to report* end to end process

9. *Analyze production costs*

    1. *Report and analyze financials and cash flow* business process, which is a child of the *Record to report* end to end process

10. End

## Track production costs benefits

There are many key benefits to using Dynamics 365 to support the *track production costs* business process area. The following sections outline the key benefits that an organization might monitor and measure for *track production costs*.

### Improve production data quality

Tracking actual costs can point to inaccurate data in bills of materials and routes. For example, if there's a consistent variance on a route step for a product, it might indicate that the route itself needs to be adjusted to be the correct length. As a result, the process supports a more accurate timing in the production schedule, leading to a better on time and in full (OTIF) percentage.

### Increased visibility into process improvement

When organizations use standard costing in Dynamics 365, analyzing variances is even easier because they can track cost changes in the general ledger. With any costing methodology, analyzing variances can help organizations spot when there's a problem in the process or a shift in the market or supply chain. Variance can come from equipment that isn't operating efficiently, a change in workers and work behavior, changes in material costs, and much more. When businesses can analyze and react to variances they can work to reduce production costs and variances, therefore improving their profit margins.

### Improved product margins

Without true production cost tracking, organizations have to rely on assumptions or heuristics to understand the cost of their produced items. This can lead to incorrect decision making in terms of which products to offer or promote. When organizations take steps to build more accurate bills of materials (BOMs) and routes in Dynamics 365 Supply Chain Management, they can define the expected costs for a produced item more accurately, and then monitor the variances. This gives them the power to potentially reduce costs and increase margins.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *track production costs* business processes, use the following resources and steps to learn more.

1. *Product and service lifecycle management*: [Define product and service costing overview](product-service-define-cost-overview.md)

2. Define production strategies

3. [Plan production operations](plan-to-produce-plan-production-operations-overview.md)  

4. [Run production operations overview](plan-to-produce-execute-production-operations-overview.md)

5. [Outsource production operations](plan-to-produce-track-production-costs-overview.md)  

6. [Control production quality](plan-to-produce-control-production-quality-overview.md)  

7. Track production costs  (the article you're currently reading)    

8. Return to the overview of business process areas at [Plan to produce business process areas](plan-to-produce-areas.md)

## Related resources

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
