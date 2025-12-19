---
title: Manage Catalog Row Changes in Azure DevOps Projects
description: Discover best practices for managing updates to the business process catalog in Azure DevOps. Optimize workflows and maintain consistency across releases.
author: rachel-profitt
ms.author: raprofit
ms.reviewer: edupont
ms.date: 12/16/2025
ms.topic: concept-article
---

# Manage business process catalog updates in Azure DevOps

The business process catalog (BPC) from Microsoft provides a structured hierarchy of processes aligned with Dynamics 365 and [Success by Design principles](../implementation-guide/success-by-design.md). Partners and customers often import this catalog into Azure DevOps by using the provided Excel format to manage work items for their particular implementation project. This article explains how to handle updates across releases, minimize data conflicts, and use automation for efficiency.

## Key concepts

The following table outlines key field values that you must understand before you begin taking updates to the business process catalog.

|Column  |Values  |Description  |
|---------|---------|---------|
|**Catalog status**| **10 - New** | New rows introduced in the catalog. |
| |**30 - Updated**| Indicates changes to existing rows.|
| |**40** - **Published**| Indicates there is no change to the row in the business process catalog.|
| |**50 - Custom**| Use this row to indicate that the work item is particular to this implementation project. Use this value as the default for new work items that don't come from Microsoft.|
| |**60 - Deprecated**| Rows marked for removal in future releases.|
| |**70 - Deleted**| Rows removed after two deprecation cycles.|

The catalog has columns that contain different types of identifiers as outlined in the following table.

|Column  |Description  |
|--------|---------|
|**Microsoft ID**| Unique, system-generated identifier for each row provided by Microsoft.|
|**Process Sequence ID**| Unique human assigned number that is designed to help sort processes in the Business Process Catalog tree. Process Sequence IDs aren't assigned to the Deliverables or Delivery Plan rows. Maintain these values for continuity but they're prone to manual errors because they're human assigned.|
|**Partner ID**| Partners who extend the business process catalog and add custom rows use the Partner ID column to keep track of their unique identifier for the row.|
|**ID**| This is the native ID column populated by Azure DevOps. The system automatically assigns this number. It's never duplicated and can't be edited.|

## Handle customer IDs

When an organization imports new rows into their Azure DevOps environment, Azure DevOps assigns each work item a unique ID. The process of importing from a .CSV file requires this ID to update existing rows in a subsequent import. The **Microsoft ID** column in the catalog file remains constant, and it should always match between Microsoft and customer environments.

### Recommendations for customer IDs

Take the following actions:

- Maintain both the **ID** and **Microsoft ID** columns in your Azure DevOps work items.

- Use **Microsoft ID** for cross-release matching and reconciliation.

- When preparing a .CSV file for updates, query Azure DevOps to retrieve Customer IDs and map them to Microsoft IDs before performing bulk updates.

- Consider automation using REST API or Power Automate to sync IDs and prevent mismatches.

## Challenges

When you import or update an existing Azure DevOps project with new values from the business process catalog, consider some key challenges.

Each partner and project can follow different project methodologies, and the way they use and maintain the catalog can be different. For this reason, you might need to adjust the exact technique for updating the catalog with each release based on the specific project and customer needs.

Use the following information to guide you for each status of row that's provided in the business process catalog.

### Updated rows

Copying a row from the template into Azure DevOps after your project is active can be risky. The project team likely modifies many work items from the detail values that Microsoft provides.

> [!IMPORTANT]
> Don't directly import the full business process catalog into an active implementation project. Instead, analyze the changes and merge changes based on the project and customer needs.

Use the following recommendations to guide you.

- Use the **Author** column to help differentiate who the row came from

  - Microsoft sets the field to *Microsoft* for published rows.

  - Partners who extend the catalog, set field in the partner specific-rows to *Partner*.

  - Customers update fields to *Customer* for project-specific rows. Set the default value for new work items to automate this.

- Implement **Azure DevOps Rules**

  - Trigger the rules when fields such as **Description** are modified  so that the **Catalog status** field changes to *Custom*.

  - The fields tab in the Azure DevOps Guidelines Template.xlsx describes each field in the Azure DevOps template. It includes metadata that describes if Microsoft provides values for the field, if the partner provides values for the fields, and so on.

### New rows

New rows in the business process catalog, Deliverables tree, or Delivery plan tree are generally low risk and safe to import into an existing project.

> [!TIP]
> Active projects should define an application lifecycle management (ALM) process to review and uptake new releases of the business process catalog as an "entry point" to determine which new features should be considered for the project or customer deployment.

### Recommendations for new rows

Take the following actions:

- Define a process and a cadence for considering new processes and deliverables in the catalog.

- Set new rows to Unspecified in the **Scope** field by default so customers can disposition the processes. Depending on the phase of your project, you might want to update all new rows to Out of scope during import.

- Consider if you should automate scope assignment during import by using Power Automate or Azure DevOps rules on each work item type.

### Deprecated rows

When you deprecate a row in the business process catalog, keep it in the catalog for two subsequent releases to help provide continuity and reference. During this period, link the deprecated row to its replacement through the Alternate Process Sequence ID field so that users can easily identify and transition to the new process or deliverable. This approach ensures that teams have adequate time to adjust to changes and maintain traceability between deprecated and replacement items within their project workflows.

### Recommendations for deprecated rows

Take the following actions:

- Merge data into the replacement work item by using **Copy Work Item** or by creating a relationship between work items.

- If you modified the original row in the catalog, consider if you should use one of the following techniques:

- Copy the data you customized to the new row. If you choose this option, consider creating a relationship between the original work items and closing the deprecated work item to prevent further updates to the work item.

- Update the deprecated row to have the new ID and other updated details of the new row. Using this technique is the preferred option as Azure DevOps work item history is preserved. However, this technique requires you to evaluate which columns you want to keep or merge from the original work item.

- Consider using Power Automate or the Azure DevOps APIs to automatically merge the two work items together.

  > [!IMPORTANT]
  > If you choose to keep a row in your catalog that's deprecated in Microsoft's catalog, remember that eventually Microsoft deletes the row and you can no longer receive updates.

### Deleted rows

When a row is marked with a **Catalog status** of Deleted from the business process catalog, this status indicates the row is removed and no updates are provided after its deletion in the next release. Handle deleted rows in a manner similar to deprecated rows by ensuring you reconcile any missing entries in future releases by using the unique Microsoft ID. This approach helps maintain consistency and traceability, allowing users to identify if a row is removed and to update their records or processes accordingly.

### Recommendations for deleted rows

Take the following actions:

- Treat similar to deprecated rows.

- If the row is missing in future releases, reconcile by using the Microsoft ID.

## Recommended practices for importing updates

- Always use Microsoft ID for matching rows during CSV import.

- Populate the ID before uploading any changes to ensure that you update the existing rows.

- Consider importing the catalog changes into a copy of your project first before importing them into your production project.

- Validate field mappings before publishing changes.

- Use Excel integration or CSV import for bulk updates.

- Consider using Power Automate flows or Azure DevOps to automate the updates.

## Related resources

- [Import the Business Process Catalog into Azure DevOps](about-import-catalog-devops.md)

- [What's New in the business process catalog](about-whats-new.md)
