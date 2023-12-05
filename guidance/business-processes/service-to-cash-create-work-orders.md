---
title: Create work orders overview
description: Learn how you can use Dynamics 365 products to support the organization's business processes to create work orders.
ms.date: 12/01/2023
ms.topic: conceptual
author: edupont04
ms.author: dehardy
---

# Create work orders overview

***Applies to: Dynamkcis 365 Business Central, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Supply Chain Management***

This article describes the benefits and process flow of the *Create work orders* business process area that is part of the *Service to cash* end-to-end process. This area covers both the business processes that lead to the creation of work orders, and those that determine the content of the work order to ensure it has the necessary information to efficiently drive the downstream scheduling and service delivery processes.

Work orders are the primary object for service management, such as in Dynamics 365 Field Service. It's important to identify and document the business processes that lead to their creation, and the population of their content, in the first stages of your implementation project. This approach helps you make sure your unique business requirements can be met with standard capabilities, or by building customizations.

The following list shows a few examples of business processes that lead to the creation of work orders:

- **Customer requests**  

  In scenarios where a customer contacts your customer service organization and the information is transferred from a case into a work order because the issue can't be resolved remotely. Other scenarios include contact from the customer directly, or through a customer portal, to the service department with a request for service in a reactive manner.

- **Ongoing maintenance**  

  These scenarios can arise from service agreements, or contracts, with customers to supply specific ongoing services over the course of the contract period. For such scenarios, work orders can be generated automatically on a repeating frequency as needed to complete the preventative maintenance schedule.

- **Smart devices**  

  More and more items that require servicing are connected to the internet and can supply alerts that trigger the need for service, and therefore the creation of a work order.

- **Integrations**  

  sometimes the service application being implemented is not be used exclusively throughout your organization or it's not considered the 'system of record' for work orders. In these scenarios, you might want to create integrations with other systems responsible for the creation of work orders and the content being updated between them.

- **Manual**  

  In many organizations, there are numerous scenarios that require the manual creation of a work order record by an application user. Somes examples include responding to a phone call from a customer, or the identification of other services that need to be supplied while a frontline worker is at the service location.

In addition to documenting work order creation scenarios and processes, it's also important to identify the required work order content during the creation process. Ensuring that work orders are populated with the necessary information enables them to be processed through the service lifecycle as efficiently as possible.

While the definition of *required content* varies by organization, industry, service type, or creation method, there are some general categories to consider in many of the scenarios. The following list covers some examples:

- **Identifying the service customer**  

  In some instances, the customer is your own organization, but most of the time the customer is an external entity with unique attributes that must be considered when delivering service to them. When you identify the service customer on the work order, those unique customer attributes can be accommodated.

- **Determining the service location**  

  When performing field service, or service in varied locations, it's important to identify the specific location where the service is provided. Usually, you register the location by a postal address that can be transformed into latitude and longitude coordinates (geocode). The geocode can then be used to figure out estimated travel time between service locations and help in selecting the right resources for scheduling the work order.

- **Defining the estimated scope of work**  

  The scope of a work order normally includes content that defines the type of service work expected to be performed, which in turn helps to determine the duration of time to be allocated, the right resources needed to carry out the work, and the potential parts and materials that might be needed. Accurately estimating the scope of work during work order creation significantly increases the likelihood of completing the work within the shortest amount of time, with the fewest number of service visits, and makes the most efficient use of your company's resources.

- **Establishing pricing and entitlements**  

  In some scenarios, there might be a need to modify the price of the parts and labor used in the work order or ensure that the service work accounts for certain entitlements, or service level agreements (SLAs), based on the service customer, the type of work being performed, or the details of a service contract. Ensuring these items are documented correctly during work order creation helps ensure that the work is scheduled and completed as expected, reducing the need to make modifications afterwards.

- **Defining scheduling parameters**  

  Particularly in field service scenarios, where frontline workers are traveling to multiple service locations within a day, and time commitments are being made to customers, ensuring that certain scheduling parameters are well defined in the work order during the creation process allows for maximum optimization of service operations while meeting customer expectations.

