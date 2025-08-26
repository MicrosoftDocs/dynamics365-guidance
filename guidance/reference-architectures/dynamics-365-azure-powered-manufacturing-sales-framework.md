---
title: Dynamics 365 and Azure-powered manufacturing sales framework
description: Learn how to modernize sales processes in manufacturing with Dynamics 365 and Azure.
author: vibhutinair23
ms.author: vibhutinair
ms.topic: reference-architecture
ms.date: 08/13/2025
---

# Dynamics 365 and Azure-powered manufacturing sales framework

***Applies to: Dynamics 365 Sales, Power Automate, Power Apps, Power Pages, Dataverse, Azure Logic Apps, Azure Functions, Azure Data Lake, Azure Synapse, Azure Key Vault, Azure SQL Database, Azure Active Directory***

This solution uses Microsoft technologies to modernize Contoso's sales and data management solutions to build a solution that addresses Contoso's challenges. The new solution includes the following apps and services:

- Dynamics 365 Sales as the core customer relationship management (CRM) solution
- Dataverse for custom data structures
- Power BI with Azure Data Lake for analytics
- Power Pages for branded external access
- SharePoint for document collaboration

Also included are Azure Integration Services with Azure Data Lake, Azure Functions, Logic Apps, Synapse, Azure SQL, and Service Bus, and Power Automate cloud flows that enable automation and scalability.

In total, the new solution addresses these challenges for Contoso:

- Inefficient sales processes
- Fragmented data across systems
- Limited visibility into performance
- Outdated legacy constraints
- Poor partner/customer engagement

By automating workflows, centralizing data into an Enterprise Data Hub, and delivering insights through Dynamics 365 and Power BI, it enhances efficiency, accuracy, and stakeholder access. Tailored for the manufacturing industry, specifically build-to-order industrial product manufacturers like Contoso (custom HVAC units), this solution supports precise sales management, territory alignment, and data-driven forecasting—key to meeting customer specs and staying competitive in complex sales cycles.

## Introduction

This section provides an overview of the business context and vision for the proposed solution.

### Business context

Contoso, a manufacturer of build-to-order industrial HVAC units tailored to customer specifications, wants to modernize its sales ecosystem through digital transformation. The company empowers its sales partners and customers with streamlined processes, accurate forecasting, and actionable insights, fixing inefficiencies in its current Dynamics 365 environment.

### Vision

The vision is to deliver an integrated Dynamics 365 and Azure-based solution that improves Contoso's sales capabilities, centralizes data, and shows real-time performance metrics. Advanced automation, analytics, and a scalable integration framework help Contoso achieve operational excellence and strengthen its competitive position in the HVAC manufacturing industry.

### Purpose

This reference architecture article outlines the design and implementation strategy for Contoso's Dynamics 365 Sales solution, integrated with Azure services, to modernize and streamline its sales processes. The initiative aligns Contoso's existing Dynamics 365 environment with a future architectural vision, improving operational efficiency, data-driven decision making, and customer engagement for its build-to-order industrial HVAC manufacturing business. This article is a blueprint for stakeholders, architects, and implementation teams to learn the scope, technical approach, and business value of the solution.

### Applicability and stakeholders

This reference architecture targets use cases like sales process optimization, territory management, and data-driven forecasting, making it ideal for the manufacturing industry—especially manufacturers of custom, build-to-order products like industrial HVAC units. Use this reference architecture early in the implementation lifecycle, during planning and design, to guide solution development and make sure it aligns with business goals.

Key stakeholders include business leaders (sales and operations managers), IT architects, Dynamics 365 admins, Azure integration specialists, and external partners (sales representatives), all critical to shaping and building the architecture.

### Scope

