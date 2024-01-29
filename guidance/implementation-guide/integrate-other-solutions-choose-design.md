---
title: Choose the right design for your Dynamics 365 apps integration
description: Learn how to choose the best design for your Dynamics 365 apps integration strategy.
author: abunduc-ms
ms.author: abunduc
ms.date: 01/25/2024
ms.topic: conceptual
ms.custom:
  - ai-seo-date: 01/25/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Choose the right design for your Dynamics 365 apps integration

When integrating your Dynamics 365 applications, you'll encounter various factors that influence your choice of patterns. Integration scenarios generally fall into three categories: user interface (UI), data, and process integration. While there's some overlap between them, each has distinct characteristics and behaviors.

## UI integration

UI integration focuses on actions that are performed within the user interface. It might or might not trigger business logic or record data in the system. The goal is to create a seamless experience for users, even when data and processes exist in separate systems. For example, an order taker in a sales system might access real-time information from an enterprise resource planning (ERP) system to respond to customer inquiries without switching apps.

The simplest UI integration involves embedding a widget or app from one system into another without affecting the hosted system's business logic or data. This approach allows users to concentrate on tasks like scheduling interviews or providing customer service without juggling multiple systems.

UI integrations can include elements like a commodity price ticker, inventory levels, or an embedded Power BI dashboard that displays production quality issues. A key feature of UI integration is that it's embedded, which saves time and reduces the need for training and user licenses.

## Data integration

Data integration occurs at the data layer, with information exchanged or shared between systems. Unlike process integration, where a process starts in one system and continues in another, data integration involves both systems working with a representation of the same data.

Scenarios for data integration include synchronizing master or transactional data that isn't central to a single business process, sharing data for calculations or references, and reflecting actions from one system in another. Examples range from synchronizing marketing assets and bank account reconciliations to updating order statuses and exchange rates.

Data might originate externally or be extracted from your system for auditing or regulatory purposes. For instance, orders that are synchronized between a sales and an ERP system allow users to access accurate order status information.

When designing data integration solutions, it's crucial to identify which system owns the information. Sometimes ownership is clear-cut, as when you're uploading worker data from Dynamics 365 Human Resources to Dynamics 365 Finance. The Human Resources app is the system of record. Other times, each system might own different parts of the overall entity. For example, when you integrate accounts to customers between Dynamics 365 Sales and Finance, the Sales app owns the customer name and contact information, while the Finance app owns the credit limit and payment terms.

Cross-app integration with Dynamics 365 apps and Dataverse allows two systems to share a data layer, instantly reflecting updates in both systems. This eliminates the need for data transfers and transformations, thanks to shared data stores, like Dataverse, that standardize how data is defined in the data layer.

## Process integration

Process integration designs business processes that span multiple systems. It can vary widely, such as a plan-to-produce workflow that starts in a production scheduling system and continues through manufacturing and billing processes in an ERP system.

This type of integration is event-driven. It enhances accuracy and timing of information and activities, and reduces manual errors. For example, a user creating a production schedule in one system can trigger procurement and production processes in another system without manual duplication of orders.

## Integration frameworks

Power Platform and Azure offer services that support dynamic and scalable solutions for various integration challenges.

### Power Automate

Power Automate provides low-code/no-code workflow automation and app integration within and outside Power Platform. It connects to more than 400 applications through [Azure Connectors](/connectors/connector-reference/connector-reference-logicapps-connectors) and offers numerous integration samples to start from. Power Automate is available to Office 365 users who have appropriate licenses.

### Azure Logic Apps

Azure Logic Apps provides advanced integration capabilities beyond Power Automate's low-code/no-code options. It uses the same connector ecosystem to automate workflows across services, apps, and systems. Azure Logic Apps alone doesn't provide the alerting, notification, monitoring, and messaging management capabilities that we recommend for a middleware. However, it can be used with Azure Service Bus to provide these capabilities.

### Azure Functions

[Azure Functions](https://azure.microsoft.com/products/functions/#overview) offers serverless architecture for extending business logic and calling external applications at scale. It can be triggered through Power Automate and Azure Logic Apps. [Learn how to use Azure Functions in Power Apps](https://powerapps.microsoft.com/blog/using-azure-functions-in-powerapps/).

### Service Bus

Azure Service Bus is a cloud messaging service that facilitates asynchronous messaging patterns for application integration. It provides a robust messaging framework that operates reliably even during offline scenarios.

### Azure API Management

Azure API Management manages APIs by offering service protection, authentication, caching, monitoring, documentation, and sample management. It acts as a proxy for APIs from various systems.

### Event Grid

Azure Event Grid allows systems to register event handlers for specific events instead of polling for new messages periodically. It can be used with Azure Service Bus and Logic Apps to trigger processes based on events.

### Azure Data Factory

Azure Data Factory is a big data service focused on ETL (extract/transform/load) operations. It orchestrates data extraction and transformation visually while providing monitoring and machine learning capabilities.

When you use these services, we recommend that you consider platform and service protection limits and Azure costs.

[Learn more about Azure Integration Services](https://azure.microsoft.com/products/category/integration/).

## Next steps

- Discover the integration patterns available with Dynamics 365 apps and what factors to consider when [choosing a pattern](integrate-other-solutions-choose-pattern.md)
- Find out what challenges you might face when integrating systems and how to overcome them with [best practices](integrate-other-solutions-challenges.md)
- Learn about the aspects that are specific to each Dynamics 365 app and how to [integrate them with other solutions](integrate-other-solutions-guidance-product.md)
- Use this Solution by Design [checklist](integrate-other-solutions-checklist.md) to make sure you've covered all the steps and considerations for your integration project
- Read how a public sector infrastructure organization learned how to [choose the right solution for their integration project](integrate-other-solutions-case-study.md)
