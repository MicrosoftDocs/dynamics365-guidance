---
title: Overview of the record to report end-to-end business process
description:  Learn about the end-to-end business process, from record to report. This article provides a high-level flow diagram and describes the relationship with other processes in Dynamics 365 solutions.
ms.date: 11/10/2023
ms.topic: conceptual
author: edupont04
ms.author: kgiardini
---

# Overview of the record to report end-to-end business process and its relationship to other processes

***Applies to: Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Human Resources, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management***

This article describes the *record to report* end-to-end business process flow and its relationship to other business processes that can be used within Dynamics 365.

## Record to report process relationship

The following diagram shows the relationship of other processes and products/features for the *record to report* process. In some ways, you can think of the *record to report* process as being before and after every process of an organization. For example, you could draw a circle and put all other end to end processes inside of it. For purposes of this diagram, we have created a list of processes and ways that you can use each process in relationship to the sub processes in *record to report*.

:::image type="content" source="media/record-to-report-process.svg" alt-text="Business process relationships with upstream and downstream processes that are explained in the next paragraphs." lightbox="media/record-to-report-process.svg":::

The upstream processes for the *record to report* process include the following.

- **Acquire to dispose**  
  
  This process involves acquiring assets or resources and disposing of them. Before the *record to report* process, the organization needs to have a procurement process in place to acquire assets and a fixed asset management process to track and manage them throughout their lifecycle. In dynamics this is done with the *Procurement and sourcing* module in Dynamics 365 Supply Chain Management and the *Fixed asset* and *Asset leasing* modules in Dynamics 365 Finance.

- **Case to resolution**  
  
  This process involves handling customer or internal inquiries and request and resolving any issues. You can optionally use the *case to resolution* process to help manage requests such as new accounts, financial dimensions, budget requests, and more. For example, in a shared service finance operation, the local companies may request chart of account changes from the corporate or shared service office.

- **Forecast to plan**  
  
  This process involves forecasting demand and creating production plans. Before the *record to report* process, the organization needs to have a sales and operations planning process in place to forecast demand and create production plans. You can optionally use a feature to transfer the demand and supply forecasts in Dynamics 365 Supply Chain Management to the budget in Dynamics 365 Finance.

- **Hire to retire**  
  
  This process involves managing employee lifecycles, from hiring to retirement. Before the *record to report* process, the organization needs to have a human resources process in place to manage employee data and a payroll process to calculate and disburse salaries and benefits. When you use Dynamics 365 Human Resources with Finance, there are multiple integration points with compensation, benefits, leave and absence, and payroll.

- **Inventory to deliver**  
  
  This process involves managing inventory levels and fulfilling customer orders. Before the *record to report* process, the organization needs to have a supply chain process in place to manage inventory levels and a sales process to fulfill customer orders. Most organizations who use Dynamics 365 Supply Chain Management will configure the chart of accounts at a minimum in order to allow the inventory transactions and sub ledger provide more robust reporting. All inventory transactions are designed to automatically post to the general ledger, although this can be turned off for some or all products and services.

- **Order to cash**  
  
  This process involves managing customer orders and receiving payment. Before the *record to report* process, the organization needs to have a sales process in place to manage customer orders and an account receivable process to receive payment. Sales orders are designed to post to the general ledger automatically when you deliver or invoice the sales orders.

- **Plan to produce**  
  
  This process involves planning and executing production processes. Before the *record to report* process, the organization needs to have a manufacturing process in place to plan and run production processes. Production, batch, and kanban orders in Dynamics 365 Supply Chain Management are designed to post to the general ledger automatically when you pick, report as finished, and end the orders, for example.

- **Procure to pay**:  

    This process involves managing the procure-to-pay cycle, including procurement, invoicing, and payments. Before the *record to report* process, procurement and invoice management should be established to support the *record to report* process. Purchase orders in Dynamics 365 Supply Chain Management are designed to post to the general ledger automatically when you receive or invoice the order. You can also optionally configure purchase requisitions to post pre-encumbrances, and purchase order confirmations to post encumbrances automatically into the general ledger.

- **Project to profit**:  

    Project to profit is an upstream process that involves managing project lifecycle from project initiation to project completion. Before the *record to report* process in Dynamics 365, the organization needs to set up project management structures, define project budgets, and monitor project progress to ensure accurate cost accounting and revenue recognition. Project transactions including time, hours, expenses, and fees are designed to automatically post to the general ledger.

- **Service to cash**:  

    Service to cash is another upstream process that involves managing the service delivery process, from scheduling services to billing and cash collection. Before the *record to report* process in Dynamics 365, the organization needs to set up service management structures, define service pricing and billing rules, and manage service contracts to ensure accurate service billing and revenue recognition.

The *record to report* end-to-end process is broken down into the following business process areas:

- Define financial structure and organizational accounting policies

- Manage budgets

- Maintain and manage cash and bank transactions

- Record financial transactions

- Close financial periods
<!-- removed???
- Report and analyze financial and cash flow -->

- Comply with tax, audit, and regulatory requirements

- Manage fund accounting

Learn more at [Record to report business process areas](record-to-report-areas.md).

The downstream processes for the *record to report* process include the following.

- **Acquire to dispose**:  

    Acquire to dispose is a downstream process that involves managing the complete lifecycle of assets, from acquisition to disposal. After you have defined the chart of accounts and other settings in *record to report* end-to-end process, the organization needs to track and manage asset-related transactions such as depreciation, maintenance, and retirement. Each of these transactions typically posts into the general ledger for financial reporting.

