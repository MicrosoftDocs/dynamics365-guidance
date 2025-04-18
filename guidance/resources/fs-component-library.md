---
title: Sample library for Field Service
description: Read about the library of sample components in GitHub that can help customers and partners create and deploy solutions with Field Service quickly and easily.
ms.date: 03/14/2025
ms.topic: conceptual
author: edupont04
ms.author: erdipple
ms.custom:
    - O25-FieldService
---

# Sample library for Dynamics 365 Field Service

***Applies to: Dynamics 365 Field Service***

This collection of sample code, components (solutions), and documents can help your Field Service projects with tasks such as customization, configuration, and operation of the platform. The library offers reusable and easy-to-follow resources for Field Service developers and users.  

> [!IMPORTANT]
> Sample codes, components (solutions), and documents created by the community aren't supported by Microsoft. If you have questions or issues with community tools, contact the tool's publisher.

## Areas

The following sections outline the content of the collection. Each section includes links to the corresponding articles and samples.

### Use Copilot to create sample data for Field Service

  You can use Copilot to generate sample data that you then import into a demonstration environment. In this way, you can show prospects the capabilities of Dynamics 365 Field Service.

  Learn more at [Use Copilot to create sample data for Field Service](fs-copilot-import-sample-data.md) and [Build a Copilot agent to create sample data in Dynamics 365](fs-use-copilot-studio-create-sample-data.md).

### Configure the schedule board in Field Service

- Add crew information to the resource cell template.

  A core element in this scenario is the flexibility to format the resource card shown on the schedule board. This sample shows how you can add crew membership information to the resource card. Learn more at [Add crew information to resource cells](fs-resource-cell-template.md). For an introduction to the area, go to [Customize the schedule board with a custom resource attribute](/dynamics365/field-service/extend-schedule-board-custom-resource-attribute).
- Customize the template for bookings.

  A core element in this scenario is the flexibility to format the booking slot shown on the schedule board. We show an example of how you can add a custom icon to the booking template based on the work order incident type. Learn more at [Customize the template for bookings](fs-booking-template.md). For an introduction to the area, go to [Edit schedule board booking templates](/dynamics365/field-service/booking-template).
- Field mapping for the schedule board settings

  Each field in the board settings maps to a particular column in the schedule board settings record for the relevant section. This information can be useful if you have to troubleshoot something about the schedule boards. Learn more at [Field mapping for schedule board settings in Dynamics 365 Field Service](fs-schedule-board-settings-field-mapping.md).  

- Custom control to manage schedule board settings

  If you use Universal Resource Scheduling for Dynamics 365 Field Service, you might want to create copies of bookings with minor tweaks or similar changes. Microsoft has published an unmanaged solution, the **Schedule board settings management** control, that can help you in such cases. Learn more at [Schedule board settings management control](fs-schedule-board-settings-management-control.md).  

### Develop the solution

- Solution component validation tool

  Solution management is the core design tenet of any Dynamics 365 implementation with Dataverse. You can manage solution structures for application lifecycles with the solution component validation tool.

  Learn more at [Manage solution structures for application lifecycles with the solution component validation tool](solution-component-validator.md).

### Test the solution

Automated end-to-end testing is an important part of Dynamics 365 implementation projects. Automation helps you test code quickly by replicating the business process flows so that you can deploy it faster with high confidence.

Here in the Dynamics 365 guidance hub, we provide articles based on samples and tools that we developed for implementation projects with Dynamics 365 Customer Service. But you can use the same tools and samples to test implementation projects with Dynamics 365 Field Service.

Learn more at [Set up test automation with Playwright](test-automation-setup.md).  

### Set up and configure

- Application lifecycle management

  Good practices and clever tools for application lifecycle management (ALM) can help you manage your solution with Dynamics 365 Field Service. For example, Universal Resource Scheduling for Dynamics 365 Field Service includes a schedule board. Through settings, you can define the layout and functions of schedule board tabs and the schedule board in general. Learn more at [Field mapping for schedule board settings in Dynamics 365 Field Service](fs-schedule-board-settings-field-mapping.md).

  You can also use Azure services to help you maintain the solution over time. Learn more at [Set up Azure Pipelines for deploying Field Service and other Dataverse solutions](fs-set-up-azure-pipelines-deploy-field-service-other-dataverse-solutions.md).



## Related information

- [Use the schedule board in Field Service](/dynamics365/field-service/work-with-schedule-board)  
- [Universal Resource Scheduling for Dynamics 365 Field Service overview](/dynamics365/field-service/universal-resource-scheduling-for-field-service)  
- [Dynamics 365 Field Service](/dynamics365/field-service/)  
