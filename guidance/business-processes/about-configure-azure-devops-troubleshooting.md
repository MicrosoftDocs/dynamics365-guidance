---
title: Troubleshooting the Azure DevOps Python Scripts (Preview)
description: Azure DevOps Python script errors? Learn how to fix missing modules, resolve file issues, and complete manual setup for a successful preview. Get solutions here.
author: rachel-profitt
ms.author: raprofit
ms.reviewer: edupont
ms.date: 03/27/2026
ms.topic: how-to

---

# Troubleshooting the Azure DevOps Python Scripts (Preview)

This section lists the most common issues encountered during the private preview and how to resolve them. If you encounter an error not listed here, capture the full error message and share it through the preview feedback form.

## Issue: ModuleNotFoundError: No module named 'openpyxl' or ImportError: Missing optional dependency 'openpyxl'

**What this means**

The script reads data from Excel (.xlsx) files. Python requires another package, **openpyxl**, to read Excel files. This package isn't included by default when installing Python.

**How to fix it**

1. Open **Command Prompt** or **PowerShell** (Windows) or **Terminal** (Mac).
1. Copy and paste the command below exactly as shown, then press Enter:
python

1. (Optional) Verify that it installed successfully:

```powershell
python -c "import openpyxl; print(openpyxl.__version__)"
```

If a version number appears (for example, 3.1.5), the issue is resolved.

You do **not** need to type a version number yourself. The command automatically displays it.

## Issue: 'pip' isn't recognized or Packages install but the script still fails

**What this means**

Your system may have multiple Python installations, or the package was installed into a different Python environment than the one running the script.

**How to fix it**

It's important that you always install packages using the following format:

```powershell
python -m pip install pandas requests openpyxl
```

Then immediately run your script again using:

```powershell
python your*script*name.py
```

Do **not** use pip install ... by itself.

## Issue: Errors caused by copy/paste characters or symbols

**Common symptoms**

- Errors that say:
   - *"The term isn't recognized…"*
   - *"Invalid requirement"*
   - *"Could not find a version that satisfies the requirement"*
**What this means**

Extra characters (such as backticks ` or smart quotes) were accidentally pasted into the command window.

**How to fix it**

- Recopy the command from the documentation.
- Ensure the command:
   - Starts with python
   - Contains **no backticks, quotes, or formatting symbols** unless explicitly shown
- Paste it once and press Enter.
## Issue: The script runs, but nothing appears in the Azure DevOps project

**What this means**

This is **expected behavior** for the current preview.

The scripts:

- Create the Azure DevOps **project**
- Create the **process**
- Create **work item types, fields, picklists, and layouts**
They **do not** import actual Business Process Catalog data yet.

**What to do next**

After the script completes successfully:

- Complete the **manual configuration steps** described in each article in the document
- Then import the Excel files manually into Azure DevOps
## Issue: Excel file errors or "file not found" messages

**Things to check**

- The Excel file:
   - Is saved locally (not locked by OneDrive or SharePoint sync)
   - Is closed in Excel before running the script
- The file path:
   - Matches exactly what is specified in the script
   - Includes the .xlsx file extension
## Issue: Cannot find work item type with reference name 'Microsoft.VSTS.WorkItemTypes.TestCase'

**What this means**

This error occurs when the script attempts to reference or modify the **Test Case** work item type in Azure DevOps.

Due to current Azure DevOps API limitations, organizational processes cannot programmatically modify the Test Case work item type (for example, adding or updating custom fields). As a result, Azure DevOps does not expose the Test Case work item type in the same way as other work item types during process automation.

Because of this limitation, the script may report that it cannot find the Test Case work item type, even though Test Cases exist in Azure DevOps.

This error is expected during the preview and does not indicate that the script failed.

**What to do**

No action is required for this error in the script.

Instead, follow the **manual configuration steps** described earlier in this document to complete Test Case setup, including:

- Adding required fields
- Updating layouts
- Configuring any Test Case-specific metadata
These steps must be performed manually because they cannot be completed using the Azure DevOps APIs.

**When to be concerned**

You only need to investigate further if:

- The script fails **before** creating the project or process, or
- Other work item types are missing or incorrectly configured, such as Features, User Stories, Bugs, or Tasks.
If everything else appears correct, you can safely proceed with the manual steps and ignore this message.

## Issue: HTML fields cannot be added to the form layout 

You may see multiple messages such as:

SKIPPED: HTML field 'Description' can't be added to the form layout via API.

**What this means**

This message appears when the script tries to place certain **form controls** (especially **HTML fields** and a few other custom control types) onto an Azure DevOps work item **layout**. Now, the Azure DevOps **layout API** doesn't support adding some control types programmatically. Because of this limitation, the script skips those items instead of failing.

**This is expected behavior in the preview** and does **not** indicate that your environment or data is broken.

**What to do**

There is **nothing to fix in PowerShell or Python** for this message. Follow the **manual configuration steps** in the instructions to:

1. Open the **Process** → **Work Item Types** → **Layouts** in Azure DevOps.
1. **Add** the required **HTML** fields, such as **Description**, to the appropriate **layout** section, such as Details or Tabs.
1. **Save** the layout.
These manual steps are **intentional** and documented because the API cannot complete them automatically.

**When to be concerned**

Investigate further only if:

- The script shows **errors** (not "SKIPPED") for supported controls, or
- Entire work item **layouts** are missing sections that **should** be created by the script.

Otherwise, you can safely proceed once you apply the manual layout steps.
