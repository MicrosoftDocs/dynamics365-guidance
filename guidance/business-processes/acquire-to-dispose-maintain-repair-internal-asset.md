---
title: Support your organization’s maintaining of internal assets
description: Learn how you can use Microsoft Dynamics 365 products to support your organization's business processes to maintain and repair internal assets.
ms.date: 08/22/2023
ms.topic: overview
author: edupont04
ms.author: hputhran
ms.custom: bap-template
---

# Support your organization’s business processes to maintain and repair internal assets

***Applies to: Dynamics 365 Finance, Dynamics 365 Supply Chain Management***

This article describes how you can use Dynamics 365 products to support your organization's business processes for maintaining and repairing internal assets.

## Introduction to the maintain and repair internal asset process

In many organizations, the terms *maintenance* and *repair* are used interchangeably. However, they might refer to different areas in the asset management process. Maintenance includes activities that can be scheduled and/or performed at a specific time to help prevent assets from breaking down and increase their life. Repairs help restore the functionality of assets when they are damaged or inoperable from a process standpoint.

There are three main types of maintenance tasks:

- **Reactive** 

    *Reactive maintenance* involves repairing an asset that has broken down or experienced a failure, typically one that isn't critical for business. If the maintenance strategy isn't effectively planned for the appropriate assets, reactive maintenance can lead to unexpected downtime and higher costs.

- **Preventive**

    *Preventive maintenance* involves performing periodic planned tasks to review the state of an asset and apply corrective procedures to help prevent it from failing. These tasks can help extend the life of the asset and can also help the organization avoid unplanned repair and restoration costs.

- **Predictive**

    *Predictive maintenance* involves using signals from machines and equipment on the production floor to sense deviations or irregularities in day-to-day operations. By using sensor intelligence mechanisms and/or smart technology, the organization can predict failures or outages before they occur. This proactive approach helps ensure that maintenance can be performed in a timely manner to mitigate potential delays.

If parts are beyond repair, it might be better to replace the asset than repair it. In this way, the daily operations continue to run at maximum efficiency.

Most tangible assets, such as vehicles, machines, and production equipment, go through a maintenance and repair journey. However, intangible assets, such as software, brands, intellectual property (IP), patents, and so on, might also require maintenance and repair. Investment in intangible assets is expensed instead of capitalized.

The owner of an asset can lease it to another party for money or another factor. Maintenance and repair of leased assets might depend on the agreement between the lessor and the lessee, based on whether the lease is a capital lease or an operating lease.

## Stakeholders for the maintain and repair internal asset process

Many people in an organization must contribute to the decision-making process and design of the *maintain and repair internal asset* process in your Dynamics 365 solution. Stakeholders include the following roles.

| Stakeholder | Responsibility |
|---|---|
| Asset managers | Manage the lifecycle of assets. |
| IT department | Maintain and test technology solutions. |
| Finance department | Track asset costs. |
| Operations department | Maintain the maintenance schedule for assets to support business operations, and provide inputs if any asset requires reactive maintenance. |
| Human resources department | Hire and train users who maintain and repair assets. |
| Procurement department | Purchase spare parts, and manage vendor relationships. |
| Legal and compliance department | Ensure regulatory compliance that is related to asset management. |
| Executive leadership | Oversee the acquisition and disposal of high-value assets, and ensure alignment with strategic goals. |

## Flow for the maintain and repair internal asset process

The following diagram shows the high-level business process flow for maintaining and repairing internal assets. For this flow, there are several exit points from the *procure spare parts/service item* process and several entry points to the *schedule maintenance* process.

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/maintain-and-repair-internal-asset-flow.svg" alt-text="Flow diagram that shows steps for maintaining and repairing internal assets." lightbox="media/maintain-and-repair-internal-asset-flow.svg":::

The flow diagram for the *maintain and repair internal asset* business process area covers the following steps.

