---
title:  Product and service lifecycle management end-to-end overview
description: Learn about the end-to-end business process, product and service lifecycle management. This article provides a high-level flow diagram and describes the relationship with other processes in Dynamics 365 solutions.
ms.date: 04/03/2023
ms.topic: conceptual
author: rachel-profitt
ms.author: raprofit

---

# Product and service lifecycle management end-to-end overview

***Applies to: Dynamics 365 Commerce, Dynamics 365 Customer Insights, Dynamics 365 Customer Service, Dynamics 365 Customer Service Insights, Dynamics 365 Field Service, Dynamics 365 Marketing, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center***

This article describes the *product and service lifecycle management* end-to-end business process flow and its relationship to other business processes that can be used within Dynamics 365.

## Product and service lifecycle management process relationship

The following diagram shows the relationship of other processes and products/features for the *product and service lifecycle management* process.  

:::image type="content" source="media/product-service-lifecycle-management-process.png" lightbox="media/product-service-lifecycle-management-process.png" alt-text="Business process relationships with upstream and downstream processes that are explained in the next paragraphs.":::

The upstream processes for the *product and service lifecycle management* process include the following.

- **Forecast to plan**  

  Often, organizations will complete the product and services definition in the *product and service lifecycle management* process prior to beginning the forecasting process.

- **Prospect to quote**  

  In some operational strategies such as engineer to order, the *prospect to quote* process will occur prior to*product and service lifecycle management process*, since the quote is often the trigger to initiate the process.

- **Order to cash**  

  In some operational strategies such as engineer to order, the *order to cash* process will occur prior to *product and service lifecycle management process*, since the quote is often the trigger to initiate the process.

- **Service to cash**  

  In some service-based organizations, the service to cash process will start before the *product and service lifecycle management* process. For example, if a service technician is conducting a repair or inspection on a customer asset and need to order new parts that are not currently part of the product catalog.

- **Project to profit**  

  In some operational strategies such as engineer to order, the project to profit process may begin before the *product and service lifecycle management process* begins. For example, the project is created and budgets are set, drawing are completed and approved, before the organization begins to setup and procure the items to make the engineered product. Additionally, when organizations use projects to manage capital projects, the project definition, budgets and so on, are typically set before the organization begins to create and procure the needed products and services.

The *product and service lifecycle management* end-to-end process is broken down into the following business process areas:

- Categorize products and services

- Introduce new products and services

- Maintain product data

- Organize and assign product attributes and catalogs

- Design and configure manufacturing products

- Control product engineering changes

- Define product and service costing

- Define product and service pricing

- Manage product assortments and catalogs

- Manage product lifecycle

The downstream processes for the *product and service lifecycle management* process include the following.

- **Procure to pay**  

  Products are typically purchased after an agreement is made with a vendor and the product is defined in the system. In organizations that manufacture products, the products to be purchased are often defined by the engineering process, which is part of the *product and service lifecycle management* process. In some cases, the request for quotation process may happen before a product or service definition is created which would make the *procure to pay process* be upstream.

- **Prospect to quote**  

  In operational strategies such as make to stock, the *prospect to quote process* happens after a product mix has been determined in the *product and service lifecycle management* process.

- **Order to cash**  

  In operational strategies such as make to stock, or brick and mortar commerce scenarios, the *order to cash process* happens after a product mix has been determined in the *product and service lifecycle management* process.

- **Service to cash**  

  In most operational strategies, the *service to cash* process will occur after to*product and service lifecycle management process*, since the services to be offered are predetermined by the organization's sales strategy.

- **Plan to produce**  

  With the exception of operational strategies for make to order and engineer to order, the production process typically comes after the *product and service lifecycle management* process has been completed. Although, there are often updates throughout the production process, which can cause the process to be both upstream and downstream.

- **Project to profit**  

  In project based organizations, the project can be integrated with the supply chain to create purchase orders or item requirements that will be shipped to the customer in a downstream process after the item is defined.

- **Inventory to deliver**  

  The *inventory to deliver process* can only happen once the product exists in the system. The product is a key pre-requisite to track inventory information including receipts, issues, and movements for example.

- **Case to resolution**  

  The *case to resolution process* is downstream to the*product and service lifecycle management process* when you use cases to manage inventory issues, vendor issues, customer complaints, and so on.

- **Record to report**  

  The *record to report process* is downstream to the *product and service lifecycle management process* because items and orders must exist to recognize costs or revenues, for example, in the general ledger.

## Featured capabilities

There are product specific capabilities offered that interact with the *product and service lifecycle management* process including, but not limited to, the following:

- **Product catalogs**  

  Dynamics 365 Commerce and includes catalog features to help with the management of products in retail channels. Additionally, Dynamics 365 Supply Chain Management includes catalogs to help with the procurement process including both internal and external, sometimes referred to as punchout catalogs, to help maintain product information from a third-party.

- **Product assortments**  

  Product assortments are used in Dynamics 365 Commerce to assign different products to different retail channels.

- **Product attributes**  

  Product attributes are used to enrich product information in Dynamics 365 Commerce and Supply Chain Management.

- **Product categories**  

  Product categories are used to help create channel navigation in Dynamics 365 Commerce for site navigation as an example. You can also use product categories in Dynamics 365 Supply Chain Management to help manage and analyze your spend and revenue across the application.

