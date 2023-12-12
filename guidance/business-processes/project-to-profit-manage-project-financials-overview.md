---
title: Manage project financials overview
description: Learn how you can use Dynamics 365 products to support the organization's business processes to manage project financials.
ms.date: 11/17/2023
ms.topic: conceptual
author: edupont04
ms.author: mibeinar
---

# Manage project financials overview

***Applies to: Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management***

This article describes how you can use Dynamics 365 products to support organization's requirements to manage project financials. <!--internal comment: This L2 is a consolidated doc of 4 L2's(Process project invoices(already published)+Recognize project revenue(already published)+Manage project budgets+Make adjustments to transactions)-->

## Introduction to manage project financials

The *manage project financials* business process area focuses on managing the financial data associated with the project work. It involves generating, processing, and reviewing invoices according to contractual arrangements. It also involves tracking payments, managing project budgets, adjusting project transactions, and recognizing project revenue. *Manage project financials* helps make sure the organization has correct and accurate project financial data associated with the project, which helps guarantee healthy cash flow for an organization, timely recognition of revenue, and effective planning.

*Manage project financials* is an essential step in the *project to profit* end-to-end business process flow. For project-based organizations, a structured and defined approach to managing project financials is critical to prevent financial risks and payment delays. It also helps ensure control and completion of project work within the organization.

The *manage project financials* business process area should be defined and incorporated into the overall implementation during the plannings phase. This phase typically occurs at the beginning of a project's lifecycle and involves establishing project goals, defining project scope, and developing a detailed project plan.

## Stakeholders 

Many people across the organization should contribute to the decision-making process and design of the manage project invoices area. The following list provides examples of such stakeholders:

- **Project managers** – responsible for managing project billing backlog and project budget, estimation and accruals, resource allocation and cost tracking. Depending on defined organizations' processes, project managers might also be accountable for reviewing and approving project transactions or preparing proforma invoices.

