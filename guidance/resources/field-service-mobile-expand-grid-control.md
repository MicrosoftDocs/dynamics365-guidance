---
title: Show more data and hide the row icon in the mobile app
description: Learn how to configure a grid to add more fields and remove icons in the Dynamics 365 Field Service mobile app.
ms.topic: how-to
ms.date: 06/11/2025
author: JonBaker007
ms.author: jobaker
ms.custom:
  - O25-FieldService
---

# Show more data and hide the row icon in the mobile app

Configure the Power Apps Grid control to hide the row icon and increase the number of columns in the mobile app grid. You can also configure the control on subgrids.

Support more fields so users can access comprehensive information at a glance, cutting down on time-consuming navigation. Streamline visuals by removing unnecessary icons to help workers stay focused on what matters most.

1. [Configure the Power Apps grid control](/power-apps/maker/model-driven-apps/the-power-apps-grid-control#configure-the-power-apps-grid-control) for the desired table.

1. In the grid **Properties**, make the control available for mobile devices.

1. Scroll down to **Show avatar** and set it to *No*. The colored circle showing the first letters of the row value is hidden from the list view.

1. Scroll to **Number of columns for list view** and adjust the value to the desired number of columns. The default number of columns for a list is three. The maximum number of columns is 10.

1. To enhance the mobile experience on iOS devices, consider setting the **Enable multi-select** property to No. This configuration ensures that tapping a record initiates navigation rather than selection, reducing confusion and streamlining user interactions.

1. Save and publish.

You can also configure the Power Apps Grid control to subgrids within a form. Add the control as a component on the subgrid in the form and then configure it.
