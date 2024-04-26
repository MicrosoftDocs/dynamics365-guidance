---
title: Telemetry insights overview (preview) 
description: Learn how to set up and use telemetry insights, including overviews on feature details, requesting access and data consent.
author: dereklh77
ms.author: meesposi
ms.topic: article
ms.date: 04/16/2024
---
# Telemetry insights overview (preview)
<!--[This article is prerelease documentation and is subject to change.]-->

> [!IMPORTANT]
> Telemetry insights in the Dynamics 365 Implementation Portal is in public preview. Capabilities that are in preview aren't meant for production use and can have limited functionality. These features are available before an official release so that our customers can get early access and provide feedback.
> By accessing or using telemetry insights, you accept the [Microsoft Preview Terms of Service](https://go.microsoft.com/fwlink/?linkid=2242556).

**Telemetry insights** detects optimization opportunities and provides actionable guidance based on usage patterns within customer environments. Results surface with severity indicators as they require attention.

You can enable telemetry insights yourself with the **Set up telemetry** guide.

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

   > [!TIP]
   > For projects with finance and operations apps, you can find the Tenant ID in Dynamics 365 Lifecycle Services. Learn more at [Subscriptions, LCS projects, and Azure Active Directory tenants FAQ](/dynamics365/fin-ops-core/dev-itpro/get-started/subscription-overview#how-can-i-find-the-tenant-name-and-tenant-id-within-lcs). You can also get this information from the Azure portal. Learn more at [Get subscription and tenant IDs in the Azure portal](/azure/azure-portal/get-subscription-tenant-id#find-your-microsoft-entra-tenant). Make sure that you're signed into the tenant that you want to retrieve the ID for.

3. Specify the environment and date information, including an environment ID.

   > [!TIP]
   > Find the IDs of the environment and organization in the Power Platform admin center or Lifecycle Services. Learn more at [Find your environment and organization ID and name - Power Platform](/power-platform/admin/determine-org-id-name).

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
> You must have a project to switch on telemetry insights for all nonproduction environments. If a project does not exist, create one with the onboarding wizard. Learn more at [Dynamics 365 Implementation Portal Onboarding Wizard](/dynamics365/guidance/implementation-portal/onboard-project). If a project does exist, but you do not have access, you're asked to contact the project admin for access.

## Consent for data sharing

> [!NOTE]
> This section loads only if you selected **Different Tenant** as your role. As part of data privacy principles, we need consent from two user contacts from the target tenant who are part of the environment's tenant.

There are two fields for this section, and each accepts one email address in the format `name@company.com`.

1. Target Tenant Reviewer 1 Email

2. Target Tenant Reviewer 2 Email

After providing the email addresses, select the **Click here to confirm the emails provided are real Organization users from the company that owns target tenant, not out-sourced users** field, and then choose the **Submit** action.

> [!NOTE]
> An email is sent to both target tenant reviewers for them to approve the user's access along with the link and other details. While the telemetry request will be created, the telemetry will not be resolved until the customer tenant reviewers approve the access. You'll be able to cancel the request and change approver emails from the **Telemetry Insights & Data Consent** option page after the request has been created.

## Telemetry recommendations

The **Telemetry recommendations** page displays various results for all environments that have been configured and approved for telemetry insights.

> [!NOTE]
> Once you've completed the setup of telemetry, results start showing up, based on the purpose of the environment. Recommendations for production environments show up about 15 minutes later. Recommendations for nonproduction environments start showing up about 24 hours after you completed the setup.

The results are grouped by **result** and **environment**. 

| Column | Description |
|------|-------------|
| **Last updated** | Shows the last time an optimization opportunity was detected for the specified environment and returned an actionable result.|
| **History** | Provides a view into the last seven actionable results generated for the environment with visual severity indicators. |
| **Read more**| Expands the result to display actionable guidance based on the associated result. Further detail is provided with selectable history dates that will adjust the guidance based on that date's specific results. By selecting a date and selecting **View details**, a new view opens providing additional technical details that vary based on each result.|

Choose the **Ideas** button to provide feedback on the telemetry insights. Alternatively, provide feedback on specific results by choosing the thumbs-up or thumbs-down buttons.

You can apply filters to narrow down results by tenant, environment, and purpose. Search can locate result names and descriptions.  

## Related resources

- [Data sharing consent](data-sharing-consent.md)  
- [Manage projects in Dynamics 365 Implementation Portal](manage-projects.md)  
- [Dynamics 365 Implementation Portal](overview.md)  
