---
title: Disable clickthrough on lookup values in forms in Field Service 
description: Disable clickthrough on lookup values to keep users on the current form in Field Service. Discover how to remove lookup hyperlinks in both the mobile and web app.
ms.topic: how-to
ms.date: 06/16/2026
author: v-wendysmith
ms.author: heerpatel
ms.reviewer: v-wesmith
ms.custom:
  - O25-FieldService
---

# Disable clickthrough on lookup values in forms

By default, lookup values in forms appear as hyperlinks, allowing users to open related records by selecting them. In some cases, you might want to prevent users from inadvertently navigating away from the current form. You can disable the clickthrough behavior on lookup fields to remove these hyperlinks. Configure this setting per form and per mobile or web app.

1. Open the form where you want to disable clickthrough on a lookup field.

1. [Configure a Power Apps lookup component](/power-apps/maker/model-driven-apps/form-designer-add-configure-lookup) or access a current lookup field.

1. Go to the **Components** property under the created lookup.

1. Select **+ Component**.

1. Search for the **Lookup Control** (not **Look-up Control**).

1. Select **Disable lookup clickthrough** for the **Lookup clickthrough** value.

   :::image type="content" source="media/field-service-disable-click.png" alt-text="Screenshot in Power Apps showing Disable lookup clickthrough.":::

   > [!NOTE]
   > To disable lookup clickthrough on a Drawer Lookup Control, follow the guidance in [Add a mobile lookup control (preview)](field-service-mobile-add-lookup.md).

1. Select **Done**.

1. Save and publish the form. The mobile app reflects the change after the next sync.

   :::image type="content" source="media/field-service-click-through-disabled.png" alt-text="Screenshot of a lookup field with clickthrough disabled.":::
