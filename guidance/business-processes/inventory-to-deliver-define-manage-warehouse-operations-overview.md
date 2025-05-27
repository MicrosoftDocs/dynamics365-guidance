---
title: Overview of the Manage warehouse operations business process area
description: Read about the business process area for managing the strategies and policies for the warehouse operations in Dynamics 365 implementations.
ms.date: 01/16/2025
ms.topic: concept-article
author: edupont04
ms.author: raprofit
ai-usage: ai-assisted
---

# Overview of the Manage warehouse operations business process area within the Inventory to deliver end-to-end scenario

***Applies to: Dynamics 365 Business Central, Dynamics 365 Finance, Dynamics 365 Supply Chain Management***

This article describes how you can use Dynamics 365 products to support the inventory and warehouse operations of your organization.

The use of technology to manage warehouse operations can be important for several reasons. For example, technology can help organizations gain efficiency and productivity, consistency and quality, cost reduction, risk management, scalability, and data-driven decision-making.

Inventory management systems can help you track the quantity, location, and status of your inventory items across multiple warehouses or locations. They can also help you optimize your inventory levels, reduce waste and excess stock, improve customer service and satisfaction, and streamline your order fulfillment and delivery processes. In addition, they can provide valuable insights and analytics about your inventory performance. Examples include the turnover rate, demand forecasting, replenishment planning, and inventory valuation.

The *define and manage warehouse operations* area is where organizations make strategic decisions about how to handle inventory in their technology solution. The process involves defining the warehouse structure, layout, and hierarchy, and also the inventory policies, rules, and workflows that apply to different warehouse scenarios. For example, an organization decides to use drop shipments, consigned inventory, multiple warehouses for fulfillment, third-party logistics, or other methods to manage its inventory and distribution. These decisions affect how the warehouse operates, controls, and manages the inventory. They also affect how the organization records and reports inventory transactions. Dynamics 365 offers a robust range of configurations to support various operation models and business requirements.

We recommend that you make these strategic decisions and define the overall logistics flow early in an implementation project. These decisions have significant implications for the data migration, configuration, integration, and testing phases. However, organizations that have an existing enterprise resource planning (ERP) system can use the *warehouse management only* mode to take advantage of the *warehouse management* functionality of Dynamics 365 Supply Chain Management. In this way, they can integrate their warehouse operations with their ERP system without affecting the financial or operational aspects of their ERP system. Learn more at [Warehouse management only mode overview](/dynamics365/supply-chain/warehousing/wms-only-mode-overview).

## Stakeholders

Many people across the organization should contribute to the decision-making process and design of the *define and manage warehouse operations strategy and policies* area. The following list provides examples of such stakeholders:

- **Warehouse manager**: This stakeholder is responsible for overseeing the daily operations of the warehouse, such as receiving, storing, picking, packing, and shipping goods. The warehouse manager can provide input about the warehouse layout, locations, zones, work centers, and picking strategies. They also provide input about the integration with the ERP system and other external systems.
- **Inventory controller**: This stakeholder is responsible for maintaining accurate and optimal inventory levels. They ensure that inventory policies and procedures are followed, and that inventory transactions, adjustments, transfers, and counts are performed. The inventory controller provides input about the inventory valuation methods, inventory dimensions, inventory journals, and inventory adjustment rules. They can also provide input about the reporting and analysis of inventory data.
- **Logistics coordinator**: This stakeholder is responsible for planning and carrying out the transportation and delivery of goods from the warehouse to the customers, and for managing the inbound and outbound shipments and returns. The logistics coordinator can provide input about the requirements for transportation management, such as carriers, modes, routes, rates, and load planning. They can also provide input about the integration with the warehouse management and sales order processing modules.
- **Warehouse worker**: This stakeholder is responsible for performing the physical tasks of the warehouse operations. Those tasks include scanning bar codes, moving pallets, picking items, packing boxes, and loading trucks. The warehouse worker can provide input about the user interface, devices, and workflows of the warehouse management mobile app. They can also provide input about training and support needs.

## Manage warehouse operations process flow

The following diagram shows the high-level flow of the *define and manage warehouse operations* business process area.

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/inventory-to-deliver-manage-warehouse-ops-flow.svg" alt-text="Diagram that shows business process relationships with upstream and downstream processes that are explained in the next paragraphs." lightbox="media/inventory-to-deliver-manage-warehouse-ops-flow.svg":::

The following steps are illustrated in the *manage warehouse operations* business process flow diagram.

1. Start
2. *Inventory to deliver*

    1. *Manage warehouse operations*

        1. *Define warehouse processes*
        2. *Design warehouse layout*
        3. *Document warehouse policies*
        4. *Manage work assignments*

    2. *Maintain inventory levels*

    3. *Manage freight and transportation*

    4. *Analyze warehouse performance*

3. *Case to resolution*
4. End

The process starts with the [Inventory to deliver](inventory-to-deliver-overview.md) scenario, where the journey of managing warehouse inventory for delivery begins. First, you define and manage the strategy and policies for the warehouse operations. This step involves setting up the processes, documenting the physical layout, and defining the policies and worker access in the warehouse. After you define these processes, you establish the *key performance indicators (KPIs) for warehouse operations* to measure success and efficiency.

