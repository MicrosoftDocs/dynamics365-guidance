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

This article describes the concept to market end-to-end business process flow and its relationship to other business processes that can be used within Dynamics 365. This end-to-end process focuses on service offering lifecycle. Learn more about the product design lifecycle at [Design to retire end-to-end overview](design-to-retire-overview.md).

## Concept to market process relationship 

The following diagram shows the relationship of other processes and products/features for the *concept to market* process.

:::image type="content" source="media/concept-to-market-process.svg" alt-text="Business process relationships with upstream and downstream processes that are explained in the next paragraphs." lightbox="media/concept-to-market-process.svg":::

The upstream processes for the *concept to market* process include the following.

- **Forecast to plan**: Often, organizations will complete the service offering definition in the *concept to market* process prior to beginning the forecasting process.


- **Prospect to quote**: In some operational strategies such as engineer to order, the *prospect to quote* process will occur prior to*concept to market*, since the quote is often the trigger to initiate the process.

- **Order to cash**: In some operational strategies such as engineer to order, the *order to cash* process runs before *concept to market*, since the quote is often the trigger to initiate the process.


- **Service to cash**: In some service-based organizations, the service to cash process will start before the *concept to market* process. For example, if a service technician is conducting a repair or inspection on a customer asset and needs to order new parts that are not currently part of the product catalog.

- **Project to profit**: In some operational strategies such as engineer to order, the project to profit process may begin before the *concept to market* process begins. For example, the project is created, budgets are set, drawings are completed and approved, before the organization begins to set up and procure the items to make the engineered product. Additionally, when organizations use projects to manage capital projects, the project definition, budgets and so on, are typically set before the organization begins to create and procure the needed products and services.

The *concept to market* end-to-end process is broken down into the following business process areas:

- Define service offerings and strategy

- Introduce new services

- Manage services pricing

- Define service costing

- Manage service lifecycle

The downstream processes for the *concept to market* end-to-end process include the following.

- **Procure to pay**: Typically, services are purchased after an agreement is made with a vendor and the product is defined in the system. In organizations that manufacture products, the services to be outsourced are often defined by the engineering process which is part of the design to retire process. In some cases, the request for quotation process may happen before a service definition is created which would make the *procure to pay process* be upstream.

- **Prospect to quote**: In operational strategies such as make to stock, the *prospect to quote process* happens after a service offering mix has been determined in the *concept to market* process.

- **Order to cash**: In operational strategies such as make to stock, or brick and mortar commerce scenarios, the *order to cash process* happens after a service offering mix has been determined in the*concept to market* process.

- **Service to cash**: In most operational strategies, the *service to cash* process will occur after to*concept to market process*, since the services to be offered are predetermined by the organization's sales strategy.

- **Plan to produce**: With the exception of operational strategies for make to order and engineer to order, the production process typically comes after the *concept to market* process has been completed. Although, there are often updates throughout the production process, which can cause the process to be both upstream and downstream. The plan to produce process is used with services when you outsource some or all of the production process.

- **Case to resolution**: The *case to resolution process* is downstream to the*concept to market process* when you use cases to manage vendor issues, customer complaints, and so on.

- **Record to report**: The *record to report process* is downstream to the*concept to market process* because items and orders must exist to recognize costs or revenues, for example, in the general ledger.

## Featured capabilities

There are product specific capabilities offered that interact with the product and service lifecycle management process including, but not limited to, the following:

- **Product catalogs**: Dynamics 365 Commerce and includes catalog features to help with the management of products in retail channels. Additionally, Dynamics 365 Supply Chain Management includes catalogs to help with the procurement process including both internal and external, sometimes referred to as punchout catalogs, to help maintain product information from a third-party.

- **Product attributes**: Product attributes are used to enrich product or service information in Dynamics 365 Commerce and Supply Chain Management.

- **Product categories**: Product categories are used to help create channel navigation in Dynamics 365 Commerce for site navigation as an example. You can also use product categories in Dynamics 365 Supply Chain Management to help manage and analyze your spend and revenue across the application.

- **Product translations**: When you sell or buy products or services in different countries, you can translate your service descriptions and define vendor or customer specific item numbers to make the communication process with your customers and vendors easier.

- **Product templates**: Product templates allow you to create new products quickly and easily with similar information.

## Concept to market business process flow

The following diagram shows the high-level flow of the *concept to market* business process. [!INCLUDE [daf-business-process-e2e-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-e2e-flow-def.md)]

:::image type="content" source="media/concept-to-market-flow.svg" alt-text="Flow diagram for the end-to-end business process, which is explained in the paragraphs after the image." lightbox="media/concept-to-market-flow.svg":::

The following steps are illustrated in the *concept to market* end-to-end business process flow diagram.

1. Start

2. *Concept to market* end-to-end process

3. *Define service offerings and strategy*

4. *Introduce new services*

    1. *Manage service pricing*

    2. *Define service costing*

5. *Manage service lifecycle*

    1. [Procure to pay](procure-to-pay-overview.md)  

    2. [Prospect to quote](prospect-to-quote-overview.md)  

    3. [Order to cash](order-to-cash-overview.md)  

    4. [Plan to produce](plan-to-produce-overview.md)  

    5. [Project to profit](project-to-profit-overview.md)  

    6. [Case to resolution](case-to-resolution-overview.md)  

    7. [Record to report](record-to-report-overview.md)  

6. End

Parallel branches from start connect to the following end-to-end processes that are that all connect to 4. *Introduce new services*.

1. *Forecast to plan*

2. *Prospect to quote*

3. *Order to cash*

4. *Service to cash*

5. *Project to profit*

## Next steps

If you would like to implement Dynamics 365 solutions to assist with your concept to market business processes, you can use the following resources and steps to learn more.

- Define the goals and objectives of implementing a product and service lifecycle management technology solution. Learn more at [Implementation strategy](../implementation-guide/implementation-strategy.md).
- Define the business process scope of your project. Learn more at [Process-focused solution](../implementation-guide/process-focused-solution.md).
- Request a demo or get a free trial of Dynamics 365 solutions for the product and service lifecycle management process. Learn more at [Request a demo](https://dynamics.microsoft.com/dynamics-365-free-trial/).
- Get an overview of the product and service lifecycle management process. Learn more at [Concept to market business process areas](concept-to-market-areas.md).

## Related resources

You can use the following resources to learn more about the product and service lifecycle management process in Dynamics 365.

- [How to Create Service Items - Business Central](/dynamics365/business-central/service-how-to-create-service-items)
- [Service management overview - Supply Chain Management](/dynamics365/supply-chain/service-management/service-management-home-page)
- [Create products or services for work orders - Dynamics 365 Field Service](/dynamics365/field-service/create-product-or-service)
- [Manage and organize your product catalog with Dynamics 365 Sales](/training/modules/manage-organize-product-catalog-dynamics-365-sales/)
- [Set up a product catalog Walkthrough - Dynamics 365 Sales](/dynamics365/sales/set-up-product-catalog-walkthrough)

## Tags

*Stakeholders:* Functional consultant, Business analyst, Product development lead, Merchandising lead, Sales lead, Purchasing lead, Production lead, Supply chain lead, Quality control lead

*Products: Dynamics 365 Commerce, Dynamics 365 Customer Insights, Dynamics 365 Customer Service, Dynamics 365 Customer Service Insights, Dynamics 365 Field Service, Dynamics 365 Marketing, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center*
