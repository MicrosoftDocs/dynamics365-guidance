---
title: Import general journals in Dynamics 365 projects
description: Learn which data entities can help you migrate data from general journals in Dynamics 365 implementation projects.
ms.date: 02/02/2024
ms.topic: conceptual
author: edupont04
ms.author: epegors
---

# Import general journals in Dynamics 365 projects

***Applies to Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Intelligent Order Management, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management***

You can use data entities to import data from general journals in Dynamics 365 projects, such as for data migration or integration scenarios. This article outlines the contexts and use cases with links to the relevant entities.  

## Context and problem

There are separate entities for importing general journals with the data management framework (DMF) and OData. The **General journal** entity combines the header and lines into a single entity and supports DMF. We recommend that you use this entity in most scenarios. The **Ledger journal header** entity and **Ledger journal line** entity separate the header and line and support OData, including the Excel add-in.

## Entities

- [General journal](/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-general-journal?toc=/dynamics365/guidance/toc.json)  
- [Ledger journal header](/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-general-journal-ledgerjournalheader?toc=/dynamics365/guidance/toc.json)  
- [Ledger journal line](/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-general-journal-ledgerjournalline?toc=/dynamics365/guidance/toc.json)  

## Next steps

- Learn how to use entities to import sales orders at [Import sales orders](import-sales-orders.md). 
- Learn how to use entities to import customers at [Import data for customers](import-customers.md).  


## Related content

- [General journal processing](/dynamics365/finance/general-ledger/general-journal-processing?toc=/dynamics365/guidance/toc.json)
- [Importing vouchers by using the General journal entity](/dynamics365/fin-ops-core/fin-ops/data-entities/tips-tricks-import-general-journal-entity?toc=/dynamics365/guidance/toc.json)
- [Financial tags](/dynamics365/finance/general-ledger/financial-tag?toc=/dynamics365/guidance/toc.json)
- [Financial journal posting performance](/dynamics365/finance/general-ledger/posting-performance?toc=/dynamics365/guidance/toc.json)
- [Journal posting failure because of imbalance](/dynamics365/finance/general-ledger/posting-fail-imbalance?toc=/dynamics365/guidance/toc.json)
- [Data import and export jobs overview](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job?toc=/dynamics365/guidance/toc.json)


<!-- ## Tags

*Industries:* Healthcare, Financial services, Retail, Manufacturing

*Stakeholders:* Functional consultant, Business analyst, Solution architect, Developer, Data migration lead, Integration lead
 -->
