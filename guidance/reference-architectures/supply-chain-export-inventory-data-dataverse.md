---
title: Export inventory data using Dataverse and Inventory Visibility
description: Learn how to implement delta tracking for on-hand inventory changes using Dynamics 365 Supply Chain Management, Inventory Visibility service, and Dataverse capabilities.
author: edupont04
contributors: Shanthini
ms.topic: reference-architecture
ms.date: 07/29/2025
ms.author: edupont
ms.reviewer: edupont
---
# Export inventory data using Dataverse and the Inventory Visibility add-in

**Applies to**: **Dynamics 365 Commerce, Dynamics 365 Supply Chain Management, Power Automate, Dataverse, Azure Logic Apps**

This article shows how to use Dynamics 365 Supply Chain Management with the *Inventory Visibility* add-in and Dataverse capabilities to track changes to inventory on hand. This architecture lets you avoid pushing events directly from Supply Chain Management. Use Logic Apps or Power Automate, depending on your needs. Or, expose the data from Dataverse to a Delta Lake for further analysis.

## Solution overview

A common use case in Supply Chain Management and Commerce is exposing global inventory on-hand values to surrounding systems or sales platforms. You might solve this challenge by using different patterns, like [Commerce Scale Unit](/dynamics365/commerce/dev-itpro/retail-store-system-begin) with [the data management framework](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities-data-packages), or by using [exports to Azure Data Lake](/dynamics365/fin-ops-core/dev-itpro/data-entities/azure-data-lake-ga-version-overview) from Finance or Supply Chain Management.

Since Microsoft introduced [the Inventory Visibility service](/dynamics365/supply-chain/inventory/inventory-visibility), complexity and performance challenges are improved. The current version uses a separate microservice and underlying architecture to replicate on-hand information from Supply Chain Management to Dataverse. The service also exposes information in a way that makes more sense to external systems.

However, the main pattern for Inventory Visibility is built around ad-hoc querying of data. Sometimes, you want to do a full export of snapshot on-hand data. Other times, you want to push events that show on-hand values changed for a specific inventory dimension or location.

Feature management in Inventory Visibility lets you periodically sync on-hand changes to a table in Dataverse, so you can enable delta tracking and send events whenever something changes. This article explains this pattern and the components and considerations you need to know.

## Architecture

This diagram shows the architecture for the solution.

:::image type="content" source="media/supply-chain-export-inventory-data-dataverse-architecture.png" alt-text="Screenshot of the architecture diagram showing the data flow between Dynamics 365 Supply Chain Management, Inventory Visibility service, Dataverse, and external systems.":::

