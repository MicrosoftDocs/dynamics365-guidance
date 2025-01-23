---
title: Procure goods and services overview
description: Learn about the procure goods and services business process, including information about stakeholders and the business process flow.
author: akbism
ms.author: kumaramar
ms.date: 12/10/2024
ms.topic: conceptual
---

# Procure goods and services overview

***Applies to: Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management***

This article describes how you can use Dynamics 365 products to support your organization's business processes for procuring goods and services.

The procurement of goods and services within the *Source to pay* business process focuses on efficiently meeting the organization's needs by acquiring essential goods or services. It covers the activities that are required to raise the order to the external vendor. The goals are to ensure the availability of goods and services for the organization, and to efficiently manage inventory levels and cost.

Procurement of goods and services requires coordination and communication between many departments, such as engineering, operations, quality sales, planning, and production.

Dynamics 365 Supply Chain Management has extensive capabilities for sourcing and procuring goods and services. These capabilities ensure that projects and processes can proceed efficiently and successfully in the business process for procuring goods and services.

To initiate the procurement process, a **purchase requisition** (PR) is created that identifies internal needs.

The organization uses the **request for quotation** (RFQ) process to gather competitive bids and select the most suitable supplier. The vendor collaboration portal enables external vendors to participate in the request for quotation process and helps improve communication about specific requests for quotation.

The **purchase agreement** process allows for the creation of a contract that commits the organization to buying a specified quantity or amount over time, through multiple purchase orders. In exchange for this commitment, the buyer receives special prices and discounts.

The **purchase order** (PO) finalizes the agreement. It provides details about the terms and conditions of the transaction and authorizes the supplier to fulfill the order.

Together, the purchase requisition, request for quotation, purchase agreement, and purchase order documents streamline the procurement process, ensure transparency, and contribute to an effective and efficient purchasing process.

The outcomes of the procurement process, including quality, quantity, price, and timing/date, significantly affect the overall performance and profitability of the organization.

Define this business process at the beginning of the implementation of Dynamics 365 Supply Chain Management. It's a foundational process for any organization.

## Stakeholders

Many people across the organization should contribute to the business process for procuring goods and services. The list includes but isn't limited to:

- **Procurement stakeholders**, such as buying agents, purchasing agents, and purchasing managers. These stakeholders are directly involved in the *procure goods and services* business process area.
- **Production stakeholders**, such as production supervisors, production managers, and material managers. These stakeholders ensure that inventory is available for production processes.
- **Retail stakeholders**, such as retail store managers. These stakeholders monitor the supply of goods to ensure store operations.
- **Project stakeholders**, such as project managers and project assistants. These stakeholders ensure the availability of services and goods for their respective projects.
- **Finance stakeholders**, such as accounts payable clerks, budget managers, treasurers, and accountants. These stakeholders closely monitor the process of procuring material and services, so that they can plan their activities that are related to accounts payable.

## Procure goods and services process flow

The following diagram illustrates the *procure goods and services* business process area. 

:::image type="content" source="media\source-to-pay-procure-materials-services.svg" alt-text="Diagram of the source to pay procure goods and services process flow." lightbox="media\source-to-pay-procure-materials-services.svg":::

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

> [!IMPORTANT]
> The diagram is not yet updated. But the following text is updated. [!INCLUDE [bus-proc-cat-pending](../includes/bus-proc-cat-pending.md)]

The flow diagram covers the following steps.

1. Start

2. *Source to pay* end-to-end process

3. *Procure goods and services* business process area

    1. *Raise purchase requisitions*
    2. *Issue purchase order*
    3. *Manage open purchases*
    4. *Issue blanket purchase orders*  
    5. *Return goods to suppliers*  
    6. *Consolidate requisitions*  
    7. *Analyze supply purchase plan*

4. *Manage accounts payable* business process area

5. *Analyze procurement and sourcing* business process area

6. End

