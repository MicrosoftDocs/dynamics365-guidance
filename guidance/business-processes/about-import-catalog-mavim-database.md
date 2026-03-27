---
title: Import the business process catalog in Mavim using the Mavim database
description: Learn how you can use Microsoft's business process catalog in Mavim, a business process management service that you can find in the Microsoft Marketplace.
author: dereklh77
ms.author: edupont
ms.topic: how-to
ms.date: 01/30/2026
---

# Import the business process catalog in Mavim using the Mavim database file

  > [!IMPORTANT]
   > This article documents the process for importing the Business Process Catalog with the March 2026 or newer releases. If you want to use older versions, please refer to [Import the Business Process Catalog using a Power Automate flow](about-import-catalog-mavim.md).

This article describes how to use Microsoft's business process catalog in Mavim, a business process management platform that you can find in the [Microsoft Marketplace](https://marketplace.microsoft.com/en-us/product/saas/mavimbv1671629332610.mavim_bpm?tab=Overview).

The business process catalog defines workflows, protocols, and procedures as a base line for process-driven Dynamics 365 implementations. However, capturing and managing such a vast array of business processes manually often leads to issues. Such issues might include inefficiencies, inconsistencies, and difficulties in maintaining alignment with organizational goals and standards. Traditional methods often lack integration, version control, and collaboration capabilities. Keeping documentation up to date and accessible to relevant stakeholders is challenging as a result.

In this context, use Mavim to visualize and customize the business process catalog.

Mavim offers a comprehensive solution tailored to address the complexities of managing business processes. Its advanced features align perfectly with the needs of capturing the business process catalog:

1. **Centralized process repository**: Mavim provides a centralized repository for storing, organizing, and accessing the business process catalog, ensuring consistency and accessibility across the organization.

2. **Integration with Microsoft ecosystem**: Mavim seamlessly integrates with Microsoft applications such as Dynamics 365, Copilot, SharePoint, Microsoft 365, Azure DevOps Services, and Visio. Mavim applies the capture and visualization of business processes within familiar environments.

3. **Collaboration and version control**: Mavim enables collaborative process modeling and documentation, allowing multiple stakeholders to contribute, review, and update processes in real-time. Version control features ensure that the catalog remains accurate and up to date.

4. **Analysis and optimization**: Mavim's analytical capabilities allow for the identification of bottlenecks, redundancies, and opportunities for optimization within the captured business processes, which drives continuous improvement and operational excellence.

5. **Governance and compliance**: Mavim supports governance frameworks and compliance requirements, enabling Microsoft to adhere to regulatory standards and internal policies while managing its business processes effectively.

Using the Mavim business process model platform to capture the business process catalog offers a holistic solution that enhances visibility, collaboration, and efficiency. It also ensures alignment with organizational objectives and regulatory standards. By adopting Mavim, organizations streamline their operations, drive innovation, and maintain their competitive position.

## Support in all phases of the Success-by-Design framework

The business process catalog provides insight in the structure and context of the business processes that Dynamics 365 supports. A process driven implementation of Dynamics 365 assures that Dynamics 365 is better configured towards how your organization operates. It also helps in the adoption of the Dynamics 365 implementation since the end users recognize their processes.

As described in the [Success-by-Design framework](../implementation-guide/success-by-design.md), the Initiate (or design) phase of a Dynamics implementation requires a process-focused approach. In this phase, you determine what processes are in scope or out scope for the Dynamics 365 implementation.

Following the processes in the business process catalog often requires some form of process (re)design or standardization compared to how the organization currently works. You acheive a shared understanding of how processes are used in Dynamics 365 by being able to visualize, describe, and interconnect the processes in the business process catalog.

Mavim is a business process management tool that allows you to manage large operating models or business process models such as the business process catalog. Mavim is based on a central process repository that combines process diagrams (using Visio), process descriptions (using Word), process metadata, and process relationships.

:::image type="content" source="media/about-import-catalog-mavim-patterns-practices.svg" alt-text="Diagram of the Dynamics 365 patterns and practices, showing the various business processes." lightbox="media/about-import-catalog-mavim-patterns-practices.svg":::

The Mavim platform facilitates the 'Initiate' phase by allowing you to (re)design the processes to match your way of working and describe upfront detailed fit-gap descriptions of specific configurations or customizations.

After Go-Live, the collaboration features of Mavim, with all your processes visualized and described, is a valuable tool for training and onboarding of new employees but also for your continuous improvement activities.

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
    4. In the **Assigned Fieldsets** pane, select each of the following fieldsets, and then click **Remove**. You can select and remove multiple assigned fieldsets at the same time by holding Shift on your keyboard. This process may take several minutes for each topic type.
        - Dynamics 365 Process attributes
        - Dynamics 365 Fit Gap
        - Azure DevOps
        - Dynamics 365 Process stage
        - Dynamics 365 Process modifiers
        - Dynamics 365 User Story

4. Import the Database
   
    1. Open Mavim Manager.
    2. Select the Database where you want to import the latest version.
    3. Click the **Action Toolbar** in the virtual machine.
    4. Click **File Transfer > Upload**.
    5. Select the .MTDX file you downloaded from the Microsoft Download Center.
    6. Wait for the database file to uplaod into the virtual machine. 
    7. When the import is complete, click the Modelling tab in the Action Pane.
    8. Click Import > Version.
    9. Select the .MTDX file you just uploaded. The uploaded file is stored in the TempDisk drive by default. You can find this by clicking on **This PC**.
    10. Select the file and then click **Open**.
    
    > [!NOTE]
   > The Mavim version with the business process catalog is now loaded into your purple cabinet called “Imported Versions”. Be aware that it can take several minutes to complete this action.

5. Copy the Imported Database to the Yellow Cabinet (active version)

To be able to start working with this process model, you need to copy it to your yellow cabinet. If you want the full experience, it’s important to copy the entire structure (including the External References part) to your yellow cabinet. The easiest way is to right-click on the purple “Business Process Catalog Export …” topic you imported and click **Copy**. Then expand your yellow cabinet node and paste it anywhere you like (ideally somewhere near the root, for example directly under the “Relationship Categories” topic.

Again, this copy and paste action might take several minutes to complete. Once finished you have the latest version of the BPC available in your Mavim environment. You can either directly create a new version definition that includes this structure and create a version and publish that version to your Mavim portal to explore it. You can also make some adjustments like adding additional fields or processes.

## Next steps

- Follow the [process-focused approach](../implementation-guide/process-focused-solution.md) of the Success by Design methodology when implementing Dynamics 365

- Manage the fit-gap analysis in Mavim and synchronize your enriched business process catalog to Azure DevOps.

## Recommended resources

- [Mavim.com](https://www.mavim.com/)
- [Application Implementation Management (mavim.com)](https://www.mavim.com/application-implementation-management)
- [Business Process Management For A Dynamics 365 Implementation: Beyond Diagnostics (blog.mavim.com)](https://blog.mavim.com/business-process-management-for-a-dynamics-365-implementation-beyond-diagnostics)
- [Mavim opens up to the Microsoft Power Platform to facilitate hyper automation (blog.mavim.com)](https://blog.mavim.com/mavim-opens-up-to-the-microsoft-power-platform-to-facilitate-hyperautomation)  
