---
title: Project to profit end-to-end overview
description: Learn about the end-to-end business process, from project to profit. This article provides a high-level flow diagram and describes the relationship with other processes in Dynamics 365 solutions.
ms.date: 10/30/2023
ms.topic: conceptual
author: edupont04
ms.author: lalithac
---

# Project to profit end-to-end overview

***Applies to: Dynamics 365 Business Central, Dynamics 365 Finance, Dynamics 365 Human Resources, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management***

This article describes the project to profit end-to-end business process flow and its relationship to other business processes that can be used within Dynamics 365.

## Project to profit process relationship

The following diagram shows the relationship of other processes and products/features for the project to profit process.

:::image type="content" source="media/project-to-profit-relationship.svg" alt-text="Project to profit process relationship diagram." lightbox="media/project-to-profit-relationship.svg":::

There are several processes that are often prerequisites to the *project to profit* process, including the following list:

<!-- - **Case to resolution**  

  When you require a robust approval process before starting a new project, you can use case management features to help drive the request and manage the onboarding of a new project. -->

- **Order to cash**  

  The *order to cash* process can be upstream to the *project to profit* process, if your organization sells tangible items that lead to a larger project. For example, installation or warranty that is related to a tangible product.

- **Design to retire**  

  This process can be an upstream process in two senses.  

  1. When you define the details for your project contract lines, or estimate projects, you can add items to the estimate. But first, you must configure the *design to retire* process.  

  2. Product lifecycle management might initiate a project to create or revise a product.

- **Prospect to quote**  

  Most organizations use some sort of quoting or opportunity management process for larger projects. If you plan to use Dynamics 365 to support this process, you must configure the *prospect to quote* process to support the creation of leads, opportunities, and quotes, for example.

<!-- - **Service to cash**  

  If your organization sells services such as maintenance, installation, or warranties, the *service to cash* process can be upstream to the *project to profit* process. -->

The *project to profit* end-to-end process is broken down into the following business process areas:

- Govern projects

- Manage project contracts

- Manage project resources and schedule

- Manage project delivery

- Manage project financials

- Monitor and analyze project performance

Learn more about the business process areas at [Project to profit business process areas](project-to-profit-areas.md).

The downstream processes for the project to profit process include the following list:

- **Acquire to dispose**  

  A primary goal of a project might be the creation of an asset with a long useful life. Maybe you must amortize the accounting value of the asset over its lifetime. When the asset enters service, the accumulated costs of the project become the acquisition value of a new fixed asset managed via the Acquire to dispose business process.

- **Case to resolution**  

  The *case to resolution* downstream process might start after an initial sale of a product or service as part of a project. For example, a company sells a software product to implement an enterprise solution. After the project is complete, the customer experiences issues. In such cases, the *case to resolution* process can be triggered to track and manage resolution of the issue.

- **Inventory to deliver**  

  As with the *order to cash* process, if a project includes the sale of tangible, stocked products, the normal downstream *inventory to deliver* process applies to pick, pack, and ship the product.

- **Order to cash**  

  *Order to cash* can be downstream to *project to profit*. Selling tangible or intangible products to customers is frequently within the scope of a project. For example, a project involves selling a software license and delivering work to implement it on behalf of a customer. For such products, the normal *order to cash* process often applies. This procces includes sales order entry, delivering the product, invoicing for it, and processing customer payment.

- **Plan to produce**  

  In scenarios such as *engineer to order* or *build to order* manufacturing, you often manage the production of sub-assemblies or finished products as part of the project. For example, a manufacturer wins a contract to design, build, and commission custom equipment. Since the project takes months, or even years, and encompass many cost components, they manage the contract as one or more discrete projects.

- **Design to retire**  

  A project might be intended to create or revise products to be sold and thus provide inputs to a downstream end-to-end process.

- **Procure to pay**  

  The *procure to pay* process involves purchasing goods and services and making payments for them. In most organizations, the procurement of various materials and equipment is necessary to complete a project. If you plan to use Dynamics 365 Project Operations to support your organization, make sure you configure the *procure to pay* process for tasks such as the following list:

  - Create purchase requisitions  

  - Create purchase orders  

  - Receive goods and services  

  - Invoice approvals  

  - Invoice payments  

  - Make financial reconciliation  

- **Record to report**  

  The *record to report* downstream process involves the following tasks:  

  - Recording generated revenue from the project as a financial transaction  

  - Performing reconciliation to ensure all financial transactions recorded accurately  

  - Preparing financial statements  

  - Analyzing financial data  

  - Closing the accounting period  

- **Service to cash**  

  *Service to cash* can be downstream to *project to profit*. For example, you sell intangible services such as consulting or health care services to customers. This process involves steps such as the following list:  

  - Providing a service  

  - Generating the service report for the services provided  

  - Invoicing for it  

  - Processing customer payment  

## Featured capabilities

There are product-specific capabilities that interact with the *project to profit* process including, but not limited to, the following list:

- **Project Sales**

  Dynamics 365 Project Operations encompasses rich capabilities to win more deals and accelerate the sales cycle with fast and accurate quotes, flexible pricing, and seamless transitions from estimate to execution.

- **Project for the Web**

  Project for the web is a project management tool offered by Dynamics 365. It's a cloud-based application that enables businesses to manage their projects, resources, and budgets in a centralized location. With Project for the web, users can create, manage, and track projects from start to finish, allowing them to stay on top of deadlines, resource allocation, and project progress.

