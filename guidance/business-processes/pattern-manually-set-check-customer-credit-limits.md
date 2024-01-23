---
title: Manually set, define, and check customer credit limit patterns
description: Manually set and check customer credit limits to reduce unpaid balance and protect against risk of non-payment in Dynamics 365.
ms.date: 02/06/2023
ms.topic: conceptual
author: rachel-profitt
ms.author: raprofit
ms.reviewer: edupont
ms.custom:
  - ai-gen-docs
  - ai-gen-desc
---

# Manually set, define, and check customer credit limit patterns

***Applies to: Dynamics 365 Finance, Dynamics 365 Supply Chain Management***

This article describes how to manually set and check a customer credit limit during transactions, such as when you process deliveries or invoices.

## Context and problem

When your organization does business with other businesses or has frequent repeat buyers, you might extend a certain amount of credit to the customer with payment terms as part of your customer agreement. You can define credit limits for your customers and check the credit limit when you process transactions such as free text invoices, sales order invoices, or sales order packing slips, for example. Credit limits help reduce the amount of unpaid balance a customer can have with your organization at a given time.

## When to use this pattern

Use this pattern when:

- Your business process requires a basic warning or error message on all documents for a sales order or free text invoice.

- You only have one credit limit per customer and no groups of customers have a credit limit defined.

This pattern might not be suitable:

- You have multiple legal entities with the same customer in more than one legal entity that needs to share a credit limit.

- You have multiple customer accounts in a single legal entity that are the same logical organization or need the same credit limit.

- You use a call center to manage sales orders and are using the **Credit limit** page to manage customers that are exceeding their credit limit available in the **Retail and commerce** module.

- You require more robust rules for checking credit limits. For example, checking credit limits on release to warehouse, checking on pro-forma documents, allowing days of grace for credit limit checks on certain documents.

## Solution: Use basic customer credit limit checking

You can manually set credit limits on each customer account. Then, you also specify a default credit limit checking type that must be used when users post transactions. Users with the proper security can override the default credit limit checking type or manually perform a credit limit check. Also, parameters might force the system to automatically check a customer's credit limit when certain events occur.  

### Procedure: Set customer credit limits and define default credit limit checking options

Use the following steps to manually set a customer credit limit and define the default credit limit checking options.

1. Select the **Allow manual editing of credit limit** option on the **Credit** tab of the **Credit and collections parameters** page.

2. Select the default value for the **Credit limit type** field on the **Credit** tab of the **Credit and collections parameters** page. For more information, see [Credit management parameters setup](/dynamics365/finance/accounts-receivable/cm-credit-mgmt-setup).

3. Set the credit limit on a customer manually. For more information, see [Add credit management information for customers](/dynamics365/finance/accounts-receivable/cm-add-credit-mgmt-information-customer#customer-information).

### Procedure: Check customer credit limits on sales orders

Use the following steps to check a customer's credit limit on a sales order.

1. Select the **Check credit limit on sales order** option on the **Credit** tab of the **Credit and collections parameters** page.

2. Select the default value for the **Credit limit type** field on the **Credit** tab of the **Credit and collections parameters** page. For more information, see [Credit management parameters setup](/dynamics365/finance/accounts-receivable/cm-credit-mgmt-setup).

3. Choose *Warning* or *Error* in the **Message when exceeding credit limit** field on the **Credit** tab of the **Credit and collections parameters** page.

4. Create a sales order.

5. Optionally, confirm the sales order. On the **Confirm sales order** page, optionally override the **Credit limit type** field on the **Parameters** FastTab.

6. Optionally, generate a picking list for the sales order. On the **Posting picking list** page, optionally override the **Credit limit type** field on the **Parameters** FastTab.

7. Optionally, post a packing slip for the sales order. On the **Packing slip posting** page, optionally override the **Check credit limit** field on the **Parameters** FastTab.

8. Post the sales order invoice. On the **Posting invoice** page, optionally override the **Credit limit type** field on the **Parameters** FastTab.

### Procedure: Check customer credit limits on free text invoices

Use the following steps to check a customer's credit limit on a free text invoice.

1. Select the **Check credit limit on free text invoice** option on the **Credit** tab of the **Credit and collections parameters** page.

2. Select the default value for the **Credit limit type** field on the **Credit** tab of the **Credit and collections parameters** page. For more information, see [Credit management parameters setup](/dynamics365/finance/accounts-receivable/cm-credit-mgmt-setup).

3. Choose *Warning* or *Error* in the **Message when exceeding credit limit** field on the **Credit** tab of the **Credit and collections parameters** page.

4. Create a free text invoice.

5. Post the sales order invoice. On the **Post free text invoice** page, optionally override the **Credit limit type** field on the **Parameters** FastTab.

## Issues and considerations

Consider the following points when deciding how to implement this pattern:

- Any user with the rights to generate or post a document can update the **Credit limit type** field on the dialog when they generate or post the document. Consider if a custom security privilege is required for your business case to prevent users from updating this option.

- If you chose *Warning* in the **Message when exceeding credit limit** field on the **Credit** tab of the **Credit and collections parameters** page, a user will receive a warning message in the info log when they perform the action. However, no actions are prevented from happening when you select *Warning*. 

  To prevent a document from posting, set the **Message when exceeding credit limit** field to *Error*. For example, the field is set to *Warning*, and a customer exceeds their credit limit. In this case, when you generate a packing slip for a customer, the user receives a warning that the credit limit is exceeded. However, the packing slip is still generated. If you do not have a manual process and training in place for your users, the product might still be shipped to your customer, increasing your risk for an unpaid balance.

## Related resources

Use the following resources to learn more about the processes for setting customer credit limits in Dynamics 365.

- [Dynamics 365 Finance: Credit Management \| February 14, 2020 - Microsoft Dynamics Blog](https://community.dynamics.com/blogs/post/?postid=48627251-aba8-4509-8f69-5c26a9652b59)

- [Configure Accounts receivable and credit and collections](/dynamics365/finance/accounts-receivable/accounts-receivables-set-up-overview)

- [Configure credit and collections in Dynamics 365 Finance (online training)](/training/modules/configure-credit-collections-dyn365-finance/)

- [Process credit and collections in Dynamics 365 Finance (online training)](/training/modules/process-credit-collections-dyn365-finance/)

<!--## Tags
*Industries:* All

*Stakeholders:* Functional consultant, Business analyst, Accounts receivable lead, Finance lead, Sales lead, Operations lead

*Products:* Dynamics 365 Finance, Dynamics 365 Supply Chain Management
