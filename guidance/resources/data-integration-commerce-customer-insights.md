---
title: Data integration between Commerce and Customer Insights
description: Learn about how a data integration between Dynamics 365 Commerce and Customer Insights can help to accelerate insightful use cases. The article also talks about how to start an implementation project.
author: OfficerSpears
contributors: tchilaud, meenulaul, stoubia, ssundar, liamkerrigan, petkra
ms.author: raphel
ms.reviewer: edupont
ms.topic: concept-article
ms.date: 07/22/2025
---

# Overview of data integration between Dynamics 365 Commerce and Customer Insights

This article provides an overview of how to configure Dynamics 365 Commerce and Dynamics 365 Customer Insights in an implementation project so data flows seamlessly between the apps. This article and two related articles explain how to combine the capabilities of these business applications and outline the use cases they help to realize. The article outlines the significance of this integration and reveals the powerful capabilities unlocked by harmonizing the apps. Additionally, the article explores how retailers can use existing data in the system to facilitate this integration.

The article explains how to architect the data integration from Dynamics 365 Commerce to Dynamics 365 Customer Insights, specifically Dynamics 365 Customer Insights - Data.

The related articles cover implementation guidance, functional and technical details, and data modeling to support different scenarios. Find them in the [Related content](#related-content) section.

While the article emphasizes the synergies between Dynamics 365 Commerce and Dynamics 365 Customer Insights, the data integration architecture also applies to integration with other Dynamics 365 finance and operations applications.

## Dynamics 365 Commerce

[Dynamics 365 Commerce](/dynamics365/commerce/welcome) delivers a comprehensive omnichannel solution that unifies back-office, in-store, call center, and digital experiences. Dynamics 365 Commerce lets you build brand loyalty through personalized customer engagements, increase revenue by improving employee productivity, optimize operations to reduce costs, and drive supply chain efficiencies to deliver better business outcomes.

## Dynamics 365 Customer Insights

[Dynamics 365 Customer Insights](/dynamics365/customer-insights/overview) is the combined customer data platform ([Dynamics 365 Customer Insights – Data](/dynamics365/customer-insights/data/overview)) and real-time journey orchestration ([Dynamics 365 Customer Insights – Journeys](/dynamics365/customer-insights/journeys/real-time-marketing-overview)) that helps your organization deliver exceptional customer experiences. It creates a foundation for personalized, responsive, and connected customer journeys.

## Why retailers want to integrate Dynamics 365 Commerce with Dynamics 365 Customer Insights

Dynamics 365 Customer Insights is a powerful tool that enables retailers to gain a better understanding of their customers. With this unified and enhanced presentation of customer data, retailers gain comprehensive insights into their customer base and can offer personalized experiences and streamline processes. This opportunity can lead to revenue growth, cost reduction, and enhanced customer satisfaction.

By connecting Dynamics 365 Commerce with Dynamics 365 Customer Insights, businesses can realize many benefits, such as:

- Creating a unified view of the customer across different channels and touchpoints.
- Segmenting and targeting customers based on their behavior, preferences, and needs.
- Personalizing and optimizing the customer journey and the shopping experience.
- Increasing customer satisfaction, retention, and loyalty.
- Improving conversion rates and revenue, thus enhancing marketing and sales performance and efficiency.
- Engaging customers in moments that matter with trigger-based customer journeys.

## Integrate data from Dynamics 365 Commerce to Dynamics 365 Customer Insights - Data

Dynamics 365 Commerce customers who already use Azure Synapse Link for Dataverse to sync data to their lake, such as for BI and analytics scenarios, can use that architecture. They can then extend it to make data available to Dynamics 365 Customer Insights – Data.

For Dynamics 365 Commerce customers who didn't already start this journey, review the recommended data integration path in the article [Choose finance and operations data in Azure Synapse Link for Dataverse](/power-apps/maker/data-platform/azure-synapse-link-select-fno-data).

Azure Synapse Link for Dataverse offers several options for the format and destination where data is synced. [Azure Synapse Link for Dataverse with Azure Data Lake](/power-apps/maker/data-platform/azure-synapse-link-data-lake) is a generic pattern that syncs data to a lake that conforms to the Common Data Model (CDM) framework.

Once Dynamics 365 Commerce data is in the lake, you must prepare it with a data transformation stack of your choice so it's consumable by Dynamics 365 Customer Insights – Data.

In Dynamics 365 Commerce, the data model and storage are optimized for transactional workloads. For example, *orders* are stored in multiple normalized tables. In Dynamics 365 Customer Insights – Data, the data model should be optimized for analytical workloads. Therefore, you're expected to integrate `Orders` as a single denormalized table. This table should include all necessary information, optionally filtered by rows and columns, with easily understandable column names.

:::image type="content" source="media/customer-insights-commerce-data-flow-architecture1-1.png" alt-text="Diagram that shows the high-level architecture of data flow from Commerce to Customer Insights – Data." lightbox="media/customer-insights-commerce-data-flow-architecture1-1.png":::

Use the following resources to learn more about the components:

- [Choose finance and operations data in Azure Synapse Link for Dataverse](/power-apps/maker/data-platform/azure-synapse-link-select-fno-data) and  [Azure Synapse Link for Dataverse with Azure Data Lake](/power-apps/maker/data-platform/azure-synapse-link-data-lake)

- Use [Azure Synapse Analytics](/azure/synapse-analytics/), [Azure Data Factory](/azure/data-factory/), or [Azure Databricks](/azure/databricks/) for data transformation and preparation

- [Connect to Azure Data Lake Storage](/dynamics365/customer-insights/data/connect-common-data-model) or [Connect to Delta tables in Azure Data Lake](/dynamics365/customer-insights/data/connect-delta-lake) from Dynamics 365 Customer Insights

A real implementation can also include external products.

## Related content

- [Data integration with Dynamics 365 Commerce and Dynamics 365 Customer Insights - Data](data-integration-commerce-customer-insights-data.md)  
- [Data integration from Dynamics 365 Commerce to Customer Insights - Journeys in near real-time](data-integration-commerce-customer-insights-journeys.md)  

## Contributors in alphabetic order

- [Liam Kerrigan](https://www.linkedin.com/in/liamkerrigan/) \| Senior Program Manager

- [Meenu Laul](https://www.linkedin.com/in/meenu-laul-6590bb17/) \| Senior Solution Architect

- [Peter Krause](https://www.linkedin.com/in/ms-peterkrause/) \| Principal Solution Architect

- [Raphael Vonderküste](https://www.linkedin.com/in/raphaelvdk/) \| Principal Program Manager

- [Sarah Toubia](https://www.linkedin.com/in/sarah-toubia/) \| Senior Solution Architect

- [Srinath Sundaresan](https://www.linkedin.com/in/srinath-sundaresan-8b05284b/) \| Senior Solution Architect

- [Thomas Chilaud](https://www.linkedin.com/in/thomas-chilaud/) \| Principal Solution Architect
