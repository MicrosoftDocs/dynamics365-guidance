---
title: Migrate legacy work orders into Field Service and Project Operations integration
description: Migrate legacy work orders into Dynamics 365 Field Service and Project Operations with phased data planning, project mapping, validation, and cutover guidance.
author: vhorvathms
ms.author: vhorvath
ms.reviewer: v-wesmith
ms.topic: overview
ms.collection: #Required; Leave the value blank.
ms.date: 11/06/2026
ms.custom: bap-template #Required; don't change.
---

# Migrate legacy work orders into Field Service and Project Operations integration

This project involves migrating work orders that currently exist only in a legacy external system into Dynamics 365 Field Service and linking them to the appropriate Project Operations records so that labor, material usage, and costs are associated with the correct project and financial structure.

Two distinct pieces are covered:

- Data migration — Extracting, transforming, and loading legacy work orders and related reference data into Dataverse and Field Service.

- Project linkage — Mapping each migrated work order, and where applicable an agreement, to the appropriate Project Operations records, including Project, Project Task, Project Contract, and organizational context.

## Prerequisites

Before starting the migration, ensure the following prerequisites are met.

### Licensing and security

- A Project Operations license is required for users who perform Project Operations activities such as project task management. Project task management is done in Project Operations — the Project Tasks view on a project isn't surfaced in Field Service for users to manage, and project tasks are exposed only as part of the linking experience.

- A Project Operations license isn't required simply to link a Field Service work order to an existing Project or Project Task from Field Service.

- Users performing the linking activity in Field Service should have the appropriate Field Service Dispatcher or Field Service Administrator security role.

- The Field Service linking experience is covered under Field Service licensing. Field Service exposes the necessary Project Operations forms so that users can access and link the relevant Project Operations records without working directly in the Project Operations app.

- The user who installs the Field Service and Project Operations integration package must have at least one Project Operations license.

### Project and financial reference data

Before migrating transactional work orders, create or migrate the Project Operations and Field Service reference records that the work orders reference. Depending on the scenario, this data can include:

- Service Account

- Owning Company, when the environment is integrated with Dynamics 365 Finance

- Project

- Project Task, when the work order is associated with a specific task

- Project Contract, for customer-billable project scenarios

- Project Contract Line

- Billing Method, such as Time and material or Fixed price

#### Customer-billable projects

For customer-billable projects, establish the applicable Project Operations commercial structure before migrating the related work orders. This structure includes:

- Project

- Project Contract with an Order Type of Work-based

- Project-based Contract Line

- Billing Method

- Applicable Project Line Customer

- Supported transaction types for the Field Service transactions that are generated, such as labor and material transactions

The Work Order Service Account should correspond to the applicable Project Line Customer on the Project Contract Line.

When the environment is integrated with Dynamics 365 Finance, also migrate and align the applicable Owning Company/legal entity used by the work order and project financial structure.

#### Projects that don't use customer billing

Where the installed integration release supports linking work orders to projects that don't use customer billing, those projects don't require a Project Contract, Project Contract Line, Billing Method, or Project Line Customer. Confirm that the target package supports this scenario before designing a no-contract migration path.

> [!IMPORTANT]
> Load configuration and foundational reference data (accounts, price lists, incident types, work order types, projects, and where customer billing applies, project contracts and contract lines) *before* migrating transactional work orders. If the records a work order needs don't exist yet, the Project lookup doesn't resolve to the intended project and the work order's financial context is incomplete or inconsistent.

## Migration process

### Phase 1: Plan and map

1. Decide the scope: which work orders to migrate (open and in-progress work orders only, or historical and closed work orders too).

1. Map legacy fields to Field Service entities: Work Order, Work Order Type, Incident Type, Service Account, Billing Account, Price List, Products, Services, Service Tasks, Bookings, and Bookable Resources.

1. Map legacy fields to Project Operations entities: Project, Project Task (if applicable), Project Contract, Project Contract Line, and Contract Line Billing Method.

