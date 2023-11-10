---
title:  Forecast to plan end-to-end overview
description:  Get an overview of the end-to-end flow and the relationship diagram for the forecast to plan business process in Dynamics 365 implementations.
ms.date: 07/28/2023
ms.topic: conceptual
author: edupont04
ms.author: annekrupke
ms.reviewer: edupont
---

# Forecast to plan end-to-end overview

***Applies to: Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Human Resources, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center***

This article describes the *forecast to plan* end-to-end business process flow and its relationship to other business processes that can be used within Dynamics 365.

## Forecast to plan process relationship

The following diagram shows the relationship of other processes and products/features for the *forecast to plan* process.  

:::image type="content" source="media/forecast-to-plan-process-relationship.svg" alt-text="forecast to plan process relationship diagram." lightbox="media/forecast-to-plan-process-relationship.svg":::

There are several processes that often are prerequisite to the *forecast to plan* process. In most companies, the *hire to retire* process is upstream of *forecast to plan* since it will be used to define the workforce capacity that will constrain the plan. Often, organizations will complete the product and services definition in the *product and service lifecycle management* process prior to beginning the forecasting process. In some operational strategies such as *make to order* or *engineer to order*, the *prospect to quote* and *order to cash* processes occur before *forecast to plan*, since they're the trigger to initiate the process.

The second column in the diagram displays the business process areas of the *forecast to plan* process. These business process areas are:

- Establish stocking and replenishment policies

- Forecast supply and demand

- Plan supply and replenishment

- Forecast and plan for intercompany trade

- Define strategic and operational plans

The third column in the diagram displays the downstream business processes. In operational strategies such as make to stock, *order to cash* would be a downstream process from *forecast to plan*, since in this case a forecast would be used to drive inventory replenishment prior to an order being placed. Other processes that are more typically downstream processes of *forecast to plan* are *plan to produce*, *procure to pay*, *inventory to deliver*, *record to report*, and *case to resolution*.  

> [!IMPORTANT]
> These downstream processes may have some prerequisites that are required before you can run a forecast or master plan in the system; however, the outputs of planning are generally considered to be purchases, production, and transfer orders.

Optionally, integrate the *case to resolution* process into the business process when there are complex review, approval, adjustment, or request processes between the planning team in your organization and other departments. The *record to report* process is considered downstream, because there isn't any financial impact to the general ledger from generating a plan. However, once orders are confirmed and processed, there's typically a financial impact to the inventory, customer and vendor balances, for example.

## Featured capabilities

There are several product capabilities in the Dynamics 365 ecosystem that support the *forecast to plan* process, including but not limited to:

- **Planning Optimization**  

  The *Plan supply and replenishment* business area often uses the Planning Optimization service to create the master plan that will be used to drive the execution of procurement and production activities. Planning Optimization allows companies to react to demand in near-real-time instead of having to wait for a nightly planning run. Learn more at [Get started with master planning](/dynamics365/supply-chain/master-planning/planning-optimization/get-started).  

- **Demand forecasting**  

  Dynamics 365 Supply Chain Management supports the *forecast supply and demand* business process area with the [demand forecast](/dynamics365/supply-chain/master-planning/introduction-demand-forecasting) capability. The demand forecasting feature uses historical demand data and Azure Machine Learning to generate a statistical demand forecast, which can then be collaboratively reviewed and published for use in planning activities.

- **Demand Driven Material Requirements Planning (DDMRP)**  

  Demand Driven Material Requirements Planning is an industry-standard replenishment methodology that uses demand data and other factors to determine the appropriate inventory levels at each location. This methodology is one of the options for how to establish stocking policies in [Dynamics 365 Supply Chain Management](/dynamics365/supply-chain/master-planning/planning-optimization/ddmrp-overview).

- **Supply and demand insights**  

  [Supply and demand insights](/supply-chain-platform/supply-chain-center/use/supply-and-demand) is one of the modules in Microsoft Supply Chain Center, which provides visibility into key performance indicators (KPIs) that allow organizations to monitor the health of their supply chain.

