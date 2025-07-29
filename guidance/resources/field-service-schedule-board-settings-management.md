---
title: Schedule board settings management control
description: Read about the Schedule board settings management control that can help users duplicate tasks and share bookings in Universal Resource Scheduling for Dynamics 365 Field Service.
ms.date: 10/29/2024
ms.topic: best-practice
author: edupont04
ms.author: delhalawani
ms.custom:
    - O25-FieldService
---

# Schedule board settings management control in Universal Resource Scheduling for Dynamics 365 Field Service

If you use Universal Resource Scheduling for Dynamics 365 Field Service, you might want to create copies of bookings with minor tweaks or similar changes. Microsoft provides an unmanaged solution, the **Schedule board settings management** control, that can help you in such cases. The **Schedule board settings management** control is a custom Power Apps component framework (PCF) control designed to enhance the management of schedule board settings in Dynamics 365 Field Service.

## Introduction

With Universal Resource Scheduling for Dynamics 365 Field Service, users can use the schedule board to quickly and easily allocate resources to resource requirements and create bookings to accomplish outstanding work. The schedule board has tabs that allow for different configurations for different specific scheduling needs. These tabs and their settings and configurations each get saved to the *Schedule Board Settings* table (`msdyn_scheduleboardsetting`), with [each setting mapping to a particular field](field-service-schedule-board-settings-field-mapping.md).

It's a common practice to have different board tabs for different scheduling needs, sometimes with limited changes of configurations between board tabs. The default board can be used to set [a baseline](/dynamics365/field-service/schedule-board-tab-settings#basic-section) of common configurations for schedule board tabs. However, there are times when requirements dictate the need for a copy of a nondefault board that only needs one or two changes made to the copy. In the standard solution, you must then create a new board and set each configuration one by one, but that can be a time-consuming experience.

Furthermore, [to share a schedule board tab with specific people](/dynamics365/field-service/schedule-board-tab-settings#share-a-schedule-board-tab-with-specific-people), you use the **Share** button on the *Schedule board setting* record's form, navigating there via the older Advanced Find UI via the **Advanced settings** link. The **Advanced settings** link directs users to the [Power Platform Environment Settings app](/power-platform/release-plan/2024wave1/power-apps/use-power-platform-environment-settings-app) that is generally available in 2025 and doesn't provide a link to the older Advanced Find UI. If a user performs an Advanced Find search for the *Schedule board settings* table in the modern Advanced Find UI, they can't open a schedule board form to share it with other users. Instead, that action opens the schedule board itself.

The **Schedule board settings management** control can help you bridge these gaps and more.

The following image illustrates the control.

:::image type="content" source="media/fs-schedule-board-settings-management-control.png" alt-text="Screenshot with fields." lightbox="media/fs-schedule-board-settings-management-control.png":::

## Support

This control source code and unmanaged solution are provided as-is. Bugs, feature addition/modification requests, and other changes are the responsibility of the end-user. You accept any responsibility for issues you might cause in modifying/copying schedule board settings via this component. Always thoroughly test components in a nonproduction environment.

## Install the schedule board settings management control

The **Schedule board settings management** control is an unmanaged solution that you download from a public GitHub repository. Follow the guidance under [Option 1](#option-1) unless you want to customize or extend the control as described under [Option 2](#option-2).  

### Option 1

1. Download the unmanaged solution from the GitHub repository at [https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Field%20Service/Component%20Library/URS/ScheduleBoardSettingsManagement](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Field%20Service/Component%20Library/URS/ScheduleBoardSettingsManagement).  

    The unmanaged solution contains the following components:

    - Schedule board settings management custom control

    - Field Service Extensions model-driven app and sitemap

    - Web resources (PNG and SVG) for the model-driven app icon and Board Management sitemap icon

2. In the Power Apps Maker portal, [import the solution](/power-apps/maker/data-platform/import-update-export-solutions) into the desired environment or environments.  

### Option 2

For more developer-oriented scenarios, you can clone and build the source code in this repository using standard PCF control build processes. You can then embed the customized control in the model-driven app of your choice.

1. Build the solution using the Power Apps CLI.

2. Import the solution into your Dynamics 365 environment.

3. Add the control to a model-driven app via the Navigation link page type with a URL field reference that follows this pattern: `/main.aspx?pagetype=control&controlName=o25fs_MicrosoftOptimize25.ScheduleBoardManagement&forceUCI=1`.

> [!NOTE]
> The control is a full-page control. It's not intended to be embedded in a form.

## How to use the schedule board settings management control

Once the solution has been imported, navigate to the Field Service Extensions model-driven app using the app picker in the upper left of any existing Dynamics 365 model-driven app.

The schedule board settings management control can be opened via the Board Management link in the sitemap navigation of the Field Service Extensions model-driven app.

The control loads a list of the schedule board settings records the logged in user currently has read access to, sorted alphabetically by name in an ascending fashion. The control also attempts to read the names of Views (`savedquery`) referenced by schedule board settings fields.

> [!NOTE]
> The Field Service Extensions model-driven app and the schedule board settings management control are intended for use by users with the **System Administrator** and **System Customizer** security roles. Other security roles might operate normally or have issues, depending on model-driven app access permissions and the granted `msdyn_scheduleboardsetting` permissions.

Use the **Copy Board** button to make a copy of the currently selected schedule board, and then specify a new name for the copy. You can make changes to [board settings](/dynamics365/field-service/schedule-board-tab-settings#board-settings) in the copy via the Schedule Board link on the left side.

Use the **Delete Board** button to remove the currently selected schedule board.

For enabled schedule boards, use **Disable Board** to remove it from the tabs. For disabled boards, use **Enable Board** to make it available again.

The pop-out style button next to the schedule board dropdown opens the currently selected schedule board setting record in a new tab. This can be used to [share](/power-platform/admin/wp-security-cds#record-sharing) the board with other users or teams for boards where the **Share Type** setting is set to **Specific people**.

Use the refresh button to refresh the list of schedule board settings currently in the dropdown menu.

A read-only view of the currently selected schedule board is shown on the page. The read-only view attempts to display JSON-based fields in a user-friendly format.

## Virtual PCF control

The GitHub repo also includes an alternative version of the **Schedule board settings management** PCF control that uses the [newer virtual PCF control framework](/power-apps/developer/component-framework/react-controls-platform-libraries). This framework allows for the control to use React and Fluent UI libraries that are already loaded by the platform at runtime, thereby not having to load those libraries itself. This results in a faster loading experience and a roughly 30% smaller control size of the bundle.js file. This version of the control is intended for a more developer-oriented audience and can be found at [https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Field%20Service/Component%20Library/URS/ScheduleBoardSettingsManagement_Virtual](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Field%20Service/Component%20Library/URS/ScheduleBoardSettingsManagement_Virtual).  

Find the reference documentation at [Schedule Board Setting in scheduling](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/projectcommon/scheduling/scheduleboardsetting).  

## Related resources

- [Schedule board tab settings - Field Service](/dynamics365/field-service/schedule-board-tab-settings)  
- [Schedule Board Setting in scheduling](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/projectcommon/scheduling/scheduleboardsetting)  
- [Field mapping for schedule board settings in Dynamics 365 Field Service](field-service-schedule-board-settings-field-mapping.md)  
