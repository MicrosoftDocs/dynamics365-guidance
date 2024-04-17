---
title: Manage projects in Dynamics 365 Implementation Portal
description: Learn how to manage projects in Dynamics 365 Implementation Portal.
ms.date: 03/27/2023
ms.topic: how-to
author: edupont04
ms.author: edupont
ms.reviewer: edupont
ms.custom: bap-template
---

# Manage projects in Dynamics 365 Implementation Portal

Following capabilities are available to manage your newly created/existing projects.

* Manage project details
* Manage project users
* Profile projects by selecting products, features, and other characteristics
* View  implementation guidance tailored for your project profile
* View Telemetry Insights (if applicable/available)

To do this, follow the steps given below.
1. Sign in to the [Dynamics 365 Implementation Portal](https://aka.ms/D365ImplementationPortal) using your work account or personal Microsoft account.
2. In the left side panel, select **Projects**.
3. Select the project you want to manage.

## Project Summary

The **Summary** tab on the project page is where you can:

* View and update key details like the project name, implementation partner, project phase, products in scope, and the country/region where the implementation team is located.

> [!NOTE]
> There are some fields such as LCS Go-Live date and LCS ID (for Finance and Operations projects), Tenant ID (for all projects) which are non-editable and are linked to the project in backend.
> - If you want to edit the LCS Go-Live date, please update it in the LCS milestone under "Deploy" methodology Go-Live date. Please refer to [Milestones](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs#milestones) to update the Milestone dates. Once you update the Go-Live date in LCS, it will be reflected in the Implementation Portal within a day.
> - If you want to update any other non-editable fields in the Project details, please reach ftd365ip-support@microsoft.com 
  

* Create project reviews or open an active project review. (This feature isn't available to all projects yet. Refer [Conduct Project Reviews](conduct-project-reviews.md) for more details)

* View implementation guidance that's tailored for your project based on the project profile.
* View Telemetry Insights if it's enabled/approved for your project.

## Project profile

Use the project profile to specify the products and features in the implementation project, their capabilities, and other characteristics. [Implementation guidance](#implementation-guidance) is tailored to your project based on information in the profile.

Update the project profile on the project's **Summary** tab or the **Project Profile** tab. The **Summary** tab collects details about the features you're implementing or planning to implement, along with other characteristics. The **Project Profile** tab gives you an overview of all the details of the project. You can switch between read-only and editable views of the **Project Profile** tab.

 > [!TIP]
 > When you select a product, the page shows the product's capabilities.

Select **Done** to save your changes. A notification at the top of the page tells you that implementation guidance will be based on the changes you made. When the message *Guidance is generated successfully* appears, select the **Implementation guidance** tab to view refreshed recommendations.

## Implementation guidance

Implementation guidance aims to bring the right information at the right time for each implementation project. Every time you update the project details or profile, the implementation guidance is refreshed.

Implementation guidance is shown in two places on the project page:

* The **Summary** tab shows the most important recommendations.

* The **Implementation guidance** tab shows all implementation guidance for your project.

You can interact with the guidance in the following ways:

* Select a card to open the link or article.

* Pin a card to save the link to the **Implementation guidance** tab.

* Select **Pinned** to view the guidance you pinned.

* Dismiss a card.

* Select **Dismissed** to view the articles you dismissed.

The **Implementation guidance** tab includes the following capabilities:

* A product filter helps you find relevant articles if you have multiple products in scope.

* If features are selected in the project profile, you can also filter guidance by feature.

* The **Search** field searches across all generated guidance using keywords you enter.

* Select guidance by type, including TechTalks, training materials, case studies, and platform-level guidance.

## Telemetry Insights
This tab is visible for all projects created via the Onboarding Wizard. Telemetry insights detects optimization opportunities and provides actionable guidance based on usage patterns within customer environments. Learn more - (Telemetry Insights Overview)[telemetry-insights.md)

## Admin

The **Admin** tab on the project page has the following sections

1. **Project Users** - This section displays the following set of users.
   
   |Type|Description|
   |----|----|
   |Project Users|Users who are part of the project and can view/edit the details of the Project|
   |Project Admins|Users who have administrative access to perform actions such as Add/Remove users and admins from the project|
   
Project admins can perform the following actions:

* Select **Add new user** to join a project user to the project.
* Select **Add new admin user** join a project admin to the project.
* Select **Delete** (the trashcan icon on the user card) to remove a user or admin from the project.
* Select **Set as admin** to make a project user an admin.

2. **Data Consent** - This section displays the Data Sharing Consent provided by the Customer Tenant users (if applicable) for the given project. Please refer to [Data Consent](data-sharing-consent.md) for more details.

3. **Center of Excellence Users** - This section is displayed only if the logged in user is part of the Center of Excellence (CoE) Partner team as part of the Partner Portfolio engagement. This section displays other CoE users who are part of the project.

## Next steps

If you update the project in the Implementation Portal as you move through the implementation process, review the new suggested content on the **Implementation guidance** tab.

[Project reviews](conduct-project-reviews.md) can help you get ready for the final go-live readiness review.
