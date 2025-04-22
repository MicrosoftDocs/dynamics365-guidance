---  
title: Estimate Project Contracts in Dynamics 365 Project Operations  
description: Learn how to estimate project contracts effectively in Dynamics 365 Project Operations, including process flows, stakeholder roles, and best practices.  
author: edupont04  
contributors:  
ms.topic: conceptual  
ms.date: 04/22/2025
ms.author: lalithac
ms.reviewer: edupont  
---  

# Estimate project contracts

***Applies to: Dynamics 365 Project Operations***

This article provides a guide on using Dynamics 365 to *estimate project contracts*, detailing the steps and best practices for efficient contract management. It's based on a business process that is part of the [Manage project contracts](project-to-profit-manage-project-contracts-overview.md) business process area in the [Project to profit end-to-end scenario](project-to-profit-overview.md).  

In today's dynamic business environment, having an efficient process for estimating project contracts is essential. This business process helps make sure that all contractual obligations are clearly defined and understood by all parties involved, which mitigates risks associated with contractual disputes. Dynamics 365 offers robust features that enable businesses to manage these processes effectively, ensuring accuracy and compliance.

The estimation of project contracts should be defined at the initial stages of an implementation project. This business process is closely linked with other processes such as procurement, sales, and project management. Understanding how to manage contract estimation in Dynamics 365 can significantly influence the configuration and customization of related modules, ensuring a seamless integration and efficient workflow.

## Estimate project contracts stakeholders

The creation of a project contract involves several key stakeholders, each playing a crucial role in the process:

- **Sales team**: They provide insights into customer needs and negotiate contract terms, ensuring the solution aligns with sales processes.  
- **Project managers**: They define the project's scope and objectives, which are crucial for setting accurate contract terms and conditions.  
- **Contract managers**: They oversee the contract creation process, ensuring all necessary elements are included and that the contract aligns with project goals.  
- **Legal team**: They review the contract to ensure compliance with relevant laws and regulations, protecting the organization's interests.  
- **Finance team**: They assess the financial aspects of the contract, including payment terms and budget considerations.  
- **Senior management**: They provide strategic oversight and final approval, ensuring the solution aligns with the organization's overall goals.  
- **Clients or external partners**: Their input is essential during the requirements gathering phase to ensure the solution meets their needs and expectations.  

## Estimate project contracts business process flow

The following diagrams illustrate the business process for the different deployment types of Project Operations.

### Deployment scenarios 1 and 2 for Lite deployment and for resource or non-stocked based scenarios

:::image type="content" source="media/project-to-profit-estimate-project-contracts-flow-lite.svg" alt-text="Flow diagram for the business process, which is explained in the paragraphs after the image." lightbox="media/project-to-profit-estimate-project-contracts-flow-lite.svg":::

The *estimate project contracts* business process flow diagram covers the following steps for the *contract manager* role in [Lite deployments](/dynamics365/project-operations/pro/project-operations-overview-lite) and for [resource/non-stocked based scenarios](/dynamics365/project-operations/environment/project-operations-integrated-deployment-overview).

1. Start
1. *Create quote*  
1. *Determine products*
1. *Identify resources*
1. *Present to customer*
<!-- The process flow diagram for the  includes the following steps.

1. Start.  
2. Enter/update contract name and contract lines.  
3. Enter/update project contract line details.  
4. Create Projects.  
5. Create invoice schedule.  
6. End.   -->
<!-- 
> [!NOTE]  
> Steps 2-5 are in one swim lane that's dedicated to a Sales Manager, Accounting Manager, Project Manager or Project Assistant. -->

### Deployment scenario 3 for stocked or production-based scenarios

> [!NOTE]
> This section doesn't currently map to the latest version of the [business process catalog](about.md).

:::image type="content" source="media/project-to-profit-estimate-project-contracts-flow-stocked.png" alt-text="Flow diagram for the more complex deployment, and the steps in the business process are explained in the paragraphs after the image." lightbox="media/project-to-profit-estimate-project-contracts-flow-stocked.png":::

The process flow diagram for [stocked/production-based scenarios](/dynamics365/project-operations/prod-pma/project-operations-prod-order-deployment-overview) deployments of Project Operations includes the following steps.

1. Start.  
2. Decision point: *Is this an agreement with a prospect?*  
   1. If yes, follow the *Create and manage prospects and customers* business process.  
      1. *Convert prospect to customer*.  
   2. If no, continue to step 3.  
3. *Create project contract* in Finance.  
4. *Enter contract name and determine funding source*.  
5. *Enter project contract details*.  
6. Decision point: *Additional funding sources needed?*  
   1. If yes, add required funding sources and related details.  
   2. If no, continue to step 7.  
7. *Attach supporting documentation as required*.  
8. Decision point: *Billing rule needed?*  
   1. If yes, *create billing rule and enter details*.  
   2. If no, continue to step 9.  
9. End.  
10. *Create projects* (subsequent business process after you end).  

> [!NOTE]  
> Steps 2-8 are in one swim lane for a Sales Manager, Accounting Manager, Project Manager, or Project Assistant.  

## Implement the estimate project contracts business process

Use the following tables to guide you in estimating a project contract.

The following tables show the configurations available, and the sequence recommended for setting up the configurations from top to bottom. Learn more about the terms used in the table at [Business processes, steps, and how to find things](/dynamics365/guidance/business-processes/about-steps-navigation).

