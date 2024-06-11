---
title: Scheduled data exports from Dynamics 365 to CSV
description: Review a reference architecture for exporting data from Dynamics 365 to a .CSV file, including outlines on architecture, dataflow, components, and scenario details.
author: dereklh77
ms.author: v-heuerderek
ms.topic: article
ms.date: 05/22/2024
---

# Scheduled data exports from Dynamics 365 customer engagement apps to CSV file

***Applies to:*** ***Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, Dynamics 365 Project Operations, Dynamics 365 Sales, Power Apps, Power Pages, Dataverse, Azure Data Lake, Azure Synapse***

This solution combines Dataverse, Azure Data Lake, Azure Synapse, and Azure Data Factory to create scheduled exports of data from Dataverse to a CSV file. The exported file is stored in Azure Blob Storage and uploaded to an FTP server or stored in any other location supported by Azure Data Factory. External systems then consume the CSV file to process the data coming from Dynamics 365.

## Introduction

Data from Dynamics 365 apps is often used in other systems. There are various aspects to be considered when designing an integration between Dynamics 365 and the other system. These aspects include the availability of an API, the volume of data and the need to integrate in real time. This architecture can be a solution for scenarios in which you have a high data volume, don't need real-time data, and the receiving system can process CSV files.

This solution isn't industry-specific. You can use it for various purposes. The solution applies to Dynamics 365 customer engagement apps that use Dataverse as the data platform.

Solution architects are key stakeholders for Dynamics 365, the external system, and business users who use data that is interfaced in this integration.

## Architecture

The following diagram illustrates the architecture for the solution.

:::image type="content" source="../media/scheduled-data-exports-from-dynamics-365-ce-to-csv.svg" alt-text="Diagram showing the connection between Data Lake Storage and Synapse S Q L serverless storage." lightbox="../media/scheduled-data-exports-from-dynamics-365-ce-to-csv.svg":::

<!-- The original Word doc implies that there is a downloadable Visio file that has not yet been provided --- Download a Visio file with this architecture. -->

## Dataflow

The following data flow demonstrates the export of data to a CSV file, which is then stored in a location where the receiving system can access it.

1. Data is maintained and stored in Dynamics 365 CE.

2. Azure Synapse Link for Dataverse replicates the required tables from Dynamics 365 to Azure Data Lake Storage Gen2.

3. Synapse Workspace is connected to Azure Data Lake Storage Gen2 and provides a serverless SQL pool that allows you to query the data in the data lake.

4. Azure Data Factory connects to the serverless SQL pool to run queries.

5. Azure Data Factory saves the data as a CSV file and stores it in Azure Blob Storage or uploads it to an FTP server.

## Components

The following components are used in the reference architecture.

- [Dataverse](/power-apps/maker/data-platform/data-platform-intro) is the system that stores your customer data in tables. It's part of the Microsoft Power Platform and it's the base for apps like Dynamics 365 Sales and Dynamics 365 Customer Service. Dataverse serves as the source of data for this scenario.

- [Azure Synapse Link for Dataverse](/power-apps/maker/data-platform/export-to-data-lake) enables you to replicate data from Dynamics 365 in near real time to Azure Synapse Analytics or Azure Data Lake Storage Gen2.

- Azure Synapse Analytics is an analytics service that combines data integration, enterprise data warehousing, and big data analytics. It's used as a source for the queries that Azure Data Factory executes to get the data to be exported.

    - An [Azure Synapse Workspace](/azure/synapse-analytics/quickstart-create-workspace) promotes collaboration between data engineers, data scientists, data analysts, and business intelligence (BI) professionals.

    - [Azure Synapse serverless SQL pools](/azure/synapse-analytics/get-started-analyze-sql-on-demand) analyze unstructured and semi-structured data in Data Lake Storage Gen2 on demand.

- [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction) is a set of capabilities dedicated to big data analytics. It provides storage for data that is used in Azure Synapse Analytics.

## Scenario details

The organization where this solution is implemented uses Dynamics 365 Customer Service to manage their members' data. The organization has more than 100k members and each member can subscribe to multiple newsletters. Contacts who aren't members can also subscribe to newsletters. Subscribing and unsubscribing to newsletters is done using a Power Pages website. All communication preferences are stored in Dynamics 365. An external email marketing tool is used to create and send the newsletters.

