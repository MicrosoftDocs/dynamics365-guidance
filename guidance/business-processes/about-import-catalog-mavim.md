---
title: Import the business process catalog in Mavim using a Power Automate flow
description: Learn how you can use Microsoft's business process catalog in Mavim, an independent software vendor found on the Azure Marketplace.
author: dereklh77
ms.author: edupont
ms.topic: article
ms.date: 10/15/2024
---

# Import the business process catalog in Mavim using a Power Automate flow

This article describes how to use Microsoft's business process catalog in the platform Mavim, an independent software vendor. Find the Mavim solution in the [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/apps/mavimbv1671629332610.mavim_bpm?tab=Overview).

The business process catalog defines workflows, protocols, and procedures as a base line for process-driven Dynamics 365 implementations. However, capturing and managing such a vast array of business processes manually often leads to issues. Such issues might include inefficiencies, inconsistencies, and difficulties in maintaining alignment with organizational goals and standards. Traditional methods often lack integration, version control, and collaboration capabilities. Keeping documentation up to date and accessible to relevant stakeholders is challenging as a result.

In this context, use Mavim to capture the business process catalog.

Mavim offers a comprehensive solution tailored to address the complexities of managing business processes. Its advanced features align perfectly with the needs of capturing the business process catalog:

1. **Centralized process repository**: Mavim provides a centralized repository for storing, organizing, and accessing the business process catalog, ensuring consistency and accessibility across the organization.

2. **Integration with Microsoft ecosystem**: Mavim seamlessly integrates with Microsoft applications like Dynamics 365, Copilot, SharePoint, Office 365, DevOps, and Visio. Mavim applies the capture and visualization of business processes within familiar environments.

3. **Collaboration and version control**: Mavim enables collaborative process modeling and documentation, allowing multiple stakeholders to contribute, review, and update processes in real-time. Version control features ensure that the catalog remains accurate and up to date.

4. **Analysis and optimization**: Mavim's analytical capabilities allow for the identification of bottlenecks, redundancies, and opportunities for optimization within the captured business processes, which drives continuous improvement and operational excellence.

5. **Governance and compliance**: Mavim supports governance frameworks and compliance requirements, enabling Microsoft to adhere to regulatory standards and internal policies while managing its business processes effectively.

Using the Mavim business process model platform to capture the business process catalog offers a holistic solution that enhances visibility, collaboration, and efficiency. It also ensures alignment with organizational objectives and regulatory standards. By adopting Mavim, organizations streamline their operations, drive innovation, and maintain their competitive position.

## Support in all phases of the Success-by-Design methodology

The business process catalog provides insight in the structure and context of the business processes that Dynamics 365 supports. A process driven implementation of Dynamics 365 assures that Dynamics 365 is better configured towards how your organization operates. It also helps in the adoption of the Dynamics 365 implementation since the end users recognize their processes.

As described in the [Success-by-Design methodology](../implementation-guide/success-by-design.md), the Initiate (or design) phase of a Dynamics implementation requires a process-focused approach. In this phase, you determine what processes are in scope or out scope for the Dynamics 365 implementation.

Following the processes in the business process catalog often requires some form of process (re)design or standardization compared to how the organization currently works. You acheive a shared understanding of how processes are used in Dynamics 365 by being able to visualize, describe, and interconnect the processes in the business process catalog.

Mavim is a business process management tool that allows you to manage large operating models or business process models such as the business process catalog. Mavim is based on a central process repository that combines process diagrams (using Visio), process descriptions (using Word), process metadata, and process relationships.

:::image type="content" source="media/about-import-catalog-mavim-patterns-practices.svg" alt-text="Diagram of the Dynamics 365 patterns and practices, showing the various business processes." lightbox="media/about-import-catalog-mavim-patterns-practices.svg":::

The Mavim platform facilitates the 'Initiate' phase by allowing you to (re)design the processes to match your way of working and describe upfront detailed fit-gap descriptions of specific configurations or customizations.

After Go-Live, the collaboration features of Mavim, with all your processes visualized and described, is a valuable tool for training and onboarding of new employees but also for your continuous improvement activities.

## Before you import

Before you import the catalog to the Mavim platform, there are a few things that you must do and consider. Ensure that you're ready to import the catalog with the following list.

