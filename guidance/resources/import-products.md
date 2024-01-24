---
title: Import product data in Dynamics 365 projects
description: Learn which data entities can help you migrate data for products in Dynamics 365 implementation projects.
ms.date: 05/02/2023
ms.topic: conceptual
author: edupont04
ms.author: katiehav
---

# Import product data in Dynamics 365 projects

***Applies to: Dynamics 365 Commerce, Dynamics 365 Intelligent Order Management, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management***

You can use data entities to import data for goods in Dynamics 365 projects, such as for data migration or integration scenarios. This article outlines the contexts and use cases with links to the relevant entities.  

## Context and problem

Dynamics 365 contains multiple entities for importing products in a Dynamics 365 project. Choosing the best one depends on the type of products that you want to import.

- The **Products V2** entity specifically refers to shared distinct products and product masters. These products are shared between all legal entities and need to be released before using them in transactions.

- The **Released products V2** entity requires that the shared products be already created. When using this entity, the product will be released on the current legal entity.

To create both the shared product and releasing the product to a specific legal entity in one step, use the **Released product creation V2** entity. However, this entity doesn't allow any updates, and the fields available are a limited set.

## Entities

- [Products V2](/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-products-v2-productsv2?toc=/dynamics365/guidance/toc.json)  

- [Released products V2](/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-released-products-v2-releasedproductv2?toc=/dynamics365/guidance/toc.json)  

## Next steps

- Released product creation V2<!--TODO: add links-->  

- Product variants  

- Released product variants  

- Released engineering products creation V2  

## Related resources

- [Product data entities](/dynamics365/supply-chain/pim/data-entities)

- [Data import and export jobs overview](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job)

- [Data management](../implementation-guide/data-management.md)  

- [Data management checklist](../implementation-guide/data-management-check-list.md)

- [Testing strategy](../implementation-guide/testing-strategy.md)  

- [Testing strategy checklist](https://aka.ms/d365-checklist-testing-strategy)  

- [EcoResProductV2Entity in Common Data Model](/common-data-model/schema/core/operationscommon/entities/supplychain/productinformationmanagement/ecoresproductv2entity)

- [EcoResReleasedProductV2Entity in Common Data Model](/common-data-model/schema/core/operationscommon/entities/supplychain/productinformationmanagement/ecoresreleasedproductv2entity)

<!--## Tags

*Stakeholders:* Data migration lead, Developer, Functional consultant, Integration lead, Solution architect

*Products:* Dynamics 365 Commerce, Dynamics 365 Intelligent Order Management, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management-->
