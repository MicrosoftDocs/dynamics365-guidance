---
title: Design to retire end-to-end overview
description: Learn about the end-to-end business process, design to retire. This article provides a high-level flow diagram and describes the relationship with other processes in Dynamics 365 solutions.
ms.date: 11/27/2023
ms.topic: conceptual
author: rachel-profitt
ms.author: raprofit
---

# Design to retire end-to-end overview

***Applies to: Dynamics 365 Commerce, Dynamics 365 Customer Insights, Dynamics 365 Customer Service, Dynamics 365 Customer Service Insights, Dynamics 365 Field Service, Dynamics 365 Marketing, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center***

This article describes the *design to retire* end-to-end business process flow and its relationship to other business processes that you can use with Dynamics 365.

## Design to retire process relationship 

The following diagram shows the relationship of other processes and products/features for the *design to retire* process. The *design to retire* process covers the process for introducing new tangible products. Learn more about bringing services to market at [Concept to market end-to-end overview](concept-to-market-overview.md).

:::image type="content" source="media/design-to-retire-process.svg" alt-text="Business process relationships with upstream and downstream processes that are explained in the next paragraphs." lightbox="media/design-to-retire-process.svg":::

The upstream processes for the *design to retire* process include the following.

- **Forecast to plan**: Often, organizations complete the products definition in the *design to retire* process before they start the forecasting process.
- **Prospect to quote**: In some operational strategies such as engineer to order, the *prospect to quote* process occurs before the *design to retire* process, since the quote is often the trigger to initiate the process.
- **Order to cash**: In some operational strategies such as engineer to order, the *order to cash* process occurs before the *design to retire process*, since the quote is often the trigger to initiate the process.
- **Project to profit**: In some operational strategies such as engineer to order, the *project to profit* process starts before the *design to retire* process begins. For example, before the organization begins to set up and procure the items to produce the product, they have created the project, defined the budgets, and they've completed and approved drawings. Additionally, when organizations use projects to manage capital projects, the project definition, budgets, and so on, are typically set before the organization begins to create and procure the needed products.

The *design to retire* end-to-end process is broken down into the following business process areas:

- Define product catalog and strategy
- Introduce new products
- Define product costing
- Define product pricing
- Manage product lifecycle

Learn more about the business process areas at [Design to retire business process areas](design-to-retire-areas.md). 

The downstream processes for the *design to retire* process include the following.

- **Procure to pay**: Typically products are purchased after an agreement is made with a vendor and the product is defined in the system. In organizations that manufacture products, the products to be purchased are often defined by the engineering process, which is part of the *design to retire* process. In some cases, the request for quotation process happens before a product definition is created, which would make the *procure to pay* process be upstream.
- **Prospect to quote**: In operational strategies such as make-to-stock, the *prospect to quote process* happens after a product mix has been determined in the *design to retire* process.
- **Order to cash**: In operational strategies such as make-to-stock, or brick and mortar commerce scenarios, the *order to cash* process happens after a product mix has been determined in the *design to retire* process.
- **Plan to produce**: Except for operational strategies for make-to-order and engineer-to -order, the production process typically comes after the *design to retire* process is completed. Although there are often updates throughout the production process, which can cause the process to be both upstream and downstream.
- **Project to profit**: In project-based organizations, the project can be integrated with the supply chain to create purchase orders or item requirements that ship to the customer in a downstream process after the item is defined.
- **Inventory to deliver**: The *inventory to deliver* process can only happen once the product exists in the system. The product is a key prerequisite to track inventory information including receipts, issues, and movements for example.
- **Case to resolution**: The *case to resolution* process is downstream to the *design to retire* process when you use cases to manage inventory issues, vendor issues, customer complaints, and so on.
- **Record to report**: The *record to report* process is downstream to the *design to retire* process because items and orders must exist to recognize costs or revenues, for example, in the general ledger.

## Featured capabilities

There are product specific capabilities offered that interact with the *design to retire* process including, but not limited to, the following list:

- **Product catalogs**: Dynamics 365 Commerce and includes catalog features to help with the management of products in retail channels. Additionally, Dynamics 365 Supply Chain Management includes catalogs to help with the procurement process including both internal and external, sometimes referred to as punchout catalogs, to help maintain product information from a third-party.
- **Product assortments**: Product assortments are used in Dynamics 365 Commerce to assign different products to different retail channels.
- **Product attributes**: Product attributes are used to enrich product information in Dynamics 365 Commerce and Supply Chain Management.
- **Product categories**: Product categories are used to help create channel navigation in Dynamics 365 Commerce for site navigation as an example. You can also use product categories in Dynamics 365 Supply Chain Management to help manage and analyze your spend and revenue across the application.
- **Engineering change management**: For manufacturing companies or organizations that need tighter control of the onboarding of new products, the engineering change management module helps manage the workflow and data validation of setting up new products, BOMs, Formulas, and Routes.
- **Product translations**: When you sell or buy products in different countries/regions, you can translate your product descriptions. You can also define vendor- or customer-specific item numbers to make the communication process with your customers and vendors easier.
- **Product templates**: With product templates, you can create new products quickly and easily with similar information.
- **Product configurator**: When you have many options for a single product, which is common in certain industries such as automotive, the product configurator allows you to define an unlimited number of options with logic to control which options and combinations are allowed for a product. Dynamics 365 Supply Chain Management supports dynamically updating the BOM or Route. There's also support for calculating the price for a product based on the options that are selected during order entry.
- **Lot (batch) and serial number control**: You can define products to be controls by a batch number, which is often referred to as a lot number, and control when a serial number is required. This approach provides better inventory tracking and visibility throughout the system. You can control when a batch or serial number is required to make sure users maintain the quality of data needed for your operations at every movement of the product.

