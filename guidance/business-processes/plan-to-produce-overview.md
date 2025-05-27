---
title: Overview of the Plan to produce end-to-end business process
description: Read about how Dynamics 365 supports the plan to produce business process, including an overview on the plan to produce process relationship.
ms.date: 02/06/2025
ms.topic: concept-article
author: edupont04
ms.author: annekrupke
ms.reviewer: edupont
---

# Overview of the Plan to produce business process flow and its relationship to other processes

***Applies to: Dynamics 365 Finance, Dynamics 365 Guides, Dynamics 365 Human Resources, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management, Dynamics 365 Business Central, Power Apps, Power BI, Power Automate***

This article describes the *plan to produce* end-to-end business process flow and its relationship to other business processes that can be used within Dynamics 365.

> [!IMPORTANT]
> [!INCLUDE [bus-proc-cat-pending](../includes/bus-proc-cat-pending.md)]

## Plan to produce process relationship

The following diagram shows the relationship of other processes and products/features for the *plan to produce* process. [!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/plan-to-produce-process.svg" alt-text="Business process relationships with upstream and downstream processes that are explained in the next paragraphs." lightbox="media/plan-to-produce-process.svg":::

The upstream processes for the *plan to produce* process include the following list:

- **Acquire to dispose**  

  One of the types of assets that are managed in the *acquire to dispose* process is production equipment, which is then used as part of the *plan to produce* process.

- **Design to retire**  

  The *design to retire* process is used to define what the organization produces, and how it produces those products.

- **Forecast to plan**  

  In certain operational strategies, such as make-to-stock, you create the forecast to then create the production plan. Organizations also use the planning process to create the initial production schedule.

- **Hire to retire**  

  The *hire to retire* process includes labor planning, which defines the capacity for production operations, and the hiring process is run in order to staff human resources for production.

- **Inventory to deliver**  

  The *inventory to deliver* business process manages movement of materials before production, including the movement of materials to the production input location.

- **Order to cash**  

  In make-to-order and similar operational strategies, sales orders are the trigger to begin planning for production.

- **Source to pay**  

  Organizations need to procure materials for use in production before the production process beginning.

- **Project to profit**  

  For job shop manufacturing or engineer-to-order operational strategies, projects define the scope and activities that drive the production process.

- **Prospect to quote**  

  Engineering-to-order scenarios define the parameters and design for products through the quotation process that is then followed by the *plan to produce* process.

- **Record to report**  

 Organizations must set up the chart of accounts, costing sheet, and overhead policies along with other financial configurations before they can start tracking estimated and actual costs in production.

The second column in the diagram displays the business process areas, which are:

- Define production strategies

- Plan production operations

- Run production operations

- Outsource production orders

- Control production quality

- Track production costs

For more information on the business process areas, see [Plan to produce business process areas](plan-to-produce-areas.md).  

The third column in the diagram displays the downstream business process including the following list:

- **Acquire to dispose**  

  Production equipment is tracked and maintained as part of the *acquire to dispose* business process.

- **Case to resolution**  

  The *case to* resolution process can include reporting issues and investigating production process, as well as identifying and implementing continuous improvements.

- **Forecast to plan**  

  Based on real-time production feedback, organizations update and rearrange their plans.

- **Hire to retire**  

  Based on production needs, organizations update labor schedules in the *hire to retire* process, and sometimes executing payroll based on piece work or hours.

- **Inventory to deliver**  

  Once the production process is completed, the *inventory to* deliver process is used to manage the movement of finished goods.

- **Order to cash**  

  In make-to-stock operational strategies, orders are placed for finished goods after production is completed and the inventory is on-hand.

- **Source to pay**  

  Organizations can subcontract work during or after the production process. They can also procure materials that the production process depleted.

- **Design to retire**  

  Products are often updated based on engineering changes or operator feedback from the production cycle. Initial production cycles in particular can be used to complete research and development activities for products.

- **Project to profit**  

  In projects-based manufacturing modes, organizations update the project status based on production activities.

- **Record to report**  

  When production is completed, organizations record production costs and analyze behaviors.

- **Service to cash**  

  Often, organizations perform aftermarket repairs on produced items.

## Featured capabilities

There are product-specific capabilities that interact with the *plan to produce* to process including, but not limited to, the following list:

- **Shop floor execution**  

  The touch-screen optimized *production floor execution* interface in Dynamics 365 Supply Chain Management helps organizations can track the progress of shop floor activities, request maintenance on production equipment, and track operator time registrations.

- **Visual scheduling**  

  The Dynamics 365 Supply Chain Management production module includes *Gantt chart* and *lean visual scheduling capabilities*. With these capabilities, organizations can graphically view the production schedule, including operation sequences, material availability, resource capacity, and delivery date warnings.

- **Mixed mode manufacturing**  

  Dynamics 365 Supply Chain Management supports four different modes of manufacturing:  

  - Discrete  
  - Process  
  - Lean  
  - Projects-based  

  Companies can mix and match these different manufacturing modes as needed based on their business requirements.

- **Engineering change management**  

  For manufacturing companies or organizations that need tighter control of the onboarding and management of product information, the engineering change management module helps model the workflow and data validation of setting up and maintaining products, BOMs, Formulas, and Routes, and other engineering information.

- **Internet of Things (IoT) device connectivity**  

  With Dynamics 365 Sensor Data Intelligence, manufacturers can use IoT devices to provide real-time signals to production managers about shop floor performance, machine breakdowns, and product quality.

- **Warehouse mobile device**  

  Organizations can use the warehouse management mobile application in Dynamics 365 Supply Chain Management to pick raw materials and put away finished goods. The advanced warehousing functionality also supports intelligent replenishment within the warehouse and full batch and serial tracking in inventory movement.

- **Maintenance management**  

  The *Asset management* module in Dynamics 365 Supply Chain Management can be used to run preventive, corrective, and predictive maintenance on production equipment and other assets. It includes a mobile app where users can request maintenance and review and update work orders on the fly.

- **Mixed reality**  

  Dynamics 365 Guides supports mixed reality instructions to be included in production shop floor operations, which can help train users on how to make products or repair machines.

- **Quality management**  

  Use the quality management functionality in Dynamics 365 Supply Chain Management to define the quality tests to perform, validate results, perform corrective action and nonconformance reporting. It also supports the inventory management aspects of quality control such as quarantining materials, recognizing destructive quality tests, and selecting sample quantities from various transactions.

- **Subcontracting**  

  With Dynamics 365 Supply Chain Management, businesses can easily track and automate subcontracting activities such as purchase order generation, transfers of work in progress materials to vendors, and receipt of goods.

- **Lot and serial number control**  

  Raw materials, work in progress items, and finished goods can all be lot (batch) and/or serial tracked in Dynamics 365 Supply Chain Management, providing your organization full traceability into your production process and beyond. It also supports tracking the shelf life of dates of batches and ensuring a first-expired, first-out inventory policy.

## Plan to produce business process flow

The following diagram shows the high-level flow of the *plan to produce* business process. [!INCLUDE [daf-business-process-e2e-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-e2e-flow-def.md)]

:::image type="content" source="media/plan-to-produce-flow.svg"  lightbox="media/plan-to-produce-flow.svg" alt-text="Flow diagram for the end-to-end business process, which is explained in the paragraphs after the image.":::

The following steps are illustrated in the order to cash end-to-end business process flow diagram.

1. Start

2. *Plan to produce* end-to-end process

    1. Define production strategies

    2. Plan production operations

        Parallel branches from this subprocess are *acquire to dispose* and *Source to pay*.

    3. Run production operations

        Parallel branches from this subprocess are e. Control production quality, *forecast to plan*, *inventory to deliver*, and *project to profit*. *Inventory to deliver* has a downstream process to *order to cash* that connects to *service to cash*.

    4. Outsource production orders

        Not shown on the diagram: Outsource production orders can connect to *Source to pay*.

    5. Control production quality

        Parallel branch from this subprocess is *case to resolution*.

    6. Track production costs

3. *Record to report*

4. End

Parallel branches from Start include the following list:

1. *Design to retire* connects to a. *Define production strategies*

2. *Prospect to quote* connect to parallel branches of 5. *Design to retire*, a. *Define production strategies*, and 7. *Project to Profit*

3. *Project to profit* connects to b. Plan production operations

4. *Hire to retire* connects to b. Plan production operations and c. Run production operations

5. *Inventory to deliver* connects to c. Run production operations

6. *Source to pay* connects to c. Run production operations and d. Outsource production orders

7. *Forecast to plan* connects to 10. *Source to pay* and c. Run production operations

8. *Order to cash* connects to 11. *Forecast to plan* and b. Plan production operations

9. *Acquire to dispose* connects to c. Run production operations

10. *Record to report* connects to f. Track production costs

The following end-to-end downstream processes have connections to End:  

- *Acquire to dispose*  
- *Source to pay*  
- *Forecast to plan*  
- *Order to cash*  
- *Service to cash*  
- *Project to profit*  
- *Case to resolution*  

## Next steps

If you want to implement Dynamics 365 solutions to help with your *track production costs* business processes, use the following resources and steps to learn more.

1. *Define product costing overview* (the article that you're currently reading)

2. [Define production strategies](plan-to-produce-define-production-strategies.md)

3. [Plan production operations](plan-to-produce-plan-production-operations-overview.md)

4. [Run production operations overview](plan-to-produce-execute-production-operations-overview.md)

5. [Outsource production operations](plan-to-produce-track-production-costs-overview.md)

6. [Control production quality](plan-to-produce-control-production-quality-overview.md)

7. [Track production costs](plan-to-produce-track-production-costs-overview.md)

Return to the overview of business process areas at [Plan to produce business process areas](plan-to-produce-areas.md).

## Learn more

If you want to implement Dynamics 365 solutions to assist with your *plan to produce* business processes, use the following resources and steps to learn more.

- Define the goals and objectives of implementing a *plan to produce* technology solution. Learn more at [Implementation strategy](../implementation-guide/implementation-strategy.md).

- Define the business process scope of your project. Learn more at [Process-focused solution](../implementation-guide/process-focused-solution.md).

- Request a demo or get a free trial of Dynamics 365 solutions for the *plan to produce* process. Learn more at [Request a demo](https://www.microsoft.com/dynamics-365/free-trial).

- Learn more about the Power Platform products at [Business Application Platform](https://powerplatform.microsoft.com/)

- Get an overview of the *plan to produce* process. Learn more at [Plan to produce overview](plan-to-produce-overview.md).

## Related information

Use the following resources to learn more about the *plan to produce* process in Dynamics 365.

- TechTalk series on the *plan to produce* process: [Production control in Dynamics 365 Supply Chain Management](https://community.dynamics.com/blogs/post/?postid=5d421c52-1fb7-46b5-ae52-93db574cf3f6)

- TechTalk on Manufacturing Accounting: [Part 4: Manufacturing Accounting in Dynamics 365 Supply Chain Management](https://community.dynamics.com/blogs/post/?postid=3e44201b-72e9-4db2-99bb-13e03b3514ae)

- TechTalk on Production Variance Analysis: [Part 7: Production Variance Analysis in Dynamics 365 Supply Chain Management](https://community.dynamics.com/blogs/post/?postid=e9612de7-2e9f-45a4-af54-81b30dc11c55)

- Product documentation: [Production process overview - Supply Chain Management](/dynamics365/supply-chain/production-control/production-process-overview)

- Product training: [Get started with production control in Dynamics 365 Supply Chain Management](/training/modules/get-started-production-control-dyn365-supply-chain-mgmt/)

- Related product certification: [Exam MB-335: Microsoft Dynamics 365 Supply Chain Management Functional Consultant Expert (beta)](/certifications/exams/mb-335)

- Dynamics 365 Community Forum: [Dynamics 365 Supply Chain Management Forum - Production Control](https://community.dynamics.com/forums/thread/?discussionforumid=bd2c77d7-890b-4a36-87a4-8afbddbca6a6)

- Find definitions of terminology used in content for *plan to produce* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article, including the following terms:

  - [Finished good](glossary.md#finished-good)  
  - [Modes of manufacturing](glossary.md#modes-of-manufacturing)  
  - [Production schedule](glossary.md#production-schedule)  
  - [Production strategies](glossary.md#production-strategies)  
  - [Raw material](glossary.md#raw-material)  
  - [Scrap](glossary.md#scrap)  
  - [Subassembly](glossary.md#subassembly)  
  - [Subcontracting](glossary.md#subcontracting)  

<!--## Tags
*Stakeholders:* Functional consultant, Business analyst, Cost accountant lead, Finance lead, Sales lead, Purchasing lead, Production lead, Supply chain lead

*Products:* Dynamics 365 Finance, Dynamics 365 Guides, Dynamics 365 Human Resources, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management, Dynamics 365 Business Central, Power Apps, Power BI, Power Automate
