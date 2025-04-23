---
title: Manage the accounts payable business process area overview
description: Learn about the Manage the accounts payable business process area, including learning about the types of stakeholders and process flow.
author: meneksesaygili
ms.author: msaygili
ms.topic: conceptual
ms.date: 04/15/2025
---

# Manage the accounts payable overview

***Applies to: Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Intelligent Order Management, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management***

This article describes the *manage the accounts payable* business process area in the *Source to pay* end-to-end process. This process area includes the processes for:

* Setting the vendor invoice matching policies of how invoicing performs and is accounted for.
* Paying vendors according to the agreed-upon payment terms, ensuring that payments are made accurately and on time, and settling them against invoices manually or using an automated process.
* Managing supplier or vendor rebates or other incentives in your supply chain.

## Manage the accounts payable

A **vendor invoice** is generated upon receiving products or services as per a purchase order. It consists of a header and item or service lines, marking the last step in the purchase process. Some invoices might not correspond to purchase orders, like ongoing service bills. There are various methods to enter vendor invoices, including vendor invoice journal, vendor invoice journal for non-purchase order invoices, and vendor invoice register for expense accrual. Additionally, you can create vendor invoices based on confirmed purchase orders using the **Open vendor invoices** and **Pending vendor invoices** pages.

Define and incorporate the *manage the accounts payable* business process area into the overall implementation. The setup and configuration of your products and base pricing along with the general procurement process should be in place before the *manage the accounts payable* process.

## Stakeholders

As policies and procedures are outlined within the procurement area, there's also input from other departments that you must take into consideration. These stakeholders include, but aren't limited to:

* **Procurement and sourcing stakeholders**: Responsible for the creation of purchase requisitions, purchase orders, and purchase order changes.
* **Audit and compliance stakeholders**: These stakeholders ensure the proper approvals and configurations are set to meet internal and external audit requirements.
* **Finance team stakeholders**: Includes Accounts Payable Specialists, Financial Analysts, Controllers, and Chief Financial Officer (CFO). These stakeholders play a crucial role in:
  * designing and configuring the vendor invoices, payments and rebates approval process, defining rebate programs, and analyzing rebate performance,
  * processing purchase ledger and incoming payments in compliance with financial policies and procedures,
  * verifying, classifying, and recording accounts payable data, and
  * preparing bills, invoices, and bank deposits.
  
  The accounts payable clerk may also be responsible for reconciling the accounts payable ledger to ensure that all bills and payments are accounted for and properly posted. They may also verify and investigate discrepancies, if any, by reconciling vendor accounts and monthly vendor statements. Their expertise ensures the financial accuracy and viability of the incentive programs.

* **Sales and procurement stakeholders**: Includes Sales Representatives, Procurement Managers, and Category Managers. These stakeholders are essential in configuring rebate eligibility and generating vendor rebates. Their input is vital for aligning incentive programs with sales targets and procurement strategies.
* **Supply chain management stakeholders**: Includes Supply Chain Managers, Inventory Planners, and Logistics Coordinators. These stakeholders contribute to the configuration of vendor rebate approval processes, ensuring alignment with supply chain operations and optimizing the logistics of rebate-related transactions.
* **Executive leadership stakeholders**: Includes Chief Executive Officer (CEO), Chief Operating Officer (COO), and the Chief Financial Officer (CFO). Executive leaders are engaged in high-level decision-making and approval processes, providing strategic direction and oversight to ensure that vendor payments, rebate and incentive programs align with organizational goals and objectives.

## Process flow

The following diagram illustrates the *manage the accounts payable* business process area. This flowchart provides a clear visual representation of the complex processes involved in managing accounts payable, which is crucial for maintaining accurate financial records and ensuring timely payments within an organization.

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media\manage-accounts-payable-process-flow.svg" alt-text="Diagram of the process vendor invoices process flow, showing the connections within the business process area." lightbox="media\manage-accounts-payable-process-flow.svg":::

1. Start
   1. A parallel branch from 1. Start includes the *Design to retire* end-to-end process.
      1. Introducing business process area
      2. *Process goods and services* business process area
         * *Manage accounts payable* business process
      3. *Process inbound goods* business process area
         * *Manage accounts payable* business process
   2. A parallel branch from 1. Start includes the *Inventory to deliver* end-to-end process.
      1. *Process inbound goods* business process area
         * *Manage accounts payable* business process
