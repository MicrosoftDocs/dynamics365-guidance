---
title: TechTalk Dynamics 365 data in lake house architecture
description: Summary of TechTalk video that talks about Dynamics 365 data lake house architectures data warehousing with Azure Synapse Link for Dataverse.
ms.date: 11/12/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Dynamics 365 data in lake house architecture with Azure Synapse Link for Dataverse

In today's digital age, the ability to seamlessly manage and transform data is vital for businesses, especially those using Dynamics 365 and Azure services. A key transition many organizations are navigating is moving from exporting data to Azure Data Lake to using Azure Synapse Link for Dataverse. This shift not only simplifies processes but also offers enhanced capabilities, such as easier data management, integration with Microsoft Fabric, and the implementation of lake house architecture.

We based this article on [a TechTalk](https://youtu.be/Wt8-M_rrwBM) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media\dataverse-synapse-link-dynamics-365-data-lakehouse-slide.svg" alt-text="Thumbnail of the presentation slide." link="https://youtu.be/Wt8-M_rrwBM":::

The ongoing evolution of these tools and platforms enables organizations to handle large volumes of both structured and unstructured data efficiently. This way, the organization get more advanced analytics and reporting. In this article, we explore the advantages of using Synapse Link for Dataverse, focusing on transitioning from Azure Data Lake to adopt the lake house architecture.

## Understanding the shift from export to Azure Data Lake to Synapse Link

Azure Data Lake has long been a popular solution for managing large datasets, such as solutions with Dynamics 365. Users can export their data from Dynamics 365 into a storage account, giving them the flexibility to work with it in Synapse workspaces or use it in tools like Power BI. However, while it's a good starting point to export to Azure Data Lake, Synapse Link for Dataverse introduces a more integrated experience, combining simplicity with efficiency.

:::image type="content" source="media/dataverse-synapse-link-dynamics-365-data-lakehouse-ai-driven-insights.svg" alt-text="Picture of a slide with the title Extend your investments to AI driven insights." lightbox="media/dataverse-synapse-link-dynamics-365-data-lakehouse-ai-driven-insights.svg":::

When the organization upgrades to Synapse Link, users not only retain their existing data schemas. They also expect substantial cost reductions in managing their datasets. For those already using Azure Data Lake, the transition to Synapse Link should be seamless. This upgrade process also enables users to use advanced tools and innovations offered by Microsoft Fabric. Fabric integrates AI-driven insights into the workflow, helping businesses unlock the true potential of their data.

## Exploring lake house architecture with Synapse Link

One of the most exciting aspects of this transition is the ability to adopt lake house architecture using Synapse Link. Lake house architecture, also referred to as medallion architecture, combines the best of both worlds—data lakes and data warehouses. This approach simplifies data processing by organizing data into three layers: bronze, silver, and gold.

The **bronze layer** holds raw, unstructured data, often in CSV format, while the **silver layer** refines and cleans this data, converting it into more usable delta formats. Finally, the **gold layer** provides a highly structured, analytics-ready dataset, which can be used for creating dashboards and reports in tools like Power BI.

The image shows Dataverse that connects to Synapse Link, which processes entities and tables from both Dataverse and Dynamics 365.

:::image type="content" source="media/dataverse-synapse-link-dynamics-365-data-lakehouse-architecture.svg" alt-text="Slide with the title Synapse Link (BYOL) with Synapse Spark and Serverless and a picture of a reference architecture." lightbox="media/dataverse-synapse-link-dynamics-365-data-lakehouse-architecture.svg":::

**Synapse Link for Dataverse** facilitates this architecture by automatically converting data from Dynamics into delta formats, which can then be read and processed with Spark notebooks. This automation eliminates many of the manual steps associated with data preparation, such as converting CSV files and managing data transformations. For businesses, this means they can more quickly move from raw data to actionable insights, using both near real-time and batch processing capabilities.

## Working with Dynamics 365 and Dataverse in the lake house

With Synapse Link, users can integrate data from multiple sources, including Dynamics 365 Finance and Dataverse, into a single workspace. This unified data model allows for the creation of complex data mashups, combining customer, product, and sales data into a seamless analytics pipeline.

For example, a company can join contact information from Dataverse with customer data from Dynamics 365 Finance, refining the data in Spark notebooks before storing it in delta format. This integration is especially useful for creating operational reports, near real-time dashboards, or even star schema models for deep analytics. By doing so, organizations can track customer trends, sales patterns, and other key performance indicators (KPIs) more effectively.

## Visualizing data with Microsoft Fabric and Power BI

The integration between Synapse Link and Microsoft Fabric further enhances the data analytics process. With **Fabric**, users can access their data without duplicating or moving it, thanks to features like shortcuts and unified storage. This means that data from Dynamics, Dataverse, and even legacy systems can all be accessed in one place, simplifying the entire analytics workflow.

The following image illustrates the integration of Microsoft Dynamics AX, Dynamics 365, and other systems through a data factory, which connects to Microsoft.

:::image type="content" source="media/dataverse-synapse-link-dynamics-365-data-lakehouse-ai-driven-insights-fabric.svg" alt-text="Slide with the title Unlock AI driven insights and action with Link to Fabric." lightbox="media/dataverse-synapse-link-dynamics-365-data-lakehouse-ai-driven-insights-fabric.svg":::

For instance, users can build **Power BI** reports directly from Fabric, without needing to import data into Power BI itself. This is made possible by **Direct Lake Mode**, which allows Power BI to read data directly from delta tables stored in Synapse. This approach offers the performance benefits of importing data, combined with the flexibility of querying live data.

Moreover, with Fabric's **machine learning** and **data science** capabilities, businesses can go beyond basic reporting to perform more advanced data modeling and predictive analytics. By integrating all these tools within a single workspace, Microsoft Fabric helps companies streamline their data processes and unlock deeper insights faster than ever before.

## Conclusion

Transitioning to **Synapse Link for Dataverse** offers significant benefits for organizations looking to modernize their data management and analytics processes. By unifying data from various Dynamics products, simplifying data transformations, and offering integration with Microsoft Fabric, this platform provides a robust foundation for future growth.

For businesses currently using Azure Data Lake, the switch to Synapse Link is straightforward, with minimal disruptions to existing workflows. As more companies adopt lake house architecture and use the power of Fabric for data processing, the opportunities for enhanced analytics and AI-driven insights continuea to grow.

Get started with Azure Synapse Analytics on [Microsoft Learn](/azure/synapse-analytics/). Also, join the Microsoft Dynamics Community to connect with peers and stay updated on the latest innovations.

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
- [Azure Synapse Link for Dataverse documentation](/powerapps/maker/data-platform/export-to-data-lake)
- [Create an Azure Synapse Link for Dataverse with your Azure Synapse Workspace - Power Apps](/power-apps/maker/data-platform/azure-synapse-link-synapse)
- [Export Microsoft Dataverse data in Delta Lake format - Power Apps](/power-apps/maker/data-platform/azure-synapse-link-delta-lake)
- [Choose finance and operations data in Azure Synapse Link for Dataverse - Power Apps](/power-apps/maker/data-platform/azure-synapse-link-select-fno-data)
- [Use managed identities for Azure with your Azure data lake storage - Power Apps](/power-apps/maker/data-platform/azure-synapse-link-msi)
- [Link your Dataverse environment to Microsoft Fabric and unlock deep insights - Power Apps](/power-apps/maker/data-platform/azure-synapse-link-view-in-fabric)
