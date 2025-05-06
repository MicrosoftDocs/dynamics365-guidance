---
title: Saga pattern with Dataverse or Dynamics 365
description: Learn about establishing a robust mechanism for transmitting data from Dataverse to other applications using the Saga pattern, with an outline on architecture.
author: dereklh77
ms.author: edupont
ms.topic: reference-architecture
ms.date: 09/04/2024
---

# Saga pattern with Dataverse or Dynamics 365

***Applies to:*** ***Dynamics 365 Customer Insights - Journeys, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Sales, Dataverse***

This solution integrates Dataverse, Azure Functions, Azure Service Bus, Azure Key Vault, and Application Insights to establish a robust mechanism for transmitting messages/data from Dataverse to other applications using the [Saga pattern](/azure/architecture/reference-architectures/saga/saga).

In its basic configuration, the Saga pattern facilitates the creation of one interface for data exchange from Dataverse to a non-Microsoft service. The Saga pattern ensures message replays, monitoring, and error management with minimal effect on Dataverse performance. In more intricate setups, it enables the simulation of distributed transactions across multiple systems.

## Introduction

Dynamics 365 applications are invariably integrated with other business applications, necessitating the exchange of data or events between them. This process often demands a high level of integrity and consistency. The Saga pattern represents a state-of-the-art approach to managing such scenarios, particularly when multiple target systems are involved. This document outlines the implementation of the Saga pattern, specifically when Dataverse serves as the source or when the application is built upon Dataverse.

## Architecture

The following diagrams illustrate the architecture for the solution. The first one is the simplest case with only one non-Microsoft service and no compensation transaction. The second is more comprehensive with multiple non-Microsoft services and compensation transactions.

:::image type="content" source="../media/saga-pattern-dataverse-dynamics-365-architecture-simple.svg" alt-text="Diagram showing the connection between Dataverse, Service Bus, Azure Functions, non-Microsoft services, and Azure Key Vault." lightbox="../media/saga-pattern-dataverse-dynamics-365-architecture-simple.svg":::

This architecture shows the Saga design pattern in its simplest form with only one target non-Microsoft service and no compensation transaction. In this case, it allows synchronization of data from Dataverse to the non-Microsoft service with high availability, automatic replays, and resilience.

:::image type="content" source="../media/saga-pattern-dataverse-dynamics-365-architecture-complex.svg" alt-text="Diagram of three integrations, showing fatal errors occurring during the Azure Functions in the main transactions." lightbox="../media/saga-pattern-dataverse-dynamics-365-architecture-complex.svg":::

This architecture shows the Saga design pattern with multiple chained non-Microsoft services and compensation transactions. In this case, it allows synchronization of data from Dataverse to multiple non-Microsoft services, in a specific order. If a fatal error occurs in one of the services, a compensation is started and run in reverse order of the main transaction.

