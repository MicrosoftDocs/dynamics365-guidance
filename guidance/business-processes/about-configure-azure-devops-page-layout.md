---
title: Automate Azure DevOps page layout creation with Python
description: Python automation for Azure DevOps page layouts helps you quickly configure projects and work items from Excel. Follow our step-by-step guide to get started.
#customer intent: As a DevOps engineer, I want to automate the creation of Azure DevOps page layouts using Python so that I can quickly set up consistent project environments at scale.
author: rachel-profitt
ms.author: raprofit
ms.reviewer: edupont
ms.date: 03/24/2026
ms.topic: how-to
---

# Automate Azure DevOps page layout creation with Python

This article shows how to automate the creation of Azure DevOps projects, processes, work item types, fields, and picklists by using a Python script and an Excel template. The template follows the Success by Design framework and recommended practices from the Microsoft Business Process Catalog. The script uses the Azure DevOps REST API and reads configuration data from an Excel file, so you can easily provision environments at scale.

## Prerequisites

Before running this script, make sure you have the following prerequisites:

1. Python 3.x installed on your machine. Install Python.
1. Required Python packages installed.

    ```powershell
    pip install pandas requests
    ```

1. Azure DevOps organization. You must have an Azure DevOps organization. Learn more at [Create an Azure DevOps organization](/azure/devops/organizations/accounts/create-organization?view=azure-devops&preserve-view=true).
1. Correct access permissions.

    a. You must be a Project Collection Administrator in Azure DevOps to run this script, as it creates projects, processes, work item types, fields, and picklists. Learn more at [Get started as a project collection administrator or organization owner](/azure/devops/user-guide/manage-organization-collection?view=azure-devops&preserve-view=true).
    b. Personal access token (PAT). When creating your PAT, select the following scopes:
      - Organization: Read & manage
      - Project and Team: Read & manage
      - Work Items: Read & write
      - Process and Work Item Types: Read & manage
    Learn more at [Use Personal Access Tokens](/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops&preserve-view=true&tabs=Windows).

