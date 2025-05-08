---
title: Business performance analytics with Dynamics 365 Finance
description: Summary of TechTalk video that provides a comprehensive overview of the business performance analytics (BPA) capabilities in Dynamics 365 Finance.
ms.date: 09/17/2024
ms.topic: concept-article
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Business performance analytics with Dynamics 365 Finance

In the evolving landscape of business, the need for integrated, real-time analytics is paramount. Companies are challenged by data that's dispersed across multiple systems, requiring significant effort to consolidate and analyze. To address these issues, Dynamics 365 Finance includes capabilities for business performance analytics (BPA). BPA is a powerful tool designed to streamline data integration and reporting, making it easier for businesses to gain insights and make informed decisions.

We based this article on [a TechTalk](https://youtu.be/Qb6uo_er6nE?si=Zs2vBU1fHXJsjFjr) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/techtalk-DTV050EXTR-slide.png" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/Qb6uo_er6nE?si=Zs2vBU1fHXJsjFjr":::

## The genesis of BPA

The development of BPA began in response to recurring feedback from customers who faced significant challenges in managing and analyzing data. Businesses reported that data was often scattered across disparate systems, making it difficult to obtain a holistic view of operations. Moreover, combining and correlating this data for accurate reporting required extensive developer or consulting resources, which added to the cost and complexity.

To solve these problems, BPA was conceived with a few guiding principles:

1. **User-centric design:** BPA prioritizes ease of use for business analysts, finance professionals, and controllers. The goal is to enable these users to create reports without requiring deep technical expertise.

2. **Data-driven and trustworthy:** The solution is designed to provide data as current as possible, with top-tier security through role-based access control.

3. **Extensibility:** BPA isn't limited to data from Dynamics 365. Connect to external data sources, partner-provided solutions, or other systems, and you have a versatile tool for comprehensive business analysis.

## BPA process architecture

BPA's architecture is centered around value chains, which group related business processes such as record-to-report, procure-to-pay, order-to-cash, and acquire-to-retire. Each business process in Dynamics 365 generates transactions, and these transactions are the foundation for reporting within BPA. The architecture supports both vertical and horizontal reporting, allowing users to view data across the entire value chain or drill down into specific transactions.

The data model is built using a dimensional approach, where the most granular data—such as individual sales order lines or invoice lines—is modeled for detailed analysis. This granularity enables more precise reporting and insights.

## Data architecture and ETL pipeline

The data architecture of BPA consists of two main components:

- The Extract, Transform, Load (ETL) pipeline.  
- A model-driven app for surfacing reports and insights.  

The ETL pipeline integrates with Dynamics 365 Finance, extracting data, transforming it to meet specific requirements, and loading it into the target system. This process ensures efficient data handling and improves data quality, scaling as the data grows.

1. **Extract:** Virtual entities are created at the time of app installation, mapping to data entities in the underlying database. The pipeline then syncs this data into a managed data lake.

2. **Transform:** BPA uses Spark transformations on Synapse clusters to process the data into a dimensional model that includes facts and dimensions related to the value chains.

3. **Load:** The final dimensional model is loaded into a Power BI workspace, which is part of the BPA's managed solution. This data is then used for generating reports within Power BI and Excel.

## Extensibility scenarios

BPA offers several extensibility scenarios to meet diverse business needs:

1. **Integration with Custom Data Warehouses:** BPA can be integrated into a company's fabric environment, allowing for custom datasets and reports based on BPA data.

2. **Complex ISV Integrations:** Businesses can extend BPA to include custom fields and tables from ISV solutions, which can then be incorporated into BPA's analytical tables and reports.

3. **Integration with Third-Party Systems:** BPA is designed to work with data from third-party ERP systems like SAP, enabling a comprehensive view that includes both Dynamics 365 data and external sources.

## Installation and cost

BPA is part of the Dynamics 365 Finance license. The installation process requires a Dynamics 365 solution that's linked to Dataverse. Learn more at [Prerequisites to installing Business performance analytics](/dynamics365/finance/business-performance-analytics/configure-bpa).

BPA provides access to three years of historical data plus the current year, with twice-daily data refreshes at general availability (GA). Microsoft hosts the solution and provides updates.

## Reporting and analytics

BPA includes a set of prebuilt reports in Power BI, which can be customized or extended as needed. These reports cover a range of financial data, including trial balances, balance sheets, budget vs. actual comparisons, and more. Users can edit these reports in Power BI or Excel, with full access to the underlying data model.

The solution also supports drill-down capabilities so that users can explore data at a detailed level directly from summary reports. This feature is particularly useful for financial analysts who need to investigate specific transactions.

## Yet to come

Microsoft continues to develop BPA, with plans to enhance its capabilities further. Follow what's going on in [the release planner app](https://releaseplans.microsoft.com/?app=Finance).

## Conclusion

BPA with Dynamics 365 Finance is a robust tool designed to address the complexities of modern business analytics. By integrating data across value chains, offering extensibility with external systems, and providing powerful reporting capabilities, BPA enables businesses to make data-driven decisions with confidence. As the solution evolves, it continues to offer more features and flexibility, making it an essential component of any organization's analytics toolkit.

Learn more about BPA and to participate in the public preview in the [documentation for Dynamics 365 Finance](/dynamics365/finance/business-performance-analytics/business-performance-analytics-home-page).

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [What is business performance analytics? - Finance](/dynamics365/finance/business-performance-analytics/business-performance-analytics-home-page)  

- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)

- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)

- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
