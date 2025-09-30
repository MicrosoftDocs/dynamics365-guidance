---
title: Manage accounts receivable
description: Learn how to use Dynamics 365 products to support your organization's business processes for invoicing sales orders.
ms.date: 09/30/2025
ms.topic: concept-article
author: edupont04
ms.author: npaldhikar
ms.custom: bap-template
---

# Overview of the Manage accounts receivable business process area

***Applies to: Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Finance Insights, Dynamics 365 Customer Insights***

The *Manage accounts receivable* process area covers creating and sending an invoice to a customer based on a sales order or a free text invoice. Invoicing is an essential part of the order to cash process. It involves creating and sending a bill to customers for the products or services they ordered and posting it to the general ledger. The invoice process starts when a sale takes place and continues through delivery to the customer and receiving payment.

> [!IMPORTANT]
> In earlier versions of the business process catalog, this article represented a business process area, *Invoice customers*. In February 2025, it was renamed to the *Manage accounts receivable*, and we're in process of updating the content to reflect this change.

Dynamics 365 supports the following types of customer invoices:

- A **customer invoice for a sales order** is an invoice that's based on a sales order, with order lines for the items or services that were sold. Subledger journal entries aren't available for a customer invoice for a sales order.

- A **free text invoice** is an invoice that isn't related to a sales order. It contains order lines with ledger accounts, free text descriptions, and a sales amount. An item number can't be entered on this kind of invoice. A main account for the sale is indicated on each invoice line, which can be distributed to multiple ledger accounts.

- A **credit note** is a document that a seller issues to a buyer to correct an invoice or a payment. Credit notes can reduce the amount that the buyer owes to the seller, or they can refund a buyer for a returned or damaged product, for example. In Dynamics 365, you can create a credit note for different types of transactions, such as free text invoices and sales order invoices.

> [!NOTE]
> Invoicing of projects is covered in the [Project to profit](project-to-profit-introduction.md) end-to-end business process. Invoicing of services is covered in the [Service to cash](service-to-cash-introduction.md) end-to-end business process.

The invoicing process is important to an organization because it affects several aspects of its financial management. It determines how quickly and accurately a business can collect payments from its customers and pay its suppliers. A smooth and efficient invoicing process can help a business optimize its cash flow, budget, and spending.

## Stakeholders

Many people in an organization contribute to the design of the invoice customers process in your Dynamics 365 project, such as:

- **Finance stakeholders** like the CFO, controller, and accounting manager  

- **Accounts receivable stakeholders** like the accounts receivable manager and the credit and collections manager  

- **Sales stakeholders** like the VP of sales, sales directors, and general managers  

## Manage accounts receivable process flow

The following diagram illustrates the flow of the invoice customers business process area in an organization.

:::image type="content" source="media/order-to-cash-manage-accounts-receivable-flow.svg" alt-text="Diagram showing the flow of the invoice customers business process area in an organization." lightbox="media/order-to-cash-manage-accounts-receivable-flow.svg":::

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

[!INCLUDE [bus-proc-cat-pending](../includes/bus-proc-cat-pending.md)] The following text doesn't fully reflect the updated diagram yet.

The invoice customers business process area flow diagram illustrates the following steps:

1. Start

1. *Order to cash* end-to-end process

1. *Manage accounts receivable*

    1. *Issue sales invoices*  
    1. *Issue customer credits*  
    1. *Bill subscriptions*  
    1. *Recognize revenue*  
    1. *Process customer payments*  
    1. *Process customer prepayments*  
    1. *Process customer refunds*  
    1. *Settle customer transactions*  
    1. *Write off bad debt*  
    1. *Manage trade allowances*  
    1. *Calculate sales commissions*  
    1. *Manage bills of exchange*
<!-- 
1. Is it a sales order invoice?

   - A parallel branch for Yes leads to Create invoice for sales orders.

   - No leads to Create free text invoice and credit notes.

1. Two parallel branches from the Case to resolution end-to-end process lead to:

   - Create sales order credit note, which has a connection to the Invoice sales orders business process area, not shown
   - Create free text invoice and credit notes, which has a connection to the Invoice sales orders business process area, not shown

1. Post invoice and recognize revenue

