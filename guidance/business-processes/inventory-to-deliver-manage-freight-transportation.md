---
title: Manage freight and transportation overview
description: Read about the business process area for managing freight and transportation in Dynamics 365 implementations.
ms.date: 07/13/2023
ms.topic: conceptual
author: edupont04
ms.author: ngump
---

# Manage freight and transportation overview

***Applies to: Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center***

This article describes the *Manage freight and transportation* business process area. It describes the process flow of this area and explains the benefits of using Dynamics 365 to support this process area.

The *Manage freight and transportation* business process area encompasses the activities that are done in an organization's transportation management process. All distribution organizations must be able to track and manage transportation costs and operations so that they can optimize this critical part of the supply chain. Meeting this goal requires cross-organization collaboration among departments such as Logistics, Procurement, Planning, Sales, and Operations.

The exact process for the *Manage freight and transportation* area varies from business to business and depends on the industry. However, the basic steps are the same: The need for transportation is identified. Identification of this need triggers planning activities, including rating and routing operations. Dock appointments can then be scheduled for pickup and/or delivery, and necessary logistics paperwork can be generated. After transportation is completed, freight invoices can be processed and reconciled against estimates. The definition of these steps is done as part of the *Inventory to deliver* end-to-end business processes and refined in the *Define and manage warehouse operations* business process area.

It's essential that you define and establish the business process for *Managing freight and transportation* when you first begin to implement Dynamics 365 Supply Chain Management. This process is a fundamental element for any distribution company, because it forms the backbone of efficient supply chain operations.

## Stakeholders

Many people across the organization should contribute to the decision-making process and the design of the *Manage freight and transportation* area. The list includes but isn't limited to the following roles:

- **Inventory stakeholders** – Examples: Warehouse manager and Transportation planner
- **Operations stakeholders** – Examples: Chief Operating Officer (COO), Vice President (VP) of Operations, and Operations Manager
- **Costing stakeholders** – Examples: Cost accountant and Controller

## Manage freight and transportation process flow

The following diagram shows the high-level flow of the *Manage freight and transportation* business process area.

