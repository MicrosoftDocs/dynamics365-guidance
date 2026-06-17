---
title: Customize the booking view
description: Learn how to customize the default booking view in the Field Service mobile app.
ms.date: 06/10/2026
ms.topic: how-to
author: JonBaker007
ms.author: jobaker
ms.custom:
  - O25-FieldService
---

# Customize the booking view

Your tasks to customize the booking view depend on which version of the mobile app you're using: the original user experience or the new experience released in 2024.

## [Unified Interface UX](#tab/vCurrent)

By default, the booking calendar control shows a predefined set of details associated with bookings. You can customize this control to include up to three more columns with optional labels or change the incident type column.

If you're using the mobile app offline, make sure your mobile offline profile includes the record types from which you want to include attributes on the calendar.

For a guided walkthrough using the classic designer, check out the following video.
>
> [!VIDEO https://learn-video.azurefd.net/vod/player?id=af1f694e-21ad-4805-b8ef-426da1f92df7]

### Add columns to the Bookings view

Add the columns to the *Booking* view of the *Bookable Resource Booking* table from any table that has a relationship to the *Bookable Resource Booking* table. For columns that don't have a relationship, create a relationship between the bookable resource booking and that table.

In the following example, add work order priority from the *Work Order* table, and then add that column to the view. Learn more in: [Add columns to model-driven app views](/power-apps/maker/model-driven-apps/choose-and-configure-columns#adding-columns).

1. In Power Apps, open the *Bookable Resource Booking* table.

1. Select **Views** and open the default view.

1. Select the **Related** tab on the **Table columns** pane. Select the table that contains the columns you want to add. In this example, select **Work Order**.

   :::image type="content" source="media/field-service-mobile-calendar-control-1.png" alt-text="Screenshot of the Bookable Resource Booking table default view showing the related Work Order table in Power Apps." lightbox="media/field-service-mobile-calendar-control-1.png":::

1. Find and select the **Priority** column. The column is added to the view.

1. Right-click the **Priority** column and select **Edit table column**.

1. Select **Advanced options** and note the schema name of the column. You need it when customizing the field. In this example, the name is *msdyn_priority*.

1. Add other columns as needed. Save and close.

> [!NOTE]
> For columns from a different table, you must create a relationship between the bookable resource booking and that table. When referencing the relationship in the control, be sure to reference the full lookup field name as `fieldName.Attribute`.

### Configure the Booking Calendar Control to show the columns

After you add the desired columns to the view, configure the control properties.

1. From the default view of the *Bookable Resource Booking* table, select **Components** in the command bar.

1. Select **Add a component** and then select **Booking Calendar Control**. If the control isn't displayed, select **Get more components**, search for **Booking Calendar Control**, select it, and then select **Add**.

1. Select the control and enter column info. In **Custom Field 1**, enter the new field as `linkedEntity.attribute`. In this example, use `msdyn_workorder.msdyn_priority`. Learn more in: [Add a calendar control](/power-apps/maker/model-driven-apps/add-calendar-control#add-the-control-using-the-modern-app-designer).

1. You can also configure the optional custom field label associated with the custom field. This label is displayed as entered, with an added colon after the field and before the value. In the example, enter *Priority*.

   :::image type="content" source="media/field-service-mobile-calendar-control-2.png" alt-text="Screenshot of booking calendar control properties being edited in Power Apps." lightbox="media/field-service-mobile-calendar-control-2.png":::

1. For **Show component on**, make sure **Phone** and **Tablet** are selected.

1. Select **Done** and then **Save**. Save and publish.

The mobile app reflects the change after the next sync. Fields without data are hidden.

:::image type="content" source="media/field-service-mobile-calendar-control-3.png" alt-text="Screenshot of the Field Service mobile app with a customized calendar agenda view.":::

The calendar's day view shows custom fields when the booking duration is long enough to support the extra text. The app also shows custom data when opening booking details from the map view.

> [!NOTE]
> If you configure multiple views for the mobile app, include the new fields in each view that users can access from the mobile app.

## [New mobile UX](#tab/vNext)

The agenda view is the default view in the [new user experience of the Field Service mobile app](/dynamics365/field-service/mobile/set-up-field-service-mobile). It shows the list of bookings in chronological order that are assigned to the user who signs in to the app. Select **Home** in the bottom navigation to return to the home page. By default, the agenda view shows the following details associated with each booking:

- Account
- Incident type
- Address
- Booking status
- Start time and duration

:::image type="content" source="media/fs-agenda-view.png" alt-text="Device render of a mobile device showing bookings on the home page in the agenda view.":::

The agenda view shows data from the *Bookable Resource Booking* table and related tables. Booking status, start time, and duration always show. You can customize which data to show by adding, removing, or changing the order of the data columns. As a best practice, [consider using a solution to apply your customizations](/power-apps/maker/data-platform/solutions-overview).

Go to Power Apps and navigate to **Tables** > **Bookable Resource Booking** > **Views** and customize **Bookings - Agenda View**.

:::image type="content" source="media/field-service-agenda-view-power-apps.png" alt-text="Agenda view in the list of views in the Power Apps maker experience.":::

Columns in this view show on a booking card within the agenda. Keep the number of columns below 10 to maintain readability and performance. Don't add more than 25 columns to the view. To learn how to configure a view, see [Choose and configure columns in model-driven app views in Power Apps](/power-apps/maker/model-driven-apps/choose-and-configure-columns).

---
