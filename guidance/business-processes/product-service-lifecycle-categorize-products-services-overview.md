---
title:  Categorize products and service overview
description: Learn how you can use Dynamics 365 products to support your organization's business processes to categorize the goods and services that you sell.
ms.date: 09/05/2023
ms.topic: conceptual
author: edupont04
ms.author: raprofit
---

# Categorize products and services overview

***Applies to: Dynamics 365 Business Central, Dynamics 365 Commerce, Dynamics 365 Customer Insights, Dynamics 365 Customer Service, Dynamics 365 Customer Service Insights, Dynamics 365 Field Service, Dynamics 365 Marketing, Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center***

This article describes how to categorize, segment, and merchandise products and services in Dynamics 365 solutions.

All organizations group and categorize or segment their products and services into logical grouping for various reasons. At the beginning of your Dynamics 365 implementation project, you should consider how to implement these groupings.

The categorization, merchandising, and segmentation of products and services are related concepts. The terms are often used interchangeably, but they have distinct meanings and functions in the system as well. Let's compare the three terms: 

- *Categorization* is the process for grouping products or services based on shared characteristics  
- *Segmentation* is the process of dividing a market (of typically customers) into smaller groups (or segments) based on shared characteristics or interests  
- *Merchandising* is the process of presenting products or services in an appealing and attractive way to the customers  

<!-- It's important for an organization to consider carefully how it categorizes, segments, and merchandises the products and services it offers. -->When the organization adopts Dynamics 365, they often already work with such groupings. It's important to consider if the current mechanism for categorizing products and services still meets all business requirements. The implementation of a new technology solution is often a good time to consider making a change to the structure if required by the business. For example, consider the following questions: 

- How do you drive downstream business processes and automation?  
- How do you report and analyze your data, including operational reporting and financial reporting?  
- How has your business grown since the organization first started using categorization, segmentation, or merchandising?  
- How do you anticipate your business will grow in the future?  

The answers to these questions should help inform your process for defining the way you implement a technology solution to support the categorization of products and services. This business process area should always be considered early in a Dynamics 365 implementation project. Also consider the number of changes that may be happening to the data in this area. Such changes can make integrations, data migration, and other aspects of your project more complex.

When an organization starts a Dynamics 365 implementation, it's important to carefully consider how you define the product lines in the system. Tasks include setting up item groups and [product categories](/dynamics365/supply-chain/pim/tasks/classify-product-category-hierarchies) in Dynamics 365 Supply Chain Management, [product families](/dynamics365/sales/create-product-family) in Dynamics 365 Sales, and [item groups](/dynamics365/business-central/inventory-how-categorize-items) or [item attributes](/dynamics365/business-central/inventory-how-work-item-attributes) in Dynamics 365 Business Central. The business process area for categorizing products and services also includes the definition of product policies. It's recommended to group similar items together based on the expected behaviors they need in the system. For example, [item model groups](/dynamics365/supply-chain/pim/product-configuration-models), reservations, storage, and tracking dimensions, and more in Dynamics 365 Supply Chain Management.  

Additionally, if your organization offers multiple types of products and services, you must define the rules and configurations for each type of product that you offer. For example, you can use catch weight items in the chemical or food and beverage industry. In some industries, consigned inventory is common, which requires other setup, configuration, and considerations. While service industries have other considerations to make for services that are offered including warranties, installation, and so on. Many organizations may also charge more fees or service charges for tangible items that are sold, which could require extra considerations. Dynamics 356 supports various flexible configurations to support many types of products, services, and more fees and charges that might be charges to customers or imposed by suppliers.

Once you have created the basic definition of how you organize products, you can start to categorize and build hierarchical structures of products. The following list outlines some options:

