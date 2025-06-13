---
title: Custom work item type for business process-related tasks
description: Track your implementation of business process scenarios in your Dynamics 365 implementation with custom work item types for end-to-end scenarios, process areas, processes, and scenarios in Azure DevOps. See required fields and options.
author: edupont04
ms.author: edupont
ms.topic: concept-article 
ms.date: 06/12/2025
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-description
  - ai-seo-date:06/11/2025
#CustomerIntent: As a <type of user>, I want <what?> so that <why?>.
---
# Custom work item types for end-to-end scenarios, process areas, business processes, and scenarios in the Dynamics 365 business process catalog

If you want to use the Dynamics 365 business process catalog as a starting point for an implementation project that you manage in Azure DevOps, you must create custom work item types. This article outlines the required fields and the optional fields for most of the work item types, namely the ones for end-to-end scenarios, process areas, processes, and scenarios (patterns) that we suggest you track using custom work item types.

Learn more about using the business process catalog with Azure DevOps at [Use the business process catalog as a template in Azure DevOps Services](about-import-catalog-devops.md).

> [!IMPORTANT]
> This article applies to the work item types for Level 1 (the **End-to-end** work item type), Level 2 (the **Process area** work item type), 3 (the **Process** work item type), and 4 (the **Scenario** work item type) in the business process catalog. However, the **Process area** work item type includes one more required field as outlined in the [Required field for the Process area work item type](#required-field-for-the-process-area-work-item-type) section.

## Prerequisites

The following list illustrates what we assume you have in place before you create the work item type that we describe in this article.

- [!INCLUDE [daf-bus-proces-download](~/../shared-content/shared/guidance-includes/daf-bus-proces-download.md)]
- Create a project in Azure DevOps. Learn more at [Create a project in Azure DevOps](/azure/devops/organizations/projects/create-project?view=azure-devops&preserve-view=true&tabs=browser) and [Agile process work item types](/azure/devops/boards/work-items/guidance/agile-process?view=azure-devops&preserve-view=true).  
- Create the required custom work item types, including the **End to end** type that we describe in this article.

## Required fields for the work item types

The **End-to-end**, **Process area**, **Process**, and **Scenario** work item types group all work items related to Level 1, 2, 3, and 4 in the catalog. Our template creates one work item for each of the entries.  

The following table outlines the required fields on these work item types.

|Field |Description|
|---------|----------|
|**Description** |Default field.|
|**Process Sequence ID** |Custom field. Add this field as a custom **Text (single line)** field, so that users can see the Microsoft assigned ID for the process. We recommend that you don't modify or change the process sequence ID provided by Microsoft. When you need to add a custom process that is not included in our standard catalog, we recommend that you suffix the ID with custom letters for your organization to ensure there is no conflict in uptaking future releases of the catalog. Learn more at [Add a custom field](/azure/devops/organizations/settings/work/customize-process-field?view=azure-devops&preserve-view=true#add-a-custom-field).|
|**Priority** |Default field.|
|**Risk** |Default field.|
|**Business value** |Default field.|
|**Time Criticality** |Default field.|
|**Effort** |Default field.|
|**Update comments** | Custom field.|

> [!NOTE]
> The business process catalog that Microsoft publishes has other fields for these work item types that are optional for you to use. Learn more at [Review the optional fields in the business process catalog](about-import-catalog-devops.md#review-the-optional-fields-in-the-business-process-catalog).

### Required field for the Process area work item type

The **Process area** work item type groups all work items related to *business process areas* that are Level 2 in the catalog.  

The following table outlines the required field that this work item type adds to the other required fields that are outlined in the [Required fields for the work item types](#required-fields-for-the-work-item-types) section.

|Field |Description|
|---------|----------|
|**Associated Key Performance Indicators** |Custom field. It contains a list of key performance indicators that's formatted as HTML.|

## Related content

Find the related articles here:

- [Use the business process catalog as a template in Azure DevOps Services](about-import-catalog-devops.md)  
- [Custom work item type for configuration deliverables in the Dynamics 365 business process catalog](about-import-catalog-devops-configuration-deliverable-work-item-type.md)  

## Next step

Learn about the next level of work item.

> [!div class="nextstepaction"]
> [Custom work item type for configuration deliverables in the Dynamics 365 business process catalog](about-import-catalog-devops-configuration-deliverable-work-item-type.md)
