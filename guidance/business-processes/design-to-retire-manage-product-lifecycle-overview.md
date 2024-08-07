---
title: Manage and define product lifecycle overview
description: Learn about the manage product lifecycle business process, including information about the various stakeholders and process flow.
author: rachel-profitt
ms.author: raprofit 
ms.topic: conceptual
ms.date: 02/27/2024
---

# Manage product lifecycle overview

***Applies to: Dynamics 365 Business Central, Dynamics 365 Commerce, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Sales, Dynamics 365 Supply Chain Management***

This article describes how organizations can use Dynamics 365 to manage the product lifecycle of tangible products. This business process area can cover tasks such as the following list:

- Buying
- Selling
- Trading
- Distributing
- Manufacturing
- Consumption in services and maintenance

Management of the product lifecycle within an organization is of paramount importance for businesses that deal with tangible products, whether they are involved in buying, selling, distributing, or manufacturing. Strategic orchestration of the product lifecycle ensures optimal efficiency, cost-effectiveness, and customer satisfaction.

When organizations use Dynamics 365 to maintain product information, the system plays a pivotal role by seamlessly integrating various products, such as Dynamics 365 Customer Service, Sales, Field Service, Project Operations, and Supply Chain Management. This comprehensive integration provides a unified approach and enables organizations to streamline operations, enhance collaboration, and make informed decisions throughout the entire product lifecycle.

The process of managing a product's lifecycle involves several critical business processes, each of which contributes to the overarching success of the data and downstream process. These business processes include analyzing product margins of products that are sold or produced. Many signals can come from upstream processes in the case-to-resolution process. These processes send signals that inventory should be removed, or that item usage should be restricted in sales, procurement, production, or servicing operations.

For organizations that manufacture products, it's critical to ensure that you:

- Define and document clear engineering policies.
- Maintain accurate product versions and details.
- Process the requested changes with rigor to ensure compliance with established policies and regulations.

Furthermore, the capability to seamlessly request, process, and retire a product underscores the agility and adaptability that Dynamics 365 affords.

Dynamics 365 Supply Chain Management includes robust product information management capabilities that seamlessly integrate with other products in the suite. Therefore, organizations can navigate the complexities of the product lifecycle with precision and ensure sustained success and adaptability in the dynamic business landscape.

The business processes for managing the product lifecycle in a Dynamics 365 implementation should be addressed in the early to mid-design and configuration stages of the project.

## Stakeholders

Many people across the organization should contribute to the decision-making process and design of the *manage product lifecycle* business process area. The following list provides examples of such stakeholders:

- **Product management and engineering stakeholders**: Product managers are responsible for overseeing the entire product lifecycle. They collaborate with various teams to ensure alignment with organizational goals. Product engineers should be engaged in defining and maintaining product engineering policies. They play a key role in the design and development phases.
- **Supply chain and inventory management stakeholders**: Supply chain managers should be involved in analyzing product margins, determining inventory removal, and managing the overall supply chain to optimize efficiency. Inventory managers are typically responsible for tracking and controlling the flow of goods within the organization to ensure optimal inventory levels.
- **Quality assurance stakeholders**: These stakeholders include quality assurance specialists. They are involved in testing and validating product changes to ensure that the implemented modifications meet the specified criteria for quality and compliance.
- **Operations stakeholders**: These stakeholders include operations managers. They are responsible for overseeing the day-to-day activities that are related to product manufacturing and distribution, to ensure smooth operations throughout the lifecycle.
- **Finance stakeholders**: These stakeholders include the financial analyst or cost accountants. They are typically involved in analyzing product margins and financial implications of product lifecycle decisions. Therefore, they can provide valuable insights for strategic planning.
- **Compliance and regulatory stakeholders**: These stakeholders include compliance officers. They are typically designated to ensure that all product engineering changes comply with regulatory standards and industry requirements. In this way, they mitigate legal and compliance risks.
- **Customer service stakeholders**: These stakeholders include customer service representatives. They play a crucial role in gathering customer feedback and insights. Therefore, they can provide valuable input into product improvements and changes.

## Manage product lifecycle process flow

