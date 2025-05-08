---
title: Overview of the source to pay business process in Dynamics 365 Finance and Supply Chain Management
description: Find a TechTalk that described how Dynamics 365 Finance and Dynamics 365 Supply Chain Management support the source-to-pay business process.
ms.date: 11/04/2024
ms.topic: concept-article
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Overview of the source to pay business process in Dynamics 365 Finance and Dynamics 365 Supply Chain Management

The *source to pay* process is a critical aspect of modern enterprise resource planning (ERP), such as Dynamics 365 Finance and Supply Chain Management. This process encompasses the entire journey of acquiring goods or services—from identifying needs to final payment. An updated approach to this process, known as *source to pay*, provides a comprehensive end-to-end business process that is more aligned with the broader scope of organizational operations, compared to the traditional *procure to pay* framework.

We based this article on [a TechTalk](https://youtu.be/Zx_GLduLEjQ?si=oAk6BHtGfc1-aHOR) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/TechTalk-source2pay.png" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/Zx_GLduLEjQ?si=oAk6BHtGfc1-aHOR":::

The following image illustrates a circular flow diagram with eight icons that represent the different stages of a supply chain process.

:::image type="content" source="media/TechTalk-source2pay-flow.png" alt-text="The icons represent payment processing, demand determination, source determination, supplier selection, purchase order processing, order monitoring, goods receipt, and invoice verification." lightbox="media/TechTalk-source2pay-flow.png":::

## Understanding source to pay

*Source to pay* refers to the full cycle of procurement activities. You start by sourcing and selecting vendors. Then you purchase goods or services and finally complete the payment. This process ensures that all transactions are accurately recorded, goods or services are received as expected, and payments are made in accordance with agreed terms.

Sourcing is the initial phase of this process, where vendors are identified, evaluated, and selected based on criteria such as cost, quality, and availability. Effective sourcing is crucial because it directly impacts the quality of the products or services acquired and the overall efficiency of the supply chain. Procurement, in contrast, refers to the broader process that includes sourcing but also encompasses the entire acquisition cycle—right from identifying the need for goods or services to the payment of invoices.

Learn more about procurement and sourcing in Dynamics 365 and how important the *source to pay* process is to supply chain management at [Procurement and sourcing overview](/dynamics365/supply-chain/procurement/procurement-sourcing-overview).

## Procurement types and benefits

There are two main types of procurement: *direct* and *indirect*. *Direct procurement* involves purchasing materials or goods that are directly used in the production process or are sold to customers. Examples include raw materials, machinery, and components essential for manufacturing. *Indirect procurement* refers to the acquisition of goods or services that support the organization's operations but aren't directly part of the production process, such as office supplies, maintenance services, and IT equipment.

Integrating technology solutions like Dynamics 365 into the *source to pay* process offers several benefits, including increased efficiency through automation, improved accuracy by reducing human errors, enhanced visibility with real-time tracking, better supplier relationships through faster and more accurate communication, and significant cost savings. These improvements collectively lead to better compliance with procurement policies and scalability as the business grows.

Learn more about the specific advantages of automating procurement with Dynamics 365 at [overview of the benefits](https://dynamics.microsoft.com/finance-and-operations/capabilities/procurement-and-sourcing/).

## Key stakeholders and their roles

The successful implementation and management of the *source to pay* process involve collaboration among various stakeholders across the organization. Procurement teams, including buyers and procurement managers, play a central role in sourcing and purchasing activities. The accounts payable team handles the financial aspects, ensuring that payments are processed accurately and on time. IT departments manage the technological infrastructure that supports the *source to pay* process, while finance teams oversee the financial implications and ensure compliance with organizational policies. Additionally, vendors are external stakeholders who supply goods and services and interact with the system for purchase orders and invoice submissions.

<!-- Find a detailed description of the roles and responsibilities that are involved in procurement and sourcing in Dynamics 365 at [guide on organizational roles](/dynamics365/supply-chain/procurement/procurement-organizational-roles) in procurement. -->

## Business process areas in source to pay

The *source to pay* process is divided into several key business process areas. Get a general overview at [Source to pay end-to-end overview](..//business-processes/source-to-pay-overview.md) where we also have the following flow diagram:

:::image type="content" source="../business-processes/media/source-to-pay-flow.svg" alt-text="Diagram of the source to pay business process area map, showing the connections between various business processes." lightbox="../business-processes/media/source-to-pay-flow.svg":::

### Procurement and sourcing strategy

Defining a procurement and sourcing strategy is a critical initial step in the *source to pay* process. This strategy involves analyzing spend data, identifying cost-saving opportunities, selecting appropriate sourcing methods, and ensuring compliance with regulatory requirements. It also includes negotiating contracts with vendors and establishing pricing agreements.

Learn more in the [documentation on procurement and sourcing in Supply Chain Management](/dynamics365/supply-chain/procurement/procurement-sourcing-overview).

### Procurement catalogs

Procurement catalogs are essential for standardizing the procurement process. These catalogs define the list of goods and services that can be purchased within the organization, along with pricing and availability information. Dynamics 365 allows for the creation of both internal and external catalogs, which can be configured to control access based on the purchasing policies.

Learn more in the [documentation on procurement catalogs in Supply Chain Management](/dynamics365/supply-chain/procurement/procurement-catalogs).

### Vendor relationship management

Managing vendor relationships effectively is vital for maintaining a smooth supply chain. This involves selecting qualified vendors, negotiating contracts, monitoring performance, and maintaining positive interactions. Dynamics 365 provides tools to create and manage vendor accounts, track transactions, and evaluate vendor performance over time.

Learn more in the [documentation on vendors in Supply Chain Management](/dynamics365/supply-chain/procurement/set-up-maintain-vendor-collaboration).

### Procurement of materials and services

This area focuses on the actual purchasing activities within the *source to pay* process. It includes creating purchase requisitions, requests for quotations, purchase orders, and agreements. The system facilitates communication with vendors, whether manually or electronically, and ensures that procurement activities align with organizational needs and policies.

Learn more in the [documentation on purchase requisitions in Supply Chain Management](/dynamics365/supply-chain/procurement/purchase-requisitions-overview).

### Vendor invoice processing

Processing vendor invoices is a crucial step in the *source to pay* process. It involves verifying the accuracy of invoices, matching them with purchase orders and goods receipts, and performing the necessary approvals before payment. Dynamics 365 supports both manual and automated invoice processing. This way, you reduce the risk of errors and ensuring that all invoices are processed efficiently.

Learn more in the [documentation on vendor invoices in Finance](/dynamics365/finance/accounts-payable/vendor-invoices-overview?context=%2Fdynamics365%2Fcontext%2Fsupply-chain).

### Vendor payment and settlement

Once invoices are processed, the next step is to manage vendor payments. This involves ensuring that payments are made accurately and on time, according to the agreed-upon terms. Dynamics 365 provides tools for generating payment proposals, applying cash discounts, and settling payments against invoices. The system also supports various payment methods, including checks, electronic funds transfer, and credit cards.

Learn more in the [documentation on vendor invoice policies in Finance](/dynamics365/finance/accounts-receivable/tasks/set-up-vendor-invoice-policies).

### Vendor rebates and incentives

Vendor rebates and incentives play a crucial role in managing financial relationships with suppliers. These programs are structured agreements that offer incentives based on specific criteria, such as volume-based discounts or promotional offerings. Dynamics 365 allows organizations to define, manage, and process vendor rebates efficiently, ensuring that all claims are accurately recorded and settled.

Learn more in the [documentation on vendor rebates in Supply Chain Management](/dynamics365/supply-chain/procurement/vendor-rebates).

## Conclusion

The *source to pay* process in Dynamics 365 Finance and Supply Chain Management offers a comprehensive approach to managing procurement activities, from sourcing to payment. By integrating technology solutions into this process, organizations can achieve significant improvements in efficiency, accuracy, and visibility, leading to better supplier relationships, cost savings, and enhanced compliance. Effective management of the *source to pay* process is essential for maintaining a smooth and efficient supply chain, ensuring that the organization can meet its operational objectives and achieve its strategic goals.

For more comprehensive information and resources, Microsoft's [official Dynamics 365 page](https://dynamics.microsoft.com/) is a valuable resource.

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [Help organizations manage the source to pay business processes](../business-processes/source-to-pay-introduction.md)
- [Source to pay end-to-end overview](../business-processes/source-to-pay-overview.md)
- [Source to pay business process areas](../business-processes/source-to-pay-areas.md)
- [Review and accept changes to confirmed purchase orders - Supply Chain Management](/dynamics365/supply-chain/procurement/purchase-order-changes-after-confirmation)
- [Get started with Invoice Capture for Dynamics 365 Finance \| December 12 & 14, 2022](https://community.dynamics.com/blogs/post/?postid=c07e4d10-30f5-42ea-b297-e2b314ea1788)
- [Punch Out \| September 21, 2017 (dynamics.com)](https://community.dynamics.com/blogs/post/?postid=18e84290-87cc-448e-9c46-664a2e48abdd)
- [Procurement and sourcing home page - Supply Chain Management](/dynamics365/supply-chain/procurement/procurement-sourcing)
- [Accounts payable home page - Finance](/dynamics365/finance/accounts-payable/accounts-payable)
- [(973) Viva Engage : Dynamics 365 and Power Platform Preview Programs : D365 Procurement and Sourcing : Conversations (yammer.com)](https://www.yammer.com/dynamicsaxfeedbackprograms/?show_login=true#/threads/inGroup?type=in_group&feedId=69010219008&view=all)
- [(973) Viva Engage : Dynamics 365 and Power Platform Preview Programs : Invoice Capture for Dynamics 365 Finance : New Conversations (yammer.com)](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=84296204288)
- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
