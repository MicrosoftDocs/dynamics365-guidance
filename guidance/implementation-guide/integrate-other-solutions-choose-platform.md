---
title:  Choose a platform for integration
description: Find guidance on how to choose the right platform for your Dynamics 365 apps integration strategy.
author: abunduc-ms
ms.author: abunduc
ms.date: 05/25/2023
ms.topic: conceptual

---

# Choose a platform for integration

This article discusses what you should consider when choosing a platform and, if needed, a middleware solution to achieve the previously mentioned business goals.

Data storage needs have increased exponentially in recent years, and it continues to intensify in this direction. The amount of data that's generated and transferred today is practically unimaginable. In addition to the new data that's being captured or generated, historical data from legacy systems might need to be preserved. The platform you choose must incorporate all of these realities, and it must reliably handle the storage and transfer of vast amounts of data.

## Cloud, on-premises, and hybrid platforms

Your organization's size and maturity level are factors when considering various platform scenarios. Most organizations find themselves using some variation of one of the following types:

- **Simple cloud**  

  In this scenario, the organization might have acquired the first cloud software as a service (SaaS) application. Overall solution complexity is low. As part of the implementation project, they want to integrate with another cloud service.

  :::image type="content" source="media/integrate-other-solutions-simple-cloud.png" alt-text="Simple cloud hybrid platforms" lightbox="media/integrate-other-solutions-simple-cloud.png":::

- **Simple hybrid**  

  In this scenario, the organization might also have acquired the first cloud application. Solution complexity is also low. But in its implementation project, the organization wants to integrate to a system on-premises, adding the need for a strategy for crossing the cloud to on-premises boundary.

  :::image type="content" source="media/integrate-other-solutions-simple-hybrid.png" alt-text="Simple hybrid platforms" lightbox="media/integrate-other-solutions-simple-hybrid.png":::

  > [!NOTE]
  > When you implement a simple cloud or simple hybrid system, make sure you use the capabilities of Microsoft Azure and Power Platform. With Dynamics 365, out-of-the-box low-code/no-code options are available for using Pull designs and RESTful service endpoints. Such an approach will build a scalable foundation, allowing expansion for years to come.
  >
  > Don't fall for the temptation of building tightly coupled point-to-point, custom synchronous service integrations. They will likely not scale well, and future expansion will likely make the system more fragile. It's good practice to lay a solid foundation early. Organizations that choose not to do that often find themselves having to make tough and expensive adjustments to make the architecture scalable as the business grows.

- **Primarily on-premises**  

  In this scenario, the organization has in place a rather complex on-premises solution with multiple line-of-business systems. The organization is using a middleware platform that's based on-premises to connect systems and might be integrating its first cloud application.

  :::image type="content" source="media/integrate-other-solutions-onprem.png" alt-text="Primarly on-premise platforms" lightbox="media/integrate-other-solutions-onprem.png":::

- **Hybrid**  

  The hybrid example represents large, diversified enterprises or organizations that are halfway through their cloud journey. The organization is using connected cloud and on-premises middleware platforms that can integrate in hybrid scenarios, and it might add another cloud application to the solution architecture.

  :::image type="content" source="media/integrate-other-solutions-hybrid.png" alt-text="Primarly hybrid platforms" lightbox="media/integrate-other-solutions-hybrid.png":::

  > [!NOTE]
  > When planning an incremental migration to the cloud, consider the best options for where and how to achieve a reliable hybrid middleware-to-cloud platform. Consider whether the current middleware platforms and on-premises components are scalable and provide opportunities for leveraging modern technologies, such as low-code/no-code development options, or whether it would make sense to leverage the possibilities within Azure and Power Platform to migrate the current line-of-business systems to the cloud to achieve scalability, elasticity, and extendibility.
  >
  > Don't silo data assets in on-premises line-of-business systems and disjointed data stores that are difficult for citizen developers, makers, and modern frameworks to access.

- **Hybrid without middleware**  

  In this scenario, the organization has likely evolved the integration architecture over time. Multiple systems are integrated using different technologies, and it seems System 4 is acting as a hub. No middleware platform is applied, and strategy is likely loosely defined. The perceived cost of applying an integration platform and middleware is making it necessary to use point-to-point integration when new systems are introduced.

  :::image type="content" source="media/integrate-other-solutions-nomiddleware-hybrid.png" alt-text="Hybrid with no middleware" lightbox="media/integrate-other-solutions-nomiddleware-hybrid.png":::

