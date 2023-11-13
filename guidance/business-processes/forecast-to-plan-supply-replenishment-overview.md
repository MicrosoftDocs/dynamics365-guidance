---
title: Plan supply and replenishment overview
description: Read about the business process area for planning supply and replenishment in Dynamics 365.
ms.date: 07/19/2023
ms.topic: conceptual
author: edupont04
ms.author: annekrupke
---

# Plan supply and replenishment overview

***Applies to: Dynamics 365 Commerce, Dynamics 365 Supply Chain Management***

This article describes the *Plan supply and replenishment* business process area that is part of the *Forecast to plan* end to end process. This process area encompasses the activities of responding to demand and generating proposed inventory supply, based on the policies set in the *Establish stocking and replenishment policies* business process area. In this article, we discuss the stakeholders, benefits, process flow, and next steps for organizations implementing this process area.

Planning supply and replenishment includes activities for planning inventory transfers, production, and purchasing. Most organizations have several planners who are responsible for the process of supplying products. The planners often split ownership by product category or vendor for purchasing or manufacturing line for produced goods. Coordination, communication, and a clear split of ownership is key to the success of the product supply.

You can run master planning on an ad-hoc basis. You can also run master planning for a single item, a group of items, or all items in a legal entity or in several legal entities.

*Plan supply and replenishment* should be defined whenever you implement the *Forecast to plan* process. Often in larger Dynamics 365 implementation projects, *Forecast to plan* is implemented as a secondary phase after the initial go-live. But it can also be part of the initial process. *Plan supply and replenishment* is a flexible process that can be changed or updated as the business and its processes grow.

## Stakeholders 

Many people across the organization should contribute to the decision-making process and design of the *plan supply and replenishment* area. The list includes but isn't limited to the following roles:

- **Manufacturing and supply chain teams** are responsible for managing the production and delivery of products. They must make sure that the system is properly integrated with manufacturing and supply chain systems and that data is properly managed.

  - **Planning stakeholders** – responsible for ordering the forecasting of materials, the plan for purchasing and the ordering itself. Examples: COO, VP of Operations, supply chain manager, operations manager, planning manager, planner

  - **Procurement stakeholders** - responsible for working with suppliers to acquire raw materials. Examples: director of procurement, buyer, purchasing agent, purchasing manager, managers

  - **Production stakeholders** - responsible for maintaining and working with resources and schedules to manufacture goods, calculating production lead time and capacity planning examples: production scheduler, production planner, production manager

  - **Inventory and transportation stakeholders** - responsible for managing and allocating warehouse capacity and resources for inventory operations and transportation management. Examples: Warehouse manager, Transportation planner

-  **IT department, business analysts, developers** - responsible for implementing technology solutions to support the *plan supply and replenishment* business processes

- **Executive leadership** - responsible for overseeing supply chain efficiency and resiliency and alignment with strategic goals

## Plan supply and replenishment process flow 

The following diagram illustrates the plan supply and replenishment business process area.

:::image type="content" source="media/forecast-to-plan-plan-supply-replenishment.SVG" alt-text="Flow diagram with steps for the process of maintaining assets that is further explained in the next paragraphs." lightbox="media/forecast-to-plan-plan-supply-replenishment.SVG":::

1. Start

    Parallel branches connect to the following processes:

    - *Inventory to deliver* that connects to *Maintain inventory levels*, which connects to 4. *Plan supply and replenishment*.

    - *Plan to produce* that connects to *Run production operations*, which connects to ii. *Plan production*.

    - *Procure to pay* that connects to *Procure materials and services*, which connects to iii. *Plan purchases*.

2. *Forecast to plan*

3. *Establish stocking and replenishment policies*

4. *Plan supply and replenishment*

    1. Generate a coordinated plan

        1. Plan inventory transfers and replenishments

        2. Plan production

        3. Plan purchases

    2. Plan for a single item or group of items

    3. React to supply chain signals

5. End

There are connections that the flow diagram doesn't show for the downstream processes:

- *Plan production* connects to *Plan to produce* that connects to *Schedule production operations*, which connects to End.

- *Plan inventory transfers and replenishments* connects to *Plan transportation loads*

- *Process inventory movements* connects to End

- *Procure materials and services* connects to End

## Plan supply and replenishment benefits 

There are many key benefits that can be used to monitor and measure the success of implementing Dynamics 365 Supply Chain Management to support the *plan supply and replenishment* area. The following sections outline the key benefits that an organization might monitor and measure for *plan supply and replenishment*. 


### Increase planning efficiency

