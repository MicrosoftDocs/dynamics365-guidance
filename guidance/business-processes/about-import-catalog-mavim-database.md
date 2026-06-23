---
title: Import the business process catalog using the Mavim database
description: Import Microsoft's business process catalog into Mavim using the MTDX file. Get clear steps and best practices for seamless integration. Try it now.
author: dereklh77
ms.author: edupont
ms.reviewer: edupont
ms.topic: how-to
ms.date: 05/27/2026
---

# Import the business process catalog in Mavim using the Mavim database file

> [!IMPORTANT]
> This article documents the process for importing the business process catalog starting with the March 2026 version and later versions. For guidance on using older versions, see [Import the Business Process Catalog using a Power Automate flow](about-import-catalog-mavim.md).

This article describes how to import Microsoft's business process catalog into Mavim using the MTDX database file available on the Microsoft Download Center. Mavim is a business process management platform that you can find in the [Microsoft Marketplace](https://marketplace.microsoft.com/en-us/product/saas/mavimbv1671629332610.mavim_bpm?tab=Overview).

## Prerequisites

Before you import the catalog to the Mavim platform, complete the following steps and consider the following points. Use the following list to ensure that you're ready to import the catalog.

Download the latest version of the catalog from [https://aka.ms/BusinessProcessCatalog](https://aka.ms/BusinessProcessCatalog). Make sure you download the Mavim Database (.MTDX file) version of the catalog.

> [!IMPORTANT]
> The December 2025 release and newer versions of the business process catalog include new values for fieldsets. You must uncouple the fieldsets in your Mavim environment from the topic types that were used in the previous releases of the business process catalog. 

To uncouple field sets:

1. Open Mavim Manager.
1. Select the **Administration** tab in the Action Pane.
1. Click on **Administration Topic Types**.
1. In the **Topic Types** pane, select the types from the list one at a time.

    - Process
    - Task
    - Module
    - Primary Topic
    - Meaning
1. In the **Assigned Fieldsets** pane, select each of the following fieldsets, and then click **Remove**. To select and remove multiple assigned fieldsets at the same time, hold down the  **Shift** button on your keyboard. This process can take several minutes for each topic type.

    - Dynamics 365 Process attributes
    - Dynamics 365 Fit Gap
    - Azure DevOps
    - Dynamics 365 Process stage
    - Dynamics 365 Process modifiers
    - Dynamics 365 User Story

## Import the database

Use the following steps to import the MTDX file into your Mavim environment.

1. Open Mavim Manager.
1. Select the database where you want to import the latest version.
1. Click the **Action Toolbar** in the virtual machine.
1. Click **File Transfer > Upload**.
1. Select the .MTDX file you downloaded from the Microsoft Download Center.
1. Wait for the database file to upload into the virtual machine.
1. When the import is complete, click the Modelling tab in the Action Pane.
1. Click Import > Version.
1. Select the .MTDX file you just uploaded. The uploaded file is stored in the TempDisk drive by default. You can find this drive by clicking on **This PC**.
1. Select the file and then click **Open**.

> [!NOTE]
> The Mavim version with the business process catalog is now loaded into your purple cabinet called *Imported Versions*. It can take several minutes to complete this action.

## After you import

To start working with this process model, you need to copy it to your yellow cabinet. For the full experience, copy the entire structure (including the External References part) to your yellow cabinet. The easiest way is to right-click on the purple **Business Process Catalog Export** topic that you imported, and then click **Copy**. Then expand your yellow cabinet node and paste it anywhere you like, such as somewhere near the root, for example directly under the **Relationship Categories** topic.

This copy and paste action might take several minutes to complete. When finished, you have the latest version of the BPC available in your Mavim environment. You can either directly create a new version definition that includes this structure and create a version and publish that version to your Mavim portal to explore it. You can also make some adjustments like adding additional fields or processes.

## Next steps

- Follow the [process-focused approach](../implementation-guide/process-focused-solution.md) of the Success by Design methodology when implementing Dynamics 365.

- Manage the fit-gap analysis in Mavim and synchronize your enriched business process catalog to Azure DevOps Services.

## Recommended resources

- [Navigate the business process catalog in Mavim](about-catalog-mavim-navigate-business-process-catalog.md)  
- [Sync Dynamics 365 processes from Mavim to Azure DevOps](about-catalog-mavim-azure-devops-sync.md)  
- [Mavim.com](https://www.mavim.com/)  

  - [Application Implementation Management (mavim.com)](https://www.mavim.com/application-implementation-management)
  - [Business Process Management For A Dynamics 365 Implementation: Beyond Diagnostics (blog.mavim.com)](https://blog.mavim.com/business-process-management-for-a-dynamics-365-implementation-beyond-diagnostics)
  - [Mavim opens up to the Microsoft Power Platform to facilitate hyper automation (blog.mavim.com)](https://blog.mavim.com/mavim-opens-up-to-the-microsoft-power-platform-to-facilitate-hyperautomation)  
