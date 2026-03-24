---
title: Automate Azure DevOps Project, Process, Work Item Types, Fields, and Picklists from Excel with Python
description: This article demonstrates how to automate the creation of Azure DevOps projects, processes, work item types, fields, and picklists using a Python script and an Excel template. The template is designed to follow the Success by Design framework and recommended practices with the Microsoft Business Process Catalog. The script leverages the Azure DevOps REST API and reads configuration data from an Excel file, making it easy to provision environments at scale.
author: rprofitt
ms.author: rprofitt
ms.date: 03/24/2026
ms.topic: how-to
ms.service: dynamics-365
ms.subservice: guidance
---

# Automate Azure DevOps Project, Process, Work Item Types, Fields, and Picklists from Excel with Python

This article demonstrates how to automate the creation of Azure DevOps projects, processes, work item types, fields, and picklists using a Python script and an Excel template. The template is designed to follow the Success by Design framework and recommended practices with the Microsoft Business Process Catalog. The script leverages the Azure DevOps REST API and reads configuration data from an Excel file, making it easy to provision environments at scale.

## Prerequisites

Before running this script, ensure you have the following:

1. Python 3.x installed on your machine. Install Python
2. Required Python packages:

```powershell
# Windows PowerShell / PowerShell 7
python --version
python -m pip install --upgrade pip
# Required packages for the ADO setup scripts
python -m pip install pandas requests openpyxl
```

# (Optional) Verify that openpyxl is available

```powershell
python -c "import openpyxl, sys; print('openpyxl', openpyxl.__version__)"
```

3. Azure DevOps Organization. You must have an Azure DevOps organization. For more information see Create an Azure DevOps organization.
4. Ensure you have the correct access.
   a. You must be a Project Collection Administrator in Azure DevOps to run this script, as it creates projects, processes, work item types, fields, and picklists. For more information, see [Get started as a project collection administrator or organization owner](https://learn.microsoft.com/en-us/azure/devops/user-guide/manage-organization-collection?view=azure-devops).
   b. Create a personal access token (PAT). When creating your PAT, select the following scopes:
      - Organization: Read & manage
      - Project and Team: Read & manage
      - Work Items: Read & write
      - Process and Work Item Types: Read & manage
For more information, see [Use Personal Access Tokens](https://learn.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops&tabs=Windows).

5. Excel Template: Download the sample Excel template from for the Microsoft Business Process Catalog from [https://aka.ms/BPEADOTemplate](https://aka.ms/BPEADOTemplate). The template includes the required sheets that are used in the code sample:
   a. Work item types
   b. Fields
   c. Picklists
> [!TIP]
> Partners and customers can modify this file to match their requirements before running the script.

6. Update partner defined picklists.
The Excel template file provided includes several picklists that are intended to be defined by the partner based on your project methodology and implementation project needs. Use the following information to guide you:

- **Partner phase.** For example, you could align these to Success by Design phases and create a phase for Strategize, Initiate, Implement, Prepare, and Operate. Or you could create more detailed phases like Analyze, Design, Build, Test, and so on.
- **Partner workshop type**. For example, Discovery, Solution Design, Business Transformation, and so on.
- **Workstream**. Workstreams are used to categorize work items that are created for filtering and assignment. For example, Finance, Procurement, Sales, Field Service, and so on.
- **Authorized for deployment.** Use this list to maintain a list of the environments for the project to indicate when code or configuration for example are ready to be deployed to the next environment. We recommend the list of values matches the name of the environment in the customers tenant. For example, DEV, TEST, and PROD.
- **Current highest deployment.** Use this list to maintain a list of the environments for the project to indicate the highest-level environment where the code or configuration has been deployed. We recommend the list of values matches the name of the environment in the customers tenant. For example, DEV, TEST, and PROD.
7. Network Access:
   a. Ensure your machine can reach dev.azure.com and that your organization allows REST API access.
## Procedure: Run the script 

**1. Prepare Your Environment**

- Install required Python packages.

```powershell
pip install pandas requests
```

- Download the script and save it as 1_ADO_Creation_Script.py.
**2. Configure the Script**

- In the script, locate the **USER CONFIGURATION** section at the top.
- Replace the following variables with your own values:
   - ADO_ORG_URL: Your Azure DevOps organization URL
   - ADO_PROJECT: The name of the project to create/use
   - PROCESS_NAME: The name of the process to create/use
   - PAT: Your Azure DevOps Personal Access Token
   - EXCEL_FILE: Path to your Excel template
   - LOG_FILE: Path for the log file
**3. Run the Script**

a. Open a terminal and run the script:

```powershell
python 1_ADO_Creation_Script.py
```

b. The script will:
   a. Create the process (if it doesn’t exist)
   b. Create the project (if it doesn’t exist)
   c. Create or update work item types from the Excel sheet
   d. Create or update picklists from the Excel sheet
   e. Create or update fields from the Excel sheet
1. All API calls and actions are logged to the specified log file.
**4. Review Results**

- Check the log file for details and troubleshooting.
- Verify the new project, process, work item types, fields, and picklists in Azure DevOps.
## Script Walkthrough

- **Authentication:** Uses a PAT for Azure DevOps REST API calls.
- Create a new Process that inherits from the Agile process
- Create a new Project that uses the new Process
- Create Work item types in the Process
- Create Picklists with values
- Create Organization level fields
- **Logging:** All API calls and actions are logged for auditing and troubleshooting.
## Sample Code

The Microsoft FastTrack for Dynamics 365 team provides a sample python script that reads the Excel file to create new pages, groups, and fields in the layouts for each work item type in the Azure DevOps. The We recommend you use these samples and templates to help you get started with using the Microsoft Business Process Catalog for Dynamics 365 implementation projects. Visit [dynamics365patternspractices/templates/Azure-DevOps-templates](https://github.com/microsoft/dynamics365patternspractices/tree/main/templates/Azure-DevOps-templates) to download the Python scripts and Excel template.

> [!NOTE]
> To report issues or suggest changes to the sample python script, please visit [https://aka.ms/businessprocesscatalogrequests](https://aka.ms/businessprocesscatalogrequests).

## Manual configuration not included in the script

The sample python script does not do certain configuration that we recommend when you are using the Microsoft Business Process Catalog to manage your projects. 

- **Disable work item types that are not used.** We recommend that you disable the Epic, Feature, and User Story work item types that are included by default in the Agile process that is inherited in the script. To learn more about how to disable work item types in Azure DevOps see [Customize work item type for inherited process](https://learn.microsoft.com/en-us/azure/devops/organizations/settings/work/customize-process-work-item-type?view=azure-devops).
- **Create work item states.** We recommend that partners extend the template or manually create work item states that match your project methodology. Only the default work item states are included in the sample template which are often not robust enough to manage a complex ERP or CRM implementation. To learn more about work item states, see [Customize the workflow of an inherited process](https://learn.microsoft.com/en-us/azure/devops/organizations/settings/work/customize-process-workflow?view=azure-devops).
- **Give users access to your project.** We recommend that you give each of the project team members access to the Azure DevOps project. To learn more about security in Azure DevOps, see [Add Users or Groups to Team or Project](https://learn.microsoft.com/en-us/azure/devops/organizations/security/add-users-team-project?view=azure-devops&tabs=preview-page).
## Next steps

After you have created the process, project, work item types, and created the organizational level fields, the next step is to add the fields to each work item type and create the page layouts for each work item type. For sample scripts and to learn more, see Automate Azure DevOps page layout creation with Python.

