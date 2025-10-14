---
title: Build Resilient Data Sync Using Asynchronous Request-Reply
description: Discover how to implement asynchronous request-reply patterns and last snapshot delivery for seamless data sync between Dynamics 365 and external systems.
author: edupont04
ms.author: edupont
ms.reviewer: edupont
ms.date: 10/09/2025
ms.topic: reference-architecture
---
# Designing reliable data sync with asynchronous request-reply and last snapshot delivery for Dynamics 365 Sales

***Applies to***: ***Dynamics 365 Sales, Dataverse, Azure Service Bus, Azure Functions, Azure Key Vault***

This solution combines Dynamics 365, Dataverse, Azure Service Bus, Azure Functions, Azure Key Vault, and Azure Application Insights to build a reliable, event-driven sync solution. In this setup, the target system acts as the primary data holder, and Dynamics 365 is the publisher that requires acknowledgment from the target system. This concept adapts the [asynchronous request-reply pattern](/azure/architecture/patterns/async-request-reply), where a front end communicates with a back end and expects a response.

## Introduction

In the digital ecosystem, it's common for data to flow between different systems to keep everything in sync and consistent. A typical use case is syncing data from Dynamics 365 or Dataverse to an external system. For example, changing a *prospect* to a *customer* when someone creates an account or changes its status. This article explains how to make sure the latest snapshot of data reliably goes to a target system by using event-driven patterns like notification services and retry mechanisms. The focus is on building a robust system where failures don't cause data loss, and the latest data always goes through, even if there's a retry.

## Architecture

The following diagram shows the solution architecture. It uses Dynamics 365 or Dataverse, Azure Service Bus, Azure Functions, Azure Key Vault, Azure Application Insight, and a target system. The diagram shows the end-to-end process in sequence with all components involved.

:::image type="content" source="media/sales-reliable-data-sync-asynchronous-request-reply.svg" alt-text="Diagram that shows the architecture for resilient data sync using the asynchronous request-reply pattern." lightbox="media/sales-reliable-data-sync-asynchronous-request-reply.svg":::