## Design to retire business process flow

The following diagram shows the high-level flow of the *design to retire* business process. [!INCLUDE [daf-business-process-e2e-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-e2e-flow-def.md)]

:::image type="content" source="media/design-to-retire-flow.svg" alt-text="Flow diagram for the end-to-end business process, which is explained in the paragraphs after the image." lightbox="media/design-to-retire-flow.svg":::

The following steps are illustrated in the *design to retire* end-to-end business process flow diagram.

1. Start
2. *Design to retire* end-to-end process
3. *Define product catalog and strategy*
4. *Introduce new products*

    1. *Manage product costing*
    2. *Define product pricing*

5. *Manage product lifecycle*

    1. *Procure to pay*
    2. *Prospect to quote*
    3. *Order to cash*
    4. *Plan to produce*
    5. *Project to profit*
    6. *Case to resolution*

6. End

Parallel branches from 5.a. *Procure to pay*, 5.b. *Prospect to quote*, 5.c. *Order to cash*, and 5.d. *Plan to produce* connect to *Inventory to deliver*, which connects to *Record to report*, and then to 6. End.

Parallel branches connect from Start to each of the following upstream end-to-end processes that all connect to 4. *Introduce new products*.

- *Forecast to plan*
- *Prospect to quote*
- *Order to cash*
- *Project to profit*

## Next steps

If you would like to implement Dynamics 365 solutions to assist with your design to retire business processes, you can use the following resources and steps to learn mor.mde.

- Define the goals and objectives of implementing a design to retire technology solution. Learn more at [Implementation strategy](../implementation-guide/implementation-strategy.md).
- Define the business process scope of your project. Learn more at [Process-focused solution](../implementation-guide/process-focused-solution.md).
- Request a demo or get a free trial of Dynamics 365 solutions for the *design to retire* process. Learn more at [Request a demo](https://dynamics.microsoft.com/dynamics-365-free-trial/).
- Get an overview of the *design to retire* process. Learn more at [Design to retire business process areas](design-to-retire-areas.md).

## Related resources

You can use the following resources to learn more about the *design to retire* process in Dynamics 365.

- [Learn the fundamentals of Dynamics 365 Supply Chain Management](/training/paths/explore-microsoft-dynamics-365-supply-chain-management/)
- [Engineering Change Management in Dynamics 365 Supply Chain Management TechTalk Series](https://community.dynamics.com/blogs/post/?postid=a8817f38-7b31-4c2c-a728-05ce505354c7)
- [Product information overview - Supply Chain Management](/dynamics365/supply-chain/pim/product-information)
- [Manage and organize your product catalog with Dynamics 365 Sales](/training/modules/manage-organize-product-catalog-dynamics-365-sales/)
- [Set up a product catalog Walkthrough (Dynamics 365 Sales)](/dynamics365/sales/set-up-product-catalog-walkthrough)
- [Configure and manage products and inventory in Dynamics 365 Supply Chain Management](/training/paths/configure-manage-products-inventory-dyn365-supply-chain-mgmt/)
- [Microsoft Certified: Dynamics 365 Supply Chain Management Functional Consultant Associate](/certifications/d365-functional-consultant-supply-chain-management/)
- Find definitions of terminology used in content for *design to retire* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article, including the following terms:

  - [Attribute](glossary.md#attribute) 
  - [Catalog](glossary.md#catalog)  
  - [Category](glossary.md#product-category)  
  - [Engineering change management (ECM)](glossary.md#engineering-change-management-ecm)  
  - [Inventory dimensions](glossary.md#inventory-dimensions)  
  - [Item](glossary.md#item)  
  - [Product](glossary.md#product) 
  - [Product family](glossary.md#product-family)  
  - [Product lifecycle management (PLM)](glossary.md#product-lifecycle-management-plm)  
  - [Service](glossary.md#service)  
  - [Variant](glossary.md#variant)  

## Tags

*Stakeholders:* Functional consultant, Business analyst, Product development lead, Merchandising lead, Sales lead, Purchasing lead, Production lead, Supply chain lead, Quality control lead.

*Products*: Dynamics 365 Commerce, Dynamics 365 Customer Insights, Dynamics 365 Customer Service, Dynamics 365 Customer Service Insights, Dynamics 365 Field Service, Dynamics 365 Marketing, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center
