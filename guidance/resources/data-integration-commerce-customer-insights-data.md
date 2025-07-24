---
title: Data integration between Commerce and Customer Insights - Data.
description: Learn how to implement a scalable data integration pipeline from Dynamics 365 Commerce into Dynamics 365 Customer Insights – Data, covering key architectural patterns, data preparation techniques, and synchronization strategies for practical retail use cases.
author: OfficerSpears
contributors: tchilaud, meenulaul, ssundar, stoubia 
ms.author: raphel
ms.reviewer: edupont
ms.topic: concept-article
ms.date: 07/22/2025
---

# Data integration with Dynamics 365 Commerce and Dynamics 365 Customer Insights - Data

This article focuses on data integration from Dynamics 365 Commerce to Dynamics 365 Customer Insights - Data.

Integrating Dynamics 365 Commerce with Customer Insights lets retailers enhance customer engagement and operational efficiency. By unifying customer data from various touchpoints, retailers get a comprehensive view of each customer. This lets them deliver personalized experiences and targeted marketing campaigns. The integration gives store associates valuable insights into customer preferences and behaviors, helping them make informed recommendations and improve customer satisfaction. It also supports advanced clienteling, boosting customer loyalty and driving sales by ensuring interactions are relevant and timely. Overall, this integration streamlines processes, reduces customer churn, and maximizes revenue opportunities.

Dynamics 365 Commerce is a cloud-based platform that enables retailers to deliver personalized, seamless, and omnichannel shopping experiences across various channels and touchpoints.

Dynamics 365 Customer Insights - Data includes the AI-powered Customer Data Platform (CDP). It lets organizations unify, enrich, and generate insights from customer data across multiple sources, helping them drive customer engagement and loyalty. Customer Insights - Journeys is the associated journey orchestration module that can use the insights from the CDP to inform personalized marketing campaigns.

To unlock the full potential of both solutions, bring data from Dynamics 365 Commerce to Dynamics 365 Customer Insights - Data as a foundation for use cases and scenarios detailed in related articles.

This article examines Dynamics 365 Commerce as one of the data sources that feed Dynamics 365 Customer Insights - Data and explains how to achieve this integration.

Because Dynamics 365 Commerce and Dynamics 365 Customer Insights operate on distinct platforms—and their data models, schemas, and database structures differ—the integration isn't automatic and requires careful planning and execution.

Managing large amounts of data requires effective and scalable approaches, such as ETL/ELT (extract, load, transform) methods and synchronization processes, as shown in the following high-level architecture schema:

:::image type="content" source="media/customer-insights-commerce-data-flow-architecture2-1.png" alt-text="End-to-end batch data integration flow from Dynamics 365 Commerce to Dynamics 365 Customer Insights." lightbox="media/customer-insights-commerce-data-flow-architecture2-1.png":::

## Step 1 - Export Dynamics 365 Commerce data to a lake