The following diagram illustrates the *manage product lifecycle* business process area.
[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media\design-to-retire-manage-product-lifecycle-overview.svg" alt-text="Diagram of the manage product lifecycle business process flow, visualizing the connection between business process areas." lightbox= "media\design-to-retire-manage-product-lifecycle-overview.svg":::



1. Start

    Parallel branches from Start include the following end-to-end processes:

    1. *Case to resolution*, which connects to *Manage product lifecycle*
    1. *Order to cash*, which connects to *Analyze product margins*
    1. *Inventory to deliver*, which has parallel branches that connect to *Determine inventory removal* and *Restrict item use*
    1. *Plan to produce*, which has parallel branches that connect to *Determine inventory removal*, *Restrict item use*, and *Define product engineering policies*
    1. *Source to pay*, which connects to *Define product engineering policies*

1. *Design to retire*

    Parallel branches from *Design to retire* include the following:

    1. *Manage product pricing*, which connects to *Analyze product margins*
    1. *Define product costing*, which connects to *Analyze product margins*

1. *Introduce new products*
1. *Manage product lifecycle*
1. *Analyze product margins*

    Parallel branches from *Analyze product margins* include the *Manage product pricing* and *Define product costing* business process areas that are shown under the *Design to retire* end-to-end process.

1. *Determine removal of inventory*

    Parallel branches from *Determine removal of inventory* include the *Define product catalog and strategy* business process area that is shown under the *Design to retire* end-to-end process, and the *Inventory to deliver* end-to-end process.

1. *Restrict item use*
1. Is manufactured?

    1. The *Yes* branch connects to *Define product engineering policies*.
    1. The *No* branch connects to Is retirement required?

        1. The *Yes* branch connects to *Retire a product*, which connects to End.

            Parallel branches from *Retire a product* include the *Define product catalog and strategy* business process area that is shown under the *Design to retire* end-to-end process, and the *Inventory to deliver* end-to-end process.

        1. The *No* branch connects to *Maintain product versions*.

1. *Define product engineering policies*
1. *Maintain product versions*
1. *Request product engineering changes*
1. *Process product engineering changes*
1. End

Other connections to End that are shown include *Manage product pricing*, *Define product costing*, *Define product catalog and strategy*, and *Inventory to deliver*.

## Manage product lifecycle benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the *manage product lifecycle* business process area. The following sections outline the key benefits that an organization might monitor and measure for managing the product lifecycle.

### Enhanced operational efficiency through streamlined product information management

You can use the **Product information management** (PIM) module in Dynamics 365 Supply Chain Management to efficiently consolidate and manage product data. The centralized repository that it provides for product information helps you reduce data redundancy, minimize errors, and ensure consistency across the entire supply chain. This streamlined approach enhances operational efficiency and helps teams make prompt, informed decisions.

Key performance indicators (KPIs) such as data accuracy rates and time saved in information retrieval underscore the tangible benefits of using Dynamics 365 PIM and contribute to a more agile and responsive organization.

### Agile adaptation to market demands with engineering change management

The **Engineering change management** module in Dynamics 365 Supply Chain Management facilitates quick and effective responses to evolving market demands. Organizations can swiftly initiate and implement engineering changes to ensure that products are aligned with the latest market trends or regulatory requirements.

KPIs such as the speed of change implementation and the reduction in product recall incidents demonstrate the module's effectiveness at enhancing adaptability and minimizing risks that are associated with outdated products.

### Cost optimization through analyzing product margins

The ability to analyze product margins in Dynamics 365 Supply Chain Management or Sales helps organizations make informed decisions about pricing, production, and inventory management. By understanding the profitability of each product, businesses can optimize pricing strategies, identify cost-saving opportunities, and prioritize high-margin products.

KPIs such as gross profit margins and cost-to-revenue ratios provide quantitative measures of the financial benefits that are derived from using Dynamics 365's analytical capabilities for better cost management.

### Efficient inventory management and reduction of holding costs

Dynamics 365 Supply Chain Management facilitates precise inventory management, so that organizations can optimize stock levels and reduce holding costs. The system's features enable real-time tracking of inventory movements to minimize the risk of overstock or stockouts.

KPIs such as inventory turnover rates and holding costs as a percentage of revenue showcase the tangible benefits of maintaining an efficient and cost-effective inventory through Dynamics 365.

### Improved product lifecycle visibility and decision making

Dynamics 365 Supply Chain Management provides comprehensive visibility into the entire product lifecycle to enable informed decision making at every stage. From product design to retirement, organizations can access real-time data and analytics to foster proactive decision making.

KPIs such as decision cycle times and the accuracy of decision outcomes reflect the improved decision-making capabilities that Dynamics 365 facilitates and that contribute to overall organizational agility and competitiveness.

## Next steps

If you would like to implement Dynamics 365 solutions to assist with your *manage product lifecycle* business processes, you can use the following resources and steps to learn more.

1. [Define product catalog and strategy overview](design-to-retire-define-product-catalog-strategy-overview.md)

2. [Introduce new products](design-to-retire-introduce-new-products-overview.md)  

3. [Manage product pricing](design-to-retire-manage-product-pricing-overview.md)  

4. [Define product costing overview](design-to-retire-define-product-costing-overview.md)

5. *Manage product lifecycle* (the article that you're currently reading).

## Related information

You can use the following resources to learn more about the *manage product lifecycle* process in Dynamics 365.

- [Engineering change management overview - Supply Chain Management](/dynamics365/supply-chain/engineering-change-management/product-engineering-overview)
- [Product lifecycle state overview - Supply Chain Management](/dynamics365/supply-chain/pim/product-lifecycle)
- [Engineering Change Management TechTalk Series](https://community.dynamics.com/blogs/post/?postid=a8817f38-7b31-4c2c-a728-05ce505354c7)
- [Create Production BOMs - Business Central](/dynamics365/business-central/production-how-to-create-production-boms)
- [Create Item Cards for Goods or Services - Business Central](/dynamics365/business-central/inventory-how-register-new-items)
- Find definitions of terminology that is used in content for *manage product lifecycle* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article. For example, this glossary includes the following terms:

    - [Batch order](glossary.md#batch-order)
    - [Bill of materials](glossary.md#bill-of-materials)
    - [Co-products and by-products](glossary.md#co-products-and-by-products)
    - [Formula](glossary.md#formula)
    - [Inventory turnover](glossary.md#inventory-turnover)
    - [Product information management](glossary.md#product-information-management-pim)
    - [Recipe management](glossary.md#recipe-management)
    - [Regulatory compliance](glossary.md#regulatory-compliance)
    - [Supply chain visibility](glossary.md#supply-chain-visibility)
    - [Yield](glossary.md#yield)

<!--## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Customer services, Engineering, Finance, Operations, Production, Project Management, Purchasing, Sales, Service operations, Transportation, Warehouse

*Products:* Dynamics 365 Business Central, Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Rachel Profitt](<https://www.linkedin.com/in/rachelprofitt/>) \| Principal Program Manager, Microsoft
