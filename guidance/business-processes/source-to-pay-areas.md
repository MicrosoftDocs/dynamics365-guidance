---
title: Overview of the Source to pay business process areas
description: Learn about the source to pay business process area and get introduced to the various functions of the business process.
author: AdiVijayashankar
ms.author: advijaya
ms.topic: concept-article
ms.date: 05/20/2025
---

# Overview of the Source to pay business process areas

***Applies to: Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center***

The *source to pay* process is broken down into multiple business process areas. The following sections further describe the business process areas.

## Develop procurement and sourcing strategies

This business process area involves developing procurement and sourcing strategies by analyzing spend data, selecting suitable procurement and sourcing methods, establishing purchasing guidelines, defining the roles and responsibilities of procurement personnel, ensuring compliance with regulations and internal policies, identifying avenues for cost-saving, and negotiating vendor contracts.

In Dynamics 365, you can configure products to determine the sourcing method for supply forecasting and master planning, as well as set pricing within trade agreements and purchase agreements, manage signing limits, setup approval hierarchies, and configure workflows to streamline the approval process along with procurement policies for multiple rules such as, when a purchase requisition is required, when a request for quotation is required, and when a purchase is considered capitalized with integration for fixed assets, among other functionalities.

Learn more at [Define procurement and sourcing strategy overview](source-to-pay-define-procurement-sourcing-strategy-overview.md).  

## Define procurement catalogs

> [!IMPORTANT]
> This business process area is deprecated. Instead, a new business process, [Define procurement catalogs](source-to-pay-define-procurement-catalogs-overview.md), appears in the [Develop a procurement and sourcing strategy](source-to-pay-define-procurement-sourcing-strategy-overview.md) area.
<!-- The business process area that defines procurement catalogs, empowers organizations to configure internal and external catalogs for use in the source-to-pay process. These catalogs, including items and services, can be organized and added, facilitating their use during the procurement process. Furthermore, categories outlined within the catalogs can be used within purchase requisition and purchase order without necessitating item or service code.

Once configured, these catalogs and their categories can be used to enforce access restrictions, ensuring that designated personnel have appropriate access to specific categories. Access control is administered through purchasing policies in Dynamics 365 Supply Chain Management.

Learn more at [Overview of the define procurement catalogs business process area](source-to-pay-define-procurement-catalogs-overview.md).   -->

## Manage supplier relationships

This business process area involves managing relationships with the prospective and chosen suppliers by identifying and selecting qualified suppliers, and creating and maintaining vendor records with all relevant information. Additionally, this business process area also covers monitoring vendor performance using various metrics and maintaining a positive relationship with vendors. Dynamics 365 Supply Chain Management has a vendor collaboration module that supports a range of business processes for suppliers.

Learn more at [Manage supplier relationships overview](source-to-pay-manage-vendor-relationships-overview.md).  

## Source and contract goods and services

We added this business process area in 2024. It covers the business processes of requesting information, quotes, and proposals from different suppliers, and then evaluating the submitted bids. The business process area also covers budget spend and registering contracts with the chosen suppliers.

## Procure goods and services

This business process area focuses on procuring materials or services and encompasses the necessary steps to initiate a purchase order with external vendors. This includes creating purchase requisitions, request for quotations (RFQ), purchase orders, and purchase agreements. Once purchase orders are created and approved, these can be confirmed and sent to the vendors.

Communication with vendors regarding the purchases can be made either manually, electronically including EDI (Electronic Data Interchange), or using a portal such as the vendor collaboration portal that allows external vendors to participate in the purchasing process. The purchase orders may also originate from other business process areas such as *Project to profit* or *Plan to produce*. Additionally, this business process area also includes the process of returning products to vendors.

Learn more at [Procure goods and services overview](source-to-pay-procure-materials-services-overview.md).  

## Manage accounts payable

This business process area involves processing supplier invoices by verifying invoice accuracy, matching invoices to purchase orders and goods receipts, and reconciling discrepancies in invoices, issuing debit memos, and managing chargebacks in accordance with contractual agreements. It also includes the process of disputing charges from vendors. Dynamics 365 also provides invoice register functionality for quick entry to accrue the expense.

