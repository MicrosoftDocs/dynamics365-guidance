---
title: Order to cash end-to-end overview
description: Learn about the end-to-end business process, from order to cash. View a high-level flow diagram and see how it fits into Dynamics 365 solutions.
ms.date: 07/11/2023
ms.topic: overview
author: rachel-profitt
ms.author: raprofit
ms.reviewer: edupont
ms.custom: bap-template
---

# Order to cash end-to-end overview

***Applies to: Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce, Dynamics 365 Finance***

This article describes the order to cash end-to-end business process flow and its relationship to other business processes in Dynamics 365.

## Order to cash process relationships

The following diagram shows the relationship of the end-to-end order to cash process with other upstream and downstream processes.

:::image type="content" source="media/order-to-cash-process-relationship.svg" alt-text="List of upstream and downstream processes in relation to the order to cash process." lightbox="media/order-to-cash-process-relationship.svg":::

The order to cash process has the following potential upstream processes:

- **Case to resolution**: When you use Dynamics 365 Customer Service to handle customer inquiries, the case may lead to a sale.

- **Forecast to plan**: In some operational strategies, such as make to stock or buy to stock, the forecast to plan processes occur before order to cash.

- **Plan to produce**: In some operational strategies, such as make to stock, the production order is completed before orders take place.

- **Product and service lifecycle management**: In some operational strategies, such as make to stock or purchase to stock, the products and services to be sold are defined before orders are placed. This is especially true for retail organizations with a brick-and-mortar presence.

- **Prospect to quote**: In some operational strategies, such as make to order and engineer to order, the prospect to quote processes occur before order to cash, since they trigger the process.

The order to cash end-to-end process comprises the following [business process areas](order-to-cash-areas-overview.md):

- Manage pricing and contracts
- Create and manage sales orders
- Trade across companies
- Issue customer invoices
- Record customer payments
- Monitor customer credit and collections
- Process customer rebates

The order to cash process has the following downstream processes:

- **Case to resolution**: The case to resolution process is often used to handle inquiries and issues with sales orders, including the returns and exchange process. In some industries, the case to resolution process is used to handle product recalls.

- **Forecast to plan**: In some operational strategies, such as make to order and engineer to order, the forecasting processes typically occur after orders are placed, since they trigger planning purchases and production.

- **Inventory to deliver**: After orders are placed, they must be fulfilled. The inventory to deliver process includes all the steps for picking and packing, including shipment and transportation planning and scheduling steps for delivering orders. It also includes inventory movements and transfers to meet supply chain requirements for orders to retail stores.

- **Plan to produce**: In some operational strategies, such as make to order and engineer to order, the forecasting processes typically occur after orders are placed, since they trigger planning production.

- **Procure to pay**: In some operational strategies, such as make to order and engineer to order, the forecasting processes typically occur after orders are placed, since they trigger planning purchases. When you use a direct delivery sales model, the sales order is also the trigger to initiate the purchase order with the supplier.

- **Product and service lifecycle management**: In engineer to order operational strategies, products and services are typically defined after an order is placed.

- **Record to report**: Processing sales orders has a financial impact on inventory, revenue, and cost of goods sold. These effects are recorded in the general ledger and reported as part of the record to report process.

## Featured capabilities

The order to cash process interacts with the following product-specific capabilities, among others:

- **Point of sale**: Dynamics 365 Commerce includes a cloud-based point of sale with a modern interface, which supports all brick-and-mortar operations.

- **E-commerce**: Dynamics 365 Commerce includes online channel capabilities, including solutions for business-to-consumer and business-to-business sales models.

- **Call center**: Dynamics 365 Commerce includes a call center channel with capabilities to support your call center staff in taking orders, answering questions, and related tasks.

- **Sales accelerator**: The sales accelerator in Dynamics 365 provides a tailored experience for sellers, which minimizes the time spent searching for the best next customer to reach out to. It's a workspace optimized with AI, which suggests activities to guide sellers through customer interactions.

- **Demand forecasting**: Dynamics 365 Supply Chain Management supports the forecast supply and demand business process area with built-in demand forecast functionality. The demand forecasting capability uses historical demand data and Azure Machine Learning to generate a statistical forecast, which can be collaboratively reviewed and published for use in planning activities.

