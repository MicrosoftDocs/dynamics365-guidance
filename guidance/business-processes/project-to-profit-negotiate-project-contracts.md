---
title: Negotiate Project Contracts in Dynamics 365  
description: Learn how to effectively negotiate project contracts using Dynamics 365, including steps, best practices, and stakeholder roles.  
author: edupont04  
contributors:  
ms.topic: concept-article 
ms.date: 07/09/2025
ms.author: edupont  
ms.reviewer: edupont  
---

# Negotiate project contracts

***Applies to:*** ***Dynamics 365 Project Operations***

This article provides a guide on using Dynamics 365 to *negotiate project contracts*, detailing the steps and best practices for effective contract negotiation. It's based on a business process that is part of the [Manage project contracts](project-to-profit-manage-project-contracts-overview.md) business process area in the [Project to profit end-to-end scenario](project-to-profit-overview.md).  

In today's competitive business environment, having a streamlined and efficient contract negotiation process is crucial. This process ensures that all contractual terms are clearly defined and agreed upon by all parties involved, reducing the risk of disputes and fostering strong business relationships. Dynamics 365 offers powerful tools that enable businesses to manage these negotiations effectively, ensuring transparency and compliance.

The *negotiation of project contracts* should be defined at the initial stages of a business solution. This business process is closely linked with other processes such as procurement, sales, and project management. Therefore, understanding how contract negotiation will be handled in Dynamics 365 can significantly influence the configuration and customization of related modules, ensuring a seamless integration and efficient workflow.

## Negotiate project contracts stakeholders

Defining project billing terms involves several key stakeholders, each playing a crucial role in the process:

- **Sales team:** They provide insights into customer needs and negotiate contract terms, ensuring the solution aligns with sales processes.  
- **Project managers:** They define the project's scope and objectives, which are crucial for setting accurate contract terms and conditions.  
- **Finance team:** They assess the financial aspects of the contract, including payment terms and budget considerations.  
- **Senior management:** They provide strategic oversight and final approval, ensuring the solution aligns with the organization's overall goals.  
- **Clients or external partners:** Their input is essential during the requirements gathering phase to ensure the solution meets their needs and expectations.  

## Negotiate project contracts process flow

The following diagram illustrates the business process for Project Operations Core and for Project Operations Integrated with ERP

:::image type="content" source="media/project-to-profit-negotiate-project-contracts-flow-lite.svg" alt-text="Flow diagram for the business process, which is explained in the paragraphs after the image." lightbox="media/project-to-profit-negotiate-project-contracts-flow-lite.svg":::

