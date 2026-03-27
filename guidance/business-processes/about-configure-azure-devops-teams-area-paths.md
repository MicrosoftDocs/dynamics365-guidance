---
title: Automate Azure DevOps Teams and Area Paths With Python
description: Automate Azure DevOps Teams and Area Paths setup with Python scripts. Streamline project organization using Excel templates and REST API integration.
author: rachel-profitt
ms.author: raprofit
ms.reviewer: edupont
ms.date: 03/24/2026
ms.topic: how-to
---

# Automate the creation of Azure DevOps teams and area paths with Python scripts

This article describes how to automate the creation of Azure DevOps teams and area paths, and assign teams to areas, using a Python script and an Excel template. The template is designed to follow the Success by Design framework and recommended practices with the Microsoft Business Process Catalog. The script leverages the Azure DevOps REST API and reads configuration data from the Excel file, enabling scalable setup of team structures and area hierarchies for your projects.

## Prerequisites

Before running this script, ensure you have the following:

- **Python 3.x** installed on your machine. [https://www.python.org/downloads/](https://www.python.org/downloads/)
- **Required Python packages:** pip install pandas requests
- **Azure DevOps Organization:** You must have an Azure DevOps organization. Learn more at [/azure/devops/organizations/accounts/create-organization?view=azure-devops](/azure/devops/organizations/accounts/create-organization?view=azure-devops&preserve-view=true).
- **Access:** You must be a Project Collection Administrator in Azure DevOps to run this script, as it creates teams and configures area paths. Learn more at [Get started as a project collection administrator or organization owner](/azure/devops/user-guide/manage-organization-collection?view=azure-devops&preserve-view=true).
- **Personal Access Token (PAT):** When creating your PAT, select the following scopes:
  - Organization: Read & manage
  - Project and Team: Read & manage
  - Work Items: Read & write
  - Learn more at [Use Personal Access Tokens](/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops&preserve-view=true&tabs=Windows).
- **Excel Template:** Download the sample Excel template for the Microsoft Business Process Catalog from [https://aka.ms/BPEADOTemplate](https://aka.ms/BPEADOTemplate). The template includes the required sheets:
  - Teams
  - Area paths

  Partners and customers can modify this file to match their requirements before running the script.

- **Network Access:** Ensure your machine can reach dev.azure.com and that your organization allows REST API access.

## Procedure: Run the Script

1. Prepare your environment

    1. Install required Python packages: 
    1. Download the script and save it as 3_ADO_Teams_Area_Script.py.
1. Configure the script

    1. In the script, locate the **USER CONFIGURATION** section at the top.
    1. Replace the following variables with your own values:

       - ADO_ORG_URL: Your Azure DevOps organization URL
       - ADO_PROJECT: The name of the project to create/use
       - PAT: Your Azure DevOps Personal Access Token
       - EXCEL_FILE: Path to your Excel template
       - LOG_FILE: Path for the log file
1. Run the script

    1. Open a terminal and run the script: 

        The script does the following for you:
        - Create teams listed in the Teams sheet (if they do not already exist)
        - Create hierarchical area paths from the Area paths sheet
        - Assign teams to their respective area paths as specified in the Excel file
        - All API calls and actions are logged to the specified log file
1. Review results

    1. Check the log file for details and troubleshooting.
    1. Verify the new teams and area paths in Azure DevOps.
    1. Confirm that teams are assigned to the correct area paths.

## Script Walkthrough

- **Authentication:** Uses a PAT for Azure DevOps REST API calls.
- **Team Creation:** Creates new teams from the Excel sheet if they do not exist.
- **Area Path Creation:** Creates hierarchical area paths (up to four levels) from the Excel sheet.
- **Team Assignment:** Assigns teams to area paths as specified in the Excel file.
- **Logging:** All API calls and actions are logged for auditing and troubleshooting.

## Sample Code

The Microsoft FastTrack for Dynamics 365 team provides a sample Python script that reads the Excel file to create teams, area paths, and assign teams to areas in Azure DevOps. We recommend you use these samples and templates to help you get started with using the Microsoft Business Process Catalog for Dynamics 365 implementation projects. Visit [dynamics365patternspractices/templates/Azure-DevOps-templates](https://github.com/microsoft/dynamics365patternspractices/tree/main/templates/Azure-DevOps-templates) to download the Python scripts and Excel template.

> [!NOTE]
> To report issues or suggest changes to the sample Python script, please visit [https://aka.ms/businessprocesscatalogrequests](https://aka.ms/businessprocesscatalogrequests).

## Manual configuration not included in the script

The sample Python script does not perform certain configurations that may be recommended for managing your projects:

- **Add users to teams:** You must manually add users to the teams created by the script. We recommend that you use the Sprint team to add all users to all Teams. For more granular control, you can select specific users from the project team to add to each Team. Learn more at [Add Users or Groups to Team or Project](/azure/devops/organizations/security/add-users-team-project?view=azure-devops\&tabs=preview-page).
- **Configure team settings:** Additional team settings (such as sprint assignments, dashboards, or permissions) must be configured manually in Azure DevOps.

## Next steps

After you have created the teams and area paths, you can proceed to configure your backlog and boards in Azure DevOps and import the Microsoft Business Process Catalog content into your Azure DevOps project. Following are the high-level steps and next actions to take.

1. [Create Iteration paths](/azure/devops/organizations/settings/set-iteration-paths-sprints?view=azure-devops&preserve-view=true&tabs=browser)
1. [Configure the backlog](/azure/devops/boards/backlogs/configure-your-backlog-view?view=azure-devops&preserve-view=true)
1. [Configure boards](/azure/devops/reference/?view=azure-devops&preserve-view=true)
1. [Add users to the Sprint team](/azure/devops/organizations/security/add-users-team-project?view=azure-devops&tabs=preview-page&preserve-view=true)
1. [Configure and create work item states](/azure/devops/organizations/settings/work/customize-process-workflow?view=azure-devops&preserve-view=true)
1. [Configure rules if desired](/azure/devops/organizations/settings/work/apply-rules-to-workflow-states?view=azure-devops&preserve-view=true)
1. Import the Microsoft Business Process Catalog data
1. [Plan your projects and create a delivery plan](/azure/devops/boards/sprints/best-practices-scrum?view=azure-devops&preserve-view=true)

## Related content

- [Use the business process catalog as a template in Azure DevOps Services](about-import-catalog-devops.md)  
