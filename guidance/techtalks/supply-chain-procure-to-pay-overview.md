---
title: TechTalk Procure to pay in Dynamics 365 Supply Chain Management 
description: Summary of TechTalk video that talks about how Supply Chain Management supports the business processes that are part of the procure-to-pay end-to-end process.
ms.date: 10/15/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Procure to pay in Dynamics 365 Supply Chain Management

In today's fast-paced business environment, procurement plays a critical role in ensuring efficient operations. Managing the acquisition of goods and services, cost forecasting, and negotiating with vendors are key to impacting both production and customer satisfaction. In this article, we will explore the end-to-end procure-to-pay process in Dynamics 365 Supply Chain Management, focusing on its capabilities, the steps involved, and how businesses can optimize their procurement cycles.  

We based this article on [a TechTalk](https://youtu.be/BUN861PBA6Q) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/DTV004-p2p-slide.png" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/BUN861PBA6Q":::

> [!TIP]
> This TechTalk predates the TechTalk [Overview of the source to pay business process in Dynamics 365 Finance and Dynamics 365 Supply Chain Management](dynamics-365-finance-supply-chain-management-source-to-pay.md). For an all-up overview of the end-to-end business processes, go to the [Source to pay end-to-end overview](../business-processes/source-to-pay-overview.md) article in the business process documentation.

## What is procurement?

Procurement refers to the strategic process of obtaining goods, materials, or services from external suppliers. It serves as the foundation for managing the cost, quality, and delivery of resources required by an organization. The process involves several key steps, including identifying the need for a product or service, selecting a vendor, negotiating terms, and making the final payment.

The following image provides a flowchart illustrating the procure to pay business process areas. For a more current overview, go to [Source to pay end-to-end overview](../business-processes/source-to-pay-overview.md).

:::image type="content" source="media/DTV004-p2p-processes.png" alt-text="Image of a flow chart that goes from managing vendor relationships, followed by developing a sourcing strategy, defining a procurement catalogue, setting procurement policies and procedures, procuring material and services, and then receiving those materials and services. The chart then details the payment processes: processing vendor invoices, issuing and settling vendor payments, managing vendor debits and chargebacks, creating and processing promissory notes, processing vendor rebates and incentives, and analyzing vendor performance. Each stage is represented by a simple icon and flows logically from start to finish to describe the procurement cycle comprehensively." lightbox="media/DTV004-p2p-related-processes.png":::

**Procure to Pay (P2P)** is an essential process that documents this entire journey—from identifying the need to making the final payment. It's not just a single function but a collaboration between different departments, such as procurement, accounts payable, and operations. Each has a role in ensuring that purchases are appropriately sourced, approved, and paid for.

## Types of procurement

There are two primary categories of procurement within Dynamics 365: **direct procurement** and **indirect procurement**.

Direct procurement refers to acquiring materials or components that are used directly in the production process. For example, in the automotive industry, components such as engines, steel, and tires are purchased to assemble vehicles. These goods are essential to production and are often managed with significant scrutiny to ensure cost-effectiveness and timely delivery.

Indirect procurement, on the other hand, involves purchasing goods or services that are not directly tied to production. These items include office supplies, IT services, marketing, and utilities. While not integral to the production process, indirect procurement is still vital to support day-to-day operations within an organization.

## The procure to pay process in Dynamics 365

The **Procure to Pay (P2P)** process in Dynamics 365 Supply Chain Management is designed to streamline the purchasing cycle, ensuring efficiency and transparency. It begins with identifying the need for goods or services and follows through several critical steps, including:

- Selecting the vendor

- Creating and approving the purchase order

- Receiving and verifying the goods or services

- Processing and approving the invoice

- Making the final payment

By automating these steps, Dynamics 365 allows businesses to minimize errors, enhance operational efficiency, and build stronger relationships with their vendors.

The following image illustrates how the procure to pay business process relates to other business processes. Learn more at [Source to pay end-to-end overview](../business-processes/source-to-pay-overview.md).  

:::image type="content" source="media/DTV004-p2p-related-processes.png" alt-text="The image depicts a diagram illustrating the connection of the Procure to Pay process to other business processes within an organization. It shows various interconnected circles labeled with different processes." lightbox="media/DTV004-p2p-related-processes.png":::

### Managing vendor relationships

One of the primary responsibilities in the P2P cycle is managing vendor relationships. This involves identifying and selecting vendors, negotiating contracts, and continuously monitoring vendor performance. Dynamics 365 provides tools to help procurement teams maintain positive relationships by integrating vendor collaboration portals for easy communication and performance tracking.

### Developing sourcing strategies

Sourcing strategies within Dynamics 365 involve analyzing data to identify cost-saving opportunities and choosing the most effective sourcing method. Through master planning and trade agreements, businesses can ensure the right sourcing methods are selected based on their needs and market conditions.

## Procurement catalog and policy management

Defining a procurement catalog in Dynamics 365 is a crucial step in standardizing the purchase process. This catalog includes a comprehensive list of goods and services that can be procured, along with associated pricing and availability. By keeping the catalog accurate and up to date, organizations can simplify the purchasing process and maintain control over expenses.

Policies and procedures are equally important, as they define the roles, responsibilities, and compliance requirements for procurement teams. In Dynamics 365, purchasing policies can be configured with approval workflows, ensuring that all acquisitions are properly authorized and align with the company's financial and operational goals.

## The purchase requisition process

A **purchase requisition** is an internal document used to authorize the purchasing department to buy certain items or services. In Dynamics 365, the purchase requisition workflow can be customized to include approval steps for requisition lines or entire documents, depending on the organization's structure.

Once approved, the requisition can be converted into a purchase order, allowing the procurement process to move forward with external vendors. The system allows employees to create requisitions easily, ensuring that necessary purchases can be made without unnecessary delays.

## Request for quotation (RFQ)

A **Request for Quotation (RFQ)** is often used when a company wants to receive competitive bids from multiple vendors for the same product or service. This ensures the best pricing and delivery terms are secured. In Dynamics 365, RFQs can be generated from purchase requisitions, and vendors can respond to the bids through the vendor collaboration portal, streamlining the entire quotation process.

The ability to compare vendor bids and choose the most favorable offer is a powerful feature within Dynamics 365. Once a bid is accepted, it can be automatically transferred into a purchase order, facilitating efficient procurement operations.

## Vendor invoicing and payments

Vendor invoicing is another critical component of the P2P process. Dynamics 365 allows for automation in handling vendor invoices, whether tied to purchase orders or service-based agreements. Invoices can be manually entered or imported through automation technologies such as **Optical Character Recognition (OCR)**, which enables the system to read invoice data without manual input.

Once the invoice is matched with the purchase order and the product receipt, it can be posted for payment. The system supports both two-way and three-way matching, ensuring that only the goods or services ordered and received are paid for.

**Vendor payment processing** in Dynamics 365 is equally streamlined, allowing companies to automate payment proposals, handle prepayments, and schedule payments according to contractual terms. This feature helps maintain good relationships with suppliers by ensuring timely and accurate payments.

## Conclusion

The **Procure to Pay (P2P)** process in Dynamics 365 Supply Chain Management offers a comprehensive, automated solution for managing procurement. By simplifying the procurement process, automating invoice matching, and enabling efficient vendor communication, Dynamics 365 helps businesses optimize cash flow, reduce errors, and improve vendor relationships.

This end-to-end process is integral to the overall efficiency of an organization, tying into other business areas such as production, inventory, and finance. For businesses looking to gain a competitive edge in their procurement processes, Dynamics 365 provides a robust platform to achieve their goals.

For more information on Dynamics 365 Supply Chain Management and its features, visit the [Microsoft Dynamics 365 page](https://dynamics.microsoft.com/).

### Related resources

You can use the following resources to learn more about Dynamics 365.

- [TechTalk: Overview of the source to pay business process in Dynamics 365 Finance and Dynamics 365 Supply Chain Management](dynamics-365-finance-supply-chain-management-source-to-pay.md)  
- [Source to pay end-to-end overview](../business-processes/source-to-pay-overview.md)  
- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)  
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