- Dynamics 365 Supply Chain Management and Commerce support multiple flexible [hierarchies](glossary.md#product-hierarchy) for procurement, sales, channel management, and more.  
- With Dynamics 365 Sales, you can create hierarchies of products with [product families](glossary.md#product-family).  
- With Dynamics 365 Customer Service, you can create and manage [subjects](glossary.md#subject) to manage complex hierarchies. For example, hierarchies can represent products, brands, or types of issues that your customers report.  
- With Dynamics 365 Customer Insights, [segments](/dynamics365/customer-insights/journeys/segmentation-lists-subscriptions) help you group customers based on their buying habits. One common segment is typically related to the products customers purchase. Organizations can define many segments based on many different attributes of the products that are purchased.  
- With Dynamics 365 Business Central, you can combine [categories, attributes, and variants](/dynamics365/business-central/inventory-how-categorize-items#categories-attributes-and-variants) to fit your needs.   

## Stakeholders 

Many people across the organization should contribute to the decision-making process and design of the *categorize product and services* business process area. The following list provides examples of such stakeholders:

- **Marketing stakeholders**: Includes roles such as the Marketing Manager, CMO, Analyst, Advertising, or Coordinator. The marketing department is responsible for developing and implementing marketing strategies based on the categorization and segmentation of products and services. Therefore, they should be involved in the implementation of the technology solution to make sure it supports their marketing initiatives.

- **Sales stakeholders**: Includes roles such as the Sales Rep, Account Executive, Business Development Manager, Sales Manger, Sales Director, Sales Engineer, Inside Sales, Key Account Manager, Channel Sales Manager, or the CSO. The sales stakeholders are responsible for selling the products and services. Involve them in the implementation of the technology solution to make sure  it supports their sales efforts.

- **Customer service stakeholders**: Includes roles such as Rep, Manager, Supervisor, Director. Customer service stakeholders are responsible for providing support to customers. Involve them in the implementation of the technology solution to make sure it meets the needs of customers.

- **Finance stakeholders**: Includes roles such as Controller, Director, CFO. The finance stakeholders are responsible for budgeting and financial reporting. Involve them in the implementation of the technology solution to make sure  it aligns with the organization's financial objectives.

- **Executive management stakeholders**: Involve the executive management in the implementation project to make sure it aligns with the organization's overall strategy and objectives and to provide support and resources for the implementation.

## Categorize products and services process flow 

The following diagram illustrates the *categorize products and services* business process area.

:::image type="content" source="media/product-service-lifecycle-categorize-flow.svg" alt-text="Categorize  products and services process flow that is explained in the next paragraphs" lightbox="media/product-service-lifecycle-categorize-flow.svg":::

[!INCLUDE [daf-business-process-flow-def](../includes/daf-business-process-flow-def.md)]

The flow diagram covers the following steps.

1. Start

2. *Product and service lifecycle management* end-to-end process

3. *Categorize products and services* business process area

4. *Define product types*

5. *Define product lines*

6. *Define product policies*

    1. Leads to the *Introduce new products and services* business process area, which leads to the following end-to-end scenarios: [Order to cash](order-to-cash-overview.md), [Plan to produce](plan-to-produce-overview.md), [Procure to pay](procure-to-pay-overview.md), and [Inventory to deliver](inventory-to-deliver-overview.md).

7. *Organize products*

    1. Leads to the *Organize and assign attributes and catalogs* business process area, which then leads to End.

8. End

## Categorize products and services benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the *categorize products and services* area. The following sections outline the key benefits that an organization might monitor and measure for *categorize products and services*.

### Streamlined product and service categorization

Dynamics 365 Supply Chain Management and Dynamics 365 Business Central provide tools for categorizing products and services based on shared characteristics such as attributes, categories, and subcategories. Categorization makes it easier to manage and organize products and services and to create targeted marketing strategies. When you also use other Dynamics 365 applications with Dynamics 365 Supply Chain Management, the product details can be synchronized using [dual-write maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page) to other tables and entities to support the business needs in many other applications automatically.

### Improved customer insights

When you use Dynamics 365 to categorize your products and services, your organization can gain insights into the needs and preferences of its customers. This information can be used to tailor its offerings to meet the specific needs of different customer groups. For example, in Dynamics 365 Marketing, you can create a dynamic segment to automatically update when customers purchase a certain type of item and then promote a similar item using a customer journey. With this approach, you can create more targeted marketing strategies, which can ultimately make your marketing campaigns more effective and improve the return on investment of your campaign.

### Optimize product development

When the organization understands the needs and preferences of different customer groups, they can develop products and services that are more likely to be successful in the marketplace. This approach can help to minimize the risk of product failures and reduce development costs. Dynamics 365 Supply Chain Management and Commerce includes flexible product categorization and attributes to support unique industry and localization requirements. When you combine this capability with Power BI, you can easily analyze the data to determine which customers and products are performing better. Similar functionality is available with Dynamics 365 Sales to create product families and analyze the sales data by using Power BI.

### Increase customer loyalty

When an organization can tailor its offerings to meet the needs of different customer groups, an organization can increase customer satisfaction and loyalty. A result could be higher retention rates and increased customer lifetime value. Dynamics 365 Commerce includes a loyalty program that allows you to track sales across every channel, and Dynamics 365 Customer Insights allows you to pull sales data from many different sources to analyze. <!--When you use the categorization or segmentation features available in Dynamics 365 to TODO: THIS SENTENCE WAS UNFINISHED AT SUBMISSION-->

### Optimize customer experiences

When you use subjects in Dynamics 365 Customer Service to manage cases, you can model them after categories of products and services. It might help you categorize and analyze cases by the subjects of cases that are created and worked on. When you use automated routing with cases, it can also improve the customer experience to ensure that the right person is assigned to the ticket to help resolve the issue. This can be especially true in organization or industries where the product or service mix is diverse. In cases where the product or service mix isn't diverse, the subject can still be helpful in analyzing trends for a given product line, product type, or service, for example. This analysis helps you determine if more training or quality issues exist.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *product and service lifecycle management* business processes, you can use the following resources and steps to learn more. Links are added when articles become available.

1. Categorize product and services. (The article you're currently reading.)

2. Introduce new products and services

3. Maintain product data

4. [Define product and service costing](product-service-define-cost-overview.md)

5. Define product and service pricing

6. Organize and assign product attributes and catalogs

7. Manage product assortments and catalogs

8. Manage product lifecycle

9. Design and configure manufactured products

10. Control product engineering changes

## Related resources

You can use the following resources to learn more about the *categorize products and services* business process area in Dynamics 365.

- [Manage product categories and products (Commerce)](/dynamics365/commerce/category-management-product-creation)
- [Set up product families (Sales)](/dynamics365/sales/create-product-family)  
- [Create segments and lists to establish target markets (Marketing)](/dynamics365/marketing/segmentation-lists-subscriptions)
- [Define subjects to categorize cases, products, and articles](/power-platform/admin/define-subjects-categorize-cases-products-articles)
- [Classify a product using category hierarchies (Supply Chain Management)](/dynamics365/supply-chain/pim/tasks/classify-product-category-hierarchies)
- [Create a new product hierarchy (Commerce)](/dynamics365/commerce/create-product-hierarchy)
- [Categorize items (Business Central)](/dynamics365/business-central/inventory-how-categorize-items)  
- Find definitions of terminology used in content for *product and service costing* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article, including the following terms:

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

