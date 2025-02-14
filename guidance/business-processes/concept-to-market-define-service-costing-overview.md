---
title: Overview of the Define service costing business process area
description: Learn how you can use Dynamics 365 products to support your organization's business processes to set the cost of the services that you sell.
ms.date: 11/24/2023
ms.topic: conceptual
author: rachel-profitt
ms.author: raprofit
---

# Overview of the Define service costing business process area within the Concept to market end-to-end scenario

***Applies to: Dynamics 365 Business Central, Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center***

This article describes the business process for defining the cost of services. It also explains how that process is related to other business processes in Microsoft business applications.

The definition of service costs is essential for any organization that wants to understand and effectively manage its finances. The goal is to know the amount of money that goes into staffing or outsourcing a particular service and delivering it to the customer. This information is crucial for setting prices, making informed decisions about resource allocation, and evaluating the financial performance of the business.

Here are some of the key reasons why the definition of service costs is important:

- **Pricing**: An understanding of the costs of delivering a service helps organizations set prices that are appropriate and profitable. If the costs aren't understood, it can be difficult to determine a fair price that covers expenses and generates a profit.
- **Profitability**: By calculating the costs that are associated with delivering services, organizations can determine whether they are making a profit. This information is crucial for assessing the financial health of the business and identifying areas for improvement.
- **Resource allocation**: An understanding of the costs of delivering or outsourcing services helps organizations more effectively allocate their resources. By understanding the costs that are involved, businesses can make decisions about how to allocate resources such as labor, materials, and equipment.
- **Cost reduction**: An understanding of the costs of delivering or outsourcing services can help organizations identify areas where costs can be reduced. If expenses can be reduced in any areas without compromising quality, businesses can become more efficient and improve their bottom line.

Overall, the definition of service costs is essential for any organization that wants to operate efficiently, remain competitive, and generate a healthy profit. By having a clear understanding of costs, businesses can make informed decisions about pricing, resource allocation, and cost reduction. Therefore, they can ultimately achieve greater success and profitability.

Microsoft business applications include tools to help support organizations as they define service costs to track, report, and analyze profitability, margins, and more. Here are just a few examples that show how Dynamics 365 can support your costing business requirements:

- Dynamics 365 Sales and Field Service include a product catalog feature that helps you quickly define the cost that is tracked on each transaction.
- Dynamics 365 Supply Chain Management supports the calculation of indirect costs (sometimes referred to as overhead costs) for purchased or produced items. It also supports a costing sheet that you can use to analyze the breakdown of costs. 

## Stakeholders

There are several stakeholders in an organization that should be involved in defining service costs, because the process can have a significant impact on the overall success of the business. Here are some of the stakeholders who should be involved:

- **Finance and accounting stakeholders**: The finance and accounting teams are responsible for managing the financial health of the organization. They should be involved in defining service costs because they have the expertise to analyze costs and identify areas where expenses can be reduced.
- **Operations stakeholders**: The operations teams are responsible for delivering and outsourcing services. In project-based organizations, these stakeholders might include project management teams. They might also include the procurement teams that are responsible for outsourcing resources for services. These teams should be involved in defining service costs because they have first-hand knowledge of the processes and resources that are required to procure, produce, and deliver the services.
- **Sales and marketing stakeholder**: The sales and marketing teams are responsible for pricing services and promoting them to customers. They should be involved in defining service costs because they must understand the costs that are associated with the services, so that they can set prices and develop marketing strategies.
- **Senior management**: Members of senior management should be involved in defining service costs because they are responsible for making strategic decisions that affect the overall direction of the organization. They must understand the costs that are associated with services, so that they can make informed decisions about resource allocation and pricing strategies.
- **Customers**: Although customers aren't directly involved in defining service costs, they are important stakeholders who can provide valuable feedback about pricing and product quality. An understanding of the costs that are associated with services can help organizations make pricing decisions that are fair and competitive, but also meet the needs of their customers.

Overall, when service costs are defined, it's important to involve all stakeholders who have a vested interest in the success of the organization. By working together to analyze costs and identify areas for improvement, organizations can make informed decisions that drive growth and profitability.

## Define service costing process flow

The following diagram illustrates the *define service costing* business process area.

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/concept-to-market-define-service-costing-flow.svg" alt-text="Flow diagram with steps for the process that is explained further in the next paragraphs." lightbox="media/concept-to-market-define-service-costing-flow.svg":::

1. Start

    Parallel branches connect to [Source to pay](source-to-pay-overview.md) processes, each of which connects to c. *Analyze costing strategy*.

1. [Concept to market](concept-to-market-overview.md)

    A parallel branch connects to *Introduce new services*, which also connects to 3. *Define service costing*.

1. *Define service costing*

    1. *Define service costing strategy*

        A parallel branch connects to *Manage services prices*, which connects to [Service to cash](service-to-cash-overview.md) and [Order to cash](order-to-cash-overview.md).

    1. *Maintain service costs*

        Parallel branches connect to *Order to cash* and *Source to pay*.

    1. *Analyze service costs*

1. [Record to report](record-to-report-overview.md)

    Each of the following downstream end-to-end processes connects to the *Record to report* box: *Service to cash*, *Order to cash*, and *Source to pay*.

1. End

## Define service cost benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the *define service costing* processes. The following sections outline the key benefits that an organization might monitor and measure for *define service costing*.

### Accurate costing

Dynamics 365 includes powerful tools for accurately defining service offering costs. For example, costing versions can be used to keep historical costs, and you can future-date costs to improve business process efficiency.

### Real-time and flexible cost information

Dynamics 365 provides real-time cost information, so that organizations can track costs as they change and adjust pricing and resource allocation accordingly. For example, Dynamics 365 Sales and Field Service include a product catalog feature that helps you quickly define the product cost that is tracked on each transaction.

### Streamlined processes

Dynamics 365 streamlines the service costing process by automating many of the manual tasks that are involved in cost calculation and analysis. For example, Dynamics 365 Supply Chain Management includes a costing sheet that you can use to analyze the breakdown of costs.

### Improved collaboration

By using Dynamics 365 with Microsoft Teams, you get a centralized platform that supports collaboration among the various teams that are involved in the service costing process, including finance, operations, and sales. This collaboration improves communication and visibility, and therefore leads to better decision-making and more informed cost calculations.

### Enhanced reporting and analysis

Dynamics 365 provides advanced reporting and analytics capabilities that are built with Power BI and Azure Data Lake. Organizations can use these capabilities to gain insights into their cost structures and identify areas for improvement.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your service costing business processes, you can use the following resources and steps to learn more. (Links are added, when the articles are ready.)

1. [Define service offerings and strategy](concept-to-market-define-service-offerings-strategy-overview.md)

2. *Define service costing* (the article that you're currently reading)

3. Manage service pricing

4. Manage service lifecycle

## Related information

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

<!-- ## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Accounts payable, Accounts receivable, Administrative, Audit, Engineering, Finance, Operations, Production, Project Management, Purchasing, Sales, Service operations, Transportation

*Products:* Dynamics 365 Business Central, Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Rachel Profitt](https://linkedin.com/in/rachelprofitt) \| Microsoft FastTrack Solution Architect

Other contributors:

- [Michael Herold](https://linkedin.com/in/maherold) \| Microsoft Dynamics Principal Consultant
