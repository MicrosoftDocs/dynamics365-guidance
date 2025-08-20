--- 
title: Power Pages with Dynamics 365 finance and operations apps 
description: Find out how Power Pages can read data directly from Dynamics 365 finance and operations apps using dual-write or virtual entities for real-time access.
author: Teeeeeeeeeeed
ms.author: edupont
ms.topic: article 
ms.date: 08/20/2025
--- 

# Architecture for Power Pages with Dynamics 365 finance and operations apps

***Applies to: Dynamics 365 Supply Chain Management, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Human Resources, Power Pages, Dual-write, Virtual entities for finance and operations apps, Dataverse, XDS***

This article describes the different ways you can use data from the Dynamics 365 database in Power Pages.

The main use case is when you need external users to work with some of the data run in a solution with finance and operations apps, such as Dynamics 365 Supply Chain Management or Dynamics 365 Finance. For example, you might want to let users work with purchase orders, sales orders, or workers.

There are two main ways that you can support this scenario:

1. Sync data between Dataverse and the Dynamics 365 database by using [dual-write](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview) or other integration engines.

1. Work directly with the Dynamics 365 database by using [Virtual entities for finance and operations apps](/dynamics365/fin-ops-core/dev-itpro/power-platform/virtual-entities-overview).

## Power Pages

[Power Pages](/power-pages/introduction) works with [Dataverse](/power-pages/admin/architecture) and can't run without a Dataverse environment. When your data is in Dataverse, you can create security roles called [web roles](/power-pages/security/power-pages-security) and assign them to a specific external user. This setup lets the user access a predefined subset of data through a Power Pages portal.  

## Dual-write and integration engines

In these scenarios, data for external users is stored in both Dataverse and the Dynamics 365 database. When changes happen in finance and operations, the integration syncs them to Dataverse. After Dataverse updates, Power Pages can read the data. Changes from Power Pages are stored in Dataverse and then synced to Dynamics 365.

These integrations can be trigger-based synchronous, trigger-based asynchronous, or batch-based. Dual-write works for trigger-based synchronous and trigger-based [asynchronous scenarios](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-async).

All communication, regardless of the integration platform, runs through [data entities](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities) for finance and operations apps. Make sure you have data entities that include the data external users need to interact with.

In these scenarios, the integration between Dataverse and the Dynamics 365 database uses admin accounts. You can manage security for external users with [web roles](/power-pages/security/power-pages-security), just like in a stand-alone Dataverse Power Pages solution.

:::image type="content" source="media/finance-operations-power-pages-dual-write.svg" alt-text="Diagram that shows data flowing between Dynamics 365 and Power Pages through dual-write." lightbox="media/finance-operations-power-pages-dual-write.svg":::
<!-- [Download a PowerPoint file](https://github.com/microsoft/dynamics365patternspractices/blob/main/architectures/dynamics-365-finance-operations-dataverse-power-pages.pptx) with this architecture.   -->

## Virtual entities for finance and operations apps

In the scenario with virtual entities for finance and operations apps, Power Pages reads directly from the Dynamics 365 database, and the data is only stored in the Dynamics 365 database.  

You can run data through virtual entities to Power Pages both as [authenticated access and anonymous access](/dynamics365/fin-ops-core/dev-itpro/power-platform/power-portal-reference). In both authenticated and anonymous virtual entities scenarios, you give the external user access to one or more finance and operations data entities and add a web role on them.  

There's a security aspect that's important to keep in mind in these scenarios. By default, you can't restrict a Dynamics 365 user in a specific table or a data entity within the same legal entity from only seeing part of the data.  

Even though you restrict external users' access to the web role, the external user can still use the credentials to directly target the data entity in finance and operations. This way, they can read all the data that the user is allowed to read from the data entity.  

For example, you created a Power Page portal where vendors can sign in and see all their purchase orders and purchase order lines. A vendor should only be able to see its own purchase orders and purchase order lines and not its competitors. The restriction of only seeing your own purchase orders and purchase order lines can be set up in the web role. Still, the possibility of targeting the data entities directly and seeing all your competitor's purchase orders and purchase order lines is there.  

In these scenarios, you must use authenticated access and set up a table to connect the umbrella table that defines what the users can see, in this example a vendor, and the user. Connected to that table, you then build [Extensible data security policies (XDS)](/dynamics365/fin-ops-core/dev-itpro/sysadmin/extensible-data-security-policies) that only allow a user to read data linked to the umbrella table. In the earlier example, that would restrict a vendor from seeing only its own purchase orders and purchase order lines.  

:::image type="content" source="media/finance-operations-power-pages-virtual-entities.svg" alt-text="Diagram that shows data flowing between Dynamics 365 and Power Pages through virtual entities for finance and operations apps." lightbox="media/finance-operations-power-pages-virtual-entities.svg":::

<!-- [Download a PowerPoint file](https://github.com/microsoft/dynamics365patternspractices/blob/main/architectures/dynamics-365-finance-operations-dataverse-power-pages.pptx) with this architecture. -->

## Related content

- [Dual-write](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview) or other integration engines  

- [Dual-write Asynchronous Scenarios](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-async)  

- [Virtual entities for finance and operations apps](/dynamics365/fin-ops-core/dev-itpro/power-platform/virtual-entities-overview)  

- [Data entities for finance and operations apps](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities)  

- [Customer portal for Dynamics 365 Supply Chain Management overview](/dynamics365/supply-chain/sales-marketing/customer-portal-overview)  

- [Power Pages](/power-pages/introduction)  

- [Power Pages Architecture](/power-pages/admin/architecture)  

- [Web roles](/power-pages/security/power-pages-security)  

- [Authenticated access and Anonymous access Portal Access](/dynamics365/fin-ops-core/dev-itpro/power-platform/power-portal-reference)  

- [Extensible data security policies (XDS)](/dynamics365/fin-ops-core/dev-itpro/sysadmin/extensible-data-security-policies)  

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*  

Principal author:

- [Ted Ohlsson](https://www.linkedin.com/in/tedohlsson/) | Dynamics 365 Architect
