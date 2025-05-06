---
title: TechTalk Integration patterns finance and operations apps
description: Summary of TechTalk video that talks about the diverse integration patterns available in Dynamics 365 finance and operations applications.
author: dereklh77
ms.author: edupont
ms.topic: concept-article
ms.date: 10/10/2024
ai-usage: ai-assisted
---

# TechTalk: Integration patterns for Dynamics 365 finance and operations applications

Are you embarking on a journey through the intricate world of Dynamics 365 finance and operations applications? This article delves into the diverse integration patterns available. It offers clarity and direction for businesses and developers navigating the realm of these advanced applications.

We based this article on [a TechTalk](https://youtu.be/tUMEZlEKjEQ?si=Txz75IE8g0TJsyAo) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media\integration-patterns-dynamics365-finance-operations-1.svg" alt-text="Thumbnail of the Integration Patterns for finance and operations applications presentation." link="https://youtu.be/tUMEZlEKjEQ":::

In the dynamic world of business software, integrating various applications is crucial for optimizing workflows, improving efficiency, and maintaining data consistency. The Dynamics 365 finance and operations apps offer robust integration capabilities that allow businesses to connect their operations seamlessly across different platforms. This article explores the integration patterns available in Dynamics 365 finance and operations apps, providing a comprehensive overview of the options and methods that can be employed.

## Understanding integration patterns

Integration with Dynamics 365 finance and operations apps can be broadly categorized into *synchronous* and *asynchronous* methods. Both patterns have distinct use cases and are crucial depending on the business needs. The *synchronous* integration pattern is primarily used for real-time data exchanges, ensuring immediate consistency across systems. In contrast, *asynchronous* integration patterns are better suited for high-volume data processing, where slight delays in data availability are acceptable.

The following image illustrates how the Dynamics 365 finance and operations apps integrate with other systems using key components, such as inventory visibility, MES integration, sensor data intelligence, and the pricing service. It highlights data entities in Dynamics 365, including the Data Management Framework, OData, custom classes, and custom services. The integration uses tools like Business Events, Synapse Link, and various data exchange methods (near real-time, asynchronous, synchronous). The diagram shows how these components work together to manage data flow and integration processes.

:::image type="content" source="media\integration-patterns-finance-operations-overview.svg" alt-text="tekst" lightbox="media/integration-patterns-finance-operations-overview.svg":::

## Synchronous integration - OData and custom services

*OData* (Open Data Protocol) is one of the most common methods for synchronous integration in Dynamics 365 finance and operations apps. It allows developers to perform CRUD (Create, Read, Update, Delete) operations through RESTful web services on data entities. These entities serve as an abstraction layer over the application's business logic, ensuring that all operations respect the business rules and data validation processes. This method is widely used in out-of-the-box integrations, such as the Excel Add-in, and supports secure HTTP connections.

*Custom services* offer another synchronous integration option. These traditional web services, reminiscent of those used in Dynamics AX 2012 and Dynamics AX 2009, are still relevant for transitioning from legacy systems. These services can be developed to expose specific X++ business logic to external applications. While they offer more flexibility, they require a higher level of customization and development effort.

Security is paramount in these integrations, with standard protocols like TLS for encryption and Microsoft Entra ID for authentication and authorization, ensuring that only authorized entities can access the data.

The following image explains the characteristics of OData and Custom Services used for integration. OData provides RESTful web services based on data entities, supporting operations like CRUD-A (Create, Read, Update, Delete, and Actions) and is typically used for modern clients like mobile or web applications. Custom Services offer SOAP and RESTful JSON services, not based on data entities, and expose X++ methods for service operations. Both types of services are limited to HTTPS protocol. The image also mentions metadata services for read-only RESTful access and highlights the importance of considering latency, performance, and security when using synchronous endpoints.

:::image type="content" source="media/integration-patterns-finance-operations-synchronous-endpoints.svg" alt-text="Four boxes that describe the various endpoints as explained before the image." lightbox="media/integration-patterns-finance-operations-synchronous-endpoints.svg":::

## Asynchronous integration with the data management framework

The Data Management Framework (DMF) in Dynamics 365 supports asynchronous integration, ideal for handling large data volumes. DMF provides two key capabilities: Package APIs and Recurring Integration APIs. Package APIs are used for importing and exporting data in bulk, making them suitable for high-volume operations. Recurring Integration APIs, on the other hand, allow for scheduled data imports and exports, providing flexibility in managing data synchronization without manual intervention.

For both synchronous and asynchronous integrations, it's crucial to consider the performance and volume of transactions. Dynamics 365 Finance and Operations is optimized for low latency but can experience performance issues under high transaction loads. Proper planning and testing are essential to ensure that the chosen integration method meets the business requirements without compromising system performance.

## Event-driven architecture with business events and data events

Event-driven integration patterns are becoming increasingly popular in modern enterprise applications, and Dynamics 365  supports this through business and data events. Business events are triggered by specific processes in Dynamics 365, such as posting a customer invoice or completing a sales order. These events can be captured and processed by external systems using services like Azure Event Grid or Logic Apps, enabling real-time integration across different platforms.

Data events, on the other hand, are triggered by changes to data entities, such as creating, updating, or deleting records. These events provide a payload containing the data that was changed, allowing external systems to react to these changes in near real-time. However, developers should be cautious when using data events, especially for update operations, as they can be more resource-intensive compared to other types of events.

Business events facilitate process integration between Finance & Supply Chain Management and external systems in a decoupled manner. There are three main components:  

1. Events  

    1. Application events
    2. Workflow events
    3. Alert events  
2. Cloud endpoints  

    1. Event Grid, Event Hub, and Service Bus
    2. Power Automate and Logic Apps
    3. HTTPS and Azure Data Lake  
3. Use cases  

    1. Integration  
    2. Workflow  
    3. Notifications  

These small, configurable, and customizable messages are defined at the process step level and enable seamless integration across various platforms and services.

## Hybrid integration scenarios

In scenarios where organizations have on-premises systems that need to integrate with Dynamics 365, hybrid integration patterns become essential. Tools like Azure Data Gateway and Azure Relay provide secure ways to bridge the gap between on-premises data and cloud applications without compromising security. These tools allow for seamless data exchange while maintaining strict access controls and minimizing the need for exposing sensitive data directly to the internet.

Azure API Management is another powerful tool for managing both on-premises and cloud APIs. It offers a unified platform to expose, secure, and manage APIs, providing a structured approach to hybrid integration. This is particularly useful for organizations looking to standardize their integration strategy across multiple environments.

### Specialized integration services

Dynamics 365 finance and operations apps also offer specialized integration services tailored for specific business needs. For instance, the Inventory Visibility service provides real-time tracking across multiple data sources, ensuring that inventory data is accurate and up-to-date across all channels. The Manufacturing Execution System (MES) integration allows for real-time synchronization between MES and Finance and Operations, ensuring that production data is always current in both systems.

For organizations looking to integrate IoT signals with their supply chain processes, the Sensor Data Intelligence service (currently in preview) offers a way to leverage real-time data from production machines and equipment. This enables predictive maintenance and more accurate operational planning, reducing downtime and improving efficiency.

### Conclusion

Integration is a critical component of modern enterprise applications, and Dynamics 365 Finance and Operations provides a wide range of patterns and tools to meet various business needs. Whether through synchronous OData services, asynchronous DMF integrations, or advanced event-driven architectures, businesses can find the right integration approach to ensure seamless data flow across their systems. By leveraging the power of Azure and other Microsoft services, organizations can build robust, scalable, and secure integrations that enhance their operations and drive business success.

For more information on the integration patterns discussed, visit the official Microsoft [Dynamics 365 documentation](/dynamics365/fin-ops-core/dev-itpro/data-entities/integration-overview).

<!-- ----

## Exploring synchronous integrations

:::image type="content" source="media\integration-patterns-dynamics365-finance-operations-2.svg" alt-text="A visual overview for integration components, showing the map of finance and operations Apps and Dataverse options." lightbox="media\integration-patterns-dynamics365-finance-operations-2.svg":::

In the realm of Dynamics 365, synchronous integrations stand out for their ability to provide real-time data exchanges. Key to these integrations is the OData RESTful Web Service, widely used for standard integrations such as the Excel Add-in. This service functions as an abstraction layer, enabling Create, Read, Update, Delete operations, and business logic actions. Alongside this, Custom Services play a crucial role, particularly in transitioning from older Dynamics versions. These services, available in SOAP/XML and RESTful/JSON formats, cater to the need for real-time data interaction.

## The world of asynchronous integrations

:::image type="content" source="media\integration-patterns-dynamics365-finance-operations-3.svg" alt-text="A spreadsheet and diagram that outlines D M F package A P I s, including the process for importing A P I s." lightbox="media\integration-patterns-dynamics365-finance-operations-3.svg":::

Asynchronous integrations in Dynamics 365 cater to scenarios where immediate response isn't critical, mainly handling large data volumes. The Data Management Framework (DMF) within these applications offers robust tools for both data import and export. This framework supports various data formats and protocols, making it a versatile choice for asynchronous data handling. Complementing the DMF is the Events Framework, which enables applications to react to various triggers through business and data events. This framework is integral in orchestrating efficient integration across various business processes.

## Hybrid solutions and advanced services

:::image type="content" source="media\integration-patterns-dynamics365-finance-operations-4.svg" alt-text="A description and illustration for Azure Synapse Link and finance and operations applications." lightbox="media\integration-patterns-dynamics365-finance-operations-4.svg":::

Beyond the standard integration patterns, Dynamics 365 finance and operations also embrace hybrid solutions. These solutions blend the functionalities of on-premises systems with cloud capabilities, offering a comprehensive approach to modern business needs. Furthermore, advanced services like Azure Synapse Link enhance the integration capabilities, especially in areas such as analytics and data warehousing. Such services are instrumental in facilitating a seamless flow of information across different platforms and systems.

## Conclusion

The integration patterns within Dynamics 365 finance and operations are a testament to the application's versatility and capability to address specific business needs. From facilitating real-time interactions to managing extensive data sets, these patterns ensure a seamless and efficient operational workflow. For those seeking in-depth guidance and insights, the Dynamics 365 TechTalk community page serves as a valuable resource, complete with detailed explanations and demonstrations. -->

## Related information

You can use the following resources to learn more about Dynamics 365.

- [TechTalk: General guidance for integrating Dynamics 365 apps](integrate-general-guidance.md)  
- [TechTalk: Integration patterns for Dataverse](integrate-finance-operations-dataverse.md)  
- [TechTalk: Set up business-to-business digital selling with Dynamics 365](set-up-dynamics-365-digital-selling.md)
- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)  
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/) 
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)  
