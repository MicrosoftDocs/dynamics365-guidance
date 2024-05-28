---
title: Storage capacity enforcement module for Power Platform CoE Starter Kit
description: Learn about the storage capacity enforcement solution used as a set of components for the Center of Excellence Starter Kit.
author: dereklh77
ms.author: reedw
ms.topic: article
ms.date: 05/21/2024
---

# Storage capacity enforcement module for Power Platform Center of Excellence Starter Kit

***Applies to: Dynamics 365***

The storage capacity enforcement solution is used as an optional and complimentary set of components for the [Center of Excellence (CoE) Starter Kit](https://aka.ms/coestarterkit). This solution provides you with the capability of enforcing storage capacity limits. It also automates the assessment of consumed capacity versus approved capacity and placing environments that are over approved capacity into [Administration Mode](/power-platform/admin/admin-mode). Dataverse environments in this state can only be accessed by those users who have System Administrator or System Customizer security roles assigned to their accounts.

 > [!IMPORTANT]
 > There is an additional cost associated with jobs executed using an Azure Automation account. You can review the [Process automation pricing](https://azure.microsoft.com/pricing/details/automation/#pricing) and use the [Azure Pricing Calculator](https://azure.microsoft.com/pricing/calculator/) to create a projected estimate. A single execution of the enable or disable runbook jobs averages 30 seconds of job run time but can vary.

## Solution components

The solution is made up of three primary component areas: notifications, automation, and reporting/audit.

### Notifications

The following notifications are included as a part of this solution and act as the primary mechanism to inform administrators and environment owners on storage capacity warnings and enforcement status.

- **Close to capacity emails** - Notify environment owner and CoE admins when an environment exceeds 80% (adjustable) but is still less than 100% of approved capacity.

- **Enforcement applied/removed emails** - Notify environment owner and CoE Admins when environment has capacity enforcement enabled or disabled.

- **Enforcement removal in-app notifications** - Notify CoE admin of environment status when running the manual Flow to disable capacity enforcement from CoE Power Platform Admin View app.

### Automation

Power Automate flows are used to facilitate the automation for sending notifications and apply/remove administration mode.

- **100% capacity – Disable environment** - Environment consumed capacity reaches 100% of approved for any capacity type (database, file, or log). A scheduled flow places the environment into admin mode.

- **Disabled environment &lt; 80% capacity – Enable environment** - Disabled environment consumption is below 80% of approved capacity for all defined capacity types. A scheduled flow disables admin mode, allowing users access.

- **Remove admin mode – Manual Flow in Power Platform Admin View** - Provides CoE admins with the option to remove admin mode from specific environments, directly from the Power Platform Admin View app.

### Reporting & auditing

The following reporting and audit components are included and provide visibility into environment storage capacity analytics.

#### Environment views in the Power Platform Admin View app

- **Environments disabled by capacity enforcement** – List of the environments currently disabled (administration mode) due to storage capacity overage.

- **Environments excused from capacity enforcement** – List of the environments that are excused and won't be assessed as a part of the storage capacity enforcement solution.

- **Environments with no storage capacity limits** – Environments that don't have any storage capacity limits currently defined.

   > [!NOTE]
   > Environments in this scenario will not be assessed or enforced since there are no storage capacity limits configured

- **Environments without environment owner** – The solution uses the CoE Starter Kit "environment owner" field for sending notifications. If an environment owner isn't defined for an environment, notifications are only sent to the CoE Admin email.

#### Environments in Power BI

The solution adds pages to the existing CoE Power BI dashboard that provide details on disabled environments, including the following list:

- Total number of environments that are switched off

- Number of environments disabled in past 30, 90 days

- Count of disabled environments by environment type

- Top 10 environments - % of approved capacity used

- Datapoints for approved, consume and % used for database, file and log capacities per environment

## Prerequisites

The following prerequisites must be deployed and configured before you can deploy the Storage Capacity Enforcement solution.

- Install the [CoE Starter Kit: Core Components solution](/power-platform/guidance/coe/setup-core-components).

- Enable [In-app Notifications](/power-apps/developer/model-driven-apps/clientapi/send-in-app-notifications?tabs=clientapi#enable-the-in-app-notification-feature) for the **Power Platform admin view** app in your CoE Starter Kit environment

- Azure subscription

    Create an [Azure Automation account](/azure/automation/quickstarts/create-azure-automation-account-portal). We recommend creating the Automation account in the same region as your CoE Starter Kit Dataverse environment.  

    > [!TIP]
    > You can learn which region your environment is hosted in by suing the [Synapse Link for Dataverse](/power-apps/maker/data-platform/azure-synapse-link-synapse#connect-dataverse-to-synapse-workspace) guide. The guide provides this information on the initial setup page. You don't have to complete the setup, and you can close the wizard once you've identified the region. This step is just to get the information about region and datacenter.

    The following image illustrates the information you see when you select a storage account:

    :::image type="content" source="media\center-of-excellence-storage-capacity-enforcement-1.svg" alt-text="Screenshot of the New Link section, with the Your environment is located in: U S Gov Central is highlighted." lightbox="media\center-of-excellence-storage-capacity-enforcement-1.svg":::

## Solution download

Download the storage capacity enforcement solution [on GitHub](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/coe-starter-kit-extensions).

## Related resources

- [Center of Excellence (CoE) overview - Power Platform](/power-platform/guidance/coe/overview)

- [Set up the CoE Starter Kit - Power Platform](/power-platform/guidance/coe/setup)

- [Environment capacity management & alerting - Power Platform](/power-platform/guidance/coe/capacity-alerting)

<!--## Tags

Stakeholders: IT -->
