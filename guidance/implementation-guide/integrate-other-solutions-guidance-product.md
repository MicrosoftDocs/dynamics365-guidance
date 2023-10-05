---
title: Product-specific guidance for integration scenarios
description: Find guidance on the aspects specific to the individual Dynamics 365 apps, in terms of integration strategy.
author: abunduc-ms
ms.author: abunduc
ms.date: 05/23/2023
ms.topic: conceptual

---

# Product-specific guidance for integration scenarios

The following sections discuss specific integration-related considerations for the different groups of apps in Dynamics 365. There are different approaches for finance and operations apps and for customer engagement apps. We also provide examples for cross-app integration between Dynamics 365 apps.

## finance and operations apps

Many ways of integrating into and from finance and operations apps use an abstraction layer with integration and data migration capabilities that shield users, administrators, and developers from the heavily normalized database. This abstraction layer consists of data entities.

### Data entities

In finance and operations apps, a data entity encapsulates a business concept, for example, a customer or sales order line, in a format that makes development and integration easier. It's a denormalized view where each row contains all the data from a main table and its related tables. The normalized data model behind it's a more complex view.

Said another way, data entities provide conceptual abstraction and encapsulation, a denormalized view of what's in the underlying table schema to represent key data concepts and functionality. There are more than 2,000 out-of-the-box data entities.

Data entities help encompass all the table-related information and make the integration, import, and export of data possible without the need to pay attention to the complex normalization or business logic behind the scenes. For more information, see the [Data entities overview](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities).

The out-of-the-box data entities are general purpose entities built to support a wide variety of features surrounding a business entity. For implementations in which a high-volume, low-latency interface is required, it's recommended to build custom data entities with the necessary targeted and specific features.

You can replicate an out-of-the-box data entity and remove any fields and logic around features not used by your organization to create a highly performant interface.

### Integration patterns for finance and operations apps

The following table is a list of integration patterns with pattern descriptions, pros and cons, and use cases.

