---
title: Solution component validation tool
description: Read how to add a tool to help catch development issues with solution components in Dynamics 365 implementation projects.
author: edupont04
ms.author: ribsingh
ms.reviewer: edupont
ms.topic: how-to #Required; don't change.
ms.collection: #Required; don't change, leave the value blank. 
ms.date: 07/03/2023
ms.custom: bap-template #Required; don't change.
---

# Solution component validation tool

***Applies to: Dynamics 365 with Dataverse***

Solution management is the core design tenet of any Dynamics 365 implementation with Dataverse. Often, medium-to-complete engagements require multi-solution models where solutions are horizontally segmented. Such implementations involve dividing solutions based on the type of components they contain, such as plugins, flows, and PCF controls, with the goal of developer isolation. For these projects, it's important that developers adhere to the segmentation. Otherwise, it can often lead to issues in solution layering issues and dependency conflicts that require fixes that take months to finish and may require support tickets/resolve layering issues.  

This tool provides proactive alerts on such deviations from the horizontal segmentation intended in solutions. It can help developers, leads, and DevOps teams maintain the agreed solution structures for healthy application lifecycle management (ALM). Learn more about solutions and ALM at [Solutions overview](/power-apps/maker/data-platform/solutions-overview).  

## Prerequisites

- [Get the samples and tools](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/ALM/)

The tool is a managed solution that includes the following components:

| Name | Type | Use|
|--|--|--|
| Component Auto Mailer | Entity |Hold configuration data|
| Record Guide | Web Resource|Guide for how to create configuration records|
| Solution Auto Mailer Admin | Security Role |Full rights on components|
| Solution Auto Mailer User | Security Role |User-level rights on component level|
| Solution Component Auto Mailer V2 | Power Automate |Holds the complete logic|

### Benefits from the tool

- Proactive alerts to the developers and leads during the development stage  
- Saves manual efforts of fixing layering issues on Upstream environments  
- Helps avoid addition delays due to support requests to resolve layering issues  

## Installation

1. Download the package at [ALM](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/ALM/)  
2. Open the target environment, go to **Settings**, and then choose **Solutions**.  
3. Choose the **Import** button, choose the .zip file, and then import the solution.  

Learn more at [Import solutions](/power-apps/maker/data-platform/import-update-export-solutions).  

## Configuration steps

Learn how to configure the solution.  

1. For each solution you want to monitor, add a new *component auto mailer* record.
2. Fill in the fields based on the following table:

    |Field  |Description  |
    |---------|---------|
    |Solution Name | The name of the solution, such as *Solution Component Auto Mailer*|
    |Solution Guid  |The ID of the solution, which you can get from the URL in the maker portal. |
    |Allowlist Component Object Code|List by object type ID the components that you expect to be included in the solution. For example, specify `[*1*,*2*]` to exclude components of type Entity and Attribute from the report, including the square brackets. The report includes all other components types if they're added incorrectly to the solution. Learn more at [solutioncomponent EntityType](/power-apps/developer/data-platform/webapi/reference/solutioncomponent?view=dataverse-latest&preserve-view=true). |
    |Owner  |Use a semi-colon delimited list of email addresses to receive the report. |

## The report

The recipients receive an email with a list of component types that have been added to the environment incorrectly. The email contains the solution ID and the types and IDs of the relevant objects.  

## Related content

- [Solution layers with Microsoft Power Platform](/power-platform/alm/solution-layers-alm)  
- [Application lifecycle management (ALM) with Microsoft Power Platform](/power-platform/alm/)  
- [Application lifecycle management (implementation guide)](../implementation-guide/application-lifecycle-management.md)  
- [ALM strategy for Dynamics 365 solutions](../implementation-guide/application-lifecycle-management-product.md#customer-engagement-apps)  
