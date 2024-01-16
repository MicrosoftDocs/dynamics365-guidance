---
title: Create work orders overview
description: Learn how you can use Dynamics 365 products to support the organization's business processes to create work orders.
ms.date: 12/01/2023
ms.topic: conceptual
author: edupont04
ms.author: dehardy
---

# Create work orders overview

***Applies to: Dynamics 365 Business Central, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Supply Chain Management***

This article describes the benefits and process flow of the *Create work orders* business process area that is part of the *Service to cash* end-to-end process. This area covers the business processes that lead to the creation of work orders. It also covers the business processes that determine the content of the work order to ensure that it has the necessary information to efficiently drive the downstream scheduling and service delivery processes.

Work orders are the primary object for service management, such as in Dynamics 365 Field Service. It's important to identify and document the business processes that lead to their creation, and the population of their content, in the first stages of your implementation project. This approach helps you ensure that your unique business requirements can be met through standard capabilities or by building customizations.

The following list shows a few examples of business processes that lead to the creation of work orders:

- **Customer requests**

    In some scenarios, a customer contacts your customer service organization, and the information is transferred from a case to a work order because the issue can't be resolved remotely. In other scenarios, the customer contacts the service department, either directly or through a customer portal, to request service in a reactive manner.

- **Ongoing maintenance**

    These scenarios can arise from service agreements, or contracts, with customers to supply specific ongoing services over the course of the contract period. For these scenarios, work orders can be automatically generated on a repeating basis as they are needed to complete the preventative maintenance schedule.

- **Smart devices**

    More and more items that require servicing are connected to the internet and can supply alerts that trigger the need for service and, therefore, the creation of a work order.

- **Integrations**

    Sometimes, the service application that is being implemented isn't used exclusively throughout your organization, or it isn't considered the "system of record" for work orders. In these scenarios, you might want to create integrations with other systems that are responsible for creating work orders and updating the content between them.

- **Manual**

    In many organizations, there are numerous scenarios where an application user must manually create a work order record. For example, a user responds to a phone call from a customer, or a frontline worker at the service location identifies other services that must be supplied.

In addition to documenting work order creation scenarios and processes, it's important to identify the required work order content during the creation process. Work orders that include all the necessary information can be processed through the service lifecycle as efficiently as possible.

Although the definition of *required content* varies by organization, industry, service type, or creation method, there are some general categories that apply to many scenarios. The following list describes some examples:

- **Identifying the service customer**

    In some cases, the customer is your own organization. However, most of the time, the customer is an external entity and has unique attributes that must be considered when you deliver service to it. When you identify the service customer on the work order, those unique customer attributes can be accommodated.

- **Determining the service location**

    During field service, or service in varied locations, it's important to identify the specific location where the service is provided. Usually, you register the location by specifying a postal address that can be transformed into latitude and longitude coordinates (a geocode). The geocode can then be used to calculate the estimated travel time between service locations. It can also be used to help select the right resources for scheduling the work order.

- **Defining the estimated scope of work**

    The scope of a work order usually includes content that defines the type of service work that is expected to be performed. This information, in turn, helps determine the amount of time to allocate, the resources that are required to carry out the work, and the parts and materials that might be needed. An accurate estimate of the scope of work during work order creation significantly increases the likelihood that the work will be completed within the shortest time and with the fewest service visits. It also helps make the most efficient use of your company's resources.

- **Establishing pricing and entitlements**

    In some scenarios, it might be necessary to modify the price of the parts and labor that are used in the work order. In other scenarios, it might be necessary to ensure that the service work accounts for specific entitlements, or service level agreements (SLAs), based on the service customer, the type of work that is being performed, or the details of a service contract. Correct documentation of these items during work order creation helps ensure that the work is scheduled and completed as expected. Therefore, it also helps reduce the need for later modifications.

- **Defining scheduling parameters**

    Particularly in field service scenarios where frontline workers travel to multiple service locations per day, and time commitments are made to customers, it's important to ensure that specific scheduling parameters are well defined in the work order during the creation process. Well-defined parameters help your organization achieve maximum optimization of service operations and also meet customer expectations.

## Stakeholders

The documentation of work order creation methods and required content is foundational to the downstream processes of scheduling and service delivery. Therefore, it's important to include the necessary stakeholders when you define these processes for your implementation project. Many people across the organization should contribute to the decision-making process and design of the *Create work orders* business process area. The following list provides examples of such stakeholders: 

- **Operations stakeholders** – Example: Chief Operating Officer (COO)
- **Field service stakeholders** – Examples: Service managers, field supervisors, dispatchers, and frontline workers
- **Customer service stakeholders** – Example: Call center manager
- **Finance stakeholder** – Examples: Chief Financial Officer (CFO) and controller

