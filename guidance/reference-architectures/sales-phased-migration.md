---
title: Key considerations for migrating to Dynamics 365 Sales
description: Discover how Dynamics 365 Sales, Power Platform, and Azure services enabled one of the largest CRM migrations with seamless system integration.
#customer intent: As a technical architect, I want to learn about the integration components used in the solution so that I can design a scalable and efficient architecture.
author: edupont04
ms.author: edupont
ms.reviewer: edupont
ms.date: 09/09/2025
ms.topic: reference-architecture
---
# Phased migration to Dynamics 365 Sales

This article describes architectures based on a project where two distinct opportunity management systems migrated to Dynamics 365 Sales. The result is one of the largest Dynamics 365 implementations to date.

The initiative uses a phased approach where they gradually transitioned parts of the organization to the new platform. Full synchronization between the legacy and new systems is critical to ensure uninterrupted operations.

The new system integrates seamlessly with the system it replaces and with critical peripheral systems that handle master data management, regulatory compliance, contact management, and more. Building the integrations requires efficient program management and technical skills to select the right technology.

This solution uses Dynamics 365 Sales, Power Apps, Dataverse, Azure Functions, Azure Data Lake, Azure Synapse, Azure Service Bus, Azure Application Insights, managed identities, Azure Key Vault, and Azure SQL Database.

## Architecture

The following subsections describe the different architectures for time-sensitive data and non-time-sensitive data, and the different flows for outbound and inbound data.

### Event-driven processing for time-sensitive data with a low-code trigger

:::image type="content" source="media/sales-phased-migration-time-sensitive-data.png" alt-text="Screenshot of event-driven processing architecture for time-sensitive data." lightbox="media/sales-phased-migration-time-sensitive-data.png":::

1. Outbound integration (green path)

    1. Power Automate cloud flow triggers are set up for specific tables in Dataverse that contain business-critical data. The triggers filter based on specific Dataverse events. When certain conditions are met, the triggers activate a cloud flow, ensuring that only necessary data changes initiate the flow. Power Automate cloud flows assemble the corresponding payload, including a timestamp for when the change occurred.

    2. The Power Automate flow places the payload in an Azure Service Bus Queue using the Azure Service Bus connector, associating each message with a unique session identified by the record's GUID.

    3. An Azure Function App is triggered by Azure Service Bus Queue messages, secured using Managed Identity. A session-aware queue, combined with the payload's timestamp, is employed to manage sequential processing concerns due to the asynchronous nature of Power Automate cloud flows. This approach defers processing to ensure messages for the same Dataverse record process sequentially.

    4. The message is mapped to the target data structures. The Azure Function App invokes the APIs of the target systems, using Azure Key Vault for credential management. Application Insights tracks informational and error level logs that the technical and support teams use for any necessary troubleshooting or maintenance activities.

    5. When an error occurs during processing, the payload and error are additionally stored in an Azure SQL Database. Based on the type of error, the Function App retries failures, or it sends alerts to the corresponding support teams via ticketing systems when manual intervention is necessary.

1. Inbound integration (orange path)

    1. External systems load transaction data into the Azure Service Bus Queue. The authentication mechanism uses OAuth2 credentials.

    2. An Azure Function App is triggered by the Service Bus Queue messages. The Azure Service Bus Queue is session-aware, using the unique identifier of the record, such as Account ID or Opportunity ID to establish sessions. This helps ensure that updates related to the same record are processed in sequence.

    3. The message is mapped to the Dataverse data structures. The Azure Function App then invokes Dataverse Upsert requests to transmit the data, specifying the Dataverse record's ID if available. Similar to the *Outbound* section in the previous step, Application Insights and an Azure SQL Database are utilized for error handling and informational purposes.

### Scheduled batch processing for non-time-sensitive data

1. Inbound integration

    :::image type="content" source="media/sales-phased-migration-non-time-sensitive-data-inbound.png" alt-text="Screenshot of scheduled batch processing for inbound integration." lightbox="media/sales-phased-migration-non-time-sensitive-data-inbound.png":::

    1. The complete dataset is loaded into Microsoft Dataverse.

    2. Delta changes for relevant records and their data points are extracted from Databricks as Parquet files.

    3. An Azure Synapse pipeline consumes the Parquet files and writes to Azure SQL staging tables.

    4. Once the data lands in the Azure SQL staging tables, the data gets converted to Dataverse-specific column types.

    5. Synapse pipelines use the copy process to write the resulting data into Dataverse.

1. Outbound integration

    :::image type="content" source="media/sales-phased-migration-non-time-sensitive-data-outbound.png" alt-text="Screenshot of scheduled batch processing for outbound integration." lightbox="media/sales-phased-migration-non-time-sensitive-data-outbound.png":::

    1. The connector between Dataverse and Azure Synapse Link replicates created or updated Dataverse data to the Synapse Data Lake at 15-minute intervals in a Delta Lake format.

    2. Pipelines run SQL queries to extract data out of the Synapse Data Lake.

    3. Pipelines generate Parquet files from the results of the SQL queries and send to the Data Warehouse, which is then processed into the downstream system.

    :::image type="content" source="media/sales-phased-migration-non-time-sensitive-data-outbound-process.png" alt-text="A diagram of a data processing process." lightbox="media/sales-phased-migration-non-time-sensitive-data-outbound-process.png":::

The connector between Dataverse and Azure Synapse Link exports data into a Data Lake in CSV format. After a 15-minute interval, the connector converts the data into Parquet files to exchange data with external systems.

## Considerations

These considerations help you implement a solution that includes Dynamics 365. Learn more at [Dynamics 365 guidance documentation](/dynamics365/guidance/).

### Cost optimization

Cost optimization focuses on reducing unnecessary expenses and improving operational efficiencies. Learn more at [Overview of the cost optimization pillar](/azure/well-architected/cost-optimization/).

Azure costs vary depending on the scale of the solution implemented. You can choose different performance and storage tiers, depending on the desired price point. Learn more at [Azure pricing](https://azure.microsoft.com/pricing/).

Dynamics 365 Sales licensing and pricing options depend on the number of users and other factors, including different tiers at different price points, depending on your needs. Learn more at [Dynamics 365 pricing overview](https://www.microsoft.com/dynamics-365/pricing-overview).

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Primary Contributors:

- [Lavanya Arthimalla](https://www.linkedin.com/in/lavanyaarthimalla)  \| Delivery Architect

- [Mike Dearing](https://www.linkedin.com/in/mikedearing) \| Lead Technical Architect, FastTrack Recommended Solution Architect (FTRSA), customer engagement apps

- [Anil Dasari](https://www.linkedin.com/in/anil-dasari-profile) \| Integration Architect

Other Contributors:

- [Kevin Jiang](https://www.linkedin.com/in/kevin-jiang-b8095585) \| Tech Consultant
