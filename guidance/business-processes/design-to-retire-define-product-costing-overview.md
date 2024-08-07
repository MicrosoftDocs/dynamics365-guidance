---
title: Overview of business process for product costing through Dynamics 365
description: Learn how you can use Dynamics 365 products to support your organization's business processes to set the cost the goods that you sell.
ms.date: 11/24/2023
ms.topic: conceptual
author: rachel-profitt
ms.author: raprofit
---

# Business process for product costing and how it relates to other processes with Dynamics 365

***Applies to: Dynamics 365 Business Central, Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center***

This article describes the business process for defining the cost of products. It also explains how that process relates to other business processes in Dynamics 365.

The definition of product costs is essential for any organization that wants to understand and effectively manage its finances. The goal is to know the amount of money that goes into producing or purchasing a particular item, and the cost of delivering that item to the customer. This information is crucial for setting prices, making informed decisions about resource allocation, and evaluating the financial performance of the business.

Here are some of the key reasons why the definition of product costs is important:

- **Pricing**: An understanding of the costs of a product helps organizations set prices that are appropriate and profitable. If the costs aren't understood, it can be difficult to determine a fair price that covers expenses and generates a profit.
- **Profitability**: By calculating the costs that are associated with producing or purchasing products, organizations can determine whether they are making a profit. This information is crucial for assessing the financial health of the business and identifying areas for improvements.
- **Resource allocation**: An understanding of the costs of producing products helps organizations more effectively allocate their resources. By understanding the costs that are involved, businesses can make decisions about how to allocate resources such as labor, materials, and equipment.
- **Cost reduction**: An understanding of the costs of producing products can help organizations identify areas where costs can be reduced. If expenses can be reduced in any areas without compromising quality, businesses can become more efficient and improve their bottom line.

Overall, the definition of product costs is essential for any organization that wants to operate efficiently, remain competitive, and generate a healthy profit. By having a clear understanding of costs, businesses can make informed decisions about pricing, resource allocation, and cost reduction. Therefore, they can ultimately achieve greater success and profitability.

Dynamics 365 includes tools to help support organizations define product costs to track, report, and analyze profitability, margins, and more. Here are just a few examples that show how Dynamics 365 can support your costing business requirements:

- Dynamics 365 Sales and Field Service include [product catalogs](/dynamics365/sales/set-up-product-catalog-walkthrough), so that you can quickly define the product cost that is tracked on each transaction.
- Dynamics 365 Supply Chain Management includes robust cost calculation features, such as bill of materials (BOM) and formula cost roll-ups or calculations for produced items. Learn more at [Cost management home page](/dynamics365/supply-chain/cost-management/cost-management-home-page).
- Dynamics 365 Supply Chain Management also supports the calculation of indirect costs (sometimes referred to as overhead costs) for purchased or produced items. In addition, it supports a costing sheet that you can use to analyze the breakdown of costs.
- The *Transportation management* module in Dynamics 365 Supply Chain Management helps you calculate your inbound and outbound freight and handling costs. Learn more at [Transportation management overview](/dynamics365/supply-chain/transportation/transportation-management-overview).
- Dynamics 365 Business Central includes *cost accounting* to help you understand the costs of running a business. Learn more at [Cost accounting overview](/dynamics365/business-central/finance-manage-cost-accounting).
- Dynamics 365 Business Central also includes *inventory costs*, so that you can report on manufacturing costs and inventory costs (that is, the value of items). Learn more at [Manage inventory costs](/dynamics365/business-central/finance-manage-inventory-costs).

## Stakeholders

There are several stakeholders in an organization that should be involved in defining product costs, because the process can have a significant impact on the overall success of the business. Here are some of the stakeholders who should be involved:

- **Finance and accounting teams**: The finance and accounting teams are responsible for managing the financial health of the organization. They should be involved in defining product costs because they have the expertise to analyze costs and identify areas where expenses can be reduced.
- **Operations teams**: The operations teams are responsible for producing, procuring, and delivering products. In project-based organizations, these teams include project management teams. These teams might also include the transportation teams that are responsible for sourcing inbound and outbound transportation. These teams should be involved in defining product costs because they have first-hand knowledge of the processes and resources that are required to procure, produce, and deliver the products.
- **Sales and marketing teams**: The sales and marketing teams are responsible for pricing products and promoting them to customers. They should be involved in defining product costs because they must understand the costs that are associated with the products, so that they can set prices and develop marketing strategies.
- **Senior management**: Members of senior management should be involved in defining product costs because they are responsible for making strategic decisions that affect the overall direction of the organization. They must understand the costs that are associated with products, so that they can make informed decisions about resource allocation and pricing strategies.
- **Customers**: Although customers aren't directly involved in defining product costs, they are important stakeholders who can provide valuable feedback about pricing and product quality. An understanding of the costs that are associated with products can help organizations make pricing decisions that are fair and competitive, but also meet the needs of their customers.

Overall, when product costs are defined, it's important to involve all stakeholders who have a vested interest in the success of the organization. By working together to analyze costs and identify areas for improvement, organizations can make informed decisions that drive growth and profitability.

## Define product costing process flow

