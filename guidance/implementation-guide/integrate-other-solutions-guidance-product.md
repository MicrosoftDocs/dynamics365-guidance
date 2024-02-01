---
title: Integrate Dynamics 365 apps with other systems
description: Learn about the different options and patterns for integrating Dynamics 365 apps with each other and with external systems, and how to choose the best one for your scenario.
author: abunduc-ms
ms.author: abunduc
ms.date: 01/26/2024
ms.topic: conceptual
ms.custom:
  - ai-seo-date: 01/26/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Integrate Dynamics 365 apps with other systems

To connect your Dynamics 365 apps with other apps or systems to share data, trigger actions, or enhance user experiences across different platforms, you need to know how to integrate your apps effectively. Finance and operations apps and customer engagement apps need different approaches to integration. This guide will help you understand your options and patterns for integrating Dynamics 365 apps with each other and with external systems, and how to choose the best one for your scenario.

## Finance and operations apps

Data entities are a key feature for integrating data with finance and operations apps. They're simplified views of the database tables that represent business concepts, such as customers or sales orders. They make it easier to develop and integrate data by hiding the complexity and logic of the normalized data model.

### Data entities

Data entities are denormalized views that combine data from a main table and its related tables into one row. For example, a sales order line entity contains data from the sales order header, sales order line, inventory, and customer tables. Data entities have more than 2,000 predefined views that cover common business scenarios.

You can use data entities to integrate, import, and export data without worrying about the details of the database schema or the business rules. [Learn more about data entities](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities).

The predefined data entities are designed to support many features for each business concept. If you need a faster and simpler interface for a specific purpose, you can create your own custom data entities. You can copy an existing data entity and remove any fields or logic that you don't need to optimize its performance.

### Integration patterns for finance and operations apps

The following table summarizes the main integration options for finance and operations apps. Each option has its benefits and drawbacks, depending on your needs and preferences.

