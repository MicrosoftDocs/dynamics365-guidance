---
title: What's new or changed in the business process catalog February 2025
description: What's new or changed in the February 2025 version of the business process catalog that Microsoft publishes as a downloadable file.
ms.date: 02/14/2025
ms.topic: whats-new #Required; don't change.
ms.collection: #Required; Leave the value blank.
author: rachel-profitt
ms.author: raprofit
---

# What's new or changed in the business process catalog February 2025

The business process catalog is a standard list of business processes across Dynamics 365 apps and services. The business process catalog is an Excel workbook that we at Microsoft use to organize and prioritize our work on the business process documentation.

The February 2025 version of the catalog includes improvements across many of the end-to-end processes. It includes improvements suggested by our user community through our GitHub issue list and Partner Advisory Board Focus Group. Download the latest version of the catalog from [https://aka.ms/businessprocesscatalog](https://aka.ms/businessprocesscatalog).

## Deprecated rows

The February 2025 version of the business process catalog includes rows with a **Catalog status** of *Deprecated*. These rows are no longer active and will be removed in the future release of the catalog. Many of these rows are moved to a location in the catalog. The **Alternate Process Sequence ID** column is used to indicate that the deprecated row is available in a new location in the catalog.

## XLSX files

We're pleased to announce that we changed all the file types to XLSX to better accommodate our global audience and eliminate issues with CSV files due to differing settings in different regions (such as the comma separator). The files are still available in the Microsoft Download Center with one file for each end-to-end process. You can also use the XLSX files to copy and paste if you use the Azure DevOps Excel add-in.

> [!NOTE]
> The custom work item types can't be changed directly in Azure DevOps. To use these new types, you must first create the work item types in your Azure DevOps instance.

## Process flow diagrams

We're excited to announce more process flow diagrams for Level 3 processes. These diagrams are generated with the help of AI and are available for download in our GitHub repository at [https://aka.ms/businessprocessflow](https://aka.ms/businessprocessflow). BPMN 2.0 cross-functional flow diagrams are now available for the following areas:

- *Acquire to dispose* (updated to match updates in the catalog)
- *Design to retire*
- *Hire to retire*
- *Order to cash*
- *Project to profit*
- *Record to report*

With this release, more than 700 Level 3 process flows are available. These flow diagrams are basic and can be used for any system an organization uses. We recommend using these diagrams to help accelerate the discovery process when implementing technology solutions such as Dynamics 365. These diagrams are intended to be used as a starting point and customized for each organization.

## Pitch decks by end-to-end processes

Ten ERP business process pitch decks are now available on Partner Hub. These decks are designed for Partners to help make the sales and discovery processes easier. Each deck aligns to the published business process catalog so that you can map each process area to the features and benefits of using Dynamics 365 to support those processes. Microsoft partners can download the resources from the Business Process Pitch Decks area on [Dynamics 365 Partner Hub](https://dynamicspartners.transform.microsoft.com/gtm/modernize-erp).

### Full list of ERP processes

- *Acquire to dispose*
- *Design to retire*
- *Forecast to plan*
- *Hire to retire*
- *Inventory to deliver*
- *Order to cash*
- *Plan to produce*
- *Project to profit*
- *Source to pay*
- *Record to report*

If you use the content and want to share your feedback, take a moment to complete the [Process Content Feedback](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR21YIT4_GIhKlpDfSHUiPFJUNkhDV0lLSEpTS05LNUxTVk5CUTVLSjY2MS4u&route=shorturl) survey.

## More metadata for configuration deliverables

We added several new columns to the catalog related to configuration deliverables to help further describe and filter the data. You must add these new custom columns into your Azure DevOps project in order to import the file. Here are the details:

- **Menu item name:** For finance and operations apps, the value includes the AOT menu item name. For configurations with customer engagement apps, the field value includes the portion of the URL with the page and view details.
- **Application family:** This is a picklist type field with three values: *Finance and operations apps*, *Customer engagement apps*, and *Cross-app*.
- **Product:** This is a picklist that indicates the specific product required for the configuration. The values in this field are as follows:

  - Commerce
  - Customer Insights
  - Customer Service
  - Field Service
  - Finance
  - Human Resources
  - Project Operations
  - Sales
  - Supply Chain Management
  - Other
  
## Comments for updates

Based on community feedback, we added a new column at the end of the business process catalog titled Update comments. These comments include additional information about the deprecated rows or updated rows in the catalog. We included the comments for the November 2024 updates and the February 2025 catalog in this release. This information in combination with the *Alternate process sequence ID* column makes it easier to understand and take updates in an existing Azure DevOps project.

## Improvements to Acquire to dispose processes

The *acquire to dispose* end-to-end process is updated to make areas and processes align with the marketing pitch deck. These changes enhance efficiency and clarity. Here are the key changes:

- **Updated names:** We updated the names of several Level 2 process areas and Level 3 processes to simplify and better reflect their functions.
- **Merged process:** We merged several level 2 process areas together to simplify the structure:
  - *Plan and budget assets* is deprecated and merged into *Acquire assets*.
  - *Manage internal assets* is deprecated and merged with *Manage and report on asset financials* and renamed to form the new *Manage active assets* process area.
- **New and updated scenarios:** Many new scenarios are added and most scenarios are updated to indicate which product the scenario is describing.

These improvements are designed to streamline operations and ensure that each process is clearly defined and efficiently managed.

## Changes to Case to resolution processes

With the updates in the pitch deck for *Order to cash*, the *Recall and return products* process area is now deprecated under the *Case to resolution* process. These processes and scenarios can now be found under various processes under the *Order to cash* end-to-end process.

## Improvements to Design to retire processes

The *design to retire* end-to-end process is updated to make areas and processes align with the marketing pitch deck. These changes enhance efficiency and clarity. Here are the key changes:

- **Updated names:** We updated the names of several Level 2 process areas and Level 3 processes to simplify and better reflect their functions.
- **Merged process:** We merged several level 2 process areas together to simplify the structure:
  - *Manage product pricing* is merged into the *Set product prices* Level 3 process under the *Introduce products* process area.
  - *Define product costing* is merged into *Maintain product costs* Level 3 process under the *Manage active products* process area.
- **New process areas:** We introduce two new process areas and related processes and scenarios to improve the end-to-end flow and coverage. Many of the processes and scenarios were under other areas before this update.
  - *Retire products*
  - *Analyze product performance*

## Improvements to Hire to retire processes

The *hire to retire* end-to-end process is updated to make areas and processes align with the marketing pitch deck. These changes enhance efficiency and clarity. Here are the key changes:

- **Updated names:** We updated the names of all Level 2 process areas and most Level 3 processes and scenarios to simplify and better reflect their functions.
- **Merged process:** We merged several level 2 process areas together to simplify the structure:
  - *Onboard and manage the employee lifecycle* is merged into the *Recruit and onboard talent* process area (which was renamed to reflect the merge).
  - *Manage travel and expenses* is merged into the *Manage compensation and benefits* process area.
- **New process areas:** We introduce two new process areas and related processes and scenarios to improve the end-to-end flow and coverage. Many of the processes and scenarios were under other areas before this update.
  - *Offboard talent*
  - *Analyze HR programs*

## Improvements to Order to cash processes

The *order to cash* end-to-end process is updated to make areas and processes align with the marketing pitch deck. These changes enhance efficiency and clarity. Here are the key changes:

- **Updated names:** We updated the names of several Level 2 process areas, many Level 3 processes, and most level 4 and scenarios to simplify and better reflect their functions.
- **Deprecated process:** We deprecated the *Manage store operations* process area. All the processes and patterns under *Manage store operations* are now moved to other business process areas. For example, processes related to policy, strategy, and setup are primarily moved to *Develop sales policies*. People-related processes are moved to *Hire to retire*, and system or device management-related processes are moved to the *Administer to operate* end-to-end process.
- **Merged process:** We merged *Record customer payments* into the *Invoice customers* process and renamed that to *Manage accounts receivable*.
- **New process areas:** We introduce one new process area and related processes and scenarios to improve the end-to-end flow and coverage. Many of the processes and scenarios were under other areas before this update.
  - *Analyze sales performance*

## Improvements to Project to profit processes

The *project to profit* end-to-end process is updated to make areas and processes align with the marketing pitch deck. These changes enhance efficiency and clarity. Here are the key changes:

- **Updated names:** We updated the names of several Level 2 process areas, many Level 3 processes, and most level 4 and scenarios to simplify and better reflect their functions. Here are the details:
  - *Govern projects* is now *Develop project strategy*
  - *Manage project resources and schedules* is now *Plan projects*
  - *Monitor and analyze project performance* is now *Analyze project performance*
- **New and updated scenarios:** We made significant updates and improvements to the scenarios under the *project to profit* area. All scenarios now indicate the product that the scenario represents including the deployment mode in parentheses.

## Service to cash is now Service to deliver

We renamed the *Service to cash* end-to-end process to be *Service to deliver*. The process areas that were duplicated in *Order to cash* and *Service to cash* are now deprecated under the new *Service to deliver* end-to-end process.

## Bug fixes

The following issues are corrected in the February 2025 catalog:

- Two processes had the same process sequence ID, 75.40.030.950. The row for 75.40.030.950 *Create direct delivery purchase orders from sales orders in Dynamics 365 Supply Chain Management* is deprecated and replaced by a new row for 75.40.030.925 *Create direct delivery purchase orders from sales orders in Dynamics 365 Supply Chain Management*.
- 75.10.060 *Develop spend strategy* and 75.10.070 *Analyze sourcing market* were listed under 75.20 *Define procurement catalogs*. This release corrects this and moved them under 75.10 *Develop procurement and sourcing strategy*. To correct this in an existing Azure DevOps project, you must delete the parent relationship before importing the file.
- Deprecated process areas that still had active processes: An issue that caused level 3 and 4 processes and scenarios under a process area is now corrected. Rows are updated as deprecated and alternate sequence IDs are populated for the new location of these rows.
- Deprecated processes that still had active scenarios: An issue that caused level 4 scenarios under a process is now corrected. Rows are updated as deprecated and alternate sequence IDs are populated for the new location of these rows.
- Orphaned configuration deliverables: An issue that caused some configuration deliverables to be orphaned and not linked to a business process has been corrected. These items now show as New under the correct process.
- Configuration deliverables linked to scenarios: An issue that caused configuration deliverables to be linked to scenarios is corrected. These items have had their incorrect relationship removed and corrected. When you import these items, you receive an error that a work item can't be linked to two parents. To correct this in an existing Azure DevOps project, you must delete the parent relationship before importing the file and saving the items.
- Missing or incorrect area paths: An issue that caused some items to have an incorrect or missing area path is now corrected. These rows are marked as updated in the February 2025 catalog.
- Missing parent links: There were various processes and scenarios primarily in *order to cash*, *source to pay*, and *record to report* that weren't linked to a parent work item. This causes the process to appear that it had no scenarios. These have been corrected and the rows show as New in the February 2025 catalog.

Many of these issues were reported by the community, and we want to thank you for continually bringing your feedback to help improve the quality of the Microsoft Business Process Catalog. You can report issues, provide feedback, and suggest improvements to the catalog by visiting [https://aka.ms/businessprocesscatalogrequests](https://aka.ms/businessprocesscatalogrequests).

## Related information

- [About the business process catalog for Dynamics 365 apps and services](about.md)  
