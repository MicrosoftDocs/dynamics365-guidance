---
title: Schedule service work overview
description: Learn about the benefits and process flow for the scheduling service requests business process within the service to cash process area.
author: nucruz
ms.author: nucruz
ms.topic: article
ms.date: 04/08/2024
---

# Schedule service work overview

***Applies to: Dynamics 365 Business Central, Dynamics 365 Field Service, Dynamics 365 Supply Chain Management***

This article describes the benefits and process flow of the *Schedule service requests* business process that is part of the *Create and process service work* process area in the *Service to cash* end to end business process. This process encompasses the steps to identify and book the correct resources to be scheduled to perform service work, which is the next step in the progress.

*Scheduling work orders* is the process of planning and organizing tasks or jobs in a systematic manner to ensure efficient and timely completion. It involves scheduling work orders within an agreed time window, considering factors such as available resources, priorities, dependencies, and skills required.

Typically, there are two different reasons to schedule a work order: new work needs to be scheduled have unscheduled work or previously scheduled work needs to be rescheduled.

Some reasons for rescheduling include:

- Customer requests a new date

- The previous service was delayed.

- Part required to complete the work is out of stock

- The required equipment is unavailable.

- Truck breaks down when traveling to a Service Location

- Work accident that causes resource unavailability

## Stakeholders

Many people across the organization should contribute to the decision-making process and design of *Scheduling Work Orders*. The following list provides examples of such stakeholders:

- **Customers**: One of the main stakeholders as they set the rules with their requirements, preferences, and availability.

- **Frontline worker**: As they perform the work specified in the work order. Their availability, skills, and workload need to be considered when scheduling the work order.

- **Dispatchers**: Responsible for coordinating and assigning work orders to frontline workers. They're responsible for scheduling tasks based on resource availability, skills, and other constraints based on the nature of the business.

- **Capacity managers**: Focus on managing overall operations, optimizing resource use, and maintaining service level agreements (SLAs).

- **IT**: Responsible for configuring and maintaining the scheduling system and providing technical support.

## Set schedule service process flow

The scheduling process plays a crucial role in industries like telecommunications, utilities, HVAC, and maintenance services, where frontline workers are deployed to perform on-site installations, repairs, or inspections relying on factors such as customer requests, frontline workers availability, skillsets, and location constraints.

Several tools are available that provide features like real-time visibility, resource tracking, automated scheduling, and route optimization. One of the most important tools is the schedule board that provides a visual representation of scheduled work orders and available resources, such as frontline workers, and allows dispatchers or managers to assign and manage work orders efficiently.

Automated scheduling also plays a significant role available through advanced algorithms and automation techniques to automatically generate optimal schedules not only based on predefined objectives and constraints, but also based on availability and proximity.

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media\service-to-cash-schedule-service-work-1.svg" alt-text="Diagram of the Schedule Service Work process, showing the connection between frontline workers and dispatchers." lightbox="media\service-to-cash-schedule-service-work-1.svg":::

The following steps are illustrated in the *schedule service work* process flow diagram includes the following steps:

1. *Create work order*

2. *Review the list of unscheduled work*

3. *Review the list of available resources that meet the work requirement and availability*

4. *Make scheduling decision applying allocation optimization as well as business needs*

5. *Rearrange or reallocate work to optimize the schedule*

6. *Booking one or more resource to work*

7. *Update remaining duration to exclude booked time*

8. *Notify resources that work has been allocated*

9. *New work allocated*

## Implementing schedule service for work orders

There are various configurations and operational processes that are part of setting up scheduling of work orders within in the Dynamics 365 Field Service application. The following table shows the configurations available, and the sequence recommended for setting up the configurations from top to bottom.

- Use the links on **Process step** for more information about the component.

- The **Process stage** column indicates which stage in the project the configuration or step should be completed.

- Modifiers may be used on each stage to further describe the timing within the phase to perform the step.

The following sections link to articles for Dynamics 365 Field Service. Dynamics 365 Business Central also includes built-in functionality for service management. Learn more at [Service management](/dynamics365/business-central/service-service).