1. Download the process catalog

    Download the latest version of the catalog from [https://aka.ms/BusinessProcessCatalog](https://aka.ms/BusinessProcessCatalog). Make sure you download the Excel version of the catalog.

2. Get the preconfigured Power Automate solution

    A Power Automate solution is created for importing the catalog into Mavim. Get the latest version of this solution from the [GitHub site](https://github.com/microsoft/dynamics365patternspractices/tree/main/sample-solutions/businessprocesscatalog-mavim). Learn more at [Upload or download image and file content](/power-automate/dataverse/upload-download-file).

3. Import the Power Automate solution and set up the connection between Mavim and the Power Platform

    When this API license is enabled, you assign it in the Mavim Connect Center to an internal user/service account. When importing the Power Automate solution, you're asked to make a connection to the Mavim-improve and Excel connectors. For the Mavim-improve connector, make sure you use the same user or service account you assigned the API license to.

    > [!NOTE]
   > The 'Mavim-improve' Power Platform connector is a Premium connector and requires a Power Automate Premium plan for the assigned user. Moreover, the 'Mavim-improve' Power Platform connector shouldn't be disabled by any Data Loss Prevention policies configured in your Power Platform admin center.

4. Preconfigurations in Mavim before importing the catalog.

    You need to configure the following fields before you import the business process catalog in Mavim:

    - Create a FieldSet in Mavim with the name **BPC attributes**.

    - Create a field in this FieldSet with the name **Sequence ID** (Field type: Text).

    - Create a root structure topic to import the level 1, 2 and 3 process levels of the catalog in. A logical name for this topic might be *Dynamics 365 business process catalog*.

    - Make sure to assign the new FieldSet to this root topic and let it inherit to the entire branch below this root topic.

    - Create a root structure topic to import the level 4 patterns (a logical name for this topic would be "Patterns"). For future additions, an extra topic "Dynamics 365 Related categories" is added to accommodate other related categories.

    - Make sure to assign the new FieldSet **BPC attributes** to this 'patterns' root topic.

:::image type="content" source="media/about-import-catalog-mavim-process-catalog.svg" alt-text="Screenshot showing the file path for Dynamics 365 business process catalog." lightbox="media/about-import-catalog-mavim-process-catalog.svg":::

The Mavim Academy accompanies the Mavim Platform. You must follow the level 1 and level 2 Mavim trainings to learn the basics of setting up process structures in Mavim and around the creation and assignment of Fields and FieldSets.

## Importing the business process catalog in Mavim

1. Run the Power Automate flow *Import the business process catalog into Mavim*.

    Before you run the Power Automate flow, make a couple of adjustments.

    1. Edit the Power Automate flow. Learn more at [Edit a solution-aware cloud flow](/power-automate/edit-solution-aware-flow).

    2. Adjust the "Initialize varMavimDatabaseID." Put in the unique ID of your Mavim database, which is found in the URL when you open the Mavim Improve website.

    3. In Mavim Improve, open the root topic *Dynamics 365 business process catalog*, and locate its unique topic ID in the URL. Put this ID in the action with the name **Initialize varMavimStartTopic**.

    4. In Mavim Improve, open the root topic "Patterns" and locate its unique ID in the URL. Put this ID in the action called "Initialize varPatternsStartTopic."

    5. Locate the Excel action called "List rows present in a table."

    6. Adjust the reference to the downloaded business process catalog Excel file.

    7. Save the Power Automate Flow.

    You can now run the Power Automate flow to import the entire business process catalog in Mavim.

2. Create a version and publish.

    After the import in Mavim Manager, you see the complete catalog structure. The level 4 Patterns are imported under the separate 'Patterns' root topic. Relations from the level 3 processes to the patterns are automatically created according to the Excel file.

    > [!TIP]
   > With the business process catalog in Mavim, you can now add process diagrams that let you navigate through the structure easily and visualize the processes. You can also add extra metadata fields in Mavim to capture more information on the processes. For a Dynamics 365 implementation project, for instance, you can add descriptions, scoping, and fit/gap metadata fields.

    To publish the business process catalog to the Mavim Portal, follow these steps:

    1. In Mavim, create a new version definition that includes both root topics:
        1. The 'Dynamics 365 business process catalog' root topic.
        1. The 'Patterns' root topic. 
    
     Create a version containing all content below these two topics.

    2. Publish this version to the Mavim portal.

## Update the business process catalog in Mavim

When the business process catalog is updated to a newer version, a second Power Automate flow allows you to update your existing business process catalog structure in Mavim. Updating your structure is useful if you make extensions like process flows that you add or other metadata fields that you create.

Based on the sequence ID, existing processes and patterns are updated. Currently, only the name of the process or pattern is updated.

1. Download the latest version of the catalog from [https://aka.ms/BusinessProcessCatalog](https://aka.ms/BusinessProcessCatalog). Make sure you download the Excel version of the catalog.

2. Run the Power Automate flow **Update the business process catalog in Mavim**.

    Before you run the Power Automate flow called "Update the business process catalog in Mavim" runs, make a couple adjustments.

    1. Edit the Power Automate flow. Learn more at [Edit a solution-aware cloud flow](/power-automate/edit-solution-aware-flow).

    2. Adjust the "Initialize varMavimDatabaseID". Put in the unique ID of your Mavim database, which is found in the URL when you open the Mavim Improve website.

    3. In Mavim Improve, open the root topic "Dynamics 365 business process catalog" and locate its unique topic ID in the URL. Put this ID in the action called "Initialize varMavimStartTopic."

    4. In Mavim Improve, open the root topic "Patterns" and locate its unique ID in the URL. Put this ID in the action called "Initialize varPatternsStartTopic."

    5. Locate the Excel action called "List rows present in a table."

    6. Adjust the reference to the downloaded business process catalog Excel file.

    7. Save the Power Automate flow.

    You can now run the Power Automate flow to update the entire business process catalog in Mavim.

3. Create a version and publish.

    After the update of the business process catalog in Mavim Manager, new and updated processes and patterns are updated in the existing structure in Mavim. Create a new version by using the existing version definition (that includes all BPC content). Publish this new version to the Mavim Portal.

## Next steps

- Follow the [process-focused approach](../implementation-guide/process-focused-solution.md) of the Success by Design methodology when implementing Dynamics 365

- Manage the fit-gap analysis in Mavim and synchronize your enriched business process catalog to Azure DevOps.

## Recommended resources

- [Mavim.com](https://www.mavim.com/)
- [Application Implementation Management (mavim.com)](https://www.mavim.com/application-implementation-management)
- [Business Process Management For A Dynamics 365 Implementation: Beyond Diagnostics (blog.mavim.com)](https://blog.mavim.com/business-process-management-for-a-dynamics-365-implementation-beyond-diagnostics)
- [Mavim opens up to the Microsoft Power Platform to facilitate hyper automation (blog.mavim.com)](https://blog.mavim.com/mavim-opens-up-to-the-microsoft-power-platform-to-facilitate-hyperautomation)  
