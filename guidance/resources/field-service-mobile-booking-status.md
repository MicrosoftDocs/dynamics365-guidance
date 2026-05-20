---
title: Add booking statuses with custom icons in the Field Service Mobile app
description: Learn how to add booking statuses with custom icons in the Dynamics 365 Field Service Mobile app
ms.topic: how-to
ms.date: 05/12/2026
author: heerpatelmsft
ms.author: heerpatel
ms.custom:
  - O25-FieldService
---

# Add booking statuses with custom icons in the Field Service Mobile app

Configure booking status options, with support for customized icons using a Booking Status Control adapted to mobile patterns. Enable an easily accessible button and drawer-based value selection, leading to improved click-targets and better usability.

## Configure booking status control in Power Apps

To configure a booking status control with icon support in Power Apps:

1. Add a Power Apps lookup component to the relevant form. Learn more at [Configure a lookup component on a form](/power-apps/maker/model-driven-apps/form-designer-add-configure-lookup).
1. Go to the **Components** property under the created lookup. Select **+ Component**.

   :::image type="content" source="media/field-service-mobile-booking-status-lookup.png" alt-text="Screenshot of components property of a lookup.":::
   
1. Search for the **Booking Status Control**.
1. Select **Work Order (Lookup)** for **WorkOrder** table column. This is a required property that isn't set by default, however it must be set to save and publish the component.
1. Select **Yes** for **Show icons**.

   :::image type="content" source="media/field-service-mobile-booking-status-control.png" alt-text="Screenshot of configuring a booking status control to show icons.":::
   
1. Select **Save and publish**.

## Create booking status in Field Service

To create a booking status with a custom icon in the Field Service Mobile app:

1. Go to the **Resources** Field Service area.
1. Go to **Booking Status**.
1. Select **+ New** and complete the fields in the **General** and **Field Service** tabs for the booking status to be created.
1. In the **Common** tab, paste the web resource image URL of the icon to be used for the new booking status.

   :::image type="content" source="media/field-service-booking-status-url.png" alt-text="Screenshot of the Common tab in the New Booking Status form displaying the image URL and status color.":::
   
1. Select **Save & close**.
   
   :::image type="content" source="media/field-service-mobile-booking-status-with-icons.png" alt-text="Screenshot of booking status experience with icons.":::
