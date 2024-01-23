---
title: Overview of the manage project financials business process area
description: Learn how you can use Dynamics 365 products to support your organization's business processes to manage project financials.
ms.date: 12/20/2023
ms.topic: conceptual
author: edupont04
ms.author: mibeinar
---

# Manage financial data for project-related activities with the manage project financials process area

***Applies to: Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management***

This article describes how you can use Dynamics 365 products to support your organization's needs for managing project financials. <!--internal comment: This L2 is a consolidated doc of 4 L2's(Process project invoices(already published)+Recognize project revenue(already published)+Manage project budgets+Make adjustments to transactions)-->

## Introduction to manage project financials

The *manage project financials* business process area focuses on managing the financial data associated with project-related activities. It involves generating, processing, and reviewing invoices according to contractual arrangements. It also involves tracking payments, managing project budgets, adjusting project transactions, and recognizing project revenue. The *manage project financials* business process ensures the accuracy of the financial data linked to the project, thereby ensuring a healthy cash flow for your organization.

*Manage project financials* is an essential step in the *project to profit* end-to-end business process flow. Maintaining a structured and well-defined approach to project financial management is critical to prevent financial risks and payment delays. It also helps ensure control and successful completion of project task in your organization.

The *manage project financials* business process should be outlined and incorporated into the overall implementation during the planning phase. Typically occurring at the project's launch, this phase involves setting project goals, defining project scope, and developing a detailed project plan.

## Stakeholders

Various individuals throughout your organization should participate in the design of the *manage project financials* business process. The following list provides examples of such stakeholders:

- **Project manager**: The project manager is responsible for overseeing the entire project. The project manager has the following assigned task:
  - overseeing the project billing backlog
  - managing the project budget
  - handling estimations and accruals
  - overseeing resource allocation and cost tracking
  
  Depending on your organization's processes, a project manager might also be responsible for reviewing and approving project transactions or preparing proforma invoices.

