---
title: Source to pay business process areas
description: Learn about the source to pay business process area and get introduced to the various functions of the business process.
author: AdiVijayashankar
ms.author: advijaya
ms.topic: conceptual
ms.date: 03/20/2024
---

# Source to pay business process areas

***Applies to: Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center***

The *source to pay* process is broken down into multiple business process areas. The following sections further describe the business process areas.

## Develop procurement and sourcing strategies

This business process area involves developing procurement and sourcing strategies by analyzing spend data, selecting suitable procurement and sourcing methods, establishing purchasing guidelines, defining the roles and responsibilities of procurement personnel, ensuring compliance with regulations and internal policies, identifying avenues for cost-saving, and negotiating vendor contracts.

In Dynamics 365, you can configure products to determine the sourcing method for supply forecasting and master planning, as well as set pricing within trade agreements and purchase agreements, manage signing limits, setup approval hierarchies, and configure workflows to streamline the approval process along with procurement policies for multiple rules such as, when a purchase requisition is required, when a request for quotation is required, and when a purchase is considered capitalized with integration for fixed assets, among other functionalities.

## Define procurement catalogs

The business process area that defines procurement catalogs, empowers organizations to configure internal and external catalogs for use in the source-to-pay process. These catalogs, including items and services, can be organized and added, facilitating their use during the procurement process. Furthermore, categories outlined within the catalogs can be used within purchase requisition and purchase order without necessitating item or service code.

Once configured, these catalogs and their categories can be used to enforce access restrictions, ensuring that designated personnel have appropriate access to specific categories. Access control is administered through purchasing policies within Dynamics 365 Supply Chain Management.

## Manage vendor relationships

This business process area involves managing vendor relationships by identifying and selecting qualified vendors, approving suitable vendors, and creating and maintaining vendor records with all relevant information. Additionally, this business process area also covers monitoring vendor performance using various metrics and maintaining a positive relationship with vendors. Dynamics 365 Supply Chain Management has a vendor collaboration module, which facilitates vendors to execute a range of business processes from various workspaces.

## Procure materials and services

This business process area focuses on procuring materials or services and encompasses the necessary steps to initiate a purchase order with external vendors. This includes creating purchase requisitions, request for quotations (RFQ), purchase orders, and purchase agreements. Once purchase orders are created and approved, these can be confirmed and sent to the vendors.

Communication with vendors regarding the purchases can be made either manually, electronically including EDI (Electronic Data Interchange), or using a portal such as the vendor collaboration portal that allows external vendors to participate in the purchasing process. The purchase orders may also originate from other business process areas such as *Project to profit* or *Plan to produce*. Additionally, this business process area also includes the process of returning products to vendors.

## Process vendor invoices

This business process area involves processing vendor invoices by verifying invoice accuracy, matching, matching invoices to purchase orders and goods receipts, and performing two-way or three-way matching, reconciling discrepancies in invoices, issuing debit memos, and managing chargebacks in accordance with contractual agreements. It also includes the process of disputing charges from vendors. Dynamics 365 also provides invoice register functionality for quick entry to accrue the expense.

You can also generate a prepayment invoice for advance vendor payment prior to the delivery of goods or services. The invoices can be received and processed manually, through automation, or EDI. For instance, the invoice capture solution in Dynamics 365 Finance is designed to automatically create vendor invoices from digital images via email inbox or manual upload.

## Issue and settle vendor payments

This business process area involves paying vendors according to the agreed-upon payment terms and ensuring that payments are made accurately and on time. This includes applying cash discounts, generating, and posting prepayments and payments, settling vendor transactions, and canceling a vendor payment. Using the invoice payment proposal feature within Dynamics 365, invoices can be settled manually or via automation. It also supports various payment formats including, but not limited to, checks, electronic payments such as ACH, NACHA, Wires, and BAC, and credit cards, among others. The process includes communication with financial institutions and the generation of files or documents to be sent to the vendor via mail or electronically. Additionally, this business process area also supports the creation and processing of promissory notes.

Learn more at [Source to pay end-to-end overview](source-to-pay-overview.md).

## Process vendor rebates and incentives

This business process area involves managing and tracking rebates and incentives offered by vendors. Key tasks include reviewing rebate agreements, identifying qualifying orders, and generating and approving claims. Efficient handling of vendor rebate enhances profitability and also helps in maintaining strong supplier relationships within supply chain operations. Additionally, this business process area also covers royalty and broker contract management making sure that the organization receives the full benefit of these programs.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *source to pay* business processes, learn more at the following resources and steps. (Links are added, when the articles are ready.)

1. [Source to pay - introduction to the end-to-end business process](source-to-pay-introduction.md)

2. [Source to pay end-to-end overview](source-to-pay-overview.md)

3. *Define procurement and sourcing strategies*

4. [Define procurement catalogs overview](source-to-pay-define-procurement-catalogs-overview.md)

5. [Manage vendor relationships overview](source-to-pay-manage-vendor-relationships-overview.md)

6. [Procure materials and services overview](source-to-pay-procure-materials-services-overview.md)

7. [Process vendor invoices overview](source-to-pay-process-vendor-invoices-overview.md)

8. [Issue and settle vendor payments overview](source-to-pay-issue-and-settle-vendor-payments-overview.md)

9. [Process vendor rebates and incentives overview](source-to-pay-process-vendor-rebates-incentives-overview.md)

## Related resources

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