2. *Manage accounts payable* end-to-end process
   1. Decision on prepayment:
      1. The process starts with a decision point: "is prepayment required?"
         * If yes, proceed to step 7.
         * If no, proceed to step 3.
   2. A parallel branch from step 2 for *Process vendor rebates and incentives*
3. Processing supplier invoices
   1. Enter the invoice details into the system.
   2. Verify the invoice against purchase orders and delivery receipts.
   3. Post the invoice for payment.
   4. Proceed to step 4.
   5. A parallel branch for *Record financial transactions*
      * Step: record financial transactions
         1. Action: update the general ledger with the payment details.
         2. Action: generate financial reports for review.
4. Disputing invoices
   1. Decision on disputing invoices:
      * The process starts with a decision point: "Dispute required?"
      * If yes,
         1. Identify discrepancies in the invoice.
         2. Communicate with the supplier to resolve the dispute.
         3. Adjust the invoice amount if needed.
         4. Proceed to step 5.
      * If no, proceed to step 7.
5. Receive supplier credits
   1. Proceed to step 6.
   2. A parallel branch for *Record financial transactions*
      * Step: record financial transactions.
         1. Action: update the general ledger with the payment details.
         2. Action: generate financial reports for review.
6. Cancel supplier payments
   1. Decision on cancellation of payment
      1. The process starts with a decision point: "Cancel required?"
         * If yes, cancel supplier payments
         * If no, proceed to step 11.
   2. A parallel branch for *Record financial transactions*
      * Step: record financial transactions.
         1. Action: update the general ledger with the payment details.
         2. Action: generate financial reports for review.
7. Issue and settle supplier payments
   1. Issue payments
   2. Settle supplier transactions
   3. Proceed to step 8.
   4. A parallel branch for *Record financial transactions*
      * Step: record financial transactions.
         1. Action: update the general ledger with the payment details.
         2. Action: generate financial reports for review.
8. Managing promissory notes
   1. Decision on promissory notes
      1. The process starts with a decision point: "Promissory note required?"
         * If yes,
            1. Summarize the total amount payable to each supplier.
            2. Proceed to step 9.
         * If no, proceed to step 9.
   2. A parallel branch for *Record financial transactions*
      * Step: record financial transactions.
         1. Action: update the general ledger with the payment details.
         2. Action: generate financial reports for review.
9. Correct supplier payments
   1. Decision on correction of payments
       1. The process starts with a decision point: " Payment correction required?"
           * If yes, proceed to step 6.
           * If no, proceed to step 10.
   2. A parallel branch for *Record financial transactions*
      * Step: record financial transactions.
         1. Action: update the general ledger with the payment details.
         2. Action: generate financial reports for review.
10. Process supplier rebates and incentives
11. End

## Benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the manage accounts payable. The following sections outline the key benefits that an organization might monitor and measure for *manage accounts payable*.

### Efficiency

The system enhances efficiency by validating vendor invoicing. It can match product receipts to invoice lines that have a three-way matching policy and prevalidate through simulated posting. This helps reduce the errors and inefficiencies that can occur when information is manually entered and processed.

### Visibility

The system provides an enhanced experience for viewing workflow and reaching the historical information for vendor invoices. This visibility can help Accounts payable clerks and managers process vendor invoices more efficiently.

### Control

When the organization manages their accounts payable, they gain direct control over each step of the process. Such control can be beneficial for businesses that require a high level of oversight or have specific procedures to follow.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *manage accounts payable* business processes, you can use the following resources and steps to learn more.

1. [Develop procurement and sourcing strategy](source-to-pay-define-procurement-sourcing-strategy-overview.md)
2. [Manage supplier relationships](source-to-pay-manage-vendor-relationships-overview.md)
3. Source and contract goods and services
4. [Procure goods and services](source-to-pay-procure-materials-services-overview.md)
5. Manage accounts payable &larr; You are on this step
6. Analyze procurement and sourcing

## Related information

You can use the following resources to learn more about the *manage account payable* process in Dynamics 365.

