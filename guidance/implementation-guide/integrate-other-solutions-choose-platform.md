---
title: Select the ideal platform for your Dynamics 365 apps integration
description: Learn how to select the best platform for integrating your Dynamics 365 apps to meet your business objectives.
author: abunduc-ms
ms.author: abunduc
ms.date: 01/25/2024
ms.update-cycle: 1095-days
ms.topic: concept-article
ms.custom:
  - evergreen
  - ai-seo-date: 01/25/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Select the ideal platform for your Dynamics 365 apps integration

In this article, we'll explore key considerations for selecting a platform and, if necessary, a middleware solution to support your business goals.

The need for data storage has grown significantly, and this trend shows no signs of slowing down. The sheer volume of data being produced and shared today is staggering. Not only must we manage new data, but we also need to preserve historical information from older systems. Your chosen platform must handle these demands and ensure reliable storage and transfer of large amounts of data.

## Cloud, on-premises, and hybrid platforms

When evaluating platform options, consider your organization's size and maturity. Most organizations use variations of the following scenarios:

- **Simple cloud**: Organizations that are new to cloud services might start with a simple cloud software as a service (SaaS) application. The solution complexity is low, and they might want to integrate with another cloud service during the implementation project.

- **Simple hybrid**: Similar to the simple cloud scenario, but with the added complexity of integrating an on-premises system, requiring a strategy for bridging cloud and on-premises environments.

  Use Microsoft Azure and Power Platform capabilities when implementing simple cloud or hybrid systems. Dynamics 365 offers low-code/no-code options for scalable foundations. Avoid creating tightly coupled point-to-point, custom synchronous service integrations, because they might not scale well.

- **Primarily on-premises**: More complex scenarios involve multiple on-premises line-of-business systems using an on-premises middleware platform, possibly integrating a first cloud application.

- **Hybrid**: Large enterprises or those transitioning to the cloud might use both cloud and on-premises middleware platforms capable of hybrid integration, possibly adding another cloud application.

  For incremental migration to the cloud, assess whether current middleware platforms are scalable and consider using Azure and Power Platform for modernization.

- **Hybrid without middleware**: Over time, an organization's integration architecture might evolve without a middleware platform, leading to loosely defined strategies and reliance on point-to-point integration for new systems.

- **Primarily cloud**: Organizations with advanced cloud maturity use platform as a service (PaaS) for both platform and middleware, integrating necessary on-premises components while moving more systems to the cloud.

  Focus on a cloud-based strategy using Azure and Power Platform tools for any necessary on-premises integration.

## Middleware

Middleware facilitates communication and data management across distributed applications. It often includes messaging services like SOAP, REST, and JSON, along with queues, transaction management, monitoring, error logging, and handling. Middleware can support on-premises, cloud-based, or hybrid scenarios.

### Key characteristics

Consider these characteristics when you're deciding whether to integrate with an existing system:

- **Scalability and performance**: Make sure that the architecture can handle current and future transaction volumes.

- **Security**: Consider authentication across systems and middleware compatibility with system security.

- **Reliable messaging**: Messaging platforms must support integrated system architectures and provide reliable messaging mechanisms.

- **High availability (HA) and disaster recovery (DR)**: Middleware should support HA requirements and have DR plans for outages in integrated systems or infrastructure.

- **Monitoring and alerting**: Platforms should facilitate activity monitoring and alerting for issues.

- **Diagnostics and audit logs**: Make sure that platforms support cross-system activity monitoring and logging requirements.

- **Extensibility and maintenance**: Consider the effect of long-term business requirements on integration extensibility.

- **Application lifecycle management (ALM)**: Verify that all solution components can use ALM tools like Azure DevOps.

Data consistency is crucial, and it requires high-quality data. Make sure that your data flows correctly and in a timely manner across the integrated system.

## Power Platform and Dataverse

Power Platform and Dataverse are the preferred platform for integrating Dynamics 365 apps on Azure. Power Platform offers low-code/no-code development models for solution integration. Dataverse provides a data foundation for applications in customer engagement apps in Power Platform.

Dataverse works with a wide variety of data sources through connectors or Microsoft Power Query. It has built-in connectors through Power Automate to Microsoft services and popular applications. Dataverse integrates with tools like Microsoft Excel, Outlook, and Power BI, providing built-in analytics, reporting, and AI capabilities. Dataverse also offers a modern REST-based API for developers.

Customer engagement app data is stored and managed in Dataverse, offering native integration capabilities with other applications.

Finance and operations apps like Dynamics 365 Finance and Supply Chain Management are built on cloud SQL schemas that are optimized for transactional processing. Integration into Dataverse is possible through various design patterns, using predefined denormalized endpoints or data entities.

Remember, a data warehouse is different from an Enterprise Resource Planning (ERP) solution like finance and operations apps. Choose the right data warehouse platform to meet your analytical needs.

## Next steps

- Explore the different types of integration scenarios and how to [choose a design](integrate-other-solutions-choose-design.md) that suits your needs
- Discover the integration patterns available with Dynamics 365 apps and what factors to consider when [choosing a pattern](integrate-other-solutions-choose-pattern.md)
- Find out what challenges you might face when integrating systems and how to overcome them with [best practices](integrate-other-solutions-challenges.md)
- Learn about the aspects that are specific to each Dynamics 365 app and how to [integrate them with other solutions](integrate-other-solutions-guidance-product.md)
- Use this Solution by Design [checklist](integrate-other-solutions-checklist.md) to make sure you've covered all the steps and considerations for your integration project
- Read how a public sector infrastructure organization learned how to [choose the right solution for their integration project](integrate-other-solutions-case-study.md)