## Create work orders process flow 

The following diagram illustrates the *Create work orders* business process area. [!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/service-to-cash-graphics-create-work-orders-flow.svg" alt-text="Flow diagram for the business process area, which is explained in the paragraphs after the image." lightbox="media/service-to-cash-graphics-create-work-orders-flow.svg":::

1. Start
2. A parallel branch from 1. Start includes the *Service to Cash* end-to-end process.

    1. *Create and manage accounts for servicing* business process area
    2. *Create and manage assets* business process area
    3. *Create and manage service resources* business process area
    4. *Establish servicing policies and procedures* business process area
    5. *Create work orders* business process area

        1. *Initiate work order creation* business process
        2. *Establish service customer* business process
        3. *Establish service location* parameters business process
        4. *Define expected scope of work* business process
        5. *Establish pricing and entitlements* business process
        6. *Define scheduling parameters* business process

3. A parallel branch from 1. Start includes the *Case to resolution* end-to-end process.

    1. *Convert to work order* business process

        1. Connects to the 2.e. *Create work orders* business process area

4. A parallel branch from 1. Start includes the *Project to profit* end-to-end business process.

    1. *Deliver project work* business process area
    2. Connects to the 2.e. *Create work orders* business process area

5. A parallel branch from 1. Start includes the *Acquire to dispose* end-to-end business process.

    1. *Acquire assets* business process area
    2. Connects to the 2.e.iv. *Define expected scope of work* business process

6. End

## Create work orders benefits

There are many benefits from the *Create work order* process area. The following sections describe key benefits of the *Create work order* process in Dynamics 365 solutions.

### Centralized work information

A work order includes all the key information that is required to carry out a service job. It provides a single centralized record of the work that service managers can track and use later for reporting and analytical purposes.

### Scheduling efficiencies

By ensuring that work orders include the necessary information, you allow for optimization of the service schedule. This optimization helps dispatchers select the best resources and time slots to perform the service work. It also helps minimize the need for other service trips.

### Quality of service delivery

When accurate and complete data is captured about the work that must be performed, field service resources can be scheduled to arrive at the right location and with the right parts, supporting guides, and steps that are required to complete the work that was promised to the customer.

## Next steps

If you want to implement Dynamics 365 solutions to help with your *Create work order* processes, you can use the following resources and steps to learn more. Links are added when articles become available.

1. *Create work orders* (the article that you're currently reading)
2. *Schedule work orders*
3. *Perform service work*
4. *Review and close work orders*
5. *Analyze service operations*

## Related resources

You can use the following resources to learn more about the *Create work orders* process in Dynamics 365.

- [Create a work order - Dynamics 365 Field service](/dynamics365/field-service/create-work-order)
- [Create and define work orders - Training](/training/modules/implement-work-order-management-agreements-inventory-and-purchasing/2-creating-and-defining-work-orders)
- [Exam MB-240: Microsoft Dynamics 365 Field Service Functional Consultant](/certifications/exams/mb-240)
- [Service Management - Dynamics 365 Supply Chain Management](/dynamics365/supply-chain/service-management/service-management-home-page)
- [Service Management - Dynamics 365 Business Central](/dynamics365/business-central/service-service)
- [Implementation strategy](../implementation-guide/implementation-strategy.md)
- [Process-focused solution](../implementation-guide/process-focused-solution.md)
- Find definitions of terminology that is used in content for *Create work orders* process area in the [Glossary of terms in Dynamics 365 business processes](/dynamics365/guidance/business-processes/glossary) article. For example, this glossary includes the following terms:

    - [Work order](glossary.md#work-order)
    - [Service customer](glossary.md#service-customer)
    - [Service location](glossary.md#service-location)
    - [Service resource](glossary.md#service-resource)
    - [Scheduling parameters](glossary.md#scheduling-parameters)
    - [Assets](glossary.md#asset)

## Contributors

*This article is* *maintained by Microsoft. It was originally written by the following contributors.*

Principal authors:

- [Jason du Plessis](https://www.linkedin.com/in/jason-du-plessis-a512171) | FastTrack Solution Architect
- [Dean Hardy](https://www.linkedin.com/in/deanahardy) | FastTrack Solution Architect

## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Customer services, Engineering, IT (Information Technology), Operations, Production, Project Management, Service operations, Transportation, Warehouse

*Products:* Dynamics 365 Business Central, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Guides, Dynamics 365 Project Operations, Dynamics 365 Remote Assist, Dynamics 365 Supply Chain Management