- **Dynamics 365 Customer Insights**: Customer Insights is a customer data platform, which helps deliver personalized customer experiences. It unifies customer data with operational and sensor data in real-time, enriched with first- and third-party sources.

- **Dynamics 365 Finance Insights**: Finance insights provides configurable and extensible solutions to help you intelligently predict your company's cash flow, predict when you may receive payment for outstanding receivables, and generate a budget proposal, which can help speed up your budgeting process.

- **Dynamics 365 Fraud Protection**: Fraud Protection is a cloud-based anti-fraud solution for medium- to large-sized organizations worldwide, designed to help lower fraud-related costs, increase profits, and improve customer experience.

- **Intelligent Order Management**: With Supply Chain Center and intelligent order management, organizations can manage the orchestration of orders through to fulfillment across different platforms and apps.

## Order to cash business process flow

The following diagram shows the high-level flow of the order to cash business process. Each solid rectangle in the diagram represents an end-to-end business process area. The arrows in the diagram show the flow of the business process in an organization. Subprocesses shown are for the order to cash business process. If a subprocess can lead to more than one other subprocess, the parallel subprocesses are shown as branches.

:::image type="content" source="media/order-to-cash-process-flow.svg" alt-text="Diagram of the order to cash process flow in an organization." lightbox="media/order-to-cash-process-flow.svg":::

The order to cash end-to-end business process flow diagram illustrates the following steps:

1. Start
1. Order to cash

    - Manage pricing and contracts
    - Create and manage sales orders

        Parallel branches are shown connecting to the following end-to-end processes, shown on the right side of the diagram: Case to resolution, Forecast to plan, Plan to produce, Procure to pay, and Product and service lifecycle management.

    - Fulfill sales orders

        A parallel branch connects to the Inventory to deliver end-to-end business process, shown on the right side of the diagram.

    - Issue customer invoices

        A parallel branch connects to the Record to report end-to-end business process, shown on the right side of the diagram.

    - Process customer rebates

        A parallel branch connects to the Record customer payments end-to-end business process.

    - Record customer payments

        A parallel branch connects to the Record to report end-to-end business process, shown on the right side of the diagram.

    - Monitor customer credit and collections

        A parallel branch connects to the Record to report end-to-end business process, shown on the right side of the diagram.

1. End

The **Start** box has the following parallel branches, shown on the left side of the diagram:

- **Case to resolution**, which connects to Manage pricing and contracts and Create and manage sales orders.

- **Forecast to plan**, which connects to Create and manage sales orders.

- **Plan to produce**, which connects to Create and manage sales orders.

- **Product and service lifecycle management**, which connects to Create and manage sales orders.

- **Prospect to quote**, which connects to Create and manage sales orders.

## Next steps

- Define the goals and objectives of [implementing an order to cash technology solution](../implementation-guide/implementation-strategy.md).

- Define the [business process scope](../implementation-guide/process-focused-solution.md) of your project.

- [Request a demo](https://dynamics.microsoft.com/dynamics-365-free-trial/) or get a free trial of Microsoft Business Applications solutions for the order to cash process.

- [Get an overview of the order to cash business process areas](order-to-cash-areas-overview.md).

## Related resources

- [Configure and manage the order to cash process in Dynamics 365 Supply Chain Management (online training)](/training/modules/configure-manage-order-cash-dyn365-supply-chain-mgmt)

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Rachel Profitt](https://www.linkedin.com/in/rachelprofitt/) | Senior Program Manager, FastTrack for Dynamics 365

<!--## Tags
*Stakeholders*: Accounts receivable, Administrative, Customer services, Engineering, Finance, IT, Marketing, Merchandising, Operations, Production, Purchasing, Retail store operations, Sales, Service operations, Transportation, Treasury, Warehouse

*Products*: Dynamics 365 Commerce, Dynamics 365 Customer Insights, Dynamics 365 Customer Service, Dynamics 365 Finance, Dynamics 365 Fraud Protection, Dynamics 365 Intelligent Order Management, Dynamics 365 Marketing, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management
-->