In parallel with these business processes, you [*maintain inventory levels*](inventory-to-deliver-maintain-inventory-levels-overview.md) to ensure that you have the correct amount of stock on hand. In this business process area, you *process outbound goods* for delivery and *process inbound goods* for storage, to help ensure a smooth flow of items into and out of the warehouse. Concurrently, you [*manage freight and transportation*](inventory-to-deliver-manage-freight-transportation.md) to handle the logistics of moving goods.

Finally, you *analyze warehouse performance* to identify areas of improvement. This business process leads to the [case to resolution](case-to-resolution-overview.md) scenario, where any outstanding issues or special cases are resolved.

## Define and manage warehouse operations benefits

This section outlines the key benefits that organizations can use to monitor and measure the success of implementing technology to support the *manage warehouse operations* business process area.

### Integrated data

When their ERP solution supports warehouse operations, businesses have a centralized platform that integrates customer data with inventory and order information. Therefore, they can maintain a holistic view of customer interactions and order fulfillment.

### Inventory visibility

In both Dynamics 365 Supply Chain Management and Business Central, the warehouse capabilities provide real-time visibility into inventory levels. This visibility helps businesses keep track of stock levels, reduce the risk of stockouts, and optimize inventory turnover.

### Optimized warehouse performance

By consolidating warehouse data in a single solution, such as Dynamics 365, businesses can use analytics tools to gain insights into warehouse performance. This data-driven approach enables better decision-making about inventory levels, order fulfillment strategies, and overall warehouse efficiency.

### Improved customer satisfaction

Because warehouse operations affect order delivery times and product availability, they directly influence customer satisfaction. Use of the warehouse capabilities in Dynamics 365 Supply Chain Management or Business Central can contribute to improved customer service by ensuring timely and accurate order deliveries. These solutions easily integrate with ordering systems, including Dynamics 365 Sales, to provide real-time visibility into the sales frontline. In this way, up-to-date and accurate information can be provided to customers.

### Enhanced inventory visibility and traceability

With Dynamics 365 Supply Chain Management or Business Central, businesses can have full visibility and traceability of their inventory across the entire supply chain. In this way, they can track the origin, location, and expiration of each product, batch, or serial number. For example, in the food industry, this process can help ensure food safety, quality, and compliance by quickly identifying and recalling any contaminated or expired products.

### Optimized costs with efficient warehouse operations

Dynamics 365 helps you save costs by enabling efficient warehouse operations. With Dynamics 365 Supply Chain Management or Business Central, you can avoid errors, reduce excess inventory, and improve overall efficiency. These solutions integrate with ordering systems, inventory management, and warehouse automation to streamline your processes and reduce waste.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *manage warehouse operations* business processes, you can use the following resources and steps to learn more. (Links are added when the articles are ready.)

1. *Manage warehouse operations* (the article that you're currently reading)  

    1. *Define warehouse processes*  
    1. *Design warehouse layout*  
    1. *Document warehouse policies*  
    1. *Manage work assignments*

1. [Maintain inventory levels](inventory-to-deliver-maintain-inventory-levels-overview.md)  
1. *Process inbound goods*
1. *Process outbound goods*
1. *Manage inventory quality*
1. [Manage freight and transportation](inventory-to-deliver-manage-freight-transportation.md)
1. *Analyze warehouse operations*

## Related information

You can use the following resources to learn more about the *manage warehouse operations* business processes in Dynamics 365.

- [Warehouse management in Supply Chain Management](/dynamics365/supply-chain/warehousing/warehouse-management-overview)
- [Warehouse management only mode in Supply Chain Management](/dynamics365/supply-chain/warehousing/wms-only-mode-overview)
- [Get started with setting up the Warehouse management module in Supply Chain Management](/dynamics365/supply-chain/warehousing/get-started-with-setting-up-module)
- [Introduction to Warehouse Management - TechTalk](https://www.youtube.com/watch?v=cPxyxEwANP8)
- [Dynamics 365 Supply Chain Management: Warehouse Management Only Mode](https://www.youtube.com/watch?v=uOURvwXwY-E)
- [Set up warehouses in Business Central](/dynamics365/business-central/warehouse-setup-warehouse)
- [Manage warehouse activities in Business Central](/dynamics365/business-central/design-details-warehouse-management)
- [Convert existing locations to warehouse locations in Business Central](/dynamics365/business-central/warehouse-how-to-convert-existing-locations-to-warehouse-locations)
- Find definitions of terminology that is used in content for *manage warehouse operations* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article. For example, this glossary includes the following term:

  - [Registrations](glossary.md#registrations)

<!-- 
## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59)

*Stakeholders:* Engineering, IT, Marketing, Merchandising, Operations, Production, Purchasing, Sales, Transportation, Warehouse

*Products:* Dynamics 365 Business Central, Dynamics 365 Finance, Dynamics 365 Supply Chain Management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Donny Badamo](https://www.linkedin.com/in/donnybadamo/) \| Microsoft Project Manager

Other contributors:

- [Rachel Profitt](https://www.linkedin.com/in/rachelprofitt/) \| Principal Program Manager

<!-- **Note:** The author created this article with assistance from AI. [Learn more](/principles-for-ai-generated-content/) -->
