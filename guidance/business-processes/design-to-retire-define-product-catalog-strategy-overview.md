---
title: Overview of the Develop product strategy business process area
description: Learn how you can use Dynamics 365 products to support your organization's business processes for categorizing, segmenting, and merchandising products and services. Learn how you can capture a strategy for the products that you want to sell.
ms.date: 01/07/2025
ms.topic: concept-article
author: rachel-profitt
ms.author: raprofit
---

# Overview of the Develop product strategy business process area within the Design to retire end-to-end scenario

***Applies to: Dynamics 365 Commerce, Dynamics 365 Customer Insights, Dynamics 365 Customer Service, Dynamics 365 Customer Service Insights, Dynamics 365 Field Service, Dynamics 365 Marketing, Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center***

This article describes how to categorize, segment, and merchandise products and services by using Dynamics 365 applications.

All organizations group and categorize or segment their products into logical grouping for various reasons. Dynamics 365 includes several capabilities that you can consider implementing together at the beginning of a project. [!INCLUDE [daf-prod-serv-cat-merch-seg](../includes/daf-prod-serv-cat-merch-seg.md)]

[!INCLUDE [daf-prod-serv-considerations](../includes/daf-prod-serv-considerations.md)]

## Stakeholders

Many people across the organization should contribute to the decision-making process and design of the *Develop product strategy* business process area. The following list provides examples of such stakeholders:

[!INCLUDE [daf-prod-serv-stakeholders](../includes/daf-prod-serv-stakeholders.md)]

## Develop product strategy process flow

The following diagram illustrates the *Develop product strategy* business process area. [!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/design-to-retire-categorize-products.svg" alt-text="Flow diagram with steps for the process that is explained further in the next paragraphs." lightbox="media/design-to-retire-categorize-products.svg":::

1. Start

    A parallel process that isn't shown connects to an upstream business process area for *Introduce new products*. This box connects to 4.b.i. *Assign product attributes*.

1. *Design to retire* end-to-end process
1. *Develop product strategy* business process area
1. *Define product policies*

    1. *Define product types*

        1. *Define product lines*
        1. *Organize products*

            A parallel branch connects to *Introduce new products*, which has parallel branches to each of the following end-to-end scenarios:

            1. *Order to cash*
            1. *Plan to produce*
            1. *Source to pay*
            1. *Inventory to deliver*

            Each of these downstream end-to-end processes connects to *Record to report*, which connects to End.

        1. *Determine product mix for a retail channel*
        1. Is update required?

            1. Yes leads to *Maintain product catalog*.
            1. No leads to End.

    1. *Determine product attributes*

        1. *Assign product attributes*
        1. Is update required?

            1. Yes leads to *Maintain product attributes*.
            1. No leads to End.

## Develop product strategy benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the *Develop product strategy* business process area. The following sections outline the key benefits that an organization might monitor and measure for *Develop product strategy*.

[!INCLUDE [daf-prod-serv-benefits](../includes/daf-prod-serv-benefits.md)]

## Next steps

If you want to implement Dynamics 365 solutions to help with your *Develop product strategy* business processes, you can use the following resources and steps to learn more. (Links are added when the articles are ready.)

1. *Develop product strategy* (the article that you're currently reading)  

    1. *Define product policies*
    1. *Develop product portfolio*
    1. *Develop product roadmap*
    1. *Define product categories*
    1. *Define product attributes*
    1. *Develop product catalogs*
    1. *Develop merchandise and assortment plans*

1. [Introduce products](design-to-retire-introduce-new-products-overview.md)  
1. [Manage active products](design-to-retire-manage-product-lifecycle-overview.md)  
1. *Retire products*
1. *Analyze product performance*
<!-- 1. [Manage product lifecycle](design-to-retire-manage-product-lifecycle-overview.md)   -->

## Related information

You can use the following resources to learn more about the *Develop product strategy* business process area in Dynamics 365.

- [Manage product categories and products](/dynamics365/commerce/category-management-product-creation)
- [Set up product families](/dynamics365/sales/create-product-family)
- [Create segments and lists to establish target markets](/dynamics365/marketing/segmentation-lists-subscriptions)
- [Define subjects to categorize cases, products, and articles](/power-platform/admin/define-subjects-categorize-cases-products-articles)
- [Classify a product using category hierarchies](/dynamics365/supply-chain/pim/tasks/classify-product-category-hierarchies)
- [Create a new product hierarchy](/dynamics365/commerce/create-product-hierarchy)
- [Categorize items (Business Central)](/dynamics365/business-central/inventory-how-categorize-items)
- [Issue and settle vendor payments overview](source-to-pay-issue-and-settle-vendor-payments-overview.md)
- Find definitions of terminology that is used in content for *Develop product strategy* in the [Glossary of terms in Dynamics 365 business processes](glossary.md). For example, this glossary includes the following terms:

    - [Category hierarchy](glossary.md#category-hierarchy)
    - [Merchandising](glossary.md#merchandising)
    - [Product category](glossary.md#product-category)
    - [Product family](glossary.md#product-family)
    - [Product hierarchy](glossary.md#product-hierarchy)
    - [Segmentation](glossary.md#segmentation)
    - [Subject](glossary.md#subject)

<!-- ## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Customer services, Engineering, Finance, Marketing, Merchandising, Operations, Production, Purchasing, Retail store operations, Sales, Service operations, Warehouse

*Products:* Dynamics 365 Commerce, Dynamics 365 Customer Insights, Dynamics 365 Customer Service, Dynamics 365 Customer Service Insights, Dynamics 365 Field Service, Dynamics 365 Marketing, Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Rachel Profitt](https://linkedin.com/in/rachelprofitt) \| Microsoft FastTrack Solution Architect

Other Contributors:

- [Michael Herold](https://linkedin.com/in/maherold) \| Microsoft Dynamics Principal Consultant
