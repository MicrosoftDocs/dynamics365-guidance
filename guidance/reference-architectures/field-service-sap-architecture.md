---
title: Dynamics 365 Field Service and SAP Integration Overview
description: Discover a reference architecture for combining Dynamics 365 Field Service and SAP to manage work orders, dispatch technicians, and handle invoicing seamlessly.
#customer intent: As a Dynamics 365 solution architect, I want to learn how to configure Dataverse and Field Service so that I can set up the environment for my organization.
author: edupont04
ms.author: edupont
ms.reviewer: edupont
ms.date: 09/26/2025
ms.topic: reference-architecture
---
# Dynamics 365 Field Service with SAP reference architecture

***Applies to***: ***Dynamics 365 Field Service, Dataverse, Azure Logic Apps, and Azure Functions***

This solution combines Dynamics 365 Field Service, augmented with Customer Service, with SAP through Azure Integration Services. It builds an integrated field service application that lets back office users manage and dispatch orders, lets technicians carry out work on site and document results with the mobile app, and handles invoicing and value flow in SAP.



## Introduction

Apply the solution across industries that use field services to install and maintain equipment on internal or external sites: manufacturing, industrial equipment, utility, medical equipment, and others.

The following use cases are supported (non-exhaustive list):

- Corrective maintenance: A customer has a service contract for one or several assets and unexpected problems with their equipment need to be addressed by identifying and dispatching an engineer.
- Preventive maintenance: A customer has a service contract for one or several assets and regular maintenance of their equipment must be planned, scheduled and executed.

Use this reference architecture as a starting point for projects with similar use cases, mostly pure onsite field service. You can also extend it to remote services, including predictive maintenance and customer service.

Key stakeholders for architecture discussions include enterprise architects, Dynamics and SAP solution architects, product managers and owners, and functional and technical leads.

## Architecture

The following diagram shows the solution architecture.

:::image type="content" source="media/field-service-sap-architecture.svg" alt-text="Screenshot of the reference architecture diagram for Microsoft Dynamics 365 Field Service with SAP." lightbox="media/field-service-sap-architecture.svg":::

