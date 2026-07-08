---
title: Business Process Catalog Azure DevOps Setup FAQ - July
description: Find answers to common setup, permissions, extension, import, and troubleshooting questions for the July 2026 release of the Business Process Catalog Azure DevOps setup.
author: rachel-profitt
ms.author: raprofit
ms.reviewer: edupont
ms.date: 06/26/2026
ms.topic: faq
---

# Business process catalog Azure DevOps setup FAQ - July

This FAQ covers common issues with the July setup package for Azure DevOps and the business process catalog from Microsoft.

> [!NOTE]
> Some entries in this article assume that you're working in a local folder at `C:\BPCADO\` with several subfolders. Remember to update the relevant code snippets to reflect the folder structure on your device.

## What Python command should I use to install packages?

Use the following command:

```powershell
python -m pip install -r requirements.txt
```

Don't use `pip install ...` by itself. Using `python -m pip` helps ensure you install packages into the same Python environment that runs the setup scripts.

## What should I do if I get `ModuleNotFoundError` or `ImportError` for `openpyxl`, `pandas`, or `requests`?

Install the package dependencies from the package folder:

```powershell
python -m pip install -r requirements.txt
```

You can verify `openpyxl` with:

```powershell
python -c "import openpyxl; print(openpyxl.__version__)"
```

## Why does PowerShell show `The output stream for this command is already redirected`?

This error usually happens when you paste the PowerShell prompt or continuation markers with the command, as shown in the following example:

```text
PS C:\BPCADO\bpc-ado-publish-package>
>>
```

Remember to always paste only the command text, as shown in the following example:

```text
C:\BPCADO\bpc-ado-publish-package
```

## Why does the script say it can't find the Excel template or catalog source folder?

The path must exist on the device where Python is running. If you run the script on a dev box, copy the template workbook and catalog source folder to a local folder, such as `C:\BPCADO\source`.

Avoid running scripts or reading large source files through redirected paths such as `\\tsclient\...`.

## Why do I get warnings that the script can't write to the log file?

This problem usually happens when you run the script package from a redirected or synced path. Copy the package to a local folder on the machine running Python, such as:

```text
C:\BPCADO\bpc-ado-publish-package
```

Then run the wizard from that local folder.

## Does Phase 2 install the DevLabs multivalue control extension?

Phase 2 attempts to install or confirm the DevLabs multivalue control extension for the Azure DevOps organization. It calls the Azure DevOps extension management API `ms-devlabs.vsts-extensions-multivalue-control`.

If the extension is already installed, Phase 2 continues and adds multivalue controls for fields marked as multiselect in the template workbook.

If the extension isn't installed and the PAT/account can't install extensions, Phase 2 logs a warning and skips multivalue controls. Install the extension manually from Azure DevOps Marketplace or rerun Phase 2 with an account and PAT that can manage extensions.

## What PAT scopes are recommended?

Use an account that's an Azure DevOps organization owner or Project Collection Administrator. Select these PAT scopes:

- **Organization:** Read & manage
- **Project and Team:** Read & manage
- **Work Items:** Read & write
- **Process and Work Item Types:** Read & manage
- **Extensions:** Read
- **Marketplace:** Read

If your organization restricts extension installation, the account might also need organization-owner or administrator rights beyond the PAT scopes.

## Does the July package still require manual HTML control setup?

In most cases, no. Phase 2 adds supported HTML fields to work item layouts by using Azure DevOps `HtmlFieldControl` payloads.

If Azure DevOps rejects a specific control or if an inherited or system work item type layout is locked, the script logs the response. Review the Phase 2 log and rerun after fixing the process or permissions issue.

## Does the July package still require manual multivalue control setup?

Usually no. Phase 2 adds multivalue controls in the following cases:

1. The template marks the field as multiselect,
1. `BPC_ADO_ADD_MULTIVALUE_CONTROLS` isn't disabled,
1. The DevLabs multivalue control extension is installed or can be installed by the script.

If the extension is unavailable, the script skips multivalue controls and logs the reason.

## What should I do if Azure DevOps returns HTTP 429 or ATCPU throttling?

Rerun Phase 5 with fewer workers. The importer records successful imports in `ado-id-map.csv`, so reruns skip work items that were already imported.

Start with 2-8 workers. Use 1 worker when diagnosing repeated throttling or validation errors.

## What should I do if a required field failure stops Phase 5?

Required field failures usually mean one of the following scenarios:

- The source row is missing a value required by the Azure DevOps process, or
- The template marks a field as applicable or required for a work item type where the source data doesn't provide that field.

Fix the source data, update the template or process requirement, or make the field not required for that work item type. Then rerun Phase 5. The importer skips keys already present in `ado-id-map.csv`.

## Why does the HTML report show resolved prior failures?

`import-failures.json` can contain a failure from an earlier run. If a later rerun imports that same key successfully, the key appears in `ado-id-map.csv`.

Phase 6 reconciles failures against `ado-id-map.csv`. If the failed key is now present in the ID map, the report lists it as a resolved prior failure and doesn't mark the run failed.

## Why does the Azure DevOps project appear empty after phases 1-4?

Phases 1-4 configure the Azure DevOps process, project, work item types, fields, layouts, teams, areas, iterations, and backlogs. They don't import Business Process Catalog work items.

Run Phase 5 to import catalog content.

## Why do Test Case state or work item type reference problems appear?

The July package handles Test Case setup in two places:

- Phase 1 confirms the `New` state on Test Case work item type references.
- Phase 5 resolves display names to the current project's Azure DevOps work item type reference names and can create without `System.State` first if Azure DevOps rejects a custom state during create.

If problems remain, rerun Phase 1 and then rerun Phase 5. Review the Phase 1 and Phase 5 output for the exact Test Case reference and state error.

## What should I check before reporting a problem?

Include these files from the project output folder:

- `bpc-ado-setup-summary.html`
- `import-failures.json`, if present
- `import-context.json`
- the latest phase log related to the failure

The HTML report includes quick links to these files.

## Related information

- [Set up Azure DevOps with the Business Process Catalog July](about-configure-azure-devops-july.md)
- [What's new in the Business Process Catalog Azure DevOps setup July](about-configure-azure-devops-july-whats-new.md)
