---
title: Sync Dynamics 365 Processes from Mavim to Azure DevOps
description: Use Mavim to capture requirements and gaps during the Dynamics 365 Initiate phase, then sync processes into Azure DevOps Services. Discover the step-by-step guide.
#customer intent: As a Dynamics 365 implementation consultant, I want to synchronize the enriched business process catalog from Mavim into Azure DevOps, so that I can manage the implement phase of the project using captured requirements and gaps.
author: edupont04
ms.author: raprofit
ms.date: 05/27/2026
ms.topic: concept-article
---

# Sync Dynamics 365 processes from Mavim to Azure DevOps

This article describes how you can use Microsoft's business process catalog in the business process management platform Mavim during the *Initiate* (or design) phase of a Dynamics 365 implementation project. You can synchronize the enriched set of processes into Azure DevOps Services to manage the *Implement* phase of the project. Mavim is a business process management platform that you can find in the [Microsoft Marketplace](https://marketplace.microsoft.com/en-us/product/saas/mavimbv1671629332610.mavim_bpm?tab=Overview).

## A process-focused approach to discovering gaps and requirements

Requirements gathering and the discovery of gaps are essential in the *Initiate* phase of your Dynamics 365 implementation project. They help you define the scope of your project and identify how well the system's configuration and functionality meet your business needs.

A process-focused approach ensures that the context of requirements and gaps is clear to all stakeholders. You can import the business process catalog into Mavim, and you can then create new instances of the catalog's entries to facilitate each implementation project.

Mavim accelerates the *Initiate* phase of the implementation project by allowing you to capture requirements and gaps from a process approach. The out-of-the-box processes in the catalog can be adjusted to reflect the desired way of working in the organization. The requirements and gaps can then exactly be matched to the (redesigned/optimized) processes and assure a clear understanding of how Dynamics 365 will be configured and ultimately support the business.

## Prerequisites

This article assumes that you already have a Mavim environment and imported the catalog into your Mavim environment. If you want to use Mavim in the *Initiate* phase of a Dynamics 365 implementation project and you want to capture gaps and requirements, you first need to add fields for this in Mavim and make sure these fields are applied to all processes.

The Power Automate flows require the following fields in the relevant Azure DevOps Services project:

| Field | Description |
| --------- | --------- |
| Status | Specifies the status of the process. For example, is it in scope or out of scope in the current implementation project. |
| Extensions | Type of extension needed for this process. |
| Gap description | Description of the gap. |
| Priority | What is the priority of this process. |
| Risk | What is the risk of this process. |
| Effort | What is the indicated effort for implementing this process. |
| Time Criticality | What is the time criticality of this process. |
| ADO WorkItemID | ID of the created work item for this process. |
| ADO WorkItemURL | URL to the created work item for this process. |

The Power Automate flow that manages the synchronization automatically sets the values for Azure DevOps work item ID and URL. The interactive Mavim platform facilitates discussion of process diagrams. You can add requirements, fit-gap analysis, and process adjustments directly in the workshops.

:::image type="content" source="media/about-catalog-mavim-azure-devops-sync.png" alt-text="Screenshot of Mavim Portal showing process diagram for Set customer credit limits beside fit gap analysis fields." lightbox="media/about-catalog-mavim-azure-devops-sync.png":::

## Import the synchronization Power Automate solution

By adding fields for capturing fit gap analysis and requirements, you can capture relevant information in the **Initiate** phase of the implementation project. At the end of the initiate phase, you can synchronize the entire set of processes in the catalog, together with the captured information on requirements and gaps, into an empty Azure DevOps project.

This synchronization requires that you have corresponding fields in your Azure DevOps project template. A Power Automate solution is available for the synchronization of processes in Mavim into work items in Azure DevOps. Since you can add your own fields in Mavim and in Azure DevOps, the Power Automate solution is a starter kit that gives you a working integration that you can extend to synchronize also the custom fields you added.

> [!IMPORTANT]
> The link to download the solution will be added when the files become available.<!--You can find the Business Process Catalog in Mavim to Azure DevOps solution here. TODO: add link to download -->

After you import this solution and make the connections to Mavim and to Azure DevOps, you can either directly run the synchronization flow or adjust the flow for the additional fields.

The Power Automate solution starter kit facilitates two approaches for the synchronization:

- Create a direct connection between Mavim and Azure DevOps.

  This approach uses two Power Automate flows:

  - **Synchronize Business Process Catalog in Mavim to Azure DevOps – Get the processes**

    This is the flow you must run. It asks for a `MavimStartTopicDCV` value. This value is the ID of the start topic in Mavim that holds all processes. For each process, this flow runs the second Power Automate flow.

  - **Synchronize Business Process Catalog in Mavim to Azure DevOps – Create a workitem**

    This flow creates a work item in Azure DevOps. This flow is called by the other flow for each process.

- Export the catalog processes (with your additional requirement and gap fields) to a CSV file that is suited for import in Azure DevOps. We recommend that you store the CSV file on a SharePoint site or on OneDrive.

  > [!NOTE]
  > Make sure the CSV file complies with the fields in the Azure DevOps project template that you use.

## Next steps

- Follow the [process-focused approach](../implementation-guide/process-focused-solution.md) of the Success by Design methodology when implementing Dynamics 365.

- Use the business process catalog in Mavim. Learn more at [Navigate the business process catalog in Mavim](about-catalog-mavim-navigate-business-process-catalog.md).

## Related content

- [Import the business process catalog in Mavim using the Mavim database file](about-import-catalog-mavim-database.md)  
- [Mavim.com](https://www.mavim.com/)

  - [Business Process Management For A Dynamics 365 Implementation: Beyond Diagnostics (Mavim)](https://blog.mavim.com/business-process-management-for-a-dynamics-365-implementation-beyond-diagnostics)
  - [Mavim opens up to the Microsoft Power Platform to facilitate hyper automation (Mavim)](https://blog.mavim.com/mavim-opens-up-to-the-microsoft-power-platform-to-facilitate-hyperautomation)

## Contributors

The following contributors authored this article:

- Principal Author: [Mavim](https://www.mavim.com/) (Microsoft Gold Partner)

Other contributors:

- [Lennard van Leuven](https://www.linkedin.com/in/lennardvanleuven/) (Mavim)
