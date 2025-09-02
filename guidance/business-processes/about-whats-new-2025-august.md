---
title: What's new or changed in the business process catalog August 2025
description: What's new or changed in the August 2025 version of the business process catalog that Microsoft publishes as a downloadable file.
ms.date: 09/02/2025
ms.topic: whats-new #Required; don't change.
ms.collection: #Required; Leave the value blank.
author: rachel-profitt
ms.author: raprofit
---

# What’s new or changed in the business process catalog in August 2025

The business process catalog is a standard list of business processes across Dynamics 365 apps and services. It's an Excel workbook that we at Microsoft use to organize and prioritize our work on the business process documentation. The August 2025 release of the catalog includes improvements across many of the end-to-end processes. It includes improvements that our user community suggested through our GitHub issue list and Partner Advisory Board Focus Group.  

Download the latest version of the catalog from [https://aka.ms/businessprocesscatalog](https://aka.ms/businessprocesscatalog).

## Deprecated rows

The August 2025 version of the business process catalog includes rows with a **Catalog status** of **Deprecated**. These rows are no longer active and will be removed in the future release of the catalog. Many of these rows are moved to a location in the catalog. The **Alternate Process Sequence ID** column specifies if the deprecated row is available in a new location in the catalog.

## Deleted rows

The August 2025 version of the business process catalog includes rows with a **Catalog status** of **Deleted**. Any row that is marked as deleted won't be included in future releases of the catalog. If you actively use a row that is now tagged as deleted, we recommend that you update your catalog to use the row that is designated in the **Alternative process sequence ID** column for the deleted entry.

## Process flow diagrams

We are excited to announce more process flow diagrams for Level 3 processes. These diagrams are generated with the help of AI, and you can download them from our GitHub repository at [https://aka.ms/businessprocessflow](https://aka.ms/businessprocessflow). We added Business Process Model and Notation (BPMN) 2.0 cross-functional flow diagrams for the following areas:
-	*Prospect to quote*
-	*Administer to operate*

These flow diagrams are basic and can be used for any system an organization uses. We recommend using these diagrams to help accelerate the discovery process when implementing technology solutions such as Dynamics 365. These diagrams are intended to be used as a starting point and customized for each organization.

## Workshops templates

We're excited to announce more discovery workshop templates in the business process catalog. These templates were generated with the help of AI, and you can download them from our GitHub repository at [https://aka.ms/businessprocessworkshops](https://aka.ms/businessprocessworkshops). Word document templates for discovery workshops are now available for the following areas:
-	*Case to resolution*
-	*Concept to market*
-	*Plan to produce*
-	*Project to profit*
-	*Record to report*
-	*Service to deliver*

## Improvements to Prospect to quote

We gave the *Prospect to quote* end-to-end process a comprehensive overhaul to better align with evolving market demands and the Dynamics 365 product ecosystem. 
Here are the key changes:
-	All business process areas (L2) and related L3 scenarios have new numbers.
-	Added a new L2 for *Analyze sales*. 
-	The L3 business processes are now simpler in structure to better align with sales operations. 
-	New L4 scenarios are added to better align with Dynamics 365 Sales functionality and related Copilot capabilities. 

We continue to enrich and enhance the L3 and L4 processes as new features are released in the coming months. 

## Improvements to Service to deliver

Based on feedback from the community, we continue to improve the *Service to deliver* end-to-end process. Here are the key updates in this release.
-	95.05 *Develop service strategy* has four new processes.
-	95.15.600 *Manage service assets* moved from 95.25 to 95.15
-	95.25 *Process service orders* is now *Manage service work*, and it has two new L3 processes.
-	95.35 *Run service operations* is now *Deliver services*, and it has four new L3 processes.
-	The processes under 95.45 are renamed for more clarity.

## Improvements for the retail and manufacturing industries

We made minor improvements across many end-to-end processes based on community feedback. We thank the team at Avanade for their feedback to improve the completeness and coverage of processes and scenarios for the retail and manufacturing industries. Thank you, the team at Avanade, for your time, expertise, and contributions.

## Updated deployment names in Project to profit

In this release, the deployment names for Dynamics 365 Project Operations reflect the recent updates for the product. We updated the L4 scenarios to reflect the new names of the deployment modes to match the product names. Learn more about the changes to the product at [Dynamics 365 Project Operations deployment modes](/dynamics365/project-operations/procurement/enable-stocked-products-integrated). Learn more about selecting the correct deployment mode for your project at [Determine your deployment type](/dynamics365/project-operations/environment/determine-deployment-type).

> [!NOTE]
> Rows that read *Dynamics 365 Project Operations* without a deployment option apply to both Dynamics 365 Project Operations Core and Dynamics 365 Project Operations Integrated with ERP. These rows are not modified in this release.

## Improved descriptions

We continue to improve and enrich the business process catalog data in each release. This release includes improved description for the following Level 2 business process areas and Level 3 scenarios:
-	*Order to cash*
-	*Source to pay*

The improved description helps drive discovery sessions with customers and help all users have a clearer understanding of the scope of a particular business process. We will continue to enhance descriptions in future releases. We thank Red Cat Consulting and Team Bennett Consulting for their help to make these descriptions available to all users. 

## Corrected values for process sequence ID

The community reported the issue that some work items in the catalog had a mismatch between the ID in the work item title and the value of the **Process sequence ID** field. The August 2025 release fixes this issue. There are a few types of updates that were made:
1.	**Corrected ID in the name** – These rows have the status **Updated**, and the **Update comments** field reads *Corrected ID in the name*. When you import these work items into an existing Azure DevOps project, you can match the rows to your existing rows based on the **Process Sequence ID** column.
2.	**Corrected process sequence ID** – These rows have the status **Updated**, and the **Update comments** field reads *Corrected Process sequence ID*. When you import these work items into an existing Azure DevOps project, you can't make a match on the **Process sequence ID** column. Instead, you must match based on the title of the work item. 
3.	**Corrected misnumbered name and process sequence ID** – These rows had an incorrect ID in both the **Title** and the **Process Sequence ID** columns. In this case, both columns were updated. We recommend that you manually find and correct these rows in your existing Azure DevOps template before you import the business process catalog. The **Update comments** column reads *Corrected misnumbered name and process sequence ID*.

> [!WARNING]
> If you modified the names of your work items, use caution when you import the file with the updates from the August 2025 version. We recommend that you test and validate the updates carefully in your environment. An easy way to test the impact is to export your current Azure DevOps work items to Excel, and then using an XLOOKUP function to compare the old file to the new file. Learn more at [XLOOKUP function](https://support.microsoft.com/office/xlookup-function-b7fd680e-6d10-43e6-84f9-88eae8bf5929).

## Added workload types
This release continues the work to populate the **Workload type** field with values across all level 4 scenarios. The updated rows now show the status **Updated**, and the **Update comments** field reads *Added workload type*.

## Module updates

In earlier versions of the catalog, some rows specified the wrong names of product modules. In this version, we changed the values *Accounts payables* to *Accounts payable* and *Accounts receivables to *Accounts receivable*, respectively.

Also, the May 2025 version of the business process catalog added many new modules to the catalog. The [Use the business process catalog as a template in Azure DevOps Services](about-import-catalog-devops.md) article now lists all modules that you must add so that you can import the catalog. Here's the list of modules that you must add:
-	App Settings
-	Demand Planning
-	Engineering Change Management
-	Inventory
-	Landed Cost
-	Personal Settings
-	Project Management & Accounting
-	Projects
-	Rebate Management
-	Resources
-	Sales & Marketing
-	Sales Insights Settings
-	Scheduling
-	Settings

## Related information

- [About the business process catalog for Dynamics 365 apps and services](about.md)  
