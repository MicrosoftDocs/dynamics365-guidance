---
title: Define product costing overview
description: Learn how you can use Dynamics 365 products to support your organization's business processes to set the cost the goods that you sell.
ms.date: 11/24/2023
ms.topic: conceptual
author: rachel-profitt
ms.author: raprofit
---

# Define product costing overview

***Applies to: Dynamics 365 Business Central, Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center***

This article describes the business process for defining the cost of products, and how that process relates to other business processes with Dynamics 365.

Defining product costs is essential for any organization that wants to understand and manage its finances effectively. The purpose is to know the amount of money that goes into producing or purchasing a particular item, and the cost of delivering that item to the customer. This information is crucial for setting prices, making informed decisions about resource allocation, and evaluating the financial performance of the business.

Here are some of the key reasons why defining product costs is important:

- **Pricing**: Knowing the costs of a product helps organizations to set prices that are appropriate and profitable. Without an understanding of costs, it can be difficult to determine a fair price that covers expenses and generates a profit.

- **Profitability**: When they calculate the costs associated with producing or purchasing products, organizations can determine whether they're making a profit or not. This information is crucial for assessing the financial health of the business and identifying areas where improvements can be made.

- **Resource Allocation**: Knowing the costs of producing products helps organizations to allocate their resources more effectively. When they understand the costs involved, businesses can make decisions about how to allocate resources such as labor, materials, and equipment.

- **Cost Reduction**: Understanding the costs of producing products can also help organizations identify areas where costs can be reduced. By identifying areas where expenses can be reduced without compromising quality, businesses can become more efficient and improve their bottom line.

Overall, defining product costs is essential for any organization that wants to operate efficiently, remain competitive, and generate a healthy profit. By having a clear understanding of costs, businesses can make informed decisions about pricing, resource allocation, and cost reduction, which can ultimately lead to greater success and profitability.

Dynamics 365 includes tools to help support organizations define product costs to track, report, and analyze the profitability, margins, and more. Let's look at the following examples:

- Dynamics 365 Sales and Field Service include [product catalogs](/dynamics365/sales/set-up-product-catalog-walkthrough) so that you can quickly define the product cost that is tracked on each transaction.  
- Dynamics 365 Supply Chain Management includes robust cost calculation features such as BOM and Formula cost roll-ups or calculations for produced items. Learn more at [Cost management home page](/dynamics365/supply-chain/cost-management/cost-management-home-page).  

  Supply Chain Management also supports the calculation of indirect costs, sometimes referred to as overhead costs, for purchased or produced items, and a costing sheet to analyze the breakdown of costs. 
- The *Transportation management* module in Dynamics 365 Supply Chain Management helps you calculate your inbound and outbound freight and handling costs. Learn more at [Transportation management overview](/dynamics365/supply-chain/transportation/transportation-management-overview).   
- Dynamics 365 Business Central includes *cost accounting* to help you understand the costs of running a business. Learn more at [Cost accounting overview](/dynamics365/business-central/finance-manage-cost-accounting).
- Business Central also includes *inventory costs* so you can report on manufacturing costs and inventory costs, that is, the value of items. Learn more at [Manage inventory costs](/dynamics365/business-central/finance-manage-inventory-costs).

The list includes just a few examples of how Dynamics 365 can support your costing business requirements.

## Stakeholders

There are several stakeholders in an organization that should be involved in defining product costs, as the process can have a significant impact on the overall success of the business. Here are some of the stakeholders who should be involved:

- **Finance and accounting teams**: The finance and accounting teams are responsible for managing the financial health of the organization. They should be involved in defining product costs as they have the expertise to analyze costs and identify areas where expenses can be reduced.

- **Operations teams**: The operations teams are responsible for the production, procurement, and delivery of products. Examples include project management teams in project-based organizations. It might also include the transportation teams responsible for sourcing inbound and outbound transportation. They should be involved in defining product costs as they have first-hand knowledge of the processes and resources required to procure, produce, and deliver the products.

- **Sales and marketing teams**: The sales and marketing teams are responsible for pricing and promoting products to customers. They should be involved in defining product costs as they need to understand the costs associated with the products to set prices and develop marketing strategies.

- **Senior management**: Senior management should be involved in defining product costs as they're responsible for making strategic decisions that affect the overall direction of the organization. They need to understand the costs associated with products to make informed decisions about resource allocation and pricing strategies.

- **Customers**: While customers aren't directly involved in defining product costs, they're important stakeholders who can provide valuable feedback on pricing and product quality. Understanding the costs associated with products can help organizations make pricing decisions that are fair and competitive while meeting the needs of their customers.