The following diagram illustrates the *define product costing* business process area. [!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/design-to-retire-define-product-cost.svg" alt-text="Flow diagram with steps for the process that is explained further in the next paragraphs." lightbox="media/design-to-retire-define-product-cost.svg":::'

1. Start

    Parallel branches connect to the *Plan to produce* and *Source to pay* end-to-end processes, each of which connects to d. *Analyze product costing strategy*.

1. *Design to retire*

    A parallel branch connects to *Introduce new products*, which also connects to 3. *Define product costing*.

1. *Define product costing*

    1. *Define product costing strategy*

        A parallel branch connects to *Manage product pricing*, which connects to *Order to cash*.

    1. *Set costing standards*

        Parallel branches connect to *Order to cash*, *Plan to produce*, *Source to pay*, and *Inventory to deliver*.

    1. *Maintain costing standards*

        Parallel branches connect to *Plan to produce*, *Source to pay*, and *Inventory to deliver*.

    1. *Analyze product costing strategy*

1. *Record to report*

    Each of the following end-to-end processes connects to the *Record to report* box:

    - *Order to cash*
    - *Plan to produce*
    - *Source to pay*
    - *Inventory to deliver*

1. End

## Define product costing benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the *define product costing* processes. The following sections outline the key benefits that an organization might monitor and measure for *define product costing*.

### Accurate costing

Dynamics 365 includes powerful tools for accurately calculating product costs based on actual expenses, such as materials, labor, and overhead. For example, Dynamics 365 Supply Chain Management includes robust cost calculation features such as BOM and formula cost roll-ups or calculations for produced items, and the ability to calculate indirect costs or overhead costs for purchased or produced items.

### Real-time and flexible cost information

Dynamics 365 provides real-time cost information, so that organizations can track costs as they change and adjust pricing and resource allocation accordingly. For example, Dynamics 365 Sales and Field Service includes a product catalog feature that helps you quickly define the product cost that is tracked on each transaction. By using the Global Inventory Accounting add-in with Dynamics 365 Supply Chain Management, organizations can analyze costs in multiple currencies or costing methodologies, for example.

### Streamlined processes

Dynamics 365 streamlines the product costing process by automating many of the manual tasks that are involved in cost calculation and analysis. For example, Dynamics 365 Supply Chain Management includes a costing sheet that you can use to analyze the breakdown of costs.

### Improved collaboration

By using Dynamics 365 together with Microsoft Teams and Microsoft 365, you get a centralized platform that supports collaboration among the various teams that are involved in the product costing process, including finance, operations, and sales. This collaboration improves communication and visibility, and therefore leads to better decision-making and more informed cost calculations.

### Enhanced reporting and analysis

Dynamics 365 provides advanced reporting and analytics capabilities that are built with Power BI and the Azure Data Lake. Organizations can use these capabilities to gain insights into their cost structures and identify areas for improvement. For example, you can use the *Transportation management* module in Dynamics 365 Supply Chain Management to calculate your inbound and outbound freight and handling costs.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your product costing business processes, you can use the following resources and steps to learn more.

1. [Define product catalog and strategy](design-to-retire-define-product-catalog-strategy-overview.md)

2. [Introduce new products](design-to-retire-introduce-new-products-overview.md)  

3. *Define product costing* (the article that you're currently reading)

4. [Define product pricing](design-to-retire-manage-product-pricing-overview.md)  

5. [Manage product lifecycle](design-to-retire-manage-product-lifecycle-overview.md)  

## Related information

You can use the following resources to learn more about the product costing process in Dynamics 365.

- [Cost management home page](/dynamics365/supply-chain/cost-management/cost-management-home-page)
- [Cost accounting home page](/dynamics365/finance/cost-accounting/cost-accounting-home-page?context=%2Fdynamics365%2Fcontext%2Fsupply-chain)
- [Work with the costing sheet in Dynamics 365 Supply Chain Management](/training/modules/work-costing-sheet-dyn365-supply-chain-mgmt/)
- [Get started with cost accounting in Dynamics 365 Finance](/training/modules/get-started-cost-accounting-dyn365-finance/)
- [Get started with cost accounting for supply chains in Dynamics 365 Finance](/training/paths/get-started-cost-accounting-supply-chains-dyn365-finance/)
- [Use cost accounting in Microsoft Dynamics 365 Business Central](/training/paths/use-cost-accounting-dynamics-365-business-central/)
- [Cost Accounting Series - Dynamics 365 Supply Chain Management TechTalk Series](https://community.dynamics.com/blogs/post/?postid=9f267e7f-a1a3-4d29-8f0f-f755c22c4ca5)
- [Inventory Costing in Dynamics 365 Supply Chain Management TechTalk Series](https://community.dynamics.com/blogs/post/?postid=a1955d50-c26c-4563-b42c-b1af2261ae6f)
- [Design Details: Costing Methods in Dynamics 365 Business Central](/dynamics365/business-central/design-details-costing-methods)
- [Cost accounting in Business Central](/dynamics365/business-central/finance-manage-cost-accounting)
- [Inventory costs in Business Central](/dynamics365/business-central/finance-manage-inventory-costs)
- [Issue and settle vendor payments overview](source-to-pay-issue-and-settle-vendor-payments-overview.md)
- Find definitions of terminology that is used in content for *define product costing* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article. For example, this glossary includes the following terms:

    - [Cost](glossary.md#cost)
    - [Cost accounting](glossary.md#cost-accounting)
    - [Costing methodology](glossary.md#costing-methodology)
    - [Costing sheet](glossary.md#costing-sheet)
    - [Costing version](glossary.md#costing-version)
    - [Overhead costs](glossary.md#overhead-costs)

<!-- ## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Accounts payable, Accounts receivable, Administrative, Audit, Engineering, Finance, Operations, Production, Project Management, Purchasing, Sales, Service operations, Transportation

*Products:* Dynamics 365 Business Central, Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Rachel Profitt](https://linkedin.com/in/rachelprofitt) \| Microsoft FastTrack Solution Architect

Other contributors:

- [Michael Herold](https://linkedin.com/in/maherold) \| Microsoft Principal Consultant
