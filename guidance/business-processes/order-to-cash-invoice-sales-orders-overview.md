---
title: Invoice customers overview
description: Learn how to use Dynamics 365 products to support your organization's business processes for invoicing customers including sales orders, free text invoices, project invoices, and service invoices.
ms.date: 05/31/2023
ms.topic: overview
author: edupont04
ms.author: npaldhikar
ms.custom: bap-template
---

# Invoice customers overview

***Applies to: Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management, Dynamics 365 Finance Insights, Dynamics 365 Customer Insights***

The invoice customers process area covers creating and sending an invoice to a customer based on a sales order, free text invoice, project, or service work. Invoicing is an essential part of the order to cash process. It involves creating and sending a bill to customers for the products or services they ordered and posting it to the general ledger. The invoice process starts when a sale or service takes place and continues through delivery or the products or services to the customer and receiving payment.

Dynamics 365 supports the following types of customer invoices:

- A **customer invoice for a sales order** is an invoice that's based on a sales order, with order lines for the items or services that were sold. Manually entered subledger journal entries aren't available for a customer invoice for a sales order becuase they are created automatically based on the setup in the customer posting profile and the item group posting profiles.

- A **free text invoice** is an invoice that isn't related to a sales order. It contains order lines with ledger accounts, free text descriptions, and a sales amount. An item number can't be entered on this kind of invoice. A main account for the sale is indicated on each invoice line, which can be distributed to multiple ledger accounts.

- A **project invoice** is an invoice that based on a project. A project invoice is a collection of expenses which can come from time, purchases, production, sales, free text invoices, on account transactions, and much more that are collected together in a project or multiple projects in a project hierarchy. The main accounts that are used for project invoices come from the project posting profile which can be defined by project groups or by project categories or a combination of both. Projects allow for flexible posting rules based on your business requirements.

- A **service invoice** is an invoice that is based on work performed in a service work order. Service work typically includes time for the services provided, but can also include materials or products consumed. When you use Dynamics 365 Field Service you can generate basic invoices that you integrate to another financial system, or you can integrate the invoices into Dynamics 365 Project Operations using Dual Write to create project invoices. 

- A **credit note** is a document that a seller issues to a buyer to correct an invoice or a payment. Credit notes can reduce the amount that the buyer owes to the seller, or they can refund a buyer for a returned or damaged product, for example. In Dynamics 365, you can create a credit note for different types of transactions, such as free text invoices and sales order invoices.

The invoicing process is important to an organization because it affects several aspects of its financial management. It determines how quickly and accurately a business can collect payments from its customers and pay its suppliers. A smooth and efficient invoicing process can help a business optimize its cash flow, budget, and spending.

## Stakeholders

Many people in an organization contribute to the design of the invoice customers process in your Dynamics 365 project, such as:

- **Finance stakeholders** like the CFO, controller, accounting manager, and project controllers. The finance stakeholders are responsible for defining and overseeing the invoicing process. They provide insights into the financial requirements, billing cycles, and payment terms, for example. Project controllers oversee financial aspects of projects, ensuring that costs are accurately accounted for and align with the budget. They collaborate with the other finance stakeholder to reconcile financial data for invoicing.

- **Accounts receivable stakeholders** like the accounts receivable manager and the credit and collections manager  

- **Sales stakeholders** like the VP of sales, sales directors, and general managers. The sales team contributes by providing customer information, sales agreements, and pricing details. Their collaboration ensures accurate invoicing based on the terms established during the sales process.

- **Customer service stakeholders** like customers service representatives, call center workers, and managers. Customer service stakeholders should play a role in handling customer inquiries related to invoices. They contribute feedback on common customer concerns and help refine the invoicing process for better customer satisfaction.

- **Complaince and legal stakeholders** like auditors and general counsel. The compliance and legal team ensures that the invoicing process adheres to regulatory requirements and industry standards. They contribute to creating legally compliant and transparent invoices. This is especially important in countries and regions that have strict requirements for reporting or sending invoices to the government, for example.

- **Customer** The customer is a crucial stakeholder in the invoicing process. Their feedback on the clarity and accuracy of invoices is valuable for continuous improvement. Customer expectations and preferences should be considered during the design of the invoicing solution.

- **Project managers** Project managers are crucial for project-based invoices. They provide insights into project milestones, deliverables, and resource allocation, ensuring accurate billing based on project progress.

- **Service delivery stakeholders** For service-based invoices, the service delivery team provides information on services rendered, hours worked, and any additional costs incurred during the delivery of services.

- **Contract stakeholders** like contract managers, sales managers, operations managers, and so on. Contract stakeholders play a pivotal role in ensuring that project or service-based invoices align with the terms and conditions specified in contracts. They collaborate with the finance stakeholders to incorporate contractual obligations into the invoicing process.

- **Time and expense approvers** In project-based or service-based billing, individuals responsible for approving time and expenses need to be included. They validate the accuracy of reported hours and expenses before they are included in the invoicing process.

- **Resource managers** Resource managers contribute by providing information on resource utilization, availability, and allocation, which directly impacts the billing for services provided by the team.

## Invoice sales orders process flow

The following diagram illustrates the flow of the invoice sales orders business process area in an organization.

