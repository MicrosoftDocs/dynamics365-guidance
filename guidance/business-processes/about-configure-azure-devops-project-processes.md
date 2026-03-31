---
title: Automate Azure DevOps Project, Processes from Excel with Python
description: Automate Azure DevOps project setup with Python and Excel. Streamline processes, work item types, and picklists. Start provisioning at scale today.
author: rachel-profitt
ms.author: raprofit
ms.reviewer: edupont
ms.date: 03/24/2026
ms.topic: how-to
---

# Automate Azure DevOps project, process, work item types, fields, and picklists from Excel with Python

This article shows how to automate the creation of Azure DevOps projects, processes, work item types, fields, and picklists by using a Python script and an Excel template. The template follows the Success by Design framework and recommended practices from the Microsoft Business Process Catalog. The script uses the Azure DevOps REST API and reads configuration data from an Excel file, so you can easily provision environments at scale.

## Prerequisites

Before running this script, make sure you have the following items:

1. Python 3.x installed on your machine. You can [download and install Python](https://www.python.org/downloads/).
1. Required Python packages:

    ```powershell
    # Windows PowerShell / PowerShell 7
    python --version
    python -m pip install --upgrade pip
    # Required packages for the ADO setup scripts
    python -m pip install pandas requests openpyxl
    ```

    Optionally, verify that *openpyxl* is available.

    ```powershell
    python -c "import openpyxl, sys; print('openpyxl', openpyxl.__version__)"
    ```

1. Azure DevOps organization. You must have an Azure DevOps organization. To learn more, see [Create an Azure DevOps organization](/azure/devops/organizations/accounts/create-organization) in the documentation for Azure DevOps Services.
1. Correct access.

    a. You must be a Project Collection Administrator in Azure DevOps to run this script, as it creates projects, processes, work item types, fields, and picklists. To learn more, see [Get started as a project collection administrator or organization owner](/azure/devops/user-guide/manage-organization-collection?view=azure-devops&preserve-view=true).
    b. Create a personal access token (PAT). When creating your PAT, select the following scopes:
      - Organization: Read & manage
      - Project and Team: Read & manage
      - Work Items: Read & write
      - Process and Work Item Types: Read & manage

    To learn more, see [Use Personal Access Tokens](/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops&preserve-view=true&tabs=Windows).

1. Excel template: Download the sample Excel template for the Microsoft Business Process Catalog from [https://aka.ms/BPEADOTemplate](https://aka.ms/BPEADOTemplate). The template includes the required sheets that are used in the code sample:
    a. Work item types
    b. Fields
    c. Picklists
    > [!TIP]
    > Partners and customers can modify this file to match their requirements before running the script.

1. Update partner defined picklists.

    The Excel template file provided includes several picklists that partners define based on your project methodology and implementation project needs. Use the following information to guide you:

    - **Partner phase.** For example, you could align these phases to Success by Design phases and create a phase for Strategize, Initiate, Implement, Prepare, and Operate. Or you could create more detailed phases like Analyze, Design, Build, Test, and so on.
    - **Partner workshop type.** For example, Discovery, Solution Design, Business Transformation, and so on.
    - **Workstream.** Workstreams categorize work items for filtering and assignment. For example, Finance, Procurement, Sales, Field Service, and so on.
    - **Authorized for deployment.** Use this list to maintain a list of the environments for the project to indicate when code or configuration, for example, is ready to be deployed to the next environment. The list of values should match the name of the environment in the customer's tenant. For example, DEV, TEST, and PROD.
    - **Current highest deployment.** Use this list to maintain a list of the environments for the project to indicate the highest-level environment where the code or configuration is deployed. The list of values should match the name of the environment in the customer's tenant. For example, DEV, TEST, and PROD.

1. Network access:
    a. Ensure your machine can reach dev.azure.com and that your organization allows REST API access.

## Procedure: Run the script 

### 1. Prepare your environment

1.  Install the required Python packages.

```powershell
python -m pip install pandas requests openpyxl
```

1. Download the script and save it as `1_ADO_Creation_Script.py`.

### 2. Configure the script

1. In the script, locate the **USER CONFIGURATION** section at the top.
1. Replace the following variables with your own values:
    - ADO_ORG_URL: Your Azure DevOps organization URL
    - ADO_PROJECT: The name of the project to create or use
    - PROCESS_NAME: The name of the process to create or use
    - PAT: Your Azure DevOps Personal Access Token
    - EXCEL_FILE: Path to your Excel template
    - LOG_FILE: Path for the log file
### 3. Run the script

1. Open a terminal and run the script:

    ```powershell
    python 1_ADO_Creation_Script.py
    ```

1. The script automates the following tasks:
    a. Create the process (if it doesn't exist)
    b. Create the project (if it doesn't exist)
    c. Create or update work item types from the Excel sheet
    d. Create or update picklists from the Excel sheet
    e. Create or update fields from the Excel sheet
1. The script logs all API calls and actions to the specified log file.
### 4. Review the results

1. Check the log file for details and troubleshooting.
1. Verify the new project, process, work item types, fields, and picklists in Azure DevOps.

## Script walkthrough

- **Authentication:** Uses a PAT for Azure DevOps REST API calls.
- Create a new process that inherits from the Agile process.
- Create a new project that uses the new process.
- Create work item types in the process.
- Create picklists with values.
- Create organization-level fields.
- **Logging:** Log all API calls and actions for auditing and troubleshooting.

## Sample code

The FastTrack for Dynamics 365 team provides a sample Python script that reads the Excel file to create new pages, groups, and fields in the layouts for each work item type in Azure DevOps. Use these samples and templates to help you get started with using the Microsoft Business Process Catalog for Dynamics 365 implementation projects. To download the Python scripts and Excel template, visit [dynamics365patternspractices/templates/Azure-DevOps-templates](https://github.com/microsoft/dynamics365patternspractices/tree/main/templates/Azure-DevOps-templates).

> [!NOTE]
> To report issues or suggest changes to the sample Python script, go to [https://aka.ms/businessprocesscatalogrequests](https://aka.ms/businessprocesscatalogrequests).

## Manual configuration not included in the script

The sample Python script doesn't include certain configuration that you should apply when using the Microsoft Business Process Catalog to manage your projects. 

- **Disable work item types that you don't use.** Disable the Epic, Feature, and User Story work item types that are included by default in the Agile process that the script inherits. To learn more, see [Customize work item type for inherited process](/azure/devops/organizations/settings/work/customize-process-work-item-type?view=azure-devops&preserve-view=true).
- **Create work item states.** Extend the template or manually create work item states that match your project methodology. The sample template includes only the default work item states, which are often not robust enough to manage a complex ERP or CRM implementation. To learn more, see [Customize the workflow of an inherited process](/azure/devops/organizations/settings/work/customize-process-workflow?view=azure-devops&preserve-view=true).
- **Give users access to your project.** Give each of the project team members access to the Azure DevOps project. To learn more about security in Azure DevOps, see [Add Users or Groups to Team or Project](/azure/devops/organizations/security/add-users-team-project?view=azure-devops&tabs=preview-page&preserve-view=true).

## Next steps

After you create the process, project, work item types, and organizational level fields, add the fields to each work item type and create the page layouts for each work item type. For sample scripts and to learn more, see [Automate Azure DevOps page layout creation with Python](/azure/devops/organizations/settings/work/automate-page-layout-creation-python?view=azure-devops&preserve-view=true).
