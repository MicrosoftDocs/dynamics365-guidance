---
title: What's New in the Business Process Catalog in March 2026
description: What's new or changed in the March 2026 version of the business process catalog that Microsoft publishes as a downloadable file.
author: rachel-profitt
ms.author: raprofit
ms.date: 01/07/2026
ms.topic: concept-article
---

# What's new or changed in the business process catalog in March 2026

The business process catalog is a standard list of business processes across Dynamics 365 apps and services. Microsoft uses it to organize and prioritize work on the business process documentation.

For the first time, the Business Process Catalog is now in the two formats:

- As an Excel‑based Azure DevOps (ADO) template, enabling structured import into implementation backlogs.
- As a database package that you can import directly into Mavim.

Microsoft now manages the Business Process Catalog directly within Mavim as the system of record, enabling improved governance, consistency, and alignment between process architecture and delivery execution.

This release introduces several new configuration areas, structural updates, and automation capabilities designed to improve implementation readiness and reduce manual mapping during discovery and design phases. 

Download the latest version of the catalog from [https://aka.ms/businessprocesscatalog](https://aka.ms/businessprocesscatalog).

## Deprecated rows

The March 2026 version of the business process catalog includes rows with a Catalog status of **Deprecated**. These rows are no longer active and are removed in a future release of the catalog. Many of these rows are moved to a new location in the catalog. The **Alternate Process Sequence ID** column indicates that the deprecated row is available in a new location in the catalog.

## Deleted rows

The March 2026 version of the business process catalog includes rows with a catalog status of **Deleted**. Any row that is marked as *Deleted* is no longer included in the catalog in future releases. If you're actively using a row tagged as *Deleted*, update your catalog to use the row that is designated in the **Alternative process sequence ID** field.

## Dynamics 365 Contact Center configurations

The catalog now includes configuration‑level processes specific to Dynamics 365 Contact Center and Customer Service deployments. With these new configurations, partners and customers can now:

- Align customer service operating models to platform configuration earlier in the implementation lifecycle
- Trace business process requirements directly to Contact Center setup decisions
- Reduce ambiguity between service design and system configuration during solution blueprinting

This supports improved collaboration between business architects and technical solution teams by creating a shared reference between operational service flows and implementation backlog items.

> [!IMPORTANT]
> Organizations currently using a prior version of the catalog should:
>
> - Review newly introduced Dynamics 365 Contact Center configuration processes
> - Map existing customer service backlog items to these processes where applicable
> - Import the updated catalog into ADO or Mavim to enable traceability between service design and platform setup

## Power Platform environment settings configurations

New processes have been introduced to support Power Platform environment‑level configuration decisions. With these new configurations, partners and customers can now:

- Capture governance and environment strategy decisions as part of the business process architecture
- Align ALM, security, and environment configuration activities with business capability requirements
- Ensure environment setup tasks are represented in implementation planning alongside functional solution processes

This helps prevent environment configuration from becoming an undocumented or late‑stage implementation dependency.

> [!IMPORTANT]
> Customers and partners maintaining local catalog copies should:
>
> - Evaluate current environment setup work items or deployment checklists
> - Map these activities to the new configuration processes
> - Re‑import the March 2026 catalog to ensure environment configuration work is captured within implementation scope

## Software development company updates

This release introduces two new metadata columns to support improved alignment between business process architecture and solution‑level implementation activities:

- Software Development Company
- Software solutions

These attributes are used to identify solution‑specific implementation ownership across Microsoft applications and ISV‑provided capabilities. The addition of these columns enables:

- Traceability between standard business processes and solution‑specific implementation scenarios
- Representation of Marketplace solution capabilities within the Business Process Catalog hierarchy
- Structured alignment between ISV functionality and implementation backlog items
- Support for mapping partner or third‑party solution behaviors to:
  - Scenarios
  - System Processes
  - Test Cases
  - Deliverables

As part of this release:

- Existing rows within the Business Process Catalog have been updated with values for these new attributes
- Two new Software Development Companies have been added to the standard catalog

These enhancements enable implementation teams - to represent both Microsoft‑provided and Marketplace‑provided capabilities within a unified process architecture.
Microsoft invites Marketplace solution providers to contribute implementation‑ready process content aligned to their offerings by extending the catalog with:

- Business Scenarios
- System Processes
- Test Cases
- Deliverables

This allows partner and Software Development Company solutions to become more discoverable and implementation‑ready for customers and other delivery organizations.

Customers and partners using the Excel‑based Azure DevOps template must create the following fields in Azure DevOps prior to importing the March 2026 catalog:

- Software Development Company
- Software Solutions

## Terminology and functional area alignments

This release includes updates to both process terminology and functional area classification to better align the Business Process Catalog with current Dynamics 365 application architecture and implementation activities. The following changes have been made:

- The Personalization work item type has been renamed to User interface
- The Sales functional area has been renamed to Customer experience

These updates improve:

- Alignment between catalog terminology and Dynamics 365 Customer Engagement application family naming conventions
- Representation of implementation activities that extend beyond individual user preferences to include:
  - Form and view configuration
  - Navigation structure
  - Role‑based experiences
  - Interaction design

Renaming the Sales functional area to Customer Engagement also reflects expanded catalog coverage acrossv Sales, Customer Service, and Contact Center.

This supports a more complete representation of customer lifecycle processes and reduces ambiguity when mapping implementation backlog items to platform capabilities across Dynamics 365 customer engagement apps workloads.

> [!IMPORTANT]
> Partners and customers using a prior version of the catalog should review the following implementation considerations before importing the March 2026 release.

### Personalization → User Interface (Work Item Type)

Azure DevOps does not support renaming existing work item types. If an active implementation project wishes to adopt the updated User Interface terminology within Azure DevOps, the following steps are required:

- Create a new Work Item Type called User Interface within the existing ADO project
- Perform a data migration from existing Personalization work items to the new User Interface work item type

Alternatively, organizations that wish to retain the previous Personalization work item type may:

Update the March 2026 Business Process Catalog spreadsheet prior to import by:

- Finding all values labeled User Interface
- Replacing these values with Personalization

This approach allows the updated catalog content to be imported into an existing Azure DevOps project without requiring work item type creation or data migration.

### Functional Area: Sales → Customer Engagement

Updating the Sales functional area to Customer Engagement does not require creation of a new work item type. Organizations may simply update the existing Functional Area value from Sales to Customer Engagement within their Azure DevOps project. Customers and partners should also validate any reporting logic, filters, or queries that reference the Sales functional area following import of the March 2026 catalog.

## Public Preview: Azure DevOps Template Python Scripts

Automation scripts supporting the Excel‑based Azure DevOps (ADO) template are now available in Public Preview. The updated ADO template and supporting Python automation scripts enable:

- Automated creation of implementation backlog items based on Business Process Catalog processes
- Structured population of Azure DevOps work items aligned to the business process hierarchy
- Improved traceability between discovery outputs and implementation planning artifacts
- Reduced manual effort during discovery‑to‑implementation transition

Microsoft recommends that new implementation projects begin using the March 2026 Azure DevOps template to take advantage of these automation and alignment capabilities. To access the new preview tempaltes, visit [https://aka.ms/BPCADOTemplate](https://aka.ms/BPCADOTemplate). To learn more about how to install and use the template, see [Configure Azure DevOps process and project](about-configure-azure-devops-project-processes.md).

> [!IMPORTANT]
>
> - For new implementation projects, we recommend that you start with the March 2026 Azure DevOps template as the foundation for implementation backlog creation and delivery planning.
> - For existing or in‑progress implementation projects customers and partners should carefully evaluate whether transitioning to the new ADO template is appropriate for the current stage of delivery.

There is no automated migration path from an existing or customized Azure DevOps process template into the March 2026 ADO template. Adopting the updated template within an active project would require:

- Creation of a new Azure DevOps project using the March 2026 template
- A full data migration of existing Azure DevOps work items into the new project

Partners and customers should assess the effort required to migrate implementation backlog data before deciding to transition an in‑flight project to the updated template.

## Mavim database updates
The March 2026 release of the business process catalog is now available in the Mavim database format. You can download the MTDX file from the Microsoft Download Center the same way that you download the Excel-based Azure DevOps version. To dowonload the catalog, visit [https://aka.ms/businessprocesscatalog](https://aka.ms/businessprocesscatalog). To learn more, see [Import the Microsoft business process catalog into Mavim using the database](about-import-catalog-mavim-database.md).

When you use the Mavim to manage your business process catalog, there are additional features and changes to the catalog data that are not provided in the Excel version.

- New icons provided for all Microsoft Products and Application families
- All workshops are updated to include the detailed workshop content in the Word editor. 
- Cleaned up the duplicated unused topics in the Dynamics 365 Related Categories node. This includes the following:
  - Workshops (you can find the workshops in the Success by Design Delivery Plan node)
  - Tasks (you can find the tasks in the Success by Design Delivery Plan node)
- New icon for Area paths node
- Added Area path full path field to all area paths. This new field maps the area path values to the area path values in Azure DevOps. The top node area path named "Project name" should be renamed to match your project and the Area path full path value is set to "Your Project Name Here" which should also be updated to your projects root area path node if you plan to integrate your Azure DevOps environment with Mavim.
- Relationships are created between Application families and Products nodes.
- A new folder of End to end journeys under the Navigation node is now available. This node includes new charts that match the current pitch deck curvy line flow diagrams that are used across all the end to end processes. You can optionally use these new navigation pages in the Mavim collaboration portal as an alternative navigation for drilling down through the various catalog levels. The following image shows the new alternative navigation page. You can optionally set this as the home page or link to your existing home page in Mavim.

:::image type="content" source="media/mavim-end-to-end-journey-navigation.png" alt-text="A large curved line showing each of the 15 end to end processes with icons for each and a series of boxes below the line for navigating the deliverables, workshops, and Success by Design elements.":::

## Downloadable workshop templates are deprecated
We will no longer maintain the Word documnet format in the GitHub repository for any workshops. The current version of the Word documents will remain available in the GitHub repository for one year at which time they will be deleted. We recommend that you leverage Azure DevOps or Mavim to manage and help you execute the workshops where the data for the workshops will be maintained.

## Related content

- [Automate Azure DevOps project, process, work item types, fields, and picklists from Excel with Python](about-configure-azure-devops-project-processes.md)  
- [About the business process catalog for Dynamics 365 apps and services](about.md)  
