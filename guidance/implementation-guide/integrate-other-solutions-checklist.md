---
title: Integration strategy and governance checklist
description: Get a thorough checklist to help Dynamics 365 implementation teams with their integration strategy, including checklists on defining goals and choosing a platform.
author: abunduc-ms
ms.author: edupont
ms.date: 01/26/2024
ms.update-cycle: 1095-days
ms.topic: checklist
ms.custom:
  - evergreen
  - ai-seo-date: 01/26/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Integration strategy checklist

## Define business goals

| Done? | Task |
| :---: | --- |
| &check; | Write down the goals and benefits of the integration in a way that the business can understand. |
| &check; | Make sure the integration supports the organization's short-term and long-term goals. |
| &check; | Explain the integration architecture, systems, and integration points clearly and simply. |
| &check; | Make sure that everyone involved knows the purpose and scope of the integration. |

## Choose a platform

| Done? | Task |
| :---: | --- |
| &check; | Help the organization understand the difference between cloud and on-premises platforms and where they connect. |
| &check; | Decide whether to use an integration middleware or a messaging service. |
| &check; | Make sure that the integration platform or middleware can monitor, audit, notify, and alert as needed. |
| &check; | Make sure that the integration platform or middleware has the expected level of security, availability, and disaster recovery. |
| &check; | Make sure that all parts of the integration platform or middleware can use application lifecycle management (ALM) and version control tools. |

## Choose a design

| Done? | Task |
| :---: | --- |
| &check; | Make sure that each integration design fits with the overall integration architecture. |
| &check; | Avoid sending or storing data that isn't needed in the solution. |
| &check; | Compare and contrast the options and benefits for each of these aspects: User interface look and feel, data, process integration, and Dataverse. |

## Choose a pattern

| Done? | Task |
| :---: | --- |
| &check; | Design integrations that use reliable, asynchronous messages to exchange data. |
| &check; | Choose a pattern that matches the expected amount, frequency, and service protection limitations of data exchange. |
| &check; | Determine realistic estimates of how much it will cost to run the services, platforms, and storage involved and how it will change over time. |

## Project governance

| Done? | Task |
| :---: | --- |
| &check; | Plan to test each integration for user experience and performance under realistic conditions, including before, during, and after the data exchange. |
| &check; | Plan to test the end-to-end process for each integration pattern according to the recommendations for data volume, frequency, and service protection limitations. |
| &check; | Manage any changes that are related to integrations in a way that supports the business goals. |
| &check; | Analyze how integrations affect other processes upstream and downstream. |

## Next steps

- Start your integration project by [defining your business goals](integrate-other-solutions-business-goals.md) and aligning them with your cross-system requirements
- Learn how to [choose a platform](integrate-other-solutions-choose-platform.md) that can handle the storage and transfer of large amounts of data across different systems
- Explore the different types of integration scenarios and how to [choose a design](integrate-other-solutions-choose-design.md) that suits your needs
- Discover the integration patterns available with Dynamics 365 apps and what factors to consider when [choosing a pattern](integrate-other-solutions-choose-pattern.md)
- Find out what challenges you might face when integrating systems and how to overcome them with [best practices](integrate-other-solutions-challenges.md)
- Learn about the aspects that are specific to each Dynamics 365 app and how to [integrate them with other solutions](integrate-other-solutions-guidance-product.md)
- Read how a public sector infrastructure organization learned how to [choose the right solution for their integration project](integrate-other-solutions-case-study.md)
