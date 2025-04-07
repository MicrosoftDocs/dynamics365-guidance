---
title: Set up Telemetry insights  
description: Learn how to set up Telemetry insights in the Dynamics 365 Implementation Portal, including how to request access and obtain data consent.
author: edupont04
ms.author: meesposi
ms.topic: how-to
ms.date: 04/07/2025
---

# Set up telemetry insights

You can enable telemetry insights yourself with the **Set up telemetry** guide in the Dynamics 365 Implementation Portal. This article outlines the steps to take. Get an introduction to telemetry insights and the rules available in [Telemetry insights overview](telemetry-insights.md).

## Set up telemetry

Switch on telemetry by choosing the **New Telemetry Request** action on the **Setup Telemetry** page. The **Active Telemetry Requests** list page shows the environments where **Telemetry Recommendations** are currently visible or pending approval. It also shows their associated tenant ID, project ID (if applicable), and the request's created date. Opt-out is available by selecting the down arrow on the line.

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

3. Specify the tenant and environment ID.

    > [!TIP]
    > Find the IDs of the environment and organization in the Power Platform admin center. For projects with finance and operations apps, you can find the Tenant ID in Dynamics 365 Lifecycle Services. Make sure that you're signed into the tenant that you want to retrieve the ID for.

     Learn more at the following resources:

    - [Subscriptions, projects, and Microsoft Entra tenants FAQ (Dynamics 365 Lifecycle Services)](/dynamics365/fin-ops-core/dev-itpro/get-started/subscription-overview#how-can-i-find-the-tenant-name-and-tenant-id-within-lcs)  
    - [Get subscription and tenant IDs in the Azure portal](/azure/azure-portal/get-subscription-tenant-id#find-your-microsoft-entra-tenant)  
    - [Find your environment and organization ID and name - Power Platform](/power-platform/admin/determine-org-id-name)

4. Specify the purpose of the environment.

    | Environment Purpose | Description |
    |------|-------------|
    | Production | An environment used for live business operations.|
    | User acceptance test | An environment used for standard acceptance testing.|
    | Sandbox | An environment used for preproduction testing.|
    | Performance | An environment used for performance testing.|
    | Dev | An environment used for development.|
 

5. If the specified tenant is associated with an existing Dynamics 365 Implementation Portal project, you're asked to associate this request with the correct existing project from a dropdown list. You don't need a project to set up telemetry insights for production environments.

> [!NOTE]
> You must have a project to switch on telemetry insights for all nonproduction environments. If a project doesn't exist, create one with the onboarding wizard. Learn more at [Create or join a project in the Implementation Portal](onboard-project.md). If a project does exist, but you don't have access, you must contact the project admin for access.

## Viewing results and recommendations

The telemetry request is now created. If you set up Telemetry insights for your own tenant, expect to see results based on the type of environment or org enrolled.

If the setup is for a non-production environment, the results are available after 24 hours. If the setup is for a production environment, the results are available within 1 hour.
## Consent for data sharing

[!INCLUDE [impl-portal-data-sharing-consent-note](../includes/impl-portal-data-sharing-consent-note.md)]

If you set up Telemetry insights for a production tenant, you must request data consent from the organization that owns the data in that tenant. The telemetry doesn't resolve until your customer's reviewers approve the access. You can cancel the request and change the email addresses of the approvers from the **Data Consent** option page after the request has been created. Telemetry insights only shows diagnostic data in the results, not personally identifiable information (PII).

## Related information

- [Telemetry insights overview](telemetry-insights.md)  
- [Give or get consent for data sharing in your project](data-sharing-consent.md)  
- [Overview of capabilities for analytics in Dynamics 365 Customer Service](../resources/analytics-capabilities.md)    
- [Create or join a project in the Implementation Portal](onboard-project.md)  
- [Manage projects in Dynamics 365 Implementation Portal](manage-projects.md)  
