---
title: Balance Inventory Between Dynamics 365 and External WMS
description: Optimize inventory management with Dynamics 365 and an external WMS by identifying discrepancies using Azure Synapse, Data Lake, and Power BI.
#customer intent: As a Dynamics 365 consultant, I want to recommend best practices for integrating with external WMS systems so that I can ensure a resilient implementation.
author: edupont04
ms.author: edupont
ms.reviewer: edupont
ms.date: 09/26/2025
ms.topic: reference-architecture
---
# Inventory balance between Dynamics 365 and an external warehouse management system

***Applies to***: ***Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Azure Logic Apps, Azure Data Lake, Azure Synapse, Power BI***

Organizations want to review and audit inventory differences between their financial backend and their external warehouse management system (WMS). This solution combines Dynamics 365 Finance and Dynamics 365 Supply Chain Management with Azure Logic Apps, Azure Data Lake, and Azure Synapse to manage inventory differences between Dynamics 365 and an external WMS. The reference architecture balances inventory between Dynamics 365 and an external WMS by snapshotting inventory from both systems into Azure Data Lake and Azure Synapse, and then compares them in Power BI to find significant discrepancies in quantity and valuation.

## Introduction

Many companies dealing with consumer products use an external WMS with Dynamics 365. When an external WMS is in scope, evaluate integrations and architecture during the Initiate/Design phase, and review them during the solution blueprint review.

IT, finance, and WMS operations should align on the architecture and process.

When an external WMS is involved, the external WMS is often the system of record for inventory quantity, and Dynamics 365 is the system of record for transactional data and inventory valuation. Because inventory values can get out of balance for various reasons (timing of inventory comparisons, failed integration transactions, and user errors in the warehouse), perform a periodic inventory review between the two systems.

Dynamics 365 and most WMS providers, such as Manhattan, don't recommend automating the inventory balance process. Typical reasons include the following list:

- False inventory difference errors caused by timing issues in inventory snapshots
- False inventory difference errors caused by failed integration transactions
- Automatic difference resolution makes it hard to identify systematic issues
- Large (1,000+ line) counting journals are hard to evaluate, troubleshoot, and post in a live system
- Splitting journals makes them easier to manage but harder for finance to see the overall impact of the adjustment

As a result, the industry is moving away from automated sync and toward weekly, manual identification and evaluation of inventory that's out of balance.

## Architecture and data flow

The following diagram illustrates the architecture for the solution.

:::image type="content" source="media/supply-chain-external-wms-item-balance-architecture.png" alt-text="Screenshot of a diagram illustrating inventory snapshot and ETL flow between Dynamics 365, WMS, and Azure Synapse." lightbox="media/supply-chain-external-wms-item-balance-architecture.png":::

<!-- Download a Visio file with this architecture. -->

1. An Azure Logic App coordinates a snapshot request of inventory in both systems.  

    Request the snapshot at the same time in both systems and when activity is low to minimize the risk that posted transactions cause false discrepancies.
1. Dynamics 365 sends an export of stock on-hand and inventory valuation data for the warehouses that the external WMS manages to Azure Synapse. Here, an Extract, Transform, Load (ETL) data integration process can occur for Power BI reporting.
1. The external WMS sends a snapshot of on hand data to Azure Synapse, where an ETL can occur for Power BI reporting.
1. Transform data so users sign in to Power BI and quickly find material inventory discrepancies based on quantity or value thresholds.  

    For example, an organization might handle low-cost items and high-cost items. An inventory discrepancy for a high-cost item might be worth investigating even if the quantity difference is small. Likewise, an organization might handle low-cost items where investigating a difference of a few units isn't a good use of resources.
1. If there's no inventory discrepancy, then the process is over until it repeats on the next recurring schedule.
1. If there's an inventory discrepancy, the next step is to perform a count in the external WMS system.
1. A Logic App looks for pending inventory adjustments and transmits them to Dynamics 365.
1. Based on the scenario, a counting journal or a movement journal can be transmitted from the WMS.  

    A counting journal can be used to "set" the inventory value, while a movement journal or adjustment journal can be used to adjust the inventory. A movement or adjustment journal can help if the journal doesn't post immediately and other transactions occur, once all transactions post, the balances between the WMS and Dynamics 365 should match.

    An out of the box data entity can be used to create the journal with manual posting, or a small customization to automate the posting.

    In scenarios with higher complexity or volume, a custom data entity is often preferred to optimize performance and error handling. If the data entity has a processing class that moves data from a staging table to a counting journal and posts the journal. If the journal fails to post, some organizations roll back the journal and mark the records as "errored" in the staging table.

    Use data package APIs or recurring integrations with either strategy.
