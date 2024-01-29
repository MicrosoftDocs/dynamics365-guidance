---
title: Case study in integration strategy
description: Learn how a public sector organization faced challenges with its initial Dynamics 365 integration architecture and how it redesigned its strategy to achieve better performance, cost savings, and data insights.
author: abunduc-ms
ms.author: abunduc
ms.date: 01/26/2024
ms.topic: conceptual
ms.custom:
 - ai-seo-date: 01/26/2024
 - ai-gen-docs-bap
 - ai-gen-title
 - ai-gen-desc
content_well_notification: AI-contribution
---

# Case study in integration strategy

This case study shows you how a public sector infrastructure service organization learned from its mistakes and adopted a better solution for integrating Dynamics 365 Customer Service with other applications.

## The challenge

The organization wanted to use Dynamics 365 Customer Service to manage its customer interactions. It also needed to integrate it with a public-facing website, several on-premises apps, and Microsoft 365, including SharePoint Online. One of the implementation objectives was to gather insights from the data that was scattered across different business applications.

## The initial solution

The organization hired an IT vendor that had experience building complex integrations using technologies such as IBM MQ and Microsoft BizTalk.

The team decided to use a microservices-based architecture. This meant they would build small, reusable components that communicated through service endpoints. They hoped this would give them the following benefits:

- Faster and independent development, deployment, and release cycles
- Simplicity of architecture to allow decoupled and reusable components
- Fault isolation

They also chose Azure API Management to manage their APIs securely.

## The problems

As the team started building and testing the initial components, they ran into some problems:

- The performance was slow for batch-integration scenarios, because they called the services as if they were doing point-to-point integration.

- They couldn't use standard features that were available with out-of-the-box approaches. For example, they couldn't integrate SharePoint Online with Power Platform easily.

- They decided to replicate all data to Dynamics 365 Customer Service for an aggregated view. This increased their storage costs.

- They faced throttling and API limits issues. These prevented the integration from completing successfully.

## The revised solution

The organization realized that it needed to rethink its standardized architecture principle and redefine its integration strategy. The team divided the organization's needs into two categories: batch and point-to-point synchronizations. They also adopted a "configure before you customize" approach.

They mapped their different integration needs to the appropriate patterns and designed a suitable integration architecture for each component.

For point-to-point integrations, they kept the microservices-based architecture. But they made some changes to align with Power Platform API limits.

For batch synchronizations, they designed the architecture to handle the ETL processes more efficiently. They did this by:

- Extracting the data from their source application using SQL Server Integration Services packages and storing the data in a staging database

- Hosting the staging environment in Azure SQL, in the datacenter as the Customer Service app

- Sending the data as batch data to Customer Service to reduce the number of individual connections

- Considering API and throttling limits and building retries into the design

For an aggregated view of the data, they changed their approach to use Azure Data Lake Storage, as Microsoft recommends. The out-of-the-box Export to Azure Data Lake feature made this easy. They didn't need any extra code.

## The results

The revised solution gave the organization significant benefits:

- Batch synchronization performance improved greatly. The duration of the daily sync dropped by more than 70 percent.
- The "configure before you customize" approach let the team choose out-of-the-box options. This reduced development and maintenance costs.
- The retry mechanism, combined with monitoring, ensured that any failure scenarios were well handled. This avoided negative impacts on users.

The organization had to reset its timeline because of the architecture realignment, but the benefits were worth it. The company could align its design with product features and best practices. It also had a change management plan in place, which helped them communicate and align with stakeholders and plan training for all affected teams.
