---
title: Components of the modern data estate
description: Learn how you can integrate services from across Dynamics 365 and get consolidated reports.
author: TimoGossen
ms.author: timogoss
ms.date: 10/17/2022
ms.topic: conceptual

---
# Components of the modern data estate

Dynamics 365 and the Power Platform can be an essential part of your modern data estate architecture. Your business data is securely stored within Dynamics 365 as a function of your day-to-day operations. In addition, Dynamics 365 can export data to or ingest data from various sources to be used in reporting, workflow, applications, or in any other way that is required by your business.

You can also generate insights and analytics from data created and managed inside each Dynamics 365 application. Apps using embedded intelligence, such as the audience insights capability inside the Dynamics 365 Customer Insights app, enrich your data and allow more informed decision-making.

## Common Data Model

Dynamics 365 data estate components can ingest, store, prepare, model, and visualize data to produce insights that will support, boost, and even transform operations.  

<!-- <T.G. figure reference not needed (Figure 13-3)-->

:::image type="content" source="media/commondatamodel.png" alt-text="common data model" lightbox="media/cdmschema.png":::

Common Data Model is one of the key technologies enabling access to many kinds of information from heterogeneous services and data stores. Learn more at [Common Data Model](/common-data-model/).  

Common Data Model is a shared data language used by business and analytical applications and offers a set of standardized, extensible data schemas to enable consistency of data and its meaning across applications and business processes.

The Common Data Model specification defines out-of-the-box standard entities representing common concepts such as people, budgets, and campaigns. Having your data in a common format for entities with the relevant metadata makes it possible to build apps and services that light up based on the data. The Common Data Model format also makes it easier to consume data in the Power Platform, which uses Power BI to get insights from your data. Normalizing the data sets up your organization to better identify opportunities and puts your data in a format that could be used for future projects. Dynamics 365 uses [Dataverse](/power-apps/maker/data-platform/) to store and secure app data, based on Common Data Model. The Common Data Model structure is defined in an extensible schema. <!-- <T.G. adding graphic directly> as shown in Figure 13-4. -->Organizations can build or extend apps by using Power Apps and Dataverse directly against their business data. Learn more at [Dataverse](/power-apps/maker/data-platform/).  

:::image type="content" source="media/cdmschema.png" alt-text="common data model schema" lightbox="media/cdmschema.png":::

## Data unification components

Services and applications that ingest data from multiple sources serve a vital role in a modern data estate. Aggregation from data stores and services provides users with business-critical information supplied in dashboards and reports. The resulting data and events can also be used to trigger workflows and act as inputs to the apps running on the Dataverse platform. Many data unification components are built into Dynamics 365 applications—and organizations can design their own integrations to fit their business needs.

### Customer Insights as a customer data platform

[Dynamics 365 Customer Insights](/dynamics365/customer-insights/audience-insights/overview) is a real-time customer data platform that brings together transactional, behavioral, and demographics data from various sources to create a 360-degree view of your customers.

:::image type="content" source="media/customerinsightssolution.png" alt-text="customer insights solution" lightbox="media/customerinsightssolution.png":::

The Customer Insights solution <!-- <T.G. adding figure on top instead (Figure 13-5)--> offers prepackaged customer-analytics capabilities such as segmentation, churn analysis, and product recommendations, with Power BI embedded for easy data exploration and visualization. It also incorporates AI and machine learning models, so data scientists can create custom models in the Azure Machine Learning platform. The addition of Azure Cognitive Services provides text, speech, image, and video analysis, and enriches data via Microsoft Graph.

## Dataverse and applications

Building an app typically involves accessing data from more than one source. Although it can sometimes be done at the application level, there are cases where integrating this data into a common store creates an easier app-building experience—and a single set of logic to maintain and operate over the data. With Dataverse, data can be integrated from multiple sources into a single store and then be used in Power Apps, Power Automate, Power BI, and Power Virtual Agents, along with data that's already available from Dynamics 365 apps.

## Data export components

A key characteristic of a data estate is the ability to export data to services as needed. Because data in the Dataverse conforms to the Common Data Model standards, businesses have the flexibility to export data from Dynamics 365 to other cloud services and applications using an industry-standard format, greatly simplifying the standardization of exported and imported data. To facilitate this business need, Dynamics 365 has several built-in export services.

### Export to Azure Data Lake

The [Export to Azure Data Lake](/dynamics365/fin-ops-core/dev-itpro/data-entities/azure-data-lake-overview) for finance and operations apps is the preferred option to continuously export data from Dynamics 365 finance and operations apps to Azure Data Lake Storage Gen2. The service supports initial and incremental writes for table data and metadata. Any data or metadata changes are automatically pushed to the Azure Data Lake without any additional action.

