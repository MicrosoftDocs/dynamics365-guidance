---
title: What's New in the Business Process Catalog in July 2026
description: What's new or changed in the July 2026 version of the business process catalog that Microsoft publishes as a downloadable file.
author: rachel-profitt
ms.author: raprofit
ms.reviewer: edupont
ms.service: dynamics-365
ms.subservice: guidance
ms.topic: concept-article
ms.date: 07/14/2026
---
# What's new in the business process catalog in July 2026

The business process catalog is a standard list of business processes across Dynamics 365 apps and services. Microsoft uses it to organize and prioritize work on the business process documentation.

You can access the catalog in two formats:

- As an Excel-based Azure DevOps template that you can import into your implementation backlog.
- As a database package that you can import directly into Mavim.

The July 2026 release expands the business process catalog to 6,834 rows, up from 5,874 rows in March 2026. This release adds 960 rows, updates 2,569 rows, and moves 25 previously deprecated rows into the second deprecation phase, which means they're scheduled for deletion in the next release. No rows are deleted in this release. The largest changes are a significant expansion of *Order to cash* system process and test case coverage, and new Finance localization and reference-data processes across *Record to report*, *Administer to operate*, and *Source to pay*. This release also refreshes the Azure DevOps template. Special thanks to the team at Globalix 365 for contributing more than 400 new rows of standard out-of-the-box localizations and their Marketplace solution to the catalog in this release.

The catalog file also gains a new **Business process flow author** column, which records the author of a business process flow (for example, *Microsoft*) in its own column, separate from the existing **Business process flow status** column.

The **Deliverables** file receives metadata updates to 1,527 rows, led by article-status refreshes. The **Delivery Plan** and **Objectives** files are unchanged.

