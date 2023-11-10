---
title:  Manage project opportunities overview
description: Learn how you can use Dynamics 365 products to support the organization's business processes to manage opportunities.
ms.date: 07/27/2023
ms.topic: conceptual
author: edupont04
ms.author: lalithac
---

# Manage project opportunities overview

***Applies to: Dynamics 365 Sales, Dynamics 365 Project Operations, Dynamics 365 Finance, Dynamics 365 Supply Chain Management***

This article describes how you can use Dynamics 365 products to support your organization's business processes to manage project opportunities.

The *Manage project opportunities* business process area covers activities that are related to the following areas:

- Identifying potential customers and leads  
- Qualifying those leads to determine if they're a good fit for the organization  
- Converting qualifying leads to opportunities  

The purpose of this process is to help organizations track and manage potential projects, and determine which projects are worth pursuing. This business process enables organizations to identify, cultivate and win new business opportunities and thus help ensure a continuous and visible pipeline of work.

To identify potential projects and opportunities, organizations may conduct market research, analyze customer needs, and perform competitive analysis. Once potential projects are identified, they're evaluated based on factors such as profitability, resource availability, risk, and strategic fit. This evaluation process helps organizations prioritize the most promising opportunities.

The business process area is important because it provides a structured approach to identifying and pursuing potential projects. This way, organizations can optimize their resources and increase their chances of winning new business. When they track and manage opportunities, organizations can make informed decisions about where to focus their efforts and resources. Then, they can make sure that they're pursuing the most promising projects.

The *Manage project opportunities* business process area should be defined early on in the overall implementation process. The process of identifying and evaluating potential projects logically comes before you can plan and run such projects.

## Stakeholders

Many people in an organization must contribute to the decision-making process in managing project opportunities. The list includes but isn't limited to the following roles:

- **Sales and marketing stakeholders** – Examples: Sales manager, Marketing manager

- **Project Management stakeholders** – Examples: Project manager, Resource manager

- **Finance stakeholders** – Examples: Controller, Finance manager, Procurement manager

- **Executive stakeholders** – Examples: COO

## Manage project opportunities process flow 

The following diagram illustrates the *manage project opportunities* business process area.

:::image type="content" source="media/project-to-profit-manage-project-opportunities-flow.svg" alt-text="Flow diagram for the business process area, which is explained in the paragraphs after the image." lightbox="media/project-to-profit-manage-project-opportunities-flow.svg":::

[!INCLUDE [daf-business-process-flow-def](../includes/daf-business-process-flow-def.md)]

The following steps are illustrated in the *manage project opportunities* business process flow diagram.

1. Start

2. *Case to resolution* end-to-end business process

3. *Prospect to quote* end-to-end business process

    1. *Identify and qualify leads*

    2. *Qualify leads*

4. *Project to profit* end-to-end business process  

5. *Manage project opportunities*

    1. *Create project opportunity*  

    2. *Develop the opportunity* by adding additional information, such as stakeholders  

    3. *Develop the proposal* and submit it for review  

    4. *Is proposal accepted*?

        1. Branch for **Yes** leads to *Opportunity won, close the deal*

        2. Branch for **No** leads to *Is there still a chance to win the opportunity?*

            1. Branch for **Yes** leads to *Develop the proposal and submit it for review*

            2. Branch for **No** leads to *Opportunity lost*

            3. *End*

    5. *Opportunity won, close the deal* connects to downstream business process *Create project contract* under the *Manage project contracts* subprocess<!-- TODO: Add link when this L2 is ready-->  

## Manage project opportunities benefits

There are many benefits that accrue from implementing technology to support the *Manage project opportunities* process area. The following sections outline key benefits that an organization might monitor and measure to track the impact of their *Manage project opportunities* process. 

### Streamlined project opportunity tracking

A key benefit of using Dynamics 365 Project Operations is tracking project opportunities from start to finish, including capturing initial leads, managing proposals and bids, and closing deals. This streamlined process helps to increase efficiency, reduce errors, ensure timely follow-up, and thus improve project sales.

### Enhanced forecasting and analytics

Dynamics 365 Project Operations has forecasting and analytics capabilities to analyze past project data and identify patterns and trends. The capabilities can help in identifying potential project opportunities that align with your organization's strengths and capabilities. With this information, users can make informed decisions about which opportunities to pursue and, as importantly, which ones not to. Additionally, the real-time data and insights provided by Dynamics 365 Project Operations enable organizations to adjust their project portfolio as needed.

### Automated opportunity management

In Dynamics 365 Project Operations, users can set up workflows to manage project opportunities efficiently. These workflows can automate repetitive tasks such as sending follow-up emails or updating opportunity status. Such automation saves time and ensures that no important opportunity-related tasks are overlooked or forgotten, which might otherwise result in the loss of the opportunity.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *manage project opportunities* business processes, use the following resources and steps to learn more. Links are added when articles become available.  

1. Run marketing campaigns  
2. Manage customer relationships  
3. [Define sales strategy](prospect-to-quote-define-sales-strategy-overview.md)  
4. Identify and qualify leads  
5. *Manage project opportunities*  (the article you're currently reading)     
6. Pursue opportunities  
7. Estimate and quote sales  

Return to the overview of business process areas at [Prospect to quote business process areas](prospect-to-quote-areas.md).     

## Related resources

You can use the following resources to learn more about the *Manage project opportunities* process in Dynamics 365.

- Find definitions of terminology used in content for *Manage project opportunities* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article, including the following terms:

  - [Lead](glossary.md#lead)  
  - [Lead and opportunity management](glossary.md#lead-and-opportunity-management)  
  - [Opportunity](glossary.md#opportunity)  
  - [Proposal](glossary.md#proposal)  
  - [Close the deal](glossary.md#close-the-deal)  
  - [Project contract](glossary.md#project-contract)  
- [Project to profit end-to-end overview](project-to-profit-overview.md)  
- [Govern projects](project-to-profit-govern-projects-overview.md)  
- [Dynamics 365 Project Operations - Sales and Inception (blog post)](https://community.dynamics.com/blogs/post/?postid=3fcc054a-377e-42b4-aed5-22e0c7026a67)    
- [Manage project opportunities (Project Operations)](/dynamics365/project-operations/sales/manage-project-based-opportunities)  
- [Project sales management (training)](/training/modules/get-started-project-operations/5-sales-management)  
- [Microsoft Certified: Dynamics 365 Fundamentals (ERP)](/certifications/d365-fundamentals-finance-and-operations-apps-erp/)  
- [Implementation strategy](../implementation-guide/implementation-strategy.md)  
- [Process-focused solution](../implementation-guide/process-focused-solution.md)   
- [Request a demo](https://dynamics.microsoft.com/dynamics-365-free-trial/)  
<!--## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Executive sponsor, Project manager, Sales and Marketing teams, Finance department, Business process owners

*Products:* Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Finance, Dynamics 365 Supply Chain Management-->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- Lalitha Chintamaneni, FastTrack Solution Architect

Other contributors:

- Martin Walker, Principal FastTrack Solution Architect
