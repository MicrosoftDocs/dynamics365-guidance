---
title: Data integration between Commerce and Customer Insights - Data.
description: Learn how to implement a scalable data integration pipeline from Dynamics 365 Commerce into Dynamics 365 Customer Insights – Data, covering key architectural patterns, data preparation techniques, and synchronization strategies for practical retail use cases.
author: OfficerSpears
contributors: tchilaud, meenulaul, ssundar, stoubia 
ms.author: raphel
ms.reviewer: edupont
ms.topic: concept-article
ms.date: 07/16/2025
---

# Data integration with Dynamics 365 Commerce and Dynamics 365 Customer Insights - Data

This article is focusing on the data integration from Dynamics 365 Commerce to Dynamics 365 Customer Insights - Data.

Integrating Dynamics 365 Commerce with Customer Insights offers retailers a powerful way to enhance their customer engagement and operational efficiency. By unifying customer data from various touchpoints, retailers can gain a comprehensive view of each customer, enabling them to deliver personalized experiences and targeted marketing campaigns. This integration allows store associates to access valuable insights into customer preferences and behaviors, helping them make informed recommendations and improve customer satisfaction. Additionally, it supports advanced clienteling, which can boost customer loyalty and drive sales by ensuring that interactions are relevant and timely. Overall, this integration helps retailers streamline processes, reduce customer churn, and maximize revenue opportunities.

Dynamics 365 Commerce is a cloud-based platform that enables retailers to deliver personalized, seamless, and omnichannel shopping experiences across various channels and touchpoints.

Part of Dynamics 365 Customer Insights - Data is the AI-powered Customer Data Platform (CDP). It helps organizations unify, enrich, and generate insights from customer data from multiple sources and gain actionable insights to drive customer engagement and loyalty. Customer Insights - Journeys is the associated journey orchestration module that can use the insights from the CDP to inform personalized marketing campaigns.

To use the full potential of both solutions, it's essential to start by bringing the data from Dynamics 365 Commerce to Dynamics 365 Customer Insights - Data as a foundation to unlock use cases and scenarios that we detail in the related articles.

For this article, we're looking at Dynamics 365 Commerce as one of the data sources that feed Dynamics 365 Customer Insights - Data and how to achieve this integration.

Due to the distinct platforms Dynamics 365 Commerce and Dynamics 365 Customer Insights operate on – and the differences between their respective data models, schemas, and database structures – the integration isn't automatic and needs to be carefully planned and executed.

Finally, with large amounts of data, there's a need for effective and scalable approaches to manage this data integration. It includes ETL/ELT (Extract, Load, Transform) methods and synchronization processes as detailed in this high-level architecture schema:

:::image type="content" source="media/customer-insights-commerce-data-flow-architecture2-1.png" alt-text="End-to-end batch data integration flow from Dynamics 365 Commerce to Dynamics 365 Customer Insights." lightbox="media/customer-insights-commerce-data-flow-architecture2-1.png":::

## Step 1 - export Dynamics 365 Commerce data to a lake

The first step of the process is to get the Dynamics 365 Commerce data into a Lake where it can be prepared to the right level (see step 2).

Several options and variations exist to accomplish this, and you're maybe already using some of those for BI & Analytics scenarios, so you might be able to benefit from those preexisting investments.

In the context of this blog post, we assume a blank state, and we focus on two reference architectures, aligned with the products' strategy and roadmap. For instance, we won't cover the "Export to Data Lake" capability of Dynamics 365 Commerce as it deprecated November 1, 2024.

These two reference architectures for data integration are respectively geared toward SaaS and PaaS, are equally valid, and are recommended as being highly scalable while offering you control over their performance.

Choosing one or the other will mainly depend on factors such as your internal strategy for SaaS versus PaaS, the preexisting investments in the corresponding technologies and the associated teams' expertise, and the total cost of ownership.

