---
title: Choose the right design for your Dynamics 365 apps integration strategy
description: Find guidance on how to choose the right design for your Dynamics 365 apps integration strategy.
author: abunduc-ms
ms.author: abunduc
ms.date: 05/25/2023
ms.topic: conceptual

---
# Choose the right design for your Dynamics 365 apps integration strategy

Many factors influence the choice of patterns for your integration. Integration scenarios can be grouped roughly into three kinds: UI, data, and process integration. While there's some degree of gray area and overlap between them, there are also some distinct characteristics and expected behaviors.

## UI integration

In UI integration, the primary point of integration is centered around an action that's performed on the UI. The integration might or might not trigger business logic or cause anything to be written to the system. UI integration creates a seamless user experience even though the data and process might exist in separate systems, as shown in the following example.

:::image type="content" source="media/integrate-other-solutions-ui-integration.png" alt-text="UI integration" lightbox="media/integrate-other-solutions-ui-integration.png":::

In this figure, an order taker at a company works in the Sales system to take an order from a customer, and in that process the order taker looks at real-time information from an ERP system.

The UI integration allows the order taker to answer the customer's inquiries accurately and immediately without switching systems. The information might or might not be used for the order-taking process.

The simplest form of UI integration is when a widget, canvas app, or view from one system is embedded in another system without touching the business logic or data of that system. This way, users can focus on their tasks, such as scheduling interviews with job applicants, or providing services to customers. They no longer have to switch between several LOB systems. Sometimes values can be passed from the hosting system to the hosted system to provide session context from one system to the other.

The following are other examples of UI integration:

- Commodity price ticker; an email view

- On-hand inventory

- Embedded Power BI dashboard showing the current day's production quality issues in a manufacturing plant

A key characteristic of UI integration design is that it's embedded.

The benefit of UI integration is that a user can retrieve and provide real-time information from multiple sources without switching between systems. As a result, the organization saves on training, user licenses, and more importantly, time when interacting with customers.  

## Data integration

Data integration is integration between systems that takes place at the data layer, and data is exchanged or shared between systems. Data integration is different from process integration. With data integration, both systems work with a representation of the same data. In process integration, the process starts in one system and continues in the other system.

:::image type="content" source="media/integrate-other-solutions-data-integration.png" alt-text="Data integration" lightbox="media/integrate-other-solutions-data-integration.png":::

We use data integration patterns in the following scenarios.

- Master data or transactional data that isn't the central part of a single, continuous business process is synchronized between a process in one system to a process in another system.

- Data is shared or exchanged between systems when needed for calculations, classifications, or references.

- Data is shared or exchanged between systems so that actions that happen in one system are reflected in the other system.

- Aggregate data from a system with a detailed level of data is exchanged to a system with a higher level representation of data.

The following are examples of data integration:

- Aggregate marketing data assets

- Bank account reconciliation

- Order status updates

- Exchange rate updates

- Postal code and city list synchronization

- Accounts and customer data synchronization

Keep in mind that often data doesn't originate from a system within your own organization; it can come from an external source to upload. Conversely, data might be extracted from your system to be sent to an auditor, a regulatory body, or an industry data exchange.

In the next example, orders are synchronized between a Sales and an ERP system. When the order is created in Sales, the ERP system sends regular updates of the order data to Sales, which enables users to find accurate order status information.

:::image type="content" source="media/integrate-other-solutions-data-integration-2.png" alt-text="Data integration example" lightbox="media/integrate-other-solutions-data-integration-2.png":::

In many areas of Dynamics 365, admins or business users can switch on data integration easily. Examples include integration with Microsoft Teams, journal uploads for expenses or bank account statements, exchange rate synchronization, and features for regulatory reporting and extracts.  

When designing data integration, you should consider which system is the system of record, or owner, of the information. There are scenarios in which this is clear cut. For example, when you want to upload worker data from Dynamics 365 Human Resources to Dynamics 365 Finance, the Human Resources app is the system of record.  

