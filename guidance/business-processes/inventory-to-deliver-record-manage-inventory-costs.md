---
title: Record and manage inventory costs overview for technology implementation
description: Read about the business process area for recording and managing inventory costs in Dynamics 365 implementations.
ms.date: 12/19/2023
ms.topic: conceptual
author: rachel-profitt
ms.author: raprofit
---

# Record and manage inventory costs overview for technology implementation

***Applies to: Dynamics 365 Business Central, Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management***

This article describes how organizations can use Dynamics 365 to record and manage inventory costs in a technology implementation.

The process of recording and managing inventory costs is vital for any business that seeks to maintain its financial health and optimize operations, especially when it implements Dynamics 365 business applications. The process starts with the establishment of clear guidelines for how the organization accounts for costs. This process sets the foundation for consistent and accurate accounting throughout the inventory lifecycle and should be done early in any Dynamics 365 implementation.

> [!NOTE]
> The cost accounting system in Dynamics 365 Finance and Supply Chain Management currently includes three modules: *Cost management*, the *Global Inventory Accounting (GIA)* add-in, and *Cost accounting*. *Cost management* and *GIA* are focused on managerial cost accounting functions, whereas *Cost accounting* is geared toward expense allocation capabilities for financial accounting purposes.

As part of the process of recording and managing inventory costs, you must consider your downstream reporting requirements. A well-structured reporting system enables efficient monitoring and analysis of cost data, and therefore helps in decision-making processes and financial planning. In a Dynamics 365 deployment, this system includes various configurations and setups. For example, if you plan to use the *Cost accounting* module that is available in Dynamics 365 Supply Chain Management, you must define the cost accounting reporting structure and the ledger for cost accounting.

> [!TIP]
> This ledger is separate from the general ledger and provides more granular control and analysis of your costing data. The same is true if you plan to use the *GIA* add-in.

> [!NOTE]
> The integration between the *Cost accounting* and *General ledger* modules hasn't yet been completed. The *Cost accounting* module currently has limited functionality.

The *GIA* add-in enables organizations to define multiple ledgers, so that you can analyze your inventory costs by multiple currencies or costing methodologies. Both features are optional and can be added at any time. However, you should carefully consider how they might affect your reporting and reconciliation process during the early phases of your project. After you complete the basic configuration for *Cost accounting* or *GIA*, you can start to process data for cost accounting and analyze the data to help identify trends, potential cost-saving opportunities, and areas for improvement.

You can also use the *Cost management* module in Dynamics 365 Supply Chain Management to examine individual transaction costs. Therefore, you can gain a granular understanding of how different expenses contribute to the overall financial picture. The solution also offers capabilities to help calculate overheads. Accurate calculation of overhead costs is crucial for understanding the full cost of production and for pricing products competitively. Through advanced features in the *Cost accounting* module, you can use allocation rules to ensure that expenses are appropriately distributed among different cost centers or departments. Therefore, you can help prevent overestimation or underestimation.

Dynamics 365 Supply Chain Management supports several costing methodologies. Examples include periodic methods such as first in, first out (FIFO), last in, first out (LIFO), LIFO date, weighted average, and weighted average date. Other examples include perpetual costing models such as standard costing and moving average. Dynamics 365 provides tools to help you review and adjust the base costs of products throughout the product and service lifecycle. By regularly reviewing and adjusting product base costs, businesses stay competitive and responsive to market fluctuations. By keeping the cost of available inventory items updated, businesses ensure accurate financial reporting and help prevent unexpected cost discrepancies. 

> [!NOTE]
> When you use a periodic costing model, remember that the costs aren't tracked in real time. Therefore, it's critical to finalize the inventory costs to close the loop in inventory cost management. Finalization of costs allows for accurate financial reporting and strategic planning.

These processes are instrumental in ensuring financial accuracy and transparency within an organization, particularly when Dynamics 365 is used. The robust capabilities of Dynamics 365 enable businesses to streamline and automate many of these processes. The result is more efficient and accurate cost management.

When you define these business processes in a Dynamics 365 implementation, it's crucial to plan strategically. Although cost accounting policies should be established early in the implementation, some features, such as cost accounting and global inventory accounting add-ins, can be integrated later. This phased approach enables organizations to adapt and fine-tune their inventory cost management processes as they become more familiar with the system's capabilities and their specific business needs. By embracing Dynamics 365, companies can enjoy a more dynamic and adaptable approach to cost accounting. Therefore, they can enhance their financial stability and decision-making abilities.

## Stakeholders

Many people across the organization should contribute to the decision-making process and design of the *record and manage inventory costs* area. The following list provides examples of such stakeholders:

- **Chief Financial Officer (CFO)**: As the top financial executive, the CFO is crucial in defining cost accounting policies and ensuring alignment with the organization's financial strategy. They provide financial oversight and ensure that cost accounting practices meet regulatory requirements.
- **Controller**: Controllers oversee the day-to-day accounting operations, including cost accounting. They are responsible for defining the cost accounting ledger, implementing reporting structures, and ensuring that cost data is accurate and timely.
- **Supply chain manager**: Supply chain managers are involved in defining cost accounting allocation rules and analyzing transaction costs. They work to optimize the flow of goods and, at the same time, minimize costs. Therefore, their input is invaluable.
- **Product managers**: Product managers have a direct stake in the accuracy of product base costs. They provide insights into product-specific cost considerations, and therefore help in the review and adjustment of base costs.
- **Inventory managers**: Inventory managers are responsible for maintaining the physical inventory and ensuring that costs are accurately reflected in the inventory management system. Their role is vital for adjusting the cost of available inventory items.
- **Cost accountants**: Cost accountants are responsible for processing source data, analyzing cost data, and calculating overheads. They ensure that all cost-related transactions are accurately recorded, analyzed, and allocated.
- **Sales and Marketing teams**: Sales and Marketing teams are stakeholders in the finalization of inventory costs, because they rely on accurate cost data for pricing strategies and profit margin calculations.
- **Compliance officers**: Compliance officers ensure that cost accounting practices adhere to regulatory requirements and internal policies. Therefore, they help reduce the risk of financial noncompliance.

