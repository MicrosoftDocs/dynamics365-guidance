---
title: How Dynamics 365 and Power Platform support your data estate
description: Discover how you can use Dynamics 365 and Power Platform to integrate, store, analyze, and act on data from various sources.
author: TimoGossen
ms.author: timogoss
ms.date: 01/23/2024
ms.topic: concept-article
ms.custom:
  - ai-seo-date: 01/23/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# How Dynamics 365 and Power Platform support your data estate

Dynamics 365 and Power Platform can help you build a modern data estate that meets your business needs. You can store and manage your business data securely within Dynamics 365 as part of your daily operations. You can also export or import data to and from various sources to create reports, workflows, apps, or other solutions.

With Dynamics 365 apps, you can also generate insights and analytics from the data you create and manage. For example, you can use the audience insights feature in Dynamics 365 Customer Insights to enrich your customer data and make better decisions.

In this article, we'll explore how Dynamics 365 and Power Platform work together with other technologies to create a modern data estate architecture.

## Common Data Model

One of the key technologies that enables a modern data estate is Common Data Model. Common Data Model is a shared language for business and analytical applications. It provides a set of standard schemas for common concepts such as people, budgets, and campaigns. This makes it easier to share and understand data across applications and processes.

The following diagram shows how Common Data Model works as part of a modern data estate:

:::image type="content" source="media/commondatamodel.png" alt-text="Diagram showing Common Data Model as a component of a modern data estate." lightbox="media/cdmschema.png":::

Common Data Model also supports extensibility. You can customize or create new schemas to fit your specific needs. [Learn more about Common Data Model](/common-data-model/).

Dynamics 365 uses [Dataverse](/power-apps/maker/data-platform/) to store and secure app data based on Common Data Model. Dataverse lets you build or extend apps using Power Apps directly against your business data.

The following diagram shows an example of the structure of a Common Data Model schema.

:::image type="content" source="media/cdmschema.png" alt-text="Diagram of a Common Data Model schema." lightbox="media/cdmschema.png":::

## Data unification components

To get the most value from your data estate, you need to be able to unify data from multiple sources into a single view to produce insights that can support, improve, or transform your operations.

Dynamics 365 offers several services and applications that can ingest data from various sources into Dataverse or other destinations. You can also design your own integrations.

### Customer Insights as a customer data platform

[Dynamics 365 Customer Insights](/dynamics365/customer-insights/audience-insights/overview) is a platform that combines transactional, behavioral, and demographic data from different sources in Dataverse to create a 360-degree view of your customers.

The following diagram shows an example of how Customer Insights works as a customer data platform:

:::image type="content" source="media/customerinsightssolution.png" alt-text="Diagram of a Customer Insights solution, with data unified to generate insights that lead to actions." lightbox="media/customerinsightssolution.png":::

Customer Insights also offers built-in analytics capabilities such as segmentation, churn analysis, and product recommendations. You can use Power BI to explore and visualize your customer data. You can also use Azure Machine Learning and Azure Cognitive Services to create custom models and enrich your data with AI.

## Dataverse and applications

Dataverse isn't just a data store. It's also a platform for creating applications. You can use Power Apps, Power Automate, Power BI, and Copilot Studio to build solutions that use your Dataverse data. You can also access data from other Dynamics 365 apps or external sources using connectors or APIs.

## Data export components

Sometimes you might need to export your data from Dynamics 365 to other services or applications for analysis, reporting, backup, or other purposes. Because data in Dataverse conforms to Common Data Model standards, Dynamics 365 offers several options for exporting your data in an easy, secure, and industry-standard way.

### Export to Azure Data Lake

The [Export to Azure Data Lake](/dynamics365/fin-ops-core/dev-itpro/data-entities/azure-data-lake-overview) service lets you export your Dynamics 365 finance and operations app data to Azure Data Lake Storage Gen2. This service supports initial and incremental writes for table data and metadata. Any changes in your Dynamics 365 data are automatically pushed to the Azure Data Lake without any extra steps.

Azure Data Lake Storage Gen2 is a scalable and cost-effective storage service for big data analytics. It offers low-cost, tiered storage with high availability and disaster recovery capabilities.

### Data Export Service

The [Data Export Service](/power-platform/admin/replicate-data-microsoft-azure-sql-database) replicates your Dataverse database to an external Azure SQL Database or SQL Server on Azure virtual machines. It syncs all your data initially, and then syncs any changes continuously as they occur in your system.

Data Export Service reached end-of-support and end-of-life in November 2022. It was replaced by Azure Synapse Link for Dataverse.

### Azure Synapse Link for Dataverse

[Azure Synapse Link for Dataverse](/powerapps/maker/data-platform/export-to-data-lake) enables you to get near-real&ndash;time insights from your Dataverse data. You can easily connect your Dataverse data to Azure Synapse Analytics, a powerful cloud service that combines data warehousing, big data processing, machine learning, and business intelligence.

With Azure Synapse Analytics, you can discover insights in your data using advanced analytics capabilities, like serverless data lake exploration, code-free data integration, data flows for extract, transform, load (ETL) pipelines, and optimized Apache Spark for big data analytics. You can also use Azure Machine Learning and Azure Cognitive Services to enhance your data with AI.

Azure Synapse Link for Dataverse is the fastest and easiest way to analyze your data and generate insights. You don't need to move or copy your data, and you can start using your Azure Synapse workspace as soon as you create it.

### Bring your own database (BYOD)

The [bring your own database (BYOD)](/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database?toc=/dynamics365/finance/toc.json) feature allows you to export your Dynamics 365 finance and operations app data to an external Azure SQL database. BYOD can help you integrate your data with other sources or systems for reporting or other purposes.

