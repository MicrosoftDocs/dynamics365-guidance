---
title: Set customer credit limits
description: Set up customer credit limits in Finance, Customer Insights, Supply Chain Management, or Commerce to control borrowing and reduce risk.
ms.date: 02/06/2023
ms.topic: conceptual
author: rachel-profitt
ms.author: raprofit
ms.reviewer: edupont
ms.custom:
  - ai-gen-docs
  - ai-gen-desc
---

# Set customer credit limits

***Applies to: Dynamics 365 Finance, Dynamics 365 Customer Insights, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce***

This article describes the setup, configuration, and design considerations for managing customer account credit limits in Dynamics 365 Finance and Dynamics 365 Customer Insights.

Credit limits help financial institutions control the maximum amount of money that a customer can borrow. In other industries, especially industries with business-to-business sales models, credit limits help the organizations restrict the total balance that is unpaid by a specific customer, or the maximum number of products that a customer can order at any given time. This way, organizations can reduce the risk for unpaid balances and the need to write off bad debt. Additionally, it encourages customers that order frequently to keep their accounts current, which helps improve an organization's cash flow.

Dynamics 365 Finance helps organizations define and periodically update customer credit limits. If your organization requires credit limit check in your order-to-cash business processes, the requirement must be included as part of your project. The setup and configuration can be done at any time during the design phase of your project. You can also add the check for credit limit later if you decide not to implement this feature during your initial go-live.

## Customer credit limit stakeholders

Many people in an organization should contribute to the decision-making process and design of the process for setting customer credit limits in your Dynamics 365 project. Stakeholders include, but is not limited to the following list:

- Finance stakeholders – Examples: CFO, Controller, Accounting manager

- Accounts receivable stakeholders – Examples: Accounts receivable manager, Credit and collections manager

- Sales stakeholders – Examples: VP of sales, Sales Directors, General Managers

- Operations stakeholders – Examples: COO, Risk managers, Fraud managers

## Set customer credit limits process flow

The following diagram illustrates the business process.

:::image type="content" source="media/order-to-cash-set-customer-credit-limits-process-flow.svg" alt-text="Set customer credit limit process flow diagram.":::

The process flow diagram includes the following steps.

1. Create a customer (a prerequisite business process before you start).

2. Start

3. Request financial statements, credit references, and/or other pertinent data from customer (manual step).

4. Gather Dun & Bradstreet data, perform ratio analysis, and so on (manual step).

    > [!NOTE]
    > If you use Dynamics 365 Customer Insights and Dun & Bradstreet, use the integration capabilities to automatically gather data about the customer. Learn more at [Enrich company profiles with Dun & Bradstreet](/dynamics365/customer-insights/enrichment-dnb).

5. Establish a customer credit rating, and propose terms and credit limit (manual step).

6. Set credit limit and check mandatory box if applicable in Finance.

7. Enter credit ratings in Finance.

8. Optionally, add the DUNS number in Finance.

9. Choose the payment terms and the method of payment in Finance.

10. Review and update relevant delivery terms as needed in Finance.

11. Submit the proposed changes in workflow in Finance.

12. Review the proposed credit limit, rating, and payment terms in Finance.

13. Approval

    1. If not approved, adjust the credit limit, alter the terms and the method of payment

    2. If approved, go to step 14.

14. The credit limit, rating, terms, and method of payment is automatically saved to the customer record

15. End

Steps 3-9 are in one swim lane that's dedicated to an Accounts receivable clerk or Accounts receivable manager.

Steps 10-14 are in another swim lane that's dedicated to an Accounts receivable manager or Accounting manager.

## Implementing credit limits for customer accounts

You can define rules in Dynamics 365 Finance to automatically place orders on hold when the criteria are met. When an order is on a credit hold, the order cannot be processed further until the order is released from the hold. Dynamics 365 includes multiple ways to put an order on hold the following tables and sections describe the various configurations and operational processes that are part of setting customer credit limits in Dynamics 365 applications.  

> [!TIP]
> A variety of terminology and concepts are used throughout this article to describe the business process. For definitions and explanations of key terms and concepts, see [Glossary of terms in Dynamics 365 business processes](glossary.md).

The following sections show the configurations available, and the sequence recommended for setting up the configurations from top to bottom. Learn more about the terms used in the table at [Business processes, steps, and how to find things](about-steps-navigation.md).  

### Basic credit limit checking

(Finance – Credit and collections management)

Use this option when you need to perform a basic credit limit check on Free text invoices, Project invoices, and Sales orders. This option allows you to select the level of warning or error and when the credit limit check will be performed.