## Record and manage inventory costs process flow 

The following diagram illustrates the *record and manage inventory costs* business process area. [!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/inventory-to-deliver-record-manage-inventory-costs-flow.svg" alt-text="Diagram of business process relationships with upstream and downstream processes that are explained in the next paragraphs." lightbox="media/inventory-to-deliver-record-manage-inventory-costs-flow.svg":::

1. Start

    A parallel branch from the Start branch connects as follows:

    1. *Inventory to deliver*

        1. *Maintain inventory levels*
        2. *Process inbound goods*
        3. *Process outbound goods*

        Each of these business process areas has parallel processes that connect to each of the following processes:

        1. *Process source data for cost accounting*
        2. *Analyze cost transactions*

2. *Design to retire*

    1. *Introduce new products*
    2. *Define product pricing*

3. *Record and manage inventory costs*

    A parallel branch connects from 3. *Record and manage inventory costs* to 4. *Analyze transaction costs*.

    1. *Define cost accounting policies*
    2. *Define cost accounting reporting structure*
    3. *Define cost accounting ledger*
    4. *Process source data for cost accounting*
    5. *Calculate overheads for cost accounting*
    6. *Define cost accounting allocation rules*
    7. *Analyze cost accounting data*

    A parallel branch connects to 6. End.

4. *Analyze transaction costs*

    1. *Adjust available inventory costs*
    2. *Review and adjust product base costs*

5. *Finalize inventory costs*
6. *Record to report*
7. End

## Record and manage inventory costs benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the *record and manage inventory costs* area. The following sections outline the key benefits that an organization might monitor and measure for recording and managing inventory costs. 

### Increase cost accuracy and transparency

Implementation of Dynamics 365 Supply Chain Management enhances cost accuracy and transparency throughout the inventory management process. By streamlining cost accounting, the system reduces the likelihood of human error and provides real-time visibility into cost data. You can dynamically control which transactions are posted to the general ledger when you use Dynamics 365 Finance with Supply Chain Management. The system keeps the inventory subledger in balance with the general ledger in Finance in real time. This benefit enables organizations to make informed decisions, minimize cost discrepancies, and maintain financial accuracy.

### Optimize cost allocation and resource utilization

Dynamics 365 enables organizations to optimize cost allocation and resource utilization. This benefit applies especially to product-centric organizations that use Dynamics 365 Supply Chain Management and service-centric organizations that use Dynamics 365 Project Operations. Through features such as cost accounting allocation rules, the system ensures that indirect costs are accurately distributed. Therefore, it helps reduce waste and improve resource allocation. This optimization helps businesses operate more efficiently, maintain competitiveness, and improve profitability.

### Enhance data-driven decision-making

Dynamics 365 business applications empower organizations to make data-driven decisions by providing comprehensive cost accounting and reporting capabilities. Through accurate, up-to-date data, businesses can analyze transaction costs, review product base costs, and adapt pricing strategies in response to market changes. This benefit results in more strategic, informed decision-making.

### Streamline compliance and audit processes

Dynamics 365 simplifies compliance and audit processes that are related to cost accounting. The system maintains an accurate and auditable record of all cost-related transactions in subledgers. Therefore, it's easier to demonstrate compliance with regulatory requirements. This streamlining not only reduces the risk of noncompliance but also minimizes the effort and time that are required for audits.

### Improve profit margins and competitiveness

Implementation of Dynamics 365 business applications can lead to improved profit margins and increased competitiveness. Organizations that accurately calculate overhead costs, adjust the cost of available inventory items, and review product base costs can better price their products or services. The results are higher profit margins and a stronger position in the market.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *record and manage inventory costs* business processes, you can use the following resources and steps to learn more. (Links will be added later, when the articles are ready.)

1. *Define and manage warehouse operations*

2. *Maintain inventory levels*

3. *Process inbound goods*

4. *Process outbound goods*

5. *Manage inventory quality*

6. [Manage freight and transportation](inventory-to-deliver-manage-freight-transportation.md)

7. *Record and manage inventory costs* (the article that you're currently reading)

## Related resources

You can use the following resources to learn more about the *record and manage inventory costs* processes in Dynamics 365.

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
- Find definitions of terminology that is used in content for inventory costing in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article. For example, this glossary includes the following terms:

    - [Cost](glossary.md#cost)
    - [Cost accounting](glossary.md#cost-accounting)
    - [Costing methodology](glossary.md#costing-methodology)
    - [Costing sheet](glossary.md#costing-sheet)
    - [Costing version](glossary.md#costing-version)
    - [Overhead costs](glossary.md#overhead-costs)

## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Public Administration (91-99)

*Stakeholders:* Audit, Engineering, Finance, Merchandising, Operations, Production, Project Management, Purchasing, Retail store operations, Sales, Transportation, Treasury, Warehouse

*Products:* Dynamics 365 Business Central, Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Rachel Profitt](https://www.linkedin.com/in/rachelprofitt/) | Principal Program Manager Microsoft