1. For environments integrated with finance and operations, map the additional organizational and financial context required for the integrated scenario: Company (legal entity) on applicable records, including the Work Order and Bookable Resource, along with any required site, warehouse, or inventory dimensions used by the customer's configuration.

### Phase 2: Load prerequisite and configuration data first

1. Load master and configuration data into Dataverse before any work orders: Accounts, Price Lists, Products and Services, Incident Types, and Resources.

1. Create or migrate the required Project Operations records for each customer engagement: Project and, where customer billing applies, Project Contract, Contract Line, Billing Method, and Project Line Customer. Learn more in the [Project and financial reference data](#project-and-financial-reference-data) section.

### Phase 3: Migrate work orders (ETL)

1. Extract work orders and related child data (service tasks, products, bookings) from the legacy system.

1. Transform: normalize statuses, resolve legacy IDs to Dataverse GUIDs (account, price list, incident type), cleanse duplicates and bad data.

1. Load using the Dataverse Import Data Wizard, dataflows, Azure Data Factory or Synapse pipelines, the Dataverse Web API, or a third-party ETL tool such as KingswaySoft — respecting referential integrity (parents before children). Work orders are Dataverse records. The finance and operations data management framework applies to the finance and operations side of an integrated deployment, not to the work orders themselves.

1. Microsoft guidance on load tooling and approach: Data migration for Dynamics 365 implementation projects [Data migrationn for Dynamics 365 implementation projects](../resources/migrate-data.md), [Importing and exporting data from Dataverse](/power-apps/maker/data-platform/import-export-data), and [Data migration approaches](/power-platform/architecture/key-concepts/data-migration/data-migration-approaches).

1. Import work orders in a non-Posted status initially (for example, Open or Scheduled).

> [!IMPORTANT]
> Work orders can only be linked to a project while Work Order System Status is not Posted. Once posted, the Project field is locked. If you load any migrated work order at Posted status, you can't link it afterward through normal means. Always import pre-Posted, link the project, then transition status if the record represents closed or completed work.

### Phase 4: Link to Project Operations

1. For each imported work order, open the work order, select the **General** tab, select **Related Project Details**, and select the correct project. Select **Save & Close**.

1. Where supported by the installed integration release, you can link a project to an agreement while the agreement is Active. Even so, link the project before configuring agreement recurrence so that generated work orders inherit the intended project context from the start. Linking while the agreement is still in Draft or Estimate status is the safest option. Work orders generated after the link is set inherit it automatically. Confirm Active-agreement linking in the target package. Older releases can require pre-activation linking. Changing the project on an agreement doesn't update work orders that you already generated. Correct those work orders manually.

1. For bulk migrations, populate the Project lookup directly during the data load step (or through a follow-up bulk update), rather than manually per record. Find the automated approaches in the [Bulk or programmatic linking options](#bulk-or-programmatic-linking-options) and [Automation script sample](#automation-script-sample) sections.

### Phase 5: Validate and test

1. Use the **Work Orders Linked to Project** or **Work Orders Without Project** system views to confirm 100% linkage.

1. Spot-check that time, material, and labor entries correctly created estimates and actuals in Project Operations.

1. Conduct User Acceptance Testing (UAT) with end users in a sandbox environment before cutover.

### Phase 6: Cutover

1. Extract and migrate remaining and delta records.

1. Switch off legacy system writes.

1. Go live.

1. Keep legacy system in read-only mode for a transition and audit period.

## Bring in historical work orders

Historical work orders - those already completed, invoiced, or closed in the legacy system - need special handling because they typically must be loaded already in a closed or Posted-equivalent state, which conflicts with the normal "link before Posted" rule. Decide and design for this explicitly; don't treat historical records the same as active or open ones.

### Recommended approach for historical work orders

1. Migrate configuration and the required Project Operations records first (same as for active work orders) — historical work orders still need a valid Project and, where customer billing applies, a Project Contract and Contract Line to post against.

1. Load historical work orders with the Project field already populated at creation time (via the import file or data load), instead of relying on the manual post-import linking step. This approach avoids the Posted-status lock entirely, since the link is set in the same operation that creates the record.

1. If you must load historical work orders as already Posted (for example, because your import tool posts on creation, or the legacy status must map 1:1), set the Project field as part of the same create call or transaction — never as a second, separate update after the record already exists in a Posted state.

1. Represent the historical financials as project actuals rather than trying to recreate the original live transaction flow. Learn more in the [Bring historical cost and sales into projects](#bring-historical-cost-and-sales-into-projects) section. Most implementations don't attempt to re-run booking, scheduling, or dispatch for closed work.

1. Decide on a cutoff date: work orders closed before the cutoff are migrated as historical or summary actuals; anything open or active on cutover follows the standard live migration path. Learn more in the [Migration process](#migration-process) section.

> [!IMPORTANT]
> The Project lookup on a Work Order is locked as soon as System Status is Posted. For historical work orders, either (a) populate the Project field at creation or import time before the record is marked Posted, or (b) if your tool truly can't avoid a two-step load, keep the record in a non-Posted status just long enough to set the Project link, then transition status. Don't attempt to update the Project field on an already-Posted historical record; the system rejects it.

### Level of historical detail

Determine the level of historical detail you want to retain.

- Full transaction-level detail (every task, product line, booking, time entry) — most accurate, most effort. You need this level of detail if the customer reports at that granularity today.

- Summarized actuals per work order (single cost and revenue total per category) — much lower migration effort, sufficient for most reporting and history needs.

- Opening or beginning balances only (life-to-date totals per project) — lowest effort; used when only project-level percent-complete or revenue recognition continuity matters, not individual work order history.

## Bring historical cost and sales into projects

Don't try to recreate the original operational flow (dispatch → time entry → booking → invoice) for historical or closed work. Instead, load the financial outcome directly as project actuals or opening balances. Use one of the following mechanisms.

### Beginning balance or opening balance journals

- Use beginning-balance style journal entries to set life-to-date (LTD) cost and revenue totals per project (and per project contract line, where the billing method requires it).

- In Project Operations Core, record these actuals with Entry journals — Microsoft explicitly calls out Entry journals for situations where creating individual time, expense, and material entries is infeasible, including data migration. Learn more at [Create and confirm Entry journals](/dynamics365/project-operations/actuals/create-confirm-entry-journals). Once an Entry journal is confirmed it cannot be edited, and Correction journals cannot be used against the actuals it creates. Microsoft also cautions that Entry journals do not enforce strict defaulting rules by default, so use them sparingly and validate the resulting actuals; the Journal line improvements feature can be enabled to enforce rules on journal lines.

- For Project Operations integrated with ERP, use the documented beginning balances feature. It requires Dynamics 365 Finance 10.0.46 or later and the Enable beginning balances in Project Operations Integrated with ERP feature. Agree on the cut-off date and beginning balance journal name with the Finance workstream before posting; the cut-off date becomes non-editable after the first beginning balance posting. Eligible actuals on or before the cut-off date create beginning balance journals, which update the project subledger without general ledger entries. Billed milestones and retainers aren't supported by this feature. Learn more at  [Manage beginning balances](/dynamics365/project-operations/advanced-configuration/int-beginning-balances).

- Beginning balances are the standard approach for Fixed Price projects, since the first Revenue Recognition run needs correct cost-to-complete and percent-complete figures. Get this right before go-live or recognition is wrong from day one.

### Project journals (cost, item, hour, expense)

- For more granular historical detail, import cost data through Project General Journals or the relevant category journal (hours, expense, item, or material) to populate Actuals at the transaction level.

- Choose this option over beginning balances only if the customer needs to report on individual historical work order transactions after go-live, not just totals.

### Time and materials vs fixed price projects

- Time and materials projects: migrate both already-billed historical costs and any unbilled Work-In-Progress (WIP), so future invoicing can continue seamlessly from Dynamics 365.

- Fixed price projects: ensure migrated costs are accurate before the first recognition run. Percent-complete calculations depend on correct cost-to-complete figures from day one.

### Avoid double-posting to the general ledger

- When you migrate trial balance or general ledger opening balances separately, agree on the project-subledger and general-ledger migration design with the Finance workstream and reconcile both before sign-off.

- For the integrated ERP beginning balances feature, use the documented beginning balance journals: they update the project subledger without generating general ledger entries. If you propose a different journal route, have the Finance workstream validate its posting controls and any clearing-account treatment in a sandbox. Don't assume a generic non-ledger flag applies to every journal type or deployment.

### Sequence dependency

Migrate in this order to avoid broken references:

Project Contract → Funding Source (if used) → Project → Work Breakdown Structure (tasks) → Opening Balances / Actuals.

> [!IMPORTANT]
> After migration, treat actuals and opening-balance entries as historical records. You can edit only limited descriptive fields. Ensure the project, contract, contract line, category, and cost status are correct during migration. Don't plan to fix them after migration.

## Migration questions

Ask these questions before finalizing the migration design. The answers can change the scope, effort, and tooling choice.

### Scope and volume

- How many work orders do you need to migrate? How many work orders are still open or active? How many work orders are closed, completed, or invoiced?

- What historical date range do you need? For example, last 12 months, last 3 years, or all time? Is there a business or compliance reason driving that window, such as audit, warranty, or regulatory retention?

- Do you need to migrate all historical work orders, or only work orders tied to active customers, contracts, or agreements?

### Financial detail and reporting needs

- Do you need to report on individual historical work order transactions (task, product, or labor line detail) after go-live, or is a project-level or work-order-level summary total sufficient?

- For historical fixed-price projects, do you need accurate percent-complete and revenue recognition continuity from day one, or are those projects already fully complete and closed (no further recognition needed)?

- For time and materials work, is there unbilled WIP that must be migrated so you can still invoice it from Dynamics 365, or is everything already billed in the legacy system?

- Will the Finance workstream migrate general ledger or trial balance opening balances separately? Confirm the supported beginning-balance or journal route, any clearing-account treatment, and the reconciliation that prevents double-posting.

### Data quality and mapping

- Is there a reliable legacy Work Order ID you can carry over (as a reference or legacy-ID field) to support reconciliation and troubleshooting after migration?

- Do all legacy work orders have a clear mapping to a target Account, Billing Account, Price List, and Incident Type in the new system? Who owns resolving gaps?

- Are there duplicate, orphaned, or incomplete legacy work orders that you should exclude rather than migrate as-is?

### Project structure alignment

- Does every legacy work order map cleanly to one target project, or are there many-to-one or one-to-many situations (for example, one legacy job spanning multiple projects, or multiple legacy jobs rolling into one project)?

- Do all necessary Project Contracts and Contract Lines (with Billing Method) already exist, or do they need to be created as part of this migration?

- For recurring work (agreements), should historical work orders generated from an agreement all roll up to one project, or does the project change over time (for example, annually)?

### Cutover and validation

- What is the cutover date, and how will you handle work orders created in the legacy system between data freeze and go-live (delta load)?

- Who will validate or reconcile financial totals (cost, revenue, WIP) between legacy and Dynamics 365 before sign-off?

- How long does the legacy system need to remain accessible (read-only) after go-live for audit and support purposes?

## How project linkage works

| Entity | Field (Display Name) | Logical Name |
| --- | --- | --- |
| msdyn_workorder (Work Order) | Project | msdyn_project |
| msdyn_workorder (Work Order) | Project Task | msdyn_projecttask |

The Project lookup establishes the relationship between the work order and the Project Operations project.

When the work order represents work associated with a specific task in the project's work breakdown structure, also populate the Project Task lookup. This action preserves the task-level relationship used for planning, execution, progress, and downstream transaction context.

For bulk migration, you can populate these lookup fields programmatically when you know the migrated work order and the corresponding Project or Project Task records.

> [!IMPORTANT]
> Populate the Project reference before, or together with, the Project Task reference so that the work order is associated with the correct project hierarchy.

> [!NOTE]
> Once a work order has both a Project and a Project Task, both fields are locked. A work order that isn't posted and has no project task associated with it can still have its project changed or removed.

## Bulk or programmatic linking options

| Method | Description |
| --- | --- |
| Dataverse Web API (PATCH) | Best for scripted migration. PATCH `msdyn_workorders(<WO GUID>)` with body: `{ "msdyn_project@odata.bind": "/msdyn_projects(<Project GUID>)" }`. Add `"msdyn_projecttask@odata.bind": "/msdyn_projecttasks(<Project Task GUID>)"` when the work order maps to a specific project task. Loop per work order using your legacy-ID → GUID mapping. |
| During initial import | Include a Project GUID column in the staging or source file and map it directly during an Import Data Wizard, dataflow, KingswaySoft, or ADF load — the work order is created already linked. Include the Project Task GUID as well where the work order maps to a specific task. |
| Bulk Edit (UI) | In the Work Orders view, select multiple records and use Edit (bulk edit) to set Project once for all selected — good for simple one project to many work orders cases. |
| Power Automate | Flow looks up the Project by a matching key (for example, legacy customer ID or staging table), then uses Update a Row on `msdyn_workorder` to set `msdyn_project`. |
| XrmToolBox | Bulk Data Updater / FetchXML Builder — practical for a one-time cleanup pass after migration. |

## Automation script sample

The reference PowerShell script, Link-WorkOrdersToProjects.ps1, is a reference sample for bulk linking. It isn't validated against a customer environment, so treat it as a starting point to review, adapt, and test before use. As drafted, it:

- Authenticates to Dataverse by using a Microsoft Entra ID (formerly Azure AD) app registration (client credentials flow).

- Reads a `mapping.csv` file with columns `WorkOrderId` and `ProjectId` (GUIDs).

- Checks each work order's System Status first and skips any that are already Posted (reports them in the output log).

- PATCHes the `msdyn_project` lookup via `@odata.bind` for all eligible records.

- Supports a `-WhatIf` dry-run mode.

- Writes a timestamped results CSV (Success / Skipped-Posted / Error) for reconciliation.

> [!IMPORTANT]
> This script isn't validated end to end. Review, adapt, and test it fully in a sandbox before any production use. Add the app registration as an application user in the target environment with a security role that grants write on Work Order and read on Project. Confirm the actual Posted option-set value for msdyn_systemstatus in your environment by using the EntityDefinitions metadata endpoint noted in the script (690970004 in a current Field Service environment, but always verify). Always run with -WhatIf against a sandbox or test environment first.

## Key risks and highlights

| # | Critical Point |
| --- | --- |
| 1 | You can edit the Project link only while Work Order System Status isn't Posted, so import work orders before posting. Once a work order has both a Project and a Project Task, both fields are locked to prevent unintended changes. |
| 2 | Load configuration and foundational data (accounts, price lists, incident types, work order types, projects, and where customer billing applies, project contracts and contract lines) before transactional work orders. |
| 3 | The required Project Operations reference data must exist before linking. Customer-billable work needs the applicable Work-based Project Contract, project-based Contract Line, Billing Method, and Project Line Customer. Where the installed integration release supports non-customer-billable project linking, the no-contract scenario in [Projects that don't use customer billing](#projects-that-dont-use-customer-billing) applies; validate release support first. |
| 4 | Changing a project on an agreement only affects future work orders generated after the change. You must manually correct existing work orders. |
| 5 | Removing a project from a work order deletes existing estimates and reverses posted actuals. Use with caution. |
| 6 | Deactivating a linked work order doesn't reverse its time entries, material usage, or actuals in Project Operations. Clean up those entries separately if required. |
| 7 | Use the **Work Orders Linked to Project** and **Work Orders Without Project** views to verify 100% linkage before go-live. |
| 8 | Set the Project field for historical work orders at or before creation (or before the record reaches Posted status). Set the link in the same load step as the record creation, not as a follow-up update. |
| 9 | For historical financials, load actuals and opening balances (beginning balance or project journals) rather than re-creating the original transactional flow. |
| 10 | Coordinate with the Finance/ERP workstream to avoid double-posting to the general ledger if you migrate trial balance opening balances separately. |