Azure Data Lake Storage Gen2 is the foundation for building enterprise data lakes on Azure and provides low-cost, tiered storage with high availability and disaster recovery capabilities.

### Data Export Service

The [Data Export Service](/power-platform/admin/replicate-data-microsoft-azure-sql-database) replicates data from the Dataverse database to an external Azure SQL Database or an SQL Server on Azure virtual machines. This service intelligently syncs all data initially, and thereafter syncs the data on a continuous basis as delta changes occur in the system, enabling several analytics and reporting scenarios on top of Azure data and analytics services. Data Export Service reached end-of-support and end-of-life in November 2022 and was replaced by Azure Synapse Link for Dataverse.

### Azure Synapse Link for Dataverse

[Azure Synapse Link for Dataverse](/powerapps/maker/data-platform/export-to-data-lake) enables our customers to get near real-time insights over their data in Microsoft Dataverse. With a few clicks, customers can bring their Dataverse data to Azure Synapse, visualize data in your Azure Synapse workspace, and rapidly start processing the data to discover insights using advanced analytics capabilities for serverless data lake exploration, code-free data integration, data flows for extract, transform, load (ETL) pipelines, and optimized Apache Spark for big data analytics. Customers can use the familiarity of T-SQL to analyze big data and gain insights from it, while optimizing their data transformation pipeline to leverage the deep integration of Azure Synapse with other Azure services such as Power BI Embedded, Azure CosmosDB, Azure Machine Learning, and Azure Cognitive Services.

Azure Synapse Link for Dataverse is the fastest path to success for our customers to analyze data and generate insights as our experiences are ready to run as soon as you launch your Azure Synapse workspace.

### Bring your own database (BYOD)

The [bring your own database (BYOD)](/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database?toc=/dynamics365/finance/toc.json) feature lets organizations export data from the finance and operations apps into an external Azure SQL database. BYOD helps support scenarios where organizations may need to export data for unification or other purposes.

## Embedded intelligence

Dynamics 365 apps with embedded intelligence, such as [Sales Insights](/dynamics365/ai/sales/overview) and [Customer Service Insights](/dynamics365/ai/customer-service-insights/overview), allow organizations to use AI without depending on highly skilled resources. These apps continuously analyze your data and generate insights to help you understand business relationships, evaluate activities and interactions with customers, and determine actions based on those insights.

Unified data results in a 360-degree view of customers to ensure high-quality decision-making and predictions informed by the best, most recent data.

## Power Platform

The [Power Platform](/power-platform/) <!-- <T.G. removing figure, adding hyperlink instead> (Figure 13-6)--> enables organizations to analyze, act on, and automate the data to digitally transform their businesses. The Power Platform today comprises four products: Power BI, Power Apps, Power Automate, and Power Virtual Agents.

### Power BI

Power BI is both part of the Power Platform and stands on its own by bridging the gap between data and decision-making. Power BI lets business analysts, IT professionals, and data scientists collaborate seamlessly, providing a single version of data truth that delivers insights across an organization. Learn more at [Power BI](/power-bi/).  

Power BI helps you analyze your entire data estate within the Dynamics 365 or Azure platforms, or external sources. Power BI can connect individually with siloed sources to provide reporting and analytics, or it can connect with data stores within or outside of Dynamics 365. As data can come from multiple sources, organizations should analyze how Power BI will connect with those sources as a part of their data estate pre-planning.

Making data available to all users is risky. Security in reporting and analytics should be aligned with your business solution. Be sure to have your data governance in place, and periodically review who needs access to which information. This may be a time-consuming process, but your data must be protected, secured, and only accessible to those who truly need it.

### Power Apps, Power Automate, and Power Virtual Agents

With [Power Apps](/power-apps/), you can consume, create, and complement information to contribute to scale and efficiency for the users consuming that data. Organizations can also get accurate insights by adding low-code AI tools to their process automation via Power Automate. Power Virtual Agents help you create and manage powerful chatbots without the need for code or AI expertise, and monitor and improve chatbot performance using AI and data-driven insights.

## Microsoft Azure

:::image type="content" source="media/azuredatawarehousearchitecture.png" alt-text="azure data warehouse architecture" lightbox="media/azuredatawarehousearchitecture.png":::

