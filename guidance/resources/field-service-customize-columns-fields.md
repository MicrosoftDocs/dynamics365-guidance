---
title: Create and edit Field Service columns
description: Learn about best practices for creating and editing columns in Dynamics 365 Field Service.
ms.date: 09/18/2025
ms.topic: how-to
author: lmasieri
ms.author: lmasieri
---

# Create and edit Field Service columns

You can add columns to tables in Dynamics 365 Field Service, such as work orders, bookable resource bookings, and customer assets. (Tables were previously called entities.) For table references including writable columns, go to [Dynamics 365 Field Service table/entity reference](/dynamics365/field-service/developer/reference/about-entity-reference).

Mobile views display up to three columns.

Use these best practices to create and edit columns:

- Understand the existing columns, and try to use them before you create new columns.
- Try to edit only the display names and labels of fields. Don't edit field properties.
- Don't change required fields to optional. You can change optional fields to required.
- Don't delete existing fields.

> [!IMPORTANT]
> Deleting columns might cause important processes to fail and lead to errors. Instead of deleting columns, hide them or remove them from the forms, so that they aren't visible to users.

This article uses the work order table as an example. However, the guidance that is offered applies to all Field Service tables.

## Create new columns

Understand the existing information and processes on the work order form, then create columns based on your business processes.

1. Sign in to [Power Apps](https://make.powerapps.com/).
1. Select your environment, and go to the table that you want to add columns to. For this example, go to the work order table.
1. Select **New** > **Column** and enter the information for the new column. Learn more in [How to create and edit columns](/power-apps/maker/data-platform/create-edit-fields).
1. Save your changes.

## Edit columns

> [!IMPORTANT]
> Before you edit existing columns, be sure to consider possible system implications. Review the documentation to help avoid potential performance or process disruption.

Administrators can edit the display names and labels of existing fields. However, they can't change the properties. Here are some examples:

- Change the display name of the **Service Account** field to **Customer**.
- For the **System Status** field, which has multiple choice options, change the label of the *In Progress* choice option to *Work Started*.

From the table, under **Schema**, select **Columns**. Select the column that you want to edit, and then select **Edit column**.

:::image type="content" source="media/field-service-customize-column-fields/customization-form-field-choice-option-set.png" alt-text="Screenshot showing the Edit column option for the System Status field in the Power Apps.":::

You can make optional columns required, but you can't make required columns optional.

### Avoid editing columns properties

> [!IMPORTANT]
> Avoid editing column properties because it disrupts performance and processes.

For example, the following edits to column properties are unsupported and can cause issues during upgrades:

- Removing choice options.
- Adding choice options.
- Changing *Required* to *Optional*. (However, it's OK to change *Optional* to *Required*).
- Changing the behavior of a *Date Only* or *Date and Time* field. These fields must remain set to *User Local*. They can't be set to *Date Only* or *Time Zone independent*.

### Avoid deleting columns

> [!IMPORTANT]
> Don't delete existing columns. Deleting columns can cause unexpected issues.

Instead of deleting a column, hide fields or remove them from the forms, so that they aren't visible to users.

### Avoid changing the behavior of Date and Time fields

Don't change the behavior of *Date Only* or *Date and Time* columns included with Field Service. These changes aren't supported, reversible, or upgrade-safe.
