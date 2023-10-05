---
title: Import sales orders in Dynamics 365 projects
description: Learn which data entities can help you migrate data for sales orders in Dynamics 365 implementation projects.
ms.date: 05/02/2023
ms.topic: conceptual
author: edupont04
ms.author: katiehav
---

# Import sales orders in Dynamics 365 projects

***Applies to: Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Intelligent Order Management, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management***

You can use data entities to import data for sales orders in Dynamics 365 projects, such as for data migration or integration scenarios. This article outlines the contexts and use cases with links to the relevant entities.  

## Context and problem

Dynamics 365 contains two entities for importing and updating sales orders:

- **Sales order headers V2**  

  Creates the general specifications of the order.
- **Sales order lines V2**  

  Creates the lines, including the specific concepts such as items, quantities, and sales price.

You must first create the headers of sales orders before you import the lines. Sales lines are always related to a specific header.

## Entities

- [Sales order headers V2](/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-sales-order-headers-v2-salesorderheaderv2?toc=/dynamics365/guidance/toc.json)  

- [Sales order lines V2](/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-sales-order-lines-v2-salesorderline?toc=/dynamics365/guidance/toc.json)  

## Next steps

- Import customer payments<!--TODO: add links-->  

## Related resources

- [Create sales orders](/dynamics365/supply-chain/sales-marketing/tasks/create-sales-orders)

- [Frequently asked questions about sales orders](/dynamics365/supply-chain/sales-marketing/sales-orders-faq)

- [Financial dimensions](/dynamics365/finance/general-ledger/financial-dimensions)

- [Data import and export jobs overview](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job)

- [Data management](../implementation-guide/data-management.md)  

- [Data management checklist](../implementation-guide/data-management-check-list.md)

- [Testing strategy](../implementation-guide/testing-strategy.md)  

- [Testing strategy checklist](https://aka.ms/d365-checklist-testing-strategy)

- [SalesOrderHeaderV2Entity in Common Data Model](/common-data-model/schema/core/operationscommon/entities/supplychain/salesandmarketing/salesorderheaderv2entity)

- [SalesOrderLineV2Entity in Common Data Model](/common-data-model/schema/core/operationscommon/entities/supplychain/salesandmarketing/salesorderlinev2entity)

<!--## Tags

*Stakeholders:* Data migration lead, Developer, Functional consultant, Integration lead, Solution architect

*Products:* Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Intelligent Order Management, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management-->