Download the PowerPoint file for this architecture at [DeltaExportInventoryOnHand-Dataverse-reference-architecture.pptx](https://engagegroupab-my.sharepoint.com/:p:/g/personal/gustav_sundblad_engagegroup_se/Ef9MzlYu3Q5PmPSncNqaHO0B9csDE04MSLR3GeC1_iyKIA?e=Lf5MOe). The link goes to the original contributor's SharePoint site.

## Dataflow

1. Install and activate the Inventory Visibility service. The following sections include links and documentation for this procedure. After you enable the service, low-level replication exports on-hand data changes to Dataverse as they occur.

1. Inventory Visibility relies on in-memory cache for the incoming on-hand requests from external systems (8). However, it always gives actual data, so there's no way to receive only changed data using the API.

1. In the IV-configuration app in Power Apps, enable either the *Inventory Summary* feature or the *Preloaded on-hand* feature. Don't enable both features. Choose one based on your current configuration.

    1. Select *Inventory Summary* if you don't use Advanced Warehousing capabilities.
    1. Select the *Preloaded on-hand* feature if you use Advanced Warehousing capabilities.

1. With either feature enabled, the Inventory Visibility service periodically syncs on-hand information to a Dataverse table (`IS_InventOnHandSum`) containing the inventory dimensions and the current on-hand values in JSON format specified by you in the Inventory Visibility app.

1. At this stage, you can use different scenarios, like exporting your on-hand table from Dataverse to Fabric link, or to your own delta lake using Synapse capabilities.

1. Use the delta tracking capabilities of Dataverse with Power Automate or Logic Apps to track changes on the `IS_InventOnHandSum` table. You can send these data events to an external system, Event Grid, or service bus.

1. Import the data from the `IS_InventOnHandSum` delta event directly into the external system, because it has the on-hand values. Or, use it as a trigger for the external system to update the on-hand values with a synchronous API call to the Inventory Visibility service (8).

## Components

The following components are used in the reference architecture.

- [Dynamics 365 Supply Chain Management](https://www.microsoft.com/dynamics-365/products/supply-chain-management) has the operational inventory data and is the main source of truth in this scenario.
- [Inventory Visibility service](/dynamics365/supply-chain/inventory/inventory-visibility) lets you expose on-hand information from Dynamics 365 and sync the information using Dataverse.
- [Power Automate](https://www.microsoft.com/power-platform/products/power-automate) tracks delta changes in tables in Dataverse so the changes are sent to external systems.
- [Logic Apps](/azure/logic-apps/logic-apps-overview) tracks delta changes similar to Power Automate. You might want to use Logic Apps to build complex integration solutions, use advanced development tools, DevOps, and monitoring, if needed.
- [Fabric Link](/power-apps/maker/data-platform/azure-synapse-link-view-in-fabric) exposes on-hand information in a Delta-Lake format for analytics and reporting (managed by Microsoft).
- [Azure Synapse Link](/power-apps/maker/data-platform/azure-synapse-link-view-in-fabric) exposes on-hand information in a Delta-Lake format for analytics and reporting using Synapse (managed by the customer).

## Scenario details

The Inventory Visibility service solves many historical pain points related to showing on-hand information from Dynamics 365 to external systems. Some architectural patterns, like delta tracking, are still needed in many scenarios. Syncing inventory on-hand from Inventory Visibility to a Dataverse table lets you use these patterns.  

> [!NOTE]
> The architecture causes a small time delay because of the recurring sync from Inventory Visibility to Dataverse.

### Potential use cases

This solution is for any organization with inventory in stock that needs to share this data with surrounding systems in near real time. Examples include companies in retail, manufacturing, or trade industries. Any organization where this pattern is relevant can use the suggested architecture.  

> [!IMPORTANT]
> This pattern isn't meant to reduce over-selling or short-picking scenarios. For these needs, rely on the [soft-reservation](/dynamics365/supply-chain/inventory/inventory-visibility-reservations) functionality in the Inventory Visibility service.

Use this solution to:

- Track changes to on-hand information with delta tracking when using Inventory Visibility service

- Export analytics using Fabric Link (online deployments) or Azure Synapse Link (hybrid deployments) from Dataverse tables with on-hand information.

- Support scenarios in Power Platform that benefit from having on-hand information in a Dataverse table directly instead of relying on API calls.

## Considerations

These considerations help implement a solution that includes Dynamics 365. Learn more in the [Dynamics 365 guidance documentation](../index.yml).

### Cost optimization

Cost optimization is about looking at ways to reduce unnecessary expenses and improve operational efficiencies. Learn more at [Overview of the cost optimization pillar](/azure/architecture/framework/cost/overview).  
  
To apply this architecture pattern, calculate the cost of using either Power Automate or Logic Apps. You might also want to consider Dataverse storage since the tables this architecture uses are stored in Dataverse.

Inventory Visibility is included in licenses for Supply Chain Management along with an entitlement of API requests toward Power Platform. Make sure you review the number of planned requests toward the service against the number of requests you're entitled to according to your licenses. If you enable the data for export to Delta-Lake for analytics purposes, it's important to understand the cost breakdown of using either Fabric Link or Azure Synapse Link. Make the right choice for your specific needs.  

## Implementing Inventory On-Hand using Dataverse and Inventory Visibility Preloaded On-Hand

In order to implement this scenario, you must enable a couple of prerequisites and feature flags in both Supply Chain Management and the Inventory Visibility service. Suggested steps are as follows:

1. Install and configure Inventory Visibility according to the [configuration and setup guide](/dynamics365/supply-chain/inventory/inventory-visibility-setup)

1. Enable either [Inventory Summary](/dynamics365/supply-chain/inventory/inventory-visibility-inventory-summary) or [Preloaded On-Hand](/dynamics365/supply-chain/inventory/inventory-visibility-preload-on-hand) using Feature Management in the Inventory Visibility configuration app. It's automatically installed when following the outlined guide in step 1.

1. Using either [Power Automate](/power-automate/dataverse/overview) or [Logic Apps](/azure/connectors/connect-common-data-service) you can then build a logical flow using the Dataverse connector on the table `IS_InventOnHandSum` (Inventory OnHand Sum).

    :::image type="content" source="media/supply-chain-export-inventory-data-dataverse-configure.png" alt-text="Screenshot of the Power Automate interface showing the Dataverse connector configuration for the IS_InventOnHandSum table.":::

1. The **Quantities** column contains the on-hand data formatted as configured in the Inventory Visibility service. You can send the data to any receiving system or location, or parse it in Power Automate or Logic Apps for further transformation.

    :::image type="content" source="media/supply-chain-export-inventory-data-dataverse-quantities.png" alt-text="Screenshot of the quantities column showing the JSON formatted on-hand data structure in Dataverse.":::

## Related resources

Review the following related architecture guides, solutions, and other guidance content:

- [Inventory Visibility Add-in overview](/dynamics365/supply-chain/inventory/inventory-visibility)
- [Preload a streamlined on-hand query](/dynamics365/supply-chain/inventory/inventory-visibility-preload-on-hand)
- [Inventory Summary](/dynamics365/supply-chain/inventory/inventory-visibility-inventory-summary)
- [Use Dataverse triggers and actions in Power Automate](/training/modules/use-dataverse-triggers-actions/)  
- [Plan to manage costs for Azure Logic Apps](/azure/logic-apps/plan-manage-costs)
- [Dataverse capacity-based storage details](/power-platform/admin/capacity-storage)  
- [Power Automate Pricing](https://www.microsoft.com/en-us/power-platform/products/power-automate/pricing?msockid=08446c876c85670524a47d3b6885617a)  
- [Microsoft Fabric Pricing](https://azure.microsoft.com/pricing/details/microsoft-fabric/)  
- [Pricing - Azure Synapse Analytics](https://azure.microsoft.com/pricing/details/synapse-analytics/)
- [Requests limits and allocations](/power-platform/admin/api-request-limits-allocations#licensed-user-request-limits)  

<!-- ## Tags

*Industries:* Wholesale Trade (50-51), Retail Trade (52-59)

*Stakeholders:* Administrative, IT, Operations, Production, Purchasing,
Retail store operations, Sales, Warehouse

*Products:* Dynamics 365 Commerce, Dynamics 365 Supply Chain Management,
Power Automate, Dataverse, Azure Logic Apps -->

## Contributors

*This article is maintained by Microsoft. It was originally written by
the following contributors.*

Principal author:

- [Gustav Sundblad](https://www.linkedin.com/in/gsundblad/) |
  Technical Solution Architect  