[!INCLUDE [daf-business-process-flow-def](../includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/inventory-to-deliver-manage-freight-transport-flow.svg" alt-text="Diagram that shows business process relationships with upstream and downstream processes that are explained in the next paragraphs." lightbox="media/inventory-to-deliver-manage-freight-transport-flow.svg":::

The following steps are illustrated in the *Manage freight and transportation* business process flow diagram.

1. Start
1. A parallel branch from the *Inventory to deliver* end-to-end business process includes:

    1. *Define and manage warehouse operations*

        1. A parallel branch to *Process inbound goods* and *Process outbound goods*

    1. *Control vendor managed inventory and consignment inventory*

1. *Manage freight and transportation*

    1. Plan transportation loads
    1. Decision point: Is routing required?

        1. If yes, Route transportation loads
        1. If no, decision point

    1. Decision point: Is rating required?

        1. If yes, Rate transportation loads
        1. If no, decision point

    1. Decision point: Is dock management required?

        1. If yes, Schedule dock appointments
        1. If no, Print shipping documentation

            1. End

    1. Process freight invoice
    1. Reconcile freight

1. *Manage inventory costs*

    1. A parallel branch to *Record and control costs* and the *Record to report* end-to-end business process

1. End

## Benefits

This section outlines the key benefits that organizations can use to monitor and measure the success of implementing technology to support the *Manage freight and transportation* business process area.

### Reduced transportation costs

Organizations can use Dynamics 365 Supply Chain Management and Supply Chain Center to maintain freight carrier contact rates. They can search for the lowest costs, even across multiple modes of transport for a specific route. Other transportation management capabilities help increase the use of load capacity. In return, organizations can reduce their costs by minimizing the number of shipments that are required. Organization can also use freight reconciliation to track and approve discrepancies between their estimates and carrier invoices.

### Improved operational efficiency

Transportation is integrated with other business processes in Dynamics 365 Supply Chain Management. Warehouse managers can schedule dock appointments for carrier pickup and/or drop-off, based on bay door vacancy, anticipated loading times, and equipment availability. This integration helps minimize driver wait time, mitigate potential fees for delays, and ensure that warehouse operations don't become bottlenecks in the overall supply chain.

### Optimized fulfillment strategies

Dynamics 365 Supply Chain Management has transportation rating and routing capabilities. Similarly, [Intelligent Order Management](/dynamics365/intelligent-order-management/welcome-to-iom) in Supply Chain Center provides order orchestration capabilities that extend beyond the distribution warehouse. It connects multiple supply chain providers, from manufacturers to retailers to third-party logistics companies. Therefore, organizations can optimize their fulfillment operations, and this optimization then leads to faster delivery and increased customer satisfaction.

## Next steps

If you want to implement Dynamics 365 solutions to help with your *Inventory to deliver* business processes, use the following resources and steps to learn more.

- Define the goals and objectives of implementing an *Inventory to deliver* technology solution. Learn more at [Implementation strategy](../implementation-guide/implementation-strategy.md).
- Define the business process scope of your project. Learn more at [Process-focused solution.md](../implementation-guide/process-focused-solution.md).
- Request a demo, or get a free trial of Dynamics 365 solutions for the *Inventory to deliver* process. Learn more at [Request a demo](https://dynamics.microsoft.com/dynamics-365-free-trial/).
- Get an overview of the *Inventory to deliver* process. Learn more at [Inventory to deliver overview](inventory-to-deliver-overview.md).

## Related resources

You can use the following resources to learn more about the *Manage freight and transportation* business process area in Dynamics 365.

- [Introduction to Transportation Management TechTalk](https://community.dynamics.com/blogs/post/?postid=6c363f60-23fb-459a-b5dd-1f06fa24a886)
- [Transportation Management Configuration Deep-Dive (Rating & Routing)](https://community.dynamics.com/blogs/post/?postid=10103d2b-afe2-4ed3-85b0-95adf9708fd5)
- [TechTalk on Parcel Carrier Integration in Dynamics 365 Supply Chain Management](https://community.dynamics.com/blogs/post/?postid=4eea123c-c220-4b93-8273-514fdb1e6997)

    - Supporting product documentation: [Small parcel shipping](/dynamics365/supply-chain/warehousing/small-parcel-shipping)
    - Supporting GitHub assets: [Dynamics-365-FastTrack-Implementation-Assets/SCM/SPS](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM/SPS)

- [Transportation Management Configuration Deep-Dive on Freight Reconciliation](https://community.dynamics.com/blogs/post/?postid=f513292c-1c2a-4f5f-8423-eb3cf5b8db39)
- Product documentation: [Transportation management overview](/dynamics365/supply-chain/transportation/transportation-management-overview)
- Product training: [Configure and work with transportation management in Dynamics 365 Supply Chain Management](/training/paths/configure-work-transportation-mgmt-dyn365-supply-chain-mgmt/)
- Related product certification: [Exam MB-335: Microsoft Dynamics 365 Supply Chain Management Functional Consultant Expert (beta)](/certifications/exams/mb-335)
- [Dynamics 365 Supply Chain Management Forum](https://community.dynamics.com/forums/thread/?discussionforumid=bd2c77d7-890b-4a36-87a4-8afbddbca6a6)
- Find definitions of terminology that is used in content for *Manage freight and transportation* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article. For example, this glossary includes the following terms:

    - [Load](glossary.md#load)
    - [Shipment](glossary.md#shipment)
    - [Rating](glossary.md#rating)
    - [Routing](glossary.md#routing)
    - [Dock management](glossary.md#dock-management)
    - [Appointment scheduling](glossary.md#appointment-scheduling)
    - [Freight reconciliation](glossary.md#freight-reconciliation)
    - [Provider](glossary.md#provider)

<!-- ## Tags

*Industries:* Distribution, Manufacturing, Wholesale trade, Retail trade

*Stakeholders:* Functional consultant, Business analyst, Transportation lead, Supply chain lead, Inventory lead, Costing lead

*Products:* Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Nicole Gump](https://www.linkedin.com/in/nicolegump/) | FastTrack Solution Architect

Other contributors:

- Weijie Sa<!--(https://www.linkedin.com/in/saweijie/)--> | Dynamics 365 SCM Product Manager