This tool needs information about the newsletters that each contact wants to receive. However, the tool also needs information about the type of membership and whether or not they register for several other services. The external email marketing tool has out-of-the-box features to import all email recipients and related properties using CSV.

Initially, an Azure function was built to connect to the Dynamics 365 API, retrieve the data, and then store it as a CSV file. The problem was the complexity of the data structure. It isn't possible to get all required data in a single query. For each contact, a separate API call had to be made to determine, for example, if someone is a member. As a result, the total runtime of the export was more than four hours.

The architecture has changed due to runtime being too long and too many resources being consumed. With the solution presented here, the total runtime went down from four hours to less than two minutes for the exact same export. The main reason for the reduction is that all data can be retrieved in a single complex SQL query with multiple subqueries, instead of many separate queries to get the data.

### Potential use cases

This solution was created for a member organization in the healthcare sector. Solutions such as this can be used by any organization looking for a way to create a scheduled export of data to CSV. This solution can be used if you need to build an integration with some of the following characteristics:

- Data from Dynamics 365 isn't needed in real time in the receiving system. Receiving data once a day or a few times per day is enough.

- There's a high volume of data. This volume can either result from a high number of new or modified records in Dynamics 365 or the receiving system can expect a full export every time instead of an incremental export.

- The receiving system doesn't have an API to which you can send data or the API isn't accessible.

- The receiving system can process CSV files in an automated manner.

You can use this solution to:

- Export all contact information including their newsletter subscriptions and other preferences to an external email marketing application.

- Create a daily export of invoices for collection by an external party.

- Create a scheduled export of data that is used by external partners.

- Create a scheduled export of data to be used by external reporting systems or data science projects.

This architecture shouldn't be used in the following scenario:

- You need to export to XML. You could still use Synapse as the source for your query, but you need to create a custom function app to create the XML file. You can still consider Azure Data Factory to trigger the function to have all data exports in one place, which makes monitoring easier.

## Considerations

These considerations help implement a solution that includes Dynamics 365. Learn more at [Dynamics 365 guidance documentation](../../guidance/overview.md).

### Cost optimization

Cost optimization is about looking at ways to reduce unnecessary expenses and improve operational efficiencies. For more information, see [Overview of the cost optimization pillar](/azure/architecture/framework/cost/overview).

The costs for this solution are composed of the following:

