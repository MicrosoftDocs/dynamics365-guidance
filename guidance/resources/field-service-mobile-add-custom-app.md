---
title: Add a custom app module to the Field Service mobile app
description: Learn how to create a custom app module for the Dynamics 365 Field Service mobile app.
ms.topic: how-to
ms.date: 09/08/2025
author: JonBaker007
ms.author: jobaker
ms.custom:
  - O25-FieldService
---

# Add a custom app module to the Field Service mobile app

We recommend using the standard Field Service Mobile app module. However, sometimes an organization wants to give frontline workers access to another custom app module to enable other business use cases and processes.

Custom app modules don't include all out-of-box business logic, such as booking travel time calculations, available in the standard Field Service Mobile app module.

## Create a custom app module

Create a custom app module based on the Field Service Mobile app module. Reuse components and the sitemap of the Field Service Mobile app module as a starting point to customize your experience.

1. In Dynamics 365, go to the list of your app modules and select **Create new App**. The app designer opens in Power Apps.

1. Enter the **Name** and other optional details. Expand **Advanced**, and select **Use components from a custom solution**.

1. Set *Field Service* as the solution and *Field Service Mobile* as the sitemap. Select **Create**.

1. Your new app module contains all standard Field Service Mobile app module entities. Add items to the sitemap and customize your app module.

1. After adding items to the sitemap, select **Save and Publish**.

## Make the custom app module available in the mobile app

After creating the custom app module, make it available in the Field Service mobile app:

1. In the Power Apps Designer, select **Settings**.

1. Under **General**, expand **Advanced settings**.

   :::image type="content" source="media/field-service-customize-forms/field-service-mobile-primary-player.jpg" alt-text="Screenshot of the primary mobile player in Power Apps." :::

1. Set **Primary Mobile Player** to *Field Service (Dynamics 365)*.

1. Close the settings dialog and **Save and Publish** your app module.

To access the custom app, sign in to the Field Service mobile app and select the app from the app picker.

> [!NOTE]
> If you don't see the app module:
>
> - Make sure users have a [predefined security role](/power-platform/admin/database-security) in the environment where the app is located. If a predefined security role is assigned to a user through a Dataverse team, use a Microsoft Entra ID group team. Users can't see model-driven apps if a predefined security role is assigned using a Dataverse owner team.
> - Check the roles assigned to the app module and ensure the user accessing it has the same role.
> - In sandbox environments, ensure "Show non-production apps" is enabled in the mobile app.
