---
title: Prospect to quote end-to-end business process flow overview
description: Learn about the prospect to quote end-to-end business process with a flow diagram and learn about the relationship with other processes in Dynamics 365 solutions.
ms.date: 10/24/2023
ms.topic: conceptual
author: edupont04
ms.author: kowildfe
ms.reviewer: edupont
---

# Overview of the prospect to quote business process flow and its relationship to other processes

***Applies to: Dynamics 365, Dynamics 365 Customer Insights, Dynamics 365 Customer Service, Dynamics 365 Marketing, Dynamics 365 Sales***

This article describes the *prospect to quote* end-to-end business process flow and its relationship to other business processes that can be used within Dynamics 365.

## Prospect to quote process relationship

The following diagram shows the relationship of other processes and products/features for the *prospect to quote* process.

:::image type="content" source="media/prospect-to-quote-process.svg" alt-text="Business process relationships with upstream and downstream processes that are explained in the next paragraphs." lightbox="media/prospect-to-quote-process.svg":::

The prerequisites include the following end-to-end business processes:

- **Concept to market**

    *Concept to market* can feed directly into the definition of a sales strategy, because the nature of a service guides how it's sold. This process informs the sales strategy and marketing campaigns, because it helps define the services that are promoted.

- **Design to retire**

    *Design to retire* can feed directly into the definition of a sales strategy, because the nature of a product guides how it's sold. This process informs the sales strategy and marketing campaigns, because it helps define the products that are promoted.

- **Forecast to plan**

    Market forecasts can guide the sales strategy, marketing campaigns, and lead identification.

- **Project to profit**

    Insights from previous projects can inform the sales strategy, lead qualification, and the pursuit of opportunities.

- **Hire to retire**

    *Hire to retire* business processes can influence *prospect to quote* if human resources and financial reporting are foundational to your sales process.

- **Record to report**

    *Record to report* business processes can influence *prospect to quote* if financial reporting is foundational to your sales process.

The *prospect to quote* end-to-end process is broken down into the following business process areas:

- Define sales strategy

- Run marketing campaigns

- Identify and qualify leads

- Pursue opportunities

- Estimate and quote sales

- Manage customer relationships
<!-- Removed
- Analyze service operations -->

Learn more at [Prospect to quote business process areas](prospect-to-quote-areas.md).

The third column in the diagram displays the downstream business process including the following processes:

- **Order to cash**

    After a quote is accepted, the *order to cash* process starts. It includes order management, fulfillment, invoicing, and payment collection.

- **Service to cash**

    This process is applicable to service-based organizations. After sales are estimated and quoted, service delivery and invoicing occur, followed by payment collection.

- **Inventory to deliver**

    This process is related to product availability and delivery, which can affect the accuracy of quotes and customer relationship management (CRM).

There are more capabilities in Dynamics 365 that depend on the *prospect to quote* business process. The following list includes key examples:

- Lead management

    Dynamics 365 Sales provides tools to capture, manage, and qualify leads. The platform enables you to track lead sources, score leads, and convert them into opportunities when they meet the qualification criteria.

- Opportunity management

    Opportunities in Dynamics 365 Sales represent potential sales deals. The platform allows you to track and manage opportunities, including key information about prospects, estimated revenue, probability, and sales stages.

- Product catalog

    The product catalog in Dynamics 365 Sales enables you to manage and maintain a list of products, services, bundles, and pricing structures. This feature is essential when creating quotes or proposals for prospects.

- Quote management

    Dynamics 365 Sales offers quote creation and management functionality. You can generate quotes based on products and services from your catalog, apply discounts, and track the status of quotes throughout the sales process.

- Sales territories and quotas

    The platform allows you to define and manage sales territories, assign salespeople, and set sales quotas. This feature helps in defining the sales strategy and aligning sales efforts with target markets.

- Activities and communications

    With Dynamics 365 Sales, you can track and manage interactions with prospects and customers, such as calls, meetings, and emails. This feature supports customer relationship management throughout the *prospect to quote* process.

- Dashboards and reports

    Dynamics 365 Sales offers customizable dashboards and reports that give you insights into your sales performance. These analytics tools help you monitor and analyze your prospect-to-quote process, identify trends, and make data-driven decisions.

These features are dependent on or closely related to the *prospect to quote* business process in Dynamics 365 Sales. They work together to streamline sales activities and improve the overall sales experience.

## Prospect to quote business process flow

The following diagram shows the high-level flow of the *prospect to quote* business process. [!INCLUDE [daf-business-process-e2e-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-e2e-flow-def.md)]

:::image type="content" source="media/prospect-to-quote-flow.svg" alt-text="Flow diagram for the end-to-end business process, which is explained in the paragraphs after the image." lightbox="media/prospect-to-quote-flow.svg":::

The following steps are illustrated in the *prospect to quote* end-to-end business process flow diagram.

1. Start
1. *Prospect to quote* end-to-end process

    1. Define sales strategy
    1. Run marketing campaigns
    1. Identify and qualify leads
    1. Pursue opportunities
    1. Estimate and quote sales

        A parallel branch from this business process area is *Inventory to deliver*.

    1. Manage customer relationships

        Parallel branches from this business process area are *Order to cash* and *Service to cash*.

1. End

Parallel branches from Start include the following:

1. *Record to report*, *Design to retire*, and *Record to report* connect to *Define sales strategy*.
1. *Forecast to plan* connects to *Run marketing campaigns*.
1. *Project to profit* connects to *Identify and qualify leads*.
1. *Record to report* and *Hire to retire* connect to *Manage customer relationships*.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *prospect to quote* business processes, use the following resources and steps to learn more.

1. Define the goals and objectives of implementing a prospect to quote technology solution. Learn more at [Solution architecture design: Vision and strategies](../implementation-guide/solution-architecture-design-pillars-vision-strategies.md)

2. Define the business process scope of your project. Learn more at [Process-focused solution](../implementation-guide/process-focused-solution.md)

<!-- Get a demo of Dynamics 365 solutions for the order to cash process.TODO: add link For more information, see \[link\].-->

3. [Sign up for a trial of Dynamics 365](https://dynamics.microsoft.com/dynamics-365-free-trial/)

4. [Prospect to quote business process areas](prospect-to-quote-areas.md)

## Related resources

Use the following resources to learn more about the *prospect to quote* process in Dynamics 365.

- [Dynamics 365 Sales User Guide](/dynamics365/sales-enterprise/user-guide)

- [Dynamics 365 Sales Community](https://community.dynamics.com/forums/thread/?partialUrl=sales/)

- Dynamics 365 Sales YouTube playlist

- Find definitions of terminology used in content for *prospect to quote* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article, including the following terms:

    - [Key entities](glossary.md#key-entities)
    - [Sales process and stages](glossary.md#sales-process-and-stages)
    - [Lead and opportunity management](glossary.md#lead-and-opportunity-management)
    - [Sales planning and strategy](glossary.md#sales-planning-and-strategy)
    - [Sales tools and technologies](glossary.md#sales-tools-and-technologies)
    - [Sales documentation and materials](glossary.md#sales-documentation-and-materials)

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Kody Wildfeuer](https://www.linkedin.com/in/kody-wildfeuer/) | Senior Solution Architect, FastTrack for Dynamics 365

<!--## Tags
*Industries:* Healthcare, Financial services, Retail, Manufacturing, Software, Technology, Agriculture

*Stakeholders:* Sales and marketing teams, product managers, customer service representatives, and senior management

*Products:* Dynamics 365, Dynamics 365 Customer Insights, Dynamics 365 Customer Service, Dynamics 365 Marketing, Dynamics 365 Sales