| Pattern | Mechanism | Trigger | Considerations | Use when |
|-------------------------|-------------------------|-------------------------|-------------------------|-------------------------|
| OData | Data is exchanged synchronously, invoking actions using RESTful web services and the HTTP protocol stack.</br>All data entities are marked public, and CRUD operations are mapped. | User actions and system events. | Pros: It allows developers and service platforms to interact with data by using RESTful web services.</br>It provides a simple and uniform way to share data in a discoverable manner. It enables broad integration across products.</br>Cons: The pattern is synchronous and subject to Service Protection limitations and throttling. Cold start might be slow. | Use with messaging services and point-to-point integration.</br>Inbound (Push) or outbound (Pull) of datasets from entities when the volume and payload are relatively low. |
| Custom Services—SOAP, REST, and JSON | A developer can create external web services by extending the application with X++. Endpoints are deployed for SOAP, REST, and JSON. | User actions and system events. | Pros: Easy for developers to add and expose service endpoints to use with integration platforms.</br>Cons: Requires ALM and SDLC for coding and deployment of extensions into finance and operations apps. The payload is low compared to other patterns. | Used when invoking an action or update, for example, invoicing a sales order or returning a specific value. We recommend using REST Custom Services in general because it's optimized for the web.</br>REST is preferred for high-volume integrations because there's reduced overhead compared to other stacks such as OData. |
| Consuming web services | A developer can consume external web services by adding a reference in X++. | Scheduled and user initiated. Can wait for off hours or idle time. | Pros: Easy for developers to add and expose service endpoints to use with integration platforms.</br>Cons: Requires ALM and SDLC for coding and deployment of references into finance and operations apps. The payload is low. Risk of hardcoding connection strings and credentials in related code. Maintenance workloads and risks when the service is updated. | Use when consuming services from other SaaS platforms or products, for example, commodity tickers and lookups of real-time values.</br>The recommended pattern is to use Power Automate instead when possible. |
| Data Management Framework REST Package API (asynchronous, batched, cloud, or on-premises) | The REST API helps integrate by using data packages. | Originating system users or system events. | Pros: On-premises and large-volume support. The only interface that supports change tracking.</br>Cons: Supports only data packages. | Large-volume integrations. Scheduling and transformations happen outside finance and operations apps. |
| Recurring Data Management integration REST API (asynchronous, cloud, or on-premises) | With the Data Management REST API, you can schedule the recurring integration of files and packages. Supports SOAP and REST. | Receiving system requests based on the schedule. | Pros: On-premises and large-volume support. Supports files and packages. Supports recurrence scheduled in Finance and transformations (XSLT) if the file is in XML.</br>Cons: None. | Large-volume integrations of files and packages. Scheduling and transformations happen inside finance and operations apps. |
| Electronic Reporting | A tool that configures formats for incoming and outgoing electronic documents in accordance with the legal requirements of countries or regions. | Data state, system, or user events. | Pros: Data extracts and imports are configurable in finance and operations apps. It supports several local government formats out of the box. It can be scheduled for recurrence.</br>Cons: Comprehensive configuration when used for messaging purposes. | Electronic reporting to regulatory authorities and similar entities. |
| Excel and Office integration | Microsoft Office integration capabilities enable user productivity. | Data state, system, or user events. | Pros: Out-of-the-box integration (export and edit) on almost every screen in the product.</br>Cons: Performance decreases with the size of the dataset. | Extracts for unplanned reporting or calculations.</br>Fast editing of column values and entry of data from manual sources.</br>Import of journal records such as general journals, expenses, and bank statements and similar transactional data. |
| Business events | Business events provide a mechanism that lets external systems, Power Automate, and Azure messaging services receive notifications from finance and operations apps. | User or system events. | Pros: Provides events that can be captured by Power Automate, Logic Apps, and Azure Event Grid.</br>Cons: Extensions are needed to add custom events. | To integrate with Azure Event Grid, Power Automate, or Logic Apps. To notify of events inherently driven by a single data entity, for example, an update of a document or a pass or fail of a quality order. |
| Embedded Power Apps (UI) | finance and operations apps support integration with Power Apps. Canvas apps can be embedded into the finance and operations apps UI to augment the product's functionality seamlessly with Dataverse. | Users. | Pros: Seamlessly integrates information from Dataverse without integrating the backend. Opens opportunities for low-code/no-code options directly into the finance and operations apps UI without the need for updates and compatibility.</br>Cons: Power Apps and related artifacts aren't deployed with the build and must be configured in the environment directly. Separate ALM stories for Power Apps. | Whenever the required data exists in Dataverse and is loosely coupled with finance and operations apps.</br>Using an app embedded in the UI provides a seamless experience for users. |
| Embedded Power BI (UI) | Seamlessly integrates Power BI reports, dashboards, and visuals with information from Dataverse or any other source, without integrating the backend. | Users. | Pros: By using graphics and visuals supported by Power BI to present data from any source, workspaces can provide highly visual and interactive experiences for users without leaving the finance and operations apps UI.</br>Cons: Power BI artifacts aren't deployed with the build and must be configured within the environment directly. Separate ALM stories for Power BI components and finance and operations apps. | Whenever reports, dashboards, or visuals exist in Power BI. |
| IFrame (UI) | The Website Host control enables developers to embed third-party apps directly into finance and operations apps inside an IFrame. | Users. | Pros: Seamlessly integrates UI from other systems or apps without integrating the backend. Information goes directly into the finance and operations apps UI without the need for updates or compatibility.</br>Cons: External systems might have separate lifecycles, and updates to those might affect user experience with little notice. | When information from loosely coupled systems can be displayed within the finance and operations apps. The experience is enhanced if the external system supports single sign-on (SSO) and deep linking. |

### Priority-based throttling

Service protection is important for ensuring system responsiveness, availability, and performance. In finance and operations apps, throttling enforces service protection. Throttling affects OData and custom service pattern integrations only. Administrators can configure priorities for external services (registered applications) directly in the application so that lower priority integrations are throttled before high-priority integrations.

Learn more at [Priority-based throttling](/dynamics365/fin-ops-core/dev-itpro/data-entities/priority-based-throttling)."

Requests that are throttled receive a response containing a retry-after value, indicating when the integrating application can attempt a retry.

Microsoft Dynamics Lifecycle Services (LCS) monitors throttling activity.

## Customer engagement

In this section, we talk about the frameworks and platforms that are avaialble in customer engagement implementations.

### IFrames

IFrame is a popular approach commonly used for hosting external URL-based applications. Consider using the Restrict cross-frame scripting options to ensure security.

### Power Apps component framework

Power Apps component framework is a modern approach for creating rich visual components that allow enhancement of the user interface of model-driven apps. It uses client frameworks such as React, and enhancements can be reused across Dynamics 365 apps. It can also pull data from an external application and display the data in a visual form.

### Canvas apps

With canvas apps, citizen developers can build business apps without any code. These apps can use connectors from other cloud services and be embedded in model-driven apps to present data from other applications on the user interface.

### HTML web resources

A precursor to Power Apps component framework, HTML web resources were commonly used to render data in a visual form, providing designers with more flexibility. They can be used to pull data into external applications using the available endpoints.

### Dynamics 365 Channel Integration Framework

