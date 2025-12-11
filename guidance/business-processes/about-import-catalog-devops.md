---
title: Import the business process catalog into Azure DevOps
description: Read how you can use Microsoft's business process catalog to build an implementation project in Azure DevOps.
author: rachel-profitt
ms.author: raprofit
ms.topic: how-to
ms.collection: #Required; Leave the value blank.
ms.date: 12/10/2025
ms.custom: bap-template
---

# Use the business process catalog as a template in Azure DevOps Services

This article describes how you can use Microsoft's business process catalog as a template that you import into a project in Azure DevOps Services to manage your Dynamics 365 implementation project.

## Prerequisites

The following list illustrates what we assume you have in place before you create the work item type that we describe in this article.

- [!INCLUDE [daf-bus-proces-download](~/../shared-content/shared/guidance-includes/daf-bus-proces-download.md)]
- Create a project in Azure DevOps. Learn more at [Create a project in Azure DevOps](/azure/devops/organizations/projects/create-project?view=azure-devops&preserve-view=true&tabs=browser) and [Agile process work item types](/azure/devops/boards/work-items/guidance/agile-process?view=azure-devops&preserve-view=true).  

## Generate work items from the business process catalog

There are many reasons why a tool such as Azure DevOps is critical to the overall success of a Dynamics 365 implementation. By using a service such as [Azure Boards](/azure/devops/boards/get-started/what-is-azure-boards?view=azure-devops&preserve-view=true) with the business process catalog, you can accelerate the deployment and follow the recommendations in the [Process-focused solution](../implementation-guide/process-focused-solution.md) articles in the Dynamics 365 implementation guide content. The following list describes just some of the benefits of using the business process catalog to build work items to manage your Dynamics 365 implementation.

- **Efficiency and time savings**  

  The business process catalog provides a standardized and comprehensive list of business processes. It can save customers and partners significant time, because they don't have to research, define, and document business processes from scratch.
- **Recommended practices and industry standards**  

  The documentation that accompanies the catalog is available in [the Dynamics 365 guidance hub](/dynamics365/guidance/business-processes). The content of this documentation often includes recommended practices and industry-standard business processes. By applying these predefined processes, you help ensure that technology solutions are aligned with recognized industry standards and compliance requirements.
- **Reduced risk**  

  Use of established and standardized processes helps reduce the risk of errors and oversights in the implementation of technology solutions. These processes are tried and tested, and therefore help reduce the likelihood of costly mistakes.
- **Alignment with Microsoft technologies**  

  The business process catalog is designed to work seamlessly with Microsoft technologies, including Dynamics 365, Microsoft Power Platform, and Azure. This alignment can simplify integration and interoperability, so that it's easier to build and deploy technology solutions.
- **Scalability**  

  As businesses grow, their processes might have to evolve. The business process catalog provides a foundation that can be scaled and customized as required to ensure flexibility for future changes.
- **Community and collaboration**  

  Use of a standardized catalog can help foster collaboration and knowledge sharing in the Microsoft community. Customers and partners can benefit from the experiences and insights of others who use similar processes.
- **Training and onboarding**  

  Standardized processes can help streamline the onboarding and training of new employees or team members who join an organization. They provide a clear reference point for understanding how the organization operates.

The business process catalog offers customers and partners a valuable resource for efficiently and effectively implementing technology solutions in a way that's aligned with industry standards. It simplifies the process of designing, customizing, and deploying solutions, and ultimately leads to improved productivity, reduced risk, and better business outcomes. Microsoft provides a template with custom work item types that you can import into your Azure DevOps project. The Azure DevOps template is designed to follow the Success by Design framework with a process-focused approach.

> [!NOTE]
> This article assumes that you use [Azure Boards](/azure/devops/boards/?view=azure-devops&preserve-view=true), and that you've downloaded the business process catalog.

[!INCLUDE [daf-bus-proces-download](~/../shared-content/shared/guidance-includes/daf-bus-proces-download.md)]