| Pattern | Description | Benefits | Drawbacks | Use when |
|-------------------------|-------------------------|-------------------------|-------------------------|-------------------------|
| OData | A standard protocol for accessing and manipulating data through RESTful web services. | Easy to use and widely supported by many systems and apps. Allows you to perform CRUD (create, read, update, delete) operations on data entities. | Synchronous and subject to service protection limitations and throttling. might have slow performance or cold start issues. | You need to exchange data synchronously using RESTful web services and the volume and payload are relatively low. |
| Custom Services | A way to create and expose your own web services using X++. Supports SOAP, REST, and JSON formats. | Flexible and powerful. Allows you to invoke actions or update data using custom logic. | Requires coding and deployment of extensions. Has low payload compared to other options. | You need to invoke an action or update data using custom logic in Dynamics 365 apps from another system or app. We recommend using REST Custom Services in general because it's optimized for the web. REST is preferred for high-volume integrations because there's reduced overhead compared to other stacks such as OData. |
| Consuming web services | A way to access and use external web services by adding a reference in X++. | Simple and convenient. Allows you to consume services from other software as a service (SaaS) platforms or products. | Requires coding and deployment of references. Has low payload. might have security or maintenance risks if connection strings or credentials are hardcoded or if the service is updated. | You need to consume services from other SaaS platforms or products, such as commodity tickers or lookups of real-time values. We recommend using Power Automate instead when possible. |
| Data Management Framework REST Package API | A way to integrate using data packages, which are collections of data entities that can be imported or exported as a unit. Supports asynchronous, batched, cloud, or on-premises scenarios. | Suitable for large-volume integrations. Supports change tracking and on-premises scenarios. | Supports only data packages. Requires scheduling and transformation outside Dynamics 365 apps. | You need to exchange large volumes of data asynchronously using data packages and change tracking. |
| Recurring Data Management Integration REST API | A way to schedule the recurring integration of files and packages using the Data Management REST API. Supports SOAP and REST formats, cloud, or on-premises scenarios. | Suitable for large-volume integrations of files and packages. Supports recurrence scheduling and transformations inside Dynamics 365 apps. Supports on-premises scenarios. | None | You need to exchange large volumes of files and packages asynchronously using recurrence scheduling and transformations. |
| Electronic Reporting | A tool that configures formats for incoming and outgoing electronic documents according to the legal requirements of countries or regions. | Useful for electronic reporting to regulatory authorities and similar entities. Supports several local government formats out of the box. Can be scheduled for recurrence. | Requires comprehensive configuration when used for messaging purposes. | You need to send or receive electronic documents in specific formats according to legal requirements. |
| Excel and Office integration | A feature that enhances user productivity by integrating with Microsoft Office applications such as Excel, Word, and Outlook. | Out-of-the-box integration on almost every screen in Dynamics 365 apps. Allows you to extract, edit, import, or export data easily. | Performance decreases with the size of the dataset. | You need to extract data from Dynamics 365 apps for unplanned reporting or calculations using Excel, or import data from manual sources using Office applications. |
| Business events | A feature that provides a mechanism for external systems, Power Automate, and Azure messaging services to receive notifications from finance and operations apps. | Enables broad integration across products and platforms using events that capture user or system actions. | Requires extensions to add custom events. | You need to integrate with Azure Event Grid, Power Automate, or Logic Apps, or notify of events driven by a single data entity, such as an update of a document or a pass or fail of a quality order. |
| Embedded Power Apps | A feature that supports integration with Power Apps, which are low-code or no-code apps that can use connectors from other cloud services. | Allows you to augment the functionality and user interface of finance and operations apps with data and logic from other sources. | Power Apps and related artifacts aren't deployed with the build and must be configured in the environment directly. Requires separate ALM stories for Power Apps. | You need to access data from other sources that's loosely coupled with finance and operations apps and provide a seamless user experience. |
| Embedded Power BI | A feature that supports integration with Power BI, which is a business analytics service that provides interactive reports, dashboards, and visuals. | Allows you to enhance the user interface of finance and operations apps with graphics and visuals from any source using Power BI. | Power BI artifacts aren't deployed with the build and must be configured in the environment directly. Requires separate ALM stories for Power BI components and finance and operations apps. | You need to display reports, dashboards, or visuals from any source in finance and operations apps. |
| IFrame | A web control that developers can use to embed non-Microsoft apps directly into finance and operations apps inside an IFrame, which is a section of a web page that displays another web page. | Allows you to integrate the user interface of other systems or apps without integrating the back end. | External systems might have separate lifecycles and updates that can affect user experience with little notice. | You need to display information from loosely coupled systems in finance and operations apps. The experience is enhanced if the external system supports single sign-on (SSO) and deep linking. |

### Priority-based throttling

Throttling is a way to protect the system from being overloaded by too many requests. It limits the number of requests that can be processed at the same time. Throttling applies to OData and custom service pattern integrations only. You can set different priorities for external services (registered applications) in the app. This way, the system processes high-priority requests before low-priority ones.

[Learn more about priority-based throttling](/dynamics365/fin-ops-core/dev-itpro/data-entities/priority-based-throttling).

If a request is throttled, the system sends back a response with a retry-after value. This value tells the integrating app when it can try again.

You can use Microsoft Dynamics Lifecycle Services to track the throttling activity.

## Customer engagement apps

In this section, we'll show you the frameworks and platforms that you can use to integrate customer engagement apps with other systems or apps.

### IFrames

IFrames are web controls that let you embed external URL-based apps into customer engagement apps. They can help you display information from other sources in the user interface. Make sure to use the Restrict cross-frame scripting options to prevent security risks.

### Power Apps component framework

Power Apps component framework is a modern way to create rich visual components that enhance the user interface of model-driven apps. It uses client frameworks like React, and you can reuse the components across Dynamics 365 apps. You can also pull data from an external app and show it in a visual form.

### Canvas apps

Canvas apps are low-code or no-code apps that you can build easily. You can use connectors from other cloud services to access data and logic from other sources. You can also embed canvas apps in model-driven apps to show data from other apps in the user interface.

### HTML web resources

HTML web resources are web pages that you can use to display data in a visual form. A precursor to Power Apps component framework, HTML web resources were commonly used to render data in a visual form, providing designers with more flexibility. You can use them to pull data from external apps using the available endpoints.

