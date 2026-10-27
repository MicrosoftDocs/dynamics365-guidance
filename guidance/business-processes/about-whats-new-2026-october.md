---
title: What's new in the business process catalog in October 2026
description: Learn about October 2026 business process catalog changes, including rental processes, Azure DevOps import enhancements, and Mavim schema updates.
author: rachel-profitt
ms.author: raprofit
ms.reviewer: edupont
ms.service: dynamics-365
ms.subservice: guidance
ms.topic: concept-article
ms.date: 10/22/2026
ms.custom:
- bap-template
- ai-gen-docs-bap
- ai-seo-date: 10/31/2023
ai-usage: ai-assisted
---
# What's new in the business process catalog in October 2026

The business process catalog is a standard list of business processes across Dynamics 365 apps and services. Microsoft uses it to organize and prioritize work on business process documentation.

The catalog supports two formats:

- An Excel-based Azure DevOps template that you can import into your implementation backlog.
- A database package that you can import directly into Mavim.

The October release expands the business process catalog to **16,323 rows**, up from **6,834 rows** in July 2026. It adds **9,489 entries** and updates **6,524 existing entries**. The catalog also includes **24 deprecated entries** and **24 entries marked Deleted**.

Most of the growth adds executable detail at the System process and Test case levels. The largest expansions are in *Inventory to deliver*, *Record to report*, and *Design to retire*. The release also introduces a **Process type** classification that helps you distinguish setup, master data, transactional, analytical, and governance processes.

The Deliverables file adds **21 entries** and includes updates to descriptions, navigation, and Microsoft references. The Success by Design (SbD) Delivery Plan adds **five workshops** and includes Scope in its report export. The Objectives file is unchanged.