The first step is to get the Dynamics 365 Commerce data into a lake where it can be prepared to the right level as described in the [Step 2 - Prepare Dynamics 365 Commerce data in Lake](#step-2---prepare-dynamics-365-commerce-data-in-lake) section. There are several options and variations that support this step. If you already use some of them for BI and analytics scenarios, you can benefit from those preexisting investments.

In this article, we assume a blank state, and we focus on two reference architectures that reflect a solid path forward for implementations. For instance, this article doesn't cover the deprecated [Export to Data Lake](/dynamics365/fin-ops-core/dev-itpro/data-entities/finance-data-azure-data-lake) capability for finance operations apps.

These two reference architectures for data integration are respectively geared toward SaaS and PaaS, and are equally valid. Both are highly scalable and offer you control over their performance.

Choosing one or the other mainly depends on factors such as the following list:

- The internal strategy for SaaS versus PaaS  
- Preexisting investments in the corresponding technologies  
- The associated teams' expertise  
- The total cost of ownership.

> [!IMPORTANT]
> When exporting to a lake, you can choose both standard and custom finance and operations entities and tables. There are some limitations though to be considered with Dynamics 365 Commerce tables and entities as detailed in [tables limitations](/power-apps/maker/data-platform/azure-synapse-link-select-fno-data#known-limitations-with-finance-and-operations-tables) and [entities known limitation](/power-apps/maker/data-platform/azure-synapse-link-select-fno-data#known-limitations-with-finance-and-operations-entities).

For example, change tracking can't be enabled for all finance and operations entities. If the chosen entity is unavailable because of the change tracking limitation, you might be able to choose the tables that comprise the data from that entity.

### Export to SaaS

This approach uses [Microsoft Dataverse direct link to Microsoft Fabric](/power-apps/maker/data-platform/azure-synapse-link-view-in-fabric) (or *Link to Fabric* for short) to make the Dynamics 365 Commerce data available in Fabric and OneLake. In this scenario, data preparation happens before exposing that prepared data to Dynamics 365 Customer Insights - Data.

- OneLake is the Lake storage layer that comes with **Microsoft Fabric** and is designed to be the single place for all your analytics data.  

- All Fabric data items, such as Data Warehouses and Lakehouses, store their data automatically in OneLake in the Delta `.parquet` format.
​​​​​​
When you use the *Link to Fabric* capability, selected Dynamics 365 Commerce data gets stored in Delta format in an internal Dataverse Managed Data Lake (DV MDL) and exposed to Fabric as a *shortcut*. That way, the data is considered part of your **OneLake**. This link affects your Dataverse capacity consumption, so it's good practice to monitor it in Power Platform admin center.

### Export to PaaS

This approach uses the [Azure Synapse Link for Dataverse with Azure Data Lake](/power-apps/maker/data-platform/azure-synapse-link-data-lake) framework to make the Dynamics 365 Commerce data available in your Azure Data Lake Storage Gen2 (ADLS gen2) storage account. In this scenario, data preparation can happen before you expose that prepared data to Dynamics 365 Customer Insights - Data.

Azure Synapse Link for Dataverse is a service designed for enterprise big data analytics, providing scalable high availability together with disaster recovery capabilities. Azure Synapse Link for Dataverse lets you choose what data from finance and operations apps is continuously exported and conforms to the Common Data Model (CDM) framework. In the Common Data Model, the actual data files are stored as partitioned .csv files with manifest metadata .json files that describe the content and location of the actual data files.

> [!NOTE]
> As mentioned, there are alternatives, such as Azure Synapse Link for Dataverse with [Azure Synapse Workspace to directly export to a Synapse Workspace](/power-apps/maker/data-platform/azure-synapse-link-synapse). If you already use another type of integration, you don't have to change anything. But this article recommends ADLS gen2 as the main PaaS approach, because it's a more generic pattern that gives you more flexibility in the tools you can use for data preparation.

In the scenario with [Azure Synapse Link for Dataverse with Azure Synapse Workspace](/power-apps/maker/data-platform/azure-synapse-link-select-fno-data#add-finance-and-operations-tables-in-azure-synapse-link), this feature uses your provided Synapse Spark pool to convert the  .csv + .json files from Common Data Model to Delta .parquet on the fly.  

Delta .parquet is a good format, providing better performance overall than .csv. We recommend using it further in this article as it relates to data preparation and integration with Customer Insights - Data.

The .csv files in your ADLS gen2 storage account let you use any data transformation tool, such as Azure Synapse Analytics, Azure Data Factory, and Databricks, to convert the data to the Delta .parquet format. You can then prepare the data,  potentially streamline your integration pipelines, and optimize resource consumption.

The [Step 3](#step-3---read-prepared-data-from-lake-with-dynamics-365-customer-insights---data) section covers how Customer Insights - Data reads data from the lake after the transformation. However, we recommend an ADLS gen2 storage account to expose data to Customer Insights - Data for the best integration.

## Step 2 - Prepare Dynamics 365 Commerce data in Lake

Whether you use a PaaS or SaaS approach, data flowing from Dynamics 365 Commerce to Dynamics 365 Customer Insights - Data requires specific data transformations to be usable.

Data transformation is essential because the data models in Dynamics 365 Commerce and Dynamics 365 Customer Insights - Data are different.

In Dynamics 365 Commerce, the data model is optimized for transactional workloads. For instance, the `Orders` information might be represented in more than one table, related to each other, with each containing a piece of the overall order information.

In Dynamics 365 Customer Insights - Data, the data model should be optimized for business consumption and analytical workloads. For example, you should implement `Orders` as a single, denormalized table that has the necessary information, and with easily understandable column names from a business standpoint.

Learn more in the blog post [Dynamics 365 Customer Insights - Data best practices for data modeling and data quality](https://community.dynamics.com/blogs/post/?postid=988fae7a-3f37-ee11-bdf4-6045bdebe084).

:::image type="content" source="media/customer-insights-commerce-data-modeling-mapping.png" alt-text="High-level data model mapping from Dynamics 365 Commerce to Dynamics 365 Customer Insights." lightbox="media/customer-insights-commerce-data-modeling-mapping.png":::

### Master data

Dynamics 365 Commerce master data typically falls into categories such as people, places, and concepts; it includes, for example,  entities such as customers, vendors, and projects.

Customers from Dynamics 365 Commerce correspond to the **Profile** category for Dynamics 365 Customer Insights - Data and are the minimum master data needed to contribute to **Profile** Unification.

Other master data can be included based on business requirements. However, it's a best practice to bring only what supports your use cases to reduce the risk of complicating the Customer Insights - Data data model. Avoid slowing the system by processing unnecessary data.

### Transactional or behavioral data

Dynamics 365 Commerce orders, payments, and online storefront actions correspond to the **Activity** category for Dynamics 365 Customer Insights - Data.

> [!IMPORTANT]
> Other master data can fall into two categories as it relates to its data modeling for Customer Insights - Data.

If the same master data is reusable across several **Profile** or **Activity** tables, include it as a dedicated **Supporting** table with proper relationships to the corresponding **Profile** or **Activity**.

For example, you have a `Product` table that includes several attributes, such as Product category, Product range, Product color, and so on. These attributes help aggregate or filter transactions for some measures. The actual products are referenced by several activities, such as orders or page visits. In this scenario, it makes sense not to denormalize it in each transaction table, but to bring it as a dedicated supporting table.

If the master data is only needed once, consider denormalizing it into the corresponding **Profile** or **Activity** table during data preparation. A single upfront join is less resource intensive than multiple joins for each calculation of a specific measure or segment in Customer Insights.

For example, if you have only one simple Geography hierarchy (for example, Country, Region, City) and it's only relevant for the Customers, bring it directly as part of the `Customer` table contributing to Profile Unification so that it's part of the unified profiles.

### The number of layers in the Lake

There are two approaches to refining the data model from the source, Dynamics 365 Commerce, to the target, Dynamics 365 Customer Insights - Data.

:::image type="content" source="media/customer-insights-commerce-data-architecture-medallion.png" alt-text="In Lake data preparation – the medallion architecture." lightbox="media/customer-insights-commerce-data-architecture-medallion.png":::

In typical Data Lakes and Lakehouses, the preferred approach is to follow the medallion architecture principle, with three layers, from Bronze to Silver to Gold:

- *Bronze* is the exact copy of the data as in the source  

  For example, Common Data Model data in .csv and .json files, or Delta exported from Dynamics 365 Commerce depending on the export approach.
- *Silver* is an intermediary layer where data from all sources are going through similar standardization, normalization, and data quality steps  

  For example, ensuring that all date/time fields are converted into a similar format, with proper time zone and proper default value, and so on, as well as format conversion, that is, from .csv and .json to Delta .parquet in our context if needed.
- *Gold* is the final layer where data is combined, denormalized, pivoted, and so on  

  This layer is fit for purpose to a specific consumption scenario, such as Dynamics 365 Customer Insights – Data.

The layers form a recommended approach to mutualize efforts and ensure consistency across your whole data estate in the Lake. It's the default pattern we recommend, and that you might already be using if you have an existing Lake. Learn more about the medallion architecture in the context of [Fabric](/fabric/onelake/onelake-medallion-lakehouse-architecture#medallion-architecture-in-fabric) or [Azure Databricks](/azure/databricks/lakehouse/medallion) as examples.

:::image type="content" source="media/customer-insights-commerce-data-architecture-simplified-integration.png" alt-text="In Lake data preparation – a simplified integration architecture." lightbox="media/customer-insights-commerce-data-architecture-simplified-integration.png":::

If you don't have an existing Data Lake or Lakehouse medallion architecture, you can opt for a simplified integration architecture with only two layers in your Lake:

- A source layer that corresponds to the Bronze layer of the medallion architecture
- A target layer that combines the data preparation and transformation tasks from the Silver and Gold layers of the medallion architecture in one step

This approach makes sense if you don't have other use cases, such as BI and analytics, that need data from Dynamics 365 Commerce. It also makes sense if you want to reduce a little bit the footprint of your data integration by sacrificing its flexibility and extensibility.

### ​​​​​​Sample Fabric notebook for the SaaS oriented approach

Microsoft provides a sample Fabric notebook to prepare customer and transaction data for Dynamics 365 Customer Insights - Data. The code is shared under the sample code notice in GitHub. The sample notebook combines the data from multiple Dynamics 365 Commerce tables (customer data such as `DirPartyTable`, `LogisticsPostalAddress`, `LogisticsLocation`, `DirPersonName`, and so on, and transactions in `SaleTables`, `SalesLine`, and so on). The notebook sample transforms and filters the data, and then  converts the data to a denormalized structure that Dynamics 365 Customer Insights can then consume.

Find the Jupyter notebook in the GitHub repo at [CustomerInsightsDataPrep.ipynb](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Commerce/BetterTogether/).

## Step 3 - Read prepared data from Lake with Dynamics 365 Customer Insights - Data

As mentioned in the [Step 2](#step-2---prepare-dynamics-365-commerce-data-in-lake) section, Delta tables (.parquet files) are the recommended format for storing data for use in Dynamics 365 Customer Insights - Data.

Delta is a format that offers the best performance overall and brings ACID (atomicity, consistency, isolation, durability) transactions to big data workloads. That approach eliminates the legacy requirement of big data architecture that would reprocess all data with every job.

Dynamics 365 Customer Insights - Data evolves to be fully Delta compatible for its internal jobs as described in [Accelerate time to insights with data in Delta Lake format](/dynamics365/release-plan/2024wave2/customer-insights/dynamics365-customer-insights-data/planned-features). If your data source is also Delta, and if you're using the appropriate data source connector, you benefit from its advantage all the way through.

With licensing entitlement, you refresh your Dynamics 365 Customer Insights - Data instance up to four times a day. Even if most batch processing and insights calculation don't require such a frequency, using Delta all the way through helps you get the most out of the platform by reducing the time required for a single end-to-end refresh.

We strongly recommend storing your prepared data in your Data Lake or Lakehouse in this format and using the corresponding Dynamics 365 Customer Insights - Data [Connect to Delta tables](/dynamics365/customer-insights/data/connect-delta-lake) data source connector.

With this pattern, Dynamics 365 Customer Insights - Data doesn't move or copy the data source data. The app simply reads it from the Lake's Gold layer when one of its jobs needs it.

> [!NOTE]
> If you opted for the SaaS approach with Fabric and OneLake for data preparation, Dynamics 365 Customer Insights - Data doesn't support this direct connection anymore.

You can create a PaaS ADLS gen2 storage account that you link to your Fabric workspace as a shortcut. This connection serves the purpose of the Gold layer to expose data to Dynamics 365 Customer Insights - Data, and the data is read with the same Customer Insights data source connector. Learn more at [Connect to Delta tables](/dynamics365/customer-insights/data/connect-delta-lake).

We advise against using Power Query connectors to ingest data from Fabric through its SQL endpoint because this breaks the Delta capabilities of Dynamics 365 Customer Insights - Data.

## Step 4 - Customers, unified customer profiles, and contacts

This article focuses mainly on retailer scenarios, where understanding consumers and reaching them through personalized marketing campaigns is the goal. As such, it's important to understand and clarify how this consumer is represented and flows between the apps.

Each app has a distinct definition and structure to support these scenarios:

- In Dynamics 365 Commerce, `Customer profile` is a single functional entity and normalized into several tables.
- In Dynamics 365 Customer Insights - Data, `Customer Profile` is the table where Customer Insights - Data reconcile the different demographic data points from the different source systems through the [Customer Profile Unification](/dynamics365/customer-insights/data/data-unification) process. It connects to the associated transactional or behavioral activities to help generate insights.
- In Dynamics 365 Customer Insights - Journeys, the `Contact` table in Dataverse is the natural starting point to build either segment-based or trigger-based journeys to reach out to consumers.  

  The Contact table is also widely used in other Dynamics 365 apps such as Dynamics 365 Sales, and so on.

Synchronizing these three structures is critical to ensure consistent data across the apps. We recommend implementing the approach described in the following subsections as illustrated in the following architecture:

:::image type="content" source="media/customer-insights-commerce-data-flow-architecture2-4.png" alt-text="Architecture for integrating Customer data with data from Customer Profiles and Contacts in Dataverse." lightbox="media/customer-insights-commerce-data-flow-architecture2-4.png":::

### Between Dynamics 365 Commerce and Dynamics 365 Customer Insights - Data

This path of the integration corresponds to the approach that was described in the earlier sections in this article for all Dynamics 365 Commerce data. But here we zoom in on just the Customer entity from Dynamics 365 Commerce.

> [!NOTE]
> Make sure that all relevant information from the Customer entity in Dynamics 365 Commerce can flow to Dynamics 365 Customer Insights - Data with full control on data preparation and data quality if the synchronization mechanism isn't enough.

### Between Dynamics 365 Commerce and Dataverse

This path of the integration is critical and mandatory to ensure that the Dataverse table `Contact` is populated, and that Dynamics 365 Customer Insights - Journeys and other customer engagement apps can access and use the data.

This approach isn't always sufficient for Dynamics 365 Customer Insights - Data because *Dual-write* doesn't map all information between the Dynamics 365 Commerce Customer entity and the Dataverse Contact table. We still recommend also using in parallel the method described in earlier.

[Dual-write](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview) is an out-of-box infrastructure that provides near-real-time integration between customer engagement apps and finance and operations apps. Dual-write provides tightly coupled, bidirectional integration between finance and operations apps and Dataverse. Any data change in finance and operations apps causes writes to Dataverse, and any data change in Dataverse causes writes to finance and operations apps. This automated data flow provides an integrated user experience across the apps.

In our context, we recommend using the [Integrated customer master](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/customer-mapping) with the [Customers V3 (contacts)](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/mapping-reference#116) mapping template.

> [!IMPORTANT]
> When you enable data entities for dual-write, always test in a sandbox to ensure that the performance and business continuity support your heaviest workloads.

There are some [known limitations](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/sync-limits) using dual-write, and some [constraints to the initial synchronization](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/initial-sync-guidance).

If you don't want to use dual-write, then design your own custom integration from Commerce to Dataverse's `Contact` entity.

### Between Dataverse and Dynamics 365 Customer Insights - Data

This integration path might seem redundant with subsection 4.1, but it's important for two reasons:

- Some relevant `Contact` information and attributes could be maintained and live in parallel in the `Contact` table in Dataverse while not being mapped and synchronized back to the `Customer` entity as part of the dual-write setup. But we would still want that information that only exists in the `Contact` table to be available as well in Dynamics 365 Customer Insights - Data.
- It's a prerequisite to achieve the "closed loop" between all structures in the three apps, namely between the Dynamics 365 Customer Insights - Data Customer Profile table and the Dataverse Contact table used by Dynamics 365 Customer Insights - Journeys. Learn more in the [Between Dynamics 365 Commerce and Dynamics 365 Customer Insights - Data](#between-dynamics-365-commerce-and-dynamics-365-customer-insights---data) section.

To achieve this integration, we recommend using the [Dataverse data source connector](/dynamics365/customer-insights/data/connect-dataverse) from Dynamics 365 Customer Insights - Data.

> [!IMPORTANT]
> Currently, this connector doesn't yet offer fine control over data selection and brings the table data as-is.

The connector evolves to offer more flexibility and even better performance end-to-end by embracing Delta format behind the scenes as documented in this [release plan article](/dynamics365/release-plan/2024wave1/customer-insights/dynamics365-customer-insights-data/planned-features)

### Between Dynamics 365 Customer Insights - Data and Dynamics 365 Customer Insights - Journeys

This path of the integration is automatic and doesn't require any specific configuration if its prerequisites are respected.

This integration between Customer Profiles in Dynamics 365 Customer Insights - Data and Contacts in Dataverse unlocks many scenarios. It ensures that Dynamics 365 Customer Insights - Journeys can operate directly on Contacts enriched with extra attributes and insights from Customer Profiles, supporting segment creation, email personalization, and journey branching.

[CustomerId backstamping](/dynamics365/customer-insights/data/integrate-d365-apps) is the name of this automatic process that will ensure that each contact in Dataverse has a relationship back to its corresponding customer profile. The `CustomerId` field is the primary key that uniquely identifies a customer profile.

The two prerequisites are that the `Contact` table is ingested in Dynamics 365 Customer Insights - Data with one of the supported data source connectors, and that the profile unification is set up correctly with its primary key, `ContactId`.

> [!IMPORTANT]
> While you can also ingest the `Contact` table from Dataverse in Dynamics 365 Customer Insights - Data through the [corresponding power query connector](/power-query/connectors/dataverse) and preserve the `CustomerId` backstamping process, we don't recommend this approach. You gain better performance with the Dataverse data source connector. It would also break the capability for Customer Insights - Data profile Unification to use the Delta format capabilities for improved performances.

Use this approach through Power Query if your `Contact` table volume is below 5 million records. We also recommend that you don't use complex transformation or joins in your Power Query dataflow, and that you do need `Optionset` labels and not just `Optionset` key values.

> [!NOTE]
> Dynamics 365 Customer Insights - Journeys can also operate on segments of customer profiles created and shared from Dynamics 365 Customer Insights - Data. However, it's not the most flexible path. We recommend that you mainly use it for scenarios where some customer profiles in Customer Insights - Data are created from an external source system without a matching entry in the `Contact` table in Dataverse.

## Step 5 – recap

This section brings everything together. For the two approaches, the end-to-end data integration architecture looks like these illustrations.

First, the SaaS approach.

:::image type="content" source="media/customer-insights-commerce-data-flow-architecture2-5.png" alt-text="Diagram that shows SaaS-oriented end-to-end data integration architecture." lightbox="media/customer-insights-commerce-data-flow-architecture2-5.png":::

Second, the PaaS approach.

:::image type="content" source="media/customer-insights-commerce-data-flow-architecture2-5b.png" alt-text="Diagram that shows PaaS-oriented end-to-end data integration architecture." lightbox="media/customer-insights-commerce-data-flow-architecture2-5b.png":::

## Related content

- [Overview of data integration between Dynamics 365 Commerce and Customer Insights](data-integration-commerce-customer-insights.md)  
- [Data integration from Dynamics 365 Commerce to Customer Insights - Journeys in near real-time](data-integration-commerce-customer-insights-journeys.md)  

## Contributors in alphabetic order

- [Meenu Laul](https://www.linkedin.com/in/meenu-laul-6590bb17/) \| Senior Solution Architect

- [Raphael Vonderküste](https://www.linkedin.com/in/raphaelvdk/) \| Principal Program Manager

- [Sarah Toubia](https://www.linkedin.com/in/sarah-toubia/) \| Senior Solution Architect

- [Srinath Sundaresan](https://www.linkedin.com/in/srinath-sundaresan-8b05284b/) \| Senior Solution Architect

- [Thomas Chilaud](https://www.linkedin.com/in/thomas-chilaud/) \| Principal Solution Architect
