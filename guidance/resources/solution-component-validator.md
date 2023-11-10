---
title:  Solution component validation tool
description: Learn how to add a tool to help catch development issues with solution components in Dynamics 365 implementation projects.
author: edupont04
ms.author: ribsingh
ms.reviewer: edupont
ms.topic: how-to #Required; don't change.
ms.collection: #Required; don't change, leave the value blank. 
ms.date: 10/23/2023
ms.custom: bap-template #Required; don't change.
---

# Solution component validation tool

***Applies to: Dynamics 365 with Dataverse***

Solution management is the core design tenet of any Dynamics 365 implementation with Dataverse. Medium-to-complete engagements often require multi-solution models where the solutions are horizontally segmented. Implementations of this type involve dividing solutions based on the type of components that they contain (for example, plugins, flows, and PCF controls), to achieve developer isolation. For these projects, it's important that developers adhere to the segmentation. Otherwise, solution layering issues and dependency conflicts can occur that take months to finish fixing and might require support tickets/resolve layering issues.

The Solution component validation tool provides proactive alerts about deviations from the intended horizontal segmentation in solutions. It can help developers, leads, and Azure DevOps teams maintain the agreed-on solution structures for healthy application lifecycle management (ALM). Learn more about solutions and ALM in [Solutions overview](/power-apps/maker/data-platform/solutions-overview).

## Prerequisites

- [Get the samples and tools.](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/ALM/)

The tool is a managed solution that includes the following components.

| Name | Type | Use |
|---|---|---|
| Component Auto Mailer | Entity | Holds configuration data |
| Record Guide | Web Resource | A guide for creating configuration records |
| Solution Auto Mailer Admin | Security Role | Full rights on components |
| Solution Auto Mailer User | Security Role | User-level rights at the component level |
| Solution Component Auto Mailer V2 | Power Automate | Holds the complete logic |

### Benefits from the tool

- Provides proactive alerts to developers and leads during the development stage
- Saves manual efforts of fixing layering issues on upstream environments
- Helps avoid additional delays because of support requests to resolve layering issues

## Installation steps

1. Download the package from [ALM](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/ALM/).
1. Open the target environment, go to **Settings**, and then select **Solutions**.
1. Select **Import**, select the zip file, and then import the solution.

Learn more in [Import solutions](/power-apps/maker/data-platform/import-update-export-solutions).

## Configuration steps

1. For each solution that you want to monitor, add a new *component auto mailer* record.
1. Fill in the fields based on the following table.

    | Field | Description |
    |---|---|
    | Solution Name | Enter the name of the solution, such as *Solution Component Auto Mailer*. |
    | Solution Guid | Enter the ID of the solution. You can get this ID from the URL in the maker portal. |
    | Allowlist Component Object Code | List, by object type ID, the components that you expect the solution to include. For example, to allow components of the *Entity* and *Attribute* types, specify `["1","2"]`, including the square brackets. The report includes all other component types if they are added incorrectly to the solution. Learn more in [solutioncomponent EntityType](/power-apps/developer/data-platform/webapi/reference/solutioncomponent?view=dataverse-latest&preserve-view=true). |
    | Owner | Use a semicolon-delimited list of email addresses that should receive the report. |

## The report

The recipients receive an email that shows a list of component types that have been added incorrectly to the environment. The email contains the solution ID and the types and IDs of the relevant objects.

## Related content

- [Solution layers with Microsoft Power Platform](/power-platform/alm/solution-layers-alm)
- [Application lifecycle management (ALM) with Microsoft Power Platform](/power-platform/alm/)
- [Application lifecycle management (implementation guide)](../implementation-guide/application-lifecycle-management.md)
- [ALM strategy for Dynamics 365 solutions](../implementation-guide/application-lifecycle-management-product.md#customer-engagement-apps)