- **Restock recommendations**  

  [Restock recommendations](/supply-chain-platform/supply-chain-center/use/restock-recommendations) is another module in Microsoft Supply Chain Center that takes demand and inventory data and proposes recommendations to help organization meet their target service levels.

## Forecast to plan business process flow

The following diagram shows an example of the high-level flow of the *forecast to plan* business process. Each solid rectangle on the diagram represents an end-to-end business process area. The sub-processes shown in the diagram are shown for the *forecast to plan* business process. The arrows on the diagram show the flow of the business process in an organization. If a sub-process can lead to more than one other sub-process, the parallel sub-processes are shown as branches.

:::image type="content" source="media/forecast-to-plan-process-flow.png" alt-text="Flow diagram for the end-to-end business process, forecast to plan, which is explained in the paragraph after the image." lightbox="media/forecast-to-plan-process-flow.png":::

The example diagram above is a sample flow that is common in either make to order scenario. The following steps are illustrated in the *forecast to plan* end-to-end business process flow diagram.

1. Start

2. *Product and service lifecycle management*

3. *Prospect to quote* end-to-end process

4. *Order to cash* end-to-end process.

5. *Forecast to plan*

    1. A parallel branch links to *Define strategic and operational plans* and *Establish stocking policies*

    2. *Forecast supply and demand*

    3. *Forecast and plan for intercompany trade*

    4. *Plan supply and replenishment*

6. *Procure to pay*

    Parallel branches from this subprocess are 9. *Case to resolution* and 10. *Record to report*

7. *Plan to produce*

    Parallel branches from this subprocess are 9. *Case to resolution* and 10. *Record to report*

8. *Inventory to deliver*

    Parallel branches from this subprocess are 9. *Case to resolution* and 10. *Record to report*

9. *Case to resolution*

10. *Record to report*

11. End

The following steps are illustrated in the *forecast to plan* end-to-end process with a parallel branch from the start box.

1. Start

2. *Hire to retire*

    1. *Forecast to plan*

    2. *Define strategic and operational plans*

    3. End

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *forecast to plan* business processes, use the following resources and steps to learn more.

- Define the goals and objectives of implementing an order to cash technology solution. Learn more at [Implementation strategy](../implementation-guide/implementation-strategy.md).

- Define the business process scope of your project. Learn more at [Process-focused solution](../implementation-guide/process-focused-solution.md).

- Request a demo or get a free trial of Dynamics 365 solutions for the order to cash process. Learn more at [Request a demo](https://dynamics.microsoft.com/dynamics-365-free-trial/).

- Get an overview of the *forecast to plan* business process areas. Learn more at [Forecast to plan business process areas](forecast-to-plan-areas.md).

## Related resources

Use the following resources to learn more about the *forecast to plan* process in Dynamics 365.

- [Master planning in Dynamics 365 Supply Chain Management](/training/paths/master-planning-supply-chain-management/)

- [TechTalk  Demand Driven Material Requirements Planning in Dynamics 365 Supply Chain Management](https://community.dynamics.com/blogs/post/?postid=72ceafd4-72c4-4921-81f1-8535076d7be6)

- [TechTalk  Priority based planning in Dynamics 365 Supply Chain Management](https://community.dynamics.com/blogs/post/?postid=dcde88fa-9009-4adc-a2a6-514dd6a43bc9)

- [TechTalk Series  Planning Optimization](https://community.dynamics.com/blogs/post/?postid=c5f1bffe-a521-4904-aa69-4e40f7336fd7)

- [TechTalk Series  Demand Forecasting with Azure Machine](https://community.dynamics.com/blogs/post/?postid=be5e2cbb-373f-4167-9e57-8ccb97f97b84)

- Find definitions of terminology used in content for *forecast to plan* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article, including the following terms:

  - [Forecast](glossary.md#forecast)  
  - [Planning](glossary.md#planning)  
  - [Replenishment](glossary.md#replenishment)  

<!--## Tags
*Stakeholders:* Functional consultant, Business analyst, Planning stakeholders, Procurement stakeholders, Sales stakeholders, Production stakeholders

*Products:* Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Human Resources, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center  
