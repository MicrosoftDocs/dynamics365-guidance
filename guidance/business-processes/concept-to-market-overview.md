---
title: Concept to market end-to-end business process flow overview
description: Learn about the end-to-end business process, concept to market. This article provides a high-level flow diagram and describes the relationship with other processes in Dynamics 365 solutions.
ms.date: 11/23/2023
ms.topic: conceptual
author: rachel-profitt
ms.author: raprofit
---

# Concept to market end-to-end business process flow and its relationship to other business processes

***Applies to: Dynamics 365 Commerce, Dynamics 365 Customer Insights, Dynamics 365 Customer Service, Dynamics 365 Customer Service Insights, Dynamics 365 Field Service, Dynamics 365 Marketing, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center***

This article describes the *concept to market* end-to-end business process flow and its relationship to other business processes that can be used in Dynamics 365. This end-to-end process focuses on the service offering lifecycle. Learn more about the product design lifecycle at [Design to retire end-to-end overview](design-to-retire-overview.md).

## Concept to market process relationship 

The following diagram shows the relationship of other processes and products/features for the *concept to market* process.

:::image type="content" source="media/concept-to-market-process.svg" alt-text="Business process relationships with upstream and downstream processes that are explained in the next paragraphs." lightbox="media/concept-to-market-process.svg":::

The upstream processes for the *concept to market* process include the following.

- **Forecast to plan**: Organizations often complete the service offering definition in the *concept to market* process before they begin the forecasting process.
- **Prospect to quote**: In some operational strategies, such as engineer to order, the *prospect to quote* process occurs before the *concept to market* process, because the quote is often the trigger that initiates the process.
- **Order to cash**: In some operational strategies, such as engineer to order, the *order to cash* process occurs before the *concept to market* process, because the quote is often the trigger that initiates the process.
- **Service to cash**: In some service-based organizations, the *service to cash* process starts before the *concept to market* process. For example, a service technician who is repairing or inspecting a customer asset must order new parts that aren't currently part of the product catalog.
- **Project to profit**: In some operational strategies, such as engineer to order, the *project to profit* process might start before the *concept to market* process. For example, before the organization begins to set up and procure the items to make the engineered product, it creates the project, sets the budgets, and completes and approves drawings. Additionally, when organizations use projects to manage capital projects, the project definition, budgets, and so on, are typically set before the organization begins to create and procure the necessary products and services.

The *concept to market* end-to-end process is broken down into the following business process areas.

- Define service offerings and strategy
- Introduce new services
- Manage services pricing
- Define service costing
- Manage service lifecycle

The downstream processes for the *concept to market* end-to-end process include the following.

- **Procure to pay**: Typically, services are purchased after an agreement is made with a vendor and the product is defined in the system. In organizations that manufacture products, the services that will be outsourced are often defined by the engineering process that is part of the *design to retire* process. In some cases, the request for quotation process occurs before a service definition is created. In these cases, the *procure to pay* process is upstream instead of downstream.
- **Prospect to quote**: In operational strategies such as make to stock, the *prospect to quote* process occurs after a service offering mix is determined in the *concept to market* process.
- **Order to cash**: In operational strategies such as make to stock, or in brick-and-mortar commerce scenarios, the *order to cash* process occurs after a service offering mix is determined in the *concept to market* process.
- **Service to cash**: In most operational strategies, the *service to cash* process occurs after the *concept to market* process, because the services that will be offered are predetermined by the organization's sales strategy.
- **Plan to produce**: Except in operational strategies for make to order and engineer to order, the production process typically occurs after the *concept to market* process is completed. Nevertheless, because there are often updates throughout the production process, the process can be both upstream and downstream. The *plan to produce* process is used with services when you outsource some or all of the production process.
- **Case to resolution**: The *case to resolution* process is downstream to the *concept to market* process when you use cases to manage vendor issues, customer complaints, and so on.
- **Record to report**: The *record to report* process is downstream to the *concept to market* process, because items and orders must exist before costs or revenues can be recognized in the general ledger, for example.

## Featured capabilities

Product-specific capabilities are offered that interact with the product and service lifecycle management process. The capabilities include, but aren't limited to, the following list.

