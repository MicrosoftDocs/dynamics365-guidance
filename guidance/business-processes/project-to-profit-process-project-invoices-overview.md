---
title: Process project invoices overview
description: Learn how you can use Dynamics 365 products to support the organization's business processes to manage project invoices.
ms.date: 07/25/2023
ms.topic: conceptual
author: edupont04
ms.author: mibeinar
---

# Process project invoices overview

***Applies to: Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management***

This article describes how you can use Dynamics 365 products to support the organization's requirements to process project invoices.

## Introduction to process project invoices

The *process project invoices* business process area focuses on managing the invoicing associated with project work. It involves generating invoices according to contractual arrangements, tracking payments, and resolving any billing issues that arise. This business process area is an essential part of the end-to-end business process flow, *[project to profit](project-to-profit-introduction.md)*. It helps organizations issue correct and accurate project invoices that include the necessary details available for reference. It also helps make sure that the invoices are processed on time, which helps guarantee a healthy cash flow for an organization.  

Dynamics 365 supports various different types of projects. However, an option to generate an invoice is only possible for projects that are external (*Time and material* and *Fixed price*). To ensure that invoices are accurate and clear, and the details of the invoice post seamlessly into the general ledger, Dynamics 365 provides built-in tools, including the following list:  

- Posting setup  
- Data validation and validation groups  
- Approval workflows  
- Expense policies  
- Reporting and consistency checks  

Dynamics 365 Project Operations has different deployment options to allow organizations to choose the one that best fits their sales and operational model:

- Dynamics 365 Project Operations integrates seamlessly with Dynamics 365 Supply Chain Management, and customers can use them together in either **stocked** or **non-stocked** scenarios to support* process project invoices* processes.

- For customers using alternative finance solution, the **lite deployment** option allows using Dynamics 365 Project Operations without Dynamics 365 Finance or Dynamics 365 Supply Chain Management.

Learn more at [Determine your deployment type](/dynamics365/project-operations/environment/determine-deployment-type).

For project-based organizations, a structured and defined approach to customer invoicing is essential to prevent financial risks, payment delays and billing challenges. The *process project invoices* business process area should be defined and incorporated into the overall implementation during the plannings phase. This phase typically occurs at the beginning of a project's lifecycle and involves establishing project goals, defining project scope, and developing a detailed project plan.

## Stakeholders

Many people across the organization should contribute to the decision-making process and design of the process project invoices area. The list includes but isn't limited to the following roles:

- **Project managers** – responsible for managing project billing backlog and project budget. Depending on defined organizations' processes, project managers might also be accountable for reviewing and approving project transactions or preparing proforma invoices.