1. Download the Excel template. You can download the sample Excel template for the Microsoft Business Process Catalog from [https://aka.ms/BPEADOTemplate](https://aka.ms/BPEADOTemplate). The template includes the required sheets that are used in the code sample:
    a. Work item types
    b. Fields
    > [!TIP]
    > Partners and customers can modify this file to match their requirements before running the script.

1. Ensure your machine can reach dev.azure.com and that your organization allows REST API access.
1. Ensure you already ran the `1_ADO_Creation_Script.py` script to create the process, projects, work item types, fields, and picklists. Learn more at [Automate Azure DevOps Project, Process, Work Item Types, Fields, and Picklists from Excel with Python](about-configure-azure-devops-project-processes.md).

## Procedure: Run the script 

### 1. Prepare your environment

1. Install the required Python packages.

    ```powershell
    pip install pandas requests
    ```

1. Download the script and save it as `2_ADO_Page_Layout_Script_Threaded.py`.

### 2. Configure the script

1. In the script, locate the **USER CONFIGURATION** section at the top.
1. Replace the following variables with your own values:
    - `ADO_ORG_URL`: Your Azure DevOps organization URL
    - `ADO_PROJECT`: The name of the project to create or use
    - `PROCESS_NAME`: The name of the process to create or use
    - `PAT`: Your Azure DevOps Personal Access Token
    - `EXCEL_FILE`: Path to your Excel template
    - `LOG_FILE`: Path for the log file

### 3. Run the script

1. Open a terminal and run the script:

    ```powershell
    python 2_ADO_Page_Layout_Script_Threaded.py
    ```

1. The script loops through each work item type:
    a. Creates pages if they don't exist from the Excel sheet
    b. Creates or updates groups from the Excel sheet
    c. Creates or updates controls from the Excel sheet
1. The script logs all API calls and actions to the specified log file.
    > [!NOTE]
    > This script takes more than an hour to run due to the very high number of API calls. The script is designed to be resilient with retry logic embedded.

1. Review results

    - Check the log file for details and troubleshooting.
    - Verify the new pages, groups, and controls are created in Azure DevOps for each work item type.

## Script walkthrough

- **Authentication:** Uses a PAT for Azure DevOps REST API calls.
- Creates a new page if the page doesn't exist.
- Creates a new group if the group doesn't exist.
- Creates a new control if the control doesn't exist.
- **Logging:** Logs all API calls and actions for auditing and troubleshooting.

## Sample code

The Microsoft FastTrack for Dynamics 365 team provides a sample Python script that reads the Excel file to create new pages, groups, and fields in the layouts for each work item type in Azure DevOps. Use these samples and templates to help you get started with using the Microsoft Business Process Catalog for Dynamics 365 implementation projects. To download the Python scripts and Excel template, visit [dynamics365patternspractices/templates/Azure-DevOps-templates](https://github.com/microsoft/dynamics365patternspractices/tree/main/templates/Azure-DevOps-templates).

> [!NOTE]
> To report issues or suggest changes to the sample Python script, visit [https://aka.ms/businessprocesscatalogrequests](https://aka.ms/businessprocesscatalogrequests).

## Manual configuration not included in the script

The sample Python script doesn't make certain configurations that you need when using the Microsoft Business Process Catalog to manage your projects. 

1. **Add HTML controls to the pages.** Due to a limitation in the Azure DevOps API, you can't add HTML controls to the layout. You must add these controls manually to the work item types. For more information, see [Add and Manage Fields for an Inherited Process](/azure/devops/organizations/settings/work/customize-process-field?view=azure-devops&preserve-view=true). Use the following table to guide you in adding the custom HTML controls to the work item types.

    | Work Item Type | Page Name | HTML Fields to Add (in sequence) |
| --- | --- | --- |
| Bug | Details | Postmortem, Contingency plan |
| Business task | References | Microsoft references, Mavim reference, Partner references, Internal references , Update comments |
| Change request | Details | Justification, Impact assessment, Alternative solution, Impedes |
| Configuration | Details | Acceptance criteria |
| Configuration | Information | Functional design |
| Configuration | References | Microsoft references, Mavim reference, Partner references, Internal references, Update comments |
| Deliverable | References | Microsoft references, Mavim reference, Partner references, Internal references , Update comments |
| Documentation | Details | Acceptance criteria |
| Documentation | Information | Functional design |
| End to end | References | Microsoft references, Mavim reference, Partner references, Internal references , Update comments |
| Enhancement | Details | Acceptance criteria |
| Enhancement | Information | Functional design, Technical design |
| Environment | Details | Acceptance criteria |
| Folder | References | Mavim reference, Update comments |
| Functional area | Details | Scope approach |
| Functional area | References | Microsoft references, Mavim reference, Partner references, Internal references , Update comments |
| Infrastructure | Details | Acceptance criteria |
| Integration | Details | Acceptance criteria |
| Integration | Information | Data cleansing strategy |
| Integration | References | Microsoft references, Mavim reference, Partner references, Internal references, Update comments |
| Issue | Details | Impact, Resolution |
| Job | Details | Acceptance criteria |
| Job | Information | Functional design |
| Job | References | Microsoft references, Mavim reference, Partner references, Internal references, Update comments |
| Migration | Details | Acceptance criteria |
| Migration | Information | Data cleansing strategy |
| Migration | References | Microsoft references, Mavim reference, Partner references, Internal references, Update comments |
| Personalization | Details | Acceptance criteria |
| Personalization | Information | Functional design |
| Personalization | References | Microsoft references, Mavim reference, Partner references, Internal references , Update comments |
| Process | Details | Scope approach |
| Process | References | Microsoft references, Mavim reference, Partner references, Internal references, Update comments |
| Process area | Details | Scope approach |
| Process area | References | Microsoft references, Mavim reference, Partner references, Internal references, Update comments |
| Requirement | Details | Acceptance criteria, Requirement mapping |
| Requirement | References | Microsoft references, Mavim reference, Partner references, Internal references |
| Report | Details | Acceptance criteria |
| Report | Information | Functional design, Technical design |
| Risk | Details | Risk impact assessment, Triggers |
| Report | References | Microsoft references, Mavim reference, Partner references, Internal references |
| Scenario | Details | Scope approach |
| Scenario | References | Microsoft references, Mavim reference, Partner references, Internal references, Update comments |
| Security | Details | Acceptance criteria |
| Security | Information | Functional design |
| Status report | Information | Project name, Executive summary |
| System process | References | Microsoft references, Mavim reference, Partner references, Internal references, Update comments |
| Task | Details | Impediment reason |
| Task | References | Microsoft references, Mavim reference, Partner references, Internal references, Update comments |
| Test Case | References | Microsoft references, Mavim reference, Partner references, Internal references, Update comments |
| Test plan | References | Mavim reference |
| Test suite | References | Mavim reference |
| Testing | References | Microsoft references, Mavim reference, Partner references, Internal references, Update comments |
| Ticket | Details | Postmortem, Repro steps |
| Ticket | References | Mavim reference |
| Triggers | Details | Risk impact assessment, Triggers |
| Tree | References | Microsoft references, Mavim reference, Partner references, Internal references, Update comments |
| Workflow | Details | Acceptance criteria |
| Workflow | Information | Functional design |
| Workflow | References | Microsoft references, Mavim reference, Partner references, Internal references, Update comments |
| Workshop | Details | Agenda, Scheduling notes, Workshop assumptions, Key questions |
| Workshop | References | Microsoft references, Mavim reference, Partner references, Internal references, Update comments |

    To use this table:

      - For each work item type, add the listed HTML fields to the specified page in the order shown.
      - If a work item type appears in multiple rows, combine all relevant fields for that type.

1. **Use multiselect controls on fields.**  

    Currently, the script doesn't handle adding custom controls to the pages. The Excel template includes fields that are recommended to be multiselect fields but aren't standard out-of-the-box form controls available in Azure DevOps. You can install the Multivalue control from Microsoft DevLabs [https://marketplace.visualstudio.com/items?itemName=ms-devlabs.vsts-extensions-multivalue-control](https://marketplace.visualstudio.com/items?itemName=ms-devlabs.vsts-extensions-multivalue-control) and then manually configure the fields to use the multiselect control. The following fields are recommended to be created as multiselect fields:

    - Products
    - Application family
    - Industries
    These fields are included on the following work items and the custom control must be added to each work item type for each field:

    - End to end
    - Process area
    - Process
    - Scenario
    - System process
    - Test case
    - Workflow
    - Report
    - Integration
    - Configuration
    - Enhancement
    - Documentation
    - Job
    - Migration
    - Personalization
    - Security
1. **System work item types**.  

    The Azure DevOps API has a limitation that prevents updating system work item type layouts through the API. This limitation means that you can't add custom fields to the system work item types for Test Case, Requirement, Task, Issue, Test Plan, and Test Suite. Follow the recommendations in the Excel template to add the custom fields to these work item types.
1. **OPTIONAL: Add fields that are in multiple pages or groups.** The Industry and Process sequence ID fields are recommended to appear on the Details and References pages. The script only adds the field to the Details page. If desired, you can add the same field to the References tab following the guidelines in the Excel template manually. 
1. **OPTIONAL: Change field labels for clarity**. The Excel template recommends using a different field label for the following fields to help make the work items easier to use. You can optionally update the label of these fields in your Azure DevOps.

    - Rename the **Iteration Path** field to **Status report details** on the **Status report** work item type.
    - Rename the **Story points** field to **Estimate** on the following work item types
      - Configuration
      - Documentation
      - Enhancement
      - Environment
      - Functional area
      - Infrastructure
      - Integration
      - Job
      - Migration
      - Personalization
      - Report
      - Security
      - Workflow

## Next steps

After you create the page layouts, set up the teams and area paths. Learn more at [Automate Azure DevOps teams and area paths with Python](about-configure-azure-devops-teams-area-paths.md).

## Related content

- [Azure DevOps backlog configuration for the Microsoft Business Process Catalog](about-configure-azure-devops-backlog.md)  
- [Use the business process catalog as a template in Azure DevOps Services](about-import-catalog-devops.md)  
- [Introduction to the business process catalog for Dynamics 365 apps and services](about.md)  
