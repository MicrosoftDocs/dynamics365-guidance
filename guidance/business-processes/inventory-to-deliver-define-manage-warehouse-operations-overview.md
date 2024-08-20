---
title: Define and manage warehouse operations overview
description: Read about the business process area for managing warehouse operations in Dynamics 365 implementations.
ms.date: 08/12/2024
ms.topic: conceptual
author: edupont04
ms.author: raprofit
ai-usage: ai-assisted
---

# Define and manage warehouse operations strategy and policies overview

***Applies to: Dynamics 365 Business Central, Dynamics 365 Finance, Dynamics 365 Supply Chain Management***

This article describes how you can use Dynamics 365 products to support the inventory and warehouse operations of your organization.

Using technology to manage warehouse operations can be important for several reasons. For example, technology can help the organization gain efficiency and productivity, consistency and quality, cost reduction, risk management, scalability, and data-driven decision-making.

Inventory management systems can help you track the quantity, location, and status of your inventory items across multiple warehouses or locations. It can also help you optimize your inventory levels, reduce waste and excess stock, improve customer service and satisfaction, and streamline your order fulfillment and delivery processes. An inventory management system can also provide you with valuable insights and analytics on your inventory performance. Examples include the turnover rate, demand forecasting, replenishment planning, and inventory valuation.

The *define and manage warehouse operations strategy and policies* area is where an organization makes strategic decisions about how to handle inventory in their technology solution. This process involves defining the warehouse structure, layout, and hierarchy, as well as the inventory policies, rules, and workflows that apply to different warehouse scenarios. For example, an organization decides to use drop shipments, consigned inventory, multiple warehouses for fulfillment, third-party logistics, or other methods to manage their inventory and distribution. These decisions affect how the warehouse operates, controls, and manages the inventory, as well as how the organization records and reports inventory transactions. Dynamics 365 offers a robust range of configurations to support various operation models and business requirements.

We recommend that you make these strategic decisions and define the overall logistics flow early in an implementation project. These decisions have significant implications for the data migration, configuration, integration, and testing phases. However, if an organization has an existing Enterprise Resource Planning (ERP) system, they can use the *warehouse management only* mode to use the *warehouse management* functionality of Dynamics 365 Supply Chain Management. That way, they can integrate their warehouse operations with their ERP system without affecting the financial or operational aspects of their ERP system. Learn more at [Warehouse management only mode overview](/dynamics365/supply-chain/warehousing/wms-only-mode-overview).  

## Stakeholders

Many people across the organization should contribute to the decision-making process and design of the *define and manage warehouse operations strategy and policies* area. The following list provides examples of such stakeholders:

- **Warehouse manager**: This stakeholder is responsible for overseeing the daily operations of the warehouse, such as receiving, storing, picking, packing, and shipping goods. The warehouse manager can provide input on the warehouse layout, locations, zones, work centers, and picking strategies. They also  provide input on the integration with the ERP system and other external systems.

- **Inventory controller**: This stakeholder is responsible for maintaining accurate and optimal inventory levels. They make sure that inventory policies and procedures are followed, and that inventory transactions, adjustments, transfers, and counts are performed. The inventory controller provides input on the inventory valuation methods, inventory dimensions, inventory journals, and inventory adjustment rules. They can also provide input on the reporting and analysis of inventory data.

- **Logistics coordinator**: This stakeholder is responsible for planning and executing the transportation and delivery of goods from the warehouse to the customers, as well as managing the inbound and outbound shipments and returns. The logistics coordinator can provide input on the requirements for transportation management, such as carriers, modes, routes, rates, and load planning. They can also provide input on the integration with the warehouse management and sales order processing modules.

- **Warehouse worker**: This stakeholder is responsible for performing the physical tasks of the warehouse operations. That's tasks such as scanning barcodes, moving pallets, picking items, packing boxes, and loading trucks. The warehouse worker can provide input on the user interface, devices, and workflows of the warehouse management mobile app, as well as the training and support needs.

## Define and manage warehouse operations strategy and policies process flow

The following diagram shows the high-level flow of the *define and manage warehouse operations strategy and policies* business process area.

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/inventory-to-deliver-define-manage-warehouse-ops-flow.svg" alt-text="Diagram that shows business process relationships with upstream and downstream processes that are explained in the next paragraphs." lightbox="media/inventory-to-deliver-define-manage-warehouse-ops-flow.svg":::

The following steps are illustrated in the *define and manage warehouse operations strategy and policies* business process flow diagram.

1. Start

2. *Inventory to deliver*

    1. *Define and manage warehouse operations*

        1. Define warehouse operations processes

        2. Document warehouse layout

        3. Document warehouse policies

        4. Identify warehouse worker access

        5. Define key performance indicators for warehouse operations

        6. Analyze warehouse performance

    2. *Maintain inventory levels*

        1. Process outbound goods

        2. Process inbound goods

    3. *Manage freight and transportation*