Dynamics 365 Channel Integration Framework hosts the widgets and triggers the events for scenarios such as telephony and chat integration. There are multiple versions of Channel Integration Framework for different scenarios, including multi-session and single-session needs. Channel Integration Framework also integrates channels such as voice, chat, and messaging.

### Virtual tables

Virtual tables pull data on demand from external data sources. This approach is implemented as tables within the Dataverse layer but doesn't replicate the data because the data is pulled real time on demand.

### Webhooks

Commonly used for near real-time integration scenarios, webhooks can be invoked to call an external application upon the trigger of a server event. When choosing between the webhooks model and the Azure Service Bus integration, consider the following items:

- Azure Service Bus works for high-scale processing and provides a full queueing mechanism if Dataverse pushes many events.

- Webhooks enable synchronous and asynchronous steps, whereas Azure Service Bus enables only asynchronous steps.

- Both webhooks and Azure Service Bus can be invoked from Power Automate or plug-ins.

For more information, visit [Use Webhooks to create external handlers for server events](/power-apps/developer/data-platform/use-webhooks).

### Dynamics 365 cross app integration

In this section, we look at the integration between two or more Dynamics 365 apps.

Some of the patterns mentioned earlier are specific to when we want to integrate one of the Dynamics 365 apps into a third-party or custom-built system.

Several options are available for integrating the customer engagement apps and finance and operations apps.  

> [!NOTE]
> In cross-app integration, we're actually integrating finance and operations apps with Dataverse. These options have distinct characteristics, different scenarios, and different pros and cons.

#### Virtual tables in finance and operations apps

The virtual table option enables you to connect Dataverse to finance and operations apps entities as virtual tables that offer the same full CRUD (create, retrieve \[or read\], update, delete) capabilities as the entity endpoint in the app. As a benefit, we can access the data in a secure and consistent way that looks and behaves the same as any other table or construct in Dataverse. We can also use Power Automate to connect to almost anything.

Another benefit is that the data doesn't have to live in both Dataverse and the transactional database. But the data is still seamlessly available as tables and rows in Dataverse.

> [!NOTE]
> Because Dataverse is cloud based, this direct integration option isn't available for on-premises implementations of finance and operations apps. You can use the Data Management REST API instead. For more information, read the [Finance and Operations virtual tables FAQ](/dynamics365/fin-ops-core/dev-itpro/power-platform/faq).

#### Dual-write

The second option is dual-write integration. Dual-write also provides synchronous, real-time integration between finance and operations apps and applications in Dataverse.

:::image type="content" source="media/integrate-other-solutions-dual-write.png" alt-text="Dual-write" lightbox="media/integrate-other-solutions-dual-write.png":::

A common scenario for the dual-write option is when users of the different Dynamics 365 apps are working on data that is fundamentally the same, such as customer and account, product and item, and projects.

The data is shared to provide seamless integrated experiences, for example, for product mastering, prospect to cash, and project to cash across systems. When setting up dual write for a data entity, two things are possible. First, check the [list](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/mapping-reference) of existing table mapping templates for integration of entities across apps.

The benefit of using the dual-write approach is that the two applications share the same dataset, so changes in one system are seamlessly and instantly reflected in the other one.

Another benefit is that in some cases the functionality is out of the box and configurable with minimal effort, but it's also extendable by a developer. Additionally, the full set of capabilities of Power Platform is available for the shared datasets.

Learn more about the mapping concepts and setup at [dual-write](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page).

#### Dataverse data and business events

Business and data events in Dataverse allow for extending business logic and providing advanced notification capabilities through asynchronous integration across platforms and apps. Business Events can be bound to a table, an API, or a custom process action.

Data events are using the event framework and support CRUD operations as well as RetrieveMultiple, Associate and Disassociate and specialized operations and custom actions.

The events are used for any kind of extension or integration scenario and open wide possibilities for integrating Dynamics 365 apps, plug-ins, Azure integrations, Virtual table providers, webhooks, and more. For example, the developer uses the "When an action is performed" trigger is used from Power Automate.

Learn more at [Dataverse business events](/power-apps/developer/data-platform/business-events) and [Dataverse data events](/power-apps/developer/data-platform/event-framework).

## Next steps

- [Define business goals](integrate-other-solutions-business-goals.md)  
- [Choose a platform](integrate-other-solutions-choose-platform.md)  
- [Choose a design](integrate-other-solutions-choose-design.md)  
- [Choose a pattern](integrate-other-solutions-choose-pattern.md)  
- [Challenges](integrate-other-solutions-challenges.md)  
- [Checklist](integrate-other-solutions-checklist.md)  
- [Case study](integrate-other-solutions-case-study.md)  
