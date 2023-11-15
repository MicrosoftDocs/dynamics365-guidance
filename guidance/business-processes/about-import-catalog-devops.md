---
title: Import the business process catalog into Azure DevOps
description: Read how you can use Microsoft's business process catalog to build an implementation project in Azure DevOps.
author: rachel-profitt
ms.author: raprofit
ms.topic: conceptual #Required; don't change.
ms.collection: #Required; Leave the value blank.
ms.date: 11/15/2023
ms.custom: bap-template #Required; don't change.
---

# Import the business process catalog into Azure DevOps

This article describes how you can use the business process catalog as a template to import into a project in Azure DevOps Services for managing your Dynamics 365 implementation project.

## Generate work items from the business process catalog

There are many reasons why using a tool like Azure DevOps is critical to the overall success of a Dynamics 365 implementation. When you use a service such as [Azure Boards](/azure/devops/boards/get-started/what-is-azure-boards?view=azure-devops&preserve-view=true) with the business process catalog, you can accelerate the deployment and follow the recommendations made in the [Process-focused solution](../implementation-guide/process-focused-solution.md) articles in the Dynamics 365 implementation guide content. The following points are just some of the benefits of using the catalog to build work items to manage your Dynamics 365 implementation.

- **Efficiency and time savings**: Microsoft's business process catalog provides a standardized and comprehensive list of business processes. This catalog can save customers and partners a significant amount of time that would otherwise be spent on researching, defining, and documenting business processes from scratch.

- **Recommended practices and industry standards**: Find the documentation that accompanies the catalog in [the Dynamics 365 guidance hub](/dynamics365/guidance/business-processes). The content often includes recommended practices and industry-standard business processes. Applying these predefined processes can help ensure that technology solutions align with recognized industry standards and compliance requirements.

- **Reduced risk**: Using established and standardized processes reduces the risk of errors and oversights in the implementation of technology solutions. These processes are tried and tested, reducing the chances of costly mistakes.

- **Alignment with Microsoft technologies**: The catalog is designed to work seamlessly with Microsoft technologies, including Dynamics 365, Power Platform, and Azure. This alignment can simplify integration and interoperability, making it easier to build and deploy technology solutions.

- **Scalability**: As businesses grow, their processes might need to evolve. The business process catalog provides a foundation that can be scaled and customized as needed, ensuring flexibility for future changes.

- **Community and collaboration**: Use a standardized catalog to help foster collaboration and knowledge sharing within the Microsoft community. Customers and partners can benefit from the experiences and insights of others who use similar processes.

- **Training and onboarding**: When new employees or team members join an organization, having standardized processes in place can streamline their onboarding and training. It provides a clear reference point for understanding how the organization operates.

In conclusion, the business process catalog offers customers and partners a valuable resource for implementing technology solutions efficiently, effectively, and in alignment with industry standards. It simplifies the process of designing, customizing, and deploying solutions, ultimately leading to improved productivity, reduced risk, and better business outcomes.

> [!NOTE]
> In this article, we assume that you use [Azure Boards](/azure/devops/boards/?view=azure-devops&preserve-view=true), and that you have downloaded the catalog.

[!INCLUDE [daf-bus-proces-download](../includes/daf-bus-proces-download.md)]

## Before you import

Before you can import the project into Azure Boards, there are a few things that you need to do and consider. Use the following information as a guide and checklist to ensure that you're ready to import the catalog.

1. Define your project scope.  

    We suggest that you use the spreadsheet as a starting point to define the scope. At the most fundamental level, delete any rows that don't apply to your project. Learn more about defining your project scope at [Process-focused solution](/dynamics365/guidance/implementation-guide/process-focused-solution).  

2. Create a project in the Azure DevOps Services tenant.  

    The template we provide is designed to work with the **Agile** work item process type. Learn more at [Create a project in Azure DevOps](/azure/devops/organizations/projects/create-project?view=azure-devops&preserve-view=true&tabs=browser) and [Agile process work item types](/azure/devops/boards/work-items/guidance/agile-process?view=azure-devops&preserve-view=true).

3. Define area paths in the  project settings.  

    For each end-to-end process that is in scope, create one area path. Learn more at [Define area paths and assign to a team.](/azure/devops/organizations/settings/set-area-paths?view=azure-devops&preserve-view=true&tabs=browser).  

