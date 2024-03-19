---
title: Process vendor invoices overview
description: Learn about the process vendor invoices business process, including learning about the types of stakeholders and process flow.
author: meneksesaygili
ms.author: msaygili
ms.topic: conceptual
ms.date: 03/18/2024
---

# Process vendor invoices overview

***Applies to: Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Intelligent Order Management, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management<!--, Microsoft Supply Chain Center-->***

This article describes the *process vendor invoices* business process area within the *Procure to pay* end to end process. This process area includes the processes for setting the vendor invoice matching policies of how invoicing performs and is accounted for.

A **vendor invoice** is generated upon receiving products or services as per a purchase order. It consists of a header and item or service lines, marking the last step in the purchase process. Some invoices may not correspond to purchase orders, like ongoing service bills. There are various methods to enter vendor invoices, including, vendor invoice approval journal, vendor invoice journal for non-purchase order invoices, and using the vendor invoice pool for expense accrual.

Additionally, you can create vendor invoices based on confirmed purchase orders using the Open vendor invoices and Pending vendor invoices pages.

The *vendor invoices* business process area should be defined and incorporated into the overall implementation. This phase typically occurs at the beginning of a project's lifecycle and involves establishing project goals, defining project scope, and developing a detailed project plan. The setup and configuration of your products and base pricing along with the general procurement process should be in place before the vendor invoice process.

## Stakeholders

As policies and procedures are outlined within the procurement area, there is also input from other departments that needs to be taken into consideration. These stakeholders include, but aren't limited to:

- **Procurement and sourcing stakeholders**: responsible for the creation of purchase requisitions, purchase orders, and purchase order changes.

- **Finance stakeholders**: The finance stakeholders are involved in ensuring any budgetary considerations are needed and assisting with the approval hierarchy (both personnel and monetary limits) for purchases and invoices.

- **Accounts payable stakeholders**: responsible for invoice generation and matching.

- **Audit and compliance stakeholders**: these stakeholders ensure the proper approvals and configurations are set to meet internal and external audit requirements.

## Process vendor invoices process flow 

The following diagram illustrates the *process vendor invoices business* process area.

:::image type="content" source="media\procure-to-pay-process-vendor-invoices-overview.svg" alt-text="Diagram of the process vendor invoices process flow, showing the connections within the business process area." lightbox="media\procure-to-pay-process-vendor-invoices-overview.svg":::

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

- Start

    - A parallel branch from 1. Start includes the *Product and service lifecycle management* end to end process

        - *Introduce new products and services* business process area

        - *Process materials and services* business process area

            - *Process vendor invoices* business process

        - *Process inbound goods* business process area

            - *Receive invoices* business process

    - A parallel branch from 1. Start includes the *Inventory to delivery* end to end process

        - *Process inbound goods* business process area

            - *Receive invoices* business process

- *Procure to pay* end to end process

- Check if there's any *pre-payment* business process

    - **If yes**, generate a *pre-payment invoices* business process

    - **If no**, *process inbound goods* business process area

- *Receive invoices* business process

- *Record invoice details* business process

- *Review and approve invoices* business process

- Check if the invoice is approved

    - **If yes**, *post invoices* business process

        - *Record financial transactions* business process area

    - **If no**, check *record invoice details* business process

- *Analyze invoice policy violations* business process

- End

## Process vendor invoices benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the process vendor invoices. The following sections outline the key benefits that an organization might monitor and measure for Process vendor invoices.

### Efficiency

The system enhances efficiency by validating vendor invoicing. It can match product receipts to invoice lines that have a three-way matching policy and pre-validate through simulated posting. This helps reduce the errors and inefficiencies that can occur when information is manually entered and processed.

### Visibility

The system provides an enhanced experience for viewing workflow and reaching the historical information for vendor invoices. This visibility can help Accounts payable clerks and managers process vendor invoices more efficiently.

### Control

Processing vendor invoices gives users direct control over each step of the process, which can be beneficial for businesses that require a high level of oversight or have specific procedures that must be followed.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your process vendor invoices business processes, you can use the following resources and steps to learn more. (Links are added later, when the articles are ready.)

1. [Manage vendor relationships](procure-to-pay-manage-vendor-relationships-overview.md)

2. *Develop a sourcing strategy*

3. [Define a procurement catalog](procure-to-pay-define-procurement-catalogs-overview.md)

4. *Define policies and procedures for procurement*

5. *Procure materials and services*

6. *Receive materials and services*

7. *Process vendor invoices* (the article that you're reading)

8. [Issue and settle vendor payments](procure-to-pay-issue-and-settle-vendor-payments-overview.md)  

9. *Manage vendor debits and chargebacks*

10. *Create and process promissory notes*

11. [Process vendor rebates and incentives](procure-to-pay-process-vendor-rebates-incentives-overview.md)

12. *Analyze vendor performance*

<!-- Orignal list from contributor
- Set up vendor invoice policies

- Key invoice data in Accounts payable system using vendor invoice

- Key invoice data into Accounts payable using an approval journal

- Key invoice data into the Accounts payable system using invoice pool

- Vendor invoices

- Understanding invoice line quantities

- Adding a line that wasn't on the purchase order

- Submitting a vendor invoice for review

- Matching vendor invoices to product receipts

- Configure an automated task for vendor invoice workflow to post the vendor invoice using a batch job

- Working with multiple invoices

- Recovering vendor invoices that are being used

- Default financial dimension in vendor invoice lines

- Resetting the workflow status for vendor invoices from Unrecoverable to Draft

- Viewing the invoice total on the Pending vendor invoices page

- Record a vendor invoice in the invoice journal

- Vendor open transactions report-->

## Related resources

You can use the following resources to learn more about the process vendor invoices process in Dynamics 365.

- [Vendor invoices overview - Finance](/dynamics365/finance/accounts-payable/vendor-invoices-overview#vendor-invoices)

- [Automated vendor invoicing processes overview - Finance](/dynamics365/finance/accounts-payable/auto-vendr-invc-process#match-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy)

- [Perform Accounts payable daily procedures in Dynamics 365 Finance](/training/modules/accounts-payable-daily-procedures-dyn365-finance/)

- [Configure Accounts payable in Dynamics 365 Finance](/training/modules/configure-accounts-payable-dyn365-finance/)
 
- Find definitions of terminology used in content for *process vendor invoices* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article, including the following terms:
    - [Two-way matching](glossary.md#two-way-matching)
    - [Three-way matching](glossary.md#three-way-matching)

<!--## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Accounts payable, Administrative, Audit, Engineering, Finance, IT, Merchandising, Operations, Production, Project Management, Purchasing, Retail store operations, Service operations, Transportation, Treasury, Warehouse

*Products:* Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Menekse Saygili](https://www.linkedin.com/in/fmsaygili) \| Senior Program Manager
