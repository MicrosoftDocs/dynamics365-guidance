---
title: Manage solution structures for application lifecycles
description: Learn how to use the solution component validation tool to help catch development issues with solution components in Dynamics 365 implementation projects.
author: edupont04
ms.author: ribsingh
ms.topic: how-to
ms.date: 06/17/2026
ms.custom: 
    - bap-template
    - O25-Service
ms.reviewer: edupont
ms.collection:
---

# Manage solution structures for application lifecycles with the solution component validation tool

***Applies to: Dynamics 365 with Dataverse***

Solution management is a core design principle for Dynamics 365 implementations with Dataverse. Many medium-to-large engagements use a multisolution model with horizontal segmentation. This model separates solutions by component type, such as plug-ins, flows, and Power Apps component framework (PCF) controls, to support developer isolation. If teams don't follow this segmentation, solution layering problems and dependency conflicts can occur and take significant time to resolve.

The solution component validation tool provides proactive alerts when solution changes deviate from the intended horizontal segmentation. It helps developers, leads, and Azure DevOps teams maintain agreed-on solution structures for healthier application lifecycle management (ALM). Learn more in [Solutions overview](/power-apps/maker/data-platform/solutions-overview).

## Prerequisites

- [Get the samples and tools.](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/Customer%20Service/ALM/)

The tool is a managed solution that includes the following components.

| Name | Type | Use |
| --- | --- | --- |
| Component Auto Mailer | Entity | Holds configuration data |
| Record Guide | Web Resource | A guide for creating configuration records |
| Solution Auto Mailer Admin | Security Role | Full rights on components |
| Solution Auto Mailer User | Security Role | User-level rights at the component level |
| Solution Component Auto Mailer V2 | Power Automate | Holds the complete logic |

This sample tool provides proactive alerts to developers and leads during the development stage. It also reduces the manual effort to fix layering problems in upstream environments. And, not least, it helps avoid extra delays because of support requests to resolve layering problems.

## Install the tool

1. Download the package from the ALM folder in the [https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/Customer%20Service/ALM/) repo.
1. Open the target environment, go to **Settings**, and then select **Solutions**.
1. Select **Import**, select the zip file, and then import the solution.

Learn more in [Import solutions](/power-apps/maker/data-platform/import-update-export-solutions).

## Configure the tool

1. For each solution that you want to monitor, add a new *component auto mailer* record.
1. Fill in the fields based on the following table.

    | Field | Description |
    |---|---|
    | Solution Name | Enter the name of the solution, such as *Solution Component Auto Mailer*. |
    | Solution Guid | Enter the ID of the solution. You can get this ID from the URL in the maker portal. |
    | Allowlist Component Object Code | List, by object type ID, the components that you expect the solution to include. For example, to allow components of the *Entity* and *Attribute* types, specify `["1","2"]`, including the square brackets. The report includes all other component types if they are added incorrectly to the solution. Learn more in [solutioncomponent EntityType](/power-apps/developer/data-platform/webapi/reference/solutioncomponent?view=dataverse-latest&preserve-view=true). |
    | Owner | Use a semicolon-delimited list of email addresses that should receive the report. |

## The report

The recipients receive an email that shows a list of component types that are added incorrectly to the environment. The email contains the solution ID and the types and IDs of the relevant objects.

## Related information

- [Solution layers with Microsoft Power Platform](/power-platform/alm/solution-layers-alm)
- [Application lifecycle management (ALM) with Microsoft Power Platform](/power-platform/alm/)
- [Application lifecycle management (implementation guide)](../implementation-guide/application-lifecycle-management.md)
- [ALM strategy for Dynamics 365 solutions](../implementation-guide/application-lifecycle-management-product.md#customer-engagement-apps)
