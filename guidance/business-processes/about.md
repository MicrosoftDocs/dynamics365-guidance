---
title: About the business process catalog for Dynamics 365 apps
description: Learn about the business process catalog for Dynamics 365, what it is, and how to navigate and learn from the catalog.
author: edupont04
ms.author: edupont
ms.topic: conceptual #Required; don't change.
ms.date: 07/11/2024
ms.custom: bap-template #Required; don't change.
---

# About the business process catalog for Dynamics 365 apps and services

Microsoft has established a business process catalog of standard business processes across Dynamics 365 apps and services. Read on to learn how to navigate and learn from the catalog.  

> [!TIP]
> [!INCLUDE [daf-business-process-def](~/../shared-content/shared/guidance-includes/daf-business-process-def.md)] [!INCLUDE [daf-business-process-def2](~/../shared-content/shared/guidance-includes/daf-business-process-def2.md)]

## What is the catalog?

The business process catalog is an Excel workbook that we at Microsoft use to organize and prioritize our work on the business process documentation. The format is Excel because it makes it easy to sort and filter the entries. We also believe our partners can use the Excel workbook to organize their onboarding journeys, their implementation projects, and their own business processes. Learn more about the content in the [What's in the catalog?](#whats-in-the-catalog) section.  

[!INCLUDE [daf-catalog-ids](../includes/daf-catalog-ids.md)] Learn more in the [Catalog IDs](#catalog-ids) section.

[!INCLUDE [daf-catalog-get](../includes/daf-catalog-get.md)]  

## What's in the catalog?

[!INCLUDE [daf-bus-proces-catalog](~/../shared-content/shared/guidance-includes/daf-bus-proces-catalog.md)]

We plan to cover each level of the catalog. The result will be guidance about how to configure Dynamics 365 to meet most use cases and scenarios. Our goal is to help our customers and partners define the scope of their implementation projects. Start from our standard business processes, and accelerate your success and implementation. We hope you can then focus on the processes that make your business unique. Work with your implementation partner to identify which business processes and patterns are relevant at the beginning of your project. Also, review the [Processes](../implementation-guide/solution-architecture-design-pillars-processes.md) solution architecture design pillar.  

New and updated content publishes to [Microsoft Learn](/dynamics365/guidance/business-processes/) every two weeks.  

## How to read the business process descriptions

The business process articles contain abbreviations that you won't see anywhere else. The abbreviations represent the different Dynamics 365 apps, services, and related portals. We hope they make it easier to quickly scan the various tables. Get an introduction to this type of shorthand at [Business processes, steps, and how to find things](about-steps-navigation.md).  

> [!TIP]
> Find definitions of business terms at [Glossary of terms](glossary.md).  

## Business process flow diagrams

Each article, be it for an end-to-end scenario or a pattern, includes a diagram that shows how that business process fits into the work of a typical organization. We share the diagrams as PowerPoint presentations in a GitHub repo so that each organization can choose to download a flow diagram and customize it to fit their particular workflow.  

Find the source files at [https://aka.ms/businessprocessflow](https://aka.ms/businessprocessflow).

> [!NOTE]
> When you navigate to the specified link, you can't view the .pptx files in GitHub. Instead, you can download the files by opening the file's page on GitHub, then selecting the **Download raw file** option.

## Catalog IDs

[!INCLUDE [daf-catalog-ids](../includes/daf-catalog-ids.md)]

But when you download the business process catalog, you'll find each entry assigned a unique ID. The IDs start with a number for each end-to-end scenario. Each level below the end-to-end scenario has an ID that starts with the ID of each parent entry.  

For example, let's look at the *administer to operate* end-to-end scenario. The following table provides a quick introduction to how IDs are generated based on four entries in the business process catalog from May 2024.

|Level  |ID  |Description  |
|---------|---------|---------|
|End-to-end scenario | 99 | ID for the end-to-end scenario, *administer to operate*. |
|Business process areas overview |99.10 |ID for the business process area *Define business continuity plan* that is part of the *administer to operate* end-to-end scenario. |
|Business process |99.10.010  |ID for the business process *Define business continuity objectives* that is part of the *Define business continuity plan* business process area. |
|Pattern |99.10.010.100|ID for the pattern *Understand Dynamics 365 RTO and RPO* that is part of the *Define business continuity objectives* business process. |

The IDs of the end-to-end scenarios are similar to the Standard Industrial Classification (SIC) codes that the U.S. government assigns to business establishments to identify the primary business of the establishment. The first two digits of a SIC code defines the major industry group that a business belongs to. Learn more at [What is a SIC Code?](https://siccode.com/page/what-is-a-sic-code).

For industries across the world, the International Standard Industrial Classification of All Economic Activities (ISIC) is the international reference classification of productive activities. It provides a set of activity categories that can be utilized for the collection and reporting of statistics according to such activities. Learn more at [Department of Economic and Social Affairs at United Nations](https://unstats.un.org/unsd/classifications/Econ/isic).

But an end-to-end scenario can apply to businesses across two or more industries. So the IDs are not the same as SIC or ISIC codes. It's the system of hierarchies of unique IDs that we have loosely based on the ISIC and SIC categories. The only exception is the *Administer to operate* end-to-end scenario that got its ID 99 from the SIC code for *Administration of Nonclassifiable Establishments*.  

## Get notified about changes through an RSS feed

[!INCLUDE [daf-rss](../includes/daf-rss.md)]

## Contribute

Internally at Microsoft, we're working hard to convert internal notes, years of experience, and various documents into business process guidance. We very much welcome contributions from the community. Help us establish patterns, identify business processes, or provide alternatives.

[!INCLUDE [daf-business-process-register](~/../shared-content/shared/guidance-includes/daf-business-process-register.md)]

[!INCLUDE [daf-business-process-submit](~/../shared-content/shared/guidance-includes/daf-business-process-submit.md)]
Optionally, add your LinkedIn profile so that you can be listed as the original author.

Learn more at [External contributions to Microsoft's documentation](/dynamics365/get-started/contribute).  

## Related information

- [Understand concepts and terminology used in the Dynamics 365 business process guide](about-steps-navigation.md)  
- [Use the business process catalog as a template in Azure DevOps Services](about-import-catalog-devops.md)  
- [Import the business process catalog in Mavim using a Power Automate flow](about-import-catalog-mavim.md)  
- [Process maturity overview](process-maturity-introduction.md)  
- [Standardize business processes during a Dynamics 365 implementation](standardize-business-processes.md)  
- [Overview of end-to-end scenarios and business processes in Dynamics 365](overview.md)  
