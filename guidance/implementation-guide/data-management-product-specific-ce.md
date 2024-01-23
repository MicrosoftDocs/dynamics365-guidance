---
title: Manage data for customer engagement apps
description: Learn how to model, store, migrate, and archive data for customer engagement apps in Dynamics 365 solutions.
author: vaniaf
ms.author: vaniaf
ms.date: 01/17/2024
ms.topic: conceptual
ms.custom:
  - ai-seo-date: 01/17/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---
# Manage data for customer engagement apps

Dynamics 365 includes apps that work together across lines of business but have different tools for managing data. This article explains some of the ways to manage data for the customer engagement apps. You'll find recommendations and resources to help you model, store, migrate, and archive data.

## Model data

Data modeling is a science. Professional data modelers use standards and tools for data modeling. You don't need to be a professional or use special tools to model data for Dynamics 365, however. You can use a tool like Microsoft Visio to create a basic diagram that shows the relationships and flow of data between tables. In this section, we share some best practices for data modeling for Dynamics 365 deployments.

- Update data models throughout deployment. Data models are usually designed at the start of a project, but they shouldn't stop there. As you deploy, you add new fields and tables. Capture these changes in the data model to keep it current. We recommend that you update it regularly to improve the system.

- Don't include every table. Some core tables, such as activities, notes, and users (record owners), relate to almost every entity in Dynamics 365. If you include every relationship with these tables in your data model, it's hard to read. The best practice is to include in your data model diagram only the main tables in your configuration. Include only custom relationships with the user and activity tables to make it easier to read.

- Include data from and to integrations with other systems through Dataverse data connectors or virtual tables. This way, you can see the whole picture of your data model.

- Start with the standard tables, then add custom entity relationships to your data model.

- Let user experience guide your data model. Sometimes you might over-normalize your data, which can make the app harder to use.

Start with what you need now, but design the data model for the future. For example, if you know that you'll need to store more details about sales territories later, don't use a text field for territory now. It will be harder to implement than if you use the territory entity relationship now. Plan ahead.

## Store data

This section gives you guidance for your solution that's specific to the product.

### Forecast capacity

The capacity your environment uses should be part of the overall environment strategy. Assess each environment for storage requirements based on usage. For example, the development environment doesn't need as much storage as the production environment.

First, calculate the approximate volume and size of the data to estimate the storage you need. You can get this information from your existing data sources. Use megabytes (MB) or gigabytes (GB) to measure the size you need in production.

Based on the estimated size for production, allocate a percentage for each environment. The following table shows an example allocation.

| Environment | Use | Percentage of product |
| --- | --- | --- |
| Production | Has all the data for go-live | 100 |
| Training | Has a sample of the data | 15 |
| QA | Has a sample of the data | 15 |
| SIT | Has a sample of the data | 15 |
| Development | Has limited data only | 5 |

The best practice is to build a data storage forecast for at least three years. Include an average annual increase in volume. We recommend that you talk with your system integrator and Microsoft contacts when you design and configure your environments. Discuss how much storage you think you need and when. Track the data growth to make sure you stay within your storage limits.

Manage environments with a good environment strategy. For example, a developer shouldn't create new environments without a plan. Doing so could make you go over your limits, which could affect your ability to deliver on the application lifecycle management (ALM) strategies.

Learn more about [environment strategy](environment-strategy-overview.md) and [application lifecycle management](application-lifecycle-management.md).

### Measure storage capacity