## Procure goods and services benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the *procure goods and services* business process area. The following sections outline the key benefits that an organization might monitor and measure for *procure goods and services*.

### Improved procurement and sourcing accuracy

Accurate identification of direct and indirect procurement needs is the first, crucial step in the procurement process. It involves determining what goods and services the business requires, in what amount, when, and where. This step helps prevent unnecessary or wasteful purchases, optimize the use of resources and budget, and align the procurement strategy with business goals.

### Efficient processing of purchase orders

A well-defined purchase order processing system helps an organization save time, money, and resources when it procures goods and services. It also helps improve the quality and compliance of the products and services, and provides useful data and insights for optimization.

In Dynamics 365 Supply Chain Management, the purchase order processing capability is well integrated with inventory and finance processes. It serves as one of the key capabilities for conducting an efficient, streamlined, and end-to-end procurement process.

### Streamlined approval workflow

Procurement and sourcing workflows in Dynamics 365 Supply Chain Management help automate the approval process for various documents and ensure consistent and efficient processes. You can track the status and performance of each workflow and manage your tasks from a centralized work list.

To manage the processes that are related to procuring goods and services, you can use a workflow framework that is extended for purchase requisition, purchase agreement, and purchase order processes.

### Enhanced compliance

Organizations can use the change management feature in Dynamics 365 Supply Chain Management to manage the modifications that are applied to purchase orders. This feature adds a workflow when a purchase order is changed, to provide an extra level of approval for any change.

Whenever an approved purchase order is confirmed, it creates a confirmation journal. This confirmation journal keeps a snapshot of what was confirmed as part of the purchase order. Therefore, it provides a better trail for audit purposes.

## Next steps

If you would like to implement Dynamics 365 solutions to assist with your *procure goods and services* business processes, you can use the following resources and steps to learn more. (Links are added, when the articles are ready.)

1. *Define procurement and sourcing strategies*

2. [Manage supplier relationships](source-to-pay-manage-vendor-relationships-overview.md)  

3. *Manage supplier relationships*

4. *Procure goods and services* (the article that you're currently reading)

5. [Manage accounts payable](source-to-pay-process-vendor-invoices-overview.md)  

6. *Analyze procurement and sourcing*  

## Related information

You can use the following resources to learn more about the *procure goods and services* process in Dynamics 365.

- [Purchase requisition overview](/dynamics365/supply-chain/procurement/purchase-requisitions-overview)
- [Purchase requisition workflow](/dynamics365/supply-chain/procurement/purchase-requisitions-workflow)
- [Requests for quotation (RFQs) overview](/dynamics365/supply-chain/procurement/request-quotations)
- [Purchase order overview](/dynamics365/supply-chain/procurement/purchase-order-overview)
- [Approve and confirm purchase orders](/dynamics365/supply-chain/procurement/purchase-order-approval-confirmation)
- [Purchase agreements](/dynamics365/supply-chain/procurement/purchase-agreements)
- [Vendor collaboration portal](/dynamics365/supply-chain/procurement/vendor-collaboration-work-external-vendors)
- [Create a purchase return order](/dynamics365/supply-chain/procurement/tasks/create-purchase-return-order)
- Find definitions of terminology that's used in content for *procure goods and services* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article. For example, this glossary includes the following terms:

  - [Purchase agreement](glossary.md#purchase-agreement)
  - [Purchase order](glossary.md#purchase-order)
  - [Purchase requisition](glossary.md#purchase-requisition)
  - [Request for quotation](glossary.md#request-for-quotation)

<!-- ## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Accounts payable, Finance, Operations, Production, Purchasing, Project

*Products:* Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Amar Kumar](https://www.linkedin.com/in/amark352/) \| Senior Solutions Architect, FastTrack for Dynamics 365

Other contributors:

- [Adi Vijayashankar](https://www.linkedin.com/in/adithya-adi-vijayashankar-b3490a16/) \| Senior Solutions Architect, FastTrack for Dynamics 365
