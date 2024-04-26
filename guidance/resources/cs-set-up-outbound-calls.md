---
title: Set up click-to-run outbound calls with Omnichannel
description: Learn how to set up click-to-run outbound calls with Omnichannel for Dynamics 365 Customer Service. Find the link to get the sample solution here.
author: rramju
ms.author: ramara
ms.reviewer: edupont
ms.topic: how-to #Required; don't change.
ms.collection: #Required; don't change.
ms.date: 06/21/2023
ms.custom: bap-template #Required; don't change.
---

# Set up click-to-run outbound calls with Omnichannel for Dynamics 365 Customer Service

***Applies to: Dynamics 365 Customer Service***

This article outlines the steps to use a custom control so that users can make outbound calls from a Customer Interaction Center (CIF) provider in Omnichannel for Dynamics 365 Customer Service. The sample solution is a resource that helps optimize the Dynamics 365 implementation. It includes a custom control that provides the capability to format a phone number and initiate an outbound call from a text or phone number field.

> [!IMPORTANT]
> The CIF provider doesn't offer any specific support method for outbound calls. Therefore, the custom control uses the Omnichannel capabilities to facilitate this functionality.

With the custom control, users can conveniently format phone numbers and initiate outbound calls directly from relevant fields. Therefore, the overall user experience is better, users can more efficiently handle customer interactions in Customer Service.

## Prerequisites

- [System requirements](/dynamics365/customer-service/channel-integration-framework/v2/system-requirements-channel-integration-framework-v2)
- [Get the samples and tools](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/Channel%20Integration%20Framework%20v2.0/ClickToDial/)

## Configuration steps

1. Download the package at [ClickToDial](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/Channel%20Integration%20Framework%20v2.0/ClickToDial/Solutions).

    Select either the managed package or the unmanaged package. Extract the files, and then open *OutBoundDialerControl* in Power Apps. Learn more in [Import solutions](/power-apps/maker/data-platform/import-update-export-solutions).

1. Add the custom control to the relevant field in the relevant entity. For example, add it to the **Mobile Phone** field in the Contact entity.

    1. If the component isn't listed, select **Add component**.
    1. In the **Field Properties** pane, on the **Controls** tab, select the **Add Control** action.
    1. Point to the **Outbound Dialer Control** control, and add it to the field properties.
    1. In the **Field Properties** pane, on the **Controls** tab, select the **Outbound Dialer Control** control, and then configure the relevant settings. The following screenshot shows an example of the settings that you can configure.

        :::image type="content" source="../media/outbound-calls-add-control.png" alt-text="Screenshot that show the settings for the custom control on the Controls tab of the Field Properties pane." lightbox="../media/outbound-calls-add-control.png":::

        For example, specify whether the control validates phone numbers. In addition, select whether the control is available only on phones and tablets, or whether it's also available in browsers.

1. Select **OK**, and then save and publish the form.

## Test the control

1. Open the relevant app where the form is configured with the control.

    For example, if you've set up the [Simulator for Channel Integration Framework v. 2.0 and Dynamics 365 Customer Service](cs-set-up-cif2-simulator.md), and you added the control to the **Contact** form, open the simulator, and go to the **Contact** form.

1. In the relevant form, select the phone symbol to call the contact. The information is passed to the CIF provider.

The following screenshot shows the control that renders a phone symbol for a contact in the simulator for Channel Integration Framework and Customer Service.

:::image type="content" source="../media/outbound-calls-use-control.png" alt-text="Screenshot that shows the Contact form with a phone symbol next to the Mobile Phone field.":::

## Related resources

- [Create and build a code component](/power-apps/developer/component-framework/create-custom-controls-using-pcf)
- [Package a code component](/power-apps/developer/component-framework/import-custom-controls)
- [Debug code components](/power-apps/developer/component-framework/debugging-custom-controls)
- [Add code components to a column or table in model-driven apps](/power-apps/developer/component-framework/add-custom-controls-to-a-field-or-entity)
- [Introduction to the voice channel](/dynamics365/customer-service/voice-channel)
- [Digital Contact Center Platform](/digital-contact-center-platform/)

<!--## Next steps-->

<!--## Tags

*Industries*: Contact center

*Products*: Dynamics 365 Customer Service

*Topics*: Outbound Dialer, Third Party Channel Provider-->