| Process step | Process stage | Process modifiers | App, navigation, and entity |
|---|---|---|---|
| [Credit and collections parameters](/dynamics365/finance/accounts-receivable/set-up-collections) | Initialize; Base; Configuration | Gold; At least one | **FIN**: Credit and collections &gt; Setup &gt; Credit and collections parameters &gt; Credit tab &gt; Credit limit FastTab <br><br> **DMF**: *CustomerParameters* |
| [Establish customer terms of payment](/dynamics365/finance/general-ledger/tasks/establish-customer-payment-terms) | Design; Fundamental; Configuration | Gold; At least one is required; Multiple are recommended | **FIN**: Accounts receivable &gt; Payments setup &gt; Payment days <br><br> **DMF**: *PaymentTerm* |
| [Establish customer methods of payment](/dynamics365/finance/accounts-receivable/tasks/establish-customer-method-payment) | Design; Fundamental; Configuration | Gold; At least one is required; Multiple are recommended | **FIN**: Accounts receivable &gt; Payments setup &gt; Methods of payment <br><br> **DMF**: *CustomerPaymentMethod* |
| Payment days | Design; Optional; Configuration | Gold; Multiple are recommended | **FIN**: Accounts receivable &gt; Payments setup &gt; Payment days <br><br> **DMF**: *PaymentDay* |
| [Cash discount codes](/dynamics365/finance/cash-bank-management/cash-discounts) | Design; Optional; Configuration | Gold; Multiple are recommended | **FIN**: Accounts receivable &gt; Payments setup &gt; Cash discount <br><br> **DMF**: *CashDiscount* |
| [Set customer credit and terms](/dynamics365/finance/accounts-receivable/cm-add-credit-mgmt-information-customer) | Design; Fundamental; Operations | Gold; At least one is required; Multiple are recommended; Continuous | **FIN**: Accounts receivable &gt; Customers &gt; All customers <br><br> **DMF**: *CustomersV3* |

### Credit holds

(Finance – Credit and collections management)

Use this option when you need more control over the credit limits and checking process for Sales orders. This option does not work with Project invoices or Free text invoices.

