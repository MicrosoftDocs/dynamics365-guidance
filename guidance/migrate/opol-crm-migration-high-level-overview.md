---
title: Dynamics CRM on-premises to Dynamics 365 migration process overview
description: Learn about the migration process from Dynamics CRM to Dynamics 365 (OP2OL), how to validate solutions and customizations, and understand the post-migration processes.
author: dereklh77
ms.author: ratrtile
ms.topic: article
ms.date: 05/08/2024
---

# Dynamics CRM (on-premises) to Dynamics 365 online migration process overview

Microsoft provides guidance on migrating your Dynamics CRM (on-premises) database to [Dynamics 365 and Microsoft Dataverse](/power-apps/maker/data-platform/data-platform-intro#dynamics-365-and-dataverse). The guidance is provided in the form of tools and support from the migration factory team.  

## Eligibility

The tool and migration support are available to all organizations and Microsoft partners that use supported versions of Dynamics CRM (on-premises).  

> [!NOTE]
> Make sure that you check the product documentation for the supported versions.

The following table provides an overview of the supported versions.

|Product  |Supported versions|
|---------|---------|
|Dynamics CRM (on-premises) | Dynamics CRM 2015 or later.|
|SQL Server   | Any version of SQL Server that the relevant version of Dynamics CRM supports.|

## Nomination form

Microsoft partners can nominate their customers for migration using the nomination form at [https://aka.ms/op2olnom](https://aka.ms/op2olnom). Learn more about the steps to take in [the whitepaper](#op2ol-whitepaper) for the on-premises to online (OP2OL) migration process.

<!-- Learn more about eligibility at [Customer eligibility and partner qualifications](../fasttrack/eligibility.md). -->

> [!NOTE]
> - To perform the migration, your source environment must be a version of Dynamics CRM 2015, or Dynamics CRM 2016, or Dynamics 365 (9.0/9.1). Also, SQL Server must be aligned with the supported/compatible versions.
>
> - Customers must procure licenses to Dynamics 365 online before they start the migration process. Learn more in [the OP2OL whitepaper](#op2ol-whitepaper).
>
> - This program requires the customer or engaged partner to fix or mitigate any unsupported customizations or SQL Server-level changes that might block the database migration.

## Migration process overview

The technical migration orchestration is carried out through the tooling hosted in the [Dynamics Lifecycle Services portal](https://lcs.dynamics.com/). Microsoft makes the Dynamics Lifecycle Services portal available to you in accordance with an agreement to use the migration tooling to manage the migration process. All migrations require appropriate access and permission to the Lifecycle Services portal.

> [!NOTE]
> We strongly recommend that you familiarise yourself with the migration process by reviewing [the OP2OL whitepaper](#op2ol-whitepaper).

## OP2OL whitepaper

You can find detailed information on the OP2OL migration process in our comprehensive whitepaper that you download at [https://aka.ms/op2olwhitepaper](https://aka.ms/op2olwhitepaper). This technical document outlines the prerequisites and provides a step-by-step guide to the migration process.

## Related resources

- [What is FastTrack for Dynamics 365?](../fasttrack/overview.md)  
- [On-premises to online migration - Dynamics 365 blog](https://community.dynamics.com/blogs/post/?postid=d6f2297c-5f43-405e-9471-63d8fbe88118)  
- [On-premises to online migration - Part 2 - Dynamics 365 blog](https://community.dynamics.com/blogs/post/?postid=9a71e640-9d17-ee11-8f6e-000d3a4e9eae)  