But there are also scenarios where each system owns a separate part of the overall entity. For example, when you integrate Accounts to Customers between Dynamics 365 Sales and Dynamics 365 Finance, the Sales app is the owner of the basic information. But in this scenario, that information is just a small subset of the fields in the Customer entity in Finance.

Another type of data integration, is when two systems share the data layer, so updates to one system are instantly reflected in the other system. This is possible with cross app integration with Dynamics 365 apps and Dataverse.

:::image type="content" source="media/integrate-other-solutions-data-sharing.png" alt-text="Data integration sharing example" lightbox="media/integrate-other-solutions-data-sharing.png":::

First-party model-driven applications, such as Dynamics 365 Sales, Field Service, and custom Power Apps, all share the same data layer. That's true, even if applications are built and deployed separately.

With Dataverse, you can also integrate customer engagement apps with finance and operations apps. This integration gives you a seamless experience between the Sales system and the ERP system.

Systems may have separate processes and even different business logic. But if the underlying data layer is the same, the need for transfers of data, synchronization, and programming to transform the data is eliminated. This kind of integration is possible due to shared data stores, such as Dataverse, that set standards for how a certain type of data is defined in the data layer.

## Process integration

Process integration refers to when a business process is designed to span multiple systems. There are many varieties of process integrations, such as a plan-to-produce workflow where production forecasting or block scheduling occurs in a Production Scheduling System. The rest of the manufacturing and supply chain management process (production, order management, and fulfillment) and the billing process occur in an ERP system.

A key characteristic of process integration design is that it's event driven.

The benefits of process integration are accuracy, efficient timing of information and activities in the organization, and reduction of manual errors.

:::image type="content" source="media/integrate-other-solutions-process-integration.png" alt-text="Process integration" lightbox="media/integrate-other-solutions-process-integration.png":::

In this scenario, the business process spans two systems. The user in the Production Scheduling System creates and maintains the production schedule. That action initiates the business logic to procure, produce, and reserve the order in the ERP system for later picking and shipping. Maybe a user must take action in the ERP system, but essentially the rest of the business process steps are handled either automatically or by the appropriate users in the ERP system.

Process integration can span multiple systems and often requires batched, scheduled, and sometimes near real-time integration.

In the example shown, without the integration part, orders would have to be manually created twice, increasing time and risking errors such as typos and missed updates.

## Integration frameworks

Let's now discuss some of the common services available across Power Platform and Azure that can help in designing a dynamic, scalable solution.

With Dataverse, you can use Power Platform to integrate apps. You should consider several components and features of Azure and Power Platform when designing an overall solution as well as individual integration.

### Power Automate

Power Automate provides low-code/no-code solutions to help you automate workflows and build integration between various applications. Power Automate automates repetitive and manual tasks and seamlessly integrates Dynamics 365 apps inside and outside Power Platform.

In fact, Power Automate has connectors to more than 400 specific applications and technologies in the [Azure Connectors ecosystem](/connectors/connector-reference/connector-reference-logicapps-connectors) and a vast selection of integration samples to start from, all with the goal of helping users to be more productive. Power Automate is available to Office 365 users who have the appropriate license and access.

Power Automate also provides automation of receiving and extracting data from documents used in workflows.

For more information, read about [Power Automate](/dynamics365/fin-ops-core/dev-itpro/business-events/home-page) and [What is Microsoft Dataverse?](/power-apps/maker/data-platform/data-platform-intro)

## The right tools

In addition to the power platform components, Azure provides designers with a rich, scalable feature set and user-friendly design elements and the option to build more complex integration solutions. Developers can use tools including Visual Studio, Visual Studio Code, and Azure DevOps.

Power Platform and Azure together can handle integration requirements from simple scenarios to enterprise architecture scenarios. The following subsections describe the integration services that are provided with Azure integration services. Together or individually these services provide vast possibilities for tailoring integration solutions—often using predefined connectors and visual orchestration with the capabilities of adding complex logic through code if needed. Azure Integration services allow you to focus on the business process and business logic instead of the traditional hassle of compatibility and making connections work.

### Azure Logic Apps