1. If these steps don't balance inventory between Dynamics 365 and the external WMS, or if the same item is unbalanced for multiple weeks, evaluate a transaction audit between the systems. Also check for process issues in the physical WMS.

## Components

Use the following components in the reference architecture.

- [Dynamics 365 Finance](https://www.microsoft.com/dynamics-365/products/finance) and [Dynamics 365 Supply Chain Management](https://www.microsoft.com/dynamics-365/products/supply-chain-management) are cloud-based business management solutions and the core systems in this architecture.  

- [Azure Logic Apps](/azure/logic-apps/logic-apps-overview) integrates systems and orchestrates inventory balances between systems.

- [Azure Synapse Analytics](https://azure.microsoft.com/products/synapse-analytics) merges and transforms data from systems for human consumption and stores it for analysis.  

- [Power BI](https://www.microsoft.com/power-platform/products/power-bi) identifies material discrepancies and visualizes trends over time. Declining inventory discrepancies indicate improved processes and system resilience, and increasing discrepancies are a red flag for investigation.  

## Scenario details

This architecture is based on joint experience from Manhattan WMS consultants and Dynamics 365 consultants who balance inventory for product companies. Often, even a smaller product catalog (1,000 active SKUs) can cause problems if the inventory balance process isn't planned correctly. Modern ERPs put more business logic into transactional posting, which might not exist in legacy systems. As a result, when you implement Dynamics 365, you might assume the wrong best practices. What worked in the legacy system might not be appropriate in Dynamics 365.

This architecture draws on experience from many Dynamics 365 implementations that integrate with external WMSs, and is the most resilient design at go-live.

### Potential use cases

This solution is for organizations that use Dynamics 365 Finance or Dynamics 365 Supply Chain Management with an external WMS.

## Considerations

These considerations help implement a solution that includes Dynamics 365. Learn more at [Dynamics 365 guidance documentation](/dynamics365/guidance/).

### Cost optimization

Cost optimization reduces unnecessary expenses and improves operational efficiency. Learn more at [Overview of the cost optimization pillar](/azure/architecture/framework/cost/overview).

- For Dynamics 365 Finance and Dynamics 365 Supply Chain Management, the reference architecture assumes that no extra licenses are required.

- For Azure Logic Apps, if the organization uses a consumption-based pricing plan, this architecture likely consumes less than \$1.00/month. If an external WMS is involved, it's probably one of many integrations and should be part of the overall integration platform cost and strategy. Learn more at [Azure Logic Apps pricing](https://azure.microsoft.com/pricing/details/logic-apps/).

- For Azure Synapse, the organization might already have a license in place as part of a reporting strategy. Potentially, more compute and storage requirements are negligible. If cost is an issue, reduce the amount of historical inventory balance data you store. That reduces your ability to evaluate trends. Learn more at [Azure Synapse pricing](https://azure.microsoft.com/pricing/details/synapse-analytics/).

- For Power BI, the organization might already have a license in place as part of a reporting strategy. Learn more at [Power BI pricing](https://www.microsoft.com/power-platform/products/power-bi/pricing).

## Implementation Considerations

When you design integration with an external WMS, an important consideration is whether or not to allow inventory to go negative. If inventory is allowed to go negative, there are more inventory discrepancies when performing an inventory balance. However, inventory transactions can then flow and post more successfully on a day-to-day basis. Rather than the same item causing errors on multiple transactions, it might only show once as out of sync during the inventory balance process. A minor customization may be needed to keep from reserving negative inventory.

## Related resources

Review the following related architecture guides, solutions, and other guidance content:

- [Dynamics 365 Inventory Management Overview](/dynamics365/supply-chain/inventory/inventory-home-page)
<!-- 
## Tags

*Industries:* Wholesale Trade (50-51), Retail Trade (52-59)

*Stakeholders:* Finance, IT, Merchandising, Operations, Production, Purchasing, Retail store operations, Warehouse

*Products:*

Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Azure Logic Apps, Azure Data Lake, Azure Synapse -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Curt McDonald](https://www.linkedin.com/in/curtis-mcdonald-096b0283/) | Delivery Director