The project covers the reimplementation and improvement of Contoso's Dynamics 365 Sales environment, focusing on key entities like Opportunities, Quotes, Quote Line Items, Orders, Products, Goals, and Forecasting. It includes Account and Contact management, onboarding and offboarding automation, Activity Management, Collaboration, and SharePoint integration. Territory Management uses a hierarchical structure (Regions, Counties, Cities/ZIP Codes), supported by an extended data model to track assignment activities. The solution uses Dataverse as the core data platform, with real-time operational reporting through Dynamics 365 dashboards and enterprise analytics through embedded Power BI reports from Azure Data Lake. A robust integration framework, built on Azure technologies (Azure Data Lake, Azure Functions, Azure Logic Apps, Azure Synapse, and Cloud Flows), sets up reusable patterns for enterprise data management, real-time point-to-point (P2P) integrations, and a medallion architecture for data layer and pipelines. More features include Power Pages for external access, extended security roles, and automated business processes to support forecasting and territory-based goal setting.

### Conceptual diagram

The conceptual diagram shows a high-level view of the system architecture. It includes:

- **Users**: Sales Representatives, Regional Managers, Marketing Directors, and Sales Directors, representing key stakeholders across Contoso's sales ecosystem.
- **Client Layer**: Apps like Sales Hub, Field Service, Partners MDA, Partners Portal, SAP, and a Quoting Tool, available on desktop and mobile devices.
- **Identity**: Managed through Microsoft Entra Identity for secure access across the tenant.
- **Application Layer**: Dynamics 365 apps, Office 365 tools, and Azure Communication Services.
- **Platform Layer**: Power Platform (Web Services, Security, Workflow, Form Engine) and Dynamics 365 tenant, supported by Copilot and Workspace tools.
- **Data Layer**: Dataverse, integrated with Azure Data Services (SQL, Data Lake) and on-premises Mainframes/ERP systems.
- **Integration Layer**: Azure Integration Services (Functions, Logic Apps, Synapse, Data Factory, Service Bus) and Cloud Flows, connecting cloud apps and SAP S/4HANA.

The following diagram shows the end-to-end flow from users to backend technologies, highlighting the integration of Dynamics 365, Azure, and third-party systems in a phased deployment:

:::image type="content" source="./media/dynamics-365-azure-powered-manufacturing-sales-framework-contoso.svg" alt-text="Diagram showing the end-to-end flow from users to backend technologies, emphasizing the integration of Dynamics 365, Azure, and third-party systems in a phased deployment." lightbox="./media/dynamics-365-azure-powered-manufacturing-sales-framework-contoso.svg":::

## Architecture

This diagram shows the end-to-end integration framework for Contoso's Dynamics 365 and Azure-powered sales solution. It highlights how data and processes flow across users, applications, and backend systems to modernize sales, quoting, and enterprise resource planning (ERP) integration. The architecture uses phases (Phase I and Phase II) for a structured rollout that fits Contoso's build-to-order HVAC manufacturing needs.

:::image type="content" source="./media/dynamics-365-azure-powered-manufacturing-sales-framework-architecture.svg" alt-text="Diagram showing the end-to-end integration framework for Contoso's Dynamics 365 and Azure-powered sales solution." lightbox="./media/dynamics-365-azure-powered-manufacturing-sales-framework-architecture.svg":::

