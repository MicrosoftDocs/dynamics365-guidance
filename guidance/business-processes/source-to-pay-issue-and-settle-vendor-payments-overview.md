---
title: Issue and settle vendor payments overview
description: Learn about the issue and settle vendor payments business process area, including the issue and settle vendor payments process flow.
author: music727
ms.author: mibeinar
ms.date: 05/28/2024
ms.topic: overview
---

# Issue and settle vendor payments overview

***Applies to: Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management***

This article describes how you can use Dynamics 365 products to support the organization's requirements to issue and settle vendor payments.

## Introduction to issue and settle vendor payments

The *issue and settle vendor payments* business process area focuses on paying vendors according to the agreed-upon payment terms, ensuring that payments are made accurately and on time, and settling them against invoices either manually or through an automated process.

*Issue and settle vendor payments* is an essential step in the *Source to pay* end-to-end business process flow and structured and defined approach to issuing and settling vendor payments is critical to prevent financial risks and payment delays and ensure financial stability within your organization.

The *issue and settle vendor payments* business process area should be defined and incorporated into the overall implementation during the plannings phase. This phase typically occurs at the beginning of a project's lifecycle. It involves establishing project goals, defining project scope, and developing a detailed project plan.

## Stakeholders

Many people across the organization should contribute to the decision-making process and design of the *issue and settle vendor payments* area. The following list provides examples of such stakeholders:

- **Accounts payable clerks** – Responsible for processing accounts and incoming payments in compliance with financial policies and procedures. Accounts payable clerks are also responsible for verifying, classifying, and recording accounts payable data, and for preparing bills, invoices, and bank deposits. They might also be responsible for reconciling the accounts payable ledger to ensure that all bills and payments are accounted for and correctly posted. They might also verify and investigate any discrepancies by reconciling vendor accounts and monthly vendor statements.
- **Finance department** – Responsible for financial supervision, financial reporting, and analysis.
- **Executive leadership** – Responsible for payment oversight, approvals, and alignment with the organization's strategic goals, which helps secure the necessary resources and funding.

## Issue and settle vendor payments process flow

The following diagram illustrates the *issue and settle vendor payments* business process area. [!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/design-to-retire-issue-and-settle-vendor-business-process-area-map.svg" alt-text="Flow diagram with steps for the process that is explained further in the next paragraphs." lightbox="media/design-to-retire-issue-and-settle-vendor-business-process-area-map.svg":::

The *issue and settle vendor payments* process area flow diagram covers the following steps:

- *Start*

- *Source to pay* end-to-end process
    
    Parallel branches to this end-to-end process are the *Design to retire* end-to-end process, *Inventory to Deliver* end-to-end process, and *Concept to market* end-to-end process.

    - *Define policies and procedures for procurement*
    - *Manage vendor relationship*
    - *Procure materials and services*
    - *Process inbound goods*
    - *Process vendor invoices*
    - *Issue and settle vendor payments*

        - *Does cash discount apply?* condition

            - A parallel branch for **Yes** leads to the *Configure and apply cash discounts* subprocess.
            - A parallel branch for **No** leads to the *Is pre-payment?* condition.

        - *Configure and apply cash discounts*
        - *Is pre-payment?* condition

            - A parallel branch for **Yes** leads to the *Generate and post prepayments* subprocess.

                Downstream to this subprocess is a *Record financial transactions* subprocess that connects to the *Record to Report* end-to-end business process.

            - A parallel branch for **No** leads to the *Generate and post payments* subprocess.

                Downstream to this subprocess is a *Record financial transactions* subprocess that connects to a *Record to Report* end-to-end business process.

        - *Generate and post prepayments*
        - *Generate and post payments*
        - *Does promissory notes apply?* condition

            - A parallel branch for **Yes** leads to the *Generate and process promissory notes* subprocess.
            - A parallel branch for **No** leads to the *Settle vendor transactions* condition.

        - *Generate and process promissory notes*
        - *Settle vendor transactions*
        - *Has payment been canceled?* condition

            - A parallel branch for **Yes** leads to the *Cancel a vendor payment* subprocess.
            - A parallel branch for **Yes** leads to *End*.

        - *Cancel a vendor payment*

- *Design to retire* end-to-end process

    - *Introduce new products and services*

        This process connects to the *Procure materials and services* subprocess.

- *Inventory to deliver* end-to-end process

    - *Process inbound goods*
    - *Process vendor invoices*

        Downstream to this subprocess is an *Issue and settle vendor payments* subprocess.

- *Concept to market* end-to-end process

    - *Introduce new services*

        This subprocess connects to a *Procure materials and services* subprocess.

- *End*

## Issue and settle vendor payments benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the issuing and settling of vendor payments. The following sections outline the key benefits that an organization might monitor and measure for this process.

### Automated vendor payment proposal

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

1. *Manage vendor relationships*
1. *Develop sourcing strategies*
1. *Define procurement catalogs*
1. *Define policies and procedures for procurement*
1. *Plan supply*
1. *Procure materials and services*
1. *Process vendor invoices*
1. *Issue and settle vendor payments* (the article that you're currently reading)
1. *Manage vendor debits and chargebacks*
1. *Create and process promissory notes*
1. *Process vendor rebates and incentives*
1. *Analyze vendor performance*

## Related resources

You can use the following resources to learn more about the *issue and settle vendor payments* process in Dynamics 365.

- [Source to Pay Overview in Dynamics 365 Supply Chain Management](https://community.dynamics.com/blogs/post/?postid=f67e343b-ed36-ee11-bdf4-00224827eb85)
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
