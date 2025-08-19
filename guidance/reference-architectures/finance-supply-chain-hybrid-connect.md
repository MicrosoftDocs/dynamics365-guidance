---
title: Business Solution with Connections to Online and On-Premises Apps
description: Learn to integrate Dynamics 365 with on-premises CRM systems using Azure Logic Apps middleware. Discover real-world architecture patterns for enterprise resource planning.
author: edupont04
contributors: edupont04
ms.topic: reference-architecture
ms.date: 08/19/2025
ms.author: edupont
ms.reviewer: edupont
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-description
  - ai-seo-date:07/28/2025
---
# Business solution with connections to online and on-premises apps

***Applies to***: ***Dynamics 365 Finance, Dynamics 365 Human Resources, Dynamics 365 Supply Chain Management, Dataverse, Azure Logic Apps, Azure Synapse.***

This solution combines Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Azure Logic Apps, Azure Synapse for data warehousing, and a partner solution, Lasernet, to meet integration needs with other applications. It's based on an implementation project with an organization that migrated from Dynamics AX to Dynamics 365 Finance and Dynamics 365 Supply Chain Management.  

## Introduction

The implementation project focused on replacing the legacy application. As a result, the reference architecture illustrates integration with 12 external applications. It uses Azure Logic Apps as middleware for transformation and to seamlessly transfer data through files and the JSON format to support the OData RESTful service. It uses Azure Synapse to expose data for data warehousing purposes. Power BI is used to build analytical reports referencing data in Azure Synapse. Electronic reporting is configured for vendor payments and customer direct debits. The key requirement of this solution is to develop a custom integration to enable seamless connectivity between Dynamics 365 and an on-premises CRM application. Since the CRM application isn't cloud-based, the out-of-the-box dual-write solution couldn't be used. Instead, we built an integration using Azure Logic Apps as middleware. Azure Logic Apps acts as a protective layer for the Dynamics 365 solution, and all inbound and outbound integrations are routed through Azure Logic Apps.

## Architecture

This diagram illustrates the architecture for the solution.

:::image type="content" source="media/finance-supply-chain-hybrid-connect-architecture-diagram.png" alt-text="Diagram showing Dynamics 365 Finance and Supply Chain Management connected to external applications through Azure Logic Apps middleware." lightbox="media/finance-supply-chain-hybrid-connect-architecture-diagram.png":::

<!-- Download a PowerPoint file with this architecture.

:::image type="content" source="./media/image2.emf" alt-text="Screenshot of the PowerPoint architecture diagram file for download."::: -->

## Dataflow

- *Accounts receivable*:

  1. Master data for customers is created both in Dynamics 365 and in the on-premises CRM application. The data is kept in sync through the real-time OData restful service through Azure Logic Apps.

  1. Master data for physical products is created in Dynamics 365 and exposed to the CRM application through Azure Logic Apps.

  1. Sales orders are created both in Dynamics 365 and the CRM application. The data is kept in sync through the file-based recurrence data job created by composite data entity through Azure Logic Apps.

  1. Sales orders are processed and invoiced in Dynamics 365.

  1. The final invoices are sent to the CRM application through Azure Logic Apps.

  1. Customer payments are made in Dynamics 365. With electronic reporting, the payments are sent to the Customer Direct Debits application through Azure Logic Apps.

- *Accounts payable*:

  1. Master data for vendors is created in Dynamics 365 and then exposed to the Basware application through Azure Logic Apps.

  1. Purchase orders are created, product receipts performed, and both sets of data is exposed to the Basware application through Azure Logic Apps.

  1. Vendor invoices are booked in the Basware application, and the data is consumed from Basware to Dynamics 365 through Azure Logic Apps.

  1. Vendor payments are performed in Dynamics 365. With electronic reporting, the payments are sent to the Vendor Payments application through Azure Logic Apps.

- *Finance*:

  1. The chart of accounts is created in Dynamics 365 and then exposed to the Basware application through Azure Logic Apps.

  1. Travel and expense entries that are made in the Workday application are consumed in Dynamics 365 through Azure Logic Apps.

  1. Master data for financial dimensions of locations, departments, and cost centers are created in Workday and is transferred to Dynamics 365 through Azure Logic Apps.

- *Human Resources*:

  1. Master data for employees is created in Workday. The data is consumed in Dynamics 365 through Azure Logic Apps.

  1. Employee salary processed in the applications H&L and Hogia is transferred to Dynamics 365 through Azure Logic Apps. Dynamics 365 posts the data as general journal lines.

## Components

The following components are used in the reference architecture.

- Azure Logic Apps act as a middleware and is used for data transformation, mapping the data between source and target system and to seamlessly transfer the data between source and target application.

- Azure Synapse is configured and used for Data Warehousing purposes.

- Power BI is used for analytical reports to be developed and enabled
  access to Business users.

## Scenario details

We based this reference architecture on a migration project for an organization that used Dynamics AX 2012, which is out of support from Microsoft. The organization wanted a modern version of Dynamics AX, which they used for many years with many customizations and a large database as a result. We decided to use Dynamics 365 Finance and Dynamics 365 Supply Chain Management since many custom-built capabilities in the old solution are now part of the default version. The organization decided not to migrate all data from the old solution, just master data and open transactions.  

### Potential use cases

This solution was created for a full-service supplier of safety and security solutions for private homes and small businesses organization. It can also be applied to industries such as financial institutes or fast-moving consumer goods (FMCG). Any organization can use this architecture if it uses multiple business applications and wants heavy but seamless integrations between the applications.

## Considerations

These considerations help implement a solution that includes Dynamics 365. Learn more at [Dynamics 365 guidance documentation](/dynamics365/guidance/).

### Cost optimization

Cost optimization is about looking at ways to reduce unnecessary expenses and improve operational efficiencies. For more information, see [Overview of the cost optimization pillar](/azure/architecture/framework/cost/overview).

## Related content

Review the following related architecture guides, solutions, and other guidance content:

- [Azure Logic Apps overview](/azure/logic-apps/logic-apps-overview)

- [Export finance and operations data to Azure Synapse Link](/power-apps/maker/data-platform/azure-synapse-link-select-fno-data)

- [Azure Synapse Link for Dataverse: Transitioning from Export to Azure Data Lake to Azure Synapse Link (TechTalk)](https://community.dynamics.com/blogs/post/?postid=9d78569b-b08f-ee11-8179-000d3a4fe8f7)
<!-- 
## Tags

*Industries:* Public Utilities (40-49), Finance, Services (70-89)

*Stakeholders:* Accounts payable, Accounts receivable, Administrative,
Audit, Finance, Human Resources, IT, Purchasing.

*Products:* ***Dynamics 365 Finance, Dynamics 365 Human Resources,
Dynamics 365 Supply Chain Management, Dataverse, Azure Logic Apps, Azure
Synapse.*** -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Other contributors:

- [Ananda Subramanian](https://www.linkedin.com/in/ananda-subramanian-a3537725/)

- [Kishore Jadhav](https://www.linkedin.com/in/kishorworld/)