1. The Post invoice and recognize revenue step has two parallel branches:

   - Process customer rebates goes to Record customer payments

   - Record customer payments

     - A parallel branch goes to the Record to report end-to-end process.

     - A parallel branch goes to the Monitor customer credit and collections business process.

1. Send invoices to customers

   - Correction needed? Yes goes to Correct invoice

   - Post Invoice and recognize revenue

1. End -->

## Benefits

Organizations can recognize many benefits from the invoice customers process in Dynamics 365.

- **More transparency and control of invoices**: You can use the customer workflow feature to change specific attributes of a customer and send the changes for approval. You can use print management settings to print or email invoices after posting, or use channels such as electronic data interchange or an integration to send the invoices to your customers.

- **Better visibility of invoices**: The invoice customers process gives you real-time tracking and reporting of invoice status, payments, and cash flow. The process helps you optimize working capital, avoid late fees, and take advantage of early payment discounts.

- **More standardized and flexible invoice workflow**: The digital invoice customers process in Dynamics 365 allows you to standardize your invoicing workflow across your customer base. Through standardization, you can better recognize revenue opportunities and improve your organization's cash flow. You can import and export information about customer invoices for sales orders and customize the layout and design of the invoice document.

- **Increased process reliability and accuracy**: You can use automated document reading to extract data from scanned or digital invoices and populate the relevant fields in Dynamics 365 Finance. This process can help you avoid duplication, mismatch, or omission of invoices. You can also use templates to create and process account assignments for recurring invoices.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *order to cash* business processes, use the following resources and steps to learn more. (Links are added when the articles are ready.)

1. *Develop sales policies*
1. *Manage sales orders*
1. *Manage accounts receivable* (the article that you're currently reading)  

    1. *Issue sales invoices*  
    1. *Issue customer credits*  
    1. *Bill subscriptions*  
    1. *Recognize revenue*  
    1. *Process customer payments*  
    1. *Process customer prepayments*  
    1. *Process customer refunds*  
    1. *Settle customer transactions*  
    1. *Write off bad debt*  
    1. *Monitor trade allowances*  
    1. *Calculate sales commissions*  
    1. *Manage bills of exchange*
1. [Manage credit and collections](order-to-cash-monitor-customer-credit-collections-overview.md)  
1. *Analyze sales performance*

## Related information

- [Create a customer invoice](/dynamics365/finance/accounts-receivable/configure-customer-invoices)

- [Create sales order invoices](/dynamics365/finance/accounts-receivable/tasks/create-sales-order-invoices)

- [Create a free text invoice](/dynamics365/finance/accounts-receivable/create-free-text-invoice-new)

- [Customer posting profiles](/dynamics365/finance/accounts-receivable/customer-posting-profiles)

- [Create a credit note against a sales invoice](/dynamics365/finance/localizations/apac-ind-GST-credit-note-against-sales-invoice)

- [Process interest](/dynamics365/finance/accounts-receivable/tasks/process-interest)

- [Implementing an order to cash technology solution](../implementation-guide/implementation-strategy.md)

- [Business process scope](../implementation-guide/process-focused-solution.md)  

- [Overview of the order to cash process](order-to-cash-overview.md).

- Find definitions of terminology in the [Glossary of terms in Dynamics 365 business processes](glossary.md), including the following terms:

  - [Invoice](glossary.md#invoice)
  - [Sales order](glossary.md#sales-order)
  - [Free text invoice](glossary.md#free-text-invoice)
  - [Pro forma invoice](glossary.md#pro-forma-invoice)
  - [Credit note](glossary.md#credit-note)
  - [Invoice payment terms](glossary.md#invoice-payment-terms)
- [Request a demo](https://www.microsoft.com/dynamics-365/free-trial)  
- [Microsoft Power Platform](https://powerplatform.microsoft.com/).

<!-- ## Tags

*Industries:* All

*Stakeholders:* Finance stakeholders, Accounts receivable stakeholders, Sales stakeholders, Operations stakeholders

*Products:* Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Nikhil Paldhikar](https://www.linkedin.com/in/nikhil-paldhikar-08232211/) \| FastTrack Senior R&D Solution Architect

Other contributors:

- [Rachel Profitt](https://www.linkedin.com/in/rachelprofitt/) \| FastTrack Solution Architect

- [Anne Krupke](https://www.linkedin.com/in/annekrupke/) \| FastTrack Solution Architect