### Dynamics 365 Channel Integration Framework

Dynamics 365 Channel Integration Framework is a feature that lets you integrate communication channels such as voice, chat, and messaging into customer engagement apps. It hosts the widgets and triggers the events for scenarios like telephony and chat integration. It has different versions for different scenarios, such as multi-session and single-session needs.

### Virtual tables

Virtual tables are tables in Dataverse, which is the data platform behind customer engagement apps, that pull data from external data sources on demand. They don't store the data, but they show it as if it were part of Dataverse. They let you access data from external sources in real time.

### Webhooks

Webhooks are HTTP requests that you can use to call an external app when a server event happens in customer engagement apps. They're useful for near-real-time integration scenarios. You can choose between synchronous and asynchronous steps. You can also invoke them from Power Automate or plug-ins.

If you need to handle many events or high-scale processing, you might want to use Azure Service Bus instead of webhooks. Azure Service Bus provides a full queueing mechanism for data exchange, but it only supports asynchronous steps.

[Learn how to use webhooks to create external handlers for server events](/power-apps/developer/data-platform/use-webhooks).

## Dynamics 365 cross-app integration

In this section, we'll show you how to integrate two or more Dynamics 365 apps with each other. Some of the integration options and patterns we discussed earlier are specific to when you want to integrate one of the Dynamics 365 apps with a partner or custom-built system. But you might also want to integrate the customer engagement apps and finance and operations apps.

When you integrate customer engagement apps and finance and operations apps, you're actually integrating finance and operations apps with Dataverse. Dataverse is the data platform behind customer engagement apps. These integration options have different characteristics, scenarios, pros, and cons.

### Virtual tables in finance and operations apps

Virtual tables let you connect Dataverse to finance and operations apps entities as virtual tables. Virtual tables have the same full CRUD (create, read, update, delete) capabilities as the entity endpoint in the app. You can access the data in a secure and consistent way that looks and behaves like any other table in Dataverse. You can also use Power Automate to connect to other sources.

The data doesn't have to live in both Dataverse and the transactional database, but it's still available as tables and rows in Dataverse.

> [!NOTE]
> This integration option works only for cloud-based implementations of finance and operations apps. If you have an on-premises implementation, you can use the Data Management REST API instead. For more information, see the [Finance and Operations virtual tables FAQ](/dynamics365/fin-ops-core/dev-itpro/power-platform/faq).

### Dual-write

Dual-write is another integration option that provides synchronous, real-time integration between finance and operations apps and applications in Dataverse.

You can use dual-write when you want to share data that's fundamentally the same across Dynamics 365 apps, such as customer and account, product and item, or project and task. This way, you can provide seamless integrated experiences for scenarios like product mastering, prospect to cash, or project to cash across systems.

When you set up dual-write for a data entity, you can use existing [table mapping templates](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/mapping-reference) for integration of entities across apps.

One benefit of using dual-write is that the two systems share the same dataset. Any changes in one system are instantly reflected in the other one.

Another benefit is that some functionality is ready to use and easy to configure, although you can also extend it by coding. Plus, you can use all the capabilities of Power Platform for the shared datasets.

[Learn how to set up dual-write](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page).

#### Dataverse data and business events

Dataverse data and business events let you extend business logic and provide advanced notification capabilities through asynchronous integration across platforms and apps. You can use data events or business events depending on your needs.

Data events use the event framework and support CRUD operations as well as RetrieveMultiple, Associate, Disassociate, and specialized operations and custom actions. Business events can be bound to a table, an API, or a custom process action.

You can use events for any kind of extension or integration scenario. For example, you can use them to integrate Dynamics 365 apps, plug-ins, Azure integrations, virtual table providers, and webhooks.

Learn how to use [Dataverse business events](/power-apps/developer/data-platform/business-events) and [Dataverse data events](/power-apps/developer/data-platform/event-framework).

## Next steps

- Use this Solution by Design [checklist](integrate-other-solutions-checklist.md) to make sure you've covered all the steps and considerations for your integration project
- Read how a public sector infrastructure organization learned how to [choose the right solution for their integration project](integrate-other-solutions-case-study.md)