Dynamics 365 Supply Chain Management includes a many capabilities that help organizations streamline and optimize the supply chain operations. With planning optimization, planners can quickly see suggestions based on the business-defined replenishment policies to help organizations quickly respond to changes in customer demand and reduce the risk of stockouts. The area covers production, purchasing, and transfers between warehouses.

### Improve plan accuracy

Constantly monitoring and adjusting the baseline plan helps ensure optimal levels of inventory in the system and minimize lead times. Based on real-time data, Dynamics 365 Supply Chain Management ensures that planning is based on the most up-to-date information. This way, you get better accuracy by eliminating manual data entry errors, reducing data latency, and providing a holistic view of the supply chain. Additionally, the solution allows organizations to make real-time adjustments to plans based on changing conditions and events. For example, if there's a sudden increase in demand or a supply disruption, Dynamics 365 Supply Chain Management can quickly assess the impact and suggest plan adjustments.

### Maximize resources and capacity

With shifting workloads and task timeframes in manufacturing environments, Dynamics 365 Supply Chain Management enables organizations to plan and optimize the use of their resources effectively. The plans include equipment, machinery, labor, and other production assets. By analyzing production schedules, demand forecasts, and resource availability, Dynamics 365 Supply Chain Management helps organizations allocate resources efficiently, ensuring optimal utilization and reducing idle time.

### Optimize inventory spend

In Dynamics 365 Supply Chain Management, organizations can define reorder points and safety stock levels based on demand variability, lead times, and service level targets. By setting optimal reorder points and safety stock levels, organizations can reduce the risk of stockouts while avoiding excessive safety stock that ties up working capital. This optimization helps strike the right balance between inventory availability and inventory carrying costs. Too much inventory ties up cash flow, not enough inventory means penalties and lost revenue.

### Improved service levels and reduced inventory levels

Dynamics 365 Supply Chain Management includes demand driven material requirements planning (DDMRP) functionality, that typically achieves inventory reductions of 30-45% keeping high service levels. Learn more about how Dynamics 365 supports the DDMRP methodology at [Demand Driven Material Requirements Planning (DDMRP) overview](/dynamics365/supply-chain/master-planning/planning-optimization/ddmrp-overview).

### Plan as often as needed

As planning in Dynamics is fast, you can plan as often as needed during the workday, which reduces lead times by up to one day. This way, you can run multiple plans in quick succession, allowing organizations to react to disruptions in minutes by finding the best possible solution in multiple simulations. Learn more about the fast planning supported by Planning Optimization in Dynamics 365 at [Master planning system architecture](/dynamics365/supply-chain/master-planning/master-planning-architecture).

## Next steps

If you want to implement Dynamics 365 solutions to assist with your plan supply and replenishment business processes, use the following resources and steps to learn more.

1. [Define strategic and operational plans](forecast-to-plan-areas.md#define-strategic-and-operational-plans)  

2. [Establish stocking and replenishment policies overview](forecast-to-plan-establish-stocking-replenishment-policies-overview.md)  

3. [Forecast supply and demand](forecast-to-plan-demand-forecasting-overview.md)  

4. [Forecast and plan for intercompany trade](forecast-to-plan-areas.md#forecast-and-plan-for-intercompany-trade)  

5. Plan supply and replenishment  (the article you're currently reading)      

## Related resources

You can use the following resources to learn more about the *plan supply and* *replenishment* process area in Dynamics 365.

- [Planning Optimization TechTalk](https://community.dynamics.com/videos/post/?postid=d20e04af-69fb-4eea-aa03-d0b17c458889)

- [Replenishment overview](/dynamics365/supply-chain/warehousing/replenishment)  

- [Use Planning Optimization in Dynamics 365 Supply Chain Management (training)](/training/modules/planning-optimization/)  

<!--## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Services (70-89)

*Stakeholders:* IT, Operations, Production, Purchasing, Transportation, Warehouse

*Products:* Dynamics 365 Commerce, Dynamics 365 Supply Chain Management-->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Anne Krupke](https://www.linkedin.com/in/annekrupke/) | FastTrack Solution Architect

Other contributors:

- [Beatriz Nebot Gracia](https://www.linkedin.com/in/beaneb/) | Product Manager

- [Rachel Profitt](https://www.linkedin.com/in/rachelprofitt/) | FastTrack Solution Architect

- [Rich Black](https://www.linkedin.com/in/blackrich) | FastTrack Solution Architect

- Lalitha Chintamaneni | FastTrack Solution Architect

- [Harshad Puthran](https://www.linkedin.com/in/harshman777) | FastTrack Solution Architect
