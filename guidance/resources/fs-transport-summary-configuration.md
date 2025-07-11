---
title: Transport summary configuration across environments
description: Learn how to migrate Copilot summary configuration between environments with Dynamics 365 Field Service.
ms.date: 02/03/2025
ms.topic: best-practice
author: SabrinaDiBartolomeo
ms.author: sabrinadi
ms.custom:
  - O25-FieldService
---

# Transport summary configurations across Dynamics 365 Field Service environments

Copilot in Field Service provides predefined summaries for specific tables. With summary configuration, administrators can replace the default summaries and configure their own to tailor to their business needs. They can configure the summary for two tables: *Work Order* and *Bookable Resource Booking*.

This article provides information on how to transport both summary configurations across environments with the [Configuration Migration tool](/power-platform/alm/configure-and-deploy-tools).

> [!IMPORTANT]
>
> When exporting and importing the data, we assume that all the tables and columns selected in the Field Service summary configuration are available in both environments with the same schema names. If there are any changes or differences, then the FS Summary Configuration will be corrupted. Import the exported data in a pre-production environment (preferably a mirror image of the production environment) to ensure that the data import results are as you intended.

## Use the Configuration Migration tool

> [!TIP]
> One way to install the Microsoft.Xrm.Tooling.ConfigurationMigration module from the PowerShell Gallery is to open PowerShell as an administrator and run the following command: `Install-Module -Name Microsoft.Xrm.Tooling.ConfigurationMigration`. Learn more at [Dataverse development tools](/power-apps/developer/data-platform/download-tools-nuget).

1. Open the Configuration Migration tool. Learn more at [Create a schema to export configuration data](/power-platform/admin/create-schema-export-configuration-data).
1. On the main screen, select **Create schema**, and then select **Continue**.
1. Provide authentication details to connect to your source environment from where you want to export data. If you have multiple organizations on the server, select **Display list of available orgs**.  

    The option allows you to select the environment to connect to on the next screen.
1. Select **Login**.
1. From the **Select the solution** list, select a solution from where you want to export the data and afterwards from the **Select Entity** list, select **Field Service Summary Configuration (msdyn_fieldservicesummaryconfiguration)**.
1. Select **Add Entity**.  

    The following image illustrates the **Configuration Migration** page at this step.

    :::image type="content" source="media/fs-transport-summary-configuration1.png" alt-text="Screenshot of the Configuration Migration page." lightbox="media/fs-transport-summary-configuration1.png":::

1. Select **Save and Export** and enter a schema name and select **Save**. You can use the downloaded XML file of the schema to export the data in case you exit the tool.
1. After the schema save is complete, select **Yes** to confirm that you want to export the data.
1. On the next screen, specify the location of the data file to be exported in the **Save to data file** box, and then select **Export Data**.  

    The following image illustrates the **Configuration Migration** page at this step.

    :::image type="content" source="media/fs-transport-summary-configuration2.png" alt-text="Screenshot of the Configuration Migration page when you selected the schema file and data file." lightbox="media/fs-transport-summary-configuration2.png":::

1. Once complete, select **Exit** to close the tool.  

    At this stage, you see the main screen again.
1. On the main screen, select **Import data**, and then select **Continue**.
1. Provide the authentication details to connect to the target environment that you want to import the data into.  

    If you have multiple organizations on the server, select the **Display list of available orgs** option so that you can specify the environment to connect to on the next screen.
1. Select **Login**.
1. On the next screen, choose the data file (.zip) to be imported, and then choose the **Import Data** action.
1. Once complete, select **Exit** to close the tool.

The summaries are now copied to the target environment and the content is available for use.

## Power Platform build tools

Microsoft Power Platform Build Tools for Azure DevOps includes tasks, includiong the following list:

- Power Platform Export Data  

  When you use this task, you must specify the following settings:

  - Service Connection: \<*of source environment for exporting the configuration*\>
  - Environment:  $(BuildTools.EnvironmentUrl)
  - Schema File: \<*file path of XML Schema (ex. $(Build.SourcesDirectory)\data\FSSummaryConfigurationSCHEMA.xml)*\>
  - Data file or folder: \<*file path of ZIP data (ex. $(Build.SourcesDirectory)\data\FSSummaryConfigurationData.zip)*\>

- Power Platform Import Data task  

  When you use this task, you must specify the following settings:

  - Service Connection: \<*of target environment for importing the configuration*\>
  - Environment: $(BuildTools.EnvironmentUrl)
  - Data file or folder: \<*file path of ZIP data (ex. $(Build.ArtifactStagingDirectory)\$(SolutionName).zip)*\>

Learn more at [Microsoft Power Platform Build Tools tasks](/power-platform/alm/devops-build-tool-tasks).

## Microsoft Power Platform CLI

Microsoft Power Platform CLI includes the pac data Command Group to export and import data from Dataverse: 

The following example illustrates how to export data.

```
pac auth create --environment <source environment for exporting the configuration (ID, url, unique name, or partial name) ex. contosotest>
pac data export --schemaFile <file path of XML Schema ex. C:\FSSummaryConfigurationSCHEMA.xml> --dataFile <file path of ZIP data ex. C:\FSSummaryConfigurationData.zip>
```

The following example illustrates how to import data.

```
pac auth create --environment <target environment for importing the configuration (ID, url, unique name, or partial name) ex. contosotest>
pac data import --data <file path ex. C:\FSSummaryConfigurationData.zip>
```

Learn more at [Microsoft Power Platform CLI Command Groups](/power-platform/developer/cli/reference/data).

## Related resources

- [Move configuration data across environments and organizations with the Configuration Migration tool](/power-platform/admin/manage-configuration-data)
- [Summary configuration](/dynamics365/field-service/work-order-recap#summary-configuration-preview)
- [Configuration Migration tool](/power-platform/alm/configure-and-deploy-tools)