### Basic scheduling

| Process step | Process stage | Application: Navigation and Entity |
|--------------|---------------|------------------------------------|
| [Booking directly from work order through Quick Book](/dynamics365/field-service/quick-scheduling) | Requirement; Configuration;  | Configuration Enable quick book: [Enable an entity for scheduling - Dynamics 365 Field Service](/dynamics365/field-service/schedule-new-entity) |
| [Booking directly from work order using book button](/dynamics365/field-service/universal-resource-scheduling-for-field-service#semi-automated-scheduling-with-the-schedule-assistant) | Fundamental  | Book from Work Order, Requirement: Passing booking parameters article? |

### Scheduling board

| Process step | Process stage | **Application: Navigation and Entity |
|--------------|---------------|--------------------------------------|
| [Configuring the Schedule Board](/dynamics365/field-service/schedule-board-tab-settings) | Design; Configuration; | Individual Schedule board tab settings Board settings -&gt; All Board settings |
| [Customize the schedule board](/dynamics365/field-service/extend-schedule-board-custom-resource-attribute) | Design; Configuration; | Individual Schedule board tab settings Board settings -&gt; All Board settings |
| [Manage booking alerts](/dynamics365/field-service/booking-alert) | Design; Configuration; | Open the schedule board, select booking alerts Icon, and select New booking alert. |

### Scheduling configuration

| Process step | Process stage | Application: Navigation and Entity |
|--------------|---------------|------------------------------------|
| [Enable an entity for scheduling](/dynamics365/field-service/schedule-new-entity) | Design; Configuration; | Individual Schedule board tab settings Board settings &gt; All Board settings |
| [Turn on auto geocoding](/dynamics365/field-service/turn-on-auto-geocoding) | Requirement; Design; Configuration; | Settings &gt; Administration &gt; Field Service Settings |
| [Set up booking statuses](/dynamics365/field-service/set-up-booking-statuses) | Design; Configuration; | Open the schedule board, select booking alerts Icon, and select New booking alert. |
| [Include appointments in scheduling](/dynamics365/field-service/appointment-scheduling) | Design; Configuration; | Resource Scheduling &gt; Settings &gt; Administration &gt; Scheduling Parameters   |
| [Fulfillment preferences](/dynamics365/field-service/set-up-time-groups) | Design; Configuration; | Universal Resource Scheduling &gt; Scheduling &gt; Fulfillment Preferences |
| [Scheduling parameters (Settings)](/dynamics365/field-service/scheduling-parameters-settings) | Design; Configuration; | Resources &gt; Administration &gt; Scheduling Parameters &gt; Resource Scheduling |

### Automated schedule optimization

| Process step | Process stage | Application: Navigation and Entity |
|--------------|---------------|------------------------------------|
| [Deployment](/dynamics365/field-service/rso-deployment) | Environment setup; | Power Platform Admin Center |
| [Configuration](/dynamics365/field-service/rso-configuration) | Design; Configuration; | Resource Scheduling Optimization &gt; Administration&gt; Scheduling Parameters |

## Next steps

After you have completed the setup and configuration for the *schedule service work* process in Dynamics 365, consider the following steps and actions to take. (Links are added, when the articles are ready.)

1. [Perform Service Work](service-to-cash-perform-service-work.md)

2. *Review and close service requests*

## Related resources

You can use the following resources to learn more about the *Schedule work orders* process in Dynamics 365.

- [Field Service Documentations](/dynamics365/field-service/rso-overview)

- [Learn Field Service scheduling capabilities](/training/modules/describe-scheduling-process/)

- [Service management - Business Central](/dynamics365/business-central/service-service)

<!-- ## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Customer services, Engineering, IT, Marketing, Merchandising, Operations, Production, Project Management, Service operations, Transportation, Warehouse

*Products:* Dynamics 365 Field Service, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal authors:

- [Nuno Cruz](https://www.linkedin.com/in/nunomrcruz/) \| FastTrack Solution Architect

- Jason du Plessis \| FastTrack Solution Architect