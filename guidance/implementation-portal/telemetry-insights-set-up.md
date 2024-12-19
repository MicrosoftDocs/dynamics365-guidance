---
title: Set up telemetry insights (preview) 
description: Learn how to set up telemetry insights in the Dynamics 365 Implementation Portal, including overviews on feature details, requesting access and data consent.
author: edupont04
ms.author: meesposi
ms.topic: how-to
ms.date: 12/19/2024
---

# Set up telemetry insights (preview)

You can enable telemetry insights yourself with the **Set up telemetry** guide in the Dynamics 365 Implementation Portal. This article outlines the steps to take. Get an introduction to telemetry insights and the rules you can use in [Telemetry insights overview (preview)](telemetry-insights.md).

> [!IMPORTANT]
> Telemetry insights in the Dynamics 365 Implementation Portal is in public preview. Capabilities that are in preview aren't meant for production use and can have limited functionality. These features are available before an official release so that our customers can get early access and provide feedback.
> By accessing or using telemetry insights, you accept the [Microsoft Preview Terms of Service](https://go.microsoft.com/fwlink/?linkid=2242556).

## Set up telemetry

Switch on telemetry by choosing the **New Telemetry Request** action on the **Active Telemetry Requests** page. The **Active Telemetry Requests** page shows the environments where **Telemetry Recommendations** are currently visible or pending approval. It also shows their associated tenant ID, project ID (if applicable), and respective start and end dates.  

The first step in the **Set up telemetry** guide is to submit the basic details of the environment.

1. Specify your role.

    | Role | Description |
    |------|-------------|
    | Partner | Choose this option if you're a partner and you want to view telemetry for your customer's environment.
    | Customer | Choose this option if you're a customer of Microsoft and you want to view telemetry for your environment.

2. Specify the type and the ID of the Microsoft Entra tenant that this request is for.

    | Tenant | Description |
    |------|-------------|
    | My Tenant | Select this option if you're switching on telemetry for an environment on your tenant. The Tenant ID is displayed in the **Your Tenant ID** field. |
    | Different Tenant | Select this option if you're switching on telemetry for a different tenant than the one you're currently signed into. |

    [!INCLUDE [impl-portal-data-sharing-consent-link](../includes/impl-portal-data-sharing-consent-link.md)]

3. Specify the environment and date information, including an environment ID.

    > [!TIP]
    > Find the IDs of the environment and organization in the Power Platform admin center. For projects with finance and operations apps, you can find the Tenant ID in Dynamics 365 Lifecycle Services. Make sure that you're signed into the tenant that you want to retrieve the ID for.

     Learn more at the following resources:

    - [Subscriptions, LCS projects, and Azure Active Directory tenants FAQ](/dynamics365/fin-ops-core/dev-itpro/get-started/subscription-overview#how-can-i-find-the-tenant-name-and-tenant-id-within-lcs)  
    - [Get subscription and tenant IDs in the Azure portal](/azure/azure-portal/get-subscription-tenant-id#find-your-microsoft-entra-tenant)  
    - [Find your environment and organization ID and name - Power Platform](/power-platform/admin/determine-org-id-name).

4. Specify the purpose of the environment.

    | Environment Purpose | Description |
    |------|-------------|
    | Production | An environment used for live business operations.|
    | UAT | An environment used for standard acceptance testing.|
    | Sandbox | An environment used for preproduction testing.|
    | Performance | An environment used for performance testing.|
    | Dev | An environment used for development.|

5. Specify the start date and end date for the period that you want telemetry insights to be visible. Consider a minimum timespan of 7 days or more to get daily updates during the specified time period.  

6. If the specified tenant is associated with an existing Dynamics 365 Implementation Portal project, you're asked to associate this request with the correct existing project from a dropdown list. You don't need a project to set up telemetry insights for production environments.

> [!NOTE]
> You must have a project to switch on telemetry insights for all nonproduction environments. If a project does not exist, create one with the onboarding wizard. Learn more at [Create or join a project in the Implementation Portal](onboard-project.md). If a project does exist, but you do not have access, you must contact the project admin for access.

## Consent for data sharing

[!INCLUDE [impl-portal-data-sharing-consent-note](../includes/impl-portal-data-sharing-consent-note.md)]

The telemetry request is now created. However, the telemetry will not be resolved until the customer's reviewers approve the access. You can cancel the request and change the email addresses of the approvers from the **Telemetry Insights & Data Consent** option page after the request has been created.

## Related information

- [Telemetry insights overview (preview)](telemetry-insights.md)  
- [Give or get consent for data sharing in your project](data-sharing-consent.md)  
- [Overview of capabilities for analytics in Dynamics 365 Customer Service](../resources/analytics-capabilities.md)  
- [Application lifecycle management for analytics on data model customizations](../resources/analytics-alm-custom-reports.md)  
- [Monitor and optimize your Dynamics 365 environments](../implementation-guide/service-solution-monitor-service-health.md)  
- [Create or join a project in the Implementation Portal](onboard-project.md)  
- [Manage projects in Dynamics 365 Implementation Portal](manage-projects.md)  
