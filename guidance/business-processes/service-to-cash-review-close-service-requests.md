---
title: Review and close service requests
description: Learn about how to set up, configure, and design the Review and close service requests business process, including a business process flow.
author: nucruz
ms.author: nucruz
ms.topic: article
ms.date: 05/14/2024
---

# The business process Review and close service requests within the Service to deliver end-to-end scenario

***Applies to: Dynamics 365 Field Service, Dynamics 365 Guides, Dynamics 365 Project Operations, Dynamics 365 Remote Assist, Dynamics 365 Supply Chain Management***

In this article, we explain how to set up, configure, and design the *Review and close service requests* business process in Dynamics 365 Field Service. Service supervisors manage this process. It starts when a frontline worker completes the service work, and the bookings are closed. This usually marks the end of the lifecycle for a given service request in the *Create and process service requests* process area. After this process, service requests move to the *Invoice customers* business process area.

> [!IMPORTANT]
> The *service to cash* end-to-end scenario has a new name in the February 2025 version of the business process catalog. The articles in Microsoft Learn are not yet fully updated based on this version. Learn more at [What's new or changed in the business process catalog February 2025](about-whats-new-2025-february.md).

This business process covers the following list of tasks:

- Review the completed service tasks, products, labor, notes, and resolution comments associated with the work order. This ensures that they're accurate, appropriate for the work performed, and meet the customers' expectations.

- Capture customer feedback and satisfaction levels. For example, use surveys, ratings, or comments, and resolving any issues or complaints that might arise.

- Create and attach any relevant documents or reports to the work order, such as service reports, inspection certificates, compliance forms, or warranty information.

- Analyze work order performance and outcomes and identify areas for improvement or best practices. Use key metrics and indicators, such as service duration, cost, profitability, quality, or customer satisfaction.

- Update the status of the work order to indicate that it's ready for closure, or invoicing, depending on the organization's workflow and policies.

For many organizations and industries, the benefits of this process include the following list:

- **Accountability**: Closing work orders ensure that tasks are completed as intended and that responsible individuals or teams are held accountable for their work.

- **Regulatory compliance**: In regulated industries, such as healthcare and utilities, proper documentation and closure of work orders are necessary to demonstrate compliance with industry standards and regulations, such as medical equipment certification.

- **Revenue and cost control**: Proper closure allows organizations to track revenue and costs associated with labor, materials, and equipment, facilitating better financial management.

- **Customer Satisfaction**: Closing work orders promptly and effectively contributes to meeting customer expectations and delivering quality services.

## Review and close work orders process flow

The following diagram illustrates the business process.

:::image type="content" source="media/service-to-cash-review-close-service-requests-business-process-diagram.svg" alt-text="Diagram showing the Review and close service requests business process for frontline workers and field service supervisors." lightbox="media/service-to-cash-review-close-service-requests-business-process-diagram.svg":::

The process flow diagram includes the following steps.

1. [Service work and bookings](service-to-cash-schedule-service-work.md) completed (a prerequisite business process before you start).

2. Start

3. Work order status set to completed in the [Dynamics 365 Field Service mobile app](/dynamics365/field-service/mobile-power-app-get-started).

4. Review the work order in the Dynamics 365 Field Service app.

5. Adjustments

    1. If adjustments are needed, adjust work order in Dynamics 365 Field Service, go to step 6.

    2. If no adjustments are needed, go to step 6.

6. Approval

    1. If approval is needed, approve work order in Dynamics 365 Field Service, go to step 7.

    2. If approval isn't needed, go to step 7.

7. Post work order in Dynamics 365 Field Service.

8. End

## Implementing the business process

The following section shows the configurations available, and the sequence recommended for setting up the configurations related to the *Review and close service requests* business process. Learn more about the terms used in the table at [Business processes, steps, and how to find things](/dynamics365/guidance/business-processes/about-steps-navigation).

| Process step | Process stage | Application: Navigation and Entity |
|--------------|---------------|------------------------------------|
| [Create work order Sub-status values](/dynamics365/field-service/work-order-status-booking-status) | Configuration | **FS:** Work Orders &gt; Work Order &gt; Sub status |
| [Booking Status](/dynamics365/field-service/work-order-status-booking-status#create-follow-up-work-order-for-a-completed-booking) | Configuration | **FS:** Resources &gt; Booking Settings &gt; Booking Statuses |
| [Time Entries](https://microsoft.sharepoint.com/teams/BusinessApplicationsContentHub/Shared%20Documents/Business%20Process%20Guide/Service%20to%20cash/L3%20Files%20(Processes)/Review%20and%20close%20service%20requests%20-%20Nuno/automatically) | Configuration | **FS**: Settings &gt; Field Service Settings &gt; Time Entry Generation Strategy |
| [Work Order Resolutions](/dynamics365/field-service/work-order-resolutions#create-resolutions) | Configuration | **FS**: Settings &gt; Resolutions &gt; + New |
| [Create billing invoice](/dynamics365/field-service/configure-default-settings#work-order--booking-settings) | Configuration | **FS:** Settings &gt; Field Service Settings &gt; Work Order / Booking &gt; Work Order Invoice Creation |
| [Work Order Completion Survey](/dynamics365/field-service/work-order-surveys) | Configuration | See documentation |

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *Review and close service requests* processes, you can use the following resources and steps to learn more. (Links are added, when the articles are ready.)

1. *Define service policies*

2. *Create service requests*

3. [Schedule service work](service-to-cash-schedule-service-work.md)

4. [Perform service work](service-to-cash-perform-service-work.md)

5. *Review and close service requests* (The article you're currently reading)

## Related information

You can use the following resources to learn more about the reviewing and close work orders process in Dynamics 365.

- [Manage work orders in Dynamics 365 Field Service - Training](/training/paths/manage-work-orders)

- [Use the Field Service (Dynamics 365) mobile app to complete work orders](/dynamics365/field-service/mobile-power-app-overview)

- [Track time expenditure with time entries](/dynamics365/field-service/field-service-time-entry)

- [Dynamics 365 Field Service documentation](/dynamics365/field-service/)

- [Exam MB-240: Microsoft Dynamics 365 Field Service Functional Consultant](/certifications/exams/mb-240)

- [Describe use cases for Dynamics 365 Field Service - Training](/training/modules/explore-dynamics-365-field-service/2-describe-use-cases-dynamics-365-field-service)

- [Complete work orders in the mobile app - Dynamics 365 Field Service](/dynamics365/field-service/get-work-done-mobile-app?tabs=vCurrent)  

- [Field Service technician service reporting - Dynamics 365 Field Service](/dynamics365/field-service/mobile-powerapp-reporting)

- [Booking Status Processes](/dynamics365/field-service/work-order-status-booking-status#booking-status-processes)

<!-- ## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Customer services, Engineering, IT, Merchandising, Operations, Production, Project Management, Retail store operations, Sales, Service operations, Transportation, Warehouse

*Products:* Dynamics 365 Field Service, Dynamics 365 Guides, Dynamics 365 Project Operations, Dynamics 365 Remote Assist, Dynamics 365 Supply Chain Management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Nuno Cruz](https://www.linkedin.com/in/nunomrcruz/) \| FastTrack Solution Architect

Other contributors:

- [Jason du Plessis](https://www.linkedin.com/in/jason-du-plessis-a512171) \| FastTrack Solution Architect

- [Dean Hardy](https://www.linkedin.com/in/deanahardy) \| FastTrack Solution Architect  