- **Project accountants**/**Accounts receivable clerks** – responsible for creation of complaint and accurate customer-facing invoice documents, revenue posting and review of project budget and reporting preparation (actual vs. forecasted, expenses. costs, and so on).

- **Finance department** – responsible for financial supervision, financial project reporting and analysis.

- **Executive leadership** – responsible for project oversight and alignment with strategic organization's goals, which helps in secure the necessary resources and funding.

## Manage project financials process flow

The following diagram illustrates the *manage project financials* business process area.

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/project-to-profit-manage-project-financials-flow.svg" alt-text="Flow diagram for the business process area, which is explained in the paragraphs after the image." lightbox="media/project-to-profit-manage-project-financials-flow.svg":::

The *manage project financials* business process area flow diagram covers the following steps:

1. Start

2. *Project to profit* end-to-end process

    A parallel branch to this end-to-end process is the *Record to report* end-to-end process  

    1. *Define ledger structure and currency policies*

    2. *Manage project financials*

        1. Estimate project

        2. Review and approve project estimates

        3. Condition *Is approved?*

              1. A branch for **Yes** leads to *iv. Manage project budgets*

              2. A parallel branch for **No** leads to subprocess *Adjust estimate*, which connects back to *i. Estimate project*
        <!--Downstream to this sub-process is *i.Estimate project* -->

        4. Manage project budgets

        5. Create project invoices

        6. Record project fees

        7. Allocate project transactions

        8. Condition "Correction required?"

              1. A branch for **No** leads to *ix. Manage and record project revenue*

              2. A parallel branch for **Yes** leads to *Correct project transactions*

        <!-- Downstream to this sub-process is *ix. Manage and record project revenue* -->

        9. Manage and record project revenue

        10. Analyze project transactions

3. *Project to profit* end-to-end process

    1. *Govern projects*

    Parallel branches of this subprocess are the subprocesses *Manage project contracts*, *Manage project resources and schedules*, and *Manage project delivery*

    <!-- Downstream of these branches is a subprocess *b.Manage project financials* -->

4. End

## Manage project financials benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the management of project financials. The following sections outline the key benefits that an organization might monitor and measure for project financials management.

### Advanced financial and resource management

A project budget can be created for all types of projects. Advanced project finance management solutions improve financial and resource management for various types of your organization's projects by helping project managers identify potential project risks, such as overspending and ineffective management of costs, and take action to mitigate them. It also enables them to prioritize tasks, track project expenses and allocate resources effectively. Project budget management allows financial transparency that contributes to fact-based decision-making by providing project managers with accurate financial data and an effective way to monitor project progress.

Learn more at [Configure accounting for billable projects](/dynamics365/project-operations/project-accounting/configure-accounting-billable-projects#define-project-cost-and-revenue-profiles).  

### Flexible invoice consolidation and control

Leading project finance management systems allow invoice consolidation for the projects across the same project contract. Invoice control supports tracking of both invoiced and non-invoiced transactions, and analysis of those transactions against quotations for an end-to-end view of a project. This allows organizations to be more flexible in providing the most suitable and preferred billing method for the customers. In addition, an easy option to add or update details, group transactions, customize invoices and manage billing queues, ensure faster invoice processing, and helps with cash-flow management.

### Efficient and automatic invoicing

Dynamics 365 project invoicing solutions has an option for billing schedules and rules that provides flexibility for fixed-priced projects to be invoiced based on defined terms of one or more milestones. For example, the following customer billing scheduled can be set up:

- 20 percent when the project contract is signed

- 30 percent on first delivery

- 15 percent on second delivery

- 35 percent on final delivery

Learn more at [Billing schedules with projects](/dynamics365/finance/accounts-receivable/sb-bill-sched-project) and [Set up billing rules for project contracts](/dynamicsax-2012/appuser-itpro/set-up-billing-rules-for-project-contracts).

For organizations that use Dynamics 365 Project Operations and Dynamics 365 Finance, automated invoicing solution provides seamless integration between products. This way, both project and finance users see posted project invoices financial details, and they can perform automatic posting if selected.

### Real-time visibility of project's progress and profitability

Successful project financials management relies on flexible project financial tracking for various project budgets, your planned project tasks, resources, resource units, and different types and categories of financial transactions. The visibility of overall budget based on these areas, and the ability to track, amend, and automatically match project actuals against budgeted amounts, allows you to see variants between budgeted and actual amount and take proactive actions where possible. If more budget is allocated to the project, or if the contract is updated based on spending, the project manager can revise the budget so that it reflects the new forecasts.

Learn more at [Project management and accounting overview](/dynamics365/project-operations/prod-pma/overview-project-management-accounting#create-projects) and [Revenue recognition overview](/dynamics365/project-operations/revenue-recognition/revenue-recognition-overview).  

### Valuable insights for future projects

Leading project management solutions allow financial project forecasting and project budget amount loading from a forecast model. This feature gives flexibility to improved project budgeting and financial management based on other projects history.

### Transaction adjustment

Project transaction adjustment gives the possibility to correct mistakes in your financial books. Project adjustments are used, for example, to mass-update the billable status, recalculate cost after a configuration change, or update funding sources.

### Multiple project cost and revenue profiles and rules

Dynamics 365 supports various accounting options and rules for billable projects that include time and material and fixed price transactions. Depending on the defined setup, various accounting principles are used when project transactions are journalized and then invoiced. For example, you can configure posting project cost and revenue of your short-term projects directly to the profit and loss accounts, and use work in progress (WIP) accounts for your long-term projects.

In addition, project cost and revenue profile rules determine the project cost and revenue profile that must be used when processing any billable project transactions. You can define rules by project contract, project group, or by a specific project. Dynamics 365 always picks the rule with the highest granularity first.

Learn more at [Configure accounting for billable projects](/dynamics365/project-operations/project-accounting/configure-accounting-billable-projects#define-project-cost-and-revenue-profiles).  

### Flexible revenue recognition and billing

Advanced project invoicing solutions support automatic revenue estimates calculation on a period basis based on the projects forecast and actual transactions entered over the period. These calculation results can be reviewed and adjusted if needed.

Learn more at [Project management and accounting overview](/dynamics365/project-operations/prod-pma/overview-project-management-accounting#create-projects) and  [Revenue recognition overview](/dynamics365/project-operations/revenue-recognition/revenue-recognition-overview).  

Subscription billing enables organizations to manage subscription revenue opportunities and recurring billing through billing schedules. An option to have a deferral schedule enables project revenue for the service to be recognized on an event-based template, or on a monthly, quarterly, yearly basis. This approach helps manage revenue for the project as it assures revenue is recognized when it's earned.

Learn more at [Project deferrals](/dynamics365/finance/accounts-receivable/sb-project-deferrals).  

### Advanced reporting

For organizations that use Dynamics 365 Project Operations and Dynamics 365 Finance, project cash inflow and outflow are tracked both from actuals and estimates. Details such as the expected payment day and actual payments received are available for reporting.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *manage project financials* business processes, you can use the following resources and steps to learn more.

1. [Govern projects](project-to-profit-govern-projects-overview.md)  
2. [Manage project contracts](project-to-profit-manage-project-contracts-overview.md)  
3. [Manage project resources and schedule](project-to-profit-manage-project-scope-schedule-overview.md)  
4. [Manage project delivery](project-to-profit-deliver-project-work.md)  
5. *Manage project financials*. (The article you're currently reading.)
6. [Monitor and analyze project performance](project-to-profit-monitor-analyze-project-performance-overview.md)  

## Related resources

You can use the following resources to learn more about the manage project financials process in Dynamics 365.

- Find definitions of terminology used in content for *Manage project opportunities* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article, including the following terms:

  - [Project manager](glossary.md#project-manager)  
  - [Project controller](glossary.md#project-controller)  
  - [Project type](glossary.md#project-type)  
  - [Fixed-price projects](glossary.md#fixed-price-projects)  
  - [Project contract](glossary.md#project-contract)  
  - [Billing rules](glossary.md#billing-rules)  
  - [Billing schedules](glossary.md#billing-schedules)  
  - [Funding source](glossary.md#funding-source)  
  - [Project budget](glossary.md#project-budget)  
  - [Cost budget](glossary.md#cost-budget)  
  - [Revenue budget](glossary.md#revenue-budget)   
  - [Budget forecast](glossary.md#budget-forecast)  
  - [Project estimate](glossary.md#project-estimate)  
  - [Correcting entry](glossary.md#correcting-entry)  
- [Dynamics 365 Project Operations - Billing and Invoicing \| August 9-10, 2022 - Microsoft Dynamics Blog](https://community.dynamics.com/blogs/post/?postid=92cfddc1-1dcd-4431-b11a-bac737a9f45e)  

- [Project invoicing (Finance)](/dynamics365/finance/accounts-payable/project-invoicing)  

- [Invoicing process overview (Project Operations)](/dynamics365/project-operations/invoicing/post-project-invoices)  

- [Get started with invoicing in Dynamics 365 Project Operations (Training)](/training/modules/get-started-invoicing-project-operations/)  

- [Project budget management overview (Project Operations)](/dynamics365/project-operations/pro/budget/projectbudgetmanagement)  

- [Project forecasts and budgets (Project Operations)](/dynamics365/project-operations/prod-pma/project-forecasts-budgets)  

- [Revise a project cost budget (Project Operations)](/dynamics365/project-operations/pro/budget/revise-project-cost-budget)  

- [Project adjustments (Project Operations)](/dynamics365/project-operations/project-accounting/project-adjustments) 

- [Create and confirm entry journals (Project Operations)](/dynamics365/project-operations/actuals/create-confirm-entry-journals)  

- [Create and confirm correction journals (Project Operations)](/dynamics365/project-operations/actuals/create-confirm-correction-journals) 

- [Project deferrals](/dynamics365/finance/accounts-receivable/sb-project-deferrals)  

- [Project management and accounting overview (Project Operations)](/dynamics365/project-operations/prod-pma/overview-project-management-accounting#create-projects)  

- [Revenue recognition overview (Project Operations)](/dynamics365/project-operations/revenue-recognition/revenue-recognition-overview)  

- [Financial estimation concepts (Project Operations)](/dynamics365/project-operations/project-management/estimating-projects-overview)  

- [Project estimates and actuals integration (Project Operations)](/dynamics365/project-operations/environment/resource-dual-write-estimates-actuals)  

- [Accruals overview (Finance)](/dynamics365/finance/general-ledger/accruals-overview)  

- [Invoicing, revenue recognition and project accounting capabilities in Dynamics 365 Project Operations](https://community.dynamics.com/videos/post/?postid=ceea402b-61e0-4b56-a2bc-1db04d0942e7)

<!-- ## Tags

*Stakeholders:* Accounts receivable, Audit, Customer services, Finance, IT, Operations, Project Management, Sales, Service operations

*Products:* Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply chain management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Milda Beinaryte](https://www.linkedin.com/in/beimilda) \| FastTrack Solution Architect
