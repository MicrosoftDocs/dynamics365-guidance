---
title:  Record to report business process areas
description: Get an overview for each of the business process areas in the record to report end-to-end business process flow in Dynamics 365 solutions.
ms.date: 04/05/2023
ms.topic: conceptual
author: edupont04
ms.author: kgiardini
---

# Record to report business process areas

***Applies to: Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Human Resources, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management***

The *record to report* process is broken down into many business process areas. The following sections describe the business process areas.

## Define the ledger and currency policies

This business process area involves setting up the organization structure, creating and maintaining companies, and defining the chart of accounts. In Dynamics 365 Finance, legal entities are a core configuration to use any functionality. The organizational hierarchy supports flexible and date-effective configuration to match your business needs. The configuration is used throughout Finance, Supply Chain Management, Commerce, Human Resources, and Project Operations. The chart of account is flexible and supports shared or unique charts for each ledger. This way, you gain the flexibility to meet the unique requirements of your organization across the globe.

As part of the structure and configuration there's also the need to manage currencies, exchange rates, and exchange rate providers to support financial transactions and reporting. Dynamics 365 Finance includes APIs to easily import exchange rates from OANDA or another provider. With the ability to track transactions in any currency and convert them to any other currency for the ledger and a second currency for reporting in real-time. Balances throughout the system can be updated automatically using quick and easy to use tools in multiple currencies.

## Manage budgets

This business process area involves creating, managing, and monitoring budgets to support financial planning and control. Dynamics 365 Finance includes robust [budgeting capabilities](/dynamics365/finance/budgeting/budgeting-overview) to help you if you need basic budgeting, or if you manage your budget externally and want to report actuals against budget, and also for public sector organizations. Finance has advanced budgeting features such as the following capabilities:

- Budget control to prevent budget overruns during transactions  
- Robust planning tools including budget apportionments  
- Automatic pre-encumbrance and encumbrance tracking  

Finance also includes AI-driven planning tools to help you create your budget and workflow to help you manage the process of finalizing and approving the budget.

In addition to the robust budgeting capabilities of Finance, there are also budgeting capabilities available in other Dynamics 365 apps that integrate seamlessly with Finance. The following list includes several examples of other budgeting features available:

- *Position forecasting* in Dynamics 365 Human Resources to budget headcount and related expenses.

- *Fixed asset budgeting* in Dynamics 365 Finance to help you manage your fixed assets costs, including estimated depreciation expenses.

- *Project budgeting* in Dynamics 365 Project Operations to help you plan project costs, monitor and control actuals at a project level, and more.

- Dynamics 365 Supply Chain Management includes robust forecasting functionality for demand and supply that can both be converted to general ledger budgets.

## Maintain and manage cash and bank transactions

This business process area involves managing cash and bank transactions, including bank account reconciliations, cash management, and bank statement processing. The Cash and bank management module in Dynamics 365 Finance supports various payment types and includes bank reconciliation functionality to help automate the month-end activities.

## Record financial transactions

This business process area involves recording financial transactions, including general ledger transactions, allocations, deferrals, and accruals, just to name a few. With the configurable workflow engine available out of the box, you can design your business process flow and approvals to match your business requirements.

## Close financial periods

This business process area involves posting and finalizing transactions in each of the sub ledgers. It also includes recording accruals and deferrals, performing currency revaluations and reconciliations of the subledgers to the general ledger. After reconciliation occurs, you can consolidate and eliminate transactions when you've more than one legal entity with requirements for consolidated financial reporting. There's also support for periodic processes such as year-end close and the preparation for a financial audit.

## Report and analyze financials and cash flow

This business process area involves monitoring and analyzing cash flow to optimize cash management and support financial planning and forecasting. Dynamics 365 Finance Insights includes AI-driven automation to create cash flow forecasts that you can compare to snapshots and actuals. This automation makes the job of analyzing your cash flow easier.

In addition to cash flow reporting, there's a need to review financial transactions and prepare financial statements, including balance sheets, and income statements. The results are then analyzed by looking at the financial results, including variance analysis, trend analysis, and financial reporting. When you use budgeting features, this process also includes the comparison of budgets to actuals.

## Comply with tax, audit, and regulatory requirements

This business process area involves complying with audit and regulatory requirements, including financial reporting, tax compliance, and internal controls. It often includes managing the security of your financial records and validation of the segregation of duties. Using the *Audit workbench*, you can manage audit cases and request through the resolution process. You can also use archival features to help manage the data retention policies of your organization.

It also covers the need to design and implement statutory, tax, and localization requirements, including tax reporting, VAT, and legal reporting requirements. Dynamics 365 Finance includes a wide-ranging tax engine to calculate and manage various different taxes including, but not limited to sales tax, use tax, withholding tax, value added taxes, and more. Dynamics 365 Finance includes more than 40 localizations. For a complete list of countries/regions and languages supported, see [Globalization resources](/dynamics365/fin-ops-core/dev-itpro/lcs-solutions/country-region).

## Manage fund accounting

In most public sector organizations, there's a requirement to track, manage, and report financials by funds. Dynamics 365 Finance includes comprehensive functionality to support the public sector in this process. This business process area involves managing fund accounting, including fund structures, fund accounting rules, and fund reporting. It also includes more capabilities and processes to support appropriations, [ledger settlements](/dynamics365/finance/general-ledger/ledger-settlements), and an extra process for closing financial periods specific to fund accounting<!--Eva: I have no idea what this last clause is supposed to mean, but I rewrote it to make some level of sense-->.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *record to report* business processes, learn more at the following resources and steps.

- [Record to report introduction](record-to-report-introduction.md)

- [Record to report end-to-end overview](record-to-report-overview.md)

<!--## Related resources

You can use the following resources to learn more about the *record to report* process in Dynamics 365.

- TechTalk link here

- Docs article link here

- GitHub sample link here

- Other links-->

<!--## Tags
*Stakeholders:* Functional consultant, Business analyst, Controller, CFO, Finance leads

*Products:* Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Human Resources, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management
