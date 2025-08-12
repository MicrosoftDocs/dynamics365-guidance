---
title: Integrate a booking system with Dynamics 365 Customer Service
description: Learn how to integrate a booking system with Dynamics 365 Customer Service to manage customer appointments and streamline data exchange.
author: vibhutinair23
ms.author: vibhutinair
ms.topic: reference-architecture
ms.date: 08/12/2025
---

# Integrate a booking system with Dynamics 365 Customer Service

***Applies to: Dynamics 365 Customer Service, Azure Logic Apps, Azure Functions***

This solution uses Dynamics 365 Customer Service, Azure Logic Apps, and Azure Functions to integrate with a system by consuming an external API. This integration allows Dynamics 365 Customer Service to obtain a session ID from the booking system, which is then used to redirect the user to the booking system to load the appropriate details.

## Introduction

This reference architecture applies to industries where customer service and support are critical, such as finance, retail, healthcare, and telecommunications. It's useful in scenarios where you require integration with external systems to provide comprehensive customer support.

Use this reference architecture during the design phase of the overall implementation to ensure seamless integration with the booking system.

Key stakeholders for this architecture include solution architects, API developers, customer service managers, and IT administrators.

This integration solution streamlines the process of managing customer appointments by connecting Customer Service with a booking solution. It ensures efficient data exchange and a unified user experience by using various systems and services, including cloud deployments and hybrid deployments  with Microsoft apps and services, and solutions from other service providers.

In today's competitive healthcare environment, efficient appointment management is crucial for enhancing patient experience and operational efficiency. This integration solution addresses the need for seamless data transfer and unified management of customer appointments, improving accuracy and reducing manual efforts.

## Architecture

The following diagram illustrates the architecture for the solution.

:::image type="content" source="./media/customer-service-integrate-booking-system-appointments.svg" alt-text="Diagram showing the integration with a booking system for appointments." lightbox="./media/customer-service-integrate-booking-system-appointments.svg":::

[Download a Visio file](https://github.com/microsoft/dynamics365patternspractices/blob/main/architectures/) with this architecture. To download an architecture, choose the file in the explorer, and then choose the download raw file icon.

The components in this architecture include:

- **Dynamics 365 Customer Service**: Manages customer details and appointment IDs
- **Booking Solution**: Handles appointment scheduling
- **iPaaS**: Facilitates data exchange
- **SAP PAS**: Supports the integration process
- **Azure**: Provides infrastructure and services
- **Stripe/Sycurio**: Manages payments and security
- **Avaya**: Provides communication services

## Dataflow

The dataflow in this architecture is as follows:

1. Dynamics 365 Customer Service sends customer details and appointment IDs to the booking solution's API to get a session ID.
1. Dynamics 365 Customer Service redirects users to the booking solution with the session ID.
1. The booking solution pushes appointment information back to Dynamics 365 using RFC/API.
1. RFC-based interaction with SAP PAS.
1. Dynamics 365 Web API interaction with iPaaS.

## Components

The components used in this architecture include:

- **Azure Logic Apps**: Used to orchestrate the API call to the booking system.
- **Azure Functions**: Used to process the session ID and redirect the user to the booking system.
- **Dynamics 365 Customer Service**: The core application where the integration is initiated.

## Scenario details

This reference architecture addresses the need for integrating Dynamics 365 Customer Service with a booking system for comprehensive customer support. The solution uses Azure Logic Apps and Azure Functions to consume an external API and process the session ID. The goal is to provide a seamless user experience by redirecting the user to the booking system with the relevant session details.

### Potential use cases

This solution is for a customer service organization. Industries like finance, retail, healthcare, and telecommunications can use it. Any organization that requires integration with external systems for customer support can use it.

Use this solution to:

- Enhance customer support by integrating with external systems.
- Streamline processes by automating API calls and redirections.
- Improve user experience by providing seamless access to external systems.

#### Scenario 1: Healthcare appointment management

A hospital uses D365 CE to manage patient information and appointments. When a patient books an appointment online through the hospital's booking solution, D365 CE sends the patient details and appointment ID to the booking solution's API to obtain a session ID. The patient is redirected to the booking solution with the session ID for confirmation. The booking solution updates the appointment information back to Dynamics 365 using RFC/API. This ensures seamless synchronization between Dynamics 365 and the hospital's booking system, reducing manual data entry and improving accuracy.

#### Scenario 2: Financial services appointment booking

A financial advisory firm uses Dynamics 365 to manage client relationships and appointment schedules. When a client books an appointment through the firm's booking solution, Dynamics 365 sends the client details and appointment ID to the booking solution's API to obtain a session ID. The client is redirected to the booking solution with the session ID for further processing. The booking solution pushes the updated appointment information back to Dynamics 365, ensuring that all appointments are accurately recorded and synchronized. This integration enhances the client experience by providing a streamlined booking process.

#### Scenario 3: Retail customer service appointments

A retail company uses Dynamics 365 to manage customer interactions and service appointments. When a customer schedules a service appointment through the company's booking solution, Dynamics 365 sends the customer details and appointment ID to the booking solution's API to obtain a session ID. The customer is redirected to the booking solution with the session ID for appointment confirmation. The booking solution updates the appointment information back to Dynamics 365 using RFC/API. This integration helps the retail company maintain accurate records of service appointments and improve customer satisfaction.

#### Scenario 4: Education institution scheduling

An educational institution uses Dynamics 365 to manage student information and class schedules. When a student books a counseling session or class appointment through the institution's booking solution, Dynamics 365 sends the student details and appointment ID to the booking solution's API to obtain a session ID. The student is redirected to the booking solution with the session ID for finalizing the booking. The booking solution updates the appointment information back to Dynamics 365 using RFC/API. This integration ensures that student schedules are accurately recorded and synchronized across systems, enhancing the administrative efficiency of the institution.

## Considerations

These considerations help implement a solution that includes Dynamics 365. Learn more at [Dynamics 365 guidance documentation](../index.yml).

<!--

## //Next steps

## //Related patterns

## Tags

*Industries*: Finance, Retail, Healthcare, Telecommunications

*Stakeholders*: Customer services, IT

*Products*: Dynamics 365 Customer Service, Azure Logic Apps, Azure Functions
--->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

[Michael Richard](https://www.linkedin.com/in/mike-richard/)