## Embedded intelligence

Some Dynamics 365 apps have embedded intelligence features that use AI to help you understand and improve your business performance. These features analyze your data and provide insights that can help you optimize your sales, customer service, marketing, or human resources processes.

For example, [Sales Insights](/dynamics365/ai/sales/overview) and [Customer Service Insights](/dynamics365/ai/customer-service-insights/overview) offer features such as conversation intelligence, predictive forecasting, sentiment analysis, and issue resolution.

Embedded intelligence features use Dataverse as the source of truth for your business data and Azure Machine Learning and Azure Cognitive Services for advanced analytics and AI capabilities.

## Power Platform

[Power Platform](/power-platform/) is a suite of no-code/low-code tools that let you analyze, automate, and build solutions using your data estate. Power Platform consists of four products: Power BI, Power Apps, Power Automate, and Microsoft Copilot Studio.

### Power BI

Power BI is a business intelligence tool that helps you turn your data into insights. You can use Power BI to connect to various data sources in Dynamics 365, Azure, or elsewhere. You can also create reports and dashboards that visualize your data in interactive ways.

Power BI is integrated with Dynamics 365 apps and Dataverse. You can use embedded Power BI reports within Dynamics 365 apps or access them from the Power BI service. You can also use the Dataverse connector in Power BI Desktop to query Dataverse data directly.

Power BI lets you collaborate with other users across your organization. You can share reports and dashboards with others or publish them on the web. You can also use natural language queries or chatbots to get answers from your data.

[Learn more about Power BI](/power-bi/).

### Power Apps, Power Automate, and Copilot Studio

[Power Apps](/power-apps/) lets you create custom apps that use your data estate without writing code. You can use prebuilt templates or start from scratch using a drag-and-drop interface.

[Power Automate](/power-automate/) lets you create workflows that automate tasks across applications using triggers and actions. You can use prebuilt templates or design your own flows using a graphical interface.

[Microsoft Copilot Studio](/microsoft-copilot-studio/fundamentals-what-is-copilot-studio) lets you create AI-powered chatbots that interact with your users using natural language. You can use a graphical interface to design your bot's conversations and logic.

All Power Platform apps let you use connectors or APIs to access data from Dynamics 365 apps, Dataverse, Azure services, or other sources.

## Microsoft Azure

Azure is a cloud platform that offers a range of services and tools for building, managing, and analyzing your data estate. You can use Azure to integrate, store, process, and visualize data from Dynamics 365 apps, Dataverse, or other sources. You can also use Azure to enhance your data with machine learning and AI.

The following diagram shows an example of how Azure can support your data estate architecture.

:::image type="content" source="media/azuredatawarehousearchitecture.png" alt-text="Diagram of Azure data warehouse architecture." lightbox="media/azuredatawarehousearchitecture.png":::

### Azure cloud platform

The Azure cloud platform offers multiple options for ingesting, storing, preparing, modeling, and visualizing data. You can also use Azure to build intelligence on top of your data, whether it's siloed or unified.

The following diagram shows an example of a modern data platform reference architecture that uses Azure services.

:::image type="content" source="media/moderndataplatformreferencearchitecture.png" alt-text="Diagram of how Azure services are part of a modern data platform reference architecture." lightbox="media/moderndataplatformreferencearchitecture.png":::

### Azure Stack

Azure Stack is a portfolio of products that lets you extend Azure services and capabilities to your own environment. You can use Azure Stack to build and deploy hybrid and edge computing applications that run consistently across different locations.

- **Azure Data Factory**: A hybrid data integration service that lets you create, schedule, and orchestrate Extract, Transform, Load (ETL) and ELT workflows.
- **Azure Event Hubs**: A big data streaming service that ingests data streams from various sources.
- **Azure Blob Storage**: A massively scalable object storage service for any type of unstructured data.
- **Azure Data Lake Storage Gen2**: A scalable and cost-effective storage service for big data analytics.
- **Azure Databricks**: A cloud-hosted Apache Spark cluster where data engineers, data scientists, and business users can collaborate to train their models and get analytics.
- **Azure Machine Learning**: A cloud service that lets you build, train, and deploy machine learning models faster and easier.
- **Azure Cognitive Services**: A collection of AI services that let you add vision, speech, language, search, and decision capabilities to your apps.
- **Azure Analysis Services**: An enterprise-grade analytics as a service (AaaS) that lets you govern, deploy, test, and deliver business intelligence solutions.
- **Azure Synapse Analytics**: A powerful cloud service that combines data warehousing, big data processing, machine learning, and business intelligence.
- **Azure Cosmos DB**: A fully managed NoSQL database service for modern app development.

## Synergy

To get the maximum value from your data, you need a modern data estate that aligns with your data strategy. Your data strategy should include the infrastructure, processes, and people that support your data goals.

Your data can flow inside a cloud solution or across different components and platforms to provide an infrastructure and processes to analyze your data and produce actionable outcomes.

People are a crucial part of the data journey. The insights and actionable outcomes help them make better decisions for themselves and the business.

> [!IMPORTANT]
> Due to budget, time, or skills constraints, some organizations decide to deliver a business solution as a first step, with a plan to improve insights and analytics capabilities later. We don't recommend this approach. You should address insights and analytics in the early phases of a business solution, even if it doesn't yet include all scenarios. Leaving these vital elements until later can affect the business and the user experience, reducing adoption, increasing costs, and giving a negative perception of the value the solution has to offer.

## Next steps

- Use the Success by Design [checklist](business-intelligence-reporting-analytics-checklist.md) to assess and improve your reporting and analytics strategy
