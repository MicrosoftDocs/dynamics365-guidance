---
title: Custom work item type for workshops
description: Track the work needed for workshops in your Dynamics 365 implementation with a custom work item type in Azure DevOps. See required fields and options.
author: edupont04
ms.author: edupont
ms.topic: concept-article
ms.date: 01/07/2026
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-description
  - ai-seo-date:06/11/2025
---
# Custom work item type for workshops in the Dynamics 365 business process catalog

If you want to use the Dynamics 365 business process catalog as a starting point for an implementation project that you manage in Azure DevOps, you must create custom work item types. This article outlines the required fields and the optional fields for the workshops that we suggest you track using a custom work item type, **Workshop**.

Learn more about using the business process catalog with Azure DevOps at [Use the business process catalog as a template in Azure DevOps Services](about-import-catalog-devops.md).

## Prerequisites

The following list illustrates what we assume you have in place before you create the work item type that we describe in this article.

- [!INCLUDE [daf-bus-proces-download](~/../shared-content/shared/guidance-includes/daf-bus-proces-download.md)]
- Create a project in Azure DevOps. Learn more at [Create a project in Azure DevOps](/azure/devops/organizations/projects/create-project?view=azure-devops&preserve-view=true&tabs=browser) and [Agile process work item types](/azure/devops/boards/work-items/guidance/agile-process?view=azure-devops&preserve-view=true).  
- Create the required custom work item types, including the **Workshop** type that we describe in this article.
- Add the relevant custom fields. Learn more at [Add a custom field](/azure/devops/organizations/settings/work/customize-process-field?view=azure-devops&preserve-view=true#add-a-custom-field).  

## Required fields for the work item type

The **Workshop** work item type groups all work items related to the workshops that we recommend that you include in the implementation project. Our template creates one work item for each of the workshops.  

The following table outlines the required fields on this work item type.

|Field |Description|
|---------|----------|
|**Description** |Default field.|
|**Priority** |Default field.|
|**Update comments** | Custom field.|
|**Workload type**|Custom field. Add this field as a **Picklist** field, so that users can select an option in a dropdown list. Find the required values for the list in the [Option values for the Workload type field](#option-values-for-the-workload-type-field) section.|
|**Work Shop Assumptions** |Custom field that includes a detailed description with rich text about the assumptions for the workshop. |
|**Agenda**|Custom field that includes a detailed description with rich text about the agenda for the workshop.|
|**Key questions**|Custom field that a list of questions to use to help aide the discussion during the workshop.|

> [!NOTE]
> The business process catalog that Microsoft publishes has other fields for this work item type that are optional for you to use. Learn more at [Review the optional fields in the business process catalog](about-import-catalog-devops.md#review-the-optional-fields-in-the-business-process-catalog).

## Option values for the Workload type field

We recommend that you have a custom field, **Workload type**, that defines the section of the Dynamics 365 family that this implementation project includes. The following list outlines the minimum number of options for the list.

- *Azure*  
- *Business Central*  
- *Cross-functional*  
- *Customer engagement apps*
- *Finance and operations apps*  
- *Productivity*

## Related content

Find the related articles here:

- [Use the business process catalog as a template in Azure DevOps Services](about-import-catalog-devops.md)  
- [Custom work item type for processes in the Dynamics 365 business process catalog](about-import-catalog-devops-process-work-item-types.md)  
- [Custom work item type for configuration deliverables in the Dynamics 365 business process catalog](about-import-catalog-devops-configuration-deliverable-work-item-type.md)  
- [Workshop preparation for Dynamics 365 implementation projects](about-workshops.md)  
