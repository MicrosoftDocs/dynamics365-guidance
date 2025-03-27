---
title: Implement SLAs for work orders.
description: Learn how to implement SLAs for work orders in Dynamics 365 Field Service.
ms.date: 03/04/2025
ms.topic: how-to
author: SabrinaDiBartolomeo
ms.author: sabrinadi
ms.custom:
  - O25-FieldService
---

# Implement service level agreements for work orders

This article provides examples of how you can use service level agreements (SLA) in the context of a work order. The article includes steps for how to create the sample SLA. It also delves into application lifecycle management for SLAs, outlining the steps to configure SLAs in a development environment, integrate the configuration into a solution, and deploy it to a target environment.

> [!NOTE]
> This article references the documentation related to [SLAs in Dynamics 365 Field Service](/dynamics365/field-service/sla-work-orders). Since SLAs can be applied to any SLA-enabled entity record, including custom tables, this information is also relevant beyond the context where the SLA was first implemented.

## Introduction

Service level agreements (SLAs) are effective for managing work orders by ensuring that services meet predefined standards. Here are some practical examples of how SLAs can be applied in this context:

- **Response times** example

  An SLA might stipulate that all high-priority work orders must receive a response within 2 hours of creation, medium-priority work orders within 12 hours, and low-priority work orders within 24 hours.  
- **Resolution times** example

  An SLA might specify that work orders related to critical issues must be resolved within 4 hours, while less critical ones within 24 hours. 
- **Service availability** example

  An SLA might require that technical support is available 24/7 for emergency work orders, while for nonurgent work orders, support might only be available during business hours.
- **Escalation procedures** example

  An SLA might define escalation procedures for work orders that aren't resolved within the specified times, detailing who should be contacted and what actions should be taken.

Apply service-level agreements to a work order in several ways:

- Automatically update the SLA information using a Power Automate flow or a custom plug-in designed for the entity.
- Manually applying SLAs to records.
- Set a specific SLA as the default.

SLAs can also be updated. When an SLA is reapplied, all its items are reevaluated. Learn more at [Apply SLAs](/dynamics365/customer-service/administer/apply-slas).

## Enable work orders for service-level agreements 

In your development environment, you probably already added the **Work Order** table to your solution. If not, add it to the solution you use to transport your customizations by using the **Add existing table** feature, and then selecting the **Work Order** table with the **Include table metadata** option. This setting is essential as it includes the table settings in the solution. If the **Work Order** table is already part of the solution, verify that the table metadata is included by taking the following steps:

1. Go to **Work Order** > **Advanced** > **Table segmentation properties**.
2. In the **Table segmentation properties**, check if the **Include table metadata** field is selected. If not, select it, choose the **Save** action, and then go to **Work Order > Publish**.

