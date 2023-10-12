---
title: Recognize project revenue overview
description: Learn how you can use Dynamics 365 products to support the organization's business processes to recognize project revenue.
ms.date: 07/27/2023
ms.topic: conceptual
author: edupont04
ms.author: mibeinar
---

# Recognize project revenue overview

***Applies to: Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management***

This article describes how you can use Dynamics 365 products to support an organization's requirements to recognize project revenue.

## Introduction to recognize project revenue

The *recognize project revenue* business process area focuses on project revenue tracking and governing, which helps customers manage costs and grow their business. This process is closely linked to the accurate and timely project work delivery, customer billing, and minimization of the cost incurred during the project. Project revenue recognition principles vary based on the selected billing method for a project or portion of the project. Various billing methods govern revenue recognition in the system, and customers can use these principles to ensure accurate and timely recognition of revenue.

*Recognize project revenue* is an essential step in the [*project to profit* end-to-end business process flow](project-to-profit-overview.md). For project-based organizations, a structured and defined approach that recognizes project revenue is essential to assure control and completion of project work within your organization.

The *recognize project revenue* business process area should be defined and incorporated into the overall implementation during the planning phase. This phase typically occurs at the beginning of a project's lifecycle where you establish project goals, define project scope, and develop a detailed project plan.

## Stakeholders 

Many people across the organization should contribute to the decision-making process and design of the recognize project revenue area. The list includes but isn't limited to the following roles:

- **Project managers**: responsible for managing project billing backlog, estimation, and accruals.

