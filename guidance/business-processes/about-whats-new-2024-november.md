---
title: What's new or changed in the business process catalog November 2024
description: What's new or changed in the November 2024 version of the business process catalog that Microsoft publishes as a downloadable file.
ms.date: 11/28/2024
ms.topic: whats-new #Required; don't change.
ms.collection: #Required; Leave the value blank.
author: rachel-profitt
ms.author: raprofit
---

# What's new or changed in the business process catalog November 2024

The business process catalog is a standard list of business processes across Dynamics 365 apps and services. It's an Excel workbook that we at Microsoft use to organize and prioritize our work on the business process documentation.

The November 2024 release of the catalog includes improvements across many of the end-to-end processes. It also includes improvements suggested by our user community through GitHub issue list and the Partner Advisory Board Focus Group. Download the latest version of the catalog from [https://aka.ms/businessprocesscatalog](https://aka.ms/businessprocesscatalog).

## Deprecated rows

The November 2024 version of the business process catalog includes rows where the status is **Deprecated**. These rows are no longer active and will be removed in a future release of the catalog. Many of these rows are moved to a location in the catalog. The **Alternate Process Sequence ID** column is used to indicate that the deprecated row is available in a new location in the catalog.

## Separate files

We separated the Azure DevOps templates by end-to-end processes based on popular demand. You can now download each CSV file from the Microsoft Download Center, providing you with greater flexibility and reducing the effort required to upload the files into Azure DevOps, especially given the 1000-row limit. Note that the *Administer to Operate* file exceeds 1,000 rows.

## Renaming of work item types

We're excited to announce a new feature based on feedback from our community: the renaming of work item types to better align with our users' needs and expectations. The changes are as follows:

- **Level 1**: Renamed from *Collections* to **End-to-end**.

- **Level 2**: Renamed from *Epics* to **Process area**.

- **Level 3**: Renamed from *Feature* to **Process**.

- **Level 4**: Renamed from *User story* to **Scenario**.

> [!NOTE]
> These are custom work item types and cannot be changed directly in Azure DevOps. To use these new types, you must first create the work item types in your Azure DevOps instance.

## Updated process sequence IDs

We made improvements to the process sequence IDs based on user feedback. Previously, Level 1, 2, and 3 processes had shorter numbers assigned, which caused issues when working with the CSV version of the file. To address this issue, we updated all process sequence IDs to be padded with zeros at the end, making them all the same length. This change ensures consistency and resolves the issues encountered with the CSV format.

Here's an example of the updates:

- **Level 1**: Previously 60, now **60.00.000.000**.

- **Level 2**: Previously 60.1, now **60.10.000.000**.

- **Level 3**: Previously 60.10.100, now **60.10.100.000**.

These updates enhance the usability and accuracy of the Process Sequence IDs fields across all levels.

## Configuration deliverables

We're pleased to announce several updates and additions to our configuration deliverables:

- **New configuration deliverables**: We added new configuration deliverables for finance and operations apps.

- **Updated existing deliverables**: All existing configuration deliverables are updated to include the menu item name.

- **New menu items**: We introduced new menu items for customer engagement apps, including Sales, Customer Service, Field Service, and Project Operations.

- **Extensive mapping**: Our catalog now includes more than 2,000 configuration deliverables mapped to business processes. Each configuration is mapped to the Level 3 process that is primary to the configuration.

These configurations are designed to guide customers and partners to the correct setups and pages required in the software, ensuring a smoother and more efficient experience.

## Process flow diagrams

We're excited to announce the availability of new process flow diagrams for Level 3 processes. These diagrams are generated with the help of AI and are available for download in our GitHub repository at [https://aka.ms/businessprocessflow](https://aka.ms/businessprocesscatalog). We created these new BPMN 2.0 cross-functional flow diagrams for the following areas:

- Acquire to dispose

- Case to resolution

- Inventory to deliver

- Plan to produce

- Source to pay

This release includes more than 200 Level 3 process flows, which are basic and can be used for any system an organization uses. We recommend using these diagrams to help accelerate the discovery process when implementing new technology solutions such as Dynamics 365. These diagrams are intended to be used as a starting point and customized for each organization.

### Excel to Visio connector

The flow diagrams are created using the Excel to Visio connector. Both the Excel and Visio files are provided with all the tables already connected. Here's how you can update the Excel and refresh the Visio:

1. **Update the Excel file**: Open the provided Excel file and make the necessary updates to the process data. Ensure that each row represents a step in the process, and columns include details such as the step name, description, and sequence.

2. **Save both files in the same location**: To support the integration, make sure that both the updated Excel file and the Visio file are saved in the same location on your computer or network.

3. **Open the Visio file**: Open the provided Visio file. Since the tables are already connected, Visio automatically links to the updated Excel data.

4. **Refresh the data in Visio**: In Visio, go to the **Data** tab, and then select **Refresh All**. This action updates the flow diagrams with the latest data from the Excel file.

5. **Customize and save**: Customize the flow diagrams as needed to fit your organization's specific requirements. Once you're satisfied with the diagrams, save the Visio file for future use.

These steps help you efficiently update and customize the process flow diagrams using the Excel to Visio connector. Learn more at [Refresh imported data](https://support.microsoft.com/office/refresh-imported-data-ab3668a1-873d-4109-8fa2-532670bc01e2)

## New forecast to plan end-to-end process

The entire *forecast to plan* process is deprecated and replaced with new, updated processes. The first version of the *forecast to plan* end-to-end process primarily focused on supply chain planning. We designed the new processes to provide a more comprehensive approach to business planning and strategy. The following list shows a summary of the new process areas:

- **50.15 Develop business strategy**: The focus is on developing a comprehensive business strategy, indicating a broader scope that includes overall business direction rather than just sales and operations.

- **50.25 Develop sales and marketing strategy**: The new process involves developing a detailed sales and marketing strategy, which likely includes market analysis, customer segmentation, positioning, promotion strategies, and so on.

- **50.35 Conduct supply chain planning**: The update moves from establishing policies for stocking and replenishment to conducting comprehensive supply chain planning, suggesting an integrated approach to managing the entire supply chain rather than just inventory policies.

- **50.45 Conduct operational planning**: This new area focuses on conducting broader operational planning that encompasses various aspects of operations beyond just inventory management.

- **50.55 Conduct financial planning:** This process involves creating and managing financial plans to ensure the organization's financial health and alignment with its strategic goals.

- **50.65 Analyze business performance:** This process focuses on evaluating the overall effectiveness of the business by analyzing key performance metrics and identifying areas for improvement.

These updates reflect a transition from specific tasks in supply chain management towards more holistic approaches. The new approach encompasses broader strategic elements such as business strategy development, comprehensive marketing strategies, integrated supply chain planning, and overall operational efficiency improvements.

> [!IMPORTANT]
> The November 2024 changes in the business process catalog don't show up in the articles here in the guidance hub yet. We hope to update all diagrams and articles early in 2025.

## Improvements to inventory to deliver processes

We made several updates to the *inventory to deliver* processes to enhance efficiency and clarity. Here are the key changes:

- **Updated names**: We updated the names of several Level 2 process areas and Level 3 processes to simplify and better reflect their functions.

- **Deprecated process**: The *Record and manage inventory costs* Level 2 process area is deprecated. The responsibilities of this process are redistributed as follows:

  - **Design to retire**: Item setup-related processes are absorbed into this end-to-end process.

  - **Other processes under Inventory to deliver**: The recording of costs, where it's a step in another process, is integrated into those respective processes.

  - **Record to report**: We moved *cost accounting*, *reporting analysis*, and *inventory close* processes to this end-to-end process.

These improvements are designed to streamline operations and ensure that each process is clearly defined and efficiently managed.

> [!IMPORTANT]
> The November 2024 changes in the business process catalog don't show up in the articles here in the guidance hub yet. We hope to update all diagrams and articles early in 2025.

## Improvements to Plan to produce processes

We made several updates to the *plan to produce* processes to simplify, update, and streamline them to reflect industry standards. Here are the key changes:

- **Simplified and updated names**: Many process areas and processes are simplified and updated to better align with industry standards.

- **Deprecated process**: The *Outsource production orders* process is deprecated. The responsibilities of this process are absorbed into other areas, and many rows are now scenarios at Level 4.

- **Track production costs**: Similar to the changes made in the inventory to deliver processes, the *Track production costs* process is deprecated and absorbed into other process areas.

  - **Design to retire**: Item setup-related processes are absorbed into this end-to-end process.

  - **Other processes in Plan to produce**: The recording of costs, where it's a step in another process, is now integrated into those respective processes.

  - **Record to report**: Reporting and analysis of production costs are moved to this end-to-end process.

- **New process area**: We added a new process area for *Analyze production operations*. All reporting and analytics processes from other areas were moved to this new area1.

These improvements are designed to streamline operations, ensure clarity, and enhance the overall efficiency of the plan to produce processes.

> [!IMPORTANT]
> The November 2024 changes in the business process catalog don't show up in the articles here in the guidance hub yet. We hope to update all diagrams and articles early in 2025.

## Improvements to Record to report processes

We made several updates to the *record to report* processes to simplify, update, and streamline them to align with industry standards. Here are the key changes:

- **Updated names**: Many process areas and processes are updated, simplified, and streamlined to better reflect industry standards.

- **Deprecated process**: The *Comply with tax, audit, and regulatory requirements* process is deprecated. The related processes are absorbed into other process areas, primarily:

  - **Define accounting policies**

  - **Close financial periods**

  - **Analyze financial performance**

- **New process area**: We added a new process area for *Manage cash*. Processes from other areas are moved to this new area to better organize cash and treasury management-related processes.

- **Deprecated Process**: The *Manage fund accounting* process is deprecated. Many of these processes are now recognized as scenarios of other processes.

These improvements are designed to streamline operations, ensure clarity, and enhance the overall efficiency of the *record to report* processes.

> [!IMPORTANT]
> The November 2024 changes in the business process catalog don't show up in the articles here in the guidance hub yet. We hope to update all diagrams and articles early in 2025.

## Changes to the Source to pay

We made several significant updates to the *source to pay* end-to-end process to improve clarity and align with industry standards. Here are the key changes:

- **Deprecated process**: The *Define procurement catalogs* process is deprecated and its responsibilities are absorbed into the *Develop procurement and sourcing strategy* process.

- **Terminology update**: We changed the term *vendor* to *supplier* to align with industry standards.

- **New sourcing process area**: We added the *Source and contract goods and services* process area. This new area consolidates sourcing processes from other areas. It also adds missing processes to create a more complete sourcing process.

- **Merged processes**: The processes *Process vendor invoices*, *Issue and settle vendor payments*, and *Process vendor rebates and incentives* are merged into a single process area, *Manage accounts payable*. This new area was renamed and previously called the *Process vendor invoices* process area.

- **New analysis area**: We added a new area for analyzing procurement and sourcing to provide better insights and decision-making capabilities.

These changes are designed to streamline operations, improve terminology consistency, and enhance the overall efficiency of the *source to pay* processes.

> [!IMPORTANT]
> The November 2024 changes in the business process catalog don't show up in the articles here in the guidance hub yet. We hope to update all diagrams and articles early in 2025.

## Related information

- [About the business process catalog for Dynamics 365 apps and services](about.md)  