* Documentation
  * [Vendor invoices overview - Finance](/dynamics365/finance/accounts-payable/vendor-invoices-overview#vendor-invoices)
  * [Automated vendor invoicing processes overview - Finance](/dynamics365/finance/accounts-payable/auto-vendr-invc-process#match-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy)
  * [Procure to Pay Overview in Dynamics 365 Supply Chain Management | August 2, 2023](https://community.dynamics.com/blogs/post/?postid=f67e343b-ed36-ee11-bdf4-00224827eb85)
  * [Vendor payment overview - Finance](/dynamics365/finance/cash-bank-management/tasks/vendor-payment-overview)
  * [Vendor payments workspace](/dynamics365/finance/accounts-payable/vendor-payments-workspace)
  * [Automate vendor payment proposals - Finance](/dynamics365/finance/accounts-payable/automate-vendor-payment-proposal)
  * [Settlement overview - Finance](/dynamics365/finance/cash-bank-management/settlement-overview)
  * [Vendor payments for a partial amount - Finance](/dynamics365/finance/accounts-payable/vendor-payments-partial-amount)
  * [Centralized payments for Accounts payable - Finance](/dynamics365/finance/accounts-payable/centralized-payments-accounts-payable)
  * [File formats for methods of payment - Finance](/dynamics365/finance/localizations/europe/emea-select-file-formats-for-the-method-of-payments)
  * [Prepayment invoices vs. prepayments - Finance](/dynamics365/finance/accounts-payable/prepayments-invoices-vs-prepayments)
  * [Vendor rebates - Supply Chain Management](/dynamics365/supply-chain/procurement/vendor-rebates)
  * [Rebate management module overview - Supply Chain Management](/dynamics365/supply-chain/rebate-management/rebate-management-overview)

* Learn courses links
  * [Process purchase order invoices in Dynamics 365 Finance - Training](/training/modules/purchase-order-invoices-finance/)
  * [Configure Accounts payable in Dynamics 365 Finance - Training](/training/modules/configure-accounts-payable-dyn365-finance/)
  * [Configure and use agreements in Dynamics 365 Supply Chain Management - Training](/training/modules/configure-use-agreements-dyn365-supply-chain-mgmt/)

* Find definitions of terminology used in content for *manage account payable* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article, including the following terms:
  * [Centralized payments](glossary.md#centralized-payments)
  * [Eligibility criteria](glossary.md#eligibility-criteria)
  * [Incentive programs](glossary.md#incentive-programs)
  * [Methods of payment](glossary.md#methods-of-payment)
  * [Payment proposal](glossary.md#payment-proposal)
  * [Prepayment](glossary.md#prepayment)
  * [Promissory note](glossary.md#promissory-note)
  * [Rebate](glossary.md#rebate)
  * [Rebate accruals](glossary.md#rebate-accruals)
  * [Rebate agreement](glossary.md#rebate-agreement)
  * [Rebate claim](glossary.md#rebate-claim)
  * [Rebate generation](glossary.md#rebate-generation)
  * [Rebate processing](glossary.md#rebate-processing)
  * [Reconciliation](glossary.md#reconciliation)
  * [Settlement](glossary.md#settlement)
  * [Terms of payment](glossary.md#terms-of-payment)
  * [Three-way matching](glossary.md#three-way-matching)
  * [Two-way matching](glossary.md#two-way-matching)

<!--## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Accounts payable, Administrative, Audit, Engineering, Finance, IT, Merchandising, Operations, Production, Project Management, Purchasing, Retail store operations, Service operations, Transportation, Treasury, Warehouse

*Products:* Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

* [Menekse Saygili](https://www.linkedin.com/in/fmsaygili) \| Senior Program Manager

Other contributors:

* [Veselina Eneva](https://www.linkedin.com/in/veselina-eneva-77744817/) \| FastTrack Solution Architect
* [Rachel Profitt](https://www.linkedin.com/in/RachelProfitt/) \| Principal Program Manager
* [Purvesh Vaghasia](https://www.linkedin.com/in/purveshvaghasia/) \| Senior Solution Architect
* [Milda Beinaryte](https://www.linkedin.com/in/beimilda/) \| FastTrack Solution Architect