1. Start
1. *Acquire to dispose*
1. *Maintain and repair internal asset*

    1. Plan maintenance
    1. Procure spare parts/service item

        1. Is part/service item available?

            1. Yes

                1. *Design to retire*
                1. Fetch part/service item

            1. No

                1. Will it be procured?

                    1. Yes

                        1. *Source to Pay*
                        1. Create/Process purchase requisition and purchase order

                    1. No

                        1. *Plan to produce*
                        1. Create/Process production order

    1. Schedule maintenance

        Parallel branches from this subprocess are *Case to resolution*, *Service to cash*, and *Project to profit*.

    1. Execute maintenance activities

        The parallel branch from this subprocess is *Project to profit*.

    1. Analyze maintenance activity performance

1. End

    The following end-to-end downstream processes have connections to End: [Case to resolution](case-to-resolution-introduction.md) and [Service to cash](service-to-cash-introduction.md).


> [!NOTE]
> The preceding flow diagram and explanation describe the *maintain and repair internal asset* business process area at a high level. The process flow might vary, depending on your operating model and business process requirements.

## Benefits of the maintain and repair internal asset process

This section outlines some of the main benefits that an organization can use to monitor and measure the success of maintaining and repairing internal assets.

### Improved asset tracking

Proper management and maintenance of assets help organizations reduce the risk of redundant assets and maximize the utility of assets during their useful life. Organizations that track the maintenance or repair costs for an asset can decide whether that asset should be marked for further investments or purchases in future.

### Increased longevity of assets

A proper predictive and preventive maintenance approach helps extend the life of assets and therefore mitigates the need to retire them before their end of useful life. In this way, organizations can reduce maintenance costs, forecast better for the replacement of existing assets, and improve overall asset reliability.

### Organizational compliance

Many organizations follow industry standards such as the Occupational Safety and Health Act (OSHA) to ensure safe and healthy working conditions for workers. Periodic maintenance helps these organizations ensure that the assets are in working order and safe to operate. Therefore, it helps prevent workplace injuries. It can also detect whether intangible assets, such as trademarks or copyrights, are handled or stored in a way that risks a breach of confidentiality. In addition, it helps ensure that software systems are kept up to date with the required security fixes.

## Next steps

If you want to implement Dynamics 365 solutions to help with your *maintain and repair internal asset* process, use the following resources and steps to learn more. Links are added when articles become available.

1. [Plan and budget assets](acquire-to-dispose-plan-budget-assets-overview.md)  
2. [Acquire assets  ](acquire-to-dispose-acquire-assets-overview.md)  
3. Manage internal assets  
4. Manage and report on asset financials  
5. **Maintain and repair internal assets**. (The article you are currently reading.)
6. Retire and dispose of assets  

## Related information

You can use the following resources to learn more about the *maintain and repair internal asset* process in Dynamics 365.

- [All TechTalks](https://community.dynamics.com/blogs/?blogid=e624b369-bfb9-4c57-8f1b-b3656ac91f5a)
- [Asset management overview](/dynamics365/supply-chain/asset-management/)
- [Work with Asset Management for Dynamics 365 Supply Chain Management (learning path)](/training/paths/work-asset-management-dyn365-supply-chain-mgmt/)
- Find definitions of terminology used in content for *maintain and repair internal assets* in the [Glossary of terms in Dynamics 365 business processes](glossary.md), including the following terms:

  - [Maintenance](glossary.md#maintenance)  
  - [Repair](glossary.md#repair)  
  - [Service](glossary.md#service)  
  - [Maintenance plan](glossary.md#maintenance-plan)  
  - [Maintenance checklist](glossary.md#maintenance-checklist)  
  - [Maintenance request](glossary.md#maintenance-request)  
  - [Maintenance schedule](glossary.md#maintenance-schedule)  
  - [Work order](glossary.md#work-order)  

<!-- ## Tags

*Stakeholders:* Accounts payable, Accounts receivable, Administrative, Audit, Customer services, Finance, Human resources, Merchandising, Operations, Production, Project management, Purchasing, Retail store operations, Service operations, Treasury

*Products:* Dynamics 365 Finance, Dynamics 365 Supply Chain Management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- Harshad Puthran | FastTrack Solution Architect
