---
title: Introduction to the forecast to plan business processes
description: Get introduced to the forecast to plan end-to-end business process. Learn how Dynamics 365 apps can help organizations optimize their forecast to plan processes.
ms.date: 07/06/2023
ms.topic: conceptual
author: edupont04
ms.author: annekrupke
ms.reviewer: edupont
---

# Introduction to the forecast to plan end-to-end business processes

***Applies to: Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Human Resources, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center***

This article introduces the *forecast to plan* end-to-end business process. It outlines how Dynamics 365 apps can help organizations manage and optimize their *forecast to plan* processes. This end-to-end business process has the number *50* in the business process catalog. Learn more at [About the business process catalog for Dynamics 365 apps](about.md).

## Forecast to plan overview

The term *forecast to plan* typically describes a collection of business processes that an organization implements to estimate demand and determine how much supply is required to meet those demands. The term *forecast* means a prediction of future events, typically sales. The *plan* is the organization's articulation and refinement of the forecast to determine exactly what to buy and produce.  

> [!NOTE]
> For the purposes of this article and related articles for the *forecast to plan* business process, we are primarily focused on forecasting and planning of products and services, as opposed to general ledger budgeting and financial planning.

The *forecast to plan* business process is typically part of an organization's larger efforts to buy and sell products or services. It's deeply related to all of the other end-to-end business processes that inform the forecasting and planning strategies. And then the execution of the plan supports the completion of the other operational processes. The upstream or downstream relationship of the *forecast to plan* business process to the other business processes is highly dependent on the operational strategies of the business. Learn more at [Solution architecture design: Vision and strategies](../implementation-guide/solution-architecture-design-pillars-vision-strategies.md).  

For example, in a make to order environment, the *forecast to plan* process is a downstream process from *forecast to plan*. While in a make to stock environment, it's an upstream process. Organizations may also use multiple operational strategies, which is fully supported in Microsoft business apps.  

The high-level strategy for *forecast to plan* processes should be planned at the early phases of a larger ERP implementation. The design and decisions made about this process have an impact on downstream processes including integrations, data that must be migrated, and so on. If your organization doesn't have a forecasting or planning process, or the *forecast to plan* approach is out of scope for early phases of your project, add *forecast to plan* business processes into your design later.

> [!IMPORTANT]
> The process defined here does not include the details for forecasting and planning financials including cash flow forecast. Learn more at [Record to report introduction](record-to-report-introduction.md).
>
> The process defined here also does not include the details for forecasting and planning human resources. Learn more at [Hire to retire introduction](hire-to-retire-introduction.md).

Every organization has variations to the *forecast to plan* processes. In this article, we define the basic benefits and outcomes for any organization looking to implement a technology solution to support the *forecast to plan* process.

## Impact on the organization

Forecasting is critical in any organization because it helps to provide visibility into expected demand and supply in order to make informed business decisions and run operational strategies. The planning activities in the *forecast to plan* process allow organizations to standardize and automate the replenishment of inventory across their manufacturing and distribution networks.

Dynamics 365 can support your *forecast to plan* business process by being flexible to allow your organization to grow and adjust as both the market and supply chain evolve. Having a periodic review of your *forecast to plan* business processes can ensure that your technology aligns with your business goals and objectives.

## Stakeholders

Many people in an organization will need to contribute to the decision-making process and design of the forecast-to-plan business processes in your Dynamics 365 project. The list of stakeholders includes, but isn't limited to the following list:

- Planning stakeholders – examples: COO, VP of operations, Operations Manager, Planning manager

- Procurement stakeholders – examples: Director of procurement, Buyer, Purchase agent, Purchasing manager

- Sales stakeholders – examples: VP of sales, Sales Directors, General Managers

- Production stakeholders – examples: Production manager, Production scheduler

- Inventory stakeholders – examples: Warehouse manager, Transportation manager

## Forecast to plan benefits

When your organization plans to implement Dynamics 365 to assist with the *forecast to plan process*, there are several benefits the solution can help provide. These key benefits should be used to determine if the solution is a good fit for your business and to drive the specific business requirements for implementing the solution. These benefits can also be used to create a baseline measurement for your goals and objectives for the project so that you can measure the success of implementing solutions to meet those business requirements.

### Prevent product stock outs

Dynamics 365 can help organizations prevent stock outs by providing real-time visibility into inventory levels, demand forecasts, and supply chain risks. Here are some ways in which Dynamics 365 can help prevent stock outs:

- Demand Forecasting

  Dynamics 365 Supply Chain Management can analyze historical data and trends using Azure Machine Learning to automatically generate a demand forecast. This capability helps organizations to make planning decisions that ensure inventory is on-hand when it's needed for production, sales, or transfer activities.

