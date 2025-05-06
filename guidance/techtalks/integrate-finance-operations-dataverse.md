---
title: TechTalk Integration patterns for Dataverse
description: Summary of TechTalk video that talks about the various facets of integrating Dataverse and Dynamics 365 finance and operations apps.
ms.topic: concept-article
author: edupont04
ms.author: raprofit
ms.date: 10/10/2024
ai-usage: ai-assisted
# CustomerIntent: As a partner, I want to learn if I should watch the recording.
---

# TechTalk: Integration patterns for Dataverse

In this article, we explore the various patterns and tools available for both inbound and outbound data integrations within Dataverse, examining the best practices and considerations for each.

We based the article on [a TechTalk](https://youtu.be/CFG1EpPuFRs) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/integration-patterns-dataverse-slide.svg" alt-text="Introductory slide from the TechTalk presented by Corina Balan and Michele Mazzucco from the FastTrack team." link="https://youtu.be/CFG1EpPuFRs":::

<!-- > [!VIDEO https://www.youtube.com/embed/CFG1EpPuFRs?si=CTxwasdR8jWT6SLD] -->

## Overview

Dataverse is a key component of the Power Platform that provides extensive capabilities for integrating data from various sources, enabling a seamless flow of information across systems. Understanding the different integration patterns available within Dataverse is crucial for designing effective and efficient solutions, particularly when integrating with external systems or applications.

The following illustration shows the architecture for integrating Dynamics 365 finance and operations apps with Dataverse. It shows various components such as Event Grid, Service Bus, Azure Function, and Power Automate that facilitate integration. The diagram highlights data flow between finance and operations apps and Dataverse using tools like Dual Write, OData/Web API, and Business Events. Different integration types, including near real-time, asynchronous, and synchronous, are indicated, along with their associated processes like electronic reporting and invoice capture. This overview illustrates the comprehensive integration setup between systems, ensuring seamless data exchange and process synchronization.

:::image type="content" source="media/integration-patterns-dataverse-overview.svg" alt-text="Diagram that shows Dynamics 365 and Dataverse components." lightbox="media/integration-patterns-dataverse-overview.svg":::

The rest of this article digs into the integration mechanisms and Dataverse as indicated by the red squiggly line in the diagram.

## Inbound integration - bringing data into Dataverse

When integrating data into Dataverse from external sources, several approaches can be considered, depending on the specific requirements of the project. The most direct approach is to write custom code to interact with Dataverse's API. Developers have two primary options here:

1. **Organization service**  

   This service defines all operations supported by the platform as messages, accessible via .NET code through the provided SDK.

2. **Web API**  

    This RESTful service exposes the same operations, which can be consumed via HTTP methods, using OData for defining functions and actions.

Alternatively, you can implement a low-code/no-code approach using components in the Power Platform or Azure. Tools such as **Power Automate** and **Logic Apps** offer extensive integration capabilities through pre-built connectors, allowing data to flow into Dataverse with minimal custom coding.

**Power Automate** is useful for orchestration of events and is included in many Power Platform and Dynamics 365 offerings. **Logic Apps**, while similar in functionality, is more suited for professional development and is deployed as an Azure resource, offering greater control and flexibility.

For scenarios where data doesn't need to be physically imported into Dataverse, real-time data embedding via **virtual tables** or custom UI components can be an effective strategy. This approach allows external data to be accessed on demand without the overhead of continuous data importation.

The following image outlines three key methods for integrating data into Dataverse. These include using **Dataverse APIs** like the Organization Service and Web API for development and operations, **Dataverse connectors** such as Power Automate and Logic Apps for low-code/no-code integration, and **UI integration** methods like Virtual Tables and Custom Controls for embedding external data and customizing the user interface. The options offer flexibility in how data is integrated and managed within Dataverse.

:::image type="content" source="media/integration-patterns-dataverse-inbound.svg" alt-text="Outlines three key methods for integrating data into Dataverse as described before the image." lightbox="media/integration-patterns-dataverse-inbound.svg":::

## Outbound integration - exporting data from Dataverse

Outbound integrations in Dataverse involve sending data from Dataverse to external systems. Outbound integration are useful when events in Dataverse must trigger actions in other systems. There are several tools and methods available for this scenario:

1. **Plugins**  

    Plugins can call external web services or post runtime context to Azure services like Service Bus or Event Hubs, providing a robust mechanism for extending Dataverse's capabilities.

2. **Webhooks**  

   A lightweight HTTP pattern, webhooks allow for real-time, event-driven integration with external systems. They're useful for scenarios where low latency is required and the external system can handle a high volume of messages.

3. **Azure Synapse Link for Dataverse**  

   This service is ideal for integration scenarios with batch data, allowing for the continuous export of data from Dataverse to Azure Synapse Analytics and Azure Data Lake Storage. This is beneficial for analytics, business intelligence, and machine learning applications.

The following image outlines methods for exporting data from Dataverse. It includes event-driven integration using plug-ins, webhooks, and business events; scheduled integration via Power Automate and Logic Apps; and batch processes like Azure Synapse Link for continuous data export and change tracking for delta updates. These approaches offer flexible ways to manage data flow from Dataverse to other systems.

:::image type="content" source="media/integration-patterns-dataverse-outbound.svg" alt-text="Outlines methods for exporting data from Dataverse as described before the image." lightbox="media/integration-patterns-dataverse-outbound.svg":::

**Dataverse Business Events** also offer a powerful mechanism for asynchronous integration, enabling developers to respond to specific events in Dataverse without the need for continuous polling or complex custom logic.

## Best practices and considerations

When deciding on the best integration pattern, several factors should be considered, including the complexity of the integration, the volume of data, the need for real-time processing, and the existing infrastructure.

- **Custom code versus low-code**  

   Evaluate whether custom development is necessary or if a low-code solution via Power Automate or Logic Apps will suffice. Custom code offers greater flexibility but comes with increased complexity and maintenance requirements.

- **Security and compliance**  

   Ensure that data handling complies with security policies, particularly when dealing with sensitive information. Using managed identities and secure configurations can help mitigate security risks.

- **Scalability**  

   Consider the scalability of the solution, particularly in scenarios involving large volumes of data or high-frequency transactions. Azure services like Service Bus provide robust mechanisms for scaling integrations.

- **Performance**  

   For real-time integrations, consider the latency of the chosen approach. Synchronous operations, while immediate, may introduce performance bottlenecks if not carefully managed.

For those looking to implement or optimize Dataverse integrations, understanding these patterns and tools is essential. By carefully selecting the right approach for your specific needs, you can ensure that your integration solutions are both effective and scalable, supporting your broader business goals.

Learn more at [What is Microsoft Dataverse?](/power-apps/maker/data-platform/data-platform-intro).

This article has provided a high-level overview of the key integration patterns available for Dataverse, with practical insights into when and how to use them. Whether you're a developer looking to implement complex integrations or a business analyst seeking to streamline data flows, these patterns serve as a valuable guide in your Dataverse journey.

### Related resources

You can use the following resources to learn more about Dynamics 365.

- [TechTalk: General guidance for integrating Dynamics 365 apps](integrate-general-guidance.md)  
- [TechTalk: Integration patterns for Dynamics 365 finance and operations applications](integrate-finance-operations-overview.md)  
- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