Azure Logic Apps are the next step in integration capabilities for more challenging integration scenarios than what you can do with power automate and the low-code/no-code option. It's a cloud-based platform that uses the same connector ecosystem so that developers can develop highly scalable automation of workflows that span services, apps, and systems, both cloud-based and on-premises. It's important to know that with the definition of a middleware, Azure Logic Apps alone doesn't provide the alerting, notification, monitoring, and messaging management capabilities that we recommend for a middleware.

### Azure Functions

Azure Functions uses serverless architecture and can be used to extend business logic, including calling external applications. It runs in Azure and operates at scale. Azure Functions can be called through Power Automate and Azure Logic Apps. For more information, read about [Azure Functions](https://azure.microsoft.com/products/functions/#overview) and [Using Azure Functions in Power Apps](https://powerapps.microsoft.com/blog/using-azure-functions-in-powerapps/).

### Service Bus

Service bus is the cloud messaging service in Azure. It provides asynchronous messaging patterns for integration between applications and services, for example Azure SQL, Azure Storage, Dataverse, and Dynamics 365 Apps under a scalable and durable operation. Azure service bus also connects on-premises applications with cloud services.

Azure service bus provides the framework for a robust, queue centric messaging service across technologies and topologies, even in offline fail scenarios. With other Azure service, such as Logic Apps and Azure Monitoring, this is the Azure based middleware platform. <!--See the links below this section for additional information.-->

### Azure API Management

When an organization has multiple systems, cloud or on-premises, they typically each have APIs that expose some of their functionality. Azure API management allows you to manage APIs in a structured manner in terms of service protection, authentication, caching, monitoring and statistics and developer documentation and samples.

API Management works as a proxy for the real APIs so that the underlying technology of the individual API is irrelevant. It can even sit on top of other Azure services, for example, Azure Service Bus and Logic Apps and third party apps and services.

The typical scenario for using API management is to apply management to all the APIs in the organization that aren't already controlled by Azure Active Directory and Oauth authentication. It basically allows the organization to make all, even non-Microsoft platform, APIs behave the same from an API management and security perspective.

The control aspect of API Management allows for restriction of number of calls, or specific IP addresses and other service protection features.

### Event Grid

Event grid adds another level of integration capabilities. Instead of having an application or a messaging service request new messages at recurring intervals, Azure Event Grid allows a receiving system to register event handlers for events that they need to react to. When the registered event occurs, the event handler is then invoked.

Event Grid is often used with Azure Service Bus and logic apps. For example, the arrival of a specific message type could be an event that kicks off a certain business process in an integrated application or run a workflow in a service.

An example of the use of Event Grid with a Logic App is to kick off a process in a Dynamics 365 app that imports the content of an Excel sheet (the automated workflow) when the sheet is uploaded to Azure Blob Storage (the event).

### Azure Data Factory

Data Factory is a big data, analytics centered service for ETL. It provides vast capabilities for visual authoring of extraction and transformation through the concept of ADF Pipelines, monitoring and use of services such as machine learning monitoring.

Azure Data Factory provides a code-free, serverless data integration service to seamlessly orchestrate ETL (extract, transform, and load) and ELT (extract, load, and transform) operations with disparate big data sources. It can ingest data from Dynamics 365 using the web API endpoints as well as structured and unstructured data between cloud services in Azure or other public clouds or on-premises data stores.

We recommend that you consider platform and service protection limits as well as Azure costs when using all of these services.

For more information about each of these Azure services, see [Azure Integration Services](https://azure.microsoft.com/products/category/integration/).
<!--Seems like obsolete info>
For information about how all of these services can work together, read this whitepaper on Azure Integration Services
-->
## Next steps

- [Define business goals](integrate-other-solutions-business-goals.md)  
- [Choose a platform](integrate-other-solutions-choose-platform.md)  
- [Choose a pattern](integrate-other-solutions-choose-pattern.md)  
- [Challenges](integrate-other-solutions-challenges.md)  
- [Product-specific guidance for integration scenarios](integrate-other-solutions-guidance-product.md)  
- [Checklist](integrate-other-solutions-checklist.md)  
- [Case study](integrate-other-solutions-case-study.md)  
