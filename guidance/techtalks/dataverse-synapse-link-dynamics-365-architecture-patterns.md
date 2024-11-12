---
title: TechTalk Architecture patterns for virtual data warehousing
description: Summary of TechTalk video that talks about architecture patterns for using Synapse Link for Dataverse with Dynamics 365 apps. 
ms.date: 10/01/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Architecture patterns for virtual data warehousing with Dynamics 365 data in Azure Synapse Link

As organizations continue to evolve their data strategies, the integration of Dynamics 365 with Azure Synapse Link for Dataverse is becoming increasingly significant. This integration offers a powerful way to manage and analyze data, providing seamless transitions from traditional methods like *Export to Data Lake* to the more sophisticated Synapse Link. In this discussion, we delve into the architecture patterns and the concept of virtual data warehousing within this context. This TechTalk offers insights into how businesses can use these technologies for enhanced data management and cost efficiency.

We based this article on [a TechTalk](https://youtu.be/sLjww7Q--7Q) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media\dataverse-synapse-link-dynamics-365-arch-slide.svg" alt-text="Thumbnail of the presentation slide." link="https://youtu.be/sLjww7Q--7Q":::

The following image provides an overview of common analytics architecture patterns, Virtual Data Warehousing, Lakehouse, Cloud Data Warehousing, and Integration using TransactSQL. Each pattern is briefly described  focusing on how data is read  transformed and ingested within different warehousing solutions.

:::image type="content" source="media/dataverse-synapse-link-dynamics-365-arch-analytics-architecture-patterns.svg" alt-text="overview of common analytics architecture patterns  which include Virtual Data Warehousing, Lakehouse, Cloud Data Warehousing, and Integration using T SQL." lightbox="media/dataverse-synapse-link-dynamics-365-arch-analytics-architecture-patterns.svg":::

## The evolution from Export to Data Lake to Synapse Link

The transition from Export to Data Lake to Synapse Link for Dataverse represents a major shift in how data is managed within Dynamics 365. Previously, many organizations relied on exporting their data from Dynamics 365 into their own Azure Data Lake, where they could then use various tools like Power BI for visualization. While this method was effective, it often involved significant overhead in terms of setup, maintenance, and cost, particularly when dealing with large datasets in CSV format.

With the introduction of Synapse Link for Dataverse, Microsoft unifies the data export process across most Dynamics 365 apps. This unification simplifies data management by offering a single experience for exporting data into Azure Data Lake, now using the more efficient Delta Parquet format. This format not only reduces the total cost of ownership by minimizing storage requirements but also enhances query performance, making it a compelling option for organizations looking to optimize their data pipelines.

## Architecture patterns and virtual data warehousing

One of the key aspects of integrating Dynamics 365 data with Synapse Link is the ability to implement various architecture patterns, including virtual data warehousing. Virtual data warehousing involves creating a layer of external tables or views in Synapse serverless, allowing users to query and analyze data directly from the Data Lake without needing to physically move the data into a separate database. This approach is useful for organizations that require real-time data access across multiple systems.

In this TechTalk, we show two architecture patterns for virtual data warehousing. The first architecture pattern shows the new and simpler architecture. The second one shows the older architecture that uses the Export to data lake functionality to get data out of Dynamics 365.

First the new pattern. The following image shows an example of virtual data warehousing with Synapse Link with Synapse Spark and Synapse Serverless.

:::image type="content" source="media/dataverse-synapse-link-dynamics-365-arch-synapse-link.svg" alt-text="tekst" lightbox="media/dataverse-synapse-link-dynamics-365-arch-synapse-link.svg":::

This image illustrates the new pattern for virtual data warehousing. The pattern uses Synapse Link for direct integration for Dynamics 365 finance and operations apps. The data flows into Synapse Serverless and can be imported into Power BI. The new pattern simplifies the process by eliminating the data lake intermediary.

In the current architecture, data is exported to the Data Lake in Delta format via Synapse Link. External data can also be integrated, allowing for a comprehensive virtual data warehouse that can be queried using tools like Power BI. This setup ensures that businesses can continue to use their existing reports and dashboards with minimal modifications, even as they transition to using Synapse Link.

The following image shows the older architecture for virtual data warehousing with Synapse Link and Export to data lake with Synapse Serverless.

:::image type="content" source="media/dataverse-synapse-link-dynamics-365-arch-synapse-data-lake.svg" alt-text="Diagram with two separate data flows that are described after the image." lightbox="media/dataverse-synapse-link-dynamics-365-arch-synapse-data-lake.svg":::

This image describes a virtual data warehousing pattern using Synapse Link with Synapse Spark and Serverless  It shows data flowing from Dataverse through Synapse Link. Another flow uses Export to data lake from Dynamics 365 finance and operations apps. Both data flows land in Synapse where Delta/Parquet storage is used with Synapse Spark and Serverless SQL. The data model is then made available for import into Power BI for analysis.

## Simplifying the transition with Synapse Link

For organizations currently using Export to Data Lake, transitioning to Synapse Link is relatively straightforward. The primary step is to upgrade to Synapse Link, which allows for a seamless migration of data pipelines without the need to redevelop reports. This upgrade process is designed to maintain the integrity of existing data shapes, ensuring that reports and dashboards continue to function as expected.

Moreover, Synapse Link offers significant benefits in terms of data compression and query performance. For example, data stored in Delta format is typically much smaller and more efficient to query compared to CSV files. This compression not only reduces storage costs but also lowers the operational costs associated with querying large datasets.

## Integration with Microsoft Fabric

Another key advantage of using Synapse Link for Dataverse is its compatibility with Microsoft Fabric, a SaaS product that combines the capabilities of Synapse and Power BI. Microsoft Fabric makes it easier for organizations to gain AI-driven insights by utilizing built-in copilots, which reduces the reliance on specialized data engineers. This compatibility ensures that businesses can easily scale their data operations as they adopt new technologies within the Microsoft ecosystem.

## Practical implementation and future-proofing

Implementing Synapse Link involves a few key steps. The first step is the configuration of the Synapse Spark Pool and the setup of external tables in the Azure Synapse serverless database. Once this is done, businesses can create views that mirror their existing data models, ensuring a smooth transition from Export to Data Lake to Synapse Link. This process not only simplifies data management but also positions organizations to take full advantage of future innovations, such as the integration with Microsoft Fabric.

Furthermore, as organizations continue to refine their data strategies, the ability to partition data by year or other criteria within Delta Lake offers more opportunities for optimization. By focusing on recent data, businesses can reduce the load on their systems and improve the performance of their reports and dashboards.

## Conclusion

The shift from Export to Data Lake to Synapse Link for Dataverse marks a significant evolution in data management for Dynamics 365 users. By adopting Synapse Link, organizations can streamline their data pipelines, reduce costs, and enhance the performance of their analytics. As Microsoft continues to innovate with tools like Microsoft Fabric, businesses that transition to Synapse Link are well-positioned to capitalize on these advancements. The transition helps make sure that their data strategies remain robust and future-proof.

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [TechTalk: Transitioning to using Azure Synapse Link from exporting data to Azure Data Lake](dataverse-synapse-link-dynamics-365-transition.md)

- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)

- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)

- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
