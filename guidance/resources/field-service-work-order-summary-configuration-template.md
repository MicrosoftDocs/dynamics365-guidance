---
title: Work order summary configuration template
description: Learn how to configure custom summaries of work orders in Dynamics 365 Field Service by importing and editing a base configuration.
ms.date: 01/28/2025
ms.topic: best-practice
author: SabrinaDiBartolomeo
ms.author: sabrinadi
ms.custom:
  - O25-FieldService
---

# Work order summary configuration template

Administrators who want to replace the default summary of work orders in Dynamics 365 Field Service and configure their own to meet their business needs must start from scratch to set up the configuration. This article provides an example of a base configuration for the [Work Order summary](/dynamics365/field-service/work-order-recap#summary-configuration-preview) that administrators can import and edit as needed.

Find the source files in the GitHub repo at [https://aka.ms/wosummaryconfigurationtemplate](https://aka.ms/wosummaryconfigurationtemplate).

> [!WARNING]
> We assume that all the tables and columns selected in the Field Service summary configuration template are available in the target environment with the same schema names. If there are any changes or differences, then the work order summary configuration will be corrupted.
> We recommend that you first try to import the configuration in a copy of the development environment.


## Tables and columns of the template

The following table shows the tables and the columns used in this configuration template:

|Table                                                           |Column                      |
|----------------------------------------------------------------|----------------------------|
|Work Order                                                      |System Status               |
|Work Order                                                      |Time From Promised          |
|Work Order                                                      |Time To Promised            |
|Work Order                                                      |Work Order Number           |
|Work Order                                                      |Street 1                    |
|Work Order                                                      |Street 2                    |
|Work Order                                                      |Street 3                    |
|Work Order                                                      |City                        |
|Work Order                                                      |State Or Province           |
|Work Order                                                      |Postal Code                 |
|Work Order                                                      |Country/Region              |
|Work Order                                                      |Completed On                |
|Work Order                                                      |Total Cost                  |
|Work Order                                                      |Total Amount                |
|Work Order                                                      |Total Estimated Cost        |
|Priority                                                        |Name                        |
|Service Account \[Account\]                                     |Account Name                |
|Product                                                         |Field Service Product Type  |
|Resource \[Bookable Resource\]                                  |Name                        |
|Primary Incident Type \[Incident Type\]                         |Incident Type               |
|Work Order Type                                                 |Work Order Type             |
|Work Order Products \[msdyn_workorder\]                         |Quantity                    |
|Work Order Products \[msdyn_workorder\]                         |Work Order Product          |
|Work Order Services \[msdyn_workorder\]                         |Name                        |
|Work Order Services \[msdyn_workorder\]                         |Estimate Duration           |
|Work Order Incidents \[msdyn_incidenttype\]                     |Description                 |
|Work Order Service Tasks \[msdyn_workorder\]                    |Name                        |
|Work Order Service Tasks \[msdyn_workorder\]                    |Estimated Duration          |
|Work Order Service Tasks \[msdyn_workorder\]                    |Description                 |
|Bookable Resource Bookings \[msdyn_workorder\]                  |Start Time                  |
|Bookable Resource Bookings \[msdyn_workorder\]                  |End Time                    |
|Bookable Resource Bookings \[msdyn_workorder\]                  |Estimated Arrival Time      |
|Bookable Resource Bookings \[msdyn_workorder\]                  |Estimated Travel Duration   |
|Bookable Resource Bookings \[msdyn_workorder\]                  |Actual Arrival Time         |
|Bookable Resource Bookings \[msdyn_workorder\]                  |Actual Travel Duration      |

## Import the template with the Configuration Migration tool

To import the template *FSSummaryConfigurationData.zip*, you can use the **Configuration Migration** tool. Learn more at [Transport summary configuration across environments](field-service-deploy-transport-summary-configuration.md). 

## Import the template with Power Platform build tools

Microsoft Power Platform Build Tools for Azure DevOps includes the Power Platform Import Data task, which can be used by specifying:

- Service Connection: \<*of target environment for importing the configuration*\>
- Environment: $(BuildTools.EnvironmentUrl)
- Data file or folder: \<*file path*\>\FSSummaryConfigurationData.zip

Learn more at [Microsoft Power Platform Build Tools tasks](/power-platform/alm/devops-build-tool-tasks?#import-dataverse-data).

### Import with Microsoft Power Platform CLI

Here is an example of how to import the template using Microsoft Power Platform CLI after you have downloaded the file *FSSummaryConfigurationData.zip* at [https://aka.ms/wosummaryconfigurationtemplate](https://aka.ms/wosummaryconfigurationtemplate):

```
pac auth create --environment <target environment for importing the configuration (ID, url, unique name, or partial name) ex. contosotest>
pac data import --data <file path ex. C:\FSSummaryConfigurationData.zip>
```

Learn more at [Microsoft Power Platform CLI Command Groups](/power-platform/developer/cli/reference/data).

### Import with a YAML pipeline

Here is an example of how to import the template using YAML pipeline after you have downloaded the file *FSSummaryConfigurationData.zip* at [https://aka.ms/wosummaryconfigurationtemplate](https://aka.ms/wosummaryconfigurationtemplate):

```yml
steps:
- task: microsoft-IsvExpTools.PowerPlatform-BuildTools.import-data.PowerPlatformImportData@2
  displayName: 'Power Platform Import Data'
  inputs:
    authenticationType: PowerPlatformSPN
    PowerPlatformSPN: <Service connection of the target environment for importing the configuration name ex. contosotest>
    DataFile: '$(Build.SourcesDirectory)\data\FSSummaryConfigurationData.zip'
```

## Related resources

- [Move configuration data across environments and organizations with the Configuration Migration tool](/power-platform/admin/manage-configuration-data)
- [Configuration Migration tool](/power-platform/alm/configure-and-deploy-tools)
- [Microsoft Power Platform Build Tools for Azure DevOps](/power-platform/alm/devops-build-tools)
- [Power Platform CLI](/power-platform/developer/cli/introduction?tabs=windows)