> [!TIP]
> In the latest versions of the business process catalog, you can download an .XLSX file for each of the end-to-end processes in the catalog, and then open each of them in Excel to can make the relevant changes. You must save the file as a .csv file to use the *import* feature described in this article. You can also use the Azure DevOps Open in Excel add-in to copy and paste changes into your Azure DevOps project. Learn more at [Add or modify work items in bulk with Microsoft Excel](/azure/devops/boards/backlogs/office/bulk-add-modify-work-items-excel?view=azure-devops&&preserve-view=true&tabs=agile-process)

In the following sections, we refer to rows in a workbook because we assume that you have opened a file in Excel so that it now works as an Excel workbook in .xlsx format. Once you're done with your changes, save the result in the .csv format for import into Azure DevOps, and then import it into your Azure DevOps instance. Alternatively, create a hierarchical query for the end-to-ends in your Azure DevOps instance so that you can use the Excel addin for Azure DevOps to load the library instead of using .csv files.

> [!NOTE]
> We suggest that you create custom work item types for the different elements in the business process catalog. If you decide to use other work item types, make sure that your version of the catalog reflects those work item types and field names.

## Prepare the import

Before you can import the project into Azure Boards, there are a few things that you must do and consider. Use the following list as a guide and checklist to ensure that you're ready to import the catalog.

1. Define your project scope.

    We recommend that you use the workbook as a starting point to define the scope. At the most basic level, delete any rows that don't apply to your project. Learn more about how to define your project scope at [Process-focused solution](/dynamics365/guidance/implementation-guide/process-focused-solution).  

1. Create a project in the Azure DevOps Services tenant.

    The template that we provide is designed to work with the *Agile* work item process type. Learn more at [Create a project in Azure DevOps](/azure/devops/organizations/projects/create-project?view=azure-devops&preserve-view=true&tabs=browser) and [Agile process work item types](/azure/devops/boards/work-items/guidance/agile-process?view=azure-devops&preserve-view=true).

1. Create custom work item types.

    The template includes custom work item types. The template generates the work item types for you, but here's the guidance for how to create them manually. Here, we assume that you're using *agile process work item types*. You can use other types; however, that might require more custom work items types and fields. Learn more at [Customize your work tracking experience](/azure/devops/reference/customize-work?view=azure-devops&preserve-view=true&tabs=browser) and [Define area paths and assign to a team](/azure/devops/organizations/settings/set-area-paths?view=azure-devops&preserve-view=true&tabs=browser).

    1. Create the following new work item types:

        |Work item type |Description  |
        |---------|---------|
        |**End-to-end** | Groups all work items related to *end-to-end processes* (Level 1 in the catalog). Our template creates one work item for each of the end-to-end business processes. Learn more at [Custom work item type for end-to-end scenarios, process areas, business processes, and scenarios in the Dynamics 365 business process catalog](about-import-catalog-devops-process-work-item-types.md).|
        |**Process area**| Groups all work items related to *business process areas* (Level 2 in the catalog) within the different end-to-end processes. Our template creates one work item for each of the business process areas. This work item type uses the same required fields as **End-to-end** but adds one more field.|
        |**Process**|Groups all work items related to *business processes* (Level 3 in the catalog) within each business process area. Our template creates one work item for each of the business processes. This work item type uses the same required fields as **End-to-end**.|
        |**Scenario**|Groups all work items related to *patterns* (Level 4 in the catalog) within a business process. Our template creates one work item for each of the patterns. This work item type uses the same required fields as **End-to-end**.|
        |**Configuration deliverable**  |Stores each *configuration* in the template. Configuration deliverables represent setup or configuration that is required in Dynamics 365 to support one or more processes. We recommend that you document the details of each configuration throughout your project. The default configurations provided in the template guide you to the configurations that are required for each business process. More information is included on each configuration to help you understand what the configuration is used for. Learn more at [Custom work item type for configuration deliverables in the Dynamics 365 business process catalog](about-import-catalog-devops-configuration-deliverable-work-item-type.md).|
        |**Document deliverable** | A placeholder for a *document* such as a design document, statement of work, or other documentation for the project. Our template includes document deliverables with most workshops and some related processes in the *Administer to operate* end-to-end process.|
        |**Workshop**|Stores detailed information about how to run a *workshop*. Learn more at [Custom work item type for workshops in the Dynamics 365 business process catalog](about-import-catalog-devops-workshop-work-item-type.md).|

    1. Add the required fields to the custom work item types.

        The following table outlines the required fields on the new work item types. Some fields are custom fields with values provided in the template. If you prefer to use other field names, you must also change the name of the relevant column in the catalog before you import the entries.  

        |Field |Applies to work item type|
        |---------|----------|
        |**Description** |All |
        |**Process Sequence ID** |All |
        |**Priority** |All |
        |**Risk** |All |
        |**Business value** |All |
        |**Time Criticality** |All |
        |**Effort** |All |
        |**Update comments** | All |
        |**Associated Key Performance Indicators** |Process area |

