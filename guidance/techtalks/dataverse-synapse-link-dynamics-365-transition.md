---
title: TechTalk Transitioning to using Synapse Link from exporting data to Azure Data Lake
description: Summary of TechTalk video that talks about using Azure Synapse Link for Dataverse with Dynamics 365 apps. 
ms.date: 09/23/2024
ms.topic: concept-article
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Transitioning to using Azure Synapse Link from exporting data to Azure Data Lake

In the ever-evolving world of data management, businesses increasingly rely on seamless and efficient methods to store, process, and analyze their data. One of the significant transitions in this space is moving from using Export to Azure Data Lake to using Azure Synapse Link. This transition marks a pivotal moment in how enterprises manage their Dynamics 365 data, offering enhanced capabilities and streamlined processes.

We based this article on [a TechTalk](https://youtu.be/j-Ef0XwgsmE) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media\dataverse-synapse-link-dynamics-365-slide.svg" alt-text="Thumbnail of the presentation slide." link="https://youtu.be/j-Ef0XwgsmE":::

## Understanding Synapse Link for Dataverse

At its core, Synapse Link for Dataverse provides a unified experience for handling all Dynamics 365 data. The primary goal is to eliminate the complexities and pains associated with working with large datasets for analytics purposes. All Dynamics 365 apps integration with Power Platform, including the finance and operations apps. Dataverse serves as the foundation of this integration, enabling businesses to manage everything from financial operations to customer service under one umbrella.

Previously, many organizations relied on Export to Azure Data Lake to manage and analyze their data. However, Synapse Link offers a significant upgrade. It supports a single-click experience that continuously exports data from Dynamics 365 to a data lake. This way, the data becomes accessible for analysis in Azure Synapse Analytics and other tools.

## The transition process

Transitioning from Export to Azure Data Lake to Synapse Link involves several steps, but Microsoft designed the process to be as seamless as possible. Organizations already using Export to Azure Data Lake can run Synapse Link concurrently, which ensures that their data remains accessible throughout the transition period.

To enable Synapse Link, administrators must configure a few key settings in the Dynamics 365 environment, such as turning on the **SQL Row Version Change Tracking** configuration. Once configured, setting up Synapse Link is straightforward via the Power Platform's Maker Portal. Users select the environment linked to their Dynamics 365 environment, and with a few clicks, they can establish a connection to Azure Synapse Workspace.

## Benefits of Synapse Link

One of the most significant advantages of Synapse Link is its efficiency in handling large datasets. For example, when exporting data using Delta format, organizations can see up to a six-fold compression, reducing storage costs and improving performance during data processing. This efficiency is noticeable when querying data in Azure Synapse Analytics, where the cost and time required to process data can be drastically reduced compared to using traditional .CSV files.

Moreover, Synapse Link integrates seamlessly with Microsoft Fabric, enabling low-code users to interact with Dynamics 365 data without needing to copy or move it. This integration ensures that authorized users can access and work with the data directly in Microsoft Fabric, using its advanced analytics capabilities without the overhead of traditional data management processes.

The following image shows how Synapse Link for Dataverse enables organizations that use Dynamics 365 and Power Apps to integrate sales, customer service, field service, marketing, finance, and operations data into Azure Synapse. Once the initial seeding of data is completed, incremental updates will continually run to enable analytics on the most recent and relevant version of the data.

:::image type="content" source="media/dataverse-synapse-link-dynamics-365-overview.svg" alt-text="Image based on a presentation slide." lightbox="media/dataverse-synapse-link-dynamics-365-overview.svg":::

## Planning your transition

For organizations currently using Export to Azure Data Lake, Microsoft recommends planning the transition to Synapse Link ahead of the November 2024 deadline. The transition not only reduces operational costs but also opens up new opportunities for using Microsoft Fabric's capabilities.

For those not yet live with Export to Azure Data Lake, adopting Synapse Link from the outset is advisable. This approach ensures that businesses can take full advantage of the latest advancements without needing to undergo a fast-follow conversion.

The following image presents an overview of Synapse Link for Dataverse. It emphasizes how you can export Dataverse data into Synapse for analytics with a single step. The integration includes continuous replication of both standard and custom tables to Azure Synapse Analytics and is now compatible with Dynamics 365 finance and operations apps.

:::image type="content" source="media/dataverse-synapse-link-dynamics-365-dataverse-synapse-link.svg" alt-text="Screenshot of slide with Dataverse connected with Synapse for enhanced analytics." lightbox="media/dataverse-synapse-link-dynamics-365-dataverse-synapse-link.svg":::

## Conclusion

Synapse Link is just the first step in a broader transition towards more integrated and efficient data management solutions within the Microsoft ecosystem. As businesses upgrade to Synapse Link, they unlock new capabilities within Microsoft Fabric, allowing for more comprehensive data analysis and reporting.

The transition from Export to Azure Data Lake to Synapse Link represents a significant step forward in data management for Dynamics 365 users. By adopting this new technology, businesses can reduce costs, improve performance, and position themselves to take full advantage of the innovations that Microsoft Fabric brings to the table.

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [TechTalk: Architecture patterns for virtual data warehousing with Dynamics 365 data in Azure Synapse Link](dataverse-synapse-link-dynamics-365-architecture-patterns.md)  

- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)

- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)

- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
