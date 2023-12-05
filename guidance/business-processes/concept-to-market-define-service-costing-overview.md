---
title: Define service costing overview
description: Learn how you can use Dynamics 365 products to support your organization's business processes to set the cost of the services that you sell.
ms.date: 11/24/2023
ms.topic: conceptual
author: rachel-profitt
ms.author: raprofit
---

# Define service costing overview

***Applies to: Dynamics 365 Business Central, Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center***

This article describes the business process for defining the cost of services and how that process relates to other business processes with Microsoft Business Applications.

Defining service costs is essential for any organization that wants to understand and manage its finances effectively. The purpose of determining the costs of services is to know the amount of money that goes into staffing or outsourcing a particular service and delivering that item to the customer. This information is crucial for setting prices, making informed decisions about resource allocation, and evaluating the financial performance of the business.

Here are some of the key reasons why defining service costs is important:

- **Pricing**: Knowing the costs of delivering a service helps organizations to set prices that are appropriate and profitable. Without an understanding of costs, it can be difficult to determine a fair price that will cover expenses and generate a profit.

- **Profitability**: By calculating the costs associated with delivering services, organizations can determine whether they are making a profit or not. This information is crucial for assessing the financial health of the business and identifying areas where improvements can be made.

- **Resource Allocation**: Knowing the costs of delivering or outsourcing services helps organizations to allocate their resources more effectively. By understanding the costs involved, businesses can make decisions about how to allocate resources such as labor, materials, and equipment.

- **Cost Reduction**: Understanding the costs of delivering or outsourcing services can also help organizations identify areas where costs can be reduced. By identifying areas where expenses can be reduced without compromising quality, businesses can become more efficient and improve their bottom line.

Overall, defining service costs is essential for any organization that wants to operate efficiently, remain competitive, and generate a healthy profit. By having a clear understanding of costs, businesses can make informed decisions about pricing, resource allocation, and cost reduction, which can ultimately lead to greater success and profitability.

Microsoft's business applications include tools to help support organizations define service costs to track, report, and analyze the profitability, margins, and more. For example, Dynamics 365 Sales and Field Service includes a product catalog feature that allow you to quickly define the cost that is tracked on each transaction. Dynamics 365 Supply Chain Management supports the calculation of indirect costs, sometimes referred to as overhead costs, for purchased or produced items, and a costing sheet to analyze the breakdown of costs. These are just a few examples of how Dynamics 365 can support your costing business requirements.

## Stakeholders

There are several stakeholders in an organization that should be involved in defining service costs, as the process can have a significant impact on the overall success of the business. Here are some of the stakeholders who should be involved:

- **Finance and accounting stakeholders**: The finance and accounting teams are responsible for managing the financial health of the organization. They should be involved in defining service costs as they have the expertise to analyze costs and identify areas where expenses can be reduced.

- **Operations stakeholders**: The operations teams are responsible for delivery and outsourcing of services. This could include project management teams in project-based organizations. It may also include the procurement teams responsible for outsourcing resources for services. They should be involved in defining service costs as they have first-hand knowledge of the processes and resources required to procure, produce, and deliver the services.

- **Sales and marketing stakeholder**: The sales and marketing teams are responsible for pricing and promoting services to customers. They should be involved in defining service costs as they need to understand the costs associated with the services to set prices and develop marketing strategies.

- **Senior management**: Senior management should be involved in defining service costs as they are responsible for making strategic decisions that affect the overall direction of the organization. They need to understand the costs associated with services to make informed decisions about resource allocation and pricing strategies.

- **Customers**: While customers are not directly involved in defining service costs, they are important stakeholders who can provide valuable feedback on pricing and product quality. Understanding the costs associated with services can help organizations make pricing decisions that are fair and competitive while meeting the needs of their customers.

Overall, it is important to involve all stakeholders who have a vested interest in the success of the organization when defining service costs. By working together to analyze costs and identify areas for improvement, organizations can make informed decisions that drive growth and profitability.

## Define service costing process flow 

The following diagram illustrates the define *service costing* business process area.

