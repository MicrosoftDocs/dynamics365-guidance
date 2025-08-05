---
title: Overview of the Process outbound goods business process area
description: Read about the business process area for managing outbound goods in Dynamics 365 implementations.
ms.topic: concept-article
author: vibhutinair23
ms.author: vibhutinair
ms.date: 07/30/2025
---

# Overview of the Process outbound goods business process area within the Inventory to deliver end-to-end scenario

***Applies to: Dynamics 365 Supply Chain Management, Dynamics 365 Business Central***

This article describes the business process area of *processing outbound goods*, which is part of the *inventory to deliver* end-to-end business process. This article also describes how you can use Dynamics 365 to handle your business process flow for processing outbound goods including picking and shipping operations within your warehouse.

The *Process outbound goods* business process flow covers the business processes your company executes to send materials or goods from your warehouse to another party. Most business processes with outbound goods cover the shipping of goods from your warehouse to a customer. However, your business might have to transfer goods and materials from one site or facility to another. In organizations that manufacture products, it might include transferring inventory from the production facility to the distribution center. In other situations where production is outsourced, it might include shipping the partially produced items to a supplier who adds value-added services to the inventory and returns it to your warehouse. Also, there might come a need to manage the process of returning goods to the vendor. Dynamics 365 supports various warehouse operating models including the use of third-party warehouses or distribution centers (3PL), consigned inventory, and distribution models, or drop shipment models.

In some organizations, customer service dictates the outbound processing and in others, warehouse operations. Customer service is close to the customer, and the warehouse is close to the inventory. Either can decide what is the best inventory to ship and it might vary from one facility to another.

Business decision makers should define these business processes early in the implementation when they're designing how to use the system to best meet their requirements.

## Stakeholders

Many people across the organization should contribute to the decision-making process and design of the *process outbound goods* area. The following list provides examples of such stakeholders:

- **Operations stakeholders** such as the Supply Chain Manager
- **Warehouse management stakeholders** such as the Manager, Shipping and Receiving Clerk, Material Handler, Fulfillment Specialist, Order Picker, and Forklift Operator.

## Process outbound goods process flow

The following diagram illustrates the *process outbound goods* business process area.

:::image type="content" source="media/inventory-to-deliver-process-outbound-goods.svg" alt-text="Diagram showing the process outbound goods process flow." lightbox="media/inventory-to-deliver-process-outbound-goods.svg":::

The flow diagram covers the following steps:

1. Start
2. *Process outbound goods* business process area
   1. *Allocate goods*
   2. *Release goods for picking*
   3. *Pick goods*
   4. *Pack goods*
   5. *Load goods for shipping*
   6. *Cross dock produced goods*
   7. *Return goods to vendor*
3. End

## Benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support *process outbound goods*. The following sections outline the key benefits that an organization might monitor and measure for the process outbound goods.

### Prioritize inventory allocation

With Dynamics 365 Supply Chain Management, there are several options to support order allocations. Businesses can require order entry to manually maintain reservations. Alternatively, they can use automated processes to perform order reservations. By applying priority criteria to order reservation and release, businesses can ensure that inventory is allocated to high priority orders, rather than simply following a first-in, first-out approach. Minimizing the need for user intervention to move reservations around can lead to improved worker efficiencies. This also reduces the number of dissatisfied customers and decreases supply chain "noise" overall.

### Gain operation efficiencies

With both Dynamics 365 Supply Chain Management and Dynamics 365 Business Central, businesses can configure a solution that handles several different outbound order scenarios. Using tools such as Cross Docking reduces the number of times the goods get touched in the warehouse. Removing put-away and picking processes for orders that need the inventory immediately allows users in the warehouse to concentrate on other high priority tasks.

### Maximize customer satisfaction

Having a clearly defined order allocation process and outbound distribution processes can streamline operations that result in accurate inventory picking and improved on time in full shipping (OTIF). These processes reduce the number of late shipments and inaccurate shipments. The reduced numbers increase customer satisfaction and decrease Customer Returns.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *process outbound goods* business processes, you can use the following resources and steps to learn more. (Links are added when the articles are ready.)

1. [Manage warehouse operations](inventory-to-deliver-define-manage-warehouse-operations-overview.md)
2. [Maintain inventory levels](inventory-to-deliver-maintain-inventory-levels-overview.md)  
3. *Process inbound goods*
4. *Process outbound goods* (the article that you're currently reading)
   1. *Allocate goods*
   2. *Release goods for picking*
   3. *Pick goods*
   4. *Pack goods*
   5. *Load goods for shipping*
   6. *Cross dock produced goods*
   7. *Return goods to vendor*
5. *Manage inventory quality*
6. [Manage freight and transportation](inventory-to-deliver-manage-freight-transportation.md)
7. *Analyze warehouse operations*

## Related resources

You can use the following resources to learn more about the *process outbound goods* process in Dynamics 365.

- [Design details: Outbound warehouse processes - Business Central](/dynamics365/business-central/design-details-outbound-warehouse-flow)
- [Pick items with inventory picks - Business Central](/dynamics365/business-central/warehouse-how-to-pick-items-with-inventory-picks)
- [Design details: Flows for production, assembly, and projects - Business Central](/dynamics365/business-central/design-details-internal-warehouse-flows)
- [Walkthrough: Picking and Shipping in Basic Warehouse Configurations - Business Central](/dynamics365/business-central/walkthrough-picking-and-shipping-in-basic-warehousing)
  
<!-- ## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Wholesale Trade (50-51), Retail Trade (52-59)

*Stakeholders:* Operations, Production, Warehouse

*Products:* Dynamics 365 Business Central, Dynamics 365 Supply Chain Management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [James Cox](https://www.linkedin.com/in/james-cox/) \| Senior Dynamics 365 Pre-Sales Solution Architect at Microsoft

Other contributors:

- [Tatiana Sahagun](https://www.linkedin.com/in/tatianasahagun/) \| Senior Consultant, Industry Strategy and Delivery at Microsoft