- **Project accountants**/**Accounts receivable clerks**: responsible for creation of revenue posting.

- **Finance department**: responsible for financial supervision, financial project reporting, and analysis.

- **Executive leadership**: responsible for project oversight and alignment with strategic organization's goals, which helps secure the necessary resources and funding.

## Recognize project revenue process flow

The following diagram illustrates the *recognize project revenue* business process area.

Each solid gray rectangle on the diagram represents an end-to-end business process. The solid blue rectangle represents the plan and budget assets business process area. The diagram shows the subprocesses for this business process area. The arrows on the diagram show the business process flow in an organization. If a subprocess can lead to more than one other subprocess, the parallel subprocesses are shown as branches.

:::image type="content" source="media/project-to-profit-recognize-project-revenue-flow.svg" alt-text="Flow diagram for the business process area, process project invoices, which is explained in the paragraph after the image." lightbox="media/project-to-profit-recognize-project-revenue-flow.svg":::

The flow diagram covers the following steps:

1. Start

2. *Record to report end-to-end process*

    Parallel branch of this end-to-end process is *Project to Profit end-to-end process*

    1. *Define ledger structure and currency policies*

    2. *Process project invoices*

    3. *Recognize project revenue*

        1. *Estimate project*

        2. *Review and approve project estimates*

        3. Condition "*Is approved?*"

            1. A parallel branch for **Yes** leads to *Accrue revenue*

            2. A parallel branch for **No** leads to subprocess *Make adjustments to project transactions.*

            Downstream to this subprocess is *Review and approve project estimates*

        4. *Accrue revenue*

        5. Condition "*Is correction needed*?"

            1. A parallel branch for **Yes** leads to *Reverse accrued revenue*

            2. A parallel branch for **No** leads to *Reconcile revenue*

            Downstream to this subprocess is the subprocess *Record financial transactions.*

3. *Project to Profit end-to-end process*

    1. *Deliver project work*

        Parallel branches of this subprocess are subprocesses *Capture project expenses* and *Manage project supply chain.*

    Downstream of these branches are the subprocesses *Process project invoices* and *Recognize project revenue.*

4. End

## Recognize project revenue benefits

There are many key benefits that you can use to monitor and measure the success of implementing technology to support recognizing project revenue. The following sections outline the key benefits that an organization might monitor and measure for recognizing project revenue.

### Multiple project cost and revenue profiles and rules

Dynamics 365 supports various accounting options and rules for billable projects that include time and material and fixed price transactions. Depending on the defined setup, various accounting principles are used when project transactions are journalized and then invoiced. For example, you can configure posting project cost and revenue of your short-term projects directly to the profit and loss accounts and use work in progress (WIP) accounts for your long-term projects.

In addition, project cost and revenue profile rules determine the project cost and revenue profile that you must use when processing billable project transactions. You can define rules by project contract, project group, or by a specific project. Dynamics 365 picks the highest granularity rule first.

Learn more at [Configure accounting for billable projects.](/dynamics365/project-operations/project-accounting/configure-accounting-billable-projects#define-project-cost-and-revenue-profiles)

### Flexible revenue recognition calculation methods and deferred project revenue

In Dynamics 365 solutions with project invoicing, revenue estimates are automatically calculated by period. The estimates are based on the forecast and actual transactions that were entered during the period. Customers can adjust and review these calculations if needed.

Learn more at [Project management and accounting overview](/dynamics365/project-operations/prod-pma/overview-project-management-accounting#create-projects) and [Revenue recognition overview.](/dynamics365/project-operations/revenue-recognition/revenue-recognition-overview)

### Project cashflow reporting

For solutions with Dynamics 365 Project Operations and Dynamics 365 Finance, project cash inflow and outflow are tracked both from actuals and estimates perspectives. Details such as expected payment day and actual payments received are available for reporting.

### Subscription billing 

Subscription billing enables organizations to manage subscription revenue opportunities and recurring billing through billing schedules. An option to have a deferral schedule enables project revenue for the service to be recognized on an event-based template or on a monthly, quarterly, or yearly basis. This approach helps manage revenue for the project as it assures revenue is recognized when it's earned.

Learn more at [Project deferrals](/dynamics365/finance/accounts-receivable/sb-project-deferrals)  

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *recognize project revenue* business processes, use the following resources and steps to learn more. Links are added when articles become available.  

1. [Manage project opportunities](project-to-profit-manage-project-opportunities-overview.md)  

2. Manage project quotations

3. Manage project contracts

4. Govern projects

5. [Manage project scope and schedule](project-to-profit-manage-project-scope-schedule-overview.md)  

6. [Resource a project](project-to-profit-resource-projects.md)  

7. [Deliver project work](project-to-profit-deliver-project-work.md)  

8. [Manage project supply chain](project-to-profit-manage-project-supply-chain-overview.md)  

9. [Capture project expenses](project-to-profit-capture-project-expenses-overview.md)

10. [Process project invoices](project-to-profit-process-project-invoices-overview.md)  

11. *Recognize project revenue*  (the article you're currently reading)      

12. Make adjustments to project transactions

13. Manage project budgets

14. Monitor and analyze project performance

15. Return to the overview of business process areas at [Project to profit business process areas](project-to-profit-areas.md)   

## Related resources

You can use the following resources to learn more about the *recognize project revenue* process in Dynamics 365.

- [Project deferrals](/dynamics365/finance/accounts-receivable/sb-project-deferrals)  

- [Project management and accounting overview](/dynamics365/project-operations/prod-pma/overview-project-management-accounting#create-projects)  

- [Revenue recognition overview](/dynamics365/project-operations/revenue-recognition/revenue-recognition-overview)  

- [Financial estimation concepts](/dynamics365/project-operations/project-management/estimating-projects-overview)  

- [Project estimates and actuals integration](/dynamics365/project-operations/environment/resource-dual-write-estimates-actuals)  

- [Accruals overview](/dynamics365/finance/general-ledger/accruals-overview)  

- [Invoicing, revenue recognition and project accounting capabilities in Dynamics 365 Project Operations (video)](https://community.dynamics.com/videos/post/?postid=ceea402b-61e0-4b56-a2bc-1db04d0942e7)  

- Find definitions of terminology used in content for *recognize project revenue* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article, including the following terms:

  - [Project type](glossary.md#project-type)  
  - [Fixed-price projects](glossary.md#fixed-price-projects)  
  - [Time and material projects](glossary.md#time-and-material-projects)  
  - [Accruals](glossary.md#accruals)  
  - [Deferrals](glossary.md#deferrals)  
  - [Billing schedules](glossary.md#billing-schedules)  

<!--## Tags

*Stakeholders*: Accounts receivable, Audit, Customer services, Finance, IT, Operations, Project Management, Sales, Service operations

*Products*: Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management-->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Milda Beinaryte](https://www.linkedin.com/in/beimilda/) | FastTrack Solution Architect  
