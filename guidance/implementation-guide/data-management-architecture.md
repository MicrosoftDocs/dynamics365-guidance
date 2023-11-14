---
title: Data architecture
description: This chapter describes how data architecture, modeling, storage, integration, and quality can help you make informed decisions. Learn how to improve your customer engagement, and gather real-time information about your products in the field. 
author: vaniaf
ms.author: vaniaf
ms.date: 03/30/2023
ms.topic: conceptual

---

# Data architecture

Data architecture is a high-level concept, traditionally part of enterprise architecture. In simpler words, data architecture describes how data can be supplied to meet a business's strategic objectives.

According to [Data Management Book of Knowledge 2](https://www.dama.org/cpages/body-of-knowledge) (DMBoK 2), data architecture defines the blueprint for managing data assets by aligning with organizational strategy to establish strategic data requirements and designs to meet these requirements.

The right data architecture is central to the success of your business's data strategy. The right architecture focuses on where and how you use your data across various sources and what technologies are available to harness. Know where the data is coming from, if it's accurate, and if it provides the insights needed by the business within the solution.

If your organization has an enterprise-level data architecture in place, make sure to research policies, procedures, and restrictions that are in place for accessing the information you need.

For example, an organization has many disparate applications to support different business units. They use a legacy Dynamics product (not Dynamics 365) as a central repository for their master data. Their data strategy is to support a master version to generate better analytics and visibility of interactions across the organization. However, interactions with a customer, such as sales opportunities, sales transactions, support cases, or general activities, is better managed in a Dynamics 365 solution.

If you don't have an enterprise data architecture and just draw the existing business applications, their interfaces, and connections, you come up with a spaghetti diagram. That effort is a good start to getting an overview of your integration and data architecture. In fact, the resulting data flow diagram is an important input into defining your integration strategy.

Learn more at [Integrate with other solutions](integrate-other-solutions.md).  

The key point for data architecture is to create a holistic view of the data repositories, their relationships with each other and ownership. If you don't implement data architecture best practices, you'll often run into misalignment issues, such as a lack of cohesion between business and technical teams.

During your design and analysis phases, it's important to capture the data owners, systems, and conceptual flow between systems. This information helps to meet the integration requirements and provides a reference for the broader project team.

When you prepare your data architecture, use the questions below to guide you.

- How do you use your data?

- Where do you store your data?

- How do you manage your data and integrate it across your lines of business?

- What are the privacy and security aspects of the data?

Before you can start working with data, it's important to know what typical enterprise data is made up of.

:::image type="complex" source="media/datamanagement_enterprisedata.png" alt-text="Diagram with Dynamics 365 in the middle with integration systems with four types of master data." lightbox="media/datamanagement_enterprisedata.png":::
Diagram with Dynamics 365 in the middle with integration to Power Applications, SharePoint, Exchange, and master data integration to systems with four types of master data.
:::image-end:::

## Types of enterprise data

There are several distinct types of physical data to be aware of. This type of data typically falls into one of four categories: master data, configuration data, transactional data, and inferred data.

### Master data

Master data is your source of common business data and represents a non-transactional, consistent, and uniform set of tables. The details are maintained and controlled for accuracy. Examples include the following types of data:

- Company data

- Contact data

- Account holdings

- Customers

- Vendors

- Products

### Configuration data

Configuration data is data about different setups needed to prepare your production environment for operational use. Besides importing master data like customers and products, you need to import the configurations data. Examples include the following types of data:

- Currencies

- Tax codes

- Modes of payment

- Address (countries/regions, states, postal codes, and so on)

### Transactional data

This type of data is high in volume due to the nature of its use. Transactional data typically refers to events or activity related to the master data tables. The information is either created automatically or recorded by a user. The actual information could be a statement in fact, such as in banking. Or it could be a user interpretation, like the sentiment of a customer during a recent sales call. Here are a few other examples:

- Communication history

- Banking transactions

- IoT transactions

- ERP transactions (purchase orders, receipts, production orders, and so on)

### Inferred data

Inferred data is information not collected by the business or users. Typically, this information is automatically generated based on other external factors, which adds a level of uncertainty. Examples include the following types of data:

- Social media posts

- Credit score

- Segmentation

## Data modeling

With a base understanding of the data governance and data architecture, we can now focus our attention on how we plan to store the information we collect. Data modeling should always be completed before any configuration begins. Let us start with a basic understanding of data modeling, recommended practices, and how it's related to a project.

According to the DMBoK 2, the process of discovering, analyzing, representing and communicating data requirements in a precise form is called the data model. While data architecture is at an elevated level and involves a data architect looking at the business requirements broadly, data modeling is at a lower level and deals with defining and designing the data flows in precise detail.

Data architecture and data modeling need to work together when designing a solution for a specific business problem. For example, if your organization wants to implement an e-commerce solution, you can't do that unless somebody knows and has defined the existing data architecture and data models, different integrations in play, existing data imports and exports, how customer and sales data is currently flowing, what kind of design patterns can be supported, and which platform is a better fit into the existing architecture.

Likewise, if your organization wants to implement a data lake, somebody must answer questions such as the following list:

- What the existing data flows are both in and out of the business applications?  
- What is their format?  
- What are the existing data warehouses we need to migrate to data lake?  

We recommend that the data model conforms to the Common Data Model standard. The Common Data Model doesn't deviate from or repurpose existing out-of-the-box tables, to ensure cross application compatibility and future readiness. Common Data Model provides a shared data language for business and analytical applications to use. It makes it possible for data and its meaning to be shared across applications and business processes such as Microsoft Power Apps, Power BI, Dynamics 365, and Azure. Learn more at [Common Data Model](/common-data-model/).

### What is data modeling?

A data model is a visual model showing how data flows through your system and how different tables relate to each other. Data models define the relationship types between tables and abstract a database to a visual representation that is easy to understand.

If your project requires creation of new tables to support storing data for some specific business processes, it's recommended that you create a data model to define and understand the schema and data flow. But if yours is largely a vanilla implementation or has minimal customizations, it might not be relevant. Discuss with your system integrator and solution architect to see what works best for your case.

There are multiple types and standards for data modeling, including Unified Modeling Language (UML), IDEF1X, logical  and physical data model. The following example shows a logical data model.

:::image type="content" source="media/datamanagement_logicaldatamodel.png" alt-text="Example of logical data mode with four boxes." lightbox="media/datamanagement_logicaldatamodel.png":::

A common type of physical data model is an entity relationship diagram (ERD) as shown in the following example.

:::image type="content" source="media/datamanagement_physicaldatamodel.png" alt-text="Example of physical data model with eight entities." lightbox="media/datamanagement_physicaldatamodel.png":::

## Data storage

We need to talk about data storage and what you can do to manage the growth and costs involved. The reality is no matter where your data is stored, there's always a cost involved. Whether you're managing data on-premises or online in Azure, storing and moving your data can impact the overall cost of the solution.

There are several factors to consider when defining a data storage strategy.

### Data archival

Implementing a data archival strategy allows regular shifting of data from Dynamics to another storage location for data maintenance and analytics.

When you start using your Dynamics 365 business app in production, over time its database grows and database comes under strain. This impacts app performance and thus degrades user experience. Even though Dynamics 365 is a SaaS application, and you don't bother with managing database, it's a clever idea to have periodic data maintenance routines in place to delete unwanted data to keep database nimble. Though there's currently no out of the box tool to archive data in Dynamics, there are cleanup routines to delete unwanted transactions, and you can create custom routines to delete data. For practical reasons and as a best practice, you shouldn't keep old historical data in Dynamics, data that the business doesn't need for day-to-day operations.

Another benefit of exporting data out of Dynamics is to enable your organization's analytics strategy. An organization wants to use all of its business data to help guide its business decision making. You can move Dynamics data out to a company owned data lake where it can be used to update a data warehouse or for machine learning.

For example, set up data export schedules to replicate data to Azure Data Lake, which is comparatively cheaper than Azure SQL. Once data is moved to the data lake, set up Azure Data Factory or Azure Synapse data flows or Databricks/Apache Spark to transform your data. Feed the data into a Synapse SQL pool/data warehouse so you can use Power BI to produce business dashboards. You can also use Azure Machine Learning to run models of this data and produce predictions. The following illustration shows a modern data warehouse architecture by using Azure Data Lake Storage.

:::image type="content" source="media/datamanagement_moderndatawarehouse.png" alt-text="Diagram with Dynamics 365 connecting to AzureData Lake Storage." lightbox="media/datamanagement_moderndatawarehouse.png":::

For more information, read [Export to Data Lake in Finance and Operations apps](/dynamics365/fin-ops-core/dev-itpro/data-entities/finance-data-azure-data-lake) , [Ingest Microsoft Dataverse data with Azure Data Factory](/powerapps/maker/data-platform/export-to-data-lake-data-adf) and [Analyze, Microsoft Dataverse exported to Azure Data Lake Storage Gen2 data with Power BI](/powerapps/maker/data-platform/export-to-data-lake-data-powerbi).

Learn more about reporting strategy  at [Business intelligence, reporting, and analytics](business-intelligence-reporting-analytics-overview.md).  

## Data integration

Integration is the connecting of one or more parts or components of a system to create a more unified experience or to ensure a more consistent outcome of a process. Integration allows use of existing services both internal and external without having to rebuild or migrate existing functionality.

Data integration is done to bring data into the system or out to other systems. Typically, it happens through an event or in a batch on a schedule. For example, when a record is created or updated it would be event driven and the nightly scheduled transmission of data would be a batch.

Learn more at [Integrate with other solutions](integrate-other-solutions.md).

## Data quality

Once data is migrated and integrated to your solution, it's critical that information remains accurate, complete, reliable, and, most importantly, up to date.

You can use various techniques to manage the quality of the data, including data profiling, data cleansing, and data validation. The most important aspect of data quality to understand is that data quality is the responsibility of everybody in an organization. We see many customers who overestimate the quality of their data and underestimate the effort it takes to get it into shape. Keeping data quality top notch requires following all the principles we highlighted in this chapter and equally strong leadership to drive the habit of managing data on an ongoing basis.

Make your data quality a habit!

## Next Steps

- Understand configuration data and how to perform a healthy data migration. Learn more at [config and migrated data](data-management-configuration-data-migration.md) section  

- Review Data Management product specific guidelines. Learn more at [Guidelines for customer engagement apps](data-management-product-specific-ce.md) and at [Guidelines for finance and operations apps](data-management-product-specific-fo.md)  

- Access the checklist at [Data Management Success by Design checklist](data-management-check-list.md)  
