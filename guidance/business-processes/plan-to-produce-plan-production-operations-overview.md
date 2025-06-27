---
title: Overview of the Plan production operations business process area
description: Get an overview of the business process area for planning production in the plan to produce end-to-end business process in Dynamics 365 solutions.
ms.date: 12/06/2023
ms.topic: concept-article
author: edupont04
ms.author: annekrupke
---
# Overview of the Plan production operations business process area within the Plan to produce end-to-end scenario

***Applies to: Dynamics 365 Supply Chain Management***

This article describes the business process area *plan production operations*. It explains the context of the process area, provides a list of the benefits of using Dynamics 365 to support the process area, and lists the processes within the area.

Planning production operations picks up where the *plan supply and replenishment* process area finishes. Production orders are either firmed from the generated planned orders or they're manually created. Then, the orders are organized into a production schedule that often includes sequencing or otherwise organizing production based on efficiency, due dates, and material and machinery availability. Once the production schedule is complete for the next time period, the information is sent to the shop floor, and the *run production operations* process area can begin.

This business process area should be included as part of the initial implementation, unless the business is only implementing financial business processes in the first phase. Additionally, some organizations choose to continue with a manual production planning and scheduling process and implement the functionality in Dynamics 365 Supply Chain Management in a later phase. The production planning functionality is flexible and can be adapted as the business changes over time.

## Stakeholders 

Many people across the organization should contribute to the decision-making process and design of the *plan production operations* area. The list includes but isn't limited to the following roles:

- **Production stakeholders**, such as production schedulers and production supervisors, provide details on the business requirements in this process.  

- **Operations/Planning stakeholders**, such as master planners, provide information about the upstream processes to generate the production plan.  

- **IT stakeholders**, such as business analysts, communicate information about expected performance of production scheduling activities and similar tasks.  

- **Warehouse stakeholders**, such as warehouse managers, describe the relationship between the production schedule and related warehouse work, such as picking and put-away of finished goods.  

## Plan production operations process flow

The following diagram illustrates the plan production operations business process area. [!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/plan-to-produce-plan-production-flow.svg" alt-text="Flow diagram for the business process area that is explained in the paragraph after the image." lightbox="media/plan-to-produce-plan-production-flow.svg":::

[!INCLUDE [bus-proc-cat-pending](../includes/bus-proc-cat-pending.md)]

The flow diagram covers the following steps.

1. *Plan production operations* business process area
   1. *Modify production plan*
   2. *Create production plan*
   3. *Schedule production jobs*
   4. *Release production to the shop floor*
   5. *Estimate the cost of production*

> [!NOTE]
> The *Plan production operations* business process area flow diagram is described at a high level. There may be variations in the process flow depending on your operating model and business process requirements.

<!--
1. Start

    1. A parallel branch from 1. Start includes the *Plan to produce* end-to-end process.

        1. *Plan production operations* business process area

        2. *Define production strategies* business process area

            1. *Schedule production operations* business process

    2. A parallel branch from 1. Start includes the *Hire to retire* end-to-end process.

        1. *Plan and recruit your workforce* business process area

            1. *Schedule production operations* business process

2. *Forecast to plan* end-to-end process

3. *Plan supply and replenishment* business process area

4. *Plan production operations* business process area

5. *Modify production plan* business process

6. *Confirm production plan* business process
    
    1. A parallel branch from 6. *Confirm production plan* includes the *Outsource production operations* business process area.

7. *Schedule production operations* business process

8. *Release production to the shop floor* business process

    1. A parallel branch from 8. *Release production to the shop floor* includes the *Run production operations* business process area.

9. End
-->

## Plan production operations benefits

Many key benefits can be used to monitor and measure the success of implementing technology to support the *plan production operations* area. The following sections outline the key benefits that an organization might monitor and measure for *plan production operations*.  

### Reduce equipment changeovers 

By using Dynamics 365 Supply Chain Management features such as **sequencing rules** and **batch order consolidation**, organizations can increase efficiency in production by sequencing and grouping similar products in production. They can reduce the number of equipment changeovers or line cleaning activities, which allows for increased efficiency and throughput. Learn more about sequencing production in Dynamics 365 at [Sequence production jobs for process manufacturing](/dynamics365/supply-chain/production-control/tasks/sequence-production-jobs-process-manufacturing).

### Improve decision making with visual scheduling

Dynamics 365 Supply Chain Management provides visual scheduling tools for the various modes of production, allowing production schedulers to easily review and adjust the schedule. Decisions can be made while using visual indicators of material availability, resource capacity, and preceding or succeeding operations. Learn more about visual scheduling in Dynamics 365 in the following articles:  

- [Gantt chart for job scheduling](/dynamics365/supply-chain/production-control/visual-scheduling-production)  
- [Visual scheduling for lean manufacturing](/dynamics365/supply-chain/production-control/visual-scheduling-lean-manufacturing)  

### Increase on-time and in-full (OTIF) shipments

When organizations use the automated production planning and scheduling tools in Dynamics 365 Supply Chain Management, they can make sure that customer delivery dates are honored in the production plan. This way, they make sure that orders are prioritized appropriately in production to meet delivery dates.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your plan production operations business processes, use the following resources and steps to learn more:

1. [Define product costing overview](design-to-retire-define-product-costing-overview.md)  

2. [Define production strategies](plan-to-produce-define-production-strategies.md)

3. *Plan production operations* (the article that you're currently reading)
   1. *Modify production plan*
   2. *Create production plan*
   3. *Schedule production jobs*
   4. *Release production to the shop floor*
   5. *Estimate the cost of production*

4. [Run production operations](plan-to-produce-execute-production-operations-overview.md)  

5. [Outsource production operations](plan-to-produce-outsource-production-operations-overview.md)  

6. [Control production quality](plan-to-produce-control-production-quality-overview.md)  

7. [Track production costs](plan-to-produce-track-production-costs-overview.md)  

Return to the overview of business process areas at [Plan to produce business process areas](plan-to-produce-areas.md).  

## Related information

You can use the following resources to learn more about the *plan production operations* process in Dynamics 365:

- [Schedule a production order with operations and job scheduling](/dynamics365/supply-chain/production-control/tasks/schedule-production-order-operations-job-scheduling)  

- [Kanban job scheduling for lean manufacturing](/dynamics365/supply-chain/production-control/lean-manufacturing-kanban-job-scheduling)  

- [Mixed mode planning - Combine discrete, process, and lean sourcing](/dynamics365/supply-chain/production-control/mixed-mode-plan)  

- Find definitions of terminology used in content for planning production operations in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article, including the following terms:  

  - [Finished good](glossary.md#finished-good)  
  - [Modes of manufacturing](glossary.md#modes-of-manufacturing)  
  - [Production schedule](glossary.md#production-schedule)  
  - [Production strategies](glossary.md#production-strategies)  
  - [Raw material](glossary.md#raw-material)  
  - [Scrap](glossary.md#scrap)  
  - [Subassembly](glossary.md#subassembly)  
  - [Subcontracting](glossary.md#subcontracting)  
<!-- ## Tags

*Industries:* Manufacturing (20-39), Wholesale Trade (50-51), Retail Trade (52-59)

*Stakeholders:* IT, Operations, Production, Warehouse

*Products:* Dynamics 365 Supply Chain Management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Anne Krupke](https://www.linkedin.com/in/annekrupke/) | FastTrack Solution Architect  

Other contributors:

- [Phillip Seaton](https://www.linkedin.com/in/pbseaton/) | FastTrack Solution Architect  