- **Engineering change management**  

  For manufacturing companies or organizations that need tighter control of the onboarding of new products, the engineering change management module helps manage the workflow and data validation of setting up new products, BOMs, Formulas, and Routes.

- **Product translations**  

  When you sell or buy products in different countries/regions, you can translate your product descriptions and define vendor or customer specific item numbers to make the communication process with your customers and vendors easier.

- **Product templates**  

  Product templates allow you to create new products quickly and easily with similar information.

- **Product configurator**  

  When you have many options for a single product, which is common in certain industries such as automotive, the product configurator allows you to define an unlimited number of options with logic to control which options and combinations are allowed for a product. Dynamics 365 Supply Chain Management supports dynamically updating the BOM or Route and calculating the price for a product based on the options that are selected during order entry.

- **Lot (batch) and serial number control**  

  You can define products to be controls by a batch number, which is often referred to as a lot number, and control when a serial number is required. This allows for better inventory tracking and visibility throughout the system. You can control when a batch or serial number is required to ensure the quality of data needed for your operations is maintained by the users at every movement of the product.

## Product and service lifecycle management business process flow

The following diagram shows the high-level flow of the *product and service lifecycle management* business process. Each solid rectangle on the diagram represents an end-to-end business process area. The sub-processes shown in the diagram are shown for the *product and service lifecycle management* business process. The arrows on the diagram show the flow of the business process in an organization. If a sub-process can lead to more than one other sub-process, the parallel sub-processes are shown as branches.

:::image type="content" source="media/product-service-lifecycle-management-flow.png" alt-text="End-to-end process flow diagram for product and service lifecycle management." lightbox="media/product-service-lifecycle-management-flow.png":::

The following steps are illustrated in the order to cash end-to-end business process flow diagram.

1. Start

2. *Product and service lifecycle management* end-to-end process

3. [Categorize products and services](product-service-lifecycle-categorize-products-services-overview.md)  

4. *Introduce new products and services*

    1. *Maintain product data*

    2. *Organize and assign product attributes*

    3. *Manage product assortments and catalogs*

    4. [Define product and service costing](product-service-define-cost-overview.md)  

    5. *Define product and service pricing*

    6. *Design and configure manufactured products*

    7. *Control product engineering changes*

    8. *Manage product lifecycle*

        A parallel branch from h. *Manage product lifecycle* connects to g. *Control product engineering changes*.

Parallel branches from start connect to the following end-to-end processes shown on the left which all connect to 4. *Introduce new products and services*.

1. *Forecast to plan*

2. *Prospect to quote*

3. *Order to cash*

4. *Service to cash*

5. *Project to profit*

Parallel branches from 4. h. include the following end-to-end processes shown on the right:

1. *Procure to pay*

2. *Prospect to quote*

3. *Order to cash*

4. *Service to cash*

5. *Project to profit*

6. *Case to resolution*

7. *Plan to produce*

Parallel branches from a. *Procure to pay*, b. *Prospect to quote*, c. *Order to cash*, and g. *Plan to produce* connect to *Inventory to deliver*. *Inventory to deliver* connects to *Record to report*. *Record to report* connects to End.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *product and service lifecycle management* business processes, use the following resources and steps to learn more.

- Define the goals and objectives of implementing a *product and service lifecycle management* technology solution. Learn more at [Implementation strategy](../implementation-guide/implementation-strategy.md).

- Define the business process scope of your project. Learn more at [Process-focused solution](../implementation-guide/process-focused-solution.md).

- Request a demo or get a free trial of Dynamics 365 solutions for the *product and service lifecycle management* process. Learn more at [Request a demo](https://dynamics.microsoft.com/dynamics-365-free-trial/).

- Get an overview of the *product and service lifecycle management* process. Learn more at [Product and service lifecycle management business process areas](product-service-lifecycle-management-areas.md).

## Related resources

Use the following resources to learn more about the *product and service lifecycle management* process in Dynamics 365.

- [Learn the fundamentals of Dynamics 365 Supply Chain Management](/training/paths/explore-microsoft-dynamics-365-supply-chain-management/)

- [Engineering Change Management in Dynamics 365 Supply Chain Management TechTalk Series](https://community.dynamics.com/blogs/post/?postid=a8817f38-7b31-4c2c-a728-05ce505354c7)

- [Product information overview](/dynamics365/supply-chain/pim/product-information)

- [Manage and organize your product catalog with Dynamics 365 Sales](/training/modules/manage-organize-product-catalog-dynamics-365-sales/)

- [Set up a product catalog Walkthrough (Dynamics 365 Sales)](/dynamics365/sales/set-up-product-catalog-walkthrough)

- [Configure and manage products and inventory in Dynamics 365 Supply Chain Management](/training/paths/configure-manage-products-inventory-dyn365-supply-chain-mgmt/)

- [Microsoft Certified: Dynamics 365 Supply Chain Management Functional Consultant Associate](/certifications/d365-functional-consultant-supply-chain-management/)

- Find definitions of terminology used in content for *product and service lifecycle management* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article, including the following terms:

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
<!--## Tags
*Stakeholders:* Functional consultant, Business analyst, Product development lead, Merchandising lead, Sales lead, Purchasing lead, Production lead, Supply chain lead, Quality control lead

*Products:* Dynamics 365 Commerce, Dynamics 365 Customer Insights, Dynamics 365 Customer Service, Dynamics 365 Customer Service Insights, Dynamics 365 Field Service, Dynamics 365 Marketing, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center