| Process step | Process stage | Process modifiers | App, navigation, and entity |
|---|---|---|---|
| [Credit management reasons](/dynamics365/finance/accounts-receivable/cm-setup-information#reasons) | Design; Fundamental; Configuration | Gold; At least 1; More than one recommended | **FIN**: Credit and collections &gt; Setup &gt; Credit management setup &gt; Credit management reasons <br><br> **DMF**: CredManBlockReason |
| Exchange rate types | Design; Fundamental; Configuration | Early; Gold; At least one; More than one recommended | **FIN**: General ledger &gt; Currencies &gt; Exchange rate types <br><br> **DMF**: ExchangeRateType |
| [Credit and collections parameters](/dynamics365/finance/accounts-receivable/cm-credit-mgmt-setup) | Design; Fundamental; Configuration | Early; Gold; At least one | **FIN**: Credit and collections &gt; Setup &gt; Credit and collections parameters &gt; Credit tab &gt; Credit limit FastTab <br><br> **DMF**: *CredManParameters* |
| [Credit management workflows](/dynamics365/finance/accounts-receivable/cm-setup-information#credit-management-workflows) | Design; Optional; Configuration | Gold; More than one recommended | **FIN** : Credit and collections &gt; Setup &gt; Credit management workflows <br><br> Use the **Versions &gt; Export** and **Import** buttons on the **Credit management workflows** page to move configuration between environments. |
| [Blocking rules](/dynamics365/finance/accounts-receivable/cm-sales-order-credit-holds#set-up-blocking-rules-and-exclusion-rules) | Design; Optional; Configuration | Gold; More than one recommended | **FIN**: Credit management &gt; Setup &gt; Credit management setup &gt; Blocking rules <br><br> **DMF**: *CredManBlockExclusionRule* |
| [Credit management groups](/dynamics365/finance/accounts-receivable/cm-setup-information#credit-management-groups) | Design; Optional; Configuration | Gold; More than one recommended | **FIN**: Credit and collections &gt; Setup&gt; Credit management setup &gt; Credit management groups <br><br> **DMF**: *CredManGroup*, *CredManCreditLimitCustGroupLine*, *CredManCreditLimitCustGroup* |
| [Account statuses](/dynamics365/finance/accounts-receivable/cm-setup-information#account-statuses) | Design; Fundamental; Configuration |Early; Gold; At least one; More than one recommended | **FIN**: Credit and collections &gt; Setup&gt; Credit management setup &gt; Account statuses <br><br> **DMF**: *CredManAccountStatus* |
| [Scoring groups](/dynamics365/finance/accounts-receivable/cm-setup-information#scoring-groups) | Design; Optional; Configuration | Gold; More than one recommended | **FIN**: Credit and collections &gt; Setup&gt; Credit management setup &gt; Risk &gt; Scoring groups <br><br> **DMF**: *CredManRiskGroup*, *CredManCustRiskScore* |
| [Guarantee/insurance types](/dynamics365/finance/accounts-receivable/cm-setup-information#guaranteeinsurance-types) | Design; Optional; Configuration | Gold; More than one recommended | **FIN**: Credit and collections &gt; Setup &gt; Insurance and guarantees &gt; Insurances and guarantee types <br><br> **DMF**: *CredManGuaranteeInsuranceType* |
| [Coverage types](/dynamics365/finance/accounts-receivable/cm-setup-information#coverage-types) | Design; Optional; Configuration | Gold; More than one recommended | **FIN**: Credit and collections &gt; Setup &gt; Insurance and guarantees &gt; Coverage types <br><br> **DMF**: CredManInsuranceCoverageType |
| [Automatic credit limits](/dynamics365/finance/accounts-receivable/cm-setup-information#automatic-credit-limits) | Design; Optional; Configuration | Gold; More than one recommended | **FIN**: Credit and collections &gt; Setup&gt; Credit management setup &gt; Risk &gt; Automatic credit limits <br><br> **DMF**: *CredManCreditLimitRule*, *CredManCreditLimitRuleLine* |
| Set customer credit and terms | Design; Fundamental; Operational | Gold; At least one; More than one recommended; Continuous | **FIN**: Accounts receivable &gt; Customers &gt; All customers <br><br> **DMF**: CustomersV3 |
| Set customer group credit limit | Design; Fundamental; Operational | Gold; At least one; More than one recommended; Continuous | **FIN**: Credit and collections management &gt; Customers &gt; Customer credit groups <br><br> **DMF**: N/A |

### Sales order holds
(Supply chain management – Sales order management)

Use this option when you need other types of holds, or when you have complex rules that need to be evaluated for sales orders. This option does not work for Project invoices or Free text invoices. Use this option in combination with any other options.

Basic sales order holds can help you manually manage credit limits and credit holds. Fraud rules (an advanced feature of the sales order hold functionality) can be used to automatically check for certain conditions. However, we generally recommend that you consider an alternative approach for managing credit limit checking in Dynamics 365. For more information about how to use sales order holds, see [Manage order holds](/dynamics365/supply-chain/sales-marketing/tasks/manage-order-holds).

### Check holds

(Commerce – Call center)

Use this option when you use a call center channel with Dynamics 365 Commerce, and you want to automatically place orders that are paid by check on a hold. The holds can be automatically released after a specified amount of time, or you can use a manual process to release the orders once the check has cleared the bank. You can use this option in combination with the *Credit limit workbench* option.

| Process step | Process stage | Process modifiers | App, navigation, and entity |
|---|---|---|---|
| [Enable order completion](/dynamics365/commerce/set-up-order-processing-options#enable-order-completion) | Initialize; Fundamental; Configuration | Early; Gold; At least one | **COM**: Retail and commerce &gt; Channel setup &gt; Call center setup &gt; Call center parameters <br><br> **DMF**: N/A |
| [Call center channel](/dynamicsax-2012/appuser-itpro/set-up-a-call-center) | Initialize; Fundamental; Configuration | Early; Gold; At least one | **COM**: Retail and commerce &gt; Channels &gt; Call centers &gt; All call centers <br><br> **DMF**: *RetailCallCenter* |
| [Call center payment methods](/dynamicsax-2012/appuser-itpro/set-up-payment-methods-call-center#1-create-payment-methods-in-retail) | Initialize; Fundamental; Configuration | Early; Gold; At least one | **COM**: Retail and commerce &gt; Channel setup &gt; Call center setup &gt; Payment methods <br><br> **DMF**: *RetailTenderType*, *RetailStoreTenderType* |
| [Check hold parameters](/dynamicsax-2012/appuser-itpro/set-up-payment-methods-call-center#3-set-parameters-for-call-center-payments) | Initialize; Fundamental; Configuration | Early; Gold; At least one | **COM**: Retail and commerce &gt; Channel setup &gt; Call center setup &gt; Call center parameters <br><br> **DMF**: N/A |
| [Create sales orders with check payments](/dynamics365/commerce/tasks/create-call-center-orders) | Operate; Optional; Operational | | **COM**: Sales and marketing &gt; Sales orders &gt; All sales orders <br><br> **DMF**: *SalesOrderV3* |
| Create free text invoices with check payments | Operate; Optional; Operational | | **COM**: Accounts receivable &gt; Invoices &gt; All free text invoices <br><br> **DMF**: N/A|
| [Manage check holds](/dynamicsax-2012/appuser-itpro/handle-payment-issues#1-release-a-check-hold) | Operate; Optional; Operational | | **COM**: COM: Retail and commerce &gt; Channels &gt; Call centers &gt; Check holds <br><br> **DMF**: N/A |

### Credit limit workbench

(Commerce – Call center)

Use this option when you use a Call center channel with Dynamics 365 Commerce and need to prevent a Sales order or Free text invoice from being processed when customer balance is exceeding the limits you define. This option does not work for Project invoices, and it does not work in combination with the Credit holds option.

| Process step | Process stage | Process modifiers | App, navigation, and entity |
|---|---|---|---|
| [Basic credit limit checking](#basic-credit-limit-checking) |  |  |See the section above for the prerequisites. | 
| Enable on account payments for customers | Design; Configuration; Optional | Gold; Continuous | **COM**: Sales and marketing &gt; Customers &gt; All customers <br><br> **DMF**: CustomersV3 |
| [Enable customer account payment method in Commerce site builder](/dynamics365/commerce/b2b/payment-method#enable-the-customer-account-payment-method-in-commerce-site-builder) | Develop; Configuration; Optional | | **CSB**: Site setting &gt; Extensions <br><br> **DMF**: N/A |
| [Enable the customer account payment method on the checkout page for the B2B e-commerce site](/dynamics365/commerce/b2b/payment-method#enable-the-customer-account-payment-method-on-the-checkout-page-for-the-b2b-e-commerce-site) | Develop; Configuration; Optional | | **CSB**: Checkout page <br><br> **DMF**: N/A |
| [Create call center orders with on account payments](/dynamicsax-2012/appuser-itpro/apply-payments-in-sales-orders#1-use-a-cash-check-card-or-customer-account-payment-in-a-sales-order) | Operate; Optional; Operational | | **COM**: Sales and marketing &gt; Sales orders &gt; All sales orders <br><br> **DMF**: SalesOrderV3 |
| [Manage call center orders over the credit limit](/dynamicsax-2012/appuser-itpro/handle-payment-issues#4-process-orders-that-are-on-hold-because-of-credit-limits) | Operate; Optional; Operational |  | **COM**: Retail and commerce &gt; Channels &gt; Call centers &gt; Credit limits <br><br> **DMF**: N/A |

## Next steps

After you have completed the basic setup and configuration for setting customer credit limits in Dynamics 365, consider the following other steps and actions to take.

1. Set customer credit limits <-- You are currently on this step.

2. Update customer credit limits

3. Block or close customer accounts

4. Handle non-sufficient fund (NSF) payments from customers

5. Process customer account statements

6. Dispute and resolve invoice discrepancies

7. Process and write-off bad debts

8. Create and process interest notes

9. Create and process collection letters

10. Detect fraudulent orders

## Related patterns

The following patterns are available to help guide your implementation of the set customer credit limits business process.

- [Manually set customer credit limits](pattern-manually-set-check-customer-credit-limits.md)
- [Set customer credit limits for a group of customers](pattern-set-customer-credit-limits-for-group-of-customers.md)

## Related resources

Use the following resources to learn more about the processes for setting customer credit limits in Dynamics 365.

- [Update customer risk scores.](/dynamics365/finance/accounts-receivable/cm-periodic-tasks#update-risk-scores)

- [Update customer balance statistics.](/dynamics365/finance/accounts-receivable/cm-periodic-tasks#update-customer-balance-statistics)

- [Collect on overdue payments.](/dynamics365/finance/accounts-receivable/cm-collections-concepts)

- [Blog post: Dynamics 365 Finance Credit Management](https://community.dynamics.com/blogs/post/?postid=48627251-aba8-4509-8f69-5c26a9652b59)

- [Configure Accounts receivable and credit and collections](/dynamics365/finance/accounts-receivable/accounts-receivables-set-up-overview)

- [Configure accounts receivable in Dynamics 365 Finance](/training/modules/configure-accounts-receivable-dyn365-finance/)

- [Perform accounts receivable daily procedures in Dynamics 365 Finance](/training/modules/accounts-receivable-daily-procedures-dyn365-finance/)

- [Set up collections](/dynamics365/finance/accounts-receivable/set-up-collections)

- [Configure credit and collections in Dynamics 365 Finance](/training/modules/configure-credit-collections-dyn365-finance/)

- [Process credit and collections in Dynamics 365 Finance](/training/modules/process-credit-collections-dyn365-finance/)

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Rachel Profitt](https://www.linkedin.com/in/rachelprofitt/) | Senior Program Manager, FastTrack for Dynamics 365  

<!--## Tags
*Stakeholders:* Functional consultant, Business analyst, Accounts receivable lead, Finance lead, Sales lead, Operations lead

*Products:* Dynamics 365 Commerce, Dynamics 365 Customer Insights, Dynamics 365 Finance, Dynamics 365 Supply Chain Management