- **Product catalogs**: Dynamics 365 Commerce includes catalog features to help manage products in retail channels. Additionally, Dynamics 365 Supply Chain Management includes both internal and external catalogs to help with the procurement process. External catalogs are sometimes referred to as punchout catalogs. They help maintain product information from a third party.
- **Product attributes**: Product attributes are used to enrich product or service information in Dynamics 365 Commerce and Supply Chain Management.
- **Product categories**: Product categories are used to help create channel navigation in Dynamics 365 Commerce (for example, for site navigation). You can also use product categories in Dynamics 365 Supply Chain Management to help manage and analyze your spend and revenue across the application.
- **Product translations**: If you sell or buy products or services in different countries or regions, you can translate your service descriptions. You can also define vendor-specific or customer-specific item numbers. In this way, you help make communication with your customers and vendors easier.
- **Product templates**: You can use product templates to quickly and easily create new products that have similar information.

## Concept to market business process flow

The following diagram shows the high-level flow of the *concept to market* business process. [!INCLUDE [daf-business-process-e2e-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-e2e-flow-def.md)]

:::image type="content" source="media/concept-to-market-flow.svg" alt-text="Flow diagram for the end-to-end business process, which is explained in the paragraphs after the image." lightbox="media/concept-to-market-flow.svg":::

The following steps are illustrated in the *concept to market* end-to-end business process flow diagram.

1. Start
1. *Concept to market* end-to-end process
1. *Define service offerings and strategy*
1. *Introduce new services*

    1. *Manage service pricing*
    1. *Define service costing*

1. *Manage service lifecycle*

    1. [Procure to pay](procure-to-pay-overview.md)
    1. [Prospect to quote](prospect-to-quote-overview.md)
    1. [Order to cash](order-to-cash-overview.md)
    1. [Plan to produce](plan-to-produce-overview.md)
    1. [Project to profit](project-to-profit-overview.md)
    1. [Case to resolution](case-to-resolution-overview.md)
    1. [Record to report](record-to-report-overview.md)

1. End

Parallel branches from Start connect to the following end-to-end processes, all of which connect to 4. *Introduce new services*.

1. *Forecast to plan*
1. *Prospect to quote*
1. *Order to cash*
1. *Service to cash*
1. *Project to profit*

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *concept to market* business processes, you can use the following resources and steps to learn more.

1. Define the goals and objectives for a technology solution that supports the organization's need for a service lifecycle management process. Learn more at [Implementation strategy](../implementation-guide/implementation-strategy.md).

2. Define the business process scope of your project. Learn more at [Process-focused solution](../implementation-guide/process-focused-solution.md).

3. Request a demo or get a free trial of Dynamics 365 solutions for the product and service lifecycle management process. Learn more at [Request a demo](https://dynamics.microsoft.com/dynamics-365-free-trial/).

4. Get an overview of the product and service lifecycle management process. Learn more at [Concept to market business process areas](concept-to-market-areas.md).

## Related resources

You can use the following resources to learn more about the product and service lifecycle management process in Dynamics 365.

- [How to Create Service Items - Business Central](/dynamics365/business-central/service-how-to-create-service-items)
- [Service management overview - Supply Chain Management](/dynamics365/supply-chain/service-management/service-management-home-page)
- [Create products or services for work orders - Dynamics 365 Field Service](/dynamics365/field-service/create-product-or-service)
- [Manage and organize your product catalog with Dynamics 365 Sales](/training/modules/manage-organize-product-catalog-dynamics-365-sales/)
- [Set up a product catalog Walkthrough - Dynamics 365 Sales](/dynamics365/sales/set-up-product-catalog-walkthrough)

<!-- ## Tags

*Stakeholders:* Functional consultant, Business analyst, Product development lead, Merchandising lead, Sales lead, Purchasing lead, Production lead, Supply chain lead, Quality control lead

*Products: Dynamics 365 Commerce, Dynamics 365 Customer Insights, Dynamics 365 Customer Service, Dynamics 365 Customer Service Insights, Dynamics 365 Field Service, Dynamics 365 Marketing, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center* -->