Storage capacity is a standard calculation in Power Platform that the system administrator can manage easily. Use the [Power Platform admin center](https://admin.powerplatform.microsoft.com/) to monitor storage and consumption. In the Power Platform admin center, go to **Resources** > **Capacity**, and then choose **Dataverse** for more details about environment capacity limits.

:::image type="content" source="media/datamanagement_ppac.png" alt-text="Screenshot of the Capacity page in the Power Platform admin center.":::

### Understand storage limits

Dataverse capacity (database, file, log, and add-ons) is shared across the tenant and among all environments and workloads. The first subscription gives a one-time default capacity limit for the tenant. [Learn more about Dataverse storage capacity](/power-platform/admin/capacity-storage).

### Segment storage

The following list breaks down how capacity is calculated in Dynamics 365 based on storage type and database tables.

- **Dataverse database**

  All database tables count for your database, except for the logs and files listed later.

- **Dataverse files**

  The following tables store data in file and database storage:

  - Attachment
  - AnnotationBase
  - Any custom or out-of-the-box entity that has fields of datatype file or image (full size)
  - Any table that's used by one or more installed Insights applications and [ends in "-analytics"](/power-platform/admin/capacity-storage#what-are-tables-ending-in---analytics-in-my-capacity-report)
  - AsyncOperation
  - Solution
  - WebResourceBase
  - RibbonClientMetadataBase

- **Dataverse logs**

  The following tables are used:

  - AuditBase
  - PlugInTraceLogBase

## Migrate data

This section gives you guidance for your solution that's specific to the product.

### Methods and tools

You can use many types of tools to migrate data to your Dynamics 365 solution. We don't list them all here, but we cover some of the most common options.

- **Don't migrate data**

  You might think that you have to migrate large amounts of data to Dynamics 365 to see the whole picture. However, just because you need to see data in Dynamics 365 doesn't mean that the data must live in the Dynamics 365 Dataverse database. Consider the value of the data versus the quality, volume, time, and cost of moving it.

  Often, you can replace data that you don't migrate with embedded Power BI reports, virtual entities, embedded canvas apps with connectors to the source data, and so on.

  For example, the email autocapture option in Dynamics 365 Sales Insights shows activities to salespeople from their Exchange inbox instead of loading the data in Dynamics 365. Showing data virtually can also save time and money, since you don't have to load data and test your migration.

- **Power Apps Excel add-in**

  Use this add-in to open entities in Excel and create and update records directly in Dataverse. Not all entities support updates from Excel, and you have to edit lookup fields manually to match.

- **Get data from Excel**

  At [make.powerapps.com](https://make.powerapps.com/), view an entity, and then choose **Get data** to import data from an Excel or .csv file. This option gives you more control over the mapping of data than the Excel add-in does. You can import data from one file into multiple entities. To make sure the format of fields and mapping is correct, export a template from a Dataverse entity, fill in your data, and then import it. Or, import a custom file and provide mapping. Lookup fields must include the primary key or entity alternate key values to match.

- **Power Platform dataflows**

  At [make.powerapps.com](https://make.powerapps.com/), select **Dataflows** from the **Data** menu and set up an import from several data sources. Data sources include common external services file sources and generic web APIs. You can use Power Query to transform data from these data sources before you import it.

- **Legacy Dynamics 365 data import utility**

  You can import data to Dynamics 365 entities from .csv, .xls, .xml, and .zip files. Although the Dataverse API `Get Data` option is recommended for most flat file imports, the legacy data import option has some unique features that might be useful in some cases.

  - Legacy data import can create new entities, fields, and option set values in Dynamics 365. Although it's convenient, it's a best practice to add these items from a solution instead of from data import.

  - Legacy data import can import multiple files at the same time if you add them to a zip file.

  - Legacy data import can match lookup fields using values that aren't in the primary or alternate keys.

- **Dynamics 365 configuration data migration utility**

  Use this tool to move data between Dynamics 365 environments. If you're migrating data from sandbox environments to production, it's useful to keep the record IDs the same between environments. Consider the tool when you have entities like country/region and specific records are referenced in workflows or flows. In such cases, the process doesn't work if the ID changes between environments. The configuration data migration utility was updated in early 2020, so you can now provide filters to choose the records to include in the data package.

- **Extract, transform, and load (ETL) software**

  For more complex migrations, such as moving all the data from an old CRM system, manual import from flat files isn't efficient and can cause errors. Instead, use ETL tools like SSIS or Azure Data Factory. Many non-Microsoft ISPs offer services and tools to create a data transformation specification that can move old data to Dynamics 365. This approach can have the following benefits:

  - The data migration developer can test and improve the migration multiple times before go-live.

  - Changes sync when moving data from a system in use to a new system. For example, users still use the old system until they switch to Dynamics 365. If you load data into production several days before go-live, more data is created in the old system after the initial load is done. ETL tools can filter the data that's loaded to include only data that's changed since the last load. This way, you make sure the migrated data is current when users start using the new system.

  - Consistency with data integration. Sometimes you move data in an initial load and then update it through an ongoing integration. In these cases, it's best to use the same tooling that you use for the ongoing integration to load the initial data.

  - More complex data transformation. When you move data in flat files, you can choose what data is mapped to the new system. But if you want to change or transform the data, you have to do it manually in the source flat files. With an ETL-based migration, you can transform the data during the migration. For example, if you have five different types of accounts in the source data, but you want to combine them into three, ETL tools allow for this transformation in the data translation specification.

  - Updates and upserts. The flat file and Excel imports support updating records that match record keys, but sometimes your matching logic is more complex. Say you want to both update and insert records (upsert). It's complex and tedious to do with the out-of-the-box data import options, since you don't always have the record IDs. With ETL tools, the data migration developer can define record matching logic and update, insert, or upsert records based on any matching criteria. This is also helpful for making sure that you don't create duplicate records in the target.

  - More flexibility in mapping lookup fields. Lookups to other entities can be challenging for data imports, especially fields that are polymorphic, such as *customer*, or fields that have special properties, such as *owner*. If your old data has owning users that have a different format, the ETL tool can transform the values into a format that can be imported.

  - Many-to-many (N:N) relationships. ETL-based imports can easily import data to N:N relationships and entities, which aren't available with some of the flat file import options.

  - Faster import of large data sets. Good ETL tools can use multi-threading to import data quickly into Microsoft Dataverse.

- **Power Automate and Azure Logic apps**

  Use Power Automate and Azure Logic apps to import data and provide connectors to more than 300 services. These options provide many of the same benefits as an ETL tool. Power Automate includes more than 300 connectors to leading services and application platforms, and it's a great option to migrate data from these services. Although we have these options, they aren't meant to do large data migration jobs. Instead, think of them as a good option for low-volume or low-rate changes that don't need a lot of throughput.

- **Custom API migrations**

  This option gives you more control over migration and doesn't need any extra tools, but it requires that you have a developer to create and support the data migration.

## References

- [Data Management/Data Warehousing information, news and tips - SearchDataManagement (techtarget.com)](https://searchdatamanagement.techtarget.com/)

- [Insights-Driven Businesses Set The Pace For Global Growth (forrester.com)](https://www.forrester.com/report/InsightsDriven+Businesses+Set+The+Pace+For+Global+Growth/-/E-RES130848)

- [DMBoK - Data Management Body of Knowledge (dama.org)](https://www.dama.org/cpages/body-of-knowledge)
