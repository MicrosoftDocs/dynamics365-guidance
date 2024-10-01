---
title: TechTalk Cloud data warehousing with Dynamics 365 data
description: Summary of TechTalk video that talks about cloud data warehousing and integration of Dynamics 365 data with Azure Synapse Link for Dataverse.
ms.date: 10/01/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Cloud data warehousing for Dynamics 365 data with Azure Synapse Link for Dataverse

In the rapidly evolving world of cloud data warehousing, Azure Synapse Link for Dataverse emerged as a powerful tool for businesses seeking seamless integration and incremental data ingestion. This article delves into the key aspects of transitioning from traditional data export methods to using Synapse Link, a platform designed to enhance cloud data warehousing by simplifying data handling and improving performance.

We based this article on [a TechTalk](https://youtu.be/tsgj1wDb7-k) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media\DTV022EXT-slide.svg" alt-text="Thumbnail of the presentation slide." link="https://youtu.be/tsgj1wDb7-k":::

## Understanding the transition to Synapse Link

Many businesses, particularly those using Dynamics 365, are familiar with the Export to Data Lake feature. This legacy system allowed for the extraction of data from Dynamics 365 finance and operations apps and its integration into a data warehouse. However, Synapse Link is a more advanced and unified solution for data handling across all Dynamics 365 applications.

The transition from Export to Data Lake to Synapse Link is a key step in the unification of Dynamics products. By centralizing data pipelines into Synapse Link for Dataverse, Microsoft enables users to streamline their data processes. Organizations can integrate data from Dynamics 365 modules such as *Sales*, *Service*, and *Marketing* into a unified storage account for easy manipulation in Synapse Link and Power BI environments.

The following image is based on a slide for Synapse Link for Dataverse to integrate all Dynamics 365 data for analytics. On the left in the image, the Dataverse logo represents the data source. An arrow points to a container symbolizing Synapse Link  which integrates data from Dataverse. In the middle, the Synapse Analytics logo emphasizes the role of Synapse in processing and managing data. To the right, the Power BI logo highlights its role in visualizing and storytelling with the integrated data. The text below the image describes this as an evolution and unification across Dynamics products for analytics.

:::image type="content" source="media/DTV022EXT-dynamics365-data-analytics.svg" alt-text="Diagram with explanation after the image." lightbox="media/DTV022EXT-dynamics365-data-analytics.svg":::

The benefits of upgrading to Synapse Link include reduced complexity, cost reduction, and enhanced capabilities for data innovation. With the general availability of Microsoft Fabric, combining Synapse Analytics, Power BI, and other services into a single cloud offering, businesses stand to gain from more streamlined data operations and advanced reporting capabilities.

## Key features of Synapse Link

One of the critical differences between the older data export methods and Synapse Link is the way incremental data is handled. Traditional methods required manual setup of pipelines for data ingestion, which could be complex and resource-intensive. Synapse Link, however, automates much of this process, allowing users to focus more on building efficient pipelines rather than managing intricate schema definitions.

The integration of Synapse Link also removes the need for the CDM utility, which was previously necessary to define database schema within Synapse. This way, businesses spend less time on setup and more time on data analysis and integration.

## Incremental data ingestion

Incremental data ingestion is a core feature of Synapse Link, designed to simplify the process of continuously updating cloud data warehouses with fresh data. Businesses that built pipelines to ingest data into on-premises or cloud data warehouses can now rely on Synapse Link for more efficient and streamlined data transfers.

In Synapse Link, the data is automatically ingested into folders within a storage account, with new changes captured in real-time. This allows for incremental data updates, eliminating the need for full data exports and reducing the workload on both storage and processing systems. The incremental folder system ensures that only the most recent data changes are captured, allowing for more efficient data synchronization across platforms.

## Simplifying cloud data warehousing

Synapse Link for Dataverse supports various cloud data warehousing options, including Azure SQL Database and Synapse Dedicated Pool, allowing businesses to choose the architecture that best suits their needs. Whether a business operates primarily in the cloud or has an on-premises data warehouse, Synapse Link provides a robust solution for integrating and managing data across different platforms.

The following image is based on a slide for option four of exporting Dynamics 365 data to Synapse Link or a data lake with AzureSQL, SQL Server, Synapse data warehouse, or a non-Microsoft system.

:::image type="content" source="media/DTV022EXT-data-export-sql.svg" alt-text="Diagram with explanation immediately after the image." lightbox="media/DTV022EXT-data-export-sql.svg":::

This image illustrates the integration of data from Dataverse and Dynamics 365 finance and operations apps into Synapse using Synapse Link. On the left, Dataverse and Dynamics 365 feed entities and tables into Synapse Link. This data is processed through Synapse Serverless and Pipelines into an Azure Data Lake, where the data is stored as CSV and metadata in JSON format. From there, the data flows into Azure SQL, SQL Managed Instance, or SQL Server for further use, including integration with Power BI for data visualization. Another path shows how the data from Dataverse and Dynamics 365.

With the flexibility to integrate with external applications via T-SQL, Synapse Link simplifies the process of moving data between systems. This way, businesses can maintain their existing pipelines while benefiting from the improvements brought by Synapse Link.

## Data virtualization with Synapse Link

A notable feature of Synapse Link is its ability to virtualize data, allowing for seamless integration between cloud storage and on-premises databases. This feature is useful for businesses that aren't yet fully migrated to the cloud but still wish to use cloud-based analytics and reporting tools.

Data virtualization in Synapse Link enables businesses to query data directly from cloud storage without having to move the data to a separate database. This reduces the need for complex ETL (Extract, Transform, Load) processes and enhances the speed and efficiency of data access.

## Enhancing performance and reducing costs

One of the most significant advantages of transitioning to Synapse Link is the reduction in total cost of ownership. By streamlining data pipelines and eliminating the need for multiple data export processes, businesses can significantly reduce their operational costs. Synapse Link's ability to handle large-scale data operations with minimal overhead makes it an ideal solution for enterprises looking to optimize their data processes.

The following table compares configuration for the ChangeFeed mechanism to the new value of incremental folder.

|  | ChangeFeed | Incremental |
|--|--|--|
| **File path to schema** | `<container>/ChangeFeed/<table name>.cdm.json` | `<container>/<folder name>/model.json` </br></br>Folders are named by creation timestamp ("yyyy-MM-dd'T'HH:mm:ss.SSSz") in UTC. |
| **File path to data** | `<container>/ChangeFeed/<table name>/<file name>.csv` | `<container>/<folder name>/<table name>/<filename>.csv` |
| **Changed data identification** | Use the Modified datetime on the individual CSV files. | Use the name of the folder and model.json size does not equal 0. |
| **Full push** | Old files within `<container>/ChangeFeed/<table name>/` deleted and new files created after table initialized. | All records synched to latest folder `<container>/<folder name>/<table name>/<filename>.csv`. |
| **Learn more** | [ChangeFeed folder](/dynamics365/fin-ops-core/dev-itpro/data-entities/azure-data-lake-change-feeds) | [Incremental folder](/power-apps/maker/data-platform/azure-synapse-incremental-updates) |

Additionally, the platform's ability to handle incremental data ingestion means that businesses no longer need to perform full data exports, which can be resource-intensive and time-consuming. Not only reduces it costs, but it also improves the overall performance of data processing systems.

## Prepare for the future and integrate with Microsoft Fabric

Microsoft Fabric represents the next step in cloud data warehousing and analytics. If they upgrade to Synapse Link, businesses can position themselves to take full advantage of Fabric's capabilities, including unified data services and enhanced reporting tools. As Fabric continues to evolve, businesses that transition to Synapse Link are ready to benefit from its new features and improvements.

## Conclusion

The shift to Synapse Link for Dataverse is a crucial evolution in cloud data warehousing, offering businesses a more streamlined, efficient, and cost-effective way to manage and integrate their data. With features like incremental data ingestion, data virtualization, and integration with Microsoft Fabric, Synapse Link simplifies the transition to the cloud while maintaining compatibility with existing data pipelines.

For businesses looking to stay ahead in the world of cloud data warehousing, transitioning to Synapse Link is not just an option—it's a necessity. As more enterprises move their data operations to the cloud, the benefits of Synapse Link become even more apparent, driving innovation and efficiency across industries.

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)

- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)

- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)

- [Synapse Link documentation](/powerapps/maker/data-platform/export-to-data-lake)  

- [Create an Azure Synapse Link for Dataverse with your Azure Synapse Workspace - Power Apps](/power-apps/maker/data-platform/azure-synapse-link-synapse)

- [Export Microsoft Dataverse data in Delta Lake format - Power Apps](/power-apps/maker/data-platform/azure-synapse-link-delta-lake)

- [Choose finance and operations data in Azure Synapse Link for Dataverse - Power Apps](/power-apps/maker/data-platform/azure-synapse-link-select-fno-data)

- [Use managed identities for Azure with your Azure data lake storage - Power Apps](/power-apps/maker/data-platform/azure-synapse-link-msi)

- [Link your Dataverse environment to Microsoft Fabric and unlock deep insights - Power Apps](/power-apps/maker/data-platform/azure-synapse-link-view-in-fabric)

- [Microsoft Fabric documentation](/fabric/)
