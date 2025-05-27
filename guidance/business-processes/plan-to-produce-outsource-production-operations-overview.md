---
title: Overview of the Subcontract production business process area
description: Get an overview of the business process area for outsourcing production operations in the plan to produce end-to-end business process in Dynamics 365 solutions.
ms.date: 12/06/2023
ms.topic: concept-article
author: edupont04
ms.author: annekrupke
---

# Overview of the Subcontract production business process area within the Plan to produce end-to-end scenario

***Applies to: Dynamics 365 Finance, Dynamics 365 Supply Chain Management***

This article describes the business process area *Subcontract production*. It explains the context of the process area, provides a list of the benefits of using Dynamics 365 to support the process area, and lists the processes in the area.

> [!IMPORTANT]
> In earlier versions of the business process catalog, this article represented a business process area, *Outsource production operations*. In February 2025, it was renamed to *Subcontract production* and is now a business process under the *Run production operations* area, and we're in process of updating the content to reflect this change.

The term *subcontracting* is also known as *outsourcing* or *tolling*. The term describes when an organization hires an external vendor to handle certain steps of the production process. It can include sending raw materials or WIP products to the vendor, or the vendor procures their own materials. When the vendor production is complete, the updated product is shipped to the business, and they can either sell it as a finished product or consume it in further production operations.

The *Subcontract production* area is typically implemented during the main implementation of Dynamics 365, unless the organization implements only financial modules in the initial phase. Companies sometimes also make a business decision to do outsourcing after they're live with Dynamics 365. With Dynamics 365, they can add new products as outsourced, and transition existing products to be outsourced instead of produced internally.

> [!NOTE]
> In addition to outsourcing production activities, companies can choose to outsource other activities such as project services or IT. These other types of outsourcing are not included in the scope of this article.

## Stakeholders 

Many people across the organization should contribute to the decision-making process and design of the *Subcontract production* area. The list includes but isn't limited to the following roles:

- **Production stakeholders**, such as production schedulers and production supervisors, provide details on the business requirements in this process.

- **Planning stakeholders**, such as master planners, describe the process of determining which products should be outsourced.

- **Procurement stakeholders**, such as buyers or vendor managers, can describe the process of contracting and communicating with outsourcing vendors.

## Subcontract production process flow 

The following diagram shows the *Subcontract production* process flow, including the related business processes and the upstream and downstream activities. [!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/plan-to-produce-outsource-production-flow.svg" alt-text="Flow diagram for the business process area that is explained in the paragraph after the image." lightbox="media/plan-to-produce-outsource-production-flow.svg":::

The flow diagram covers the following steps:

1. Start

    1. A parallel branch from 1. Start includes the *Source to pay* end-to-end process.

        1. *Procure materials and services* business process area

        2. *Process vendor invoices* business process area

            1. End

    2. An unshown parallel branch from 1. Start includes the *Inventory to deliver* end-to-end process.

        1. *Process outbound goods* business process area

        2. *Process inbound goods* business process area

            1. *Process vendor invoices* business process area

2. *Plan to produce* end-to-end process

    1. A parallel branch from 2. *Plan to produce* includes the *Define production strategies* business process area.

        1. *Define outsourcing policies* business process

    2. A parallel branch from 2. *Plan to produce* includes the *Plan production operations* business process area.

        1. *Communicate work to subcontractor* business process

3. *Run production operations* business process area

4. *Subcontract production* business process area

5. *Define outsourcing policies* business process

6. *Communicate work to subcontractor* business process

    1. A parallel branch from 6. *Communicate work to subcontractor* includes the *Procure materials and services* business process area.

7. *Send material to subcontractor* business process

    1. A parallel branch from 7. *Send material to subcontractor* includes the *Process outbound goods* business process area.

8. *Receive material from subcontractor* business process

    1. A parallel branch from 8. *Receive material from subcontractor* includes the *Process inbound goods* business process area.

        1. *Process vendor invoices* business process area

9. End

## Subcontract production benefits

Many key benefits can be used to monitor and measure the success of implementing technology to support the *Subcontract production* area. The following sections outline the key benefits that an organization might monitor and measure for the *Subcontract production* area. 

### Improve product quality

Using external vendors who may have more experience or specialized machinery to do some production steps can help lead to improved product quality. This way, manufacturers can focus on their core competencies instead of having to cover a wider range of activities.

### Increase production capacity

In peak seasons or other times of high demand, using a subcontractor is one way to add production capacity without having to invest in more machinery or facilities. It's also something that can be used ad-hoc to replace in-house manufacturing if a machine is down or personnel are out sick. Outsourcing in general helps businesses increase their scalability and can provide greater global market access.

### Increase process efficiency

With the **subcontracting** capabilities in Dynamics 365 Supply Chain Management, businesses can identify products that are subcontracted and automatically create the supporting documentation when subcontracted products are on the production schedule.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *Subcontract production* business processes, use the following resources and steps to learn more. (Links are added when the articles are ready.)

1. [Develop production strategies](plan-to-produce-define-production-strategies.md)
1. [Plan production operations](plan-to-produce-plan-production-operations-overview.md)  
1. [Run production operations](plan-to-produce-execute-production-operations-overview.md)  

    1. *Start production*  
    1. *Adjust production plan*  
    1. *Consume materials*  
    1. *Consume resources*  
    1. *Report production output*  
    1. *Subcontract production* (the article that you're currently reading)  
    1. *Record production costs*
1. [Control production quality](plan-to-produce-control-production-quality-overview.md)  
1. *Analyze production operations*  

## Related information

You can use the following resources to learn more about the *Subcontract production* process in Dynamics 365:

- [Manage subcontracting work in production](/dynamics365/supply-chain/production-control/manage-subcontract-work-production)  

- [Configure activity-based subcontracting and production flow costing in Dynamics 365 Supply Chain Management (training)](/training/modules/configure-subcontracting-flow-dyn365-supply-chain-mgmt)  

- [Plan to produce business process areas](plan-to-produce-areas.md)  
<!-- ## Tags

*Industries* Manufacturing (20-39), Wholesale Trade (50-51), Retail Trade (52-59)

*Stakeholders:* Accounts payable, Finance, Production, Purchasing, Operations

*Products:* Dynamics 365 Finance, Dynamics 365 Supply Chain Management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Anne Krupke](https://www.linkedin.com/in/annekrupke/) | FastTrack Solution Architect  

Other contributors:

- [Phillip Seaton](https://www.linkedin.com/in/pbseaton/) | FastTrack Solution Architect  

- [Johan Hoffmann](https://www.linkedin.com/in/johan-hoffmann-1ba1b83/) | Senior Product Manager, Production control
