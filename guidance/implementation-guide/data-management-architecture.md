---
title: Manage your data effectively with the right architecture
description: Learn how to design, store, integrate, and maintain your data to support your business goals and strategies.
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

# Manage your data effectively with the right architecture and modeling

Data is a valuable asset for any business. But to use it effectively, you need a clear and consistent way to organize, store, and integrate it across your systems and applications. That's where data architecture and modeling come in.

Data architecture is a high-level concept that describes how data supports your business's strategic objectives. Data modeling is a lower-level process that defines and designs the data flows and relationships in your system. Together, they help you create a blueprint for managing your data assets and aligning them with your organizational strategy.

In this chapter, you'll learn about the key aspects of data architecture and modeling, such as:

- The types and sources of enterprise data
- The standards and best practices for data modeling
- The options and considerations for data storage
- The methods and tools for data integration
- The techniques and habits for data quality

## Data architecture

Data architecture defines how data can be supplied to meet a business's strategic objectives. It involves identifying the data sources, formats, flows, and quality across your organization. It also considers the privacy and security aspects of the data, and the technologies and policies that govern its use.

The right data architecture is central to the success of your business's data strategy. It helps you focus on where and how you use your data across various sources and what technologies are available to harness it. It also helps you know where the data is coming from, if it's accurate, and if it provides the insights you need for your solution.

If your organization has an enterprise-level data architecture in place, make sure to research the policies, procedures, and restrictions that are in place for accessing the information you need.

For example, suppose your organization has many disparate applications to support different business units. They use a legacy Dynamics product (not Dynamics 365) as a central repository for their master data. Their data strategy is to support a master version to generate better analytics and visibility of interactions across the organization. However, interactions with a customer, such as sales opportunities, sales transactions, support cases, or general activities, are better managed in a Dynamics 365 solution.

If you don't have an enterprise data architecture and just draw the existing business applications, their interfaces, and connections, you might end up with a spaghetti diagram. That effort is a good start to getting an overview of your integration and data architecture. In fact, the resulting data flow diagram is an important input into defining your integration strategy.

The key point for data architecture is to create a holistic view of the data repositories, their relationships with each other, and their ownership. If you don't implement data architecture best practices, you might run into misalignment issues, such as a lack of cohesion between business and technical teams.

During your design and analysis phases, it's important to capture the data owners, systems, and conceptual flow between systems. This information helps you meet the integration requirements and provides a reference for the broader project team.

When you prepare your data architecture, use the following questions to guide you:

- How do you use your data?
- Where do you store your data?
- How do you manage your data and integrate it across your lines of business?
- What are the privacy and security aspects of the data?

Before you can start working with data, it's important to know what typical enterprise data is made up of. The following diagram illustrates the different types of enterprise data and how they relate to each other:

:::image type="content" source="media/datamanagement_enterprisedata.png" alt-text="Diagram with Dynamics 365 in the middle with integration systems with four types of master data." lightbox="media/datamanagement_enterprisedata.png":::

## Types of enterprise data

Physical data typically falls into one of four categories: master data, configuration data, transactional data, and inferred data.

### Master data

Master data is your source of common business data and represents a nontransactional, consistent, and uniform set of tables. The details are maintained and controlled for accuracy. Examples include the following types of data:

- Company data
- Contact data
- Account holdings
- Customers
- Vendors
- Products

### Configuration data

Configuration data is data about different setups needed to prepare your production environment for operational use. Besides importing master data like customers and products, you need to import the configuration data. Examples include the following types of data:

- Currencies
- Tax codes
- Modes of payment
- Address information, such as country/region, state, postal code, and city

### Transactional data

This type of data is high in volume due to the nature of its use. Transactional data typically refers to events or activity related to the master data tables. The information is either created automatically or recorded by a user. The actual information could be a statement in fact, such as in banking. Or it could be a user interpretation, like the sentiment of a customer during a sales call. Here are a few other examples:

- Communication history
- Banking transactions
- IoT (Internet of Things) transactions
- ERP (enterprise resource planning) transactions such as purchase orders, receipts, and production orders

### Inferred data

Inferred data is information not collected by the business or users. Typically, this information is automatically generated based on other external factors, which adds a level of uncertainty. Examples include the following types of data:

- Social media posts
- Credit score
- Segmentation

## Data modeling

With a base understanding of the data governance and data architecture, we can now focus our attention on how we plan to store the information we collect. Data modeling should always be completed before any configuration begins. Let's start with a basic understanding of data modeling, recommended practices, and how it's related to a project.