- Inventory Management  

  With Dynamics 365 Supply Chain Management, organizations manage their inventory levels effectively by setting up minimum, reorder point, and maximum stock levels. This setup helps make sure that replenishment supply is triggered in time to meet expected demand. It also supports prioritization of replenishment based on the likelihood of stocking out.

- Supply Chain Visibility  

  Microsoft Supply Chain Center provides real-time visibility into the entire supply chain, enabling organizations to monitor supplier performance and respond to any issues that may impact inventory levels. It also supports deeper vendor and customer collaboration and transfer of information.

- Automated Replenishment  

  Dynamics 365 Commerce and Dynamics 365 Supply Chain Management can automate the replenishment process by generating replenishment orders and sending them to suppliers when inventory levels fall below the minimum threshold. This helps to ensure optimal inventory levels.

- Collaboration and Communication  

  Together applications such as Microsoft 365, Microsoft Teams, and Dynamics 365 provide collaboration and communication tools that enable organizations to communicate with suppliers and other stakeholders in real-time. This helps to ensure that everyone is on the same page and can respond quickly to any issues that may impact inventory levels.

Overall, Dynamics 365 can help organizations prevent stock outs by providing real-time visibility into inventory levels, demand forecasts, and supplier information, enabling organizations to optimize their inventory levels and respond quickly to any issues that may impact inventory levels.

### Reduce on-hand inventory carrying costs

Dynamics 365 can help organizations reduce on hand inventory carrying costs by minimizing excess inventory while still protecting the business from running out. Reducing on hand inventory is important in any organization because it can lead to lower costs, improved cash flow, and improved efficiency. Holding excess inventory can be expensive, as it requires more space for storage, increases the risk of inventory obsolescence, and ties up capital that could be used for other purposes.

### Reduce customer lead times and increase delivery date accuracy

Implementing technology solutions like Dynamics 365 can help organizations reduce customer lead times by improving collaboration with suppliers, providing real-time visibility into order status and production schedules, automating order processing, and enabling more accurate demand forecasting. By streamlining their supply chain processes and improving their ability to respond quickly to customer demand, organizations can reduce customer lead times and improve their overall competitiveness.

Dynamics 365 can increase accuracy of customer order delivery dates by using the end-to-end supply chain data along with the business's replenishment strategy to quickly calculate a realistic fulfillment lead time. It also considers required ship dates to prioritize downstream processes like production and procurement. This allows organization to improve their ability to deliver products to their customers on time, improving customer satisfaction and loyalty, and in many cases preventing penalties due to exceeding a service-level agreement.

### Optimize operations

Dynamics 365 can help optimize the use of production resources by providing real-time visibility into inventory levels, demand forecasting, and production capacity. By using this data, organizations can optimize their production schedules, ensuring that resources are used efficiently and that production runs are scheduled to meet customer demand. Additionally, Dynamic 365 Supply Chain Management supports the production scheduling process, considering factors such as lead times, machine capacity, and labor availability to create optimal production schedules. This enables organizations to reduce downtime, increase throughput, and improve overall efficiency, all while ensuring that customer demand is met in a timely and cost-effective manner.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *forecast to plan* business processes, use the following resources and steps to learn more.

1. Define the goals and objectives of implementing a *forecast to plan* technology solution. Learn more at [Implementation strategy](../implementation-guide/implementation-strategy.md).

2. Define the business process scope of your project. Learn more at [Process-focused solution](../implementation-guide/process-focused-solution.md).

3. Request a demo or get a free trial of Dynamics 365 solutions for the *forecast to plan* process. Learn more at [Request a demo](https://dynamics.microsoft.com/dynamics-365-free-trial/).

4. Get an overview of the *forecast to plan* process. Learn more at [Forecast to plan overview](forecast-to-plan-overview.md).

## Related information

Use the following resources to learn more about the *forecast to plan process* in Dynamics 365.

- [Master planning in Dynamics 365 Supply Chain Management](/training/paths/master-planning-supply-chain-management/)

- [TechTalk: Demand Driven Material Requirements Planning in Dynamics 365 Supply Chain Management](https://community.dynamics.com/blogs/post/?postid=72ceafd4-72c4-4921-81f1-8535076d7be6)

- [TechTalk: Priority based planning in Dynamics 365 Supply Chain Management](https://community.dynamics.com/blogs/post/?postid=dcde88fa-9009-4adc-a2a6-514dd6a43bc9)

- [TechTalk Series: Planning Optimization](https://community.dynamics.com/blogs/post/?postid=c5f1bffe-a521-4904-aa69-4e40f7336fd7)

- [TechTalk Series: Demand Forecasting with Azure Machine Learning](https://community.dynamics.com/blogs/post/?postid=be5e2cbb-373f-4167-9e57-8ccb97f97b84)

<!--## Tags
*Stakeholders:* Functional consultant, Business analyst, Planning stakeholders, Procurement stakeholders, Sales stakeholders, Production stakeholders, Inventory stakeholders

*Products:* Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Human Resources, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center