1. Define area paths in the project settings.

    For each end-to-end process that is in scope, create one area path. Learn more at [Add or modify work item types](/azure/devops/reference/add-modify-wit?view=azure-devops-2022&preserve-view=true&tabs=browser).

1. Insert any other rows in the relevant .csv files that your project requires.

    You might need more *process areas*, *processes*, *scenarios*, or *configuration deliverables* than our template contains. *Process area* uses the second **Title** column, *Process* uses the third **Title** column, and *Scenario* uses the fourth **Title** column. To establish a firm relationship between the rows, don't insert the next *process area* or *Feature* row until you've listed all rows that require a relationship to the last process area or feature. You might want to add other work item types too, such as *Documentation deliverables*. However, the template that we provide doesn't currently include other work item types.

1. Fill in the other columns in the workbook as required. Use the following recommendations as guidance.

    |Field |Description|
    |---------|----------|
    |**Description**|Optionally, add a detailed description for your business processes before you import, or work on this description throughout the project. In future releases, we plan to prepopulate this column for you.|
    |**Assigned to**| Typically, select the consultant or person who is responsible for configuring the process from the partner organization. Make sure that the person is already added to your project as a user.|
    |**Business owner**| Typically, select the stakeholder from the customer organization that is responsible for the business process. Make sure that the person is already added to your project as a user.|
    |**Business process lead**| Typically, select the subject matter expert from the customer organization that is responsible for the business process. Make sure that the person is already added to your project as a user.|
    |**Tags**| Optionally, create tags for sorting, filtering, and organizing your work items. The default template doesn't include any tags. Consider using this column to separate departments, phases, geographic regions, or product families (for example, customer engagement apps and finance and operations apps).|
    |**Priority**| By default, all rows in the workbook have a priority of *1*. However, you can change the priorities to suit your needs. A priority of *1* indicates "must have" features, and a priority of *3* indicates "nice to have" features. You can also make your own definitions. In this case, we recommend that you document them for your project team.|
    |**Risk**| Optionally, add a rating for the risk. For example, you might give a high risk score to processes that are very complex or require lots of modification.|
    |**Effort**| Optionally, add a rating for the effort. For example, you might give a high effort score to processes that require integration or modification.|

1. Update the **Area path** value in the file.

    You must replace the value in the **Area path** column with the exact name of your project and area paths. If you create the areas paths so that they match the end-to-end process names, you just have to replace the text *BA Content Hub* with the name of your project in your area path.

1. Optionally, add more columns to the file, or remove columns that you don't plan to use before you import. If any of the custom fields that you add to your Azure DevOps project are mandatory, make sure that you include them in the file. Otherwise, import of the file might fail.
1. Split large files for import.

    Determine if you must split your file into multiple files before you can upload the catalog. Azure DevOps limits the number of rows that can be uploaded in one import to 1,000. If your final file has more than 1,000 rows, split the file. When you split the file, make sure that all process areas, features, and user stories that are related to the same end-to-end process are in the same file. For example, if row 1000 is in the middle of the [order to cash](order-to-cash-overview.md) process after the deletion and insertion of any required rows, split the file at the first row for *order to cash*. In this way, you ensure that all *order to cash* processes are included, and that you can establish the relationships during the import. If you try to import the entire catalog, you must split the file into four parts for import.

    > [!NOTE]
    > The *administer to operate* end-to-end process is more than 1000 rows. We recommend that you split the file at one of the level 2 process areas. Be sure to include the parent row for the end-to-end process in both files and reference the work item ID in the second file after you import the first file. This ensures that the parent-child relationships are maintained.