3. *Case to resolution*

4. End

The process starts with the [Inventory to deliver](inventory-to-deliver-overview.md) scenario, where the journey of managing warehouse inventory for delivery begins. We *define and manage warehouse operations*, which involves setting up the processes, documenting the physical layout, and defining the policies and worker access within the warehouse. Once we've defines these processes, we establish the *key performance indicators (KPIs) for warehouse operations* to measure our success and efficiency.  

In parallel with these business processes, we *maintain inventory levels* to ensure we have the right amount of stock on hand. In this business process area, we *process outbound goods* for delivery and *process inbound goods* for storage to help make sure there's a smooth flow of items in and out of the warehouse. Concurrently, we [manage freight and transportation](inventory-to-deliver-manage-freight-transportation.md) to handle the logistics of moving goods.  

Finally, we *analyze warehouse performance* to identify areas of improvement. This business process leads to the [case to resolution](case-to-resolution-overview.md) scenario, where any outstanding issues or special cases are resolved.

## Define and manage warehouse operations benefits

This section outlines the key benefits that organizations can use to monitor and measure the success of implementing technology to support the *define and manage warehouse operations* business process area.  

### Integrated data

When their ERP solution supports warehouse operations, businesses have a centralized platform that integrates customer data with inventory and order information. This way, they can maintain a holistic view of customer interactions and order fulfillment.

### Inventory visibility

In both Dynamics 365 Supply Chain Management and Business Central, the warehouse capabilities provide real-time visibility into inventory levels. This helps businesses keep track of stock levels, reduce the risk of stockouts, and optimize inventory turnover.

### Optimize warehouse performance

By consolidating warehouse data within a single solution such as Dynamics 365, businesses can use analytics tools to gain insights into warehouse performance. This data-driven approach enables better decision-making regarding inventory levels, order fulfillment strategies, and overall warehouse efficiency.

### Improved customer satisfaction

Warehouse operations impact order delivery times and product availability, directly influencing customer satisfaction. Using the warehouse capabilities in Dynamics 365 Supply Chain Management or Business Central can contribute to improved customer service by ensuring timely and accurate order deliveries. These solutions easily integrate with ordering systems including Dynamics 365 Sales to provide real-time visibility to the sales frontline to provide up to date and accurate information to customers.

### Enhance inventory visibility and traceability 

With Dynamics 365 Supply Chain Management or Business Central, businesses can have full visibility and traceability of their inventory across the entire supply chain. This way, they can track the origin, location, and expiration of each product, batch, or serial number. For example, in the food industry, this process can help ensure food safety, quality, and compliance by quickly identifying and recalling any contaminated or expired products.

### Optimize costs with efficient warehouse operations

Dynamics 365 helps you save costs by enabling efficient warehouse operations. You can avoid errors, reduce excess inventory, and improve overall efficiency with Dynamics 365 Supply Chain Management or Business Central. These solutions integrate with ordering systems, inventory management, and warehouse automation to streamline your processes and reduce waste.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *define and manage warehouse operations* business processes, you can use the following resources and steps to learn more. (Links are added, when the articles are ready.)

1. *Define and manage warehouse operations strategy and policies* (the article that you're currently reading)

2. *Maintain inventory levels*

    1. *Process inbound goods*

    2. *Process outbound goods*

3. *Manage inventory quality*

4. [Manage freight and transportation](inventory-to-deliver-manage-freight-transportation.md)

5. [Record and manage inventory costs](inventory-to-deliver-record-manage-inventory-costs.md)

## Related information

You can use the following resources to learn more about the *define and manage warehouse operations* business processes in Dynamics 365.

- [Warehouse management in Supply Chain Management](/dynamics365/supply-chain/warehousing/warehouse-management-overview)

- [Warehouse management only mode in Supply Chain Management](/dynamics365/supply-chain/warehousing/wms-only-mode-overview)

- [Get started with setting up the Warehouse management module in Supply Chain Management](/dynamics365/supply-chain/warehousing/get-started-with-setting-up-module)

- [Introduction to Warehouse Management - TechTalk](https://www.youtube.com/watch?v=cPxyxEwANP8)

- [Dynamics 365 Supply Chain Management: Warehouse Management Only Mode](https://www.youtube.com/watch?v=uOURvwXwY-E)

- [Set up warehouses in Business Central](/dynamics365/business-central/warehouse-setup-warehouse)  

- [Manage warehouse activities in Business Central](/dynamics365/business-central/design-details-warehouse-management)

- [Convert existing locations to warehouse locations in Business Central](/dynamics365/business-central/warehouse-how-to-convert-existing-locations-to-warehouse-locations)  

- Find definitions of terminology that is used in content for *define and manage warehouse operations* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article. For example, this glossary includes the following term:

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