- **Case to resolution**  

    Case to resolution is another downstream process that involves managing customer or internal issues and request from initial intake to final resolution. You can use the case to resolution process to help manage issues with posted transactions, perform internal audits, or to help manage external audits after financial statements are finalized, as a few examples.

- **Forecast to plan**:  

    Forecast to plan is a downstream process that involves using forecasting data to create production plans and schedules. After you have transferred the demand and supply forecasts to the budget, the organization needs to convert forecasted demand into actionable production plans, and manage inventory levels to meet customer demand. The record report process will continue when you analyze the budgets to actuals.

- **Hire to retire**:  

    Hire to retire is a downstream process that involves managing employee lifecycle from hiring to retirement or termination. After the chart of accounts is designed and budgets are set, the organization needs to manage employee-related transactions such as payroll, benefits, and retirement plans. The *record to report* process continues when the transactions are recorded and you begin to analyze and report on the financial transactions.

- **Inventory to deliver**:  

    Inventory to deliver is another downstream process that involves managing the complete inventory lifecycle from receiving raw materials to delivering finished goods to customers. After the you have defined the chart of accounts and started posting transactions, the organization needs to manage inventory levels, track inventory movement, and fulfill customer orders.

- **Order to cash**:  

    Order to cash is a downstream process that involves managing the complete sales order lifecycle from order creation to cash receipt. After the *record to report* end-to-end process, the organization needs to fulfill customer orders, generate invoices, and manage accounts receivable to ensure timely cash collection.

- **Plan to produce**:  

    Plan to produce is a downstream process that involves converting production plans into actual production activities. After the *record to report* end-to-end process, the organization needs to manage production activities, monitor production progress, and track production costs.

- **Procure to pay**:  

    Procure to pay is another downstream process that involves managing the complete procurement lifecycle from requisition to payment. After the *record to report* end-to-end process, the organization needs to manage procurement activities, receive goods and services, process vendor invoices, and manage accounts payable.

- **Project to profit**:  

    Project to profit is a downstream process that involves tracking project progress and profitability. After the *record to report* end-to-end process, the organization needs to analyze project costs and revenues, manage project budgets, and ensure that projects are profitable.

- **Service to cash**:  

    Service to cash is another downstream process that involves managing service delivery, from scheduling services to billing and cash collection. After the *record to report* end-to-end process, the organization needs to manage service contracts, track service delivery, and generate accurate service invoices to ensure timely cash collection.

## Featured capabilities

There are product specific capabilities offered that interact with the *record to report* process including, but not limited to, the following:

- Financial analytical reporting

- Cash flow forecasting

- Financial period close workspace

- Fund accounting

- Budget planning

## Record to report business process flow

The following diagram shows the high-level flow of the *record to report* business process. [!INCLUDE [daf-business-process-e2e-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-e2e-flow-def.md)]

:::image type="content" source="media/record-to-report-flow.svg"  lightbox="media/record-to-report-flow.svg" alt-text="Flow diagram for the end-to-end business process, which is explained in the paragraphs after the image.":::

The following steps are illustrated in the *record to report* end-to-end business process flow diagram.

1. [Forecast to plan](forecast-to-plan-overview.md)  

2. [Hire to retire](hire-to-retire-overview.md)  

3. [Acquire to dispose](acquire-to-dispose-overview.md)  

4. [Inventory to deliver](inventory-to-deliver-overview.md)  

5. [Order to cash](order-to-cash-overview.md)  

6. [Plan to produce](plan-to-produce-overview.md)  

7. [Procure to pay](procure-to-pay-overview.md)  

8. [Project to profit](project-to-profit-overview.md)  

9. [Service to cash](service-to-cash-overview.md) 

10. [Case to resolution](case-to-resolution-overview.md)  

11. *Record to report*

    1. Parallel branches

        1. *Define the financial ledger structure and organizational accounting policies*

            1. *Manage budgets*

        2. *Comply with tax, audit, and regulatory requirements*

            1. *Manage fund accounting*

    2. *Record financial transactions*

    3. *Maintain cash and bank management transactions*

    4. *Close financial periods*

    5. *Report and analyze financials and cash flow*

12. *Case to resolution*

13. *Acquire to dispose*

14. *Service to cash*

15. *Inventory to deliver*

16. *Order to cash*

17. *Plan to produce*

18. *Procure to pay*

19. *Project to profit*

20. *Forecast to plan*

21. *Hire to retire*

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *record to report* business processes, use the following resources and steps to learn more.

- Define the goals and objectives of implementing an *record to report* technology solution. Learn more at [Implementation strategy](../implementation-guide/implementation-strategy.md).  

- Define the business process scope of your project. Learn more at [Process-focused solution](../implementation-guide/process-focused-solution.md).  

- Get a demo of Dynamics 365 solutions for the *record to report* process. Learn more at [Request a demo](https://dynamics.microsoft.com/)

- Sign up for a trial of Dynamics 365. Learn more at [Start a Free Trial for Microsoft Dynamics 365](https://dynamics.microsoft.com/dynamics-365-free-trial/)

## Related resources

You can use the following resources to learn more about the *record to report* process in Dynamics 365.

- [Record to report business process areas](record-to-report-areas.md)  
- [Financial reporting overview - Finance](/dynamics365/finance/general-ledger/financial-reporting-getting-started)  
- [Financial Reports and Analytics in Business Central](/dynamics365/business-central/finance-reports)  
