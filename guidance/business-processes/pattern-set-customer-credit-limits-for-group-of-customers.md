---
title: Manually set credit limit patterns for a group of customers
description: Learn how to set customer credit limits for a group of customers using Dynamics 365 to manage credit limits, including an outline on when to use this pattern.
ms.date: 02/06/2023
ms.topic: conceptual
author: rachel-profitt
ms.author: raprofit
ms.reviewer: edupont
ms.custom:
  - ai-gen-docs
  - ai-gen-desc
---

# Manually set, define, and check credit limit patterns for a group of customers

***Applies to: Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce***

This article describes how to use Dynamics 365 to manage credit limits for a group of customers.

## Context and problem

Your organization might have customers that have more than one location or account with your business. Alternatively, you might do business with the same customer in more than one legal entity. In these scenarios, it's rarely enough to define a credit limit on an individual account, when the same customer is captured as an account more than once in Dynamics 365.

## When to use this pattern

Use this pattern when:

- You primarily use sales orders or the Commerce B2B portal to manage customer balances due.

- You have multiple legal entities with the same customer in more than one legal entity that needs to share a credit limit.

- You have multiple customer accounts in a single legal entity that are the same logical organization or need the same credit limit.

This pattern might not be suitable:

- You primarily use project invoices to manage customer balances due.

- You primarily use free text invoices to manage customer balances due.

- You use a call center to manage sales orders and are using the **Credit limit** page to manage customers that are exceeding their credit limit available in the **Retail and commerce** module.

## Solution: Use credit groups to assign a credit limit to multiple customers

You can define groups of customers who have a shared credit limit. The individual credit limit that is defined on the customer invoice account is also considered.

Members of a customer credit group can be selected from different legal entities. When you add a customer to the list of customers in the customer credit group, the expiration date of the credit limit for each customer is changed to the expiration date for the group.

### Procedure: Use customer credit groups

Use the following steps to use customer credit groups to define credit limits for groups of customers.

1. Create a new customer credit group. For more information, see Customer credit groups.

2. Set the credit limit on the customer credit group.

3. Add customers to the customer credit group.

4. Optionally, add a credit limit directly to the customer account.

## Issues and considerations

A credit limit can be assigned to customers at the customer account level. Each customer can also be assigned to a *customer credit limit group*, and each group has a credit limit. Therefore, a credit limit can also be assigned to customers at the group level. All customers that are assigned to the same customer credit group have the same credit limit.

In general, group credit limits are checked before individual credit limits. The individual credit limit doesn't always override the group credit limit. For more information, see [Credit limit scenarios](/dynamics365/finance/accounts-receivable/credit-limit-scenarios).

Consider the following points when deciding how to implement this pattern:

- Is cross-company data sharing implemented for customer accounts? For more information about cross-company data sharing, see [Cross-company data sharing overview](/dynamics365/fin-ops-core/dev-itpro/sysadmin/srs-overview).

- Are projects used to invoice customers?  

  The credit management functionality does not perform a credit limit check on project invoices. However, the balance related to project invoices *is* considered when you use credit management to manage credit limits on sales orders.

- Are free text invoices used to invoice customers?  

  Keep in mind that the credit management functionality does not perform a credit limit check on free text invoices. However, the balance on free text invoices is considered in the balance for customers when you use credit management to manage credit limits on sales orders.

- Are sales orders created through a call center channel?  

  Call center channels include another credit limit check for call center orders when the *enable order completion* option is selected. We recommend that you use the two options together.

- Do you have customers in multiple legal entities and multiple currencies across legal entities?  

  You can specify a currency exchange rate type to be used for calculating customer balances in multiple currencies. Consider how the exchange rate will be managed and maintained. In most cases, for the most accurate balance calculations, consider using the same currency exchange rate type that you select in the Ledger for default transactions.

## Related resources

Use the following resources to learn more about the processes for setting customer credit limits in Dynamics 365.

- [Dynamics 365 Finance: Credit Management \| February 14, 2020 - Microsoft Dynamics Blog](https://community.dynamics.com/blogs/post/?postid=48627251-aba8-4509-8f69-5c26a9652b59)

- [Configure Accounts receivable and credit and collections](/dynamics365/finance/accounts-receivable/accounts-receivables-set-up-overview)

- [Configure credit and collections in Dynamics 365 Finance (online training)](/training/modules/configure-credit-collections-dyn365-finance/)

- [Process credit and collections in Dynamics 365 Finance (online training)](/training/modules/process-credit-collections-dyn365-finance/)

<!--## Tags
*Industries:* All

*Stakeholders:* Functional consultant, Business analyst, Accounts receivable lead, Finance lead, Sales lead, Operations lead

*Products:* Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Supply Chain Management
