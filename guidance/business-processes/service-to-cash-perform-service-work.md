---
title: Setup and considerations for performing service work
description: Learn about how to set up and configure for performing service work in Dynamics 365 apps, including types of stakeholders and a business process map.
author: jasondpms
ms.author: jaduples
ms.topic: article
ms.date: 04/09/2024
---

# Perform service work

***Applies to: Dynamics 365 Field Service, Dynamics 365 Guides, Dynamics 365 Project Operations, Dynamics 365 Remote Assist, Dynamics 365 Supply Chain Management***

This article describes the setup, configuration, and design considerations for performing service work in Dynamics 365. Frontline workers that work for an organization that provides a service to customers or clients. Performing service work is typically the process where frontline workers perform the tasks specified in the work order assigned, using various tools and equipment.

The work of a frontline worker involves, for example,  installing, maintaining, and repairing various types of systems in different locations. The frontline worker also communicates with stakeholders and updates them on the progress and status of the service work.

This work is a crucial part of ensuring customer satisfaction and loyalty. By following this process, the frontline worker can deliver reliable services that meet or exceed customer expectations and generate revenue and profit for the business. Following this process helps to increase the efficiency of a frontline worker. Task-based guidance provides a clear and concise way of doing things. It can help to reduce errors and to speed up the work.

## Perform service work stakeholders

Stakeholders involved in performing service work include, but isn't limited to, the following list:

- Frontline worker who performs the actual work on-site. They may be employees of the service provider or contracted technicians. They have the expertise and skills to diagnose and fix problems, install, or maintain equipment, ensure work is carried out efficiently and safely, and report to the service manager. A field service frontline worker typically reports to a field service manager by documenting the tasks completed, the time taken, any issues encountered, and the resolutions provided.

- Service manager or supervisor who oversees the performance and productivity of the field service team. They may also handle approval processes and address any issues that arise during the execution process.

- Remote experts are subject matter experts who possess specialized knowledge or skills relevant to the field service work being performed. They may be in a different geographical location and can provide real-time assistance through video calls or augmented reality applications.

- Parts and inventory manager who ensures the availability of necessary parts in cases where repairs or maintenance require replacements. They manage stock levels, and coordinate with frontline workers to ensure they have the required resources to complete the work orders.

- Customer who requests the service and provides feedback on the quality of the work.

## Perform service work process flow