## Stakeholders  

Given that the documentation of work order creation methods and required content is foundational to the downstream processes of scheduling and service delivery, it's important to include the necessary stakeholders when defining these processes for your implementation project. Many people across the organization should contribute to the decision-making process and design of the *Create work orders* business process area. The following list provides examples of such stakeholders: 

- **Operations stakeholders**– Examples: COO  

- **Field service stakeholders**– Examples: Service managers, Field Supervisors, Dispatchers, Frontline Workers

- **Customer service stakeholders** – Examples: Call center manager

- **Finance stakeholder** – Examples: CFO. Controller

## Create work orders process flow 

The following diagram illustrates the *Create work orders* business process area.

:::image type="content" source="media/service-to-cash-graphics-create-work-orders-flow.svg" alt-text="Flow diagram for the business process area, which is explained in the paragraphs after the image." lightbox="media/service-to-cash-graphics-create-work-orders-flow.svg":::

1. Start

2. A parallel branch from 1. Start includes the *Service to Cash* end-to-end process.

    1. *Create and manage accounts* for servicing business process area

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

3. A parallel branch from 1. Start includes *Case to resolution* end-to-end process

    1. *Conver to work order* business process

        1. Connects to 2.e *Create work orders* business process area

4. A parallel branch from 1. Start includes *Project to profit* end-to-end business process

    1. *Deliver project work* business process area

    2. Connects to 2.e *Create work orders* business process area

5. A parallel branch from 1. Start includes *Acquire to dispose* end-to-end business process

    1. *Acquire assets* business process area

    2. Connects to 2.e.iv *Define expected scope of work* business process

6. End

## Create work orders benefits

There are many benefits from the *Create work order* process area. The following sections describe key benefits of the *Create work order* process in Dynamics 365 solution.   

### Centralized work information

A work order includes all key information needed to execute a service job, supplying a single centralized record of the work that service managers can track and later use for reporting and analytical purposes.

### Scheduling efficiencies

Ensuring that work orders include the necessary information allows optimization of the service schedule. Allowing dispatchers to select the best resources and time slots to conduct the service work, while minimizing the need for other service trips.

### Quality of service delivery

Capturing accurate and complete data about the work to be executed so that field service resources are scheduled to arrive at the right location, with the right parts, supporting guides and steps that need to be executed to complete the work promised to the customer.

## Next steps

If you would like to implement Dynamics 365 solutions to help with your *Create work order* processes, you can use the following resources and steps to learn more. Links are added when articles become available.

1. *Create work orders* (The article that you're currently reading)

2. *Schedule work orders*

3. *Perform service work*

4. *Review and close work orders*

5. *Analyze service operations*

## Related resources

You can use the following resources to learn more about the Create work orders process in Dynamics 365.

- [Create a work order - Dynamics 365 Field service](/dynamics365/field-service/create-work-order)
- [Create and define work orders - Training](/training/modules/implement-work-order-management-agreements-inventory-and-purchasing/2-creating-and-defining-work-orders)
- [Exam MB-240: Microsoft Dynamics 365 Field Service Functional Consultant](/certifications/exams/mb-240)
- [Service Management - Dynamics 365 Supply Chain Management](/dynamics365/supply-chain/service-management/service-management-home-page)
- [Service Management - Dynamics 365 Business Central](/dynamics365/business-central/service-service)
- [Implementation strategy](../implementation-guide/implementation-strategy.md)
- [Process-focused solution](../implementation-guide/process-focused-solution.md)

- Find definitions of terminology used in content for *Create work orders* process area in the [Glossary of terms in Dynamics 365 business processes](/dynamics365/guidance/business-processes/glossary) article, including the following terms:

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

##  Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Customer services, Engineering, IT (Information Technology), Operations, Production, Project Management, Service operations, Transportation, Warehouse

*Products:* Dynamics 365 Business Central, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Guides, Dynamics 365 Project Operations, Dynamics 365 Remote Assist, Dynamics 365 Supply Chain Management