- **Primarily cloud**  

  In this scenario, the organization has a higher level of cloud maturity, platform, and middleware are platform-as-a-service (PaaS) cloud services. The organization has integrated a few on-premises components that are necessary, and more line-of-business systems are all in the cloud.

  :::image type="content" source="media/integrate-other-solutions-nomiddleware-cloud.png" alt-text="No middleware and primarily cloud platforms" lightbox="media/integrate-other-solutions-nomiddleware-cloud.png":::

    It's important to not continue using resources on maintaining an integration architecture that spans multiple technologies and doesn't have a centralized mechanism for error handling, notification, high availability (HA), and disaster recovery (DR).

   Continue to use the cloud-based strategy and the toolset provided by Azure and Power Platform to integrate to on-premises components when necessary.

  > [!NOTE]
  > When implementing a system that's primarily cloud, compare the cost of implementing a clear strategy and using a platform and middleware such as Azure and Power Platform with the cost of operating and maintaining the existing integrations.

## Middleware

Integration middleware is software or services that enable communication and data management for distributed applications. Middleware often provides messaging services on technologies such as SOAP, REST, and JSON. Some middleware offers queues, transaction management, monitoring, and error logging and handling. Different middleware platforms can support on-premises, cloud-based, or hybrid scenarios. The following are characteristics you should consider when choosing a middleware platform.

> [!IMPORTANT]
> Middleware provides specialized capabilities to enable communication, transformation, connectivity, orchestration, and other messaging-related functionality. Dynamics 365 Finance and Operations are business apps that provide integration capabilities to support interfaces, but they are not designed to replace middleware.

### Key characteristics

When deciding whether to integrate to an existing system, you should consider several important characteristics of the solution, the system, and its context.

- **Scalability and performance**  

  The planned platform, middleware, and supporting architecture must be able to handle your organization's expected persistent and peak transaction volumes in the present, the short term, and the long term.

- **Security**  

  Authentication defines how each system confirms a user's identity, and you should consider how that works across systems and with middleware. Authorization specifies how each system grants or denies access to endpoints, business logic, and data. It's important to ensure that an integration platform and middleware are compatible with system security and fit into the solution architecture landscape.

