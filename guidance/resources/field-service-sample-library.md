---
title: Library of tools and guidance for Field Service
description: Read about the collection of tips, tricks, answers to popular questions, and other guidance that can help our customers and partners create and deploy solutions with Field Service quickly and easily.
ms.date: 11/11/2025
ms.topic: concept-article
author: edupont04
ms.author: erdipple
ms.custom:
    - O25-FieldService
---

# Library of tools and guidance for Dynamics 365 Field Service

***Applies to: Dynamics 365 Field Service***

This collection of sample solutions, components, and documentation can help Field Service implementors customize, configure, and operate the solution. The library offers reusable and easy-to-follow resources for Field Service developers and users.  

> [!IMPORTANT]
> Sample codes, components (solutions), and documents created by the community aren't supported by Microsoft. If you have questions or issues with community tools, contact the tool's publisher.

## Areas

The following sections outline the content of the collection. Each section includes links to the corresponding articles and samples.

### Scheduling

- Add crew information to the resource cell template.

  A core element in this scenario is the flexibility to format the resource card shown on the schedule board. This sample shows how you can add crew membership information to the resource card. Learn more at [Add crew information to resource cells](field-service-resource-cell-template.md). For an introduction to the area, go to [Customize the schedule board with a custom resource attribute](/dynamics365/field-service/extend-schedule-board-custom-resource-attribute).

- Customize the template for bookings.

  A core element in this scenario is the flexibility to format the booking slot shown on the schedule board. We show an example of how you can add a custom icon to the booking template based on the work order incident type. Learn more at [Customize the template for bookings](field-service-customize-booking-template.md). For an introduction to the area, go to [Edit schedule board booking templates](/dynamics365/field-service/booking-template).

- Schedule board settings management control

  If you use Universal Resource Scheduling for Dynamics 365 Field Service, you might want to create copies of bookings with minor tweaks or similar changes. Microsoft has published an unmanaged solution, the **Schedule board settings management** control, that can help you in such cases. Learn more at [Schedule board settings management control](field-service-schedule-board-settings-management.md).  

- Field mapping for the schedule board settings

  Each field in the board settings maps to a particular column in the schedule board settings record for the relevant section. This information can be useful if you have to troubleshoot something about the schedule boards. Learn more at [Field mapping for schedule board settings in Dynamics 365 Field Service](field-service-schedule-board-settings-field-mapping.md).  

- Vendor self-service for technician management

  Organizations that deal with field service want to efficiently manage external vendors and contractors. Find an article that illustrates now to configure that in a solution with Dynamics 365 Field Service, including customization to meet specific business needs at [Vendor self-service for technician management](field-service-vendor-self-service-technician-management.md).  

### Work orders

- Work order summary configuration template

  Administrators who want to replace the default summary of work orders in Dynamics 365 Field Service and configure their own to meet their business needs must start from scratch to set up the configuration. Learn more at [Work order summary configuration](field-service-work-order-summary-configuration-template.md).

- Customized work order summary

  Organizations often begin service requests as support cases, capturing key context like issue descriptions, urgency, and communication history. When these cases are converted into work orders, technicians may lose access to this valuable information. You can extend work order summaries to include fields from both standard and custom tables so that technicians are fully prepared before site visits. You can also include fields from related case entities. Learn more at [Customized work order summary with fields from custom tables](field-service-work-order-summary-custom-tables.md) and [Custom work order summary with related case details](field-service-work-order-summary-related-case-details.md), respectively.

- Transport summary configurations across environments

  Copilot in Field Service provides predefined summaries for specific tables. With summary configuration, administrators can replace the default summaries and configure their own to tailor to their business needs. They can configure the summary for two tables: Work Order and Bookable Resource Booking. Learn more at [Transport summary configurations across environments](field-service-deploy-transport-summary-configuration.md).

### Field Service Mobile