> [!IMPORTANT]
> When exporting to a Lake, you can choose both standard and custom finance and operations entities and tables.
>
> There are some limitations though to be considered with Dynamics 365 Commerce tables and entities as detailed in [tables limitations](/power-apps/maker/data-platform/azure-synapse-link-select-fno-data#known-limitations-with-finance-and-operations-tables) and [entities known limitation](/power-apps/maker/data-platform/azure-synapse-link-select-fno-data#known-limitations-with-finance-and-operations-entities).

 For example, change tracking can't be enabled for all finance and operations entities. If the chosen entity is unavailable because of the change tracking limitation, you might be able to choose the tables that comprise the data from that entity.

### Export to SaaS

This approach uses [Microsoft Dataverse direct link to Microsoft Fabric](/power-apps/maker/data-platform/azure-synapse-link-view-in-fabric) (or *Link to Fabric* for short) to make the Dynamics 365 Commerce data available in **Fabric** and **OneLake** where data preparation can happen before exposing that prepared data to Dynamics 365 Customer Insights - Data.

**OneLake** is the Lake storage layer that comes with **Microsoft Fabric** and is designed to be the single place for all your analytics data. 

All **Fabric** data items like Data Warehouses and Lakehouses store their data automatically in **OneLake** in Delta .parquet format.
​​​​​​
When using **Link to Fabric**, selected Dynamics 365 Commerce data gets stored in Delta format in an internal **Dataverse Managed Data Lake (DV MDL)** and exposed to **Fabric** as a "Shortcut", hence considered part of your **OneLake**. This means it has an impact on your Dataverse capacity consumption, so it's good practice to monitor it in Power Platform admin center.

### Export to PaaS

This approach uses the [Azure Synapse Link for Dataverse with Azure Data Lake](/power-apps/maker/data-platform/azure-synapse-link-data-lake) framework to make the Dynamics 365 Commerce data available in your **Azure Data Lake Storage gen2** (ADLS gen2) Storage Account where data preparation can happen before exposing that prepared data to Dynamics 365 Customer Insights - Data.

**Azure Synapse Link for Dataverse** is a service designed for enterprise big data analytics, providing scalable high availability together with disaster recovery capabilities.

**Azure Synapse Link for Dataverse** lets you choose what data from Finance and Operations Apps is to be continuously exported, conforming to the Common Data Model (CDM) framework, where actual data files are stored as partitioned .csv files along with manifest metadata .json files describing the content and location of the actual data files.

> [!IMPORTANT]
> As mentioned in the introduction, other variations exist such as Azure Synapse Link for Dataverse with **[Azure Synapse Workspace to directly export to a Synapse Workspace](/power-apps/maker/data-platform/azure-synapse-link-synapse)** instead of to an ADLS gen2 Storage Account.
>
> While a valid approach, especially if you're already using this pattern for other use cases, we aren't recommending it as the main PaaS approach in this article, mainly because exporting to an ADLS gen2 Storage Account instead is a more generic pattern and gives you more flexibility in the tools you can use for data preparation.

When selecting finance and operations data with [Azure Synapse Link for Dataverse with Azure Synapse Workspace](/power-apps/maker/data-platform/azure-synapse-link-select-fno-data#add-finance-and-operations-tables-in-azure-synapse-link), this feature uses your provided Synapse Spark pool to convert the CDM structures (that is, .csv + .json files) to Delta .parquet on the fly.

Delta .parquet is a good format, providing better performance overall than .csv, and we recommend using it further in this article as it relates to data preparation and integration with CI-D.

Though, having access to the .csv files in your ADLS gen2 Storage Account gives you the possibility to use any data transformation tool - including but not limited to Azure Synapse Analytics, such as Azure Data Factory, Databricks, etc. - both to convert to Delta .parquet format and do the actual data preparation, thus potentially mutualizing your integration pipelines and optimizing resource consumption.

As a final note, we cover how Customer Insights - Data reads data from Lake once it's transformed in section 3, but we won't recommend using the Azure Synapse Analytics data source connector from CI-D as it comes with some limitations, such as lack of support for incremental refreshes or for firewalled Workspaces, so you'll anyway need an ADLS gen2 Storage Account to expose data to CI-D for best integration.

## Step 2 - Prepare Dynamics 365 Commerce data in Lake

No matter if you have opted for a PaaS or SaaS approach, data flowing from Dynamics 365 Commerce to Dynamics 365 Customer Insights - Data require some specific data transformations to be usable.

Data transformation is an essential and required step because the data models in Dynamics 365 Commerce and how they would be used in Dynamics 365 Customer Insights - Data are different.

In Dynamics 365 Commerce, data model is optimized for transactional workloads, for instance "Orders" information could be represented in more than one table, related to each other, and each containing a piece of the overall order information.
On the other hand, for Dynamics 365 Customer Insights - Data, data model should be optimized for business consumption and analytical workloads, for instance "Orders" would be expected to be integrated as a single table, denormalized, containing necessary and sufficient information, and ideally with easily understandable column names from a business standpoint.

Learn more in the blog post for [Dynamics 365 Customer Insights - Data best practices for data modeling and data quality](https://community.dynamics.com/blogs/post/?postid=988fae7a-3f37-ee11-bdf4-6045bdebe084).

:::image type="content" source="media/customer-insights-commerce-data-modeling-mapping.png" alt-text="High-level data model mapping from Dynamics 365 Commerce to Dynamics 365 Customer Insights." lightbox="media/customer-insights-commerce-data-modeling-mapping.png":::

### Master data

Dynamics 365 Commerce master data typically falls into categories such as people, places, and concepts; it includes, for example,  entities such as customers, vendors, and projects.

Customers from Dynamics 365 Commerce correspond to the "Profile" category for Dynamics 365 Customer Insights - Data and will be the bare minimum master data that you'll want to bring in to contribute to **Profile** Unification.

Other master data can also be brought in depending on your business requirement, but the best practice is to only bring what will support your use cases to avoid over complexifying the CI-D data model and slowing down the system by processing unnecessary data.

### Transactional or behavioral data

Dynamics 365 Commerce orders, payments, and online storefront actions correspond to the **"Activity"** category for Dynamics 365 Customer Insights - Data.

> [!IMPORTANT]
> Other master data can fall into two categories as it relates to its data modeling for CI-D.

If the same master data is meant to be reusable across several **"Profile"** or **"Activity"** tables, bring it as a dedicated **"Supporting"** table with proper relationships to the corresponding **"Profile"** or **"Activity"**.

For example, if you have a Product table that includes several attributes (for example, Product category, Product range, Product color, etc.) that would help aggregate or filter transactions for some measures, and those products would be referenced by several **"Activities"** (for example, orders, page visits, etc.) then it makes sense to not denormalized it in each transaction table, but to bring it as a dedicated **"Supporting"** table.

On the other hand, if the master data is only needed once, consider already denormalizing it into the corresponding **"Profile"** or **"Activity"** table during data preparation, a join once upfront early in the integration will be less resource intensive overall than multiple joins, one each time you want to calculate a specific Measure or Segment in Dynamics 365 Customer Insights - Data.

For example, if you have only one simple Geography hierarchy (for example, Country, Region, City) and it's only relevant for the Customers, bring it directly as part of the Customer table contributing to Profile Unification so that it's directly included as part of the Unified Profiles.

### The number of layers in the Lake

There are two approaches to refine the data model from source (as provided by Dynamics 365 Commerce) to target (as expected by Dynamics 365 Customer Insights - Data)

:::image type="content" source="media/customer-insights-commerce-data-architecture-medallion.png" alt-text="In Lake data preparation – the medallion architecture." lightbox="media/customer-insights-commerce-data-architecture-medallion.png":::

In typical Data Lakes and Lakehouses, the preferred approach is to follow the medallion architecture principle, with three layers, from Bronze to Silver to Gold:

- Bronze is the exact copy of the data as in the source (that is, CDM .csv + .json or Delta exported from Dynamics 365 Commerce depending on the export approach)
- Silver is an intermediary layer where data from all sources are going through similar standardization, normalization, and data quality steps (for example, ensuring that all date/time fields are converted into a similar format, with proper time zone and proper default value, etc.) as well as format conversion (that is, from CDM .csv + .json to Delta .parquet in our context if needed)
- Gold is the final layer where data has been combined, denormalized, pivoted, etc. and is fit for purpose to a specific consumption scenario (that is, Dynamics 365 Customer Insights – Data)

This is a recommended approach to mutualize efforts and ensure consistency across your whole data estate in the Lake, so this is the default pattern we recommend, and that you might already be using if you have an existing Lake.

Read more details on the medallion architecture in the context of Fabric or Databricks as examples.

:::image type="content" source="media/customer-insights-commerce-data-architecture-simplified-integration.png" alt-text="In Lake data preparation – a simplified integration architecture." lightbox="media/customer-insights-commerce-data-architecture-simplified-integration.png":::

As a fallback, if you don't have an existing Data Lake or Lakehouse medallion architecture in place that you would use to support the data integration between Dynamics 365 Commerce to Dynamics 365 Customer Insights - Data, you could opt for a simplified integration architecture with only two layers in your Lake:

- Source layer corresponds to the Bronze layer of the medallion architecture
- Target layer combines the data preparation and transformation tasks from the Silver and Gold layers of the medallion architecture in one step

This approach makes sense if you don't have, nor anticipate having, any other use cases (for example, BI & Analytics) that would need to use Dynamics 365 Commerce data and if you want to reduce a little bit the footprint of your data integration by sacrificing its flexibility and extensibility.

### ​​​​​​Sample Fabric notebook for the SaaS oriented approach

Below is a sample Fabric notebook to prepare the customer and transactions data to be made available to Dynamics 365 Customer Insights - Data. The code is shared under the sample code notice.

The sample notebook combines the data from multiple Dynamics 365 Commerce tables(Customer - DirPartyTable,LogisticsPostalAddress,LogisticsLocation,DirPersonName etc. Transactions - SaleTables,SalesLine etc.) and transforms and filters the data and converts the data to a denormalized structure to be consumed by Dynamics 365 Customer Insights.

Find a Jupyter notebook in the GitHub repo at [CustomerInsightsDataPrep.ipynb](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Commerce/BetterTogether/).

## Step 3 - Read prepared data from Lake with Dynamics 365 Customer Insights - Data

As mentioned in the previous section, the recommended format for storing data that has been prepared for Dynamics 365 Customer Insights - Data consumption is Delta tables (.parquet files).

Delta is a format that offers best performance overall, and brings ACID (Atomicity, Consistency, Isolation, Durability) transactions to big data workloads, eliminating the legacy requirement of big data architecture that needed to reprocess all data with every job.

Dynamics 365 Customer Insights - Data is evolving to be fully Delta compatible for its internal jobs as per [Accelerate time to insights with data in Delta Lake format](/dynamics365/release-plan/2024wave2/customer-insights/dynamics365-customer-insights-data/planned-features). If your data source is also Delta, and if you're using the appropriate data source connector, you benefit from its advantage all the way through.

By licensing entitlement, you can refresh your Dynamics 365 Customer Insights - Data instance up to four times a day, and even if most batch processing and insights calculation don't require such a frequency, using Delta all the way through helps you get the most out of the platform by reducing the time required for a single end-to-end refresh.

This is why we strongly recommend that you have your prepared data in your Data Lake or Lakehouse in this format and to use the corresponding Dynamics 365 Customer Insights - Data  [Connect to Delta tables](/dynamics365/customer-insights/data/connect-delta-lake) data source connector.

With this pattern, Dynamics 365 Customer Insights - Data doesn't move or copy the data source data but simply reads it from the Lake (that is, Gold layer) when one of its jobs needs it.

> [!IMPORTANT]
> If you opted for a SaaS approach with Fabric and OneLake for data preparation, note that Dynamics 365 Customer Insights - Data does not support this direct connection as of today.

You can create a PaaS ADLS gen2 Storage Account, linked to your Fabric workspace as a shortcut, that will serve the purpose of the Gold layer to expose data to Dynamics 365 Customer Insights - Data and that will be read with the same recommended CI-D data source connector, that is, [Connect to Delta tables](/dynamics365/customer-insights/data/connect-delta-lake).

We advice against the use of one of the Power Query connectors to ingest data from Fabric through its SQL endpoint as this will imply extra data movement, latency, and will break the Delta capabilities of Dynamics 365 Customer Insights - Data.

## Step 4 - customers, unified customer profiles, and contacts

In this article and the related article focus mainly on retailers' scenarios, where achieving a better understanding of your consumers and reaching out to them through personalized marketing campaigns is the main goal.

As such, it's important to understand and clarify how this consumer is represented and will flow between the Apps.

Each app has its distinct definition and structure to support this:

- In Dynamics 365 Commerce, Customer profile is a single functional entity and normalized into several tables.
- In Dynamics 365 Customer Insights - Data, the Customer Profile is the table in which  CI-D reconcile the different demographic data points from the different source systems through the [Customer Profile Unification](/dynamics365/customer-insights/data/data-unification) process, and is connected to the associated transactional or behavioral Activities to help generate Insights.
- In Dynamics 365 Customer Insights - Journeys, the Contact table in Dataverse is the natural starting point to build either Segment-based or Trigger-based Journeys to reach out to your consumers.  

  The Contact table is also widely used in other Dynamics 365 apps such as Dynamics 365 Sales, and so on.

It's critical to ensure that these three structures are kept in synchronization and are consistent with each other in the three apps to unlock all scenarios we'll develop in the rest of the series, and to achieve this, we recommend implementing the approach described in the following subsections as per this schema:

:::image type="content" source="media/customer-insights-commerce-data-flow-architecture2-4.png" alt-text="Architecture for Customers, Unified Customer Profiles and Contacts integration." lightbox="media/customer-insights-commerce-data-flow-architecture2-4.png":::

### Between Dynamics 365 Commerce and Dynamics 365 Customer Insights - Data

This path of the integration corresponds to the approach that was described in the earlier sections in this article for all Dynamics 365 Commerce data, but here zoomed in specifically to just the Customer entity from Dynamics 365 Commerce.

It's important to ensure that all relevant information from the Customer entity in Dynamics 365 Commerce can flow to Dynamics 365 Customer Insights - Data with full control on data preparation and data quality if the synchronization mechanism that is described in the next section isn't enough.

### Between Dynamics 365 Commerce and Dataverse

This path of the integration is critical and mandatory to ensure that the Dataverse Contact table is populated and can be used by Dynamics 365 Customer Insights - Journeys (and other customer engagement apps).

Though, it isn't necessarily sufficient for Dynamics 365 Customer Insights - Data, as the recommended approach is to use **Dual-write** which doesn't necessarily map all information between the Dynamics 365 Commerce Customer entity and the Dataverse Contact table. We still recommend also using in parallel the method described in earlier.

[Dual-write](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview) is an out-of-box infrastructure that provides near-real-time integration between customer engagement apps and finance and operations apps.

Dual-write provides tightly coupled, bidirectional integration between finance and operations apps and Dataverse. Any data change in finance and operations apps causes writes to Dataverse, and any data change in Dataverse causes writes to finance and operations apps. This automated data flow provides an integrated user experience across the apps.

In our context, we recommend using the [Integrated customer master](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/customer-mapping) with the [Customers V3 (contacts)](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/mapping-reference#116) mapping template.

> [!IMPORTANT]
> When enabling data entities for **Dual-write**, always test in a sandbox to ensure that performance and business continuity support your heaviest workloads.

There are some [known limitations](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/sync-limits) using **Dual-write**, and some [constraints when it comes to initial synchronization](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/initial-sync-guidance).

If you don't want to use Dual-write then you should design your own custom integration from commerce to Dataverse contact entity.

### Between Dataverse and Dynamics 365 Customer Insights - Data

This path of the integration could feel redundant with what is described in subsection 4.1, though it's important for two reasons:

- Some relevant Contact information and attributes could be maintained and live in parallel in the Dataverse Contact table while not being mapped and synchronized back to the Dynamics 365 Commerce Customer entity as part of the Dual-write setup. But we would still want that information that only exists in the Contact table to be available as well in Dynamics 365 Customer Insights - Data
- It's a pre-requisite to achieve the "closed loop" between all structures in the three apps, namely between the Dynamics 365 Customer Insights - Data Customer Profile table and the Dataverse Contact table used by Dynamics 365 Customer Insights - Journeys. Learn more in the [Between Dynamics 365 Commerce and Dynamics 365 Customer Insights - Data](#between-dynamics-365-commerce-and-dynamics-365-customer-insights---data) section.

To achieve this integration, we recommend using the [Microsoft Dataverse](/dynamics365/customer-insights/data/connect-dataverse) data source connector from Dynamics 365 Customer Insights - Data.

> [!IMPORTANT]
> As of today, this connector doesn't offer yet fine control over data selection and brings the table "as they are."

The connector evolves to offer more flexibility and even better performance end-to-end by embracing Delta format behind the scenes as documented in this [release plan article](/dynamics365/release-plan/2024wave1/customer-insights/dynamics365-customer-insights-data/planned-features)

### Between Dynamics 365 Customer Insights - Data and Dynamics 365 Customer Insights - Journeys

This path of the integration is automatic and doesn't require any specific configuration if its prerequisites are respected.

Having this integration between Customer Profiles from Dynamics 365 Customer Insights - Data and Contacts in Dataverse unlock many scenarios by ensuring that Dynamics 365 Customer Insights - Journeys can operate directly on Contacts, enriched with extra attributes and insights from Dynamics 365 Customer Insights - Data Customer Profiles, be it for segment creation, email personalization, or journey branching.

[CustomerId backstamping](/dynamics365/customer-insights/data/integrate-d365-apps) is the name of this automatic process that will ensure that each Contact in Dataverse has a relationship back to its corresponding Customer Profile. CustomerId being the name of the Primary Key generated by Dynamics 365 Customer Insights - Data to uniquely identify a Customer Profile.

The two prerequisites are that the Contact table is ingested in Dynamics 365 Customer Insights - Data with one of the supported data source connectors as described in earlier run through the Profile Unification with its Primary Key (ContactId) properly setup

> [!IMPORTANT]
> While the Contact table from Dataverse could also be ingested in Dynamics 365 Customer Insights - Data through the [corresponding power query connector](/power-query/connectors/dataverse), and preserve the CustomerId backstamping process, we don't recommend this approach as it doesn't scale and perform as well as using the Microsoft Dataverse data source connector. It would also break the capability for Customer Insights - Data profile Unification to use the Delta format capabilities for improved performances.

We could only recommend this approach through Power Query if your Contact table volume isn't too high (for example, < 5 million records), that you don't have to use complex transformation or joins in your Power Query dataflow, and that you do need Optionset labels and not just Optionset key values.

> [!NOTE]
> Dynamics 365 Customer Insights - Journeys can also operate on segments of Customer Profiles created and shared from Dynamics 365 Customer Insights - Data, but it's not the most flexible path and should be recommended mostly for scenarios where some CI-D Customer Profiles are created from an external source system without a matching Contact in Dataverse.

## Step 5 - recap

Bringing everything together, the end-to-end data integration architecture would respectively look like this for the two approaches:

:::image type="content" source="media/customer-insights-commerce-data-flow-architecture2-5.png" alt-text="SaaS oriented end-to-end data integration architecture." lightbox="media/customer-insights-commerce-data-flow-architecture2-5.png":::

:::image type="content" source="media/customer-insights-commerce-data-flow-architecture2-5b.png" alt-text="PaaS oriented end-to-end data integration architecture." lightbox="media/customer-insights-commerce-data-flow-architecture2-5b.png":::

## Related content

- [Overview of data integration between Dynamics 365 Commerce and Customer Insights](data-integration-commerce-customer-insights.md)  
- [Data integration from Dynamics 365 Commerce to Customer Insights - Journeys in near real-time](data-integration-commerce-customer-insights-journeys.md)  

## Contributors in alphabetic order

- [Meenu Laul](https://www.linkedin.com/in/meenu-laul-6590bb17/) \| Senior Solution Architect

- [Raphael Vonderküste](https://www.linkedin.com/in/raphaelvdk/) \| Principal Program Manager

- [Sarah Toubia](https://www.linkedin.com/in/sarah-toubia/) \| Senior Solution Architect

- [Srinath Sundaresan](https://www.linkedin.com/in/srinath-sundaresan-8b05284b/) \| Senior Solution Architect

- [Thomas Chilaud](https://www.linkedin.com/in/thomas-chilaud/) \| Principal Solution Architect
