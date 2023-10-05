---
title: Establish stocking and replenishment policies overview
description: Read about the business process area for stocking and replenishment policies in Dynamics 365.
ms.date: 08/23/2023
ms.topic: conceptual
author: edupont04
ms.author: annekrupke
---

# Establish stocking and replenishment policies overview

***Applies to: Dynamics 365 Finance, Dynamics 365 Supply Chain Management***

This article describes the benefits and process flow of the *establish stocking and replenishment policies* business process area. This area encompasses the business processes to set the rules that ultimately drive the execution of supply planning on the different items that an organization stocks. Planners decide which operational strategies they'll use for different items, including which items to make or purchase to stock, and which items to make or purchase to order. For items that they'll generally keep in stock, they must establish the target inventory levels for each location based on demand history, forecasts, and space and capacity constraints. Organizations also establish the patterns for the planning process, such as the following examples:

- How frequently they'll run planning  
- How far into the future they create plans for  
- How they'll coordinate the planning efforts for procurement, production, and inventory movements  

> [!NOTE]
> The stocking and replenishment policies described here refer to the policies that determine how inventory will be supplied to a particular business location. Learn more about the policies that apply to how inventory will be positioned within a specific warehouse and movements within that warehouse in the content for the [*inventory to deliver*](inventory-to-deliver-overview.md) business process.

Sometimes planning policies are included in the initial rollout of Dynamics 365 Supply Chain Management, but they're often implemented at a later phase. Many organizations establish stocking policies and execute supply planning manually, using tools like Excel, or may even have a separate planning software and therefore it may not be included in the scope of a minimum-viable-product (MVP) implementation. The planning functionality inside Dynamics 365 Supply Chain Management is flexible and can be configured after the initial go live. It can also be updated as often as needed to reflect changes in the company's stocking and replenishment policies.

## Stakeholders

Many people in an organization must contribute to the decision-making process and design of the execute production operations area. The list includes but isn't limited to the following roles:

- **Inventory stakeholders** – examples: Warehouse manager, Transportation planner

- **Planning stakeholders** – examples: COO, VP of Operations, Operations manager, Planning manager

- **Production stakeholders** – examples: Production manager, Production scheduler

- **Procurement stakeholders** – examples: Buyer, Procurement planner

- **Finance stakeholders** – examples: Controller, Inventory accountant

## Establish stocking and replenishment policies process flow 

The following diagram shows the business processes within the establish *stocking and replenishment policies* area. The flow of the diagram represents the approach taken by most organization to periodically review and refresh their stocking and replenishment policies on their entire catalog of products. However, organizations must also establish stocking and replenishment policies for new items; alternatively  update their policies ad-hoc for specific items. This alternate scenario isn't shown in the process diagram, but generally the business processes listed are the same in both scenarios.

:::image type="content" source="media/forecast-to-plan-establish-stock-policies-flow.SVG" alt-text="Business process relationships with upstream and downstream processes that are explained in the next paragraphs.":::

The following steps are illustrated in the *establish stocking and replenishment policies* business process flow diagram.

1. Start

    Parallel branches from 1. Start include

    1. *Inventory to deliver*

        1. Define and manage warehouse operations

        2. Define inventory planning policies

    2. *Plan to produce*

        1. Define production strategies

        2. Define production planning policies

    3. *Procure to pay*

        1. Develop sourcing strategies

        2. Define procurement planning policies

2. *Forecast to plan* end-to-end process

3. *Define strategic and operation plans* process area

4. *Establish stocking and replenishment policies*

5. *Define planning policies*

6. *Define inventory planning policies*

    A parallel branch from 6. *Define inventory planning policies* is *Define procurement planning policies*

7. *Define production planning policies*

8. End

## Establish stocking and replenishment policies benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the establish stocking and replenishment policies area. The following sections outline the key benefits that an organization might monitor and measure for establish stocking and replenishment policies. 

### Reduce inventory stock outs

Stocking items as inventory buffers allows companies to ensure that items are on hand when they're needed. There are multiple options in Dynamics 365 Supply Chain Management which guide companies to determine the appropriate target inventory levels based on demand, capacity, and other key factors. Preventing stock outs helps achieve the On Time and In Full targets, increase customer satisfaction, and reduce delays in the production process.

### Reduce cost of order fulfillment

Building a coordinated set of stocking and replenishment policies across the entire production and distribution network in a company allows organizations to reduce unnecessary transfers of inventory, expedited freight costs for rush shipping, or customer penalties for service agreement violations. Dynamics 365 Supply Chain Management supports this by providing flexible replenishment rules, logic for setting target inventory levels, and a planning service that incorporates real time feedback throughout the day to adjust to changes in the supply chain.

### Reduce sales lead time

Having the right amount of inventory on hand for key items allows customer orders to be fulfilled faster, since the business doesn't have to wait for a purchase order or production work to be completed. Companies gain an advantage by building customer loyalty and increasing customer satisfaction.

## Next steps

If you want to implement solutions with Dynamics 365 to assist with your *forecast to plan* business processes, use the following resources and steps to learn more.

1. [Define strategic and operational plans](forecast-to-plan-areas.md#define-strategic-and-operational-plans)    
2. Establish stocking and replenishment policies  (the article you're currently reading)      
3. [Forecast supply and demand](forecast-to-plan-demand-forecasting-overview.md)  
4. [Forecast and plan for intercompany trade](forecast-to-plan-areas.md#forecast-and-plan-for-intercompany-trade)  
5. [Plan supply and replenishment](forecast-to-plan-areas.md#plan-supply-and-replenishment)  

## Related resources

The following resources can help you learn more about the establish stocking and replenishment policies process area in Dynamics 365.

- [Master planning in Dynamics 365 Supply Chain Management (training)](/training/paths/master-planning-supply-chain-management/)

- [TechTalk: Demand Driven Material Requirements Planning in Dynamics 365 Supply Chain Management](https://community.dynamics.com/blogs/post/?postid=72ceafd4-72c4-4921-81f1-8535076d7be6)

- [TechTalk: Priority based planning in Dynamics 365 Supply Chain Management](https://community.dynamics.com/blogs/post/?postid=dcde88fa-9009-4adc-a2a6-514dd6a43bc9)

- [Forecast to plan end-to-end overview](forecast-to-plan-overview.md)  

- [Implementation strategy](../implementation-guide/implementation-strategy.md)  

- [Process-focused solution](../implementation-guide/process-focused-solution.md)  

- Find definitions of terminology used in content for establishing stocking and replenishment policies in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article, including the following terms:  

  - [Forecast](glossary.md#forecast)  
  - [Planning](glossary.md#planning)  
  - [Replenishment](glossary.md#replenishment)  

<!--## Tags

*Industries:* Mining, Construction, Manufacturing, Wholesale Trade, Retail Trade

*Stakeholders:* Functional consultant, Business analyst, Planning stakeholders, Procurement stakeholders, Sales stakeholders, Production stakeholders, Inventory stakeholders

*Products:* Dynamics 365 Finance, Dynamics 365 Supply Chain Management-->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Anne Krupke](https://www.linkedin.com/in/annekrupke/) | FastTrack Solution Architect  

Other contributors:

- [Rachel Profitt](https://www.linkedin.com/in/rachelprofitt/)| FastTrack Solution Architect  

- [Beatriz Nebot Gracia](https://www.linkedin.com/in/beaneb/)| Product Manager, Dynamics 365 Supply Chain Management  
