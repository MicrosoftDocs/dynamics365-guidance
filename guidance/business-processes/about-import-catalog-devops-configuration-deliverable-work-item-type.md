---
title: Custom work item type for configuration deliverables
description: Track configuration deliverables in your Dynamics 365 implementation with a custom work item type in Azure DevOps. See required fields and options.
author: edupont04
ms.author: edupont
ms.topic: concept-article
ms.date: 06/11/2025
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-description
  - ai-seo-date:06/11/2025
---
# Custom work item type for configuration deliverables in the Dynamics 365 business process catalog

If you want to use the Dynamics 365 business process catalog as a starting point for an implementation project that you manage in Azure DevOps, you must create custom work item types. This article outlines the required fields and the optional fields for the configuration deliverables that we suggest you track using a custom work item type, **Configuration deliverable**.

Learn more about using the business process catalog with Azure DevOps at [Use the business process catalog as a template in Azure DevOps Services](about-import-catalog-devops.md).

## Prerequisites

The following list illustrates what we assume you have in place before you create the work item type that we describe in this article.

- [!INCLUDE [daf-bus-proces-download](~/../shared-content/shared/guidance-includes/daf-bus-proces-download.md)]
- Create a project in Azure DevOps. Learn more at [Create a project in Azure DevOps](/azure/devops/organizations/projects/create-project?view=azure-devops&preserve-view=true&tabs=browser) and [Agile process work item types](/azure/devops/boards/work-items/guidance/agile-process?view=azure-devops&preserve-view=true).  
- Create the required custom work item types, including the **Configuration deliverable** type that we describe in this article.
- Add the relevant custom fields. Learn more at [Add a custom field](/azure/devops/organizations/settings/work/customize-process-field?view=azure-devops&preserve-view=true#add-a-custom-field).  

## Required fields for the work item type

The **Configuration deliverable** work item type groups all work items related to *patterns* that are Level 4 in the catalog. Our template creates one work item for each of the patterns.  

The following table outlines the required fields on this work item type.

|Field |Description|
|---------|----------|
|**Description** |Default field.|
|**Process Sequence ID** |Custom field. Add this field as a custom **Text (single line)** field, so that users can see the Microsoft assigned ID for the process. We recommend that you don't modify or change the process sequence ID provided by Microsoft. When you need to add a custom process that is not included in our standard catalog, we recommend that you suffix the ID with custom letters for your organization to ensure there is no conflict in uptaking future releases of the catalog. Learn more at [Add a custom field](/azure/devops/organizations/settings/work/customize-process-field?view=azure-devops&preserve-view=true#add-a-custom-field).|
|**Priority** |Default field.|
|**Risk** |Default field.|
|**Business value** |Default field.|
|**Time Criticality** |Default field.|
|**Effort** |Default field.|
|**Products** | Custom field. Add this field as a **Picklist** field, so that users can select an option in a dropdown list. Find the required values for the list in the [Option values for the Products field](#option-values-for-the-products-field) section.|
|**Update comments** | Custom field.|
|**Workload type**|Custom field. Add this field as a **Picklist** field, so that users can select an option in a dropdown list. Find the required values for the list in the [Option values for the Workload type field](#option-values-for-the-workload-type-field) section.|
|**Menu Path**| Custom field. Add this field as a custom **Text (single line)** field, so that users can enter a menu path to navigate to the configuration in Dynamics 365.|
|**Included in entity**| Custom field. Add this field as a custom **Text (single line)** field, so that you can indicate if the configuration is included in a data entity by entering the name of the data entity.|
|**Menu item name**|For finance and operations apps, this value includes the AOT menu item name. For configurations with customer engagement apps, the field includes the portion of the URL with the page and view details. Add the field as a custom **Text (single line)** field, so that you can indicate if the configuration is included in a data entity by entering the name of the data entity.|
|**Application family**| Custom field. Add this field as a **Picklist** field, so that users can select an option in a dropdown list. Find the required values for the list in the [Option values for the Application family field](#option-values-for-the-application-family-field) section.|
|**Module/Functionality**|Custom field. Both names are equally valid. The current version of the catalog uses **Module** to describe a group of product capabilities, such as *Fixed assets*. Add this field as a **Picklist** field, so that users can select an option in a dropdown list. Find the required values for the list in the [Option values for the Module/Functionality field](#option-values-for-the-modulefunctionality-field) section|

> [!NOTE]
> The business process catalog that Microsoft publishes has other fields for this work item type that are optional for you to use. Learn more at [Review the optional fields in the business process catalog](about-import-catalog-devops.md#review-the-optional-fields-in-the-business-process-catalog).

## Option values for the Products field

We recommend that you have a custom field, **Products**, that defines the Dynamics 365 apps that this implementation project includes. The following list outlines the minimum number of options for the list.  

- Business Central
- Commerce
- Customer Insights Data
- Customer Insights Journey
- Customer Service
- Customer Voice
- Field Service
- Finance
- Fraud Protection
- Guides
- Human Resources
- Project Operations
- Remote Assist
- Sales
- Sales Copilot
- Supply Chain Management
- Microsoft 365
- Teams
- SharePoint
- Project
- Power BI/Fabric
- Power Platform
- Azure
- Other

## Option values for the Workload type field

We recommend that you have a custom field, **Workload type**, that defines the section of the Dynamics 365 family that this implementation project includes. The following list outlines the minimum number of options for the list.

- *Azure*  
- *Business Central*  
- *Cross functional*  
- *Customer engagement*
- *Finance and operations*  
- *Productivity*

## Option values for the Application family field

We recommend that you have a custom field, **Application**, that defines the section of the Dynamics 365 family that this implementation project includes. The following list outlines the minimum number of options for the list.  

- Finance and operations apps
- Customer engagement apps
- Cross-app

## Option values for the Module/Functionality field

We recommend that you have a custom field, **Module/Functionality**, that defines the section of the Dynamics 365 family that this implementation project includes. The following list outlines the minimum number of options for the list. 

- Accounts payable
- Accounts receivable
- Asset leasing
- Asset management
- Audit workbench
- Budgeting
- Cash and bank management
- Common
- Consolidations
- Cost accounting
- Cost management
- Credit and collections
- Expense management
- Fixed assets
- General ledger
- Human resources
- Inventory management
- Master planning
- Organization administration
- Payroll
- Pricing management
- Procurement and sourcing
- Product information management
- Production control
- Project management and accounting
- Questionnaire
- Retail
- Sales
- Sales and marketing
- Service
- Service management
- System settings
- Tax
- Time and attendance
- Transportation management
- Warehouse management

> [!TIP]
> These names are based on common names for various departments or roles or functional areas in business apps. They partially overlap with the names of modules in Dynamics 365 but are not necessarily identical with the names of modules.

## Related content

Find the related articles here:

- [Use the business process catalog as a template in Azure DevOps Services](about-import-catalog-devops.md)  
- [Custom work item type for end-to-end scenarios in the Dynamics 365 business process catalog](about-import-catalog-devops-process-work-item-types.md)  
- [Custom work item type for workshops in the Dynamics 365 business process catalog](about-import-catalog-devops-workshop-work-item-type.md)  

## Next step

Learn about the next level of work item.

> [!div class="nextstepaction"]
> [Custom work item type for workshops in the Dynamics 365 business process catalog](about-import-catalog-devops-workshop-work-item-type.md)