[Download a PowerPoint file](https://github.com/microsoft/dynamics365patternspractices/blob/main/architectures/field-service-sap-reference-architecture.pptx) with this architecture. To download an architecture, choose the file in the explorer, and then choose the download raw file icon.

## Dataflow

The main dataflow is as follows:

1. Persist master data in Dynamics 365. Typical records include accounts, contacts, service contracts, and products from SAP (for example, SAP MDG). It's often sufficient to load these records once per day via ETL (for example, Azure Data Factory). When you need near-real-time updates, use the message integration pattern described below.
1. Users can maintain customer assets directly in Dynamics 365 Field Service, which then services as the Installed Base (IBase). For some organizations, the IBase is maintained in the separate system that they must then integrate, usually via message integration.
1. A customer creates a case for corrective maintenance by using a portal, sending an email, or calling the call center.
1. Convert the corrective-maintenance case to a work order, or create the work order automatically by using the agreement functionality for preventive maintenance.
1. When a work order is created, the system automatically syncs it to SAP via message integration and records it there as a service order.
1. A dispatcher handles the related resource requirement and creates a bookable resource booking. The technician records materials (work order products) and time (time entries) during processing.
1. Confirm the process to close a work order based on business requirements; for example, you can require a customer signature. After you close the work order, send time and materials to SAP.
1. SAP handles invoicing and provides final status—sometimes including the invoice PDF—to Dynamics.

The specific dataflow for the SAP integration is as follows. Note that this is a simplified view that leaves out, for example, secret handling with Azure Key Vault and specific error handling:

1. When the work order creation event triggers, Dynamics sends the payload to a Service Bus queue.
1. A Logic App or function app picks up the message and transforms it for the receiving SAP system.
1. The message is routed via API Management.
1. API Management calls the respective SAP endpoint (note that there could also be a standard connector being used which can sit before or after API Management).
1. SAP sends a response (this could also be a specific outbound message initiated from SAP).
1. The message is routed into a Service Bus queue.
1. The message is picked up by a Logic App or Function App.
1. The app transforms and enriches the message as needed, then calls the Dataverse API endpoints to perform CRUD operations on the appropriate tables.

## Components

The following components are used in the reference architecture. For simplicity, some components are left out; an exhaustive set of Microsoft platform capabilities can expand the feature scope, increase security, and improve operations:

- [Dataverse](/power-apps/maker/data-platform)  

  This key offering from Microsoft is the backbone of the solution providing the main data storage and capabilities to access and configure the user interface and workflows.
- [Dynamics 365 Field Service](/dynamics365/field-service/)  

  Microsoft's SaaS offering provides full field service capabilities on top of Dataverse. Back-office users use the web client, and technicians use the mobile app to work with the data. Configure UI elements as a model-driven app, and configure out-of-the-box artifacts as needed to meet business requirements.
- [Azure Service Bus](/azure/service-bus-messaging/)  

  Use Microsoft's enterprise message broker to queue inbound and outbound messages for resilient, effective communication with SAP and other systems. It supports the message integration pattern: outbound messages with the full payload go into queues through Dataverse's out-of-the-box integration, and Logic Apps or Azure Functions pick up inbound messages to update Dataverse.
- [Azure Logic Apps](/azure/logic-apps/)  

  This part of Microsoft's Azure Integration Services provides enterprise integration capabilities and orchestrates message distribution using standard connectors (including SAP). [Azure Functions](/azure/azure-functions/) are a more pro-code alternative; they require developer skills but can provide more reusability and control.
- [API Management](/azure/api-management/)  

  Use this component to manage, protect, and monitor integration endpoints, and to facilitate access to the client's other cloud or on-premises environments.

## Scenario details

This solution addresses field service needs: it handles resource requirements, booking, and work-order processing, and integrates data with SAP for invoicing to help dispatchers manage operations.

This scenario uses Microsoft Dataverse, Dynamics 365 Field Service, Azure Service Bus, Azure Logic Apps, and API Management. These services provide infrastructure for data storage, workflow configuration, resilient messaging, integration workflow orchestration, and endpoint management.

The organization's goals are to streamline field service operations, ensure effective communication between systems, and optimize the invoicing process. Implementing this solution improves operational efficiency, data integration, and service delivery.

This solution is applicable to various industries such as telecommunications, healthcare, manufacturing, and government. It suits any organization that requires a robust field service management system with seamless integration capabilities.

### Potential use cases

Use this solution to streamline field service operations in industries such as telecommunications, healthcare, manufacturing, and government. It handles resource requirements, booking, work-order processing, and integration with SAP for invoicing.

Use this solution to:

- Streamline field service operations
- Ensure effective communication between systems
- Optimize the invoicing process

## Considerations

These considerations help implement a solution that includes Dynamics 365. Learn more at [Dynamics 365 guidance documentation](../index.yml).

### Cost optimization

Cost optimization is about reducing unnecessary expenses and improving operational efficiency. For more information, see [Overview of the cost optimization pillar](/azure/architecture/framework/cost/overview).

One key price component is the Field Service license. Learn more at [Dynamics 365 Field Service pricing](https://www.microsoft.com/dynamics-365/products/field-service/pricing). Azure pricing mainly relates to the number of messages sent. If you use the default tiers of the services described earlier, the price depends on the number of cases and messages. For example, assume three messages per case: one to initiate the service order, one to send final work order information to SAP, and one for SAP to confirm that invoicing is complete.

It's important, though, to consider licenses that aren't consumption based, for example the Logic Apps Integration Account (needed to use Liquid), API Management (Premium can be costly and can be the only option when, for example, a VNET integration is needed), or Service Bus.

## Deploying Dataverse and Dynamics 365 Field Service

Consider the following steps for all environments that are part of your ALM and environment strategy (typically development, test, and production):

1. Set up your Dataverse environment and database instance. Follow the steps in [Create and manage environments in the Power Platform admin center](/power-platform/admin/create-environment).
1. Follow the steps in this article to install the Field Service module: [Install Dynamics 365 Field Service](/dynamics365/field-service/install-field-service).

## Implementing Azure Integrations

This section doesn't describe every Azure component. It provides an example to get started.

### Procedure: Logic App (Outbound)

1. Create an Azure Service Bus Queue

    1. **Create a Service Bus Namespace**: In the Azure portal, create a new Service Bus namespace if you don't already have one.
    1. **Create a Queue**: Within the Service Bus namespace, create a new queue where your messages will be stored.

1. Create the Logic App

    1. **Create a Logic App**: In the Azure portal, create a new Logic App.
    1. **Add a Trigger**: Add the trigger When a message is received in a queue from the Azure Service Bus connector. Configure it to point to your Service Bus namespace and queue.

1. Transform the message

    1. **Add a Parse JSON Action**: Use the Parse JSON action to parse the message content. You'll need to provide a sample JSON payload to generate the schema.
1. **Add a Compose Action**: Use the Compose action to build the JSON message in the format required by SAP S/4. Use dynamic content from the parsed message to construct this JSON.

1. Send the message to Azure API Management.

    1. **Add an HTTP Action**: Use the HTTP action to send the JSON message to Azure API Management. Configure the action with the appropriate method (e.g., POST), URL, headers, and body.

1. Route the message to SAP S/4 via Azure API Management.

1. **Create a Policy to Route the Message**: In Azure API Management, create a policy to route the incoming message to SAP S/4. Use the set-backend-service policy to specify the SAP S/4 endpoint.

## Related resources

Review the following related architecture guides, solutions, and other guidance content:

- [Dynamics 365 Field Service](https://www.microsoft.com/dynamics-365/products/field-service)  
- [Integration Services](https://azure.microsoft.com/products/category/integration)

<!-- ## Tags

*Industries:* Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Real Estate (60-67), Services (70-89)

*Stakeholders:* Customer services, Engineering, IT, Service operations

*Products:* Dynamics 365 Field Service -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- Armin Fischer