- **Project accountants**/**Accounts receivable clerks** – responsible for creation of complaint and accurate customer-facing invoice documents.

- **Finance department** – responsible for financial supervision, financial project reporting and analysis.

- **Executive leadership** – responsible for project oversight and alignment with strategic organization's goals, which helps in secure the necessary resources and funding.

## Process project invoices process flow

The following diagram illustrates the *process project invoices* business process area.

Each solid gray rectangle on the diagram represents an end-to-end business process. The solid blue rectangle represents the plan and budget assets business process area. The diagram shows the subprocesses for this business process area. The arrows on the diagram show the flow of the business process in an organization. If a subprocess can lead to more than one other subprocess, the parallel subprocesses are shown as branches.

:::image type="content" source="media/project-to-profit-process-project-invoices-flow.svg" alt-text="Flow diagram for the business process area, process project invoices, which is explained in the paragraph after the image." lightbox="media/project-to-profit-process-project-invoices-flow.svg":::

The process project invoices process area flow diagram covers the following steps:

1. Start

2. *Record to report end-to-end process*

    Parallel branch of this end-to-end process is *Project to Profit end-to-end process*

    1. Define ledger structure and currency policies

    2. Process project invoices

        1. Validate transactions to be invoiced

        2. Generate invoice proposals

        3. Review and approve invoice proposal

        4. Condition *Is approved?*

            1. A parallel branch for **Yes** leads to the condition *Is credit note?*

            2. A parallel branch for **No** leads to subprocess *Make adjustments to project transactions.*

            Downstream to this subprocess is *Review and approve invoice proposal*

        5. Condition *Is credit note?*  

            1. A parallel branch for **Yes** leads to *Generate and send credit note*

            2. A parallel branch for **No** leads to *Generate and send invoice*

            Downstream to this subprocess is *Record financial transactions.*

3. *Project to Profit end-to-end process*

    1. Deliver project work

    Parallel branches of this subprocess are subprocesses *Capture project expenses* and*Manage project supply chain.*

    Downstream of these branches is a subprocess, *Process project invoices*.  

4. End

## Process project invoices benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the *process project invoices*. The following sections outline the key benefits that an organization might monitor and measure for processing project invoices.

### Flexible invoice consolidation and control

Dynamics 365 as a technology solution allows invoice consolidation for the projects across the same project contract. Invoice control supports tracking of both invoiced and noninvoiced transactions, and analysis of those transactions against quotations for an end-to-end view of a project. This way, organizations become more flexible in providing the most suitable and preferred billing method for the customers. In addition, an easy option to add or update details, group transactions, customize invoices and manage billing queues assures faster invoice processing and helps with the cash-flow management.

### Efficient invoicing for fixed price projects

Dynamics 365 project invoicing solutions has an option for billing schedules and rules that provides flexibility for fixed-priced projects to be invoiced based on defined terms of one or more milestones. For example, the following customer billing scheduled can be set up:

- 20 percent when the project contract is signed

- 30 percent on first delivery

- 15 percent on second delivery

- 35 percent on final delivery

Learn more at [Billing schedules with projects (Finance)](/dynamics365/finance/accounts-receivable/sb-bill-sched-project).

### Automated invoicing

For organizations that use Dynamics 365 Project Operations and Dynamics 365 Finance, automated invoicing solution provides seamless integration between products. This way, both project and finance users see posted project invoices financial details and perform automatic posting if selected.  

### Flexible deployment types

Depending on your business needs, Dynamics 365 allows flexible deployment types that determine how project invoices are processed:

- *Lite deployment*  

  With this deployment type, users can create proforma invoices for project managers to review and edit.

- *Project Operations for resource/non-stocked scenarios*  

  This deployment type includes both proforma and customer-facing invoicing for projects with nonstock item scenarios.

- *Project Operations for stocked/production order scenarios*  

  This deployment type includes full invoicing for projects with stocked or production order scenarios.  

Learn more about deployment types and determine the most suitable option for your organization at [Determine your deployment type](/dynamics365/project-operations/environment/determine-deployment-type).

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *process project invoices* business processes, use the following resources and steps to learn more. Links are added when articles become available.

1. [Manage project opportunities](project-to-profit-manage-project-opportunities-overview.md)  

2. Manage project quotations

3. Manage project contracts

4. Govern projects

5. [Manage project scope and schedule](project-to-profit-manage-project-scope-schedule-overview.md)  

6. [Resource a project](project-to-profit-resource-projects.md)  

7. [Deliver project work](project-to-profit-deliver-project-work.md)  

8. [Manage project supply chain](project-to-profit-manage-project-supply-chain-overview.md)  

9. [Capture project expenses](project-to-profit-capture-project-expenses-overview.md)

10. *Process project invoices*  (the article you're currently reading)    

11. [Recognize project revenue](project-to-profit-recognize-project-revenue.md)  

12. Make adjustments to project transactions

13. Manage project budgets

14. Monitor and analyze project performance

15. Return to the overview of business process areas at [Project to profit business process areas](project-to-profit-areas.md)   

## Related resources

You can use the following resources to learn more about the *process project invoices* process in Dynamics 365.

- [Dynamics 365 Project Operations - Billing and Invoicing TechTalk](https://community.dynamics.com/blogs/post/?postid=92cfddc1-1dcd-4431-b11a-bac737a9f45e)  

- [Project invoicing (Finance)](/dynamics365/finance/accounts-payable/project-invoicing)  

- [Invoicing process overview (Project Operations)](/dynamics365/project-operations/invoicing/post-project-invoices)  

- [Get started with invoicing in Dynamics 365 Project Operations (training)](/training/modules/get-started-invoicing-project-operations/)  

<!-- ## Tags

*Stakeholders:* Accounts receivable, Audit, Customer services, Finance, IT, Operations, Project Management, Sales, Service operations

*Products:* Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Milda Beinaryte](https://www.linkedin.com/in/beimilda/) | FastTrack Solution Architect  

Contributors:

- [Rachel Profitt](https://www.linkedin.com/in/rachelprofitt/) | FastTrack Solution Architect  