- **Reliable messaging**  

  Middleware typically provides messaging services. The messaging platform must support the architecture of the integrated systems. It must also provide a reliable mechanism or technology to ensure that messaging across systems is accurately sent, acknowledged, received, and confirmed. This is especially important in situations in which a system or part of the supporting architecture is unavailable. Error-handling concepts related to messaging, such as idempotency and transient versus persistent errors, are discussed in the [Mind the errors](integrate-other-solutions-choose-pattern.md#mind-the-errors).

- **HA and DR**  

  The middleware platform supports the expected level of stability and availability across the interface in line with the cross-system requirements, for example, HA for mission-critical scenarios. Requirements for DR are another consideration for the platform and middleware. For example, if there's an outage in the integrated systems or the supporting infrastructure, what happens to shared or synchronized data when the outage is resolved? What happens if either system has to roll back to the latest backup?

- **Monitoring and alerting**  

  The platform, middleware, and supporting infrastructure must support the requirements for monitoring activity and alerting users and administrators if there's a problem. The platform must manage adequate levels and venues of alerts and notifications. It's also important to consider who in your organization is responsible for responding to those alerts and notifications and whether the necessary workload is feasible.

- **Diagnostics and audit logs**  

  It's important to also consider the requirements for monitoring cross-system activity and for audit trails and logging. You should consider whether the planned platform and middleware support that.

- **Extensibility and maintenance**  

  It's important to consider the impact of other business requirements in the long term. Considerations include the following list:  

  - The level of effort required to extend the integration beyond the first implementation  
  - Whether the integration requires expertise in multiple technologies and changes to both systems  
  - Whether there's a single low-code/no-code point of extensibility  
  - How and how often updates are applied  
  - What level of technical and functional support is available  

- **ALM**  

  To keep costs as low as possible, consider how you can ensure effective lifecycle management, version control, and documentation of the integrated solution. You should verify that all components and parts of the solution can use ALM tools such as Azure DevOps. Learn more at [Application lifecycle management](application-lifecycle-management.md).

Data consistency across multiple systems is important, and for that to occur you need to ensure data quality. Keep in mind the saying that *if garbage comes in, garbage comes out*. It's important to verify that your data flows correctly and in a timely manner across all the integrated systems.

The following section discusses the preferred platform to use to integrate with Dynamics 365 apps on Azure.

> [!NOTE]
> Dynamics 365 apps and Power Platform allow users to design, configure, and customize an application to meet a customer's business needs. In doing so, it's important to consider performance and scalability. Ensuring a performant system is a shared responsibility among customers, partners, ISV providers, and Microsoft.

## Power Platform and Dataverse

Power Platform enables integration between your organization's systems. It also provides opportunities for your organization to use low-code/no-code development models and more complex developer platforms to integrate solutions. In Dynamics 365 apps, this avenue for integration and much more becomes available when you use Microsoft Dataverse.

Dataverse provides a data foundation for applications in customer engagement apps and Power Platform. When your solution components live in Dataverse, you can natively connect and extend the solution using Power BI, Power Apps, Power Automate, and Power Virtual Agents.

:::image type="content" source="media/integrate-other-solutions-power-platform.png" alt-text="Dataverse" lightbox="media/integrate-other-solutions-power-platform.png":::

The primary benefits of using an integration pattern based on Dataverse are as follows.

### Works with any type of app

- Dataverse works with a broad set of data sources through connectors or Microsoft Power Query.

- Dataverse has built-in connectors through Power Automate that offer configurable, deep integration to Microsoft cloud services, but also to popular applications such as Adobe, Mailchimp, and Twitter.

- Dataverse provides a modern REST-based API, a vast developer toolkit, and a growing list of samples that link two or more connectors. You often don't need to start your integration project from a blank slate.

### Works with any kind of data

- Dataverse is integrated into data-centric tools and services such as Microsoft Excel, Outlook, Power BI, Power Query, and AI Builder. These services are used by knowledge workers and integration engineers.

- The Dataverse has built-in analytics, reporting, and AI that you can use to provide insights into your organization and support decision making. You can obtain analytics and reporting data using low-code/no-code options or by using the full capability set of Azure Data Factory, Power BI, and Azure Databricks. Learn more at [Business intelligence, reporting, and analytics](business-intelligence-reporting-analytics-overview.md).

Let's take a look now at how you can use Power Platform and Dataverse with Dynamics 365 apps.

## Customer engagement apps

The data for customer engagement apps is securely stored and managed in Dataverse. This means that the apps can natively use Dataverse capabilities to integrate to other applications.

## Dynamics 365 apps and Dataverse

Finance and operations apps such as Dynamics 365 Finance, Supply Chain Management, or Business Central, are built on a specialized cloud SQL schema, optimized for online transactional processing (OLTP). However, you can integrate into Dataverse through several design patterns, some of which are seamless and synchronous or near real time. When you connect these apps with Dataverse, you're using a rich set of predefined denormalized endpoints, namely data entities. Learn more at [Product-specific guidance for integration scenarios](integrate-other-solutions-guidance-product.md).

> [!NOTE]
> A data warehouse provides capabilities to store, process, aggregate, analyze, data mine, and report on both current and historical data sets typically with data aggregated from a varied set of cloud and line-of-business (LOB) applications. A data warehouse has specific architecture optimized for analytical functions. An Enterprise Resource Planning (ERP) solution such as Finance and Operations apps maintains a highly normalized data set optimized for transactional processing and business functionality. It's important to select the appropriate data warehouse platform to meet your organization's data warehouse and analytical needs.

## Next steps

- [Define business goals](integrate-other-solutions-business-goals.md)  
- [Choose a design](integrate-other-solutions-choose-design.md)  
- [Choose a pattern](integrate-other-solutions-choose-pattern.md)  
- [Challenges](integrate-other-solutions-challenges.md)  
- [Product-specific guidance for integration scenarios](integrate-other-solutions-guidance-product.md)  
- [Checklist](integrate-other-solutions-checklist.md)  
- [Case study](integrate-other-solutions-case-study.md)  
