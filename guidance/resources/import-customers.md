---
title: Import data for customers in Dynamics 365 projects
description: Learn which data entities can help you migrate data for customer in Dynamics 365 implementation projects.
ms.date: 02/02/2024
ms.topic: conceptual
author: edupont04
ms.author: katiehav
---

# Import data for customers in Dynamics 365 projects

***Applies to: Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Intelligent Order Management, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management***

You can use data entities to import data for customers in Dynamics 365 projects, such as for data migration or integration scenarios. This article outlines the contexts and use cases with links to the relevant entities.  

## Context and problem

Dynamics 365 contains multiple entities for importing customers in a Dynamics 365 project. Choosing the best one requires understanding the similarities and differences between the available entities. The **Customer definitions** entity is recommended for most scenarios. The **Customer definitions** entity, when combined with the **Customers details V2** entity, supports most of the same functionality as the **Customers V3** entity.  

The highest performance can usually be achieved using a combination of the **Customer definitions** and **Customer details V2** entities. In most cases, using one of those entities, or even using both of them, one after the other, will outperform the **Customers V3** entity.  

Use the **Customers V3** entity when any of the approximately 80 fields that aren't supported by the **Customer definitions** and **Customer details V2** entities must be included in the import.

## Entities

- [Customer definitions](/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-customer-definitions-customerbase?toc=/dynamics365/guidance/toc.json)  

- [Customers V3](/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-customers-v3-customerv3?toc=/dynamics365/guidance/toc.json)  

- [Customer details V2](/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-customer-details-v2-na?toc=/dynamics365/guidance/toc.json)  

## Next steps

- Learn how you can use entities to import sales orders at [Import sales orders](import-sales-orders.md)  

- Learn how you can use entities to import customer free text invoices<!--TODO: add links-->  

- Learn how you can use entities to import customer payment journals  

- Learn how you can use entities to import general journals [Import general journals](import-general-journals.md)  

## Related information

- [Financial dimensions](/dynamics365/finance/general-ledger/financial-dimensions)
- [Data import and export jobs overview](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job)
- [Data management](../implementation-guide/data-management.md)  
- [Data management checklist](../implementation-guide/data-management-check-list.md)
- [Testing strategy](../implementation-guide/testing-strategy.md)  
- [Testing strategy checklist](../implementation-guide/testing-strategy-checklist.md)

<!--## Tags

*Stakeholders:* Data migration lead, Developer, Functional consultant, Integration lead, Solution architect

*Products:* Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Intelligent Order Management, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management-->