- **Project accountant**/**Accounts receivable clerk**: This individual is responsible for generating precise and accurate customer-facing invoice documents, posting revenue, and reviewing the project's budget.

- **Finance department**: The finance department is tasked with overseeing financial matters, conducting financial project reporting and performing analysis.

- **Executive leadership**: Executives are responsible for project oversight and ensuring alignment with the strategic goals of the organization.

## Manage project financials process flow

The following diagram illustrates the *manage project financials* business process area.

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/project-to-profit-manage-project-financials-flow.svg" alt-text="Flow diagram for the business process area, which is explained in the paragraphs after the image." lightbox="media/project-to-profit-manage-project-financials-flow.svg":::

The *manage project financials* business process area flow diagram covers the following steps:

1. Start

1. *Project to profit* end-to-end process
 (A parallel branch to this process is the *Record to report* end-to-end process.)  

    1. *Define ledger structure and currency policies*

    1. *Manage project financials*

        1. Estimate project

        1. Review and approve project estimates

        1. Condition *Is approved?*

              1. A branch for **Yes** leads to *iv. Manage project budgets*

              1. A parallel branch for **No** leads to subprocess *Adjust estimate*, which connects back to *i. Estimate project*
            <!--Downstream to this sub-process is *i.Estimate project* -->

        1. Manage project budgets

        1. Create project invoices

        1. Record project fees

        1. Allocate project transactions

        1. Condition "Correction required?"

              1. A branch for **No** leads to *ix. Manage and record project revenue*

              1. A parallel branch for **Yes** leads to *Correct project transactions*

            <!-- Downstream to this sub-process is *ix. Manage and record project revenue* -->

        1. Manage and record project revenue

        1. Analyze project transactions

1. *Project to profit* end-to-end process

    1. *Govern projects*

        Parallel branches of this subprocess are:

      - *Manage project contracts*
      - *Manage project contracts*
      - *Manage project resources and  schedules*
      - *Manage project delivery*

        <!-- Downstream of these branches is a subprocess *b.Manage project financials* -->

1. End

## Manage project financials benefits

There are several factors that can be employed to monitor and measure the success of integrating technology to support the management of project financials. The following section outlines the key benefits that an organization might monitor and measure for project financials management.

### Advanced financial and resource management

Advanced project finance management solutions improve financial and resource management for your organization's projects. These tools help project managers identify potential project risks, such as overspending. They also enable project managers to prioritize tasks, track project expenses and allocate resources effectively. Project budget management offers financial transparency, aiding project managers in making informed decisions based on accurate financial data.

Learn more at [Configure accounting for billable projects](/dynamics365/project-operations/project-accounting/configure-accounting-billable-projects#define-project-cost-and-revenue-profiles).  

### Flexible invoice consolidation and control

Top-level project finance management systems enable the consolidation of invoices for projects across the same project contract. Invoice control helps monitor both invoiced and noninvoiced transactions. It also provides an end-to-end view of a project by analyzing such transactions against quotations. The outcome of this business process allows your organization to offer customers the most suitable and preferred billing method. In the end, a streamlined invoice control process ensures faster invoice processing and helps with cash-flow management.

### Efficient and automatic invoicing

Dynamics 365 project invoicing solutions offer flexibility for fixed-priced projects. The tools allow determining invoice creation based on defined terms and milestones using billing schedules and rules. For instance, you can establish the following customer billing schedule:

- 20 percent when the project contract is signed

- 30 percent on first delivery

- 15 percent on second delivery

- 35 percent on final delivery

Learn more at [Billing schedules with projects](/dynamics365/finance/accounts-receivable/sb-bill-sched-project) and [Set up billing rules for project contracts](/dynamicsax-2012/appuser-itpro/set-up-billing-rules-for-project-contracts).

For organizations that use Dynamics 365 Project Operations and Dynamics 365 Finance, automated invoicing solution provides seamless integration between products. This way, both project and finance users see posted project invoices financial details, and they can perform automatic posting if selected.

### Real-time visibility of project's progress and profitability

Successful project financials management relies on:

- flexible project financial tracking
- planned project tasks
- resources
- resource units
- different types and categories of financial transactions

The overall budget's visibility enables you to identify differences between the budgeted and the actual amounts and take proactive measures when necessary. If more budget is allocated to the project, the project manager can revise the budget so that it reflects the new forecasts.

Learn more at [Project management and accounting overview](/dynamics365/project-operations/prod-pma/overview-project-management-accounting#create-projects) and [Revenue recognition overview](/dynamics365/project-operations/revenue-recognition/revenue-recognition-overview).  

### Valuable insights for future projects

Top project management solutions enable financial project forecasting and loading project budget amounts from a forecast model. This feature provides flexibility for enhanced project budgeting and financial management, drawing insights from the history of past projects.

### Transaction adjustment

Adjusting project transactions allows you to correct mistakes in your financial records. Project adjustments are used, for example, to update billable status on a large scale, recalculate cost after a configuration change, or update funding sources.

### Multiple project cost and revenue profiles and rules

Dynamics 365 supports various accounting options and rules for billable projects, including both time and material and fixed-price transactions. Depending on the defined setup, various accounting principles are applied when project transactions are recorded and invoiced. For example, you can set up short-term project costs and revenue to be directly recorded in profit and loss accounts, while using work in progress (WIP) accounts for long-term projects.

In addition, rules for project cost and revenue profiles determine the specific profiles to apply when processing billable project transactions. You can define rules by project contract, project group, or by a specific project. Dynamics 365 always picks the rule with the highest level of detail first.

Learn more at [Configure accounting for billable projects](/dynamics365/project-operations/project-accounting/configure-accounting-billable-projects#define-project-cost-and-revenue-profiles).  

### Flexible revenue recognition and billing

Advanced project invoicing solutions automatically calculate revenue periodically based on the forecast and actual transactions entered during that period. These calculation results can be reviewed and adjusted if needed.

Learn more at [Project management and accounting overview](/dynamics365/project-operations/prod-pma/overview-project-management-accounting#create-projects) and  [Revenue recognition overview](/dynamics365/project-operations/revenue-recognition/revenue-recognition-overview).  

Subscription billing enables organizations to manage subscription revenue opportunities and recurring billing using billing schedules. An option to have a deferral schedule enables project revenue for the service to be recognized either based on an event-based template, or on a monthly, quarterly, or yearly basis. This approach helps manage revenue for the project as it assures revenue is recognized when earned.

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

*Microsoft maintains this article and the following contributors originally wrote it.*

Principal author:

- [Milda Beinaryte](https://www.linkedin.com/in/beimilda) \| FastTrack Solution Architect