You can also generate a prepayment invoice for advance vendor payment prior to the delivery of goods or services. The invoices can be received and processed manually, through automation, or EDI. For instance, the invoice capture solution in Dynamics 365 Finance is designed to automatically create vendor invoices from digital images via email inbox or manual upload.

Learn more at [Manage accounts payable](source-to-pay-manage-accounts-payable-overview.md).  

> [!NOTE]
> In the first versions of the business process catalog, this business process area had the name *Process vendor invoices overview*. We're in process of updating the article based on the November 2024 version.

## Issue and settle vendor payments

> [!IMPORTANT]
> This business process area is deprecated. Instead, a new business process appears in the *Manage accounts payable* business process area.
<!-- This business process area involves paying vendors according to the agreed-upon payment terms and ensuring that payments are made accurately and on time. This includes applying cash discounts, generating, and posting prepayments and payments, settling vendor transactions, and canceling a vendor payment. Using the invoice payment proposal feature within Dynamics 365, invoices can be settled manually or via automation. It also supports various payment formats including, but not limited to, checks, electronic payments such as ACH, NACHA, Wires, and BAC, and credit cards, among others. The process includes communication with financial institutions and the generation of files or documents to be sent to the vendor via mail or electronically. Additionally, this business process area also supports the creation and processing of promissory notes.

Learn more at [Source to pay end-to-end overview](source-to-pay-overview.md). -->

## Process supplier rebates and incentives

> [!IMPORTANT]
> This business process area is deprecated. Instead, a new business process appears in the *Manage accounts payable* business process area.
<!-- 
This business process area involves managing and tracking rebates and incentives offered by vendors. Key tasks include reviewing rebate agreements, identifying qualifying orders, and generating and approving claims. Efficient handling of vendor rebate enhances profitability and also helps in maintaining strong supplier relationships within supply chain operations. Additionally, this business process area also covers royalty and broker contract management making sure that the organization receives the full benefit of these programs.

Learn more at [Process vendor rebates and incentives overview](source-to-pay-process-vendor-rebates-incentives-overview.md).   -->

## Analyze procurement and sourcing

We added this business process area in 2024. It covers business processes for measuring and analyzing procurement spend and supplier performance. It includes analysis of rebate and incentives, the efficiency of the organization's sourcing processes, and management of risks in the procurement processes.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *source to pay* business processes, learn more at the following resources and steps.

1. [Source to pay - introduction to the end-to-end business process](source-to-pay-introduction.md)
2. [Source to pay end-to-end overview](source-to-pay-overview.md)
3. Learn about the business process catalog at [About the business process catalog for Dynamics 365 apps and services](about.md)  

## Related information

You can use the following resources to learn more about the *source to pay* process in Dynamics 365.

- [Procurement and sourcing overview](/dynamics365/supply-chain/procurement/procurement-sourcing-overview) 

- [Procurement and sourcing home page](/dynamics365/supply-chain/procurement/procurement-sourcing) 

- [Procurement catalogs overview](/dynamics365/supply-chain/procurement/procurement-catalogs)

- [Vendor collaboration with external vendors](/dynamics365/supply-chain/procurement/vendor-collaboration-work-external-vendors)

- [Purchasing policies](/dynamics365/supply-chain/procurement/purchase-policies)

- [Supply risk assessment](/dynamics365/supply-chain/procurement/supply-risk-assessment-overview)

- [Onboard vendors](/dynamics365/supply-chain/procurement/vendor-onboarding)

- [Vendor invoices overview - Finance](/dynamics365/finance/accounts-payable/vendor-invoices-overview)

<!--## Tags

*Stakeholders:* Functional consultant, Buyer, Director of Procurement, Purchasing agent, Purchasing manager, Accounts payable clerk, Accounts payable manager, System administrator, Business Analyst, Director of IT, Business Systems Analyst, Controller, CFO, Accountant, or Accounting manager, Internal auditors, External auditors

*Products:* Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center -->