With Dynamics 365 apps at the center of the data estate, Azure provides an ideal platform <!-- <T.G. figure reference not needed (Figure 13-7)--> for hosting services for business workloads, services, and applications that can easily interact with Dynamics 365 apps. Built-in services in Dynamics 365 let you export data as needed or scheduled. Power BI can aggregate information from Dynamics 365 and Azure sources into an integrated view, and Power Apps can access both Dynamics and Azure sources for low-code, custom applications designed for business use.

### Azure cloud platform

For data estates that include Dynamics 365 and other platforms, Azure can help with unification of data to generate insights. There are multiple options within the Azure cloud platform to ingest, store, prepare, model, and visualize data <!-- <T.G. reference not required>(Figure 13-8)-->, as well as build intelligence on top of that data—whether it's siloed or unified.  

:::image type="content" source="media/moderndataplatformreferencearchitecture.png" alt-text="modern data platform reference architecture" lightbox="media/moderndataplatformreferencearchitecture.png":::

### Azure Stack

Azure Stack is a portfolio of products that allows you to use embedded intelligence to extend Azure services and capabilities to your environment of choice—from the datacenter to edge locations and remote offices. You can also use it to build and deploy hybrid and edge computing applications, and run them consistently across location boundaries.

### Data load, ingestion, and pipeline orchestration

Azure Data Factory is a hybrid data integration service for creating, scheduling, and orchestrating ETL and extract, load, and transform (ELT) workflows. Organizations can use Azure Data Factory to combine Common Data Model data and other data sources, and process that data for unique insights. Azure Event Hubs can ingest data streams generated by a client application.

### Data store

Azure Blob Storage offers massively scalable object storage for any type of unstructured data—such as images, videos, audio, and documents—while Azure Data Lake Storage eliminates data silos with a single and secured storage platform.

### Machine learning and AI

Azure Databricks provides a cloud-hosted Apache Spark cluster where data engineers, data scientists, and business users can collaborate to train their models and get analytics.

The Azure Machine Learning service gives developers and data scientists a range of productive experiences to build, train, and deploy machine learning models faster.

Azure Cognitive Services puts AI within reach of every developer—without requiring machine-learning expertise. It only takes an API call to embed the ability to see, hear, speak, search, understand, and accelerate decision-making in your apps.

### Model and serve

Azure Analysis Services employs enterprise-grade analytics as a service (AaaS) to govern, deploy, test, and deliver business intelligence solutions.

Azure Synapse Analytics is a fast, flexible, and trusted cloud data warehouse that lets you scale, compute, and store data elastically and independently with a massively parallel processing architecture. It can scale across proprietary SQL and open-source databases and manage analytics workloads to provide fast, cost-effective power over any data—whether it is structured, semi-structured, run in real time, or globally distributed.

Azure Cosmos DB is a fully managed NoSQL database service for modern app development.

## Synergy

Getting maximum value from your data requires a modern data estate based on a data strategy that includes infrastructure, processes, and people.

Your data can flow inside a cloud solution or via synergy with other components and platforms to provide an infrastructure and processes for analyzing data and producing actionable outcomes.

People are a big part of the process, and the data journey will often start and finish with them. The insights and actionable outcomes will allow them to make better decisions—for themselves and the business.
> [!IMPORTANT]
> Due to budget, time, or skills constraints, some organizations decide to deliver a business solution as a first step, with a plan to improve insights and analytics capabilities at some point in the future. Insights and analytics should be addressed in the early phases of a business solution, even if it doesn't yet include all scenarios. Leaving these vital elements until later can affect the business and the user experience, eventually reducing adoption, increasing costs, and giving a negative perception of the value the solution has to offer.
<!-- T.G.<Make this part of the introduction instead>
# Conclusion

In this chapter, we discussed how organizations are becoming more competitive, expanding their global reach to attract customers, and using business intelligence solutions to make the most of their data.

While seeking data on how customers interact with their products and services, organizations are acting on that data to give customers access to more content, new purchasing channels, and brand options. By deeply understanding customer behavior, organizations can engage customers proactively and make predictions about their future behavior.

Successful organizations will use data to empower their employees, intelligently engage their customers, transform their products and services, and optimize their operations. They'll also use data to reduce operational risks and costs, and to respond to opportunities and market changes to meet their customers' needs.

Business intelligence, reporting, and analytics should not be an afterthought. Focusing on building a unified and modern data estate gives organizations access to augmented analytics and embedded intelligence solutions, which will be the differentiator in the future. By changing the ways that they use data to understand and engage with their customers, organizations can reach each customer at the right time, on the right channel, with the right message, for the right outcome.
-->
