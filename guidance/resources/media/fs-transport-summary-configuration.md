---
title: Transport Field Service summary configuration across environments
description: Learn how to migrate Copilot summary configuration between environments.
ms.date: 11/05/2024
ms.topic: reference
author: SabrinaDiBartolomeo
ms.author: SabrinaDiBartolomeo
ms.reviewer: mhart
ms.custom:
  - O25-FieldService
---

# Transport Field Service summary configuration across environments

Copilot in Field Service provides predefined summaries for specific tables. With summary configuration, administrators can replace the default summaries and configure their own to tailor to their business needs. They can configure the summary for two tables: *Work Order* and *Bookable Resource Booking*.

This article provides information on how to transport both summary configurations across environments with the [Configuration Migration tool](/power-platform/alm/configure-and-deploy-tools).

> [!IMPORTANT]
>
> When exporting and importing the data, we assume that all the tables and columns selected in the Field Service summary configuration are available in both environments with the same schema names. If there are any changes or differences, then the FS Summary Configuration will be corrupted.

## Use the Configuration Migration tool

> [!TIP]
> One way to install the Microsoft.Xrm.Tooling.ConfigurationMigration module from the PowerShell Gallery is to open PowerShell as an administrator and run: `Install-Module -Name Microsoft.Xrm.Tooling.ConfigurationMigration`. Learn more: [Dataverse development tools](/power-apps/developer/data-platform/download-tools-nuget).

1. [Open the Configuration Migration tool](/power-platform/admin/create-schema-export-configuration-data).
1. On the main screen, select **Create schema**, and then select **Continue**.
1. Provide authentication details to connect to your source environment from where you want to export data. If you have multiple organizations on the server, select **Display list of available orgs**. The option allows you to select the environment to connect to on the next screen.
1. Select **Login**.
1. From the **Select the solution** list, select a solution from where you want to export the data and afterwards from the **Select Entity** list, select **Field Service Summary Configuration (msdyn_fieldservicesummaryconfiguration)**.
1. Select **Add Entity**.
   ![image](https://github.com/user-attachments/assets/3e8ead9e-7d65-4f90-a9a3-cd97f897a85f)
1. Select **Save and Export** and enter a schema name and select **Save**. You can use the downloaded XML file of the schema to export the data in case you exit the tool.
1. After the schema save is complete, select **Yes** to confirm that you want to export the data.
1. On the next screen, specify the location of the data file to be exported in the **Save to data file** box, and then select **Export Data**.
   ![image](https://github.com/user-attachments/assets/e7970841-31a6-4cef-8c13-dacff8e72155)
1. Once complete, select **Exit** to close the tool. You should see the main screen again.
1. On the main screen, select **Import data**, and then select **Continue**.
1. Provide authentication details to connect to your target environment to where you want to import data. If you have multiple organizations on the server, select **Display list of available orgs**. The option allows you to select the environment to connect to on the next screen.
1. Select **Login**.
1. On the next screen, choose the data file (.zip) to be imported. Select **Import Data**.
   ![image](https://github.com/user-attachments/assets/1850236c-56db-460a-94f6-550e5ae6e45e)
1. Once complete, select **Exit** to close the tool.

## Related information

- [Move configuration data across environments and organizations with the Configuration Migration tool](/power-platform/admin/manage-configuration-data)
- [Summary configuration](/dynamics365/field-service/work-order-recap#summary-configuration-preview)
- [Configuration Migration tool](/power-platform/alm/configure-and-deploy-tools)