[!INCLUDE [daf-business-process-flow-def](../includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/concept-to-market-define-service-costing-flow.svg" alt-text="Flow diagram with steps for the process that is explained further in the next paragraphs.":::

1. Start

    Parallel branches connect to [Procure to pay](procure-to-pay-overview.md) processes that each connect to c. *Analyze costing strategy*.

2. [Concept to market](concept-to-market-overview.md)

    A parallel branch connects to *Introduce new services*, which also connects to 3. *Define service costing*.

3. *Define service costing*

    1. *Define service costing strategy*

        A parallel branch connects to *Manage services prices*, which connects to [Service to cash](service-to-cash-overview.md) and [Order to cash](order-to-cash-overview.md).

    2. *Maintain service costs*

        Parallel branches connect to *Order to cash* and *Procure to pay*.

    3. *Analyze service costs*

4. [Record to report](record-to-report-overview.md)

    Each of the following downstream end-to-end processes connect to the *Record to report* box: *Service to cash*, *Order to cash*, and *Procure to pay*.

5. End

## Define service cost benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the *define service costing* processes. The following sections outline the key benefits that an organization might monitor and measure for *defining service costing*.

### Accurate costing

Dynamics 365 includes powerful tools for accurately defining service offering costs. For example, costing versions can be used to keep historical costs, and you can future date costs to improve business process efficiency.

### Real-time and flexible cost information

Dynamics 365 provides real-time cost information, allowing organizations to track costs as they change and adjust pricing and resource allocation accordingly. For example, Dynamics 365 Sales and Field Service includes a product catalog feature that allows you to quickly define the product cost that is tracked on each transaction.

### Streamlined processes

Dynamics 365 streamlines the service costing process by automating many of the manual tasks involved in cost calculation and analysis. For example, Dynamics 365 Supply Chain Management includes a costing sheet to analyze the breakdown of costs.

### Improved collaboration

When you use Dynamics 365 with Microsoft Teams, you get a centralized platform that supports collaboration between teams involved in the service costing process, including finance, operations, and sales. This improves communication and visibility, leading to better decision-making and more informed cost calculations.

### Enhanced reporting and analysis

Dynamics 365 provides advanced reporting and analytics capabilities that are built with Power BI and the Azure Data Lake that enable organizations to gain insights into their cost structures and identify areas for improvement.

## Next steps

If you would like to implement Dynamics 365 solutions to assist with your service costing business processes, you can use the following resources and steps to learn more. (Links will be added later, when the articles are ready.)

1. [Define service offerings and strategy](concept-to-market-define-service-offerings-strategy-overview.md)  

2. *Define service costing* (the article you're currently reading)  

3. Manage service pricing

4. Manage service lifecycle

## Related resources

You can use the following resources to learn more about the service costing process in Dynamics 365.

- [Service Management - Business Central](/dynamics365/business-central/service-service)  
- [Cost management home page - Supply Chain Management](/dynamics365/supply-chain/cost-management/cost-management-home-page)
- [Cost accounting home page - Finance](/dynamics365/finance/cost-accounting/cost-accounting-home-page?context=%2Fdynamics365%2Fcontext%2Fsupply-chain)
- [Work with the costing sheet in Dynamics 365 Supply Chain Management](/training/modules/work-costing-sheet-dyn365-supply-chain-mgmt/)
- [Get started with cost accounting in Dynamics 365 Finance](/training/modules/get-started-cost-accounting-dyn365-finance/)
- [Get started with cost accounting for supply chains in Dynamics 365 Finance](/training/paths/get-started-cost-accounting-supply-chains-dyn365-finance/)
- [Use cost accounting in Microsoft Dynamics 365 Business Central](/training/paths/use-cost-accounting-dynamics-365-business-central/)
- [Cost Accounting Series - Microsoft Dynamics Blog](https://community.dynamics.com/blogs/post/?postid=9f267e7f-a1a3-4d29-8f0f-f755c22c4ca5)
- [Inventory Costing in Dynamics 365 Supply Chain Management TechTalk Series - Microsoft Dynamics Blog](https://community.dynamics.com/blogs/post/?postid=a1955d50-c26c-4563-b42c-b1af2261ae6f)

## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Accounts payable, Accounts receivable, Administrative, Audit, Engineering, Finance, Operations, Production, Project Management, Purchasing, Sales, Service operations, Transportation,

*Products:* Dynamics 365 Business Central, Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Rachel Profitt](https://linkedin.com/in/rachelprofitt) \| Microsoft FastTrack Solution Architect

Other contributors:

- [Michael Herold](https://linkedin.com/in/maherold) \| Microsoft Dynamics Principal Consultant