### Deployment scenarios 1 and 2

[!INCLUDE [bus-proc-config-table-explained](../includes/bus-proc-config-table-explained.md)]

| Process step | Process stage | Process modifier | Application: Navigation and Entity |
|--|--|--|--|
| [Create project contract](/dynamics365/project-operations/pro/sales/manage-contracts-sales) | Develop; Fundamental; Operational | Continuous; At least one | **Sales**: Sales > Project Contracts<br>**Import Data**: *Order* |
| [Create project](/dynamics365/project-operations/project-management/project-management-overview) | Develop; Fundamental; Operational | Continuous; At least one | **Projects**: Projects > Projects<br>**Import Data**: *Project* |

### Deployment scenario 3

[!INCLUDE [bus-proc-config-table-explained](../includes/bus-proc-config-table-explained.md)]

| Process step | Process stage | Process modifier | Application: Navigation and Entity |
|--|--|--|--|
| Project management and accounting parameters | Develop; Base; Configuration | Early; Gold | **FIN**: Project management and accounting > Setup > Project management and accounting parameters > Number sequences tab > Project contract ID<br>**DMF**: *Number sequence code V2 & Number sequence references V2* |
| [Create customers](/training/modules/configure-accounts-receivable-dyn365-finance/8-customers?ns-enrollment-type=learningpath&ns-enrollment-id=learn-dynamics.work-accounts-receivable-d365-finance-ops) | Develop; Fundamental; Operational | Continuous; At least one | **FIN**: Accounts receivable > Customers > All customers<br>**DMF**: *Customers, Customers V2, Customers V3* |
| [Create operating unit](/dynamics365/fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit) | Develop; Fundamental; Configuration | Early; At least one | **FIN**: Organization administration > Organizations > Operating units<br>**DMF**: *Operating unit* |
| [Create grant](/dynamics365/project-operations/prod-pma/project-grants)<sup>1</sup> | Develop; Optional; Operational | Continuous; At least one | **FIN**: Project management and accounting > Grants > Grants<br>**DMF**: *Project grants V2* |
| [Create project contract](/dynamics365/project-operations/prod-pma/project-contracts) | Develop; Fundamental; Operational | Continuous; At least one | **FIN**: Project management and accounting > Projects > Project contracts<br>**DMF**: *Project contract headers & Project contract lines* |
| [Create project](/dynamics365/project-operations/prod-pma/create-new-project) | Develop; Fundamental; Operational | Continuous; At least one | **FIN**: Project management and accounting > Projects > All projects<br>**DMF**: *Projects V2* |

> [!CAUTION]
> The configuration that's marked with *<sup>1</sup>* can't be changed once transactions exist.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *Estimate project contracts* business processes, you can use the following resources and steps to learn more. (Links are added when the articles are ready.)

1. *Estimate project contracts*  (the article you're currently reading)  
1. [*Negotiate project contracts* ](project-to-profit-negotiate-project-contracts.md)  
1. *Finalize project contracts*  
1. *Maintain project contracts*  
1. *Process project change requests*  
1. *Define project stakeholders*
<!-- 
## Related patterns

[If there are no related patterns at time of publishing, this section can be commented out. Do not delete. To comment out a section use two slashes //.]

The following patterns are available to help guide your implementation of the set customer credit limits business process.

- Pattern link 1  
- Pattern link 2  
- Pattern link n…   -->

## Related resources

You can use the following resources to learn more about the *Estimate project contracts* business process in Dynamics 365.

- [Project Operations non-stocked based scenario TechTalk](https://community.dynamics.com/blogs/post/?postid=a18d2afb-428f-420d-829b-2fd5820132a6)
- [Project Operations for resource/non-stocked based scenarios deployment overview](/dynamics365/project-operations/environment/project-operations-integrated-deployment-overview)
- [Project Operations for stocked/production-based scenarios deployment overview](/dynamics365/project-operations/prod-pma/project-operations-prod-order-deployment-overview)
- [Project contracts](/dynamics365/project-operations/prod-pma/project-contracts)
- [Get started with project management in Dynamics 365 Project Operations](/training/modules/get-started-project-management/)
- [Get started with project sales management in Dynamics 365 Project Operations](/training/modules/get-started-project-sales-management/06-project-contracts?ns-enrollment-type=learningpath&ns-enrollment-id=learn-dynamics.get-started-features-project-operations)
- [Project contracts - training](/training/modules/get-started-project-sales-management/06-project-contracts?ns-enrollment-type=learningpath&ns-enrollment-id=learn-dynamics.get-started-features-project-operations)
<!-- 
## Tags

**Industries:**  
Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

**Stakeholders:**  
Finance, Operations, Project Management, Sales

**Products:**  
Dynamics 365 Finance, Dynamics 365 Project Operations -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Lifia Tamara](https://www.linkedin.com/in/lifia/) \| Consultant

Other contributors:

- [Rachel Profitt](https://www.linkedin.com/in/rachelprofitt/) \| Principal Program Manager
- [Muhammad Ali Khan](https://www.linkedin.com/in/muhammad-ali-khan-37096a18) \| Senior Consultant
- [Ted Leung](https://www.linkedin.com/in/ted-leung-06b85010) \| Consultant
- [Mathieu Binaisse](https://www.linkedin.com/in/mathieu-binaisse-microsoft) \| Senior Fasttrack Solution Architect
- Lalitha Chintamaneni \| Senior Fasttrack Solution Architect
