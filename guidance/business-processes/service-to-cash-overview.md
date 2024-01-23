---
title: Overview of the service to cash end-to-end business process flow
description: Learn about the end-to-end business process, from service to cash. This article provides a high-level flow diagram and describes the relationship with other processes in Dynamics 365 solutions.
ms.date: 03/24/2023
ms.topic: conceptual
author: edupont04
ms.author: dehardy
ms.reviewer: edupont
ms.custom: ai-gen-docs-bap
content_well_notification: 
  - AI-contribution

---

# Overview of the service to cash end-to-end process flow and its relationship to other processes

***Applies to: Dynamics 365 Field Service, Dynamics 365 Customer Service, Dynamics 365 Remote Assist Dynamics 365 Guides, Dynamics 365 Connected Spaces***

This article describes the *service to cash* end-to-end business process flow and its relationship to other business processes that can be used within Microsoft business applications.

## Service to cash process relationship

The following diagram shows the relationship of other processes to the *service to cash process*.

:::image type="content" source="media/service-to-cash-relationship.png" alt-text="forecast to plan process relationship diagram." lightbox="media/service-to-cash-relationship.png":::

There are several processes that are often prerequisites to the *service to cash* process, including:

- **Concept to market**  

  When *service to cash* processes require consumption of services, the *concept to market* process is a perquisite process. This way, the services are available to be consumed during the *service to cash* process.

- **Inventory to deliver**  

  Many *service to cash* process scenarios require the consumption of on-hand inventory that must be available in warehouses for access by service personnel.

- **Procure to pay**  

  When you use Dynamics 365 to manage your procurement process, the *service to cash* process may require the procurement of inventory to be used in service delivery.  

- **Case to resolution**  

  Often service requests are initiated through a customer service process before creating a work order and beginning the *service to cash* process.

- **Project to profit processes**  

  Sometimes service requests are generated through a *project to profit* process when they're part of a larger ongoing project operation.

The second column in the diagram displays the business process areas of the *service to cash* process.

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

Learn more at [Service to cash business process areas overview](service-to-cash-areas-overview.md).  

The third column in the diagram displays the downstream business processes.

- **Concept to market**  

  When service delivery involves the use of new services, you may have to invoke the *concept to market* process as a downstream process to make sure the new items become part of the catalog.

- **Inventory to deliver**  

  When the inventory is unavailable at a warehouse to complete the service delivery, the inventory to deliver process may be used to make the inventory accessible to the service delivery personnel.

- **Order to cash**  

  In some business operations, more service needs are discovered during service delivery, which may lead to an order to cash process.

- **Procure to pay**  

  When inventory items are needed for the completion of a service, and aren't currently available in stock, the procure to pay process may need to be invoked to acquire the inventory.

- **Case to resolution**  

  when the service to cash was initiated through a customer service process, the case to resolution process may be invoked again once the service work is complete.

- **Project to profit**  

  When a work order is completes in the service to cash process, it may be used to update projects I the project to profit process.

- **Record to report**  

  Analyzing service operations often leads to the record to report process.

## Featured capabilities

There are product specific capabilities that interact with the *service to cash* process including, but not limited to, the following list:

- **Dynamics 365 Resource schedule optimization**  

  When the volume of scheduling work orders becomes too great, the optional resource scheduling optimization solution for Dynamics 365 Field Service can help to automate those processes. The same applies if  the number of parameters for choosing the best resource and time slots is too complex.

- **Dynamics 365 Remote assist**  

  The remote assist solution, used with Dynamics 365 field service, allows for remote experts to provide guidance to frontline workers without needing to be physically onsite.

- **Dynamics 365 guides**  

  The Dynamics 365 guides application can empower frontline workers with holographic guidance and real-time collaboration.

- **Dynamics 365 Supply Chain Management:** Includes asset management and service management capabilities, and better together benefits when integrated Dynamics 365 Field Service

## Service to cash business process flow

The following diagram shows the high-level flow of the *service to cash* business process. [!INCLUDE [daf-business-process-e2e-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-e2e-flow-def.md)]

:::image type="content" source="media/service-to-cash-process-flow.png" alt-text="end-to-end process flow diagram" lightbox="media/service-to-cash-process-flow.png":::

The following steps are illustrated in the service to cash end-to-end business process flow diagram.

1. Establish servicing policies and procedures

2. Create and manager service resources

3. Create and manage service accounts

4. Manage asset

5. Create work orders

6. Schedule work orders

7. Perform service work

8. Review and close work order

9. Analyze Service Operations

## Next steps

If you want to implement Dynamics 365 solutions to assist with your service to cash business processes, use the following resources and steps to learn more.

- Define the goals and objectives of implementing a service to cash technology solution. Learn more at [Implementation strategy](../implementation-guide/implementation-strategy.md).  

- Define the business process scope of your project. Learn more at [Process-focused solution](../implementation-guide/process-focused-solution.md).  

- Request a demo or get a free trial of Dynamics 365 solutions for the *service to cash* process. Learn more at [Request a demo](https://dynamics.microsoft.com/dynamics-365-free-trial/).  

- Get an overview of each end-to-end business process area at [Service to cash business process areas overview](service-to-cash-areas-overview.md).  

## Related resources

Use the following resources to learn more about the service to cash process in Dynamics 365.

- [Overview of Dynamics 365 Field Service](/dynamics365/field-service/overview)

- [Dynamics 365 Field Service user guide](/dynamics365/field-service/user-guide)

<!--## Tags
*Stakeholders:* Functional consultant, Business analyst, Accounts payable lead, Accounts receivable lead, Finance lead, Sales lead, Purchasing lead, Production lead, Supply chain lead

*Products:* Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Guides, Dynamics 365 Project Operations, Dynamics 365 Remote Assist