- Add a custom app module to the Field Service mobile app

  You can create a custom app module to enable other use cases and process that your frontline workers can access. Use the Field Service Mobile app module as a base to reuse components. You can make the custom app available in the mobile app. Learn more at [Add a custom app module to the Field Service mobile app](field-service-mobile-add-custom-app.md).

- Add custom service reports in Dynamics 365 Field Service

  You can implement a reporting solution with a custom control and relevant customizations so that technicians can generate service reports that summarize their work. The custom control works well in Field Service Mobile, which your technicians will appreciate. Learn more at [Add custom service reports in Dynamics 365 Field Service](field-service-service-reports-solution.md).

- Create workflows and scripts for the Field Service mobile app

  You can automate business processes to work with the Field Service mobile app. Use tools such as Power Automate flows, Dataverse workflows, JavaScript, or business rules. Learn more at [Create workflows and scripts for the mobile app](field-service-mobile-automate-business-processes.md).

- Customize the mobile app booking view

  You can customize the booking view on the mobile app by adding custom fields, including fields from different tables such as the Work Order table. Learn more at [Customize the booking view](field-service-mobile-customize-booking-view.md).

- Edit the booking and work order form

  You can customize the **Booking and Work Order** form in the Field Service mobile app to meet your business needs. Learn more at [Edit the booking and work order form](field-service-mobile-change-work-order-booking-form.md).

- Edit the navigation and views

  In the Field Service mobile app, you can change navigation, forms, and views to suit your business purposes. Learn more at [Edit the navigation and views on the mobile app](field-service-mobile-edit-navigation-views.md).

- Use deep links to the Field Service mobile app

  Because multiple apps might be needed to complete onsite work, you can allow technicians to create deep links from the Dynamics 365 Field Service mobile app to other apps and vice versa. Learn more at [Use deep links to the Field Service mobile app](field-service-mobile-use-deep-links.md).

- Use Power Apps to configure the Field Service mobile app

  For other customization uses with Power Apps, go to [Use Power Apps to configure the Field Service mobile app](field-service-mobile-customize-powerapps.md).  

### Field Service web

- Customize the desktop experience

  System customizers add custom fields to entity forms to capture information that is specific to their industry and business, to run business processes, and to collect information to report. However, too many custom fields on a form can cause performance issues. Learn more at [Customization best practices](field-service-customize-best-practices.md).  

- Customize the work order form

  Customizing forms correctly is important for maximizing performance. Form customizations affect form load and save times. Proper customization improves usability, making it easier for users to view and update information.  Learn more at [Customize the work order form](field-service-customize-forms.md).  

### Copilot Studio

- Build an agent in Copilot Studio to create sample data in Dynamics 365 Field Service

  With Copilot Studio, you can take advantage of generative AI and integrations with Dynamics 365 to generate sample data in locations where your organization does business. Learn more at [Build an agent in Copilot Studio to create sample data](/dynamics365/guidance/resources/field-service-deploy-copilot-studio-create-sample-data).

- Use Copilot to create sample data for Field Service

  Go through the steps to create account and contact data that you can use for demonstrations of Dynamics 365 Field Service environments. Learn more at [Use Copilot to create sample data for Field Service](/dynamics365/guidance/resources/field-service-copilot-import-sample-data).

- Streamline inventory visibility

  You can extend the Field Service Copilot chat to integrate with the Inventory Visibility app in Supply Chain Management. By integrating external data sources and customizing the Copilot agent using Copilot Studio, Field Service Managers gain real-time access to inventory data, enabling more efficient and informed decision-making. Learn more at [Streamline inventory visibility in Field Service](field-service-streamline-inventory-visibility.md).

## Related content

- [Use the schedule board in Field Service](/dynamics365/field-service/work-with-schedule-board)  
- [Universal Resource Scheduling for Dynamics 365 Field Service overview](/dynamics365/field-service/universal-resource-scheduling-for-field-service)  
- [Dynamics 365 Field Service](/dynamics365/field-service/)  