[Download a Visio file](https://github.com/microsoft/dynamics365patternspractices/blob/main/architectures/) with this architecture. To download an architecture, choose the file in the explorer, and then choose the download raw file icon.

> [!NOTE]
> This reference architecture shows a specific implementation project that connects to SAP. Solutions that connect to Dynamics 365 finance and operations apps use different architectures.

## Dataflow

This section describes the data flow and integration processes in the architecture. It details how data moves between components and systems to support Contoso's sales operations. The numbers refer to the numbered callouts in the architecture diagram.

### Quoting tool online enhancement

This component enhances Contoso's quoting process by integrating real-time data flows between the Quoting Tool, Data Hub, and managerial systems.

1. The lines marked as *1a* send forecasting data to the Data Hub from the Quoting Tool. It's a real-time transfer of quoting and forecasting data from sales representatives to the Data Hub, enabling immediate visibility into sales projections.

   The lines marked as *1b* send user data from the Data Hub to the Quoting Tool. It's real-time synchronization of manager-approved data (pricing, approvals) to the Quoting Tool, ensuring alignment with business rules.

3. The lines marked as *3* represent long-term job data storage. Data from the Quoting Tool is archived in Azure SQL. Periodically, data is sent to the Data Hub for historical analysis and reporting to support a long-term sales trend analysis.

### Data Hub – Dynamics 365 implementation

The Data Hub serves as the centralized integration layer that connects Dynamics 365, Azure services, and external systems.

4. The line marked as *4* sends data from the Quoting Tool that stored in Azure SQL to the Data Hub.  Data from Azure SQL is ingested into the Data Hub to help ensure a unified repository for quoting metrics.

5. The lines marked as *5* connect the legacy mainframe data to the Data Hub. Legacy data, such as orders or inventory is integrated in different ways:

      a. Logic App calls API: Retrieves only updated records for efficiency.

      b. Functions App gets API token: Secures access with dynamic token generation.

      c. Logic App writes to Data Lake: Stores processed data in Azure Data Lake's medallion architecture (Bronze, Silver, Gold layers) for scalability.

6. The line marked as *6* connects the Data Hub with Dataverse: A Synapse Pipeline/notebook loads transformed data into Dataverse so that  Dynamics 365 can use enriched datasets.

7. The line marked as *7* connects Dataverse with the Data Hub: Through Azure Synapse Link, updates from Dataverse synchronize back to the Data Hub for analytics.

8. The line marked as *8* represents Power Pages that show data from Dataverse to external stakeholders, such as sales partners, so that they get secure, branded access to quoting and order data.

9. The line marked as *9* connects Power BI to the Data Hub to generate real-time reports and dashboards and offer insights into sales performance, territory goals, and forecasting accuracy.

This setup ensures a single source of truth, critical for Contoso's complex manufacturing workflows.

### SAP implementation

Integration with SAP systems enhances ERP capabilities and real-time data exchange:

10. The line marked as *10* connects SAP to the Data Hub and, by extension, Dataverse for batch processing. Scheduled batch jobs transfer SAP data, such as sales orders or supplier details, to the Data Hub, then to Dataverse for consumption in Dynamics 365.

11. The line marked as *11* connects Dataverse to the Data Hub and then to SAP for batch processing. Updates from Dynamics 365, such as order confirmations, flow back to SAP through the Data Hub, maintaining synchronization.

12. The line marked as *12* represents Azure Service Bus (ASB) that enables near real-time updates between SAP and Dynamics 365, supporting urgent order adjustments.

    In the current version of the diagram, the number 12 is missing, but it's the line that connects SAP with Dataverse through ASB.

This integration aligns SAP's operational data with Dynamics 365's sales processes, optimizing Contoso's end-to-end supply chain.

The following diagram provides a detailed visualization of the data flow process.

:::image type="content" source="media/dynamics-365-azure-powered-manufacturing-sales-framework-sequential.svg" alt-text="Diagram showing the sequential data flow between SAP, DataHub, and Dataverse." lightbox="media/dynamics-365-azure-powered-manufacturing-sales-framework-sequential.svg":::

The following steps outline the sequential flow.

- **Quote creation in Quoting Tool**: The process initiates with the creation of a quote in the Quoting Tool, which serves as the starting point for the data flow.
- **Quote pushed to Dataverse**: The created quote is then pushed directly to Dataverse for initial storage and processing.
- **Quote qualification in Dataverse**: Within Dataverse, the quote is qualified, indicating that it's reviewed and deemed ready for the next step.
- **Flag pushed back to Quoting Tool**: After qualification, a flag is sent back to the Quoting Tool to indicate that the quote is ready, triggering the submission of an order to SAP.
- **Order submission to SAP**: The Quoting Tool submits the order to SAP through the SAP API, where it's processed further (generating Sales Orders, Sales Order Details, and Customer Asset data).
- **Data transfer to Data Lake**: The data from SAP and the Quoting Tool is transferred to the Data Lake, the data is organized into Silver Layer and Gold Layer, enhancing its structure and usability for analytics.
- **Data integration into Dataverse**: The processed data from Synapse is then integrated into Dataverse.
- **Data utilization in Power BI**: Finally, Power BI accesses the data in Dataverse for the creation of dashboards and reports, completing the data flow and enabling business intelligence and decision-making processes.

## Components

The components used in this architecture include:

- **Dynamics 365 Sales**: Serves as the core CRM platform, managing opportunities, quotes, orders, products, goals, forecasting, accounts, contacts, and hierarchies of territories. It provides real-time operational dashboards, model-driven apps, business process flows (BPFs), and native security features.
- **Microsoft Dataverse**: Acts as the foundational data layer, extended with custom tables and columns to support territory management, goals automation, and hierarchical data structures. It enables seamless data integration and real-time reporting.
- **Power BI**: Embedded within Dynamics 365, it uses Azure Data Lake as a data source to deliver enterprise-level analytics, offering detailed insights into sales performance, territory metrics, and forecasting accuracy.
- **Power Pages**: Provides a branded, external-facing interface for sales representatives and partners, integrated with Dataverse for secure data access and enhanced with agents from Copilot Studio for self-service capabilities.
- **Microsoft SharePoint**: Integrates with Dynamics 365 for document management and collaboration, exposing libraries within the portal for Knowledge Management features.
- **Azure Integration Services**:
  - **Azure Data Lake**: Centralizes data storage and supports Power BI reporting with a medallion architecture (Bronze, Silver, Gold layers) for scalable data processing.
  - **Azure Functions**: Enables serverless automation for real-time processes like order syncing and forecasting updates.
  - **Azure Logic Apps**: Orchestrates automated workflows, such as onboarding/offboarding and forecasting approvals.
  - **Azure Synapse**: Provides advanced analytics and data integration capabilities for enterprise reporting.
  - **Azure Service Bus (ASB)**: Facilitates real-time, point-to-point (P2P) integrations for near real-time data synchronization.
- **Cloud Flows (Power Automate)**: Automates business processes within Dynamics 365, such as territory assignments and goal calculations.
- **Mainframe Integration**: Syncs legacy order data into the solution through the Enterprise Data Hub, ensuring a unified data ecosystem.

This technology stack combines Dynamics 365's CRM capabilities with Azure's cloud infrastructure and analytics tools to create a scalable, integrated solution tailored to Contoso's needs.

## Scenario details

Contoso faces several challenges in its current sales ecosystem that this solution addresses:

- **Inefficient sales processes**: Manual onboarding/offboarding, territory management, and forecasting processes lead to delays and inaccuracies, hindering sales team productivity.
- **Fragmented data**: Disparate data sources (mainframes, CRM, and external tools) result in inconsistent account, contact, and order information, complicating reporting and decision-making.
- **Limited visibility**: Lack of real-time operational insights and detailed analytics restricts Contoso's ability to track territory performance, set accurate goals, and forecast sales effectively.
- **Legacy system constraints**: The existing Dynamics 365 environment and mainframe integration don't align with a future-state vision, lacking automation and scalability for modern sales demands.
- **Partner and customer engagement**: Sales partners and end customers require streamlined access to data and self-service options, which the current system can't efficiently provide.

The solution resolves these issues by automating processes, centralizing data into an Enterprise Data Hub, delivering actionable insights through Dynamics 365 and Power BI, and providing a branded portal for external stakeholders. It supports Contoso's digital transformation by enhancing operational efficiency, data accuracy, and customer satisfaction.

The *Dynamics 365 and Azure-powered manufacturing sales framework* reference architecture is for scenarios where manufacturing companies, particularly those producing build-to-order industrial products like custom HVAC units, need to modernize their sales processes and integrate legacy systems such as mainframes and SAP. It applies to situations requiring real-time quoting, territory management, and forecasting, with seamless data synchronization across CRM (Dynamics 365), ERP (SAP), and external tools like Quoting Tools. This architecture is also valuable for organizations seeking to enhance customer and partner engagement through portals, use advanced analytics through Power BI, and implement a scalable, phased integration strategy to support complex sales and supply chain workflows.

### Potential use cases

This solution is for a manufacturing organization, specifically Contoso, a producer of build-to-order industrial HVAC units. Industries such as automotive, aircraft, agriculture, and energy, where custom product manufacturing and complex sales processes are prevalent can also use it. Any organization can use it that's seeking to modernize sales ecosystems, integrate legacy systems (mainframes, SAP), and use real-time quoting, territory management, forecasting, and analytics through Dynamics 365 and Azure, particularly those with a need for scalable, phased integration and enhanced customer/partner engagement. More use cases may include retail (for customized product sales) and facilities (for real estate with tailored service offerings), which share similarities with manufacturing in requiring data-driven sales and integration but differ in their focus on consumer-facing or property-specific workflows.

You can use this solution to:

- **Enhance sales efficiency**: Streamline quoting, forecasting, and territory management with real-time data integration across Dynamics 365, SAP, and external tools.
- **Centralize data management**: Establish a unified Data Hub to synchronize legacy systems (mainframes) and enable advanced analytics via Power BI.
- **Improve customer engagement**: Deploy branded Power Pages to provide seamless access for partners and customers, tailored to specific industry needs.

## Considerations

These considerations help implement a solution that includes Dynamics 365. Learn more at [Dynamics 365 guidance documentation](/dynamics365/guidance/).

Based on the Dynamics 365 and Azure-powered manufacturing sales framework solution for Contoso, address several key considerations to ensure a successful implementation.

- **Licensing and cost management** is critical because integrating Dynamics 365, Power Platform, and Azure services (Data Lake, Synapse, Logic Apps) requires careful planning to align with organizational budgets and usage patterns, as outlined in [the Dynamics 365 licensing documentation](https://www.microsoft.com/dynamics-365/products/customer-service/pricing).
- **Security and compliance** are paramount, particularly with sensitive customer and order data flowing between Dataverse, SAP, and mainframes. Set up Microsoft Entra Identity and Azure Key Vault to enforce role-based access control and encrypt data in transit, following industry standards for manufacturing.
- **Scalability and performance** are important, especially with real-time integrations (ASB, Azure Functions) and the medallion architecture in Azure Data Lake. Plan capacity to handle peak quoting and forecasting loads, as recommended in the performance optimization guides.
- **Data integration complexity** is a challenge. Use robust error handling and monitoring for pipelines (Synapse Link, Logic Apps) that connect legacy systems. Deploy in phases (Phase I and II) to reduce risks, as suggested in the integration best practices.
- **User adoption and training** is essential because diverse stakeholders (sales reps, managers, partners) use Power Pages and Portals. Provide tailored training programs to maximize the solution's value, aligning with the adoption strategies in the guidance.
- **Timeline and phased rollout** are important, especially for SAP and rep firm data flows. Define the rollout to align with manufacturing cycles and minimize disruption, using the phased approach detailed in the deployment documentation.

### Cost optimization

Cost optimization means finding ways to reduce unnecessary expenses and improve operational efficiency. For more information, see [Overview of the cost optimization pillar](/azure/well-architected/cost-optimization/).

For Contoso with 1,000 internal Dynamics 365 users, 2,000 external B2C-authenticated portal users, and an integrated data volume of 5,000 records per hour, the cost structure includes multiple components. For your use of the reference architecture, see [Dynamics 365 pricing](https://www.microsoft.com/dynamics-365/pricing-overview) for more information.

### Cost optimization strategies

To reduce costs, Contoso took the following into consideration:

- **License optimization**: Limit full Dynamics 365 licenses to active users (for example, 800 core users, 200 with Power Platform add-ons) and use read-only licenses for report-only users. This approach can save 10 to 20 percent on licensing.
- **Azure cost management**: Set up auto-scaling for Synapse and Data Factory, use reserved instances for predictable workloads, and archive cold data to Azure Blob Storage to lower Data Lake costs.
- **Portal usage efficiency**: Monitor B2C login patterns and buy login tiers strategically (for example, 2,500 logins at $2,200 per month versus 2,000 logins at $2,000), avoiding over-provisioning.
- **Data volume optimization**: Filter data pipelines (for example, `changedonly=true` in Logic Apps) to process only updated records. This approach can reduce compute costs by 20 to 30 percent.
- **Phased deployment**: Roll out core Dynamics 365 and Data Hub in Phase I. Delay SAP and portal expansions until you see initial benefits, deferring costs.

<!-- ## Procedure: Implement Azure Functions for real-time data processing in Data Hub

To configure and deploy an Azure Function to handle real-time data processing (for example, syncing Quoting Tool data to the Data Hub) as part of the reference architecture, follow these steps:

1. Open the [Azure Portal](https://portal.azure.com) and sign in with your Azure account.
2. Navigate to the **Function App** service by clicking **Create a resource**, then search for **Function App** and select **Create**.
3. Configure the basics:
   - **Subscription**: Select your Azure subscription.
   - **Resource Group**: Create a new group (for example, Contoso-DataHub-RG).
   - **Function App name**: Enter a unique name (for example, ContosoDataHubFunction).
   - **Runtime stack**: Select **.NET** or preferred language.
   - **Region**: Select the same region as your Azure Data Lake (for example, West US).
4. Set up hosting:
   - **Operating System**: Select **Windows** or **Linux**.
   - **Plan type**: Select **Consumption Plan** for cost efficiency.
   - **Storage account**: Create a new storage account (for example, contosodatastorage).
5. Review and create the Function App, then wait for deployment.
6. Once deployed, go to the Function App, click **Functions**, then click **+ Create** and select **HTTP trigger**.
7. Configure the HTTP trigger:
   - **Name**: Enter **ProcessQuotingData**.
   - **Authorization level**: Set to **Function** (requires a key).
8. To save and test the function, click **Get function URL** and use a tool like Postman to send a sample request.
9. Integrate with Logic Apps (step 5b from architecture) by adding an HTTP action to call this URL with the API token.

## Procedure: Configure Azure AD B2C for Power Apps Portals authentication

To set up Azure AD B2C authentication for 2,000 external portal users in the reference architecture, follow these steps:

1. Open the [Azure Portal](https://portal.azure.com) and ensure you're in the default directory.
2. Go to **Azure AD B2C** by selecting **Create a resource**, then search for **Azure AD B2C** and select **Create**.
3. Set up the B2C tenant:
   - **Organization name**: Enter **ContosoB2C**.
   - **Initial domain name**: Enter **contosob2c** (for example, contosob2c.onmicrosoft.com).
   - **Country**: Select **United States**.
4. Create the tenant, then switch to the new B2C tenant from the top directory switcher.
5. Register an application for the Power Apps portal:
   - Go to **App registrations** and select **+ New registration**.
   - **Name**: Enter **ContosoPortalB2CApp**.
   - **Redirect URI**: Set to `https://your-portal-domain.microsoftcrmportals.com/signin-azure-ad-b2c` (replace with your portal URL).
   - **Supported account types**: Select **Accounts in any identity provider or organizational directory**.
6. Note the application (client) ID after creation.
7. Generate a client secret:
   - Go to **Certificates & secrets** and select **+ New client secret**.
   - **Description**: Enter **PortalSecret**.
   - **Expires**: Set to **2 years**.
   - Copy the secret value and store it securely.
8. Set up a user flow:
   - Go to **User flows** and select **+ New user flow**.
   - Select **Sign up and sign in**, then enter **B2CSignupSignin** as the name.
   - Identity provider: Choose **Email signup**.
   - **User attributes**: Select **Email Address**, **Given Name**, and **Surname**.
   - **Claims**: Select **Email**, **Given Name**, **Surname**, and **Identity Provider**.
9. Link to Power Apps portal:
   - In the portal admin center, go to **Site Settings**.
   - Add the following settings:
      - **Name**: "Authentication/OpenIdConnect/ContosoB2C/ClientId"
      - **Value**: Paste the Application ID from step 6.
      - **Name**: "Authentication/OpenIdConnect/ContosoB2C/ClientSecret"
      - **Value**: Paste the client secret from step 7.
      - **Name**: "Authentication/OpenIdConnect/ContosoB2C/Authority"
      - **Value**: `https://contosob2c.b2clogin.com/contosob2c.onmicrosoft.com/B2CSignupSignin/v2.0`
10. Test the login by going to the portal URL and checking B2C authentication for external users.

## Procedure: Link Dataverse to Microsoft Fabric for data integration

Connect Dataverse to Microsoft Fabric for advanced analytics in the reference architecture. Follow these steps:

1. Open [Power Apps](https://make.powerapps.com) and sign in with admin credentials.
2. Navigate to **Environments** and select the environment linked to Dynamics 365.
3. Go to **Azure Synapse Link** from the left navigation pane.
4. Select **Microsoft OneLake** and click **Link to Microsoft Fabric**.
5. Choose a Power BI premium workspace:
   - Select a workspace in the same region (for example, West US) with a capacity SKU (for example, "F2" for trial).
   - If none exists, create one through the Fabric admin portal or sign up for a free Fabric trial.
6. Enable Parquet/Delta lake:
   - Check **Enable Parquet/Delta lake option** to allow Fabric access.
7. Add tables to Fabric:
   - Select **Manage tables** and then select **+ Add table**.
   - Choose key Dataverse tables (for example, Opportunities, Quotes, Accounts).
   - Wait for the initial sync to complete and verify the OneLake shortcut creation.
8. Refresh and monitor:
   - To update newly enabled tables, click **Refresh Fabric tables**.
   - Review downstream Power BI reports to ensure that there is no impact from changes.
9. Build analytics:
   - Open Fabric through **View in Microsoft Fabric** and create a lakehouse or report using synced Dataverse data for 5,000 records/hour processing. -->

<!--
## Next steps
-->

## Related patterns

The following patterns are available to help guide your implementation of the set customer credit limits business process.

### Event-driven architecture

[Event-driven architecture (EDA) style](/azure/architecture/guide/architecture-styles/event-driven): This guide explains event-driven design, applicable to real-time data flows (for example, 5,000 records/hour via ASB, Functions, and cloud flows), emphasizing asynchronous communication and scalability.

### Data lakehouse architecture

[Medallion lakehouse architecture](/azure/databricks/lakehouse/medallion): This resource explores how to implement the medallion architecture using a data lake as a middle integration layer to connect multiple systems, such as CRM (Dynamics 365), ERP (SAP), and external tools (Quoting Tool). It emphasizes the use of Delta Lake for data ingestion (Bronze), transformation (Silver), and analytics-ready aggregation (Gold), with integration services facilitating seamless data flow across systems. The article highlights practical examples of using Azure Databricks and integration tools to manage data pipelines, making it highly relevant to this architecture's Data Hub and real-time processing needs (for example, 5,000 records/hour).

## Related resources

- [Dynamics 365 Sales documentation](/dynamics365/sales/)  
- [Azure Functions documentation](/azure/azure-functions/)
- [Power Apps documentation](/power-apps/)  

<!--
## Tags

*Industries:* Agriculture (01-09), Construction (15-17), Manufacturing (20-39)

*Stakeholders:* Merchandising, Operations, Production, Project Management, Purchasing, Retail store operations, Sales, Warehouse

*Products:* Dynamics 365 Sales, Power Automate, Power Apps, Power Pages, Dataverse, Azure Logic Apps, Azure Functions, Azure Data Lake, Azure Synapse, Azure Key Vault, Azure SQL Database, Azure Active Directory
--->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributor.*

Principal author:

[Lorenc Koka](https://www.linkedin.com/in/lorenckoka/) \| Principal Solution Architect Dynamics 365
