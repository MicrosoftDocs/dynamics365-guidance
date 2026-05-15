---
title: Add a mobile lookup control to the Field Service mobile app
description: Learn how to add a mobile lookup control for the Dynamics 365 Field Service mobile app.
ms.topic: how-to
ms.date: 05/8/2026
author: heerpatelmsft
ms.author: heerpatel
ms.custom:
  - O25-FieldService
---

# Add a mobile lookup control to the Field Service mobile app

Optimize the Field Service mobile lookup experience by configuring a Drawer Lookup control to a lookup component. Improve mobile navigation speed with reduced clicks, select quickly from lists with a modern bottom sheet, and increase overall user efficiency and satisfaction.

To use mobile lookup in Power Apps:

1. [Configure a Power Apps lookup component on form](/power-apps/maker/model-driven-apps/form-designer-add-configure-lookup).
1. Go to the **components** property under the created lookup.
1. Select **+ Component**.

   :::image type="content" source="media/field-service-mobile-lookup-components-new.png" alt-text="Screenshot of Components property for a lookup field.":::

1. Search for the **Drawer Lookup Control**.
    1. Select device experiences to enable the control for mobile and tablet.
    1. Select **Done**.

   :::image type="content" source="media/field-service-mobile-drawer-lookup.png" alt-text="Screenshot of Drawer Lookup Component for a lookup field.":::

   > [!NOTE]
   > The primary focus of this control is mobile and tablet. It might work on the web, but it's only supported on mobile and tablet.

1. Save and publish.

   :::image type="content" source="media/field-service-mobile-lookup-new.png" alt-text="Screenshot of Lookup in the mobile app after Drawer Lookup control.":::

## Limitations

Mobile lookup isn't supported for [multi-table lookups](/power-apps/developer/data-platform/webapi/multitable-lookup).
