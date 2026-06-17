---
title: Add a Control for Note-Taking to the Field Service Mobile App (preview)
description: Learn how to add a note-taking control for the Dynamics 365 Field Service mobile app.
ms.topic: how-to
ms.date: 06/08/2026
author: heerpatelmsft
ms.author: heerpatel
ms.custom:
  - O25-FieldService
---

# Add a control for note-taking to the Field Service mobile app (preview)

You can optimize the Field Service mobile note-taking experience by configuring a control for taking notes. Enable quick and seamless note-taking supported through an overlay screen for text input and image and video upload, including the ability to create a note and **add multiple images and videos**, enhancing usability.

## Configure note-taking

In [Power Apps](https://make.powerapps.com), open the app where you want to configure note-taking, and then complete the following steps:

1. Add a data column with the **Data type** field set to **Single line of text** and the **Required** field set to **Optional** as shown in the following screenshot.  

    :::image type="content" source="media/field-service-mobile-take-notes-column.png" alt-text="Screenshot of Column creation." lightbox="media/field-service-mobile-take-notes-column.png":::

    Learn more at [Create and edit columns in Dataverse using Power Apps](/power-apps/maker/data-platform/create-edit-field-portal).

1. Add the new column to the form on which you want to configure note-taking.
1. Select the columns on the form. In the **Display options** property, select **Hide label**.

    :::image type="content" source="media/field-service-mobile-take-notes-options.png" alt-text="Screenshot of Display options property for a column with the Hide label checkbox selected.":::

1. In the **Components** property, select **+ Component**.

    :::image type="content" source="media/field-service-mobile-take-notes-component.png" alt-text="Screenshot of Components property for a column." lightbox="media/field-service-mobile-take-notes-component.png":::

1. Search for and select the **Mobile Notes** control, and then configure the following options:

    :::image type="content" source="media/field-service-mobile-take-notes-config.png" alt-text="Screenshot of Mobile Notes component for a column.":::

    1. For **Display mode**, select one of the following options:

       - **All** - show both the **+ Add Notes** button and the notes wall.
       - **Add Notes** - Hides the note wall and shows the **+ Add Notes** button. Users can only view existing notes in the Timeline.
       - **Notes Wall** - Hides the **+ Add Notes** button and shows only the notes wall. Users create notes from the Timeline.

    1. For **Attach to**, select one of the following options:
       - **Current Form** - associate notes with the current form's record.
       - **Top Level Form** - associate the notes with the parent form's record when the form is nested. If there's no nested form, notes are associated with the current form.

       > [!NOTE]
       > The primary focus of this control is mobile and tablet. It might work on the web, but it's only supported on mobile and tablet.

1. Save and publish the form.

The following screenshot shows how a user adds notes in the Field Service mobile app. If a user uploads multiple images or videos, the app creates a separate note for each uploaded file, using the same title and text.

   :::image type="content" source="media/field-service-mobile-notes-experience.png" alt-text="Screenshot of note-taking process after adding a control for taking notes." lightbox="media/field-service-mobile-notes-experience.png":::

## Enable attachments on a new table

When you create a new table for notes, select the **Enable attachments (including notes and files)** checkbox, as shown in the following screenshot.

:::image type="content" source="media/field-service-mobile-take-notes-new-table.png" alt-text="Screenshot of creating a new table with the Enable attachments checkbox selected.":::

## Related content

- [Create workflows and scripts for the mobile app](field-service-mobile-automate-business-processes.md)  
- [Customization best practices](field-service-customize-best-practices.md)    