Download the latest version of the catalog from [https://aka.ms/businessprocesscatalog](https://aka.ms/businessprocesscatalog).

## At a glance

| Change type | Rows |
| --- | ---: |
| New | 9,489 |
| Updated | 6,524 |
| Unchanged | 262 |
| Deprecated | 24 |
| Deleted | 24 |
| **Total (October 2026)** | **16,323** |

The catalog adds most of its new detail at Levels 5 and 6:

| Work item type (level) | July 2026 | October 2026 | Change |
| --- | ---: | ---: | ---: |
| End to end (L1) | 15 | 16 | +1 |
| Process area (L2) | 94 | 101 | +7 |
| Process (L3) | 677 | 720 | +43 |
| Scenario (L4) | 3,592 | 3,892 | +300 |
| System process (L5) | 827 | 3,334 | +2,507 |
| Test case (L6) | 1,628 | 8,259 | +6,631 |

The overall totals also include the catalog's top-level row.

## New and expanded content

All 15 existing end-to-end processes receive new content. The release also introduces *Rent to return* as an end-to-end catalog entry. The additions are:

| End-to-end process | New rows | Highlights |
| --- | ---: | --- |
| Inventory to deliver | 1,582 | New warehouse replenishment, work and wave processing, shipping documents, shipment confirmation, inventory scrapping, and warehouse key performance indicator (KPI) processes. |
| Record to report | 1,358 | New escheatment content and expanded financial dimensions, fiscal books, accounting, reporting, and period-close detail. |
| Design to retire | 1,258 | Expanded system process and test case coverage beneath product design, engineering, costing, and product lifecycle scenarios. |
| Acquire to dispose | 784 | Expanded fixed asset, asset leasing, maintenance, and disposal system process and test case coverage. |
| Hire to retire | 738 | Expanded executable coverage for Human Resources setup, worker administration, benefits, leave, compensation, and related processes. |
| Order to cash | 662 | Expanded Commerce, customer, sales order, invoicing, payment, credit, and collection coverage. |
| Administer to operate | 613 | New environment provisioning, app deployment, Microsoft 365 and Azure resource provisioning, and agent governance processes. |
| Plan to produce | 573 | New costing-sheet and production-control policy scenarios, with broader production setup and execution detail. |
| Project to profit | 547 | Expanded project accounting, posting, billing, resource, and project delivery coverage. |
| Source to pay | 411 | Expanded procurement, vendor, and purchasing system process and test case coverage. |
| Forecast to plan | 257 | Expanded planning, forecasting, budgeting, and demand-planning coverage. |
| Prospect to quote | 200 | Expanded lead, opportunity, quotation, and sales process detail. |
| Service to deliver | 153 | Expanded service setup, scheduling, work order, and service execution detail. |
| Case to resolution | 132 | Expanded case management and customer service process coverage. |
| Concept to market | 130 | Expanded product ideation, introduction, and lifecycle process detail. |
| Rent to return | 91 | New end-to-end entry with six process areas, 25 processes, and 59 scenarios. |

### Rental-related processes

The release introduces the *Rent to return* end-to-end entry with six process areas, 25 processes, and 59 scenarios. The six process areas are:

- *Define rental strategy and policies*
- *Initiate rental agreements*
- *Fulfill rental agreements*
- *Manage active rentals*
- *Return rental equipment*
- *Analyze rental performance*

Separately, the release adds 76 rental-related scenarios across existing process branches. These scenarios cover fleet acquisition, depreciation, transfers, maintenance, disposal, rental pricing, invoicing, deposits, and customer service. Three new System process entries cover creating fleet purchase orders from configuration templates, transmitting fleet purchase orders to suppliers, and creating purchase orders for trade-in equipment. These cross-branch additions are separate from the 59 scenarios within *Rent to return*.

Thank you to **XAPT** and **CAT** for contributing to and reviewing the *Rent to return* catalog additions. The catalog also adds **NAXT365 from XAPT** as another software development company (SDC) solution.

### Inventory to deliver

*Inventory to deliver* receives the largest expansion, with **1,582 new rows**. The release adds six Level 3 processes:

- *Define warehouse management KPIs*
- *Replenish warehouse locations*
- *Scrap inventory*
- *Process warehouse work and waves*
- *Produce outbound shipping documents*
- *Confirm shipment and delivery*

The release also adds new scenarios for warehouse inventory adjustments, material movement analysis, warehouse integrations, freight classification, catch weight handling, warehouse work policies, mobile app configuration, packing operations, replenishment, shipping labels, packing slips, shipment confirmation, proof of delivery, and quality testing.

### Administer to operate

*Administer to operate* adds **613 rows** and introduces a new group of implementation and governance processes. New Level 3 processes cover:

- Provisioning Dataverse, finance and operations, Business Central, and Microsoft 365 environments.
- Deploying and installing Dynamics 365 apps and solutions.
- Provisioning supporting Azure and Microsoft 365 resources.
- Configuring calendars and electronic signatures.
- Registering and discovering agents.
- Managing agent identity and access.
- Securing and protecting agents.
- Governing agent data and compliance.
- Monitoring agent activity and performance.
- Managing the agent lifecycle.

These additions help you represent environment preparation, application deployment, and agent governance as part of the implementation process architecture.

### Record to report

*Record to report* adds **1,358 rows**, including the new Level 3 process *Manage escheatment*. New scenarios cover processing unclaimed checks, configuring fiscal books, and managing financial dimension defaults and integrations. Existing accounting, reporting, tax, consolidation, budgeting, and period-close scenarios receive additional system process and test case detail.

### Executable detail across the catalog

The release adds **2,507 System process rows** and **6,631 Test case rows**. This extra detail helps implementation teams connect business scenarios to application setup, navigation, and validation activities across Dynamics 365.

## Process type classification

The October release introduces the **Process type** field for Process, Scenario, and System process rows. The field uses the following values:

- **Setup** - configuration or policy-setting processes that prepare the system for operation.
- **Master data** - processes that create or maintain shared business records.
- **Transactional** - processes that execute day-to-day business events.
- **Analytical** - processes that monitor, report, forecast, or analyze business performance.
- **Governance** - processes that establish oversight, control, compliance, or decision frameworks.

Use this classification to filter the catalog, organize workshops, identify implementation dependencies, and distinguish operational processes from the setup and governance activities that support them.

## Updated content

Updates affect **6,524 existing entries** between July and October 2026. Updates include fit and gap defaults, navigation metadata, Microsoft Learn references, functional-area assignments, product and module alignment, and descriptions.

| Field | Rows updated |
| --- | ---: |
| Fit gap status | 5,911 |
| Gap solution approach | 5,880 |
| Menu path | 2,952 |
| Microsoft references | 2,208 |
| Area path | 2,232 |
| Menu item name | 1,848 |
| Module | 1,544 |
| Application family | 925 |
| Products | 578 |
| Description | 558 |

A row can have updates to more than one field.

Module values now cover more application navigation and service areas. This release uses **Retail and Commerce** in place of **Retail**. The full additional module choice list appears under [Mavim database updates](#mavim-database-updates). The **Products** list adds **Agent 365** and uses **Microsoft Copilot Studio** as the display name for the existing Copilot Studio product.

## Deliverables updates

The October Deliverables file contains **7,645 rows**, including **21 new entries**. It also advances **675 entries** to **Deleted**.

The largest deliverables updates are:

- Module alignment on 1,676 rows.
- Improved implementation descriptions on 1,397 rows.
- Updated Microsoft references on 790 rows.

These changes provide more consistent product navigation, clearer implementation context, and stronger links to Microsoft guidance.

## Deprecated rows

The October 2026 business process catalog includes **24 deprecated rows**, all in the first deprecation phase.

Deprecated rows remain visible for two releases so that you have time to update dependent implementation content. When a deprecated row is available in a new location, the **Alternate Process Sequence ID** column identifies the replacement.

Notable changes include:

- Inventory scrapping processes move from quality-management locations to a consolidated *Scrap inventory* structure.
- Warehouse key performance indicator content moves to the warehouse management policy area.
- Commerce, Sales, and Business Central sales scenarios are consolidated under updated product-specific sales structures.
- The *Configure and manage agents* process is replaced by the expanded agent governance process area.
- The older budget-control *Set thresholds and permissions* test case is deprecated in favor of the active replacement identified by its Alternate Process Sequence ID.

Review these rows and update any dependent implementation content before they reach the final deprecation phase and are marked Deleted in a later release.

## Deleted rows

**24 business process catalog entries** have **Deleted** status. They cover budget control setup, rules, commitment accounting and validation activities, manual budget entry in Dynamics 365 Business Central, and work order maintenance in Dynamics 365 Field Service. This set includes budget-control entries that completed their final deprecation phase in July.

If you maintain local mappings or backlog links to these entries, review the replacement information and update those dependencies to the current processes.

## Azure DevOps template updates

The October 2026 release refreshes the Azure DevOps work-item template that you can import to manage business process catalog projects in your own Azure DevOps organization.

### New field and picklist

- **Process type** - a new single-select field and picklist for classifying Process, Scenario, and System process work items as *Setup*, *Master data*, *Transactional*, *Analytical*, or *Governance*.

### Field and picklist changes

- **Module** - expands the allowed choices for application navigation and service areas, including *Customer Voice* and *Not applicable*. The full additional choice list appears under [Mavim database updates](#mavim-database-updates). The former *Retail* value is replaced by *Retail and Commerce*. Module is available as an optional field on Test case work items and remains excluded on Process work items.
- **Products** - adds *Agent 365* and renames the existing *Copilot Studio* choice to *Microsoft Copilot Studio*. Update the existing choice rather than creating a duplicate.
- **Application family** - replaces *Cross Functional* with the applicable application families. Select each family that applies rather than using a general placeholder. For integrations such as dual-write that span finance and operations apps (**F&O**) and customer engagement apps (**CE**), select both families.
- **Mandatory** - corrects the former *Manadatory* label. The field and the seven other existing Boolean fields are included in Deliverables exports, with `false` defaults only where applicable.
- **Impact severity** - keeps the Risk field separate from other impact fields. Its four existing choices and optional requirement are unchanged.
- **Article status** - adds **00 - Not applicable** and includes the field on Task work items. Use this value, with a Task-specific default, when an article isn't applicable. Keep **10 - Not started** as the default for work item types that use articles; preserve their existing article progress.

### Area paths for rental operations

The template adds two area paths for the new rental branch:

- **Business process catalog\Rent to return** - for the *Rent to return* end-to-end process, process area, and process work items (L1-L3).
- **Functional areas\Operations\Rental management** - for the scenarios (L4) within *Rent to return*.

Prefix these paths with your Azure DevOps project name. Area paths classify the work; they don't change its parent, identity, or position in the catalog hierarchy. Rental-related activities in other end-to-end processes keep their relevant functional ownership. For example, fixed-asset depreciation stays under **Finance\Accounting\Asset financials**, and customer invoicing stays under **Finance\Accounts receivable\Accounts receivable**. Don't move every activity that mentions rental equipment into Rental management.

The template update doesn't create these paths in an existing Azure DevOps project automatically. Apply the updated area paths configuration before importing work items that use them.

### Fix: missing fields on Integration and Migration

The template corrects an omission by including the existing **Fit gap status**, **Gap solution approach**, and **Business approval state** fields on both **Integration** and **Migration** work items. Use these fields to assess fit and gaps, plan gap resolutions, and track business approval for these deliverables.

The field definitions, defaults, and rules are unchanged. If you maintain an existing Azure DevOps process, add the existing fields to both work item types rather than creating duplicate fields. No new Mavim attributes are required.

### Retired dedicated Steps field

The Azure DevOps template retires the dedicated **Steps** field for Test case work items. The catalog **Description** column and its numbered instructions are retained. **Repro steps** remains available for Bug and Ticket work items.

Updating the template doesn't remove fields from your existing Azure DevOps processes. Review any dependencies before changing a customized process.

### Work item type changes

The process, scenario, and system process work item types include the **Process type** field. Test case work items don't include this field.  

Test case work items include the **Author** field. The **Business process flow author** and **Business process flow status** fields remain separate from **Author** and are blank on scenario, system process, and test case work items.  

**Module** is an optional field on test case work items so that you can retain the application-navigation context used by a test.  

> [!IMPORTANT]
> If you use the Excel-based Azure DevOps template, add the new **Process type** field and its picklist to your Azure DevOps process before you import the October 2026 catalog. Add the field only to the process, scenario, and system process work item types.

## Azure DevOps setup and import enhancements

**BPCTool** is a new contribution that provides a browser-based interface and a local Python runner for configuring Azure DevOps and importing the catalog. It builds on the workbook-driven setup approach of the July scripts, bringing setup, import, and reporting into a selectable workflow.

Thank you to **Bill Curtis from BDO** for the enhancements and contributions to the Azure DevOps import experience.

### A guided, selectable setup workflow

The interface organizes the work into seven steps: process template, page layouts, project, teams and areas, backlog and iterations, catalog import, and report. You can run a selected step, include its incomplete prerequisites, run from a selected step onward, or run all incomplete steps.

The tool reads the ADO template guideline and catalog workbooks from a release folder, rather than requiring a release-specific copy of the application. It supports the Business Process Catalog, Deliverables, Objectives, and SbD Delivery Plan workbooks. Keep each release's template and catalog files together in a separate folder so that an import doesn't mix versions.

### Plan, rehearse, then apply

**Preview plan** reads the local workbooks and shows planned steps, counts, warnings, and data checks without contacting Azure DevOps. **Rehearsal only** runs the selected workflow without changing Azure DevOps; it can read an existing project to compare its work items with the workbook. A live run applies changes to the selected organization, process, and project.

Review the target and planned changes before a live run. Rehearsal isn't the same as an offline plan preview. Follow the [BPCTool user guide](https://github.com/microsoft/dynamics365patternspractices/blob/main/templates/Azure-DevOps-templates/BPCTool/bpctool/USER_GUIDE.md) for prerequisites, personal access token permissions, and the Multivalue control extension requirements.

### Resumable imports and clearer results

The importer supports parallel processing, resume tracking, and parent-link backfill. It follows the workbook's **Title 1..N** outline to preserve the catalog hierarchy. Deprecated and deleted rows, and their descendants, are skipped by default.

Keep the project's **ado-id-map.csv** between runs: it maps catalog entries to created work items so that reruns can resume without creating those items again. Catalog field import is create-only for mapped entries; a rerun isn't an automatic field update of existing work items. Rehearsal can report differences that need review.

The results include HTML and JSON summaries, import failures, data adjustments made before import, skipped rows, and parent-link backfill results. Review these reports rather than treating a completed run as confirmation that every source value was imported unchanged. Keep reports private because they can contain catalog content and work item identifiers.

Get the tool from the [BPCTool folder in the Dynamics 365 patterns and practices repository](https://github.com/microsoft/dynamics365patternspractices/tree/main/templates/Azure-DevOps-templates/BPCTool). Learn more in the [BPCTool README](https://github.com/microsoft/dynamics365patternspractices/blob/main/templates/Azure-DevOps-templates/BPCTool/README.md) and [workflow and reference-script comparison](https://github.com/microsoft/dynamics365patternspractices/blob/main/templates/Azure-DevOps-templates/BPCTool/bpctool/docs/workflow-and-script-comparison.md).

## Mavim database updates

The October catalog introduces the **Process type** attribute for Process, Scenario, and System process topics, along with updated Module and Products choices.

If you maintain a customized Mavim repository, add Process type and its choices to a field set assigned to Process, Scenario, and System process topics. Include the attribute in your Business Process Catalog report and update your import or export mappings before loading the October catalog.

### Rental Area path choices

Add **Rent to return** and **Rental management** to the choices for the existing **Area path** attribute before importing the rental updates. These choices are new, not new attributes. Adding the choices can require a manual update in Mavim; updating the Azure DevOps template doesn't update the Mavim choice list.

Assign **Rent to return** to the branch's L1-L3 topics and **Rental management** to its L4 Scenarios. The transformation maps these short Mavim choices to the full Azure DevOps paths described in [Area paths for rental operations](#area-paths-for-rental-operations). Keep other process branches assigned to their relevant functional areas, and preserve topic IDs, parent relationships, and unrelated metadata.

### Article status for topics without articles

The **Article status** list includes **00 - Not applicable**. Use this choice for Success by Design **Task** topics, which don't use articles, instead of **10 - Not started** or an empty value. This choice distinguishes topics without articles from work where article authoring hasn't started.

Retain the shared **Catalog details** field set on Task topics. Don't remove the Article status attribute or change the default for topic types that use articles. Preserve their existing article progress, including published statuses. When upgrading a customized repository, add the choice only if it's missing and assign it only to the applicable non-article topics.

### Application family choices

The **Cross Functional** choice is retired. Use the specific application families that each process or deliverable supports.

When upgrading a customized repository, replace any existing Cross Functional assignments with the applicable families before removing the old choice. Include both F&O and CE for dual-write integrations that connect those application families. Review your records for missing family assignments after updating the choices.

### Module and product choices

Check the following **Module** choices and add only those missing from your customized repository. These choices are module values, not new product choices. Reuse an existing matching value rather than creating a duplicate:

- Administration
- Agent Map
- Agent Overview
- Agent Registry
- Agents
- Assembly management
- Azure API Management
- Azure Event Grid
- Azure Functions
- Azure Key Vault
- Azure Logic Apps
- Azure Monitor
- Azure Service Bus
- Azure Storage
- Business
- Business intelligence and reporting
- Customer Voice
- Customer support
- Customizations
- Data exchange
- Finance
- General business functionality
- Global inventory accounting
- Incoming documents
- Manufacturing
- Microsoft 365 Copilot
- Microsoft Access
- Microsoft Clipchamp
- Microsoft Designer
- Microsoft Excel
- Microsoft Forms
- Microsoft OneDrive
- Microsoft OneNote
- Microsoft Outlook
- Microsoft Planner
- Microsoft PowerPoint
- Microsoft Project
- Microsoft SharePoint
- Microsoft Teams
- Microsoft Whiteboard
- Microsoft Word
- Not applicable
- Online store with Shopify
- Operations
- Planning
- Project management
- Purchasing
- Quality management
- Relationship management
- Retail and Commerce
- Supplier Engagement app
- Support experience
- Sustainability management
- Syntex
- System
- System Settings
- Trade allowance management
- Vendor collaboration
- Workflow

For **Products**, add **Agent 365** if it is missing and update the existing **Copilot Studio** choice to **Microsoft Copilot Studio**. Don't create a second choice for the same product. Customer Voice, Contact Center, Customer Insights, and Microsoft Cloud for Sustainability remain available Product choices.

Use **Not applicable** only when a module doesn't apply, not when the value is unknown. Use the **System Settings** label and avoid adding a duplicate **Systems settings** choice. Include the appropriate product relationships and report settings when you add module choices.

Existing module labels also use consistent capitalization. Update the existing choices rather than adding duplicates: **Demand planning**, **Inventory management**, **Landed cost**, **Master planning**, **Organization administration**, **Procurement and sourcing**, **Product information management**, **Production control**, **Service management**, **Time and attendance**, **Transportation management**, and **Warehouse management**.

**Common** remains an existing Module value. When upgrading a customized repository, replace Retail assignments with **Retail and Commerce** before removing the old Retail choice.

### References for partner-provided content

For content supplied by an independent software vendor (ISV) or software development company (SDC), include the solution's **Microsoft Marketplace** or **AppSource** listing in **Microsoft references**. Microsoft Learn articles are optional additional references for this content. Use plain HTTPS URLs, one per line.

For published Microsoft-authored articles, Microsoft references must include the corresponding Microsoft Learn article.

### Business Process Catalog report fields

If you maintain a customized Business Process Catalog report, include these 13 additional fields. They expand export coverage without requiring new Azure DevOps field definitions:

- Automation status
- Baseline complexity
- Business process owner
- Industries
- Internal references
- Mavim ID
- Mavim reference
- Partner ID
- Priority
- Reason
- Scope approach
- Subject matter expert
- Workstream lead

Use **Not Automated** for Test case Automation status until the test's automation state is known. Leave that field blank on other topic types. Leave unknown owners, identifiers, priorities, and other optional values blank. Retain the existing **Author** field, including on Test cases.

### Deliverables report fields

The Deliverables report is separate from the Business Process Catalog report. For a customized Deliverables report, include these 26 additional fields:

- Acceptance criteria
- Approval levels
- Approval types
- Authorized for deployment
- Average daily volume
- Average hourly transactions
- Configuration variant key
- Current highest deployment
- Data cleansing strategy
- Data scrubbing technology
- Estimate (the standard Story points field)
- Estimated complexity
- Functional design
- Internal references
- Mavim ID
- Mavim reference
- Middleware
- Organizational scope type
- Organizational scope values
- Partner ID
- Partner references
- Peak hour volume
- Reason
- Technical design
- Transformation technology
- Validation method

Also include the eight Boolean fields added to Deliverables export coverage:

- Mandatory
- Can change later
- Can add later
- Early
- Gold environment
- Continuous
- At least one
- Multiple are recommended

Use **false** as the initial Boolean value only on applicable Configuration, Job, Report, and Workflow topics. Leave these fields blank on other topic types. Unknown optional estimates, volumes, designs, and deployment values remain blank. Don't use zero for an unknown estimate or volume, or infer deployment authorization from a blank value. **Partner ID** is reserved and remains blank in the Microsoft catalog.

Include each field only on its supported topic types, even when several topic types share a report. Reuse existing attributes rather than creating duplicates, and check your export mappings before loading the catalog.

### SbD Delivery Plan report field

The SbD Delivery Plan report includes **Scope** so you can export the recorded Scope values. Scope is an existing attribute, not a new Mavim attribute or Azure DevOps field.

If you maintain a customized Mavim repository, include Scope in your SbD Delivery Plan report. Maintain this report separately from the Business Process Catalog and Deliverables reports. Adding the column doesn't populate blank Scope values.

## Next steps

Review the [release history](about-whats-new.md) for catalog versions. Before importing the October release, review the template and report changes in this article and update your customized environment as applicable.

## Related content

- [Dynamics 365 guidance business process catalog](overview.md)
- [Understand the business process catalog for Dynamics 365 apps](about.md)
- [What's new in the business process catalog in July 2026](about-whats-new-2026-july.md)
- [Set up Azure DevOps with the Business Process Catalog July](about-configure-azure-devops-july.md)
- [Import the business process catalog in Mavim using the Mavim database file](about-import-catalog-mavim-database.md)