- **Universal Resource Scheduling**

  Universal Resource Scheduling is an advanced scheduling engine in Dynamics 365 Project Operations. Organizations can optimize resource use by aligning the right people with the right skills, to the right projects. It also provides a visual representation of resource availability and workload, which makes it easier for project managers to manage and allocate resources.

- **Time and Expense Tracking**

  With the *Time and Expense Tracking* system in Dynamics 365 Project Operations, team members can easily track and submit their time and expenses for approval and billing purposes. Project team members can submit time and expenses from anywhere, using their mobile devices or desktops.

- **Material usage**

  *Material usage* in Dynamics 365 Project Operations supports tasks such as the following list for project managers:  

  - Create purchase orders for materials  

  - Track material deliveries  

  - Manage material inventory levels  

  - Allocate materials to specific tasks or projects  

  - Track material usage and costs at the project level  

- **Subcontracting**

  With Dynamics 365 Project Operations, organizations can manage subcontracting activities within projects such as the following list:  

  - Create and manage subcontractor contracts with vendors  

  - Track subcontractor work  

  - Monitor subcontractor costs  

  - Create subcontractor invoices  

  - Manage subcontractor payments  

- **Project Accounting**

  Project accounting provides essential capabilities such as the following list:  

  - Accurate forecasting  

  - Budgeting and recording of project costs and revenues  

  - Invoicing  

  - Revenue recognition  

  - Compliance  

  - Visibility into key project and overall business health metrics  

- **Microsoft Teams**

  Project teams can improve productivity, and collaborate more effectively with Microsoft Teams. The teams can communicate via chat, video, and voice. They can share files within Project Operations, and access project information directly from within Teams.  

## Project to profit business process flow

The following diagram shows the high-level flow of the *project to profit* business process. [!INCLUDE [daf-business-process-e2e-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-e2e-flow-def.md)]

:::image type="content" source="media/project-to-profit-process-flow.svg" alt-text="Flow diagram for the end-to-end business process, which is explained in the paragraphs after the image." lightbox="media/project-to-profit-process-flow.svg":::

The following steps are illustrated in the *project to profit* end-to-end business process flow diagram.

The upstream processes *Case to resolution*, *Order to cash*, *Prospect to quote*, and *Service to cash* are connected to subprocess a.*Manage project opportunities*. *Product and service lifecycle* *management* is connected to subprocess c.*Manage project contracts*.

1. Start

2. Project to profit end-to-end process

    <!-- 1. Manage project opportunities -->
    <!-- 2. Manage project quotations -->
    1. [Govern projects](project-to-profit-govern-projects-overview.md)  

        1. Manage project stakeholders

        2. Manage project budgets

        3. Manage project risks

        4. Manage project quality

        5. Manage project communications

            *Manage project budgets*, *Manage project quality*, and *Manage project communications* connect to subprocess l.*Monitor and analyze project performance*.

            *Manage project risks* connects to subprocess l.*Monitor and analyze project performance* and the downstream process *Case to Resolution*

    2. Manage project contracts

    3. [Manage project resources and schedule](project-to-profit-manage-project-scope-schedule-overview.md)

    <!-- 6. Resource a project

        Parallel branch from this subprocess is l. *Monitor and analyze project performance* -->

    4. [Manage project delivery](project-to-profit-deliver-project-work.md)  

        Parallel branches from this subprocess are i. *Capture project expenses*, j.*Process project invoices*, and the downstream processes *Service to cash*, *Design to retire*, *Order to cash*, *Plan to produce*, and *Procure to pay*.

    5. [Manage project financials](project-to-profit-manage-project-financials-overview.md)

    <!-- 8. Manage project supply chain

        Parallel branches from this subprocess are the downstream processes *Service to cash*, *Design to retire*, *Order to cash*, *Plan to produce*, and *Procure to pay*

    9. Capture project expenses

        Parallel branch from this subprocess is the downstream process *Acquire to dispose*

    10. Process project invoices

        Parallel branch from this subprocess is the downstream process *Order to cash*

    11. Recognize project revenue

        Parallel branch from this subprocess is the downstream process *Record to Report* -->

    6. Monitor and analyze project performance

        The downstream processes *Service to cash* and *Case to Resolution* connect to End

3. End

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *project to profit* business processes, use the following resources and steps to learn more.

- Define the business process scope of your project. Learn more at [Process-focused solution](../implementation-guide/process-focused-solution.md)  

- Request a demo or get a free trial of Dynamics 365 solutions for *the project to profit* process. Learn more at [Request a demo](https://dynamics.microsoft.com/dynamics-365-free-trial/)  

- Get an overview of each end-to-end business process area at [Project to profit business process areas overview](project-to-profit-areas.md).  

## Related resources

Use the following resources to learn more about the project to profit process in Dynamics 365.  

- [Dynamics 365 Project Operations series (blog)](https://community.dynamics.com/blogs/post/?postid=a18d2afb-428f-420d-829b-2fd5820132a6)  

- [Dynamics 365 Project Operations (Microsoft Learn)](/dynamics365/project-operations/)  

- [Microsoft Certified: Dynamics 365 Fundamentals (ERP)](/certifications/d365-fundamentals-finance-and-operations-apps-erp/)  

- [Project Operations learning paths](/training/browse/?expanded=dynamics-365&products=dynamics-project-operations&resource_type=learning%20path)  

<!--## Tags 

*Stakeholders:* Executive Sponsor, Project Manager, IT Department, Finance Department, Sales and Marketing Teams and End Users 

*Products:* Dynamics 365 Business Central, Dynamics 365 Finance, Dynamics 365 Human Resources, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management -->
