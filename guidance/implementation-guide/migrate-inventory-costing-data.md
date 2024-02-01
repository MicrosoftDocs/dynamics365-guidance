---
title: Migrate inventory costing data for your items when using Dynamics 365 Supply Chain Management
description: Read about the process for migrating inventory costing data for your items when you use Dynamics 365 Supply Chain Management to manage your inventory.
ms.date: 08/22/2022
ms.topic: conceptual
author: rachel-profitt
ms.author: raprofit
ms.reviewer: edupont
---

# Migrate inventory costing data for your items when managing your inventory

***Applies to: Dynamics 365 Supply Chain Management***

This article describes the process for migrating inventory costing data for your items when you use Dynamics 365 Supply Chain Management to manage your inventory.

## Background

You need to migrate costs at the time of cut-over to ensure that new transactions are created with the correct cost and that your financials correctly reflect the cost of your items. You will need to migrate your inventory costing data regardless of the costing methodology you use or the industry you are in. However, the industry and costing methodology may have an impact on the approach you use to migrate the inventory costing data.

## Pattern: Load cost components

When you are preparing to load your inventory costs, you will need to carefully plan the steps based on the types of products and services you sell, and the various cost components that you have. There are four key cost components to consider:

1. Raw materials, services, or distributed goods costs  

    If you manufacture items, the raw materials that are part of your bill of materials or formulas will need to have a price. If you don't manufacture items, the items that you purchase and directly distribute to your customers or services that you provide need to have a cost.

2. Indirect costs  

    If you use the **Costing sheets** to calculate indirect costs, also known as *overheads*, for purchased or manufactured items, you must load the indirect costs.

3. Resource costs  

    If you manufacture items and use routes to track the labor related costs of your manufactured goods, you must migrate the resource costs. Such costs are known as *cost categories* in Dynamics 365 Supply Chain Management.

4. Sub assembly or finished good costs  

    When you manufacture goods in your organization, you will need to perform a cost rollup for any sub-assemblies or finished good products to define the sum of the costs

### Prerequisites

Before you can begin to load costs, you will need to ensure that you have defined and configured the following:

* At least one costing version that is not blocked. Learn more at [Costing versions overview](/dynamics365/supply-chain/cost-management/costing-versions).

* Configured the costing sheet in each legal entity, if required. Learn more at [Costing sheets](/dynamics365/supply-chain/cost-management/costing-sheets).

* Configured resources, resource groups, and cost categories, if required. Learn more at [Cost categories used in production routing](/dynamics365/supply-chain/cost-management/cost-categories-used-production-routings).

* BOM Calculation groups are defined and assigned to all items if you are manufacturing items with multi-level BOMs or formulas. Learn more at [BOM calculations groups](/dynamics365/supply-chain/cost-management/bom-calculation-groups).

We recommend that you use the Data management framework to migrate your data related to costs. Learn more at [Data management overview](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities-data-packages). You can use the following entities to import the required data:

* Pending item prices V2 (Load raw material or distributed goods and service prices.)

* Pending route cost category unit costs (load resource costs by cost category.)

* Costing sheet node calculation factors V2 (load indirect costs into the costing sheet.)

### Procedure: Migrate inventory costing data

Use the following steps to migrate your inventory costing data.

1. Use the Data management framework to load all raw material costs into the costing version.

2. Use the Data management framework to load all indirect cost calculations into the costing version.

3. Use the Data management framework to load all cost category prices (for resources) into the costing version.

4. Validate the migrated data.

5. Activate the costing version prices.

6. Perform a cost rollup.

7. Validate the rolled-up costs.

8. Activate the rolled-up costs.

> [!TIP]
> If you are not using standard cost you can still use costing versions to easily manage the purchase prices and costs of your items. Alternatively, you can use trade agreements to manage purchase prices, or the default price fields on the **Released products** page to manage the costs.

<!--### Design considerations (things to watch out for)

If you have Multi-site BOMs, it's super complicated and you have to copy stuff and its hard. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Etiam sagittis elementum ullamcorper. Mauris nec varius justo. Vivamus ante sapien, semper sed enim ut, pulvinar sollicitudin ex. Nulla dictum est libero, at faucibus massa dictum at. Duis ac ultrices ante. Sed dapibus nulla eu sollicitudin porttitor. Cras malesuada, sapien vitae eleifend varius, tellus arcu gravida est, vitae egestas lorem sapien vel felis.-->

## Anti-pattern: Load fully loaded cost prices when using standard cost

When you use standard costing as your costing methodology for one or more items, it is important to note that you should not migrate costs for the semi-finished or finished good type items that have a BOM or Formula. Additionally, you should not use the costing version to manually enter the cost of the semi-finished or finished good product. Instead, you should always perform a cost roll-up by using the Calculation process on the costing version.

If you load or enter costs manually for a semi-finished or finished good product, the system will always calculate a variance when finishing a production order for the difference between the product cost, and the indirect costs and labor costs. These variances will be posted into the related general ledger accounts and make reconciliation difficult. These variances are not a true reflection of the variances on your production process.

## Additional resources

You can use the following resources to learn more about data migration and inventory costing in Dynamics 365 Supply Chain Management.

* [Inventory Costing in Dynamics 365 Supply Chain Management TechTalk Series](https://community.dynamics.com/blogs/post/?postid=a1955d50-c26c-4563-b42c-b1af2261ae6f)

* [Finance and Supply Chain Management: Data Management TechTalk](https://community.dynamics.com/blogs/post/?postid=d555c724-3035-4a1a-a360-56059c4242d9)

* [Data management overview](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities-data-packages)

* [Cost management home page](/dynamics365/supply-chain/cost-management/cost-management-home-page)

<!--## Tags

Industries: Manufacturing; Retail; Distribution

Stakeholder: Cost accountant; Manufacturing SME

Products: Dynamics 365 Supply Chain Management

Configuration stage: Iterative-->
