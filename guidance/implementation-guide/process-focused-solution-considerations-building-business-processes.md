---
title: Build quality with optimized and standardized business processes
description: Learn how to design, build, and assess quality, optimized, and standardized business processes for your Dynamics 365 implementation.
ms.date: 01/27/2026
ms.update-cycle: 1095-days
ms.topic: concept-article
author: edupont04
ms.author: raprofit
ms.reviewer: edupont
ms.custom:
  - evergreen
  - ai-seo-date: 01/16/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
ai-usage: ai-assisted
---

# Build quality with optimized and standardized business processes

To create a process-focused solution for your Dynamics 365 implementation, follow these recommendations. They help you improve the quality, optimization, and standardization of your business processes.

## Use the business process catalog

- Start from Microsoft's business process catalog.  

  [!INCLUDE [daf-catalog-get](../includes/daf-catalog-get.md)]  

- Apply the business process catalog to the concrete implementation project.  

  Use the business process catalog as a baseline so you can derive more specific business processes. Learn more at [About the business process catalog](../business-processes/about.md).

- Import the catalog into a tool, such as Azure DevOps, to help you manage the catalog and project.  

  Learn more at [Use the business process catalog as a template in Azure DevOps Services](../business-processes/about-import-catalog-devops.md).  

## Define your business requirements and goals clearly

- Map your requirements to your processes, and map your processes to your business goals.  

  When you use the business process catalog, map all requirements to the lowest level possible. In other words, map your processes to a business process at level 3 or a pattern at level 4. Find inspiration at [Standardize business processes](../business-processes/standardize-business-processes.md) and at [Deliverables in the business process catalog as Azure DevOps work items](../business-processes/about-devops-work-items-deliverables.md).

- Map the current processes (as-is) with the desired processes (to-be), if applicable.  

  Understand how the organization carries out business processes today and how they want to work in the future in support of the business goals. If you start from scratch, focus on designing the desired process only.

- Choose the appropriate level and type of business process.  

  Depending on the purpose, the hierarchy level, and the message of your process, use different forms of flows to illustrate it. The following list shows some options:

  - Basic process flow
  - Cross-functional flow
  - Data flow
  - Decision flow
  - Workflow process
  - Business value process flow
  - Value stream map

- Build the end-to-end processes.  

  The end-to-end process shows the overall purpose of the business by connecting the core processes across different areas. Identify the business areas of your organization, and then create the end-to-end business process for each. The following table shows some examples of this type of mapping.

  | Business area | End-to-end process |
  | --------- | --------- |
  | HR | [Hire to retire](../business-processes/hire-to-retire-overview.md) |
  | Sales | [Order to cash](../business-processes/order-to-cash-overview.md) |
  | Procurement | [Source to pay](../business-processes/source-to-pay-overview.md) |
  | Customer | [Prospect to quote](../business-processes/prospect-to-quote-overview.md) |
  | Marketing | [Concept to market](../business-processes/concept-to-market-overview.md) |

## Define roles and responsibilities  

- Assign the right access and security to the users who carry out the tasks and activities.  

  This step also helps you estimate the number of users and licenses you need for your project budget.

- Determine what fits the standard and what the system gaps are.  

  Sometimes, the current processes aren't fully covered by the new system. This gap can be an opportunity to find better or more optimal ways to execute these processes. You might need to develop more features to meet your business needs.

## Reassess your business processes  

Plan to monitor and reassess your business processes during multiple iterations to verify that the information is still accurate, and make relevant adjustments. For example, reassess processes during each Conference Room Pilot (CRP).

[Learn more about end-to-end business processes in Dynamics 365](../business-processes/overview.md) and [use the catalog to drive workshops](../business-processes/about-workshops.md).

## Next steps

- Learn how to do a [fit-to-standard and a fit-gap analysis](process-focused-solution-fit-to-standard-fit-gap-analysis.md)
- [Define your requirements](process-focused-solution-define-requirements.md)
- Follow the [checklist](process-focused-solution-checklist.md) to prepare for your implementation
- Read a [case study](process-focused-solution-case-study-journey.md) about a company that implemented Dynamics 365 using a process-focused approach
