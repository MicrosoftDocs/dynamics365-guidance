---
title: Overview of the service to deliver end-to-end business process
description: Learn about the service to deliver end-to-end business process with a flow diagram and describes the relationship with other processes in Dynamics 365 solutions.
ms.date: 10/03/2025
ms.topic: concept-article
author: edupont04
ms.author: DeanHardy
ms.reviewer: edupont
ms.custom: ai-gen-docs-bap
ai-usage: ai-assisted

---

# Overview of the service to deliver end-to-end process flow and its relationship to other processes

***Applies to: Dynamics 365 Field Service, Dynamics 365 Customer Service, Dynamics 365 Remote Assist Dynamics 365 Guides, Dynamics 365 Connected Spaces***

This article describes the *service to deliver* end-to-end business process flow and its relationship to other business processes that can be used within Microsoft business applications.

> [!IMPORTANT]
> This end-to-end scenario has a new name in the February 2025 version of the business process catalog. The articles in Microsoft Learn are not yet fully updated based on this version. Learn more at [What's new or changed in the business process catalog February 2025](about-whats-new-2025-february.md).

## Service to deliver process relationship

The following diagram shows the relationship of other processes to the *service to deliver process*. [!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/service-to-cash-relationship.png" alt-text="forecast to plan process relationship diagram." lightbox="media/service-to-cash-relationship.png":::

There are several processes that are often prerequisites to the *service to deliver* process, including:

- **Concept to market**  

  When *service to deliver* processes require consumption of services, the *concept to market* process is a perquisite process. This way, the services are available to be consumed during the *service to deliver* process.

- **Inventory to deliver**  

  Many *service to deliver* process scenarios require the consumption of on-hand inventory that must be available in warehouses for access by service personnel.

- **Procure to pay**  

  When you use Dynamics 365 to manage your procurement process, the *service to deliver* process may require the procurement of inventory to be used in service delivery.  

- **Case to resolution**  

  Often service requests are initiated through a customer service process before creating a work order and beginning the *service to deliver* process.

- **Project to profit processes**  

  Sometimes service requests are generated through a *project to profit* process when they're part of a larger ongoing project operation.

The second column in the diagram displays the business process areas of the *service to deliver* process.

The business process areas are:

- Establish servicing policies and procedures

- Create and manage service resources

- Create and manage service accounts

- Manage assets

- Create work orders

- Schedule work orders

- Perform service work

- Review and close work orders

- Analyze service operations

Learn more at [Service to deliver business process areas overview](service-to-cash-areas-overview.md).  

The third column in the diagram displays the downstream business processes.

- **Concept to market**  

  When service delivery involves the use of new services, you may have to invoke the *concept to market* process as a downstream process to make sure the new items become part of the catalog.

- **Inventory to deliver**  

  When the inventory is unavailable at a warehouse to complete the service delivery, the inventory to deliver process may be used to make the inventory accessible to the service delivery personnel.

- **Order to cash**  

  In some business operations, more service needs are discovered during service delivery, which may lead to an order to cash process.

- **Source to pay**  

  When inventory items are needed for the completion of a service, and aren't currently available in stock, the source to pay process may need to be invoked to acquire the inventory.

- **Case to resolution**  

  when the service to deliver was initiated through a customer service process, the case to resolution process may be invoked again once the service work is complete.

- **Project to profit**  

  When a work order is completes in the service to deliver process, it may be used to update projects I the project to profit process.

- **Record to report**  

  Analyzing service operations often leads to the record to report process.

## Featured capabilities

There are product specific capabilities that interact with the *service to deliver* process including, but not limited to, the following list:

- **Dynamics 365 Resource schedule optimization**  

  When the volume of scheduling work orders becomes too great, the optional resource scheduling optimization solution for Dynamics 365 Field Service can help to automate those processes. The same applies if  the number of parameters for choosing the best resource and time slots is too complex.

- **Dynamics 365 Remote assist**  

  The remote assist solution, used with Dynamics 365 field service, allows for remote experts to provide guidance to frontline workers without needing to be physically onsite.

- **Dynamics 365 guides**  

  The Dynamics 365 guides application can empower frontline workers with holographic guidance and real-time collaboration.

- **Dynamics 365 Supply Chain Management:** Includes asset management and service management capabilities, and better together benefits when integrated Dynamics 365 Field Service

## Service to deliver business process flow

The following diagram shows the high-level flow of the *service to deliver* business process. [!INCLUDE [daf-business-process-e2e-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-e2e-flow-def.md)]

:::image type="content" source="media/service-to-cash-process-flow.svg" alt-text="end-to-end process flow diagram" lightbox="media/service-to-cash-process-flow.svg":::

The following steps are illustrated in the service to deliver end-to-end business process flow diagram:

1. Start
2. *Service to deliver* business process
   1. *Develop service strategy*
   2. *Plan service strategy*
   3. *Process service orders*
   4. *Run service operations*
   5. *Analyze service performance*
3. End

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *service to deliver* business processes, use the following resources and steps to learn more.

1. Define the goals and objectives of implementing a service to deliver technology solution. Learn more at [Implementation strategy](../implementation-guide/implementation-strategy.md).  

2. Define the business process scope of your project. Learn more at [Process-focused solution](../implementation-guide/process-focused-solution.md).  
3. Request a demo or get a free trial of Dynamics 365 solutions for the *service to deliver* process. Learn more at [Request a demo](https://www.microsoft.com/dynamics-365/free-trial).  

4. Get an overview of each end-to-end business process area at [Service to deliver business process areas overview](service-to-cash-areas-overview.md).  

## Related information

Use the following resources to learn more about the service to deliver process in Dynamics 365.

- [Overview of Dynamics 365 Field Service](/dynamics365/field-service/overview)

- [Dynamics 365 Field Service user guide](/dynamics365/field-service/user-guide)

- [Manage service assets overview](service-to-cash-manage-service-assets.md)

<!--## Tags
*Stakeholders:* Functional consultant, Business analyst, Accounts payable lead, Accounts receivable lead, Finance lead, Sales lead, Purchasing lead, Production lead, Supply chain lead

*Products:* Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Guides, Dynamics 365 Project Operations, Dynamics 365 Remote Assist
