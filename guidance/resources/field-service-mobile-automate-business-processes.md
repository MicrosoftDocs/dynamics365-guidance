---
title: Create workflows and scripts for the mobile app
description: Learn about workflows and scripts for the Field Service mobile app.
ms.topic: how-to
ms.date: 09/08/2025
author: JonBaker007
ms.author: jobaker
ms.custom:
  - O25-FieldService
---

# Create workflows and scripts for the mobile app

Administrators can use tools like Power Automate flows, classic background workflows, JavaScript, or business rules to automate business processes. Some processes work when the Dynamics 365 Field Service mobile app runs [offline first](/dynamics365/field-service/mobile/work-offline), and others require internet connectivity.

## Power Automate flows and classic Dataverse workflows

Workflows and flows are commonly used to automate tasks based on triggers and conditions. We recommend you [use Power Automate to build flows](/power-automate/flow-types) and replace existing workflows with flows. Flows offer several advantages. Learn more in [Comparison of workflows and flow](/power-automate/replace-workflows-with-flows).

Workflows and flows require an internet connection. In offline-first mode with an internet connection, saving a record triggers the workflow or flow. Results download during the next data sync.

## Business rules

Business rules and recommendations let you apply logic without writing code or creating plug-ins. Learn more in [Create a business rule for a table](/power-apps/maker/data-platform/data-platform-create-business-rule).

## Custom process actions

Actions provide many options to create business logic. [Use custom process actions](/power-apps/maker/data-platform/actions) to perform several operations in sequence.

Actions require an internet connection.

## JavaScript web resources

You can add [JavaScript web resources](/power-apps/developer/model-driven-apps/script-jscript-web-resources) to mobile forms and include them in offline profiles.

JavaScript web resources run with or without internet connection.

Review the article [Mobile offline capabilities and limitations](/power-apps/mobile/offline-capabilities) for potential limitations regarding your planned code.

## Debugging the mobile app

You can debug custom code using the Windows or Android application:

- Debug JavaScript with the [Windows application](/power-apps/developer/model-driven-apps/clientapi/debug-javascript-code#debug-javascript-in-the-windows-desktop-app).
- Debug JavaScript with the [Android application](/power-apps/developer/model-driven-apps/clientapi/debug-javascript-code#debug-javascript-in-mobile-apps).

