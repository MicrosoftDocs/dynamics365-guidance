---
title: Data integration between Commerce and Customer Insights
description: Learn about how a data integration between Dynamics 365 Commerce and Customer Insights can help to accelerate insightful use cases. The article also talks about how to start an implementation project.
author: OfficerSpears
contributors: tchilaud, meenulaul, stoubia, ssundar, liamkerrigan, petkra
ms.author: raphel
ms.reviewer: edupont
ms.topic: concept-article
ms.date: 07/16/2025
---

# Overview of data integration between Dynamics 365 Commerce and Customer Insights

This article provides an overview of how you can configure Dynamics 365 Commerce and Dynamics 365 Customer Insights in an implementation project so that data flows seamlessly between the apps. This article and two related articles how to combine the capabilities of these business applications and outline the use cases business applications help to realize. We outline the significance of this integration and reveal the potent capabilities that can be unlocked by harmonizing the apps. Additionally, we'll explore how retailers can take advantage of the existing data in the system to facilitate this integration.

The article sets the foundations around how to architect the data integration from Dynamics 365 Commerce to Dynamics 365 Customer Insights, precisely Dynamics 365 Customer Insights - Data.

The related articles dive into implementation guidance, functional, technical details and data modeling to support different scenarios. Find them in the [Related content](#related-content) section.

While the article emphasizes the synergies between Dynamics 365 Commerce and Dynamics 365 Customer Insights, the data integration architecture applies to integration with the other Dynamics 365 finance and operations applications.

## Dynamics 365 Commerce

[Dynamics 365 Commerce](/dynamics365/commerce/welcome) delivers a comprehensive omnichannel solution that unifies back-office, in-store, call center, and digital experiences. Dynamics 365 Commerce enables you to build brand loyalty through personalized customer engagements, increase revenue with improved employee productivity, optimize operations to reduce costs and drive supply chain efficiencies, ultimately delivering better business outcomes.

## Dynamics 365 Customer Insights

[Dynamics 365 Customer Insights](/dynamics365/customer-insights/overview) is the combined customer data platform ([Dynamics 365 Customer Insights – Data](/dynamics365/customer-insights/data/overview)) and real-time journey orchestration ([Dynamics 365 Customer Insights – Journeys](/dynamics365/customer-insights/journeys/real-time-marketing-overview)) that helps your organization deliver exceptional customer experiences. It lays the foundation to create truly personalized, responsive, and connected customer journeys.

## Why retailers want to integrate Dynamics 365 Commerce with Dynamics 365 Customer Insights

Dynamics 365 Customer Insights is a powerful tool that enables retailers to gain a better understanding of their customers. By unifying and enhancing customer data, retailers can attain comprehensive insights into their customer base. Using this information, they can offer personalized experiences and streamline processes. This can lead to revenue growth, cost reduction, and enhanced customer satisfaction.

By connecting Dynamics 365 Commerce with Dynamics 365 Customer Insights, businesses can realize many benefits, such as:

- Creating a unified view of the customer across different channels and touchpoints.
- Segmenting and targeting customers based on their behavior, preferences, and needs.
- Personalizing and optimizing the customer journey and the shopping experience.
- Increasing customer satisfaction, retention, and loyalty.
- Improving conversion rates and revenue thus enhancing marketing and sales performance and efficiency.
- Engage customer in moments that matter with trigger-based customer Journeys.

## How to integrate data from Dynamics 365 Commerce to Dynamics 365 Customer Insights - Data

Dynamics 365 Commerce customers that already use Azure Synapse Link for Dataverse to synchronize data to their Lake, for example for BI & Analytics scenarios, can use that architecture and extend it to make data available to Dynamics 365 Customer Insights – Data.

For Dynamics 365 Commerce customers that haven't embarked on this journey, review [Finance and operation data in Azure synapse link](/power-apps/maker/data-platform/azure-synapse-link-select-fno-data) as this is the recommended data integration path.

Azure Synapse Link for Dataverse offers several options as to the format and destination where data are synced, though we recommend [Azure Synapse Link for Dataverse with Azure Data Lake](/power-apps/maker/data-platform/azure-synapse-link-data-lake) as a generic pattern that synchronizes data to the Customer's Lake (ADLS Gen2) conforming to the Common Data Model (CDM) framework.

Once Dynamics 365 Commerce data is in the Lake, it is required to prepare it with a data transformation stack of choice, so it's consumable by Dynamics 365 Customer Insights – Data.

In Dynamics 365 Commerce, data model and storage are optimized for transactional workloads, for example "Orders" are stored in multiple normalized tables. In Dynamics 365 Customer Insights - Data, data model should be optimized for analytical workloads, therefore "Orders" would be expected to be integrated as a single denormalized table. This table should include all necessary information, optionally selectively filtered by rows and columns, ideally with easily understandable column names.

:::image type="content" source="media/customer-insights-commerce-data-flow-architecture1-1.png" alt-text="High Level Architecture of Data Flow from Commerce to Customer Insights Data." lightbox="media/customer-insights-commerce-data-flow-architecture1-1.png":::

- [Finance and operation data in Azure synapse link](/power-apps/maker/data-platform/azure-synapse-link-select-fno-data) and  [Azure Synapse Link for Dataverse with Azure Data Lake](/power-apps/maker/data-platform/azure-synapse-link-data-lake)

- Data transformation and preparation such as Azure Synapse Analytics, Azure Data Factory, Azure Databricks, and external products

- [CID Connect to Azure Data Lake Storage](/dynamics365/customer-insights/data/connect-common-data-model) or [Connect to Delta tables in Azure Data Lake](/dynamics365/customer-insights/data/connect-delta-lake)

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
