---
title: Checklist for data management
description: Review a detailed checklist for managing data as part of implementing a Dynamics 365 solution.
author: vaniaf
ms.author: vaniaf
ms.date: 01/18/2024
ms.topic: conceptual
ms.custom:
  - ai-seo-date: 01/17/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Checklist for data management

Data management is an important element in solutions that include Dynamics 365. This article lists deliverables that team members must consider for each aspect of data management.

## Data governance and architecture

| Done? | Task |
|: --: |--|
| &check; | Establish data governance principles to ensure data quality throughout the lifecycle of your business processes. Focus on the availability, usability, integrity, security, and compliance of your data. |
| &check; | Appoint a data steward to apply and monitor the data governance principles. |
| &check; | Define clear use cases and make the data available to support your business processes. |
| &check; | Define the rules and select the applications for managing your master data. |
| &check; | Define a data architecture that shows a holistic view of your data repositories, their relationships, and ownership. Identify the data owners, systems, and conceptual flow between systems during your design and analysis phases. |

## Data modeling

| Done? | Task |
|: --: |--|
| &check; | Define, document, and update a data model that serves as a blueprint for your solution. |
| &check; | Follow the Common Data Model standard without deviations to ensure compatibility and readiness for future updates across applications. |

## Data storage

| Done? | Task |
|: --: |--|
| &check; | Estimate and forecast your data storage needs across different environments and types of data stores in your solution. |

## Configuration data and data migration

| Done? | Task |
|: --: |--|
| &check; | Create, maintain, update, and test a configuration plan throughout the project. The plan should include all the required configuration data that you import to support the go-live phase. |
| &check; | Create a data migration plan that identifies the data sources, data mapping, environments, ETL, testing, and cutover planning. The key contributors are the data migration analyst, data migration architect, and data steward. |
| &check; | Maximize the data throughput during migration by following best practices. |
| &check; | Optimize for network latency by staging in the cloud and batching requests. |

## Data integration

| Done? | Task |
|: --: |--|
| &check; | Store only the necessary data in the app for the key processes that interact with it. Choose the right type of data store based on the usage. |

## Data quality

| Done? | Task |
|: --: |--|
| &check; | Assess your data quality realistically and estimate the efforts required to perform the cleanup. |
| &check; | Ensure that the apps have the validations and controls to enforce data quality and that you have processes to measure and report on it. |
| &check; | Maintain high-quality data by following the principles in this article and by having leadership drive the habit of managing data on an ongoing basis. |

## Next steps

- [Review data architecture](data-management-architecture.md) and the different types of enterprise data
- [Understand configuration data and how to perform a healthy data migration](data-management-configuration-data-migration.md)
- Review product-specific guidelines for data management: [guidelines for customer engagement apps](data-management-product-specific-ce.md) and [guidelines for finance and operations apps](data-management-product-specific-fo.md)
- [Read a case study in data management](data-management-case-study.md)
