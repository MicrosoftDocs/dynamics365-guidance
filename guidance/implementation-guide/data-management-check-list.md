---
title: Data management checkList
description: View a detailed checklist on several aspects of data management. We examine the various ways that data management plays a role in the creation of an effective Dynamics 365 solution and here you can find a summary list.
author: vaniaf
ms.author: vaniaf
ms.date: 03/01/2023
ms.topic: conceptual

---

# Data management checkList

Data management is an important element in solutions that include Dynamics 365. This article lists deliverables that team members must consider for each aspect of data management.  

## Data governance and architecture

- Establish data governance principles to ensure data quality throughout the business processes lifecycle, focusing on the data's availability, usability, integrity, security, and compliance.

- Appoint a data steward to ensure data governance principles are applied.

- Define proper use cases and make data available to support the business processes.

- Define proper rules and select applications for master data management.

- Define a proper data architecture that depicts a holistic view of the data repositories, their relationships with each other, and ownership. Capture the data owners, systems, and conceptual flow between systems during your design and analysis phases.

## Data modeling

- Define, clearly document, and keep a data model up to date to serve as a blueprint.

- Conform the data model to the Common Data Model standard without deviations to ensure cross-application compatibility and future readiness.

## Data storage

- Estimate and forecast data storage needs across different environments and types of data stores used in the solution.

## Configuration data and data migration

- Create, maintain, update, and test a configuration plan throughout the project lifetime. It accounts for all the required configuration data you import to support go live.

- Make sure you create a plan for data migration that includes identifying data sources, data mapping, environments, ETL, testing, and cutover planning. Key contributors are the data migration analyst, data migration architect, and data steward.  

- Focus on maximizing the data throughput during migration by following best practices.

- Optimize for network latency by staging in the cloud and batching requests.

## Data integration

- Only store necessary data in the app for key processes that actively interact with it and choose the right type of data store based on the usage.

## Data quality

- Create a realistic view of your data quality and estimate the efforts required to perform the necessary cleanup.

- Ensure that the apps have the necessary validations and controls to enforce data quality and that you have processes to measure and report on it.

- Maintain high-quality data by following the principles in this chapter, and have leadership drive the habit of managing data on an ongoing basis.
