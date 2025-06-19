---

title: Build quality with optimized and standardized business processes
description: Learn how to design, build, and assess quality, optimized, and standardized business processes for your Dynamics 365 implementation.
ms.date: 01/07/2025
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

- Update the business process catalog.  

  The business process catalog serves as a baseline for deriving more detailed business processes. Learn more at [About the business process catalog for Dynamics 365 apps and services](../business-processes/about.md).

- Consider importing the catalog into a tool, such as Azure DevOps, to help you manage the catalog and project.

## Define your business requirements and goals clearly

- Your requirements should map to your processes, and your processes should map to your business goals.  

  When you use the business process catalog, we recommend that you map all requirements to the lowest level possible. In other words, map your processes to a business process at level 3, work item type **Feature**, or a pattern at level 4, work item type **User story**.

- Map the current processes (as-is) with the desired processes (to-be), if applicable.  

  Understand how your process works today and how you want it to work in the future to meet your business goals. If you're starting from scratch, focus on designing the desired process only.

- Choose the appropriate level and type of business process.  

  Depending on the purpose, the hierarchy level, and the message of your process, you can use different forms of flows to illustrate it, such as the following list:

  - Basic process flow
  - Cross-functional flow
  - Data flow
  - Decision flow
  - Workflow process
  - Business value process flow
  - Value stream map

- Build the end-to-end processes.  

  The end-to-end process shows the overall purpose of the business by connecting the core processes across different areas. Identify the business areas of your organization, and then create the end-to-end business process for each. For example:

  - HR: *Hire to retire*
  - Sales: *Order to cash*
  - Procurement: *Source to pay*
  - Customer: *Prospect to quote*
  - Marketing: *Concept to market*

## Define roles and responsibilities  

- Assign the right access and security to the users who carry out the tasks and activities.  

  This also helps you estimate the number of users and licenses you need for your project budget.

- Determine what fits the standard and what the system gaps are.  

  Sometimes, the current processes might not be fully covered by the new system, which can be an opportunity to find better or more optimal ways to execute them. You might need to develop more features to meet your business needs.

## Reassess your business processes  

- Plan to monitor and reassess your business processes during multiple iterations to verify that the information is still accurate, and make relevant adjustments. For example, reassess processes during each Conference Room Pilot (CRP).

[Learn more about end-to-end business processes in Dynamics 365](../business-processes/overview.md).

## Next steps

- Learn how to do a [fit-to-standard and a fit-gap analysis](process-focused-solution-fit-to-standard-fit-gap-analysis.md)
- [Define your requirements](process-focused-solution-define-requirements.md)
- Follow the [checklist](process-focused-solution-checklist.md) to prepare for your implementation
- Read a [case study](process-focused-solution-case-study-journey.md) about a company that implemented Dynamics 365 using a process-focused approach
