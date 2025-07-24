---
title: Issue and settle supplier payments
description: Learn about the issue and settle supplier payments business process area, including the process flow.
author: music727
ms.author: mibeinar
ms.date: 05/21/2025
ms.topic: overview
---

# Issue and settle supplier payments

***Applies to: Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management***

This article describes how you can use Dynamics 365 products to support the organization's requirements to issue and settle payments to your suppliers.  

> [!NOTE]
> In the first versions of the business process catalog, this article represented a business process area, but it is now a business process under *Manage accounts payable*. We're in process of updating the article based on the November 2024 version.

## Introduction to issue and settle supplier payments

The *issue and settle vendor payments* business process focuses on paying vendors according to the agreed-upon payment terms, ensuring that payments are made accurately and on time, and settling them against invoices either manually or through an automated process.

*Issue and settle vendor payments* is an essential step in the *Source to pay* end-to-end business process flow and structured and defined approach to issuing and settling vendor payments is critical to prevent financial risks and payment delays and ensure financial stability within your organization.

Several steps must be completed to prepare Dynamics 365 solution for successful issue and settlement vendor payments processing. This includes but isn't limited to configuration of cash discount and term of payment.

The *issue and settle vendor payments* business process should be defined and incorporated into the overall implementation during the plannings phase. This phase typically occurs at the beginning of a project's lifecycle. It involves establishing project goals, defining project scope, and developing a detailed project plan.

## Stakeholders

Many people across the organization should contribute to the decision-making process and design of the *issue and settle vendor payments* business process. The following list provides examples of such stakeholders:

- **Accounts payable clerks** – Responsible for processing accounts and incoming payments in compliance with financial policies and procedures. Accounts payable clerks are also responsible for verifying, classifying, and recording accounts payable data, and for preparing bills, invoices, and bank deposits. They might also be responsible for reconciling the accounts payable ledger to ensure that all bills and payments are accounted for and correctly posted. They might also verify and investigate any discrepancies by reconciling vendor accounts and monthly vendor statements.
- **Finance department** – Responsible for financial supervision, financial reporting, and analysis.
- **Executive leadership** – Responsible for payment oversight, approvals, and alignment with the organization's strategic goals, which helps secure the necessary resources and funding.

## Issue and settle supplier payments process flow

The following diagram illustrates the *issue and settle supplier payments* business process.

:::image type="content" source="media/source-to-pay-issue-settle-supplier-payments.svg" alt-text="Flow diagram with steps for the process." lightbox="media/source-to-pay-issue-settle-supplier-payments.svg":::

The *issue and settle supplier payments* process area flow diagram covers the following steps:

1. Start
2. Identify Payment Needs
3. Prepare Payment
4. Review Payment
5. Approve Payment?
   - No: Revise Payment
   - Yes: Issue Payment
6. End

## Issue and settle supplier payments benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the issuing and settling of vendor payments. The following sections outline the key benefits that an organization might monitor and measure for this process.

### Automated supplier payment proposal

In Dynamics 365 Finance, you can use vendor payment proposals to settle invoices either manually or through an automated process. Organizations that pay vendors on a recurring schedule can automate the process of generating vendor payment proposals by specifying criteria and a scheduled time.

Learn more at [Automate vendor payment proposals](/dynamics365/finance/accounts-payable/automate-vendor-payment-proposal).

### Various payment formats

Dynamics 365 supports various payment formats, including checks, electronic payments such as ACH, NACHA, Wires, and BAC, credit cards, and more. The process also covers communication with financial institutions and the generation of files or documents that are sent to the vendor either through the mail or electronically.

Learn more in the following articles in the documentation for Dynamics 365 Finance:

- [Electronic reporting sample vendor checks](/dynamics365/finance/accounts-payable/electronic-reporting-sample-vendor-checks)
- [Create and export vendor payments using ISO20022 payment format](/dynamics365/finance/localizations/europe/create-export-vendor-payments-iso20022-payment-format)
- [File formats for methods of payment](/dynamics365/finance/localizations/europe/emea-select-file-formats-for-the-method-of-payments)

### Centralized payments

Organizations that include multiple companies can create and manage payments by using a single company that handles all payments. This approach provides better visibility into the payment process, because payment clerks can view invoices across companies. In addition, a dedicated payment workspace provides better visibility into overdue invoices and gives an easy way to keep track of invoices and payments across organization.

Learn more at [Centralized payments for Accounts payable](/dynamics365/finance/accounts-payable/centralized-payments-accounts-payable).

### Efficient settlement process

In Dynamics 365, you can settle transactions between different document types, such as invoices, payments, credit memos, and fees. The settlement process can also generate new transactions, which can help streamline the payment process.

Learn more at [Settlement overview](/dynamics365/finance/cash-bank-management/settlement-overview).

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *issue and settle vendor payments* business processes, use the following resources and steps to learn more. (Links are added when articles are ready.)

1. [*Develop procurement and sourcing strategy*](source-to-pay-define-procurement-sourcing-strategy-overview.md)
1. [*Manage supplier relationships*](source-to-pay-manage-vendor-relationships-overview.md)
1. *Source and contract goods and services*
1. [*Procure goods and services*](source-to-pay-procure-materials-services-overview.md)
1. [*Manage accounts payable*](source-to-pay-manage-accounts-payable-overview.md)  

    1. *Process supplier invoices*  
    1. *Dispute invoices*  
    1. *Receive supplier credits*  
    1. *Issue and settle supplier payments* (The article you're currently reading)  
    1. *Manage promissory notes*  
    1. *Cancel supplier payments*  
    1. *Correct supplier payments*  
    1. [*Process supplier rebates and incentives*](source-to-pay-process-vendor-rebates-incentives-overview.md)  
1. *Analyze procurement and sourcing*

## Related information

You can use the following resources to learn more about the *issue and settle supplier payments* process in Dynamics 365.

- [Source to Pay Overview in Dynamics 365 Supply Chain Management blog post](https://community.dynamics.com/blogs/post/?postid=f67e343b-ed36-ee11-bdf4-00224827eb85)
- [Vendor payment overview](/dynamics365/finance/cash-bank-management/tasks/vendor-payment-overview)
- [Vendor payments workspace](/dynamics365/finance/accounts-payable/vendor-payments-workspace)
- [Automate vendor payment proposals](/dynamics365/finance/accounts-payable/automate-vendor-payment-proposal)
- [Settlement overview](/dynamics365/finance/cash-bank-management/settlement-overview)
- [Vendor payments for a partial amount](/dynamics365/finance/accounts-payable/vendor-payments-partial-amount)
- [Centralized payments for Accounts payable](/dynamics365/finance/accounts-payable/centralized-payments-accounts-payable)
- [File formats for methods of payment](/dynamics365/finance/localizations/europe/emea-select-file-formats-for-the-method-of-payments)
- [Prepayment invoices vs. prepayments](/dynamics365/finance/accounts-payable/prepayments-invoices-vs-prepayments)

<!---## Tags

*Stakeholders:* Accounts receivable, Audit, Finance, Purchasing

*Products:* Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management --->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Milda Beinaryte](https://www.linkedin.com/in/beimilda/) \| FastTrack Solution Architect
