---
title: Manage credit and collections
description: Learn how to use Dynamics 365 products to monitor customer credit and collections and reduce bad debt.
ms.date: 11/17/2023
ms.topic: concept-article
author: rachel-profitt
ms.author: raprofit
ms.reviewer: edupont
ms.custom:
  - ai-gen-docs
  - ai-gen-desc
---

# Manage credit and collections business process area

***Applies to: Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Project Operations, Dynamics 365 Finance Insights, Dynamics 365 Fraud Protection, Dynamics 365 Customer Insights***

This article describes how you can use Dynamics 365 products to support your organization's business processes for monitoring customer credit and collections.

> [!IMPORTANT]
> In earlier versions of the business process catalog, this article represented a business process area, *Monitoring customer credit and collections*. In February 2025, it was renamed to the *Manage credit and collections*, and we're in process of updating the content to reflect this change.

## Introduction to Manage credit and collections

In many organizations, not least organizations with a business-to-business sales model, setting credit limits is an important process that helps organizations remain competitive. Credit limits can also help an organization minimize bad debt and the need to write off unpaid balances. When you manage the collection process carefully, it helps you get customers pay on time, increases the cash flow, and helps make the cash flow of the organization more predictable.

The process for managing credit and collections often splits into two main focuses in a Dynamics 365 project:

1. The configuration of master data for your customers, and the establishment of the credit limits, payment terms, and so on.  
2. The monitoring of orders and invoices to ensure that customers remain within the credit limits and rules that you established to ensure that you can reduce the risk for fraudulent orders and accounts.  

## Using Dynamics 365 to manage credit and collections

Dynamics 365 Finance includes functionality to help you manage your customer master data including establishing credit limits, credit scores, and so on. The Finance app can also help you monitor orders for fraudulent activity, reconcile the credit limits to the customers' balances, and place orders or customers on hold based on your business rules.

Large retailers, not least retailers that primarily do business online with consumers, typically have credit or fraud departments that monitor sales for fraudulent activity. Dynamics 365 Fraud Protection includes functionality to help customers manage fraud in three key pillars including account protection, loss prevention, and purchase protection. Fraud Protection uses artificial intelligence (AI) to help protect your business from fraud.

## Stakeholders

Many people in an organization must contribute to the decision-making process and design of the monitoring customer credit and collections process in your Dynamics 365 project. Stakeholders include the roles listed in the following list:

- Finance stakeholders – Examples: CFO, Controller, Accounting manager

- Accounts receivable stakeholders – Examples: Accounts receivable manager, Credit and collections manager

- Sales stakeholders – Examples: VP of sales, Sales Directors, General Managers

- Operations stakeholders – Examples: COO, Risk managers, Fraud managers

## Process flow

The following diagram shows the high-level business process flow for monitoring customer credit and collections. There are several entry points for the subprocesses described in the diagram including one from the prospect to quote end-to-end process, and several from the order to cash end-to end process.

The following diagram shows the high-level flow of the *Manage credit and collections* business process area. [!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/order-to-cash-monitor-customer-credit-collections-process-flow.svg" alt-text="Monitor customer credit and collections process flow." lightbox="media/order-to-cash-monitor-customer-credit-collections-process-flow.svg":::

The *Manage credit and collections* business process area flow diagram covers the following steps.

1. [Order to cash](order-to-cash-overview.md)

2. *Monitor customer credit and collection*

    1. *Set customer credit limits*

        a. *Update customer credit limits*

          The following sequence shows an alternate starting point for this step.

          1. *Prospect to quote*

          2. *Create customer*

          3. *Establish payment terms*

          4. *Set customer credit limit*
        b. *Block or close customer accounts*

    2. *Detect fraudulent orders*

          The following sequence shows an alternate starting point for this step.

          1. *Order to cash*

          2. *Create and manage sales orders*

          3. Is the order fraudulent? If yes, then *Detect fraudulent orders*.

    3. *Handle NSF payments*

          The following sequence shows an alternate starting point for this step.

          1. *Order to cash*

          2. *Record customer payments*

          3. Are there non-sufficient funds? If yes, then *handle NSF payments*.
    4. *Dispute and resolve invoice discrepancies*

          The following sequence shows an alternate starting point for this step.

          1. *Order to cash*

          2. *Issue customer invoices*

          3. Is the invoice disputed? If yes, then *dispute and resolve invoice discrepancies*.
    5. *Process customer account statements*

        a. *Create and process collection letters*

        b. *Create and process interest notes*

> [!NOTE]
> The *Manage credit and collections* business process area flow diagram is described at a high level. There may be variations in the process flow depending on your operating model and business process requirements.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *Manage credit and collections* business process area, you can use the following business processes. Use the following resources and steps to learn more. (Links are added when the articles are ready.)

1. *Develop sales policies*
1. *Manage sales orders*
1. [Manage accounts receivable](order-to-cash-invoice-sales-orders-overview.md)  
1. *Manage credit and collections* (the article that you're currently reading)  

    1. *Assess customer credit risk*
    1. *Manage customer account holds*
    1. *Monitor customer credit*
    1. *Collect interest*
    1. *Manage customer*
1. *Analyze sales performance*

## Related information

Use the following resources to learn more about the *Manage credit and collections* process in Dynamics 365.

- [Dynamics 365 Finance: Credit Management TechTalk](https://community.dynamics.com/blogs/post/?postid=48627251-aba8-4509-8f69-5c26a9652b59)

- [Process Automation for Customer Collections and Vendor Payments TechTalk](https://community.dynamics.com/blogs/post/?postid=642c2a5d-99b8-4c00-90c2-822c4ff511c8)  

- [Credit and collections overview](/dynamics365/finance/accounts-receivable/cm-credit-and-collections-overview)

- [Finance insights home page](/dynamics365/finance/finance-insights/finance-insights-home-page)

- [Overview of Dynamics 365 Fraud Protection](/dynamics365/fraud-protection/)

- [Configure credit and collections in Dynamics 365 Finance (online training)](/training/modules/configure-credit-collections-dyn365-finance/)

- [Process credit and collections in Dynamics 365 Finance (online training)](/training/modules/process-credit-collections-dyn365-finance/)

- [Set up and work with Finance insights in Dynamics 365 Finance (online training)](/training/paths/setup-work-finance-insights/)

- [Deploy and work with Account Protection and Purchase Protection for Dynamics 365 Fraud Protection (online training)](/training/paths/deploy-work-account-purchase-protection/)

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Rachel Profitt](https://www.linkedin.com/in/rachelprofitt/) | Principal Program Manager, FastTrack for Dynamics 365  

<!--## Tags
*Industries:* All

*Stakeholders:* Finance stakeholders, Accounts receivable stakeholders, Sales stakeholders, Operations stakeholders

*Products:* Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Fraud Protection, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management