1. The file must be saved as a .csv file before you can import it to Azure DevOps.

    If you added columns and features such as formatting or formulas in the workbook, and you don't want to lose them, consider saving a version of the file as an .xlsx file. This version can help you avoid losing those features. However, the version that you import must be the .csv file.

    > [!NOTE]
    > If the version of the catalog that you're about to save contains special characters such as commas (,) or quotation makes ("), remove them before you save the .csv file. For example, the October 2023 version of the uncustomized catalog contains the entry *Implement "secret shopper" program*. Change this entry to *Implement secret shopper program* before you save the .csv file.

## Review the optional fields in the business process catalog

The business process catalog from Microsoft includes custom fields that are entirely optional - you don't necessarily need them on your work items. We list some of the here because they might otherwise be a source of confusion. If you don't want to use the fields, delete the columns from the templates. Learn more at [Add and manage fields](/azure/devops/organizations/settings/work/customize-process-field?view=azure-devops&preserve-view=true).

- **Catalog status**  

  This field can help you track the status of the row in the business process catalog when Microsoft publishes new versions. The following list shows the four options:

  - **New**
  - **Published**
  - **Updated**
  - **Deprecated**
- **Business owner**  

  This field can help you specify a user or person in the identity picker. We recommend you add owners to all your work items types. Learn more at [Add an Identity field](/azure/devops/organizations/settings/work/customize-process-field?view=azure-devops&preserve-view=true#add-an-identity-field).

- **Business process lead**  

  This field can help you select a user or person in the identity picker. We recommend you add owners to all your work items types.  

- **Business outcome category**  

  This field is a list so that users can select an option in a dropdown list. We recommend you add owners to the **Process** and **Scenario** work items types at a minimum. In our template, the field has following three options for the list:

  - *Business unit*

    Use this option when the work item is for a specific business unit.
  - *Organization*

    Use this option when the work item is for the entire organization.
  - *Process team*

    Use this option when the work item is for a subset of your business unit, organization, or group of people in your organization. Although we use the term *process team*, you can use any other term that's appropriate for your project.

- **Alternate process sequence ID**  

  We use this field to provide the replacement for a deprecated entry in the business process catalog. We recommend that you review the deprecated rows in the process catalog to decide how you want to handle the transition. In most cases, we have moved the process to a new location in the catalog. You can manually move an existing work item in your catalog by deleting the *Parent* relationship and creating a new relationship. This ensures that all the additional information you have tracked on your work item is kept in place.  

- **Microsoft Learn URL**  

  We use this field to specify the link to the related article on Microsoft Learn.

- **Update comments**
  
  This field includes comments that describe the updates or changes about the row in the business process catalog. If you want to import this column, add this field as a custom **Rich-text, HTML** field. Alternatively, you can delete this column before importing.

- **Responsible party**

  Optionally, use this field to define a clear ownership for this entry in the implementation project. We recommend you add to all work items types at a minimum. By default, we have the following options for the list:

  - *Customer*
  - *Partner*

- **Role type**  

  This field describes the type of role of the key people that are involved in this entry. We have the following three options for the list:

  - *Functional*
  - *Governance*
  - *Technical*

- **Program Areas**  

  This field defines the part of the scope of a business app that the entry applies to. We recommend you add to all work items types at a minimum. We have the following options for the list:

  - *Business Process Management*
  - *Data Management & Governance*
  - *Executive Leadership*
  - *Infrastructure Management*
  - *Integrations & Interfaces*
  - *Organizational Change Management*
  - *Project Management & Governance*
  - *Reporting & Business Analytics*
  - *Security Management*
  - *Solution Architecture*
  - *Solution Development*
  - *Solution Testing*
  - *Training*
  - *Usability and Experience*
  - *Workflow Management*

- **Responsible Role**  

  This field defines the role of the responsible person for the entry. We recommend you add it to all work items types. Optionally, create a similar filed with the same options but with the name *Contributor*. We have the following options for the list:

  - *Application Administrator*
  - *Build Manager*
  - *Business Analyst*
  - *Business Architect*
  - *Business Change Leads*
  - *Business Lead*
  - *Business Process Owner*
  - *Business Subject Matter Experts (SME)*
  - *Business Unit Sponsors*
  - *Change Management Lead*
  - *Communications Lead*
  - *Compliance Manager*
  - *Data Architect*
  - *Data Migration Analyst*
  - *Data Migration Lead*
  - *Database Administrator*
  - *Delivery Lead*
  - *Deployment Lead*
  - *Developer*
  - *Development Lead*
  - *Enterprise Architect*
  - *Executive - Business (CEO/CFO/COO)*
  - *Executive - Technology (VP/Director/CTO/CIO)*
  - *Executive Sponsor*
  - *Infrastructure Lead*
  - *Integration Analyst*
  - *Integration Architect*
  - *Integration Lead*
  - *Network Administrator*
  - *Program Manager*
  - *Project Manager*
  - *Project Sponsor*
  - *Quality Analyst*
  - *Reporting Analyst*
  - *Reporting Lead*
  - *Security Administrator*
  - *Security Analyst*
  - *Security Developer*
  - *Security Lead*
  - *Solution Architect*
  - *Solution Manager*
  - *Solution Specialist*
  - *Support Analyst*
  - *Support Manager*
  - *Technical Architect*
  - *Testing Lead*
  - *Trainer*
  - *Training Lead*
  - *UX Designer*
  - *Workflow Analyst*
  - *Workflow Lead*

- **Estimated complexity**  

  We recommend you add this field as a drop-down picklist to all work items types because it help you capture scope and complexity. We have the following options for the list:

  - L - Large
  - M - Medium
  - S - Small
  - XL - Extra Large
  - XS - Extra Small

- **Estimated impact**  

  We recommend you add this field as a drop-down picklist to all work items types because it help you capture scope and complexity. We have the following options for the list:

  - Critical
  - High
  - Low
  - Medium

- **Success by Design Phase**  

  We recommend you add this field as a drop-down picklist to all work items types because it help you manage the schedule. We have the following options for the list:

  - 01 Strategize
  - 02 Initiate
  - 03 Implement
  - 03 Implement-Analysis
  - 03 Implement-Design
  - 03 Implement-Development
  - 03 Implement-Test
  - 04 Prepare
  - 04 Prepare-Train
  - 05 Operate

- **Estimated frequency**  

  We recommend you add this field as a drop-down picklist to all work items types because it help you capture scope and complexity. We have the following options for the list:

  - Annually
  - Biweekly
  - Continuous
  - Monthly
  - Once per environment
  - Once per project
  - Once per project phase
  - Once per tenant
  - Quarterly
  - Weekly

## Import the file

After you prepare your file for import and configure the basic setup in the project with area paths, security, teams, and users, you can import your work items. Learn more at [Import update bulk work items with CSV files](/azure/devops/boards/queries/import-work-items-from-csv?view=azure-devops&preserve-view=true).

## Validate the work items

After you import the file, validate that the import was successful. If file import fails, use the messages that are provided to fix the issue, and then try again. After the file is successfully imported, you can start to use the features of Azure Boards to manage your project.  

The following list includes a few tasks and tips to consider.

- [Use backlogs to manage projects](/azure/devops/boards/backlogs/backlogs-overview?view=azure-devops&preserve-view=true)
- [Implement Scrum work practices in Azure Boards](/azure/devops/boards/sprints/scrum-overview?view=azure-devops&preserve-view=true)
- [Use managed queries to list work items](/azure/devops/boards/queries/about-managed-queries?view=azure-devops&preserve-view=true)
- [Analytics & Reporting](/azure/devops/report/?view=azure-devops&preserve-view=true)

## Next step

Learn about the next level of work item.

> [!div class="nextstepaction"]
> [Custom work item types for the six levels in the Dynamics 365 business process catalog](about-import-catalog-devops-process-work-item-types.md)
