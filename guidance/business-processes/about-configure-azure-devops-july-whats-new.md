---
title: What's new in the July release for Azure DevOps setup
description: The July release for applying the Dynamics 365 business process catalog to Azure DevOps adds a guided six-phase wizard. Learn what changed and how to upgrade.
author: rachel-profitt
ms.author: raprofit
ms.date: 06/26/2026
ms.topic: whats-new
ms.collection: bap-ai-copilot

---

# What's new in the July release for setting up Azure DevOps based on the business process catalog

The July release expands the Azure DevOps setup package from a set of discrete scripts into an end-to-end guided setup and import workflow. It adds a resumable catalog importer, stronger validation and retry behavior, project-scoped outputs, and a deterministic HTML summary report.

Download the July assets from GitHub at [Azure DevOps templates - July](https://github.com/microsoft/dynamics365patternspractices/tree/main/templates/Azure-DevOps-templates/July).

## Comparison with the current published version

| Area | Current published version | July |
| --- | --- | --- |
| Execution model | Individual scripts run manually in sequence. | `setup_wizard.py` orchestrates phases 1-6 with `--start-at` and `--stop-after` rerun support. |
| Manual article steps | Users follow separate Learn articles and complete several manual checks between scripts. | The wizard runs phases in order, supports selected phase reruns, and reduces manual switching between articles. |
| HTML controls | Earlier guidance documented manual layout steps for HTML fields when the API skipped them. | Phase 2 adds supported HTML fields by using `HtmlFieldControl` payloads where Azure DevOps supports them. |
| Multivalue controls | Users manually handle multivalue controls. | Phase 2 attempts to install or confirm the DevLabs multivalue control extension, then uses its contribution for fields marked as multiselect. |
| System work item types | System and inherited work item types could require manual handling. | The setup scripts materialize inherited or system work item types when needed and retry field/layout updates against the process-specific reference. |
| PAT requirements | PAT guidance was split across individual articles. | The July user guide documents consolidated PAT scope recommendations for setup, layout controls, extension checks, and catalog import. |
| Catalog import | Not included or handled separately. | Phase 5 imports catalog source files into Azure DevOps using a parent-aware, resumable importer. |
| Import resume | Manual reruns can duplicate work unless handled outside the scripts. | `ado-id-map.csv` records successful work item IDs and reruns skip imported keys. |
| Output organization | Logs and outputs are script-local. | Import output is scoped by organization/project under `out\<organization>_<project>\`. |
| Parallelism | Page layout script includes threading; catalog import isn't part of the package. | Catalog import supports parent-aware parallel workers with retry and backoff controls. |
| Throttling resiliency | Limited transient handling. | Retries HTTP 408, 429, and 5xx responses and supports configurable retry count and delay. |
| Work item type resolution | Scripts rely on source/template work item names. | Importer resolves Azure DevOps work item type display names to current project reference names dynamically. |
| Test Case state handling | Test Case `New` state support isn't consistently handled. | Phase 1 confirms Test Case `New` state; Phase 5 handles create-time state validation fallback. |
| Multi-select picklists | Source duplicate picklist values can block setup. | Phase 1 de-duplicates picklist values before Azure DevOps updates; source template should still be kept clean. |
| Summary reporting | Users review console output and log files manually. | Phase 6 generates a deterministic HTML report with metrics, failure reconciliation, quick links, and latest log details. |

## New setup wizard

The wizard runs setup in six phases:

1. Create process, project, work item types, fields, picklists, and Test Case state.
1. Configure work item page layouts, HTML controls, and multivalue controls.
1. Create teams, area paths, and team assignments.
1. Configure backlog levels, iterations, and team settings.
1. Import work items for the business process catalog.
1. Generate the HTML setup/import summary report.

Use `--start-at` and `--stop-after` to resume or rerun selected phases without repeating the full setup.

## Reduced manual setup

The July release reduces or removes several manual steps from the earlier articles:

- The wizard passes shared organization, project, process, template, and PAT settings into each phase.
- Phase 1 handles process and project setup, picklists, custom fields, and Test Case `New` state handling.
- Phase 2 adds supported HTML controls and multivalue controls to work item layouts.
- Phase 2 attempts to install or confirm the DevLabs multivalue control extension. If organization policy blocks extension installation, install the extension manually and rerun Phase 2.
- Phase 2 handles process-specific references for inherited and system work item types instead of requiring users to manually resolve them.
- Phase 3 creates teams, area paths, and team area assignments.
- Phase 4 configures backlog levels, iterations, and team settings from the workbook.
- Phase 5 imports catalog source workbooks with resume support.
- Phase 6 generates an HTML summary report instead of requiring users to inspect multiple raw logs.

Some steps remain manual. Users still need to create or select the Azure DevOps organization, create a PAT, grant project users access, install or enable required Azure DevOps extensions when needed, and validate the resulting project configuration.

## PAT and permission changes

The July release uses more Azure DevOps APIs than the earlier version because it configures layouts, handles inherited and system work item types, checks extension availability for multivalue controls, and imports work items. The recommended PAT scopes are:

- **Organization:** Read & manage
- **Project and Team:** Read & manage
- **Work Items:** Read & write
- **Process and Work Item Types:** Read & manage
- **Extensions:** Read
- **Marketplace:** Read

If you expect Phase 2 to install the DevLabs multivalue control extension, the PAT and account must have permission to manage organization extensions. Some organizations restrict extension installation to organization owners or administrators even when a PAT has extension-related scopes.

## Known limitations

- Phase 5 create and import mode doesn't update existing work items other than recovery from ambiguous transient failures.
- `Deprecated` and `Deleted` rows are skipped in create and import mode.
- Very high parallel worker counts can trigger Azure DevOps ATCPU throttling. Start with 2-8 workers and increase only after validating process stability.
- The HTML report is deterministic and local. It doesn't query Azure DevOps to verify every work item after import.

## Related information

- [Set up Azure DevOps with the Business Process Catalog July](about-configure-azure-devops-july.md)
- [Business Process Catalog Azure DevOps setup FAQ - July](about-configure-azure-devops-july-faq.md)