The *negotiate project contracts* business process flow diagram covers the following steps for the *contract manager* role in [Project Operations Core](/dynamics365/project-operations/pro/project-operations-overview-lite) and for [Project Operations Integrated with ERP](/dynamics365/project-operations/environment/project-operations-integrated-deployment-overview). Deployments with Project Operations for manufacturing are more complex as described in the section [Deployment scenario 3](#deployment-scenario-3).  

1. Start.  
1. *Adjust contract*
1. *Review legal redlines*
1. *Apply payment terms*
1. *Obtain customer approval*.

    1. If the customer approves the contract, then *Finalize contract*.
    1. If the customer doesn't approve the contract, then *revise contract*, and then *obtain customer approval* again.
1. End

<!-- ### Deployment scenario 3 for Project Operations for manufacturing

> [!NOTE]
> This section doesn't currently map to the latest version of the [business process catalog](about.md).

:::image type="content" source="media/project-to-profit-negotiate-project-contracts-flow-stocked.png" alt-text="Flow diagram that's explained after the image." lightbox="media/project-to-profit-negotiate-project-contracts-flow-stocked.png":::

The process flow diagram for deployments with Project Operations for manufacturing includes the following steps.

1. Start.  
1. *Review/add cost and sales prices*  
1. *Review/add funding sources*  
1. *Determine additional funding rules*  
1. *Review billing rules*  
1. *Add advances and retainers*  
1. End.  
 -->
<!-- > [!NOTE]  
> Steps 2-6 are in one swim lane that's dedicated to a Project Manager, Project Accountant, or Project Supervisor role.   -->

## Implementing Negotiate project contracts process

Use the following table to guide you in negotiating a project contract.

[!INCLUDE [bus-proc-config-table-explained](../includes/bus-proc-config-table-explained.md)] Learn more about the terms used in the table at [Business processes, steps, and how to find things](/dynamics365/guidance/business-processes/about-steps-navigation).

### Deployment scenarios 1 and 2

This section describes the configuration for the business process in deployments with Project Operations Core and for Project Operations Integrated with ERP.

| Process step | Process stage | Process modifier | Application: Navigation and Entity |
|--|--|--|--|
| [Manage Project Price List](/dynamics365/project-operations/sales/contracts-manage-project-price-lists) | Develop; Base; Configuration | Early; Gold; At least one | **Sales**: Sales > Price Lists<br>**Import Data**: *Project Contract Project Price List* |
| [Create Contract Lines](/dynamics365/project-operations/pro/sales/manage-contract-values-project-based-sales) | Develop; Fundamental; Operational | Early; At least one | **Sales**: Sales > Project Contracts > Contract Lines<br>**Import Data**: *Order Product* |
| [Create Advances/Retainers](/dynamics365/project-operations/pro/sales/set-up-advances-retainer-based-contracts-sales) | Develop; Optional; Operational | Continuous | **Sales**: Sales > Project Contracts > Advances and Retainers<br>**Import Data**: *Project Contract Retainers* |

### Deployment scenario 3

This section describes the configuration for the business process in deployments with Project Operations for manufacturing.

| Process step | Process stage | Process modifier | Application: Navigation and Entity |
|--|--|--|--|
| [Create Cost and Sales Prices](/dynamics365/project-operations/prod-pma/tasks/configure-standard-costs-labor-expenses) | Develop; Base; Configuration | Early; Gold; At least one | **FIN**: Project management and accounting > Setup > Prices<br>**DMF**: *Project – expense cost price*<br>*Project – expense sales price*<br>*Project – hour cost price V2*<br>*Project – hour sales price V2*<br>*Project – fee sales price*<br>*Project transfer price V2* |
| [Add additional Funding Sources](/dynamics365/project-operations/prod-pma/project-contracts) | Develop; Optional; Operational | Continuous; At least one | **FIN**: Project management and accounting > Projects > Project contracts > Funding sources<br>**DMF**: *Custom* |
| [Determine additional Funding Rules](/dynamics365/project-operations/prod-pma/project-contracts) | Develop; Optional; Operational | Continuous; At least one | **FIN**: Project management and accounting > Projects > Project contracts > Funding rules<br>**DMF**: *Custom* |
| [Review billing rules](/dynamics365/project-operations/prod-pma/project-contracts) | Develop; Optional; Operational | Continuous; At least one | **FIN**: Project management and accounting > Projects > Project contracts > Billing rules<br>**DMF**: *Project contract lines* |
| [Add Advances/Retainers](/dynamics365/project-operations/prod-pma/project-create-advanced-contracts-for-billing-based-progress) | Develop; Optional; Operational | Continuous | **FIN**: Project management and accounting > Projects > Project contracts > Billing rules<br>**DMF**: *Project contract lines* |

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *Negotiate project contracts* business processes, you can use the following resources and steps to learn more. (Links are added when the articles are ready.)  

1. [Develop project strategy](project-to-profit-govern-projects-overview.md)
1. [Manage project contracts](project-to-profit-manage-project-contracts-overview.md)  

    1. [Estimate project contracts](project-to-profit-estimate-project-contracts.md)  
    1. Negotiate project contracts. (The article you're currently reading.)  
    1. *Finalize project contracts*  
    1. *Maintain project contracts*  
    1. *Process project change requests*  
    1. *Define project stakeholders*

1. [Plan projects](project-to-profit-manage-project-scope-schedule-overview.md)  
1. [Manage project delivery](project-to-profit-deliver-project-work.md)  
1. [Manage project financials](project-to-profit-manage-project-financials-overview.md)  
1. [Analyze project performance](project-to-profit-monitor-analyze-project-performance-overview.md) 

## Related content

You can use the following resources to learn more about the *Negotiate project contracts* process in Dynamics 365.

- [Manage project contracts](/dynamics365/project-operations/pro/sales/manage-contracts-sales)
- [Manage project price lists on project contracts](/dynamics365/project-operations/sales/contracts-manage-project-price-lists)
- [Advances and retainer-based contracts](/dynamics365/project-operations/pro/sales/set-up-advances-retainer-based-contracts-sales)
- [Project contracts](/dynamics365/project-operations/prod-pma/project-contracts)
- [Understand how cost prices, sales prices, transfer prices, and taxes work together](/dynamics365/project-operations/project-accounting/understand-cost-price-sales-prices-transfer-price-taxes)
- [Project contracts - Training](/training/modules/get-started-project-sales-management/06-project-contracts?ns-enrollment-type=learningpath&ns-enrollment-id=learn-dynamics.get-started-features-project-operations)
- [Create and apply vendor payment retention terms](/dynamics365/project-operations/prod-pma/create-and-apply-vendor-payment-retention-terms)
- [Project Operations Integrated with ERP deployment overview](/dynamics365/project-operations/environment/project-operations-integrated-deployment-overview)
- [Project Operations for manufacturing deployment overview](/dynamics365/project-operations/prod-pma/project-operations-prod-order-deployment-overview)  
- [Project Operations TechTalks](https://community.dynamics.com/blogs/post/?postid=a18d2afb-428f-420d-829b-2fd5820132a6)  
- [Project management in Dynamics 365 Business Central](/dynamics365/business-central/projects-manage-projects)  

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Lifia Tamara](https://www.linkedin.com/in/lifia/) \| Consultant

Other contributors:

- [Muhammad Ali Khan](https://www.linkedin.com/in/muhammad-ali-khan-37096a18) \| Senior Consultant  
- Lalitha Chintamaneni \| Senior FastTrack Solution Architect  