[Download a PowerPoint file with this architecture](https://github.com/microsoft/dynamics365patternspractices/tree/main/architectures). To download an architecture, select the file in the explorer, and then select the download raw file icon.

## Dataflow

1. A change in Dataverse, like account creation, status change, or an on-demand trigger through a custom API, starts an asynchronous event.
1. The system creates a notification message based on the row data and adds an internal record to a dedicated table before trying to send it, including the notification content, to the Service Bus.
1. The plugin uses *managed identity* to access the right Service Bus queue.
1. After the message reaches the Service Bus, the system deletes the internal record to confirm delivery. You don't need to monitor the end-to-end flow using this table because Dynamics 365 or Dataverse finishes its part at this stage.

    If the plugin can't reach the Service Bus, it updates the internal record's status to show the failure and the reason. This setup lets you resend the message by running a retry process on this table.
1. An Azure Function runs when it gets the event message from the outbound queue.
1. The Azure Function gets the latest data from Dynamics 365 or Dataverse by using the details in the notification message (**Source Row ID**).

    If any errors happen, including temporary ones, the system returns the notification message to the initial queue and schedules it for retry up to X times. The notification message has a **RetryCount** property to track the number of tries. If it hits a set threshold (which is better if it's configurable), the system moves the message to the [*dead-letter queue*](/azure/service-bus-messaging/service-bus-dead-letter-queues) (DLQ). Otherwise, it reschedules the message in the outbound queue with an exponential backoff, so the delay between retries grows each time.
1. The Azure Function changes the data to fit the target system's needs and sends the message.

    1. Get credential information only after the function app checks the message to avoid extra calls to Azure Key Vault. If you can, use credential caching to reuse the authentication token instead of getting a new one each time.
    2. Errors can happen due to a bad message transformation, a temporary issue, invalid credentials, or an unavailable upstream system. If an error occurs, the retry process either reschedules the message or moves it to the dead-letter queue of the outbound queue.
1. After the message is delivered to the target system, the system processes the response and sends it to another dedicated queue with both integration keys (**Source Row ID** and **Target System Row ID**).

    The main reason for using a second queue is to make sure that if the next step—reaching the Dynamics 365 or Dataverse instance—doesn't work, only the acknowledgment process is retried, not the whole dataflow.
1. A second Azure Function runs when it gets the event message from the inbound queue.
1. The Azure Function processes the response, updates the source row, and makes sure the record is acknowledged.

    The retry process also works here. If a problem happens, the system either reschedules the message for reprocessing or moves it to the dead-letter queue for more analysis.

Throughout the process, the system logs all telemetry in Application Insights by using a correlation ID for traceability and troubleshooting. Dynamics 365 or Dataverse can connect directly to Application Insights to send more information during steps 1 to 4. All authentication between Azure services and between Azure services and Dynamics 365 or Dataverse uses a managed identity. In this scenario, only the target system is a non-Microsoft service, so using Azure Key Vault is highly recommended.

## Components

The following components are used in the reference architecture:

- [Dynamics 365](https://www.microsoft.com/dynamics-365/what-is-dynamics-365) and [Dataverse](/power-apps/maker/data-platform/data-platform-intro) are the source of data and event triggers.

- [Azure Service Bus](/azure/service-bus-messaging/service-bus-messaging-overview) stores notification messages that represent data changes.

  - Use a [queue](/azure/service-bus-messaging/service-bus-queues-topics-subscriptions#queues) per direction for data isolation and to prevent message loss.

  - If multiple systems need to subscribe, use [Topic & Subscription](/azure/service-bus-messaging/service-bus-queues-topics-subscriptions#topics-and-subscriptions) instead of [Queues](/azure/service-bus-messaging/service-bus-queues-topics-subscriptions#queues).

- [Azure Functions](/azure/azure-functions/) handles data transformations and sends data to the target system.

  - Each system, such as a business solution, needs a dedicated Function App - one for Dynamics 365/Dataverse and one for the target system.

- [Azure Key Vault](/azure/key-vault/) securely stores secrets, keys, and certificates for authentication and encryption.

- [Application Insights](/azure/azure-monitor/app/app-insights-overview) monitors system performance, failures, retries, and other key metrics.

- The target system receives and processes data, and returns a response that includes an integration key.

## Scenario details

This architecture addresses these key requirements:

- Asynchronous data replication with near-real-time acknowledgment

  Data sync uses an asynchronous model for efficient replication to the target system. Near-real-time acknowledgment confirms that the system processes data changes successfully.

- Ensuring the latest snapshot

  To keep data accurate, only the most recent state of a record is sent:

  When a record is created or updated in Dataverse, the system always sends the latest version to the target system.

  An Azure Function gets the current state of the record from Dataverse before sending it. This approach makes sure the system never sends outdated values, so you avoid data inconsistencies.

  This mechanism also makes sure that automatic or manual retries don't overwrite newer data with older snapshots.

- Reliable message delivery

  To make sure the system delivers messages and handles failures gracefully:

  - The system processes messages with automatic retries if there are transient failures.
  - The retry mechanism requeues messages with a delay and a retry count, so failed messages aren't reprocessed right away.
  - If a message fails after multiple retries, the system moves it to the dead-letter queue for manual intervention. This process makes sure no data is lost.

### Potential use cases

The solution was created for a leading global retail organization. You can also apply it to industries such as the following list:

- Finance and banking, where it can help ensure accurate customer and transaction data sync.
- Manufacturing and supply chain, where it can help manage seamless integration of orders, accounts, and inventory data.
- Energy and utilities, where it can help keep data for assets, contracts, and customers in sync across different platforms.
- Retail and e-commerce, where it can help keep information about customers, orders, and fulfillment up to date.

The solution works well for organizations that:

- Need resilient, event-driven data sync with external systems.
- Use asynchronous processing to handle high-volume transactions efficiently.
- Want automated error handling and retry mechanisms to prevent data loss.
- Prefer loosely coupled integrations that don't need continuous monitoring from Dynamics 365 or Dataverse.

## Considerations

These considerations help implement a solution that includes Dynamics 365. Learn more at [Dynamics 365 guidance documentation](/dynamics365/guidance/).

When designing a reliable data sync solution, consider:

- Resilience and fault tolerance  

  Implement retry mechanisms and dead-letter queues to handle transient failures without data loss.
- Data freshness versus latency  

  The system retrieves the latest snapshot, ensuring data accuracy, but might introduce slight processing delays.
- Security and compliance  

  Use managed identities for authentication, enforce role-based access control (RBAC), and store credentials in Azure Key Vault.
- Scalability  

  The solution scales with increasing data volumes, but message retention and queue length should be monitored to avoid performance bottlenecks.
- Monitoring and observability  

  Application Insights provides visibility into failures, retries, and processing times, ensuring efficient troubleshooting.

### Cost optimization

Cost optimization is about looking at ways to reduce unnecessary expenses and improve operational efficiencies. For more information, see [Overview of the cost optimization pillar](/azure/architecture/framework/cost/overview).

#### Cost breakdown

The total cost depends on usage patterns and scales with data volume and message frequency. Key cost-driving components include:

- [Azure Service Bus](https://azure.microsoft.com/pricing/details/service-bus/) uses billed based on message volume, queue size, and retention policies.
- [Azure Functions](https://azure.microsoft.com/pricing/details/functions/) charges per execution and compute duration; consider premium or consumption plans based on expected workload.
- [Application Insights](https://azure.microsoft.com/pricing/details/monitor/) varies logging and telemetry costs with data ingestion rates; optimize by filtering unnecessary logs.
- [Azure Key Vault](https://azure.microsoft.com/pricing/details/key-vault/) costs are tied to secret retrievals and key operations; caching authentication tokens reduces frequent calls.

#### Cost optimization strategies

- Optimize message processing  

  Reduce redundant messages by ensuring to define appropriate triggers.
- Use autoscaling  

  Use Azure Functions' consumption plan to scale dynamically and avoid overprovisioning.
- Filter logs efficiently  

  Configure Application Insights sampling to balance observability and cost.
- Consolidate queues  

  Use topics and subscriptions instead of multiple queues when multiple subscribers are required.

#### Cost estimation

Use the [Azure Pricing Calculator](https://azure.microsoft.com/pricing/calculator/) to estimate costs based on:

- Small scale – Low message volume, fewer function executions.
- Medium scale – Moderate volume, steady message processing.
- Large scale – High-frequency updates, increased retry handling.

Adjust parameters (message count, function execution time, and logging levels) to fit your expected load.

### Scalability Considerations

Scalability is a critical factor in enterprise-grade implementations involving Dataverse and related Azure services. In scenarios with high transaction volumes or bursty workloads (for example, queue-based integrations, bulk data ingestion), failing to plan for scalability can result in performance degradation, data loss, or throttling.

Key considerations and mitigations:

The following outlines common scalability challenges encountered and provides recommended mitigation strategies to ensure resilient and performant implementations.

- Queue growth and message backlogs

  - Use Azure Service Bus Premium with autoscaling message processors (for example, Azure Functions or Azure Container Apps).
  - Implement dead-letter queues (DLQs) and configure retry policies.
  - Monitor queue length and processing lag using Azure Monitor/Log Analytics.

- High volume data processing

  - Break workloads into smaller, manageable batches using scheduled or event-driven patterns.
  - Use parallelism and task partitioning where safe to do so (for example, by record ownership or message correlation ID).

- Out-of-order processing

  - Use session-enabled queues or correlation tokens to preserve message order when required.
  - Ensure idempotency in API logic and message handlers.

- Scaling guidelines

  The following scaling guidelines are intended to help solution architects design robust and future-proof Dataverse implementations that can handle growing workloads, increased user concurrency, and larger data volumes without degrading performance or reliability.

  - Asynchronous operations: Always favor async messaging (for example, queue or event-based processing) to decouple producers and consumers.
  - Autoscaling: Use Azure Functions Premium Plan, Container Apps, or Kubernetes with horizontal pod autoscaling.
  - Monitoring: Enable Application Insights, define alert rules on queue length, execution time, and failure rates.

### Dataverse API limits and mitigation strategies

In high-scale implementations involving Power Platform and Dataverse, it's essential to plan for API consumption proactively. Dataverse enforces both [service protection limits](/power-apps/developer/data-platform/api-limits?WT.mc_id=5004279) (to safeguard the platform against noisy or unbalanced traffic) and [entitlement-based API limits](/power-apps/maker/data-platform/api-limits-overview?WT.mc_id=5004279#entitlement-limits), which are tied to the licenses assigned to users and non-interactive clients. These constraints—if unaccounted for—can lead to throttling, failed operations, or degraded performance, especially in data-intensive or highly automated environments.

To ensure resilient and scalable architecture, teams must understand how these limits apply to their workloads and implement mitigation strategies early in the design phase. The following list outlines key limitations and recommended approaches to handle them effectively:

- Service protection throttling

  - Distribute loads across service principles rather than a single user.
  - Disable Affinity Cookie so Dataverse doesn't use sticky sessions, allowing requests to be load balanced across different front-end servers.
  - Batch requests where possible using XMultiples or Batch APIs.
  - Introduce exponential backoff in custom code and integrations.
  - Use Azure Durable Functions or Logic Apps with delay/retry policies.

- Entitlement limits

  - Monitor consumption with the Power Platform Admin Center and set alerts.
  - Align API-heavy workloads with licensed users or capacity add-ons.
  - If you are approaching or have reached your entitlement limits, contact Microsoft to discuss custom solutions or options for increasing your API capacity.

## Related patterns

The following patterns are available to help guide your implementation.

- [Asynchronous Request-Reply pattern](/azure/architecture/patterns/async-request-reply) lets systems communicate without waiting for an immediate response, so the sender can keep processing.
- [Retry pattern](/azure/architecture/patterns/retry) outlines the approach for designing and implementing effective retry strategies. This pattern provides resilience by automatically reattempting failed operations due to transient errors, network issues, or temporary unavailability of services.

## Related resources

Review the following related architecture guides, solutions, and other guidance content:

- [TechTalk: General guidance for integrating Dynamics 365 apps](../techtalks/integrate-general-guidance.md)
- [TechTalk: Integration patterns for Dataverse](../techtalks/integrate-finance-operations-dataverse.md)
- [Analyze model-driven apps and Dataverse telemetry with Application Insights](/power-platform/admin/analyze-telemetry)
- [Power Platform managed identity overview (preview)](/power-platform/admin/managed-identity-overview)  
- [Azure Service Bus Messaging documentation](/azure/service-bus-messaging/)
- [Azure Monitor documentation](/azure/azure-monitor/)
- [Service Bus queues, topics, and subscriptions](/azure/service-bus-messaging/service-bus-queues-topics-subscriptions)  
- [What is Azure Service Bus?](/azure/service-bus-messaging/service-bus-messaging-overview)  
- [Getting started with Azure Functions](/azure/azure-functions/functions-get-started)
<!-- 
## Tags

*Industries:* Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Administrative, IT, Operations, Production, Sales, Service operations

*Products:* Dynamics 365 Sales, Dataverse, Azure Service Bus, Azure Functions, Azure Key Vault -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Allan De Castro](https://www.linkedin.com/in/allandecastro/) | Dynamics 365 & Power Platform Solution Architect