- [Azure Synapse Link for Dataverse](https://azure.microsoft.com/pricing/details/synapse-analytics/) is part of Dynamics 365 licenses and can be used at no extra cost.

- [Data Lake Storage Gen2](https://azure.microsoft.com/pricing/details/storage/data-lake/) pricing depends on the amount of data that is stored on it and how often it's accessed. You can save costs by only replicating the tables that you need to export to the data lake instead of all tables from Dynamics 365. This component can also be used for other purposes such as reporting on data in Power BI or training AI models.

- [Azure Synapse Analytics](https://azure.microsoft.com/pricing/details/synapse-analytics/) pricing depends on the number of queries that you run. In this solution, we use the serverless option, the cheapest option.

- [Azure Data Factory](https://azure.microsoft.com/pricing/details/data-factory/data-pipeline/) pricing depends on your number of pipeline runs.

If you only need to export a small amount of data and you can create a query, you can also skip the creation of a data lake and using Synapse. In this case, it's more efficient to connect Azure Data Factory directly to Dataverse.

## Implementing scheduled data exports from Dynamics 365 to CSV

For the implementation of this solution, it's assumed that the Dynamics 365 instance with source data already exists. The implementation steps are focused on setting up the export procedure.

### Setting up Azure Synapse Link for Dataverse

Before you can set up Azure Synapse Link for Dataverse, you need to create an Azure Data Lake Storage Gen2 resource and an Azure Synapse Analytics workspace. All step-by-step instructions can be found here: [Create an Azure Synapse Link for Dataverse with your Azure Synapse Workspace](/power-apps/maker/data-platform/azure-synapse-link-synapse).

### Setting up Azure Data Factory

Once the Synapse workspace is set up and all data is populated by Azure Synapse Link for Dataverse, you can create an Azure Data Factory. Steps for creating the Azure Data Factory are available here: [Create an Azure Data Factory](/azure/data-factory/quickstart-create-data-factory)

### Creating the export procedure

Once all of the above services are created, you can start creating the export itself in Azure Data Factory by following these steps:

1. Open Azure Data Factory Studio.

2. Create a new pipeline.

3. Add a **Copy data** step.

4. Select the **Copy data** step, and then create a new source.

   1. Select Azure SQL Database as the source.

   2. Create a new linked service. In this linked service there are various ways to connect and manage the authentication with the serverless SQL pool. Below is just one way to do this.

      1. In the Account selection method, choose **Enter Manually** and select your subscription.

      2. Look up the endpoint of the serverless SQL endpoint for your Synapse workspace. You can find it by navigating to the overview page of the Synapse workspace resource in the Azure portal. Enter the endpoint in the **Fully qualified domain name** field.

      3. Enter the correct database name. This can be found by opening Synapse Studio.

      4. In Authentication type, select **System Assigned Managed Identity**. The managed identity that is used is shown here. To grant Azure Data Factory access to the serverless SQL pool, add the managed identity as a Synapse user to the Synapse workspace and grant the managed identity at least the Blob storage contributor role on the storage account.

      5. Test the connection to verify that Azure Data Factory can access the data in the Synapse workspace. If you see a notification that the SQL pool is warming up, try again in a minute.

   3. In the source dataset settings, you can leave the table name empty. The table is specified in the query. Save the source dataset by clicking **OK**.

5. Write a query to get the source data for your CSV file. The easiest way to do the mapping to CSV in a later step is to make sure that your source query contains the exact columns that you want to output to the CSV file. To write the query and validate the results, it's recommended to do this in Synapse Studio instead of the query editor in Azure Data Factory because it provides a richer experience.  
      
   > [!TIP]
   > To make your query run faster, select a TOP x number of records. Even if the number is much higher than the number of rows you expect, it will optimize your query and produce results faster.

6. In Azure Data Factory, in the source panel of the Copy data step, choose to use a query and paste your query into the editor.

7. Set the isolation level to *Read uncommitted* to reduce the chance of errors when data is written to the data lake at the same time that your query runs.

8. Navigate to the Sink properties of the Copy data step. You can use any destination needed. In this example, we use SFTP.

   1. Select SFTP and select Delimited Text to export to CSV.

   2. Create a new linked service and enter the details of the SFTP server.

   3. Test the connection to validate that Azure Data Factory can connect to it.

   4. Enter the file path and file name of the CSV to be created.

   5. *Optional*: you can enter a schema for the destination CSV by uploading a sample file.

9. Navigate to the Mapping panel of the copy data action to map the source fields to the destination fields.

10. Test the pipeline by clicking **Debug**.

You should now have a working export to CSV. You can schedule the export to run automatically by creating triggers in Azure Data Factory.

The serverless SQL pool may need time to warm up if you haven't used it for a while. As a result, it can happen that the first time you run a query, you'll receive an error message saying that the SQL pool is warming up. To properly handle this scenario, make sure that you enable retries in Azure Data Factory in steps where you're querying the database. Once the SQL pool is warmed up, all subsequent queries usually succeed immediately.

## Related resources

- For more information about Dynamics 365, see [Dynamics 365 on Microsoft Learn](/training/dynamics365).

- For more information about Azure Data Factory, see [Get started and try out your first data factory pipeline](/azure/data-factory/quickstart-get-started).

- For more information about Azure Synapse Analytics, see [Azure Synapse Analytics](/azure/synapse-analytics/).

<!-- ## Related patterns

If there are no related patterns at time of publishing, this section can be commented out. Do not delete. To comment out a section use to slashes.

## //Related resources

\[Consider the related resources carefully.\]

## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* IT

*Products:* Dynamics 365 Customer Service, Dynamics 365 Customer Voice, Dynamics 365 Field Service, Dynamics 365 Marketing, Dynamics 365 Project Operations, Dynamics 365 Sales
-->
## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributor.*

Principal author:

- Tycho Bom (https://www.linkedin.com/in/tychobom/) \| Freelance Microsoft Dynamics 365 Solution Architect