[Download a PowerPoint file](https://github.com/microsoft/dynamics365patternspractices/blob/main/architectures/saga-pattern-with-dataverse-or-dynamics-365.ppt) with these architectures. To download an architecture, choose the file in the explorer, and then choose the download raw file icon.

## Dataflow

1. Event is triggered by Dataverse, which stores a message in an Azure Service Bus queue.

2. First Azure function app is triggered:

    1. It transforms the message.

    2. It retrieves credentials from Azure Key Vault. (If the non-Microsoft service is on Azure, using a managed identity is preferable.)

    3. It sends the message to the non-Microsoft service.

    4. If successful, it stores the results in the next queue.

    5. If given a transient error, the message is posted again in the queue with a custom delay.

    6. If given a definitive error, either it logs the error, or it starts a compensating transaction.

3. The second Azure function app is triggered and it processes the message to the next non-Microsoft service.

4. Continue until all services are reached or a definitive error occurs.

At each stage, each component must store log information in Application Insights.

## Components

The reference architecture incorporates the following components:

- [Dataverse](/training/paths/get-started-cds/): The platform where the trigger event takes place, and the source of messages and data.

- [Azure Service Bus](/azure/service-bus-messaging/service-bus-messaging-overview): The platform hosting all [queues](/azure/service-bus-messaging/service-bus-queues-topics-subscriptions#queues). There's one dedicated queue for each partner, ensuring that messages directed toward a specific partner are stored in the corresponding queue. This design is integral for preventing message loss.

- [Azure Functions](/azure/azure-functions/functions-overview?pivots=programming-language-csharp): There's one Azure function app assigned to each partner. These functions are responsible for processing messages within their respective queues.

- *Optional*: If you're implementing a compensation transaction, an extra queue and Azure function app are required for each non-Microsoft system.

- [Application Insights](/azure/azure-monitor/app/app-insights-overview): Integrated to provide comprehensive monitoring and insights into the system.

- [Azure Key Vault](/azure/key-vault/): Optional if all non-Microsoft services support managed identities.

## Scenario details

The proposed architecture is designed to address the following scenarios:

- Exporting data from Dataverse to a single non-Microsoft system with reliability.

- Exporting data from Dataverse to multiple non-Microsoft systems with reliability and consistency:

  - Ensures reliability and consistency across multiple non-Microsoft systems.

  - If given a transient error on one system, the transaction for that system is retried independently.

  - If an error persists, a compensating transaction can be initiated on preceding systems.

  - The compensating transaction has the capability to roll back transactions or update specific statuses.

This architecture aims to provide a robust and dependable framework for data exportation from Dataverse to external systems, ensuring seamless operations even in the face of temporary disruptions or errors.

### Potential use cases

The proposed solution isn't industry-specific; its application extends to situations requiring data integrity across multiple systems. In instances where real-time data synchronization is imperative between a Dynamics 365 application and a non-Microsoft system, particularly in scenarios involving significant data volumes or intricate non-Microsoft system interactions, it serves as a viable alternative to Power Automate.

For straightforward cases, where only one target system is involved, the solution has proven effective across various organizations. However, its utility is most apparent in complex scenarios that entail intricate processes across multiple systems. For example, in an organization, when a contact was created in Dynamics 365 Sales, the following sequence of actions is required:

- Transmitting contact information to a system with master data, which assigns a unique identifier to the contact.

- Storing the unique identifier on the Dynamics 365 contact record.

- Transmitting both the contact information and the unique identifier to the ERP system.

In such intricate cases, the Saga pattern is employed. This pattern divides the entire transaction into three smaller transactions, ensuring data consistency without creating dependencies between systems. This approach is beneficial in scenarios where maintaining data integrity is crucial, and system coupling must be avoided.

## Considerations

These considerations help implement a solution that includes Dynamics 365. Learn more at [Dynamics 365 guidance documentation](../../guidance/overview.md).

Consider the following points when implementing the Saga pattern:

- It's adapted for complex workflows or for huge volume.

- For each system, you must think about the retry strategy (how many times do we retry, time between each retry) and about the compensation transaction (what do we do if the transaction with other systems fails).

- There are multiple variants of implementation for the transactions with the non-Microsoft system.

- This requires pro-development skills.

### Cost optimization

Cost optimization is about looking at ways to reduce unnecessary expenses and improve operational efficiencies. For more information, see [Overview of the cost optimization pillar](/azure/architecture/framework/cost/overview).

The cost depends on the number of non-Microsoft systems, on the number of exchanged messages, and on the execution time required to call the non-Microsoft systems.

You must allocate:

- An environment with Dataverse or Dynamics 365.  

- One [Application Insights](https://azure.microsoft.com/pricing/details/monitor/).

- One [Azure Key Vault](https://azure.microsoft.com/pricing/details/key-vault/) (not required if all non-Microsoft systems aren't on Azure).

- One [Azure Service Bus](https://azure.microsoft.com/pricing/details/service-bus/) with one queue per non-Microsoft system (two if you implement compensation transactions).

- One [Azure Function](https://azure.microsoft.com/pricing/details/functions/) per non-Microsoft system (two if you implement compensation transactions).

## Implementing the Saga pattern with Dataverse or Dynamics 365

The initial step involves crafting your scenario:

1. Identify all non-Microsoft systems in use.

2. Define the sequence of transactions between systems, specifying the initial trigger and required actions on each system.

3. Establish the message exchange format for queues between systems.

4. Specify necessary transformations between a message and the expected payload of a system.

5. Define authentication modes for each non-Microsoft system, considering options such as managed identities or the use of secrets (Api-Key, passwords, certificates, and so on).

6. Establish an automatic retry strategy for each system. This determines the conditions under which a message should be retried, the number of retries, and the time intervals between each attempt (an exponential retry strategy is recommended).

7. Outline compensation transactions: identify actions to be taken if given a fatal error on a system, including changes required on systems that have already processed the transaction (for example, rollback, status change).

## Procedure: Deploy Azure Key Vault

If you identified some secrets to use during Step 5, you must store them securely. For that, you need to create key vault as described in this [Quickstart](/azure/key-vault/general/quick-create-portal).

## Procedure: Deploy Azure Service Bus queues

For each non-Microsoft system, you must create a queue (if the system isn't involved in a compensation transaction) or two queues (if the system is involved in a compensation transaction). For that, you can use this [Quickstart](/azure/service-bus-messaging/service-bus-quickstart-portal).

## Procedure: Integrate Dataverse/Dynamics 365 apps with Azure Service Bus

The first step is to [register a service endpoint in Dataverse](/power-apps/developer/data-platform/walkthrough-configure-azure-sas-integration).

Then you [register an Azure-aware plug-in](/power-apps/developer/data-platform/walkthrough-register-azure-aware-plug-in-using-plug-in-registration-tool) with a step matching the defined trigger.

Alternatively, you can write your own Dataverse plugin, which posts a message in the queue. You can either:

- Use the [IServiceEndpointNotificationService](/dotnet/api/microsoft.xrm.sdk.iserviceendpointnotificationservice). You're given more control over the trigger while letting Dataverse manage the message and the connection with Service Bus.

  *Or*

- Use the Service Bus API directly from your .NET code. You're given more control over the trigger and over the message format, but you must manually handle the connections and the retries.

## Procedure: Implement Azure Functions

For each queue, you must develop an Azure function app, which processes the messages of the queue. You can follow the [Getting started with Azure Functions](/azure/azure-functions/functions-get-started?pivots=programming-language-csharp) guide for implementing the function. Then you have to trigger the function when a message is available in the queue by following the [Azure Service Bus trigger for Azure Functions](/azure/azure-functions/functions-bindings-service-bus-trigger?tabs=python-v2%2Cisolated-process%2Cnodejs-v4%2Cextensionv5&pivots=programming-language-csharp) documentation.

The function should:

1. Read the message.

2. Transform the message if required.

3. Send the message to the related non-Microsoft system (if necessary, the credentials must be retrieved from Azure Key Vault).

4. Based on the response, create a new message for the next system and put it in its queue.

5. If given a transient error, retry the message following the defined strategy. This can be easily implemented with the [ScheduledEnqueueTime](/dotnet/api/azure.messaging.servicebus.servicebusmessage.scheduledenqueuetime) property: if given an error, create a copy of the message, define the time when it must be retried, and put it again in the source queue. We recommend adding a counter of failures so that you can adjust the strategy based on the number of failures.

6. If given a fatal error, create a new message for the compensation transaction and put it in the queue for the previous system.

## Procedure: Implement Application Insights

All your components should log events into Application Insights so that you're able to monitor the whole system.

To do this:

1. Set up Azure Monitor following this [Getting Started](/power-platform/admin/analyze-telemetry) guide.

2. Integrate Dataverse with Application Insights as documented in the [Export data to Application Insights](/power-platform/admin/set-up-export-application-insights) guide.

3. Ensure your Azure Functions send logs to Application Insights:

    1. All message exchanges in the queue should have a Diagnostic-Id identifier as described in the [End-to-end tracing and diagnostics](/azure/service-bus-messaging/service-bus-end-to-end-tracing) documentation.

    2. Standard monitoring of Azure Functions must be configured as described in the [Monitoring Azure Functions](/azure/azure-functions/monitor-functions) documentation.

    3. Relevant traces of custom code must be sent to Application Insights using the [ILogger service](/azure/azure-monitor/app/ilogger).

## Related patterns

The following patterns are available to help guide your implementation of the Saga pattern with Dataverse:

- [Saga distributed transactions pattern](/azure/architecture/reference-architectures/saga/saga) describes the pattern in a general context, without Dataverse.

- [Retry pattern](/azure/architecture/patterns/retry) describes how to define and implement retry strategies.

## Related information

You can use the following resource to learn more about the integration of Dynamics 365 with Azure:

- [Azure integration](/power-apps/developer/data-platform/azure-integration)

<!-- ## Tags

*Products:* Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, Dynamics 365 Sales, Dataverse -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributor.*

Principal author:

- [Nicolas Prats](https://www.linkedin.com/in/nicolas-prats-97808096) \| Solution Architect