Overall, it's important to involve all stakeholders who have a vested interest in the success of the organization when defining product costs. By working together to analyze costs and identify areas for improvement, organizations can make informed decisions that drive growth and profitability.

## Define product costing process flow 

The following diagram illustrates the *define product costing* business process area. [!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/design-to-retire-define-product-cost.svg" alt-text="Flow diagram with steps for the process that is explained further in the next paragraphs." lightbox="media/design-to-retire-define-product-cost.svg":::'

1. Start

    Parallel branches connect to the *Plan to produce* and *Procure to pay* end-to-end processes that each connect to d. *Analyze product costing strategy*.

2. *Design to retire*

    A parallel branch connects to *Introduce new products*, which also connects to 3. *Define product costing*.

3. *Define product costing*

    1. *Define product costing strategy*

        A parallel branch connects to *Manage product pricing*, which connects to *Order to cash*.

    2. *Set costing standards*

        Parallel branches connect to *Order to cash*, *Plan to produce*, *Procure to pay*, and *Inventory to deliver*.

    3. *Maintain costing standards*

        Parallel branches connect to *Plan to produce*, *Procure to pay*, and *Inventory to deliver*.

    4. *Analyze product costing strategy*

4. *Record to report*

    Each of the following end-to-end processes connects to the *Record to report* box:  

    - *Order to cash*  
    - *Plan to produce*  
    - *Procure to pay*  
    - *Inventory to deliver*  

5. End

## Product costing benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the product costing. The following sections outline the key benefits that an organization might monitor and measure for product costing.

### Accurate costing

Dynamics 365 includes powerful tools for accurately calculating product costs based on actual expenses such as materials, labor, and overhead. For example, Dynamics 365 Supply Chain Management includes robust cost calculation features such as BOM and Formula cost roll-ups or calculations for produced items, and the ability to calculate indirect costs or overhead costs for purchased or produced items.

### Real-time and flexible cost information

Dynamics 365 provides real-time cost information, allowing organizations to track costs as they change and adjust pricing and resource allocation accordingly. For example, Dynamics 365 Sales and Field Service includes a product catalog feature that allows you to quickly define the product cost that is tracked on each transaction. When you use the Global Inventory Accounting add-in with Dynamics 365 Supply Chain Management, organizations can analyze costs in multiple currencies or costing methodologies, for example.

### Streamlined processes

Dynamics 365 streamlines the product costing process by automating many of the manual tasks involved in cost calculation and analysis. For example, Dynamics 365 Supply Chain Management includes a costing sheet to analyze the breakdown of costs.

### Improved collaboration

Using Dynamics 365 together with Microsoft Teams and Microsoft 365 provides a centralized platform that enables collaboration between teams involved in the product costing process, including finance, operations, and sales. This improves communication and visibility, leading to better decision-making and more informed cost calculations.

### Enhanced reporting and analysis

Dynamics 365 provides advanced reporting and analytics capabilities that are built with Power BI and the Azure Data Lake that enable organizations to gain insights into their cost structures and identify areas for improvement. For example, the Transportation management module in Dynamics 365 Supply Chain Management allows you to calculate your inbound and outbound freight and handling costs.

## Next steps

If you would like to implement Dynamics 365 solutions to assist with your product costing business processes, you can use the following resources and steps to learn more.

1. [Define product catalog and strategy](design-to-retire-define-product-catalog-strategy-overview.md)  
2. Introduce new products
3. *Define product costing* (the article that you're currently reading)  
4. Manage product pricing
5. Manage product lifecycle

## Related resources

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
- Find definitions of terminology used in content for *product costing* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article, including the following terms:

  - [Cost](glossary.md#cost)  
  - [Cost accounting](glossary.md#cost-accounting)  
  - [Costing methodology](glossary.md#costing-methodology)  
  - [Costing sheet](glossary.md#costing-sheet)  
  - [Costing version](glossary.md#costing-version)  
  - [Overhead costs](glossary.md#overhead-costs)  

## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Accounts payable, Accounts receivable, Administrative, Audit, Engineering, Finance, Operations, Production, Project Management, Purchasing, Sales, Service operations, Transportation,

*Products:* Dynamics 365 Business Central, Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Rachel Profitt](https://linkedin.com/in/rachelprofitt) \| Microsoft FastTrack Solution Architect

Other contributors:

- [Michael Herold](https://linkedin.com/in/maherold) \| Microsoft Principal Consultant

