---
title: Overview of the Run production operations business process area
description: Learn how you can use Dynamics 365 products to support your organization's business processes for running production operations.
ms.date: 12/06/2023
ms.topic: concept-article
author: edupont04
ms.author: annekrupke
---

# Overview of the Run production operations business process area within the Plan to produce end-to-end scenario

***Applies to: Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Power Apps, Power Platform, Power BI***

This article describes how you can use Dynamics 365 products to support your organization's business processes for *running production operations*.  

The *run production operations* business process area covers the activities in an organization's internal production process. Any manufacturing organization finds it critical to track and control production operations. The goal is to ensure consistent product quality and minimize production costs. *Running production operations* also requires coordination and communication between many departments, such as engineering, operations, quality, sales, planning, and procurement.

The process for executing production operations varies from business to business, depending on industry and product, but it follows the same basic steps. At the beginning of production, materials are consumed into the process. A combination of people and tools or machines then run the specific production steps. Finally, the sub-assembly or finished good is created as the output of the process. The definition of these steps is done as part of the *Design to retire* end-to-end business processes and refined further in the *define production strategies* business process area.

Define this business process at the beginning of an implementation of Dynamics 365 Supply Chain Management. It's a foundational process for any manufacturing company.

## Stakeholders

Many people across the organization should contribute to the decision-making process and design of the *run production operations* area. The list includes but isn't limited to the following roles:

- **Inventory stakeholders** – examples: Warehouse manager, Transportation planner

- **Planning stakeholders** – examples: COO, VP of Operations, Operations Manager, Planning manager

- **Production stakeholders** – examples: Production manager, Production scheduler

- **Engineering stakeholders** - examples: Product owner, Engineering manager

- **Costing stakeholders** - examples: Cost accountant, Controller

- **Quality stakeholders** – examples: Quality manager, Quality technician

## Run production operations process flow

The following diagram shows the high-level flow of the *run production operations* business process area. [!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/execute-production-operations-flow.svg" alt-text="Execute production operations process flow" lightbox="media/execute-production-operations-flow.svg":::

The following steps are illustrated in the *run production operations* business process flow diagram.

1. Start

    1. A parallel branch from **Start** includes *Inventory to deliver*

        1. Consume materials in production

        2. Put away finished goods or sub-assembly inventory

2. *Plan to produce* end-to-end process

3. *Plan production operations*

4. *Run production operations*

5. Is operation outsourced?

    1. A parallel branch for **Yes** leads to *Outsource production operations*, which has an unshown connection to 10. End

6. *Start production* if operations aren't outsourced  

    1. A parallel branch, *Adjust production plan*, connects back to *Plan production operations*

7. *Consume materials in production*

    1. Control production quality

    2. Track production costs

8. *Use production resources*

    1. Control production quality

    2. Track production costs

9. *Report production output*

    1. Control production quality

    2. Track production costs

    3. Put away finished goods or sub-assembly inventory

10. End

## Benefits

There are many key benefits to using Dynamics 365 to help the organization run the production operations. The following sections outline the key benefits that an organization might monitor and measure for the *run production operations* process.

### Increase production throughput

Dynamics 365 Supply Chain Management collects and shows immediate feedback from the shop floor from workers and sensor data. This input empowers supervisors to quickly identify when different operations are delayed or deviate from the allowed boundaries and take appropriate actions. With the connection between production and maintenance, workers can register production downtime immediately. Supervisors can then either reschedule the remaining work to a new machine or expedite repair on the machine. Increasing production throughput results in shorter lead times and can also help improve the percentage of orders delivered on-time and in full (OTIF).

### Reduce material shortages

Production fully integrates with the other business processes in Dynamics 365 Supply Chain Management. Planners can see real-time inventory of materials throughout the production process so that they can make sure that materials are replenished appropriately. This process reduces the number of stockouts and the subsequent production delays.

### Improve product quality

Dynamics 365 Supply Chain Management connects production and quality so that quality managers can investigate the source of quality defects. This way, they can drive continuous process improvements to reduce the defect rate and improve the overall product quality.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *plan to produce* business processes, use the following resources and steps to learn more.

1. [Plan supply and replenishment](forecast-to-plan-supply-replenishment-overview.md)  

2. [Define production strategies](plan-to-produce-define-production-strategies.md)

3. [Plan production operations](plan-to-produce-plan-production-operations-overview.md)

4. *Run production operations* (the article that you're currently reading)

5. [Outsource production operations](plan-to-produce-outsource-production-operations-overview.md)  

6. [Control production quality](plan-to-produce-control-production-quality-overview.md)  

7. [Track production costs](plan-to-produce-track-production-costs-overview.md)  

Return to the overview of business process areas at [Plan to produce business process areas](plan-to-produce-areas.md).

## Related information

You can use the following resources to learn more about the *run production operations* process in Dynamics 365.

- Discrete Manufacturing TechTalk: [Discrete Manufacturing Overview](https://community.dynamics.com/blogs/post/?postid=13f0b0ac-6755-482e-ab73-9fcc1b55380a)

- TechTalk on Third Party MES Integrations tool: [Integrating third party Manufacturing Execution System with Dynamics 365 for Supply Chain Management](https://community.dynamics.com/blogs/post/?postid=39606559-7c7e-4a68-8261-3cf501e84770)

- TechTalk on Production floor execution interface: [Production Floor Execution Interface in Dynamics 365 Supply Chain Management](https://community.dynamics.com/blogs/post/?postid=81f0f2ee-0c2f-47e5-b121-cdb98821f287)

- Product documentation: [Production process overview](/dynamics365/supply-chain/production-control/production-process-overview)  

- Product training: [Get started with production control in Dynamics 365 Supply Chain Management](/training/modules/get-started-production-control-dyn365-supply-chain-mgmt/)  

- Related product certification: [Exam MB-335: Microsoft Dynamics 365 Supply Chain Management Functional Consultant Expert (beta)](/certifications/exams/mb-335)  

- Dynamics 365 Community Forum: [Dynamics 365 Supply Chain Management Forum](https://community.dynamics.com/forums/thread/?discussionforumid=bd2c77d7-890b-4a36-87a4-8afbddbca6a6)

- Define the goals and objectives of implementing a *plan to produce* technology solution. Learn more at [Implementation strategy](../implementation-guide/implementation-strategy.md).

- Define the business process scope of your project. Learn more at [Process-focused solution.md](../implementation-guide/process-focused-solution.md).

- Request a demo or get a free trial of Dynamics 365 solutions for the plan to produce process. Learn more at [Request a demo](https://www.microsoft.com/dynamics-365/free-trial).

- Find definitions of terminology used in content for *run production operations* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article, including the following terms:

  - [Production source documents](glossary.md#production-source-documents)  
  - [Production journals](glossary.md#production-journals)  
  - [Manufacturing Execution System](glossary.md#manufacturing-execution-system)  
  - [Internet of Things sensors](glossary.md#internet-of-things-sensors)  

<!--## Tags

*Industries:* Mining, Construction, Manufacturing, Wholesale trade, Retail trade

*Stakeholders:* Functional consultant, Business analyst, Production lead, Supply chain lead, Inventory lead, Costing lead

*Products:* Dynamics 365 Supply Chain Management-->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Anne Krupke](https://www.linkedin.com/in/annekrupke/) \| FastTrack Solution Architect

Other contributors:

- [Rachel Profitt](https://www.linkedin.com/in/rachelprofitt/) \| FastTrack Solution Architect
