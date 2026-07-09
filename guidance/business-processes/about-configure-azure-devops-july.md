---
title: Set up Azure DevOps with the Business Process Catalog July
description: Learn how to use the July setup package to create an Azure DevOps project and import the business process catalog.
author: rachel-profitt
ms.author: raprofit
ms.reviewer: edupont
ms.date: 06/26/2026
ms.topic: how-to
---

# Set up Azure DevOps with the Business Process Catalog July

The July setup package helps you configure Azure DevOps for the business process catalog and import catalog work items into Azure Boards. The package includes a guided setup wizard, Azure DevOps process and project configuration scripts, a resumable catalog importer, and a deterministic HTML summary report.

Download the July assets from GitHub at [Azure DevOps templates - July](https://github.com/microsoft/dynamics365patternspractices/tree/main/templates/Azure-DevOps-templates/July).

## What the July package does

The setup wizard runs six phases:

| Phase | Purpose |
| ---: | --- |
| 1 | Create or update the process, project, work item types, fields, picklists, and Test Case `New` state. |
| 2 | Configure work item page layouts, supported HTML controls, and DevLabs multivalue controls. |
| 3 | Create teams, area paths, and team area assignments. |
| 4 | Configure backlog levels, iterations, and team settings. |
| 5 | Import work items for the business process catalog. |
| 6 | Generate a deterministic HTML setup and import summary report. |

## Prerequisites

Before running the setup package, make sure you have the following items:

- A Windows dev box or Windows device with network access to `dev.azure.com`.
- Python 3.12 or later.
- An Azure DevOps organization.
- An account that's an Azure DevOps organization owner or Project Collection Administrator.
- An Azure DevOps personal access token (PAT) with the required scopes.
- The ADO template guideline workbook from the July package.
- The source folder for the business process catalog.

For long-running catalog imports, use a local folder on the machine that runs Python, such as `C:\BPCADO`. Avoid running scripts or reading large source files from redirected paths such as `\\tsclient\...`.

## Create the Azure DevOps PAT

The July release uses more Azure DevOps APIs than the earlier version because it configures layouts, handles inherited and system work item types, checks the DevLabs multivalue control extension, configures teams and backlogs, and imports work items.

Select the following scopes for personal access tokens (PAT):

- **Organization:** Read & manage
- **Project and Team:** Read & manage
- **Work Items:** Read & write
- **Process and Work Item Types:** Read & manage
- **Extensions:** Read
- **Marketplace:** Read

If your organization restricts extension installation, the account might also need organization-owner or administrator rights beyond the PAT scopes. Phase 2 attempts to install or confirm the DevLabs multivalue control extension. If the extension isn't installed and the PAT or account can't install extensions, Phase 2 logs a warning and skips multivalue controls. Install the extension manually from Azure DevOps Marketplace or rerun Phase 2 with an account and PAT that can manage extensions.

Don't paste the PAT into scripts or commit it to source control. Let the wizard prompt for it, or set it only for the current PowerShell session:

```powershell
$env:BPC_ADO_PAT = "<paste PAT here>"
```

## Prepare the package

Copy the July package and catalog source files to a local folder on the machine running Python.

```powershell
Set-Location "C:\BPCADO\bpc-ado-publish-package"
python -m pip install -r requirements.txt
```

> [!TIP]
> A Python virtual environment is optional. Use one if you want to isolate this package's dependencies from other Python tools on the machine. Find guidance for Windows guidance at [Creation of virtual environments](https://docs.python.org/3/library/venv.html#creating-virtual-environments). After creating and activating a virtual environment, use the same commands shown in this article.

## Run the full setup

```powershell
python setup_wizard.py `
  --ado-org-url "https://dev.azure.com/<organization>" `
  --ado-project "<project name>" `
  --process-name "<process name>" `
  --excel-file "<path to ADO template guideline workbook>" `
  --catalog-source-dir "<path to Business Process Catalog source folder>" `
  --catalog-output "C:\BPCADO\out" `
  --catalog-parallel-workers 4
```

The wizard prompts for the Azure DevOps PAT if `BPC_ADO_PAT` isn't already set.

## Run selected phases

Run only process and project setup:

```powershell
python setup_wizard.py --start-at 1 --stop-after 4
```

Run only catalog import:

```powershell
python setup_wizard.py --start-at 5 --stop-after 5
```

Generate only the HTML report:

```powershell
python setup_wizard.py --start-at 6 --stop-after 6
```

## Choose a worker count

| Worker count | Recommended use |
| --- | --- |
| 1 | Safest option after throttling or when diagnosing failures. |
| 2-4 | Good first preview validation. |
| 8 | Reasonable after the target process is stable. |
| 16+ | Use only when you accept higher Azure DevOps throttling risk. |

If Azure DevOps returns ATCPU or HTTP 429 throttling, rerun Phase 5 with fewer workers. The importer skips keys already recorded in `ado-id-map.csv`.

## How the catalog import works

Phase 5 is a single-process, resumable Azure DevOps import utility. It reads the source files for the business process catalog and the ADO template workbook, builds a deterministic parent-first import plan, and creates work items in Azure DevOps.

The importer takes the following steps:

1. Loads source files from the catalog source folder. Supported formats are `.xlsx`, `.xlsm`, `.csv`, and `.tsv`.
1. Loads the ADO template workbook to map source columns to Azure DevOps field reference names and work item types.
1. Builds work item drafts with parent-child relationships.
1. Normalizes placeholder area and iteration paths to the target project name.
1. Creates parent work items before child work items.
1. Writes each successful work item ID to `ado-id-map.csv`.
1. Skips any source key already present in `ado-id-map.csv` on rerun.

The source key is usually `MSBPC.microsoftid` or the process sequence ID. This key lets the importer resume safely after throttling, validation failures, or an interrupted run.

## Review output

Open the HTML report. Use the report to review:

```text
<catalog-output>\<organization>_<project>\bpc-ado-setup-summary.html
```


- setup and import status,
- planned, imported, skipped, and failure counts,
- resolved prior failures,
- elapsed time and worker count,
- quick links to Azure DevOps and output files,
- phase log details.

The importer also writes:

- `ado-id-map.csv` for successful imported or recovered work item IDs,
- `import-plan.json` for the deterministic import plan,
- `import-preview.csv` for a human-readable preview,
- `import-failures.json` for detailed failure messages,
- `skipped-deprecated-deleted.csv` for rows skipped by create/import mode.

## Rerun behavior

Phase 5 is resumable. When you rerun, the importer skips keys already in `ado-id-map.csv` and continues from remaining work items.

## Related articles

- [What's new in the Business Process Catalog Azure DevOps setup July](about-configure-azure-devops-july-whats-new.md)
- [Business Process Catalog Azure DevOps setup FAQ - July](about-configure-azure-devops-july-faq.md)
- [Use the business process catalog as a template in Azure DevOps Services](about-import-catalog-devops.md)