4. Insert any other rows required for your project.  

    You might need more epics, features, or user stories. Epics use the first *Title* column, features use the second *Title* column, and user stories use the third *Title* column. To establish a firm relationship between the rows, don't insert the *Next Epic* or *Feature* row until you've listed all rows that required a relationship to the last epic or feature. You might want to consider adding other work items types too such as Configuration or Workshops, for example, but the template provided doesn't include other work item types.

5. Complete the other columns in the spreadsheet as required. Use the following recommendations to guide you.

    1. **Description** – in future releases, we plan to prepopulate this column for you. Optionally, add a detailed description for your business processes before you import, or work on this description throughout the project.

    2. **Assigned to** – typically the consultant or person who is responsible for configuring the process from the partner organization. Make sure the person is already added as a user to your project.

    3. **Business owner** – typically the stakeholder from the customer organization that is responsible for the business process. Make sure the person is already added as a user to your project.

    4. **Business process lead** – typically the subject matter expert from the customer organization that is responsible for the business process. Make sure the person is already added as a user to your project.

    5. **Tags** – optionally, create tags for sorting, filtering, and organizing your work items. The default template doesn't include any tags. Consider using this column to separate departments, phases, geographic regions, or product families, such as customer engagement apps and  finance and operations apps, for example.

    6. **Priority** – all rows in the spreadsheet have a default priority of 1. change the priorities to suit your needs, where 1 is for all "must have" features, and 3 is for all "nice to have features". You can define your own definitions, too. We recommend that you document the definitions for your project team.

    7. **Risk** – optionally, add a rating for the risk. For example, you might give processes a high risk score if there's a lot of complexity or modification required to the process.

    8. **Effort** – optionally, add a rating for the effort. For example, you might apply a high effort score to processes that require integration or modification.

6. Update the **Area path** in the file.  

    You must replace the value in the **Area path** column with the exact name of your project and area paths. If you create the areas paths to match the end to end process names, you just have to replace the following text *DevOps Product Catalog Working Instance* with the name of your project in your area path.

7. Optionally, add more columns to the file, or remove columns that you won't use before you import. If you add custom fields to your Azure DevOps project that are mandatory, make sure you include them in the file, or the file might fail to import.

8. Split large files for import.  

    Determine if you must split your file into multiple files for uploading. Azure DevOps has a limit of 1,000 rows that can be uploaded in one import. If your final file has more than 1,000 rows, split the file. It's critical that when you split the file, all epics, features, and user stories that are related to the same end-to-end process are in the same file. For example, if row 1000 is in the middle of the [*order to cash*](order-to-cash-overview.md) process after deleting and inserting any required rows, you'll want to split the file at the first row for *order to cash*. That way, you make sure that all *order to cash* processes are included, and that you can establish the relationships during the import. If you attempt to import the entire catalog, you must split the file into four parts for importing.

9. The file must be saved as a .CSV file to be imported into Azure DevOps.  

    If you added extra columns and features in the spreadsheet that you don't want to lose such as formatting or formulas, consider saving a version of the file as an .XLSX file. This version can help you avoid losing those features. However, the version you import must be the .CSV file.

> [!NOTE]
> If the version of the catalog that you are about to save contains special characters, such as **,** or **"**, remove them before you save the .CSV file. For example, the October 2023 version of the uncustomized catalog contains a pattern, *Implement "secret shopper" program*. Change that entry to *Implement secret shopper program*, and then save the .CSV file.  

## Import the file

Once you have prepared your file for import, and you have configured the basic setup in the project with area paths, security, teams, and users, you can import your work items. Learn more at [Import update bulk work items with CSV files](/azure/devops/boards/queries/import-work-items-from-csv?view=azure-devops&preserve-view=true).

## After you import

After you import the file, validate the import was successful. If the file import fails, use the messages provided to help guide you to correct the issue and then try again. Once the file is imported successfully, you can begin managing your project using the features of Azure Boards. The following list includes a few tasks and tips to consider.

- [Use backlogs to manage projects](/azure/devops/boards/backlogs/backlogs-overview?view=azure-devops&preserve-view=true)
- [Implement Scrum work practices in Azure Boards](/azure/devops/boards/sprints/scrum-overview?view=azure-devops&preserve-view=true)
- [Use managed queries to list work items](/azure/devops/boards/queries/about-managed-queries?view=azure-devops&preserve-view=true)
- [Analytics & Reporting](/azure/devops/report/?view=azure-devops&preserve-view=true)