:::image type="content" source="media/order-to-cash-invoice-sales-orders-flow.svg" alt-text="Diagram showing the flow of the invoice sales orders business process area in an organization." lightbox="media/order-to-cash-invoice-sales-orders-flow.svg":::

[!INCLUDE [daf-business-process-flow-def](../includes/daf-business-process-flow-def.md)]

The invoice sales orders business process area flow diagram illustrates the following steps:

1. Start

   - A parallel branch leads to Project to profit and Service to cash end-to-end processes shown on the left side.
   - A parallel branch leads to Case to resolution end-to-end process shown on the top to the right of Order to cash end-to-end process. 

1. Order to cash end-to-end process

1. Invoice customers

   - Create sales order invoices
   - Create free text invoices
   - Create project invoices
      - An alternate starting branch connects from the Project to profit end-to-end process 
   - Create service invoices
      - An alternate starting branch connects from the Service to cash end-to-end process 

1. Credit required?

   - The yes branch has parallel connections to each of the following:

      - Create sales order credit notes
      - Create free text credit notes
      - Create project credit notes
      - Create service credit notes

   - Each of these has a connection to the Correction needed? decision box.
   - No leads to Correction needed? decision box.

1. Correction needed? decision box

   - Yes leads to Correct invoices
   - No leads to Post inovices and recognize revenue
     
1. Post invoices and recognize revenue

   - An on page reference labeled 1, connects to Record to report end-to-end process shown on the right.
   - Record ro report connects to Record financial transactions.
   - Record financial transactions connects to End.

1. Send invoices to customers

   - A parallel branch connects to Order to cash end-to-end process on the right.
   - Order to cash connects to Record customer payments
   - Record customer payments has parallel branches connecting to Monitor customer credit and collections and Record to report end-to-end process. 

1. End

## Invoice sales orders benefits

Organizations can recognize many benefits from the invoice sales orders process in Dynamics 365.

- **More transparency and control of invoices**: You can use the customer workflow feature to change specific attributes of a customer and send the changes for approval. You can use print management settings to print or email invoices after posting, or use channels such as electronic data interchange or an integration to send the invoices to your customers.

- **Better visibility of invoices**: The invoice sales orders process gives you real-time tracking and reporting of invoice status, payments, and cash flow. The process helps you optimize working capital, avoid late fees, and take advantage of early payment discounts.

- **More standardized and flexible invoice workflow**: The digital invoice sales orders process in Dynamics 365 allows you to standardize your invoicing workflow across your customer base. Through standardization, you can better recognize revenue opportunities and improve your organization's cash flow. You can import and export information about customer invoices for sales orders and customize the layout and design of the invoice document.

- **Increased process reliability and accuracy**: You can use automated document reading to extract data from scanned or digital invoices and populate the relevant fields in Dynamics 365 Finance. This process can help you avoid duplication, mismatch, or omission of invoices. You can also use templates to create and process account assignments for recurring invoices.

## Next steps

1. Manage store operations

1. Create and manage sales

1. Invoices customers (you are currently on this step.)

1. Record customer payments
   
1. [Monitor customer credit and collections](order-to-cash-monitor-customer-credit-collections-overview.md).

## Related resources

- [Create a customer invoice](/dynamics365/finance/accounts-receivable/configure-customer-invoices)

- [Create sales order invoices](/dynamics365/finance/accounts-receivable/tasks/create-sales-order-invoices)

- [Create a free text invoice](/dynamics365/finance/accounts-receivable/create-free-text-invoice-new)

- [Customer posting profiles](/dynamics365/finance/accounts-receivable/customer-posting-profiles)

- [Create a credit note against a sales invoice](/dynamics365/finance/localizations/apac-ind-GST-credit-note-against-sales-invoice)

- [Process interest](/dynamics365/finance/accounts-receivable/tasks/process-interest)

- [Project invoice proposals](/dynamics365/project-operations/invoicing/format-update-project-invoice-proposals.md)

- [Correct project invoice proposals](/dynamics365/project-operations/invoicing/correct-project-invoice-proposals.m)

- [Projcet invoicing](/dynamics365/finance/accounts-payable/project-invoicing.md)

- [Set up agreements to automatically generate work orders and invoices](dynamics365/field-service/set-up-customer-agreements.md)

- Find definitions of terminology in the [Glossary of terms in Dynamics 365 business processes](glossary.md), including the following terms:

  - [Invoice](glossary.md#invoice)
  - [Sales order](glossary.md#sales-order)
  - [Free text invoice](glossary.md#free-text-invoice)
  - [Pro forma invoice](glossary.md#pro-forma-invoice)
  - [Credit note](glossary.md#credit-note)
  - [Invoice payment terms](glossary.md#invoice-payment-terms)

<!-- ## Tags

*Industries:* All

*Stakeholders:* Finance stakeholders, Accounts receivable stakeholders, Sales stakeholders, Operations stakeholders

*Products:* Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Nikhil Paldhikar](https://www.linkedin.com/in/nikhil-paldhikar-08232211/) \| FastTrack Senior R&D Solution Architect

Other contributors:

- [Rachel Profitt](https://www.linkedin.com/in/rachelprofitt/) \| Principal Program Manager

- [Anne Krupke](https://www.linkedin.com/in/annekrupke/) \| FastTrack Solution Architect
