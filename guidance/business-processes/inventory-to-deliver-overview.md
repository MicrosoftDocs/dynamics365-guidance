---
title: Inventory to deliver end-to-end overview
description: Learn about the end-to-end business process, from inventory to deliver. This article provides a high-level flow diagram and describes the relationship with other processes in Dynamics 365 solutions.
ms.date: 03/22/2023
ms.topic: conceptual
author: rachel-profitt
ms.author: raprofit
ms.reviewer: edupont
---

# Inventory to deliver end-to-end overview

***Applies to: Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center***

This article provides a high-level flow diagram and an overview for each of the business process areas in the end-to-end business process *from inventory to deliver*. The article also describes this business process' relationship to other business processes in Dynamics 365.

## Inventory to deliver process relationship

The following diagram shows the relationship of other processes and products/features for the *inventory to deliver* process.

:::image type="content" source="media/inventory-to-deliver1.png" lightbox="media/inventory-to-deliver1.png" alt-text="Business process relationships with upstream and downstream processes that are explained in the next paragraphs.":::

The upstream processes for the *inventory to deliver* process include the following.

- **Concept to market**  

  Mandatory prerequisite: A service must exist before you can ship the service.

- **Design to retire**  

  Mandatory prerequisite: An item must exist before you can begin to receive, handle inventory, or ship the product.

- **Procure to pay**  

  When you use Dynamics 365 to manage your procurement process, the *inventory to deliver* process requires a purchase order to exist to receive the inventory. There are also downstream processes that happen after the *inventory to deliver* process is complete, such as the *procure to pay* process.

- **Order to cash**  

  When you use Dynamics 365 to manage your sales process, the *inventory to deliver* process requires a sales order to deliver the inventory. There are also downstream processes that happen after the *inventory to deliver* process is complete, such as the *order to cash* process.

- **Service to cash**  

  When you use Dynamics 365 to manage your service process, the *inventory to deliver* process includes outbound handling, for example: loading spare parts into a delivery truck.

- **Plan to produce**  

  When you use Dynamics 365 to manage your production process, there are overlaps with the *inventory to deliver* process for both inbound and outbound processes. For example: issuing raw materials to a production order and reporting a production order as finished have inventory implications.

- **Project to profit**  

  When you use Dynamics 365 to manage your project process, there can be connections to the *inventory to deliver* process for both inbound and outbound inventory. For example, in some industries, especially engineer-to-order business models, the project process includes production orders. There can also be purchases and/or sales for specific projects, which are referred to as item requirements. When projects are used to manage services, for example: professional services or maintenance services, there can also be a connection to the service to cash process.

The *inventory to deliver* end-to-end process is broken down into the following business process areas:

- Define and manage warehouse operations

- Process inbound goods

- Manage inventory quality

- Maintain inventory levels

- Manage inventory costs

- Record and control costs

- Process outbound goods

- Manage freight and transportation

- Control vendor managed inventory and consignment inventory

- Analyze warehouse performance

The downstream processes for the *inventory to deliver* process include the following.

- **Procure to pay**  

  When the *inventory to deliver* process is completed as a sub process in the procure to pay process, the procure to pay process continues. For example, the invoicing and payment for the purchases.

- **Order to cash**  

  When the *inventory to deliver* process is completed as a sub process in the order to cash process, the order to cash process continues. For example, the invoicing, payment and collection of payment for the sales.

- **Service to cash**  

  When the *inventory to deliver* process is completed as a sub process in the service to cash process, the service to cash process continues. For example, the invoicing, payment and collection of payment for the service.

- **Plan to produce**  

  When the *inventory to deliver* process is completed as a sub process in the plan to produce process, the plan to produce process continues. For example, the ending of production orders and analyzing of production costs.

- **Project to profit**  

  When the *inventory to deliver* process is completed as a sub process in the project to profit process, the project to profit process continues. For example, the invoicing of the project for external projects, the capitalization and conversion to an asset of the project for internal capital projects, or the expensing of the project for other internal non-capital projects.

- **Case to resolution**  

  The *case to resolution* process can optionally be used downstream to handle and respond to quality issues with vendors; this process is also the starting point for many returns and exchanges, for example.

- **Record to report**  

  When you use Dynamics 365 to manage your financials, the *inventory to deliver* process is tightly integrated with the record to report process. The *inventory to deliver* process is responsible for the management of the inventory subledger and records vouchers into the general ledger throughout the process.

## Featured capabilities

There are product-specific capabilities that interact with the *inventory to deliver* to process including, but not limited to, the following:

- **Advanced warehouse management (mobile device)**  

  The *Process inbound goods* and*Process Outbound goods* business process areas can optionally use advanced warehouse management processes to automate and simplify the inventory processes on the warehouse floor using mobile devices.

- **Transportation management**  

  The Transportation management module in Dynamics 365 Supply Chain Management can be used to help manage the inbound and outbound processing of goods, including but not limited to, rating, routing, and reconciling freight invoices.

