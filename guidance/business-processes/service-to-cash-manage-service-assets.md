---
title: Overview of the Manage service assets business process area
description: Learn about how to support your organization's business processes for managing service assets in your Dynamics 365 products.
author: SabrinaDiBartolomeo
ms.author: sabrinadi
ms.date: 02/15/2024
ms.topic: overview
---

# Overview of the Manage service assets business process area within the Service to cash end-to-end scenario

***Applies to: Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Supply Chain Management***

This article describes how you can use Dynamics 365 products to support your organization's business processes for managing service assets.

## Introduction to manage service assets

Many organizations provide services for products that their customers purchase, lease from them, or from other sources and that need to be maintained and serviced regularly. These services may include installation, maintenance, repair, troubleshooting, or upgrading of the products.

> [!IMPORTANT]
> This article primarily pertains to the servicing of assets owned by, or located at, customer locations. Learn more at [Manage internal assets overview](acquire-to-dispose-manage-internal-assets.md).

To manage service assets effectively, it's vital to keep a repository of serviceable items (assets) and to track them, recording all the needed information that will be helpful during the maintenance process, such as:

-   Identification number

-   Location

-   Properties, such as the manufacturing date

-   Service history

Each customer's asset, based on its nature, could require different properties. For items such as equipment, relevant information could be the installation date, the warranty period, or the service history.

Typically, each asset in the system is linked to the customer and to its physical location. By knowing where the asset is located and who is using it, the asset manager can optimize the maintenance of the asset and can provide valuable insights for strategic decision making and planning.

Companies might have requirements for servicing customer equipment arranged into a hierarchy of functional locations. Functional locations could be based on geographical locations or other characteristics.

Many products are composed of distinct parts that have their own attributes and functions. Each part can be identified by a unique code, name, description, price, or other properties and even distinct location at customer site. To save the structure of these products in the system, one approach could be to use a hierarchy model that relates the parts with the parent asset.

Arranging customer assets in categories or families can serve as a label to organize assets into groups. This can help companies manage their assets more efficiently and effectively grouping by relevant criteria.

Whenever a product undergoes a change, such as being relocated or disposed of, the asset catalog should be updated accordingly to reflect the change. This ensures that the information in the catalog is accurate and up-to-date, and that the products can be tracked and monitored effectively. Updating the asset catalog also helps to avoid errors, confusion, and waste that may arise from outdated or incorrect data.

A company can also leverage the IoT (internet of things) capabilities of customer assets to proactively manage them, identifying and correcting potential defects or hazards before they cause any harm or damage to the asset. This can be achieved by providing real-time data, insights, and control over assets.

## Stakeholders for the manage service assets process

Many people in an organization must contribute to the decision-making process and design of the manage service asset process in your Dynamics 365 project. The following list provides examples of such stakeholders:

-   **Customer** - who owns or leases the asset.

-   **Asset manager** - who maintains the asset records and is responsible for planning the maintenance activities for the customer assets.

-   **Inventory manager** - responsible for managing the inventory of spare parts, tools, and equipment that are needed for repairing and maintaining the customer assets

## Manage service assets process flow 

The following diagram shows the high-level business process flow for managing service assets.

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/service-to-cash-business-process-area-map.svg" alt-text="Follow steps in following paragraphs." lightbox="media/service-to-cash-business-process-area-map.svg":::

Each solid gray rectangle on the diagram represents an end-to-end business process. The solid blue rectangle represents the business process area. The diagram shows the subprocesses for the business process area. The arrows on the diagram show the flow of the business process in an organization. If a subprocess can lead to more than one other subprocess, the parallel subprocesses are shown as branches.

The manage service assets business process area flow diagram covers the following steps.

1. *Start*

2. *Decision box: Internal asset?*

3. *If yes: Service to cash*

    1. *Manage service asset*

        1. *Set up customer assets*

        2. *Monitor customer assets*

        3. *Update customer assets*

4. *End*

5. *If no: Acquire to dispose*

## Manage service assets benefits

There are many key benefits that can be used to monitor and measure the success of maintaining and repairing service assets. The following sections outline the key benefits that an organization might monitor and measure to manage service assets.

## Productivity

By keeping track of customer products as assets, the company can enhance its service delivery to the customers by inspecting, supporting, and repairing the assets where and when needed. By having a clear and accurate inventory of the products that customers own, the company can plan their service visits more efficiently, avoid unnecessary trips or delays, and ensure that Frontline Workers have the right parts and tools for each job.

## Improved quality

The history and status of the assets can help the company to improve the quality and performance of the products. You can also monitor the performance and condition of the products, identify potential issues or failures before they become critical, and provide proactive maintenance and support.

## Customer satisfaction

The maintenance process aims to ensure customer satisfaction, retention and loyalty and ensures that the asset is in good working order and meets the customer's expectations and requirements.

## Next steps

If you want to implement Dynamics 365 solutions to help with your *track production costs* business processes, use the following resources and steps to learn more. (Links are added, when articles are ready.)

1. *Manage service assets* (The article you're currently reading.)

2. *Manage service resources*

3. [Create and process service work](service-to-cash-create-process-service-work.md)

<!--- **Manage service resources and create and process service work links pending tasks migrating document files to Markdown files.

--->

## Related information

You can use the following resources to learn more about the maintain service asset process in Dynamics 365.

- [Work with customer assets (contains video)](/dynamics365/field-service/assets)

- [Customer assets in Dynamics 365 Field Service - Training](/training/modules/customer-assets)

- [Asset management overview](/dynamics365/supply-chain/asset-management)

- [Functional locations and assets](/dynamics365/supply-chain/asset-management/overview/functional-locations-and-objects)

<!--## Tags

*Industries:* Healthcare, Financial services, Retail, Manufacturing

*Stakeholders:* Customer project manager, Partner project manage, Program manager, Cutover lead, Training lead, Adoption lead, Solution architect, Developer, Data migration lead, Integration lead, Functional consultant, Business analyst, Accounts payable lead, Accounts receivable lead, Finance lead, Sales lead, Purchasing lead, Production lead, Supply chain lead

*Products: Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Supply Chain Management* -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

### Principal author:

-   Sabrina Di Bartolomeo ([Sabrina Di Bartolomeo \| LinkedIn](https://www.linkedin.com/in/sabrina-di-bartolomeo-025463/)) \| FastTrack Solution Architect