> [!TIP]
> Learn more at [How to add an existing component to a solution](/power-apps/maker/data-platform/create-solution#add-an-existing-component-to-a-solution). 

Now you're ready to enable the **Work Order** table for SLA. Go to [Enable SLA functionality for Field Service](/dynamics365/field-service/sla-work-orders#enable-sla-functionality-for-field-service).

> [!IMPORTANT]
> This option can't be switched off once it's switched on.

## Example 1: Configure work order resolution service-level agreement

As a first example, let's create a service level agreement that defines the resolution times for a work order based on its priority:

- **High priority**: Must be completed within 2 days.
- **Medium priority**: Must be completed within 7 days.
- **Low priority**: Must be completed within 15 days.

1. Create an SLA with *Work Order Resolution SLA* as the name and *Work Order* as the value of the **Primary entity** field. For more information, go to [Create an SLA](/dynamics365/field-service/sla-work-orders#create-an-sla).
2. Create three SLA items for the three values of the work order priority: High, Medium, and Low.

### Create an SLA item for high priority work orders

1. Create an SLA item. Fill in the fields as outlined in the following table.

    |Field|Value|
    |-|-|
    |**Name**|*Work Order Resolution High Priority*|
    |**Allow Pause and Resume**|**No**|
    |**Allow Custom Time Calculation**|**No**|

1. Create a New SLA KPI. Fill in the fields as outlined in the following table.

    |Field|Value|
    |-|-|
    |**Name**|Work Order Resolution SLA KPI|
    |**Entity Name**|Work Order|
    |**KPI Field**|Work Order Resolution KPI|
    |**Applicable From**|Created On|

1. Save and close the form.

   The newly created **Work Order Resolution SLA KPI** is now visible in the **KPI** field of the **New SLA Item** form. You can reuse it for the SLA items for medium and low priority work orders created next.

1. In the **Applicable When** section, select **+ Add > Add row**, and enter the condition **Priority (Work Order) Equals High**.

1. In the **Success Conditions** section, select **+ Add > Add row**, and enter the condition **System Status (Work Order) Equals Completed**.

1. In the **Warn and Fail Duration** section, enter the following conditions:

    |Field|Value|
    |-|-|
    |**Warn After**|1 day|
    |**Failure After**|2 days|

1. Save and close the form.

### Create an SLA item for medium priority work orders

1. Create an SLA item. Fill in the fields as outlined in the following table.

    |Field|Value|
    |-|-|
    |**Name**|*Work Order Resolution Medium Priority*|
    |**KPI**|**Work Order Resolution SLA KPI**|
    |**Allow Pause and Resume**|**No**|
    |**Allow Custom Time Calculation**|**No**|

1. In the **Applicable When** section, select **+ Add > Add row**, and enter the condition **Priority (Work Order) Equals Medium**.

1. In the **Success Conditions** section, select **+ Add > Add row**, and enter the condition **System Status (Work Order) Equals Completed**.

1. In the **Warn and Fail Duration** section, enter the following conditions:

    |Field|Value|
    |-|-|
    |**Warn After**|4 days|
    |**Failure After**|7 days|

1. Save and close the form.

### Create an SLA item for low priority work orders

1. Create an SLA item. Fill in the fields as outlined in the following table.

    |Field|Value|
    |-|-|
    |**Name**|*Work Order Resolution Low Priority*|
    |**KPI**|**Work Order Resolution SLA KPI**|
    |**Allow Pause and Resume**|**No**|
    |**Allow Custom Time Calculation**|**No**|

1. In the **Applicable When** section, select **+ Add > Add row**, and enter the condition **Priority (Work Order) Equals Low**.

1. In the **Success Conditions** section, select **+ Add > Add row**, and enter the condition **System Status (Work Order) Equals Completed**.

1. In the **Warn and Fail Duration** section, enter the following conditions:

    |Field|Value|
    |-|-|
    |**Warn After**|10 days|
    |**Failure After**|15 days|

1. Save and close the form.

> [!NOTE]
> Ignore Business Hours for now.

### Activate the work order resolution service-level agreement

You can have multiple service-level agreements active, but only one can be set as the default. The default SLA automatically applies to any new work order unless a different SLA is specifically assigned.

1. Select the **Work Order Resolution SLA** in the **All Service Level Agreements** view.
2. Select **Active** and then choose **Activate** in the **Confirm SLA Activation** dialog.
3. After activating the SLA, select **Set As Default**, and confirm with **OK**.

> [!TIP]
> To remove the default setting from an SLA, just deactivate it and then reactivate it.

### Add SLA information to the Work Order form

1. Before testing the SLA, [update the **Work Order** form to display the service level agreements](/dynamics365/field-service/sla-work-orders#add-the-sla-field-to-the-work-order-form). 
1. Add a **new section** to the form and include a **new Subgrid**:

    |Field|Value|
    |-|-|
    |**Table**| *SLA KPI Instances (Regarding)*|
    |**Default view**| *SLA KPI Instances List View*|

1. Save and publish your changes.

> [!TIP]
> If you came to this spot from the section under Example 2, then once you complete the steps here, then jump back to the [Test the work order arrival time service-level agreement](#test-the-work-order-arrival-time-service-level-agreement) section and carry on with Example 2.

### Test the work order resolution service-level agreement

You can now test the work order resolution service-level agreement in your Development environment. To do this, create a new work order, fill in the required information, set the Priority to **High**, and save it.

Observe the following:

- The Work Order Resolution SLA is automatically applied.
- In the SLA subgrid, you'll see the Status as **In Progress**, and the **Failure Time** indicating the deadline by which the Work Order must be completed.

:::image type="content" source="media/fs-implementing-sla-work-order1.svg" alt-text="Screenshot of Work Order resolution SLA high priority." lightbox="media/fs-implementing-sla-work-order1.svg":::

If you later discover that the Work Order should have a Low priority, update the priority and save it again.

You'll observe the following actions:

- The previous SLA Item Instance has been canceled, and a new Instance has been created and is now in progress.
- The new Failure Time has been recalculated based on the newly selected Priority.
- This information can also be added to the [Configurable Work Order summary](/dynamics365/field-service/work-order-recap).
:::image type="content" source="media/fs-implementing-sla-work-order2.svg" alt-text="Screenshot of Work Order resolution SLA low priority with Copilot summary." lightbox="media/fs-implementing-sla-work-order2.svg":::

## Example 2: Configure work order arrival time service-level agreement

Let's look at another example. To ensure urgent repairs receive prompt attention, some Work Orders may require swift action from a technician. We can establish a service level agreement (SLA) that specifies the arrival time for a work order based on its priority:

- **High priority**: The technician should arrive within 2 hours.
- **Medium priority**: The technician should arrive within 1 day.
- **Low priority**: The technician should arrive within 2 days. 

1. Create an SLA with *Work Order Arrival Time SLA* as the name and *Work Order* as the value of the **Primary entity** field. For more information, go to [Create an SLA](/dynamics365/field-service/sla-work-orders#create-an-sla).
1. Create three SLA items for the three values of the work order priority: High, Medium, and Low.

### Create an SLA item for arrival time on high priority work orders

1. Create an SLA item. Fill in the fields as outlined in the following table.

    |Field|Value|
    |-|-|
    |**Name**|*Work Order Arrival Time High Priority*|
    |**Allow Pause and Resume**|**No**|
    |**Allow Custom Time Calculation**|**No**|

1. Create a New SLA KPI. Fill in the fields as outlined in the following table.

    |Field|Value|
    |-|-|
    |**Name**|Work Order Arrival Time SLA KPI|
    |**Entity Name**|Work Order|
    |**KPI Field**|Work Order Arrival Time KPI|
    |**Applicable From**|Created On|

1. Save and close the form.

    This new created **Work Order Arrival Time SLA KPI** is now visible in the **KPI** field of the **New SLA Item** form. You can reuse it for the SLA items for medium and low priority work orders that we create next.  

1. In the **Applicable When** section, select **+ Add > Add row**, and enter the condition **Priority (Work Order) Equals High**.

1. In the **Success Conditions** section, select **+ Add > Add row**, and enter the condition **First Arrived On (Work Order) Contains data**.

1. In the **Warn and Fail Duration** section, enter the following conditions:

    |Field|Value|
    |-|-|
    |**Warn After**|1 hour|
    |**Failure After**|2 hours|

1. Save and close the form.

### Create an SLA item for arrival time on medium priority work orders

1. Create an SLA item. Fill in the fields as outlined in the following table.

    |Field|Value|
    |-|-|
    |**Name**|*Work Order Arrival Time Medium Priority*|
    |**KPI**|**Work Order Arrival Time SLA KPI**|
    |**Allow Pause and Resume**|**No**|
    |**Allow Custom Time Calculation**|**No**|

1. In the **Applicable When** section, select **+ Add > Add row**, and enter the condition **Priority (Work Order) Equals Medium**.

1. In the **Success Conditions** section, select **+ Add > Add row**, and enter the condition **First Arrived On (Work Order) Contains data**.

1. In the **Warn and Fail Duration** section, enter the following conditions:

    |Field|Value|
    |-|-|
    |**Warn After**|4 hours|
    |**Failure After**|1 day|

1. Save and close the form.

### Create an SLA item for arrival time on low priority work orders

1. Create an SLA item. Fill in the fields as outlined in the following table.

    |Field|Value|
    |-|-|
    |**Name**|*Work Order Arrival Time Low Priority*|
    |**KPI**|**Work Order Arrival Time SLA KPI**|
    |**Allow Pause and Resume**|**No**|
    |**Allow Custom Time Calculation**|**No**|

1. In the **Applicable When** section, select **+ Add > Add row**, and enter the condition **Priority (Work Order) Equals Low**.

1. In the **Success Conditions** section, select **+ Add > Add row**, and enter the condition **First Arrived On (Work Order) Contains data**.

1. In the **Warn and Fail Duration** section, enter the following conditions:

    |Field|Value|
    |-|-|
    |**Warn After**|1 day|
    |**Failure After**|2 days|

1. Save and close the form.

> [!NOTE]
> Ignore Business Hours for now.

### Activate work order arrival time service-level agreement

Given that multiple service-level agreements can be active simultaneously, we can now activate this second SLA and set it as the default.  

1. Select **Work Order Arrival Time SLA** in the **All Service Level Agreements** view.
1. In the **Confirm SLA Activation** dialog box, select **Active**, and then choose **Activate**.
1. After activating the SLA, select **Set As Default**, and confirm by choosing **OK**.

> [!TIP]
> To remove the default setting from an SLA, just deactivate it, and then reactivate it.

### Add the SLA to the Work Order form

If you didn't follow the steps in Example 1, go back to the [Add SLA information to the Work Order form](#add-sla-information-to-the-work-order-form) section and follow the steps there. Then come back to the [Test the work order arrival time service-level agreement](#test-the-work-order-arrival-time-service-level-agreement) section.

### Test the work order arrival time service-level agreement

You can now test the arrival time service-level agreement in your development environment. To do this, create a new work order, fill in the required information, set the Priority to **High**, and save it.

You should observe the following activities:

- The Work Order Arrival Time SLA is automatically applied.
- In the SLA subgrid, you'll see the status as **In Progress**, and the **Failure Time** indicating the deadline for the technician's arrival.
- The **Promised window** was set accordingly due to a Field Service setting, **Field Service SLA Configuration**. This setting is on by default in all Field Service environments.

:::image type="content" source="media/fs-implementing-sla-work-order3.svg" alt-text="Screenshot of Work Order arrival time SLA high priority with Copilot summary." lightbox="media/fs-implementing-sla-work-order3.svg":::

> [!TIP]
> Users can choose a different SLA after one has been set. Many organizations don't have a default SLA. Instead, they decide based on specific criteria whether to use the resolution service-level agreement or the arrival time service-level agreement each time. In this example, you can modify it from the UI since the SLA field is visible and editable in the form. However, as mentioned earlier, you ca also modify it using other techniques, set the SLA field as  read-only or not visible, and thereby prevent manual changes to the SLA field.

## Business hours and holiday calendars

You might have noticed that each service level agreement item record lets you select a *business hour schedule*. This helps set up when the service team is available, including business hours for each day of the week and days off.

To ensure SLAs are tracked correctly, combine the business hour schedule with a holiday calendar. This way, SLAs aren't affected when the service team is off.

For example, if the team has an SLA to complete work orders within four business hours, adding a holiday schedule to the service calendar ensures that holiday closures don't affect the SLA.

> [!WARNING]
> Set up business hour schedules and holiday calendars directly in the development environment. When exporting the solution, all SLA-related components and their dependencies, including linked schedules and calendars, will also be exported. However, this is *only* possible if the **Enable calendar export and import** setting is manually set to **Yes** in both the development and target environments. Enable this setting in the Power Platform Environment Settings app by navigating to Business > Service Management > Service configuration settings.

To create a holiday calendar record, open the **Power Platform Environment Settings** app, and select **Business > Service Management > Holiday schedule**. Learn more at [Create and manage holiday schedules](/dynamics365/customer-service/administer/set-up-holiday-schedule).

To create a business hour schedule, or *customer service schedule*, open the **Power Platform Environment Settings** app, and select **Business > Service Management > Customer service schedule**. The holiday calendar can be linked to a customer service schedule. Learn more at [Create customer service schedule and define the work hours](/dynamics365/customer-service/administer/create-customer-service-schedule-define-work-hours).

## How to transport the Service Level Agreements to a target environment using managed solutions

If you followed the guide, you should now have the **Work Order** entity in your solution, along with the customizations needed to display the SLAs.

> [!WARNING]
> Don't use the default publisher that comes with an environment. When you start making customizations, create a new publisher instead of using the default one. Try to avoid creating more publishers unless you have to. Learn more at [Solution concepts with Power Platform](/power-platform/alm/solution-concepts-alm#solution-publisher).

Next, add the SLA records to the solution. Open the **Power Platform Environment Settings** app, navigate to **Customization** > **Customizations** > **Solution**. Open your solution, select **Add existing > Rules > SLA**, choose the SLAs you created, and then select **Add**.

> [!TIP]
> An even better approach is to create the SLAs directly within the solution by using the + New > Rules > SLA feature.

Next, export SLAs from the development environment and import them with a managed solution to a target environment along with other customizations using your preferred mechanism: pipelines in Power Platform, ADO pipelines, or others.

After the import, the SLA's state in the target system changes from **Active** to **Draft**. However, you can restore the same *isdefault* and *statecode* values of the development environment using a flow. Below is an example of a Power Automate flow created in the development environment, outside of any solution, that queries these values from development and then connects to a specific target environment to perform an update. This update creates active layers for the SLA records and isn't supported if you have enabled the **Block Unmanaged Customizations** option in the target environment.

:::image type="content" source="media/fs-implementing-sla-work-order4.svg" alt-text="Screenshot of a Power Automate flow." lightbox="media/fs-implementing-sla-work-order4.svg":::

## Related resources

- [SLA limitation](/dynamics365/customer-service/administer/sla-limitations)
- [SLA for work orders](/dynamics365/field-service/sla-work-orders)
- [SLA for work orders training](/training/modules/use-service-level-agreements-entitlements/)