- **Cross docking**  

  When you need to tightly integrate your inbound and outbound processes to minimize the handling of inventory, cross docking capabilities allow you to receive goods, and immediately distribute them through the outbound process without the need to put the inventory into intermediate storage.

- **Cost accounting**  

  When you have complex requirements for managing the cost of your products or produced items, you can use the Cost accounting module in Dynamics 365 Supply Chain Management to keep a set of books that help you monitor and control your inventory costs closely.

- **Global inventory accounting add-in**  

  The Global inventory accounting add-in, which is part of Dynamics 365 Supply Chain Management, allows organizations to track the value of inventory in multiple ways. For example: multiple currencies, multiple costing methodologies, or multiple accounting standards such as IFRC or GAAP.

- **Production floor execution**  

  The Production floor execution features can be used on your production floor to help manage the inventory receipt and report as finished processes when you use Dynamics 365 Supply Chain Management to manage your production process.

- **Dynamics 365 Guides**  

  You can use Halo Lens with Dynamics 365 Guides to deliver mixed reality solutions through Production floor execution or as a training tool in your inventory to help optimize your *inventory to deliver* business processes.

- **Supply chain insights with Microsoft Supply Chain Center**  

  You can synchronize your data from first party applications or third-party applications to the Dataverse to use advanced analytics capabilities for monitoring your supply chain.

- **Intelligent Order Management with Microsoft Supply Chain Center:** You can orchestrate your order fulfillment operations using this solution built on the Power Platform.

## Inventory to deliver business process flow

The following diagram shows the high-level flow of the *inventory to deliver* business process. [!INCLUDE [daf-business-process-e2e-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-e2e-flow-def.md)]

:::image type="content" source="media/inventory-to-deliver2.png"  lightbox="media/inventory-to-deliver2.png" alt-text="inventory to deliver end-to-end process flow diagram":::

The following steps are illustrated in the *inventory to deliver* end-to-end business process flow diagram.

1. *inventory to deliver* end-to-end process  

    1. Define and manage warehouse operations
    2. Manage inventory quality
    3. Manage inventory costs
    4. Record and control costs
    5. Report to report
    6. End

2. Project to profit end-to-end process  

    Parallel branches from *Project to profit* connect to *Procure to pay*, *Plan to produce*, *Order to cash*, and *Service to cash*.

3. Product and service lifecycle management

    The diagram doesn't illustrate connections, but product and service lifecycle management are also upstream process for the *Produce to pay*, *Plan to produce*, *Order to cash*, and *Service to cash* business processes.

4. Procure to pay end-to-end process  

    1. Manage inbound freight and transportation

        1. Process inbound goods

        2. Control vendor management inventory

    2. Manage inventory quality

    3. Manage inventory costs

    4. Record and control costs

    5. Record to report

    6. End

5. Plan to produce end-to-end process  

    1. Process inbound goods

    2. Process outbound goods

    3. Manage outbound freight and transportation

    4. Manage inventory quality

    5. Manage inventory costs

    6. Record and control costs

    7. Record to report

    8. End

6. Order to cash end-to-end process  

    1. Process outbound goods

    2. Manage outbound freight and transportation

    3. Manage inventory quality

    4. Manage inventory costs

    5. Record and control costs

    6. Record to report

    7. End

7. Service to cash end-to-end process  

    1. Process outbound goods

    2. Manage outbound freight and transportation

    3. Manage inventory quality

        A parallel branch from this subprocess is *Case to resolution*, which connects to *End*.

    4. Manage inventory costs

        A parallel branch from this subprocess is *Record to Report*, which connects to *End*.
    5. Record and control costs

    6. Record to report

    7. End

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *inventory to deliver* business processes, learn more at the following resources and steps.

[Inventory to deliver - introduction to the end-to-end business process](inventory-to-deliver-introduction.md)  
[Inventory to deliver business process areas](inventory-to-deliver-areas.md)

## Related resources

Use the following resources to learn more about the *inventory to deliver* process in Dynamics 365.

- [TechTalk Series: Warehouse & Transportation Management in Dynamics 365 Supply Chain Management - Microsoft Dynamics Blog](https://community.dynamics.com/blogs/post/?postid=4b4d8aa8-2922-4fe8-b93f-a404cb59e5d4)

- [Inventory management overview](/dynamics365/supply-chain/inventory/inventory-home-page)

- [Warehouse management overview](/dynamics365/supply-chain/warehousing/warehouse-management-overview)

- [Transportation management overview](/dynamics365/supply-chain/transportation/transportation-management-overview)

- [Dynamics-365-FastTrack-Implementation-Assets/SCM in GitHub](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM)

<!--## Tags
*Stakeholders:* Functional consultant, Business analyst, Accounts payable lead, Accounts receivable lead, Finance lead, Sales lead, Purchasing lead, Production lead, Supply chain lead, Warehouse lead, Transportation lead…

*Products:* Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center