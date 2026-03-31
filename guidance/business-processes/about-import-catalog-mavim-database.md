---
title: Import the business process catalog using the Mavim database
description: Import Microsoft's business process catalog into Mavim using the MTDX file. Get clear steps and best practices for seamless integration. Try it now.
author: dereklh77
ms.author: edupont
ms.reviewer: edupont
ms.topic: how-to
ms.date: 01/30/2026
---

# Import the business process catalog in Mavim using the Mavim database file

  > [!IMPORTANT]
   > This article documents the process for importing the Business Process Catalog with the March 2026 or newer releases. If you want to use older versions, please refer to [Import the Business Process Catalog using a Power Automate flow](about-import-catalog-mavim.md).

This article describes how to import Microsoft's business process catalog into Mavim using the MTDX database file available on the Microsoft Download Center. Mavim is a business process management platform that you can find in the [Microsoft Marketplace](https://marketplace.microsoft.com/en-us/product/saas/mavimbv1671629332610.mavim_bpm?tab=Overview).

## Before you import

Before you import the catalog to the Mavim platform, there are a few things that you must do and consider. Ensure that you're ready to import the catalog with the following list.

1. Download the process catalog

    Download the latest version of the catalog from [https://aka.ms/BusinessProcessCatalog](https://aka.ms/BusinessProcessCatalog). Make sure you download the Mavim Database (.MTDX file) version of the catalog.

> [!IMPORTANT]
   > The December 2025 release and newer versions of the Business Process Catalog included  all new Fieldsets. Therefore you must uncouple the Fieldsets in your Mavim environment from the topic types that were used in the previous releases of the business process catalog. To do this follow these instructions.

2. Uncouple field sets
   
    1. Open Mavim Manager.
    2. Select the **Administration** tab in the Action Pane.
    3. Click on **Administration Topic Types**.
    4. In the **Topic Types** pane, select the types from the list one at a time.
        - Process
        - Task
        - Module
        - Primary Topic
        - Meaning
    5. In the **Assigned Fieldsets** pane, select each of the following fieldsets, and then click **Remove**. You can select and remove multiple assigned fieldsets at the same time by holding Shift on your keyboard. This process may take several minutes for each topic type.
        - Dynamics 365 Process attributes
        - Dynamics 365 Fit Gap
        - Azure DevOps
        - Dynamics 365 Process stage
        - Dynamics 365 Process modifiers
        - Dynamics 365 User Story

## Import the Database
Use the following steps to import the MTDX file into your Mavim environment.

1. Open Mavim Manager.
2. Select the Database where you want to import the latest version.
3. Click the **Action Toolbar** in the virtual machine.
4. Click **File Transfer > Upload**.
5. Select the .MTDX file you downloaded from the Microsoft Download Center.
6. Wait for the database file to upload into the virtual machine.
7. When the import is complete, click the Modelling tab in the Action Pane.
8. Click Import > Version.
9. Select the .MTDX file you just uploaded. The uploaded file is stored in the TempDisk drive by default. You can find this by clicking on **This PC**.\
10. Select the file and then click **Open**.

> [!NOTE]
> The Mavim version with the business process catalog is now loaded into your purple cabinet called "Imported Versions". Be aware that it can take several minutes to complete this action.

## After you import
To be able to start working with this process model, you need to copy it to your yellow cabinet. If you want the full experience, it's important to copy the entire structure (including the External References part) to your yellow cabinet. The easiest way is to right-click on the purple "Business Process Catalog Export …" topic you imported and click **Copy**. Then expand your yellow cabinet node and paste it anywhere you like (ideally somewhere near the root, for example directly under the "Relationship Categories" topic.

Again, this copy and paste action might take several minutes to complete. Once finished you have the latest version of the BPC available in your Mavim environment. You can either directly create a new version definition that includes this structure and create a version and publish that version to your Mavim portal to explore it. You can also make some adjustments like adding additional fields or processes.

## Next steps

- Follow the [process-focused approach](../implementation-guide/process-focused-solution.md) of the Success by Design methodology when implementing Dynamics 365

- Manage the fit-gap analysis in Mavim and synchronize your enriched business process catalog to Azure DevOps.

## Recommended resources

- [Mavim.com](https://www.mavim.com/)
- [Application Implementation Management (mavim.com)](https://www.mavim.com/application-implementation-management)
- [Business Process Management For A Dynamics 365 Implementation: Beyond Diagnostics (blog.mavim.com)](https://blog.mavim.com/business-process-management-for-a-dynamics-365-implementation-beyond-diagnostics)
- [Mavim opens up to the Microsoft Power Platform to facilitate hyper automation (blog.mavim.com)](https://blog.mavim.com/mavim-opens-up-to-the-microsoft-power-platform-to-facilitate-hyperautomation)  
