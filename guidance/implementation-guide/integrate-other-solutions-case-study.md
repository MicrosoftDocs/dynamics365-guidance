---
title: Integration strategy case study
description: Learn about a case study that walks you through a real-life example of how a Dynamics 365 customer approached the integration strategy.
author: abunduc-ms
ms.author: abunduc
ms.date: 05/23/2023
ms.topic: conceptual

---
# Integration strategy case study

Let's go through an example of how a public sector infrastructure organization learns how to choose the right solution for integration

## Story

A public sector infrastructure service organization implements Dynamics 365 Customer Service. They require integration with a public-facing website, several on-premises apps, and Microsoft 365, including SharePoint Online. One of the implementation objectives is to gather insights from the data that is scattered across different business applications.

## Case study

The organization works with an IT vendor that has several years of experience building complex integrations using technologies such as IBM MQ and Microsoft BizTalk.

They decide to keep a uniform integration architecture and proceeded with a microservices-based architecture to build small, reusable components using service endpoints to gain the following benefits:

- Faster and independent development, deployment, and release cycles

- Simplicity of architecture to allow decoupled and reusable components

- Fault isolation

The organization chooses Azure API Management to abstract their APIs and implement a secure integration layer.

As the team started building and testing the initial components, they identified some challenges due to the architecture:

- They experienced slow performance with batch-integration scenarios because they called the services as they would have in a point-to-point integration.

- They couldn't use standard functionalities that would have been available with out-of-the-box approaches such as SharePoint Online integration with Power Platform.

- For an aggregated view, they decide to replicate all data to Dynamics 365 Customer Service, which leads to more storage costs.

- They encountered throttling and API limits issues, which prevented successful completion of the integration.

At this stage, the organization decides to reevaluate their standardized architecture principle and redefine their integration strategy. They divide their needs into two categories: batch and point-to-point synchronizations. They also adopted a "Configure-before-you-customize" approach.

With a reasonable mapping of different integration needs to the patterns, they can redefine a suitable integration architecture for these components.

For point-to-point integrations, the organization uses the previously defined microservices-based architecture and incorporated the necessary changes for aligning with Power Platform API limits.

For batch synchronizations, the organization designs the architecture to manage the overall ETL processes with the following approach:

- They extract the data from their source application by creating SQL Server Integration Services packages and storing that data in a staging database to perform all transformations.

- They host their staging environment in Azure SQL, within the same datacenter as the Customer Service app.

- They send that data as batch data to the Customer Service app to reduce the number of individual connections.

- They consider API and throttling limits and build retries as part of the design.

For an aggregated view of the data, they realign their approach to use Azure Data Lake, as Microsoft recommends. The out-of-the-box Export to Azure Data Lake feature requires simple configurations to export data from the Customer Service app into Data Lake. No extra code is needed.

These changes in their overall approach provide significant benefits:

- Their batch synchronization performance improves significantly, and they cut the duration of the daily sync by more than 70 percent.

- Their "Configure-before-you-customize" approach lets them choose out-of-the-box options to reduce development and maintenance costs.

- The retry mechanism, combined with monitoring, ensures that any failure scenarios were well handled and negative impacts on end users were avoided.

Even though the architecture realignment resets the organization's timeline, the benefits outweigh the risk, because they can align their design with product features and the recommended practices. The organization already had a change-management plan in place to take care of stakeholder communication and alignment, and to plan training for all affected teams in a timely manner.

## Next steps

Return to the overview at [Integrate with other solutions](integrate-other-solutions.md)  