According to the [Data Management Book of Knowledge 2](https://www.dama.org/cpages/body-of-knowledge) (DMBoK 2), the process of discovering, analyzing, representing, and communicating data requirements in a precise form is called the data model. Data architecture is at an elevated level and involves a data architect looking at the business requirements broadly. Data modeling is at a lower level and deals with defining and designing the data flows in precise detail.

Data architecture and data modeling need to work together when designing a solution for a specific business problem. For example, if your organization wants to implement an e-commerce solution, someone first has to define the existing data architecture and data models. That includes any integrations in play, data imports and exports, how customer and sales data is currently flowing, what kind of design patterns can be supported, and which platform is a better fit into the existing architecture.

Likewise, if your organization wants to implement a data lake, someone must answer questions like these:

- What are the existing data flows in and out of the business applications?
- What are their formats?
- What are the existing data warehouses we need to migrate to the data lake?

We recommend that the data model conforms to the Common Data Model standard. The Common Data Model doesn't deviate from or repurpose existing out-of-the-box tables, to ensure cross-application compatibility and future readiness. The Common Data Model provides a shared data language for business and analytical applications to use. It makes it possible for data and its meaning to be shared across applications and business processes such as Microsoft Power Apps, Power BI, Dynamics 365, and Azure. [Learn more about the Common Data Model](/common-data-model/).

### What is data modeling?

A data model is a visual model showing how data flows through your system and how different tables relate to each other. Data models define the relationship types between tables and abstract a database to a visual representation that's easy to understand.

If your project requires creating tables to support storing data for some specific business processes, we recommend that you create a data model to define and understand the schema and data flow. But if your project is largely a vanilla implementation or has minimal customizations, creating a data model might not be relevant or necessary. Discuss with your system integrator and solution architect to see what works best for your case.

There are multiple types and standards for data modeling, including Unified Modeling Language (UML), IDEF1X, and a logical and physical data model. The following example shows a logical data model:

:::image type="content" source="media/datamanagement_logicaldatamodel.png" alt-text="Example of logical data mode with four boxes." lightbox="media/datamanagement_logicaldatamodel.png":::

A common type of physical data model is the entity relationship diagram (ERD) shown in the following example:

:::image type="content" source="media/datamanagement_physicaldatamodel.png" alt-text="Example of physical data model with eight entities." lightbox="media/datamanagement_physicaldatamodel.png":::

## Data storage

We need to talk about data storage and what you can do to manage the growth and costs involved. The reality is that no matter where your data is stored, it always involves a cost. Whether you're managing data on-premises or online, storing and moving your data can affect the overall cost of the solution.

You should consider several factors when you're defining a data storage strategy.

### Data archival

Implementing a data archival strategy allows you to move data from Dynamics 365 to another storage location for data maintenance and analytics.

When you start using your Dynamics 365 business app in production, its database grows over time and puts strain on the system. This affects app performance and user experience. Even though Dynamics 365 is a software as a service (SaaS) application, and you don't have to worry about managing the database, it's a good idea to have periodic data maintenance routines in place to delete unwanted data and keep the database nimble. Although there's no out-of-the-box tool to archive data in Dynamics 365, there are cleanup routines to delete unwanted transactions, and you can create custom routines to delete data. As a best practice, you shouldn't keep old historical data in Dynamics 365 that the business doesn't need for day-to-day operations.

Another benefit of exporting data out of Dynamics 365 is that it can facilitate your organization's analytics strategy. You can move Dynamics 365 data to a company-owned data lake where it can be used to update a data warehouse or for machine learning.

For example, you can set up data export schedules to replicate data to Azure Data Lake Storage, which is cheaper than Azure SQL. After data is moved to the data lake, you can set up Azure Data Factory or Azure Synapse data flows or Databricks/Apache Spark to transform your data. Then you can feed the data into a Synapse SQL pool or data warehouse so that you can use Power BI to produce business dashboards. You can also use Azure Machine Learning to run models on the data and produce predictions. The following illustration shows a modern data warehouse architecture that uses Azure Data Lake Storage:

:::image type="content" source="media/datamanagement_moderndatawarehouse.png" alt-text="Diagram with Dynamics 365 connecting to Azure Data Lake Storage." lightbox="media/datamanagement_moderndatawarehouse.png":::

## Data integration

Integration is the process of connecting one or more parts or components of a system to create a more unified experience or to ensure a more consistent outcome of a process. Integration allows you to use internal and external services without having to rebuild or migrate existing functionality.

Data integration is done to bring data into the system or out to other systems. Typically, it happens through an event, like when a record is created or updated, or in a batch on a schedule, like the nightly scheduled transmission of batched data.

[Learn more about integrating with other solutions](integrate-other-solutions.md).

## Data quality

After data is migrated and integrated to your solution, it's critical that the information remains accurate, complete, reliable, and up to date.

You can use various techniques to manage the quality of the data, including data profiling, data cleansing, and data validation. The most important aspect of data quality to understand is that it's the responsibility of everyone in an organization. We see many customers who overestimate the quality of their data and underestimate the effort it takes to get it into shape. Keeping data quality top-notch requires following all the principles we highlighted in this chapter and strong leadership to drive the habit of managing data on an ongoing basis.

## Next steps

- [Understand configuration data and how to perform a healthy data migration](data-management-configuration-data-migration.md)
- Review product-specific guidelines for data management: [guidelines for customer engagement apps](data-management-product-specific-ce.md) and [guidelines for finance and operations apps](data-management-product-specific-fo.md)
- [Review the Data Management Success by Design checklist](data-management-check-list.md)
- [Read a case study in data management](data-management-case-study.md)

### See also

- [Export to data lake in finance and operations apps](/dynamics365/fin-ops-core/dev-itpro/data-entities/finance-data-azure-data-lake)
- [Ingest Microsoft Dataverse data with Azure Data Factory](/powerapps/maker/data-platform/export-to-data-lake-data-adf)
- [Analyze Microsoft Dataverse data in Azure Data Lake Storage Gen2 with Power BI](/powerapps/maker/data-platform/export-to-data-lake-data-powerbi)
- [Business intelligence, reporting, and analytics](business-intelligence-reporting-analytics-overview.md)