Download the latest version of the catalog from [https://aka.ms/businessprocesscatalog](https://aka.ms/businessprocesscatalog).

## At a glance

| Change type | Rows |
| -- | -- |
| New | 960 |
| Updated | 2,569 |
| Unchanged | 3,280 |
| Deprecated | 25 |
| Removed | 0 |
| **Total (July 2026)** | **6,834** |

Most of the growth is at the lower levels of the hierarchy, where the catalog adds executable detail:

| Work item type (level) | March 2026 | July 2026 | Change |
| ---------------------- | ---------- | --------- | ------ |
| End to end (L1)        | 15         | 15        | 0      |
| Process area (L2)      | 94         | 94        | 0      |
| Process (L3)           | 674        | 677       | +3     |
| Scenario (L4)          | 3,557      | 3,592     | +35    |
| System process (L5)    | 451        | 827       | +376   |
| Test case (L6)         | 1,082      | 1,628     | +546   |

## New and expanded content

New content is concentrated in four end-to-end processes.

| End-to-end process | New rows | Highlights |
| -- | -- | -- |
| Order to cash | 600 | 283 new system processes and 316 new test cases that deepen sales-order and receivables coverage. |
| Record to report | 249 | New Finance localization (LATAM taxes and fiscal information), fiscal document policies, and Invoicing 365 Software Development Company Solution added. |
| Administer to operate | 66 | New address and location reference-data processes and reporting service references. |
| Source to pay | 37 | New vendor classification and vendor set processes. |
| Inventory to deliver | 5 | Two new system processes with supporting test cases. |
| Prospect to quote | 3 | One new system process with test cases. |

### Order to cash

*Order to cash* receives the largest expansion this release, with 600 new rows - 283 system processes and 316 test cases - that add step-level, testable detail beneath existing scenarios. A new scenario, *Manage customer sets in Dynamics 365 Finance* (`65.05.030.300`), is also introduced. 390 existing *Order to cash* rows are updated with refreshed metadata.


### Record to report

*Record to report* adds 249 new rows, including a new Level 3 process, *Define fiscal document policies* (`90.10.300.000`). The new content centers on Finance localization and reference data, for example:

- LATAM posting, dimension allocation, and bank parameters.
- LATAM withholding taxes, tax groups, and withholding base calculation.
- LATAM tax ID types, taxpayer types, and country/region and state fiscal information.
- Company (legal entity) setup with Invoicing 365 in Dynamics 365.

### Administer to operate

*Administer to operate* adds 66 new rows, including a new Level 3 process, *Define address and location policies* (`99.20.300.000`). The new processes cover core geographic reference data - *Manage country/regions*, *Manage states*, *Manage counties*, *Manage cities*, and *Manage districts* in Dynamics 365 Finance - along with management of SQL Server Reporting Services (SSRS) report and service references.

### Source to pay

*Source to pay* adds 37 new rows, including a new Level 3 process, *Define vendor classifications* (`75.10.050.000`), and the *Manage vendor sets in Dynamics 365 Finance* scenario (`75.10.050.100`). *Source to pay* also has the largest volume of updated content this release, with 1,409 rows refreshed - most of which were part of a cleanup that removed the *Scope* field from the work item types that shouldn't include it.


## Updated content

2,569 rows are updated between March and July 2026. Updates are dominated by metadata alignment and field-scope cleanup rather than structural change. The most frequently updated fields are:

| Field                        | Rows updated |
| ---------------------------- | ------------ |
| Scope                        | 1,396        |
| Business process flow status | 783          |
| Microsoft references         | 443          |
| Area path                    | 405          |
| Description                  | 389          |
| Products                     | 385          |
| Application family           | 383          |
| Module                       | 304          |
| Menu path                    | 122          |
| Menu item name               | 108          |

The most frequently changed field, **Scope**, reflects a cleanup: the Scope field was removed from the work item types that shouldn't include it, so those rows no longer carry the *10 - Unspecified* placeholder. The next field, **Business process flow status**, reflects the new **Business process flow author** column described earlier - the author value (for example, *Microsoft*) moved into its own column. Both are metadata or structural changes rather than new content.

Updates by level: Test case (1,006), Process (674), System process (421), Scenario (384), Process area (94), and End to end (15). The end-to-end processes with the most updates are *Source to pay* (1,409), *Order to cash* (390), *Administer to operate* (149), *Record to report* (81), *Inventory to deliver* (77), and *Hire to retire* (71). The high *Source to pay* count is largely the Scope-field cleanup applied to its test cases.

## Deprecated rows

The July 2026 catalog includes 25 rows that were deprecated in a previous release and are now in their second deprecation phase, which means they're deleted in the next release. Deprecated rows are no longer active, but they remain visible in the catalog for two releases so that you have time to react before the content is removed. When a deprecated row is available in a new location, the **Alternate Process Sequence ID** column identifies the replacement row.

Most of the deprecations are in the *Source to pay* budget control setup block (`75.10.060.*`), which covers configuring budget control parameters, funds-available formulas, budget control rules and groups, thresholds and permissions, commitment accounting, and budget control activation, together with their test cases. Two more scenarios are deprecated:

- *Enter budget amounts manually into Dynamics 365 Business Central* (`90.30.050.110`)
- *Maintain work orders in Dynamics 365 Field Service* (`95.25.200.400`)

Review these rows and update any dependent implementation content before the content is retired in a future release.

## Azure DevOps template updates

The July 2026 release also refreshes the Azure DevOps (ADO) work-item template that partners and customers import to run business process catalog projects in their own ADO organization. If you already imported the Preview template, review these changes before re-importing or updating your project.

### New field and picklist

- **Business approval state** — a new field is added to the template, backed by a new *Business approval state* picklist. Use it to track the approval state of a work item. This new field is added for the Requirement work item type.

### Field and picklist changes

- **Business process flow source** — the default value is corrected from *10 - Not started* to *Microsoft*, and the picklist value *Microsoft original* is renamed to *Microsoft*.
- **Field use recommendation** — the former *Partner recommendations* column is renamed to *Field use recommendation* to better describe how each field should be used.
- **Module** picklist — adds *Leave and absence*, *Product information management*, and *Sales insights settings*, and corrects the misspelled *Production information management* value to *Product information management*.
- **Products** picklist — adds *Contact Center*, *Customer Insights*, and *Microsoft Cloud for Sustainability*.

### Work item type changes

- The *Data type* field moves from the **Job** work item type to the **Migration** work item type.
- The **Requirement** work item type no longer inherits from the base Requirement type.
- Two new columns — *Business process flow source* and *Business approval states* — are added to the work item type definitions.

> [!IMPORTANT]
> If you use the Excel-based Azure DevOps template, create the new **Business approval state** field in your Azure DevOps project before you import the July 2026 catalog.

## Azure DevOps setup automation

This release also updates the Python automation scripts that accompany the Excel-based Azure DevOps template. The scripts move from a set of individual scripts that you run in sequence to an end-to-end guided setup wizard that runs the setup in six phases: create the process and project, configure work item layouts and controls, create teams and area paths, configure backlogs and iterations, import the catalog work items, and generate a summary report. Key improvements include:

- A resumable catalog importer that creates parent work items before children, skips rows that were already imported when you rerun, and skips *Deprecated* and *Deleted* rows.
- Stronger validation and retry behavior, including transient-error retries and configurable parallel workers.
- Project-scoped output folders and a deterministic HTML summary report with import counts, quick links, and failure reconciliation.

Learn more about the setup wizard phases, catalog importer behavior, personal access token (PAT) scope recommendations, and known limitations at [What's new in the July release for setting up Azure DevOps based on the business process catalog](about-configure-azure-devops-july-whats-new.md).

## Mavim-powered process visualization in the Dynamics 365 Implementation Portal

The Dynamics 365 Implementation Portal now brings business process context directly into the project profiling experience through integration with Mavim and the business process catalog.

As part of project profiling, solution architects can access visual business process flows directly from the business process profile control. Select a business process and use the information icon to open the corresponding process visualization, powered by Mavim, without leaving the portal.

### Why it matters

Project profiling helps implementation teams identify the products, capabilities, and business processes that are in scope for a project. With process visualizations, teams can:

- Align more quickly on standard Microsoft business processes during discovery and scoping.
- Improve workshop preparation with a shared visual understanding of end-to-end processes.
- Reduce ambiguity by using governed, maintained process content instead of static diagrams.
- Create a stronger foundation for implementation planning, guidance, and downstream activities.

### What's included

This initial release introduces:

- Business process visualizations embedded within the project profiling experience.
- Direct access to business process catalog flow diagrams through Mavim.
- Unified project profiling across products, characteristics, and business processes.
- Process context available exactly where implementation teams make scoping decisions.

### Looking ahead

This integration is an early step toward a more connected implementation experience. Planned future capabilities include profile import and export between the Implementation Portal, Mavim, and Azure DevOps; expanded implementation scenarios that carry process scope into downstream artifacts; and AI-powered experiences that reason over structured business process information to provide more intelligent guidance and recommendations.

By bringing governed process knowledge directly into project profiling, this release lays the foundation for richer implementation guidance and future agent-assisted implementation experiences built on a shared process model.

## Related information

- [Dynamics 365 guidance business process catalog](overview.md)
- [Understand the business process catalog for Dynamics 365 apps](about.md)
- [What's new in the July release for setting up Azure DevOps based on the business process catalog](about-configure-azure-devops-july-whats-new.md)  
