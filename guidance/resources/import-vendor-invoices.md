---
title: Import vendor invoices in Dynamics 365 projects
description: Learn which data entities can help you migrate data for vendor invoices in Dynamics 365 implementation projects.
ms.date: 05/02/2023
ms.topic: conceptual
author: edupont04
ms.author: katiehav
---

# Import vendor invoices in Dynamics 365 projects

***Applies to: Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Intelligent Order Management, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management***

You can use data entities to import data for vendor invoices in Dynamics 365 projects, such as for data migration or integration scenarios. This article outlines the contexts and use cases with links to the relevant entities.  

## Context and problem

Use the **Vendor invoice header** and **Vendor invoice line** entities to import vendor invoices with the most typical fields.

Vendor invoices can also have charges and attachments that must be imported. The **Vendor invoice charges** and **Vendor invoice document attachment V2** entities have a dependency on the vendor invoice header. The **Vendor invoice line charges** entity has a dependency on the vendor invoice line.

## Entities

- [Vendor invoice header](/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-vendor-invoice-header-vendorinvoiceheader?toc=/dynamics365/guidance/toc.json)  

- [Vendor invoice line](/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-vendor-invoice-line-vendorinvoiceline?toc=/dynamics365/guidance/toc.json)  

- [Vendor invoice document attachment V2](/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-vendor-invoice-document-attachment-v2-vendorinvoicedocumentattachment?toc=/dynamics365/guidance/toc.json)  

- [Vendor invoice charges](/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-vendor-invoice-charges-vendorinvoiceheadercharge?toc=/dynamics365/guidance/toc.json)  

- [Vendor invoice line charges](/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-vendor-invoice-line-charges-vendorinvoicelinecharge?toc=/dynamics365/guidance/toc.json)  

## Next steps

- Import vendor payments<!--TODO: add links-->  

## Related resources

- [Financial dimensions](/dynamics365/finance/general-ledger/financial-dimensions)

- [Data import and export jobs overview](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job)

- [Data management](../implementation-guide/data-management.md)  

- [Data management checklist](../implementation-guide/data-management-check-list.md)

- [Testing strategy](../implementation-guide/testing-strategy.md)  

- [Testing strategy checklist](https://aka.ms/d365-checklist-testing-strategy)

<!--## Tags

*Stakeholders:* Data migration lead, Developer, Functional consultant, Integration lead, Solution architect

*Products:* Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Intelligent Order Management, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management-->