The following diagram illustrates the business process. [!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media\service-to-cash-perform-service-work-1.svg" alt-text="Diagram of the Perform service work business process area and its relationship with other business processes." lightbox="media\service-to-cash-perform-service-work-1.svg":::

The process flow diagram includes the following steps.

1. *Dispatch the Work Order* (a prerequisite business process before you start).

2. Start.

3. Review of the assigned job, prework activities and travel to location.

4. Start the work following guidance.

5. Part Required.

    1. If *Parts are Required*, *Approve and manage Purchase Order*.

    2. If not, go to step 6.

6. *Perform Installation/ Maintenance/ Inspection*.

7. *Assistance*.

    1. If *Assistance* required, request *Remote Assistance help*.

    2. If not, go to step 8.

8. *Complete the work/ scan pictures/ videos/ asset barcodes*.

9. *Update the Booking*.

10. *Sign off*.

11. *Complete Booking* / *Time Tracking*.

12. End.

## Terminology and concepts

Various terminology and concepts are used throughout this article to describe the business process. For definitions and explanations of key terms and concepts, see [Glossary of terms in Dynamics 365 business processes](../business-processes/glossary.md).

### Implementing perform service work

The following tables and sections describe the various configurations and operational processes that are part of implementing the process of *Perform service work* in Dynamics 365 applications.

> [!TIP]
> A variety of terminology and concepts are used throughout this article to describe the business process. For definitions and explanations of key terms and concepts, see [Glossary of terms in Dynamics 365 business processes](../business-processes/glossary.md).

The following sections show the configurations available, and the sequence recommended for setting up the configurations from top to bottom. Learn more about the terms used in the table at [Business processes, steps, and how to find things](../business-processes/about-steps-navigation.md).

## Perform service work on mobile

Frontline workers are people who are primarily scheduled for onsite jobs. Follow these steps if you want frontline workers to use the Dynamics 365 Field Service mobile app. With this app, they can view and update work orders, customer assets, accounts, and more on the go.

| Process step | Process stage | Process modifiers | App, navigation, and entity |
|--------------|---------------|-------------------|-----------------------------|
| [Read about best practices and limitations for using the offline profile](/dynamics365/field-service/mobile-power-app-system-offline#best-practices-for-using-the-offline-profile) | Strategize; Base; Configuration | Early |  |
| [Create a territory](/dynamics365/field-service/set-up-territories#create-a-territory) | Initialize; Fundamental; Configuration | Early | FS: Settings &gt; General section &gt; Territories |
| [Specify characteristics](/dynamics365/field-service/set-up-characteristics) | Initialize; Fundamental; Configuration | Early | RS: Settings &gt; Resource section &gt; Skills |
| [Set up booking statuses](/dynamics365/field-service/set-up-booking-statuses) | Initialize; Optional; Configuration | Early | RS: Settings &gt; Scheduling section &gt; Booking Statuses |
| [Track time expenditure with time entries - Configuration considerations](/dynamics365/field-service/field-service-time-entry#configuration-considerations) | Initialize; Optional; Configuration | Early | FS: Settings &gt; General section &gt; Field Service Settings &gt; Time Entry |
| [Configure travel charges](/dynamics365/field-service/travel-charges) | Initialize; Optional; Configuration | Early | FS: Settings &gt; General section &gt; Field Service Settings &gt; Work Order / Booking |
| [Set up frontline workers](/dynamics365/field-service/frontline-worker-set-up#set-up-frontline-workers) | Initialize; Fundamental; Configuration | Continuous | FS: Service &gt; My Work section &gt; Get Started |
| [Send frontline workers a download link for the mobile app](/dynamics365/field-service/frontline-worker-set-up-email-approval) | Initialize; Fundamental; Configuration | Early |  |
| [Install and set up the mobile app](/dynamics365/field-service/mobile-power-app-get-started#assign-mobile-app-users-appropriate-security-roles) | Initialize; Base; Configuration | Early |  |
| [Set up the mobile offline profile](/dynamics365/field-service/mobile-power-app-system-offline-setup) | Initialize; Fundamental; Configuration | Early |  |
| [Enable location and map settings](/dynamics365/field-service/field-service-maps-address-locations) | Develop; Fundamental; Configuration | Early | PPAC: Environment &gt; Settings &gt; Product &gt; Features |
| [Enable Copilot for Mobile](/dynamics365/field-service/work-order-update) | Initialize; Fundamental; Configuration | Early | FSM: Setting &gt; Features |
| [Enable Booking Map for Field Service Mobile](/dynamics365/field-service/configure-default-settings#work-order--booking-settings) | Initialize; Fundamental; Configuration | Early | FS: Settings &gt; General section &gt; Field Service Settings &gt; Work Order / Booking |
| [Set up knowledge articles](/dynamics365/field-service/field-service-knowledge-management) | Initialize; Fundamental; Configuration | Continuous | FSM: Setting &gt; Knowledge management section &gt; Knowledge articles |
| [Add a barcode field to the form](/dynamics365/field-service/mobile-power-app-system-barcode-scanning#add-a-barcode-field-to-the-form) | Initialize; Optional; Configuration | Early |  |
| [Enable push notifications](/dynamics365/field-service/mobile-power-app-push-notifications) | Initialize; Fundamental; Configuration | Early |  |
| [Location auditing for the mobile app](/dynamics365/field-service/mobile-powerapp-location-auditing?tabs=iOS) | Develop; Fundamental; Configuration | Gold |  |
| [Geofencing for the Field Service mobile app](/dynamics365/field-service/mobile-powerapp-geofence) | Develop; Fundamental; Configuration | Early |  |
| [Configure Teams App for frontline workers](/dynamics365/field-service/flw-teams-worker) | Initialize;</br>Fundamental; Configuration | Early |  |

## Contractor licenses

Choose this option for situations where you need to include a contractor or vendor in your Field Service delivery operations.

| Process step | Process stage | Process modifiers | App, navigation, and entity |
|--------------|---------------|-------------------|-----------------------------|
| [Manage B2B collaboration users in Microsoft Entra](/dynamics365/field-service/users-licenses-permissions#b2b-collaboration-users) | Initialize; Base; Configuration | Early | |
| [Assign Field Service Contractor Licenses](/dynamics365/field-service/users-licenses-permissions#assign-licenses) | Initialize; Base; Configuration | Early | |

## Work with inspections

Field Service inspections are digital forms that frontline workers use to quickly and easily answer a list of questions as part of a work order. The list of questions can include safety protocols, pass-and-fail tests for a customer asset, an interview with a customer, or other audits and assessments. Follow these steps if you want frontline workers to work with inspections.

| Process step | Process stage | Process modifiers | App, navigation, and entity |
|--------------|---------------|-------------------|-----------------------------|
| [Turn the analytics for inspections on or off](/dynamics365/field-service/configure-default-settings#inspection-settings) | Prepare; Fundamental; Configuration | Early | FS: Settings &gt; General section &gt; Field Service Settings &gt; Inspection |
| [Create and view inspections](/dynamics365/field-service/inspections) | Develop; Fundamental; Configuration | Continuous | FS: Settings &gt; Work Order section &gt; Inspection Templates |
| [Configure advanced options for inspections](/dynamics365/field-service/inspections-advanced) | Develop; Fundamental; Configuration | Continuous | FS: Settings &gt; Work Order section &gt; Inspection Templates |
| [Enable inspections on customer assets without a work order](/dynamics365/field-service/inspections-customer-assets) | Prepare; Optional; Configuration | Early | |

## Work with service reports

Frontline workers often create service reports summarizing work done during a customer visit. These reports can carry details such as tasks completed, and products or parts used during the service. Service reports must often be delivered to the customer in the form of a PDF. Follow these steps if you want frontline workers to work with Service Reports.

| Process step | Process stage | Process modifiers | App, navigation, and entity |
|--------------|---------------|-------------------|-----------------------------|
| [Import the reporting solution](/dynamics365/field-service/mobile-powerapp-reporting#import-the-reporting-solution) | Develop; Fundamental; Configuration | Early | |
| [Create your custom report](/dynamics365/field-service/mobile-powerapp-reporting#create-your-custom-report) | Develop; Fundamental; Configuration | Early | |

## The perform service work phases

The Perform service work business process typically consists of four main steps: overview, prework activities, execution, completion.

### Work order overview

In one example, a frontline worker, after being notified on their mobile device, will need a clear overview of the service work assigned to them. This overview includes information such as priority and status to be able to accept or reject the work based on their availability.

Work order bookings are typically displayed in a list or map view. The frontline worker can filter and sort by different criteria, such as due date, distance, or type. After filtering and sorting, they can decide to accept or reject work orders providing a reason for rejection. The company can then assign the work order to another frontline worker or reschedule it with the customer.

Work order overviews are possible by:

- Using the Work Order List ([Work Order List)](/dynamics365/field-service/work-order-experience#work-order-list))

- Using the calendar view in the mobile app: ([Booking maps](/dynamics365/field-service/mobile-powerapp-booking-maps))

- In the Team App ([Teams app)](/dynamics365/field-service/flw-teams-worker))

- Receiving push notification ([Enable push notifications)](/dynamics365/field-service/mobile-power-app-push-notifications))

### Prework activities

During this phase, the frontline worker can utilize their mobile device to familiarize themselves with the job's scope, task, and service requirements. This allows the frontline worker to make the necessary preparations for the visit to the customer's location. This preparation time is a critical component to ensure that the frontline worker has all the tools, parts, and other resources needed to successfully complete the work. It also allows the frontline worker to understand any specific instructions or deadlines that the customer may require.

More customer details can be found in the work order such as the customers' name, contact information, and the service location. It can also have the steps required to perform specific tasks, links to knowledge articles and any guides that might help the frontline worker complete the job in a timely manner.

All this preparation work pays off when the frontline worker can make one visit to address the issue, ensuring that it's resolved. While this can save time and money, more importantly it shows the customer that the frontline worker fully understood the issue and resolved it in a timely manner. This increases customer satisfaction and wins customer loyalty.

### Execution

In this step, the frontline worker first locates the customer site and plans the route efficiently to arrive at the customer site on time. The frontline worker might communicate, using geo location enabled on the mobile device, to the customer and the service manager that they are on their way, and might also edit the status of the booking to show when they're traveling.

Once on site the frontline worker carries out the tasks as specified in the work order. This may involve repairs, maintenance, installations, or any other service activity. The frontline worker may use various tools and equipment to complete the service work.

Frontline workers equipped with mobile devices, like tablets or smartphones, can scan images, videos, and asset barcodes. Frontline workers have the option to use guides during the performance of service tasks. This allows them to reference structured instructions and best practices, ensuring that each task is carried out with precision and care. Additionally, they can update the booking statuses, allowing managers to effectively track the advancement of work order requirements.

Here's a list of typical tasks:

- Install a new product bought by a customer at the location.

- Repair a customer asset like changing a part that is broken.

- Regular maintenance work. This can be done by following a checklist to verify the condition, quality, or performance of a system. Inspections help to identify any issues, defects, or risks that may affect the safety, functionality, or reliability of the system or component. This can be documented using forms, reports, or other methods.

The service frontline worker may encounter unexpected issues or changes during the execution, such as other problems, missing parts, or customer requests. In such cases, the service frontline worker documents the issues or changes and obtains approval from the customer or the service manager before proceeding. The work order can also be canceled and removed from the list of assigned or pending orders of the frontline worker. Using their mobile device offline, the frontline worker can synchronize the work order data with the cloud and receive new assignments or notifications.

If a subject matter expert is needed, by using a device, such as a mobile phone, a frontline worker can contact experts to collaborate more efficiently by sharing their real-time view, working together and solving the problem faster. This step can save time because it allows the frontline worker to access the expertise of remote specialists without having to travel or wait for them to arrive.

### Completion and reporting

Once the service work is concluded, the customer is informed. The customer may provide their feedback and sign out on the completion of the service.

The frontline worker updates the work order with information such as the start and end time of each task, tracks time spent on traveling, the actions performed, the parts used or replaced, the test results, the recommendations for future maintenance and improvement, and the customer feedback and signature. One of the ways to update the work order is to use the field service mobile app on their mobile phone or tablet, ideally with offline access to synchronize the data later in case there is no internet connection.

This ensures that the field service manager is kept informed of the frontline worker's activities, a summary of the key aspects of the service work and provides evidence of completion and quality.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *Perform service work* processes, you can use the following resources and steps to learn more.

1. *Define service policies*

2. *Create service requests*

3. [Schedule service work](service-to-cash-schedule-service-work.md)

4. *Perform service work* (The article you're currently reading)

5. *Review and close service requests*

## Related resources

You can use the following resources to learn more about the *Perform service work* process in Dynamics 365.

- [Use the Field Service (Dynamics 365) mobile app to complete work orders](/dynamics365/field-service/mobile-power-app-overview)

- Work with checklists like [Add inspections to work orders (contains video)](/dynamics365/field-service/inspections) or [Maintenance checklists](/dynamics365/supply-chain/asset-management/work-orders/maintenance-checklists)

- Request Remote Assistance 
    - [Collaborate in mixed reality with Field Service, Dynamics 365 Remote Assist, and HoloLens (contains video)](/dynamics365/field-service/remote-assist-hololens)
    - [Integrate Field Service with Dynamics 365 Guides](/dynamics365/field-service/mixed-reality-guides-integration)

- [Track time expenditure with time entries (contains video)](/dynamics365/field-service/field-service-time-entry)

- [Track a technician on the Field Service portal](/dynamics365/field-service/customer-portal-technician-tracking)

- [Dynamics 365 Field Service documentation](/dynamics365/field-service/)

- [Exam MB-240: Microsoft Dynamics 365 Field Service Functional Consultant](/certifications/exams/mb-240)

- [Dynamics 365 Guides](/dynamics365/mixed-reality/guides/overview)

- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/ra-overview)

- [Solve problems in real time with Dynamics 365 Remote Assist](/training/paths/solve-problems-remote-assist/)

- [Describe use cases for Dynamics 365 Field Service](/training/modules/explore-dynamics-365-field-service/2-describe-use-cases-dynamics-365-field-service)

- [Complete work orders in the mobile app](/dynamics365/field-service/get-work-done-mobile-app?tabs=vCurrent)

- [Field Service technician service reporting (contains video)](/dynamics365/field-service/mobile-powerapp-reporting)

- [Booking Status Processes](/dynamics365/field-service/work-order-status-booking-status#booking-status-processes)

- [Access related applications](/dynamics365/field-service/access-related-apps-mobile-app)

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- Sabrina Di Bartolomeo ([Sabrina Di Bartolomeo \| LinkedIn](https://www.linkedin.com/in/sabrina-di-bartolomeo-025463/)) \| FastTrack Solution Architect

Other contributors:

- Jason du Plessis (<https://www.linkedin.com/in/jason-du-plessis-a512171>) \| FastTrack Solution Architect

<!-- ## Tags

*Industries:* All

*Stakeholders:* Functional consultant, Business analyst, Operational Lead

*Products: Dynamics 365 Field Service, Dynamics 365 Guides, Dynamics 365 Project Operations, Dynamics 365 Remote Assist, Dynamics 365 Supply Chain Management* -->