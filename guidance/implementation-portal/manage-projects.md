---
title: Manage projects in Dynamics 365 Implementation Portal
description: Learn how to manage projects in Dynamics 365 Implementation Portal, including overviews on project summaries, project profiles, and implementation guidance.
ms.date: 04/17/2024
ms.topic: how-to
author: edupont04
ms.author: edupont
ms.reviewer: edupont
ms.custom: bap-template
---

# Manage projects in Dynamics 365 Implementation Portal

When you onboard an implementation project to the Dynamics 365 Implementation Portal, the following capabilities can help you manage your project.

* Manage project details
* Manage project users
* Profile projects by selecting products, features, and other characteristics
* View  implementation guidance tailored for your project profile
* View telemetry insights (if applicable/available)

## Get started

To start managing an implementation project, follow these steps.

1. Sign in to the [Dynamics 365 Implementation Portal](https://aka.ms/D365ImplementationPortal) using your work account or personal Microsoft account.
2. In the navigation panel on the left side, select **Projects**.
3. Choose the project that you want to manage.

## Project summary

The **Summary** tab on the project page is where you can do the following tasks:

* View and update key details, such as the name of the project, the implementation partner, the project phase, the products that are in scope, and the country or region where the implementation team is located.

  > [!NOTE]
  > Some fields are not editable, such as **LCS Go-Live date** and **LCS ID** (for projects with finance and operations apps), **Tenant ID** (for all projects). Insterad, they are linked to the project in the backend.
  >
  > To change the go-live date,  update it in the LCS milestone under the **Deploy** methodology's go-live date. Learn more at [Milestones](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs#milestones). Once you update the go-live date in Dynamics 365 Lifecycle Services, it will be reflected in the Implementation Portal within a day.
  >
  > If you want to update any other non-editable fields on this tab, contact [ftd365ip-support@microsoft.com](mailto:ftd365ip-support@microsoft.com).  
  
* Create project reviews or open an active project review.  

  This feature isn't available to all projects yet. Learn more at [Conduct Project Reviews](conduct-project-reviews.md).

* View implementation guidance that's tailored for your project based on the project profile.
* View telemetry insights if it's enabled/approved for your project.

## Project profile

Use the project profile to specify the products and features in the implementation project, their capabilities, and other characteristics. [Implementation guidance](#implementation-guidance) is tailored to your project based on information in the profile.

Update the project profile on the project's **Summary** tab or the **Project Profile** tab. The **Summary** tab collects details about the features you're implementing or planning to implement, along with other characteristics. The **Project Profile** tab gives you an overview of all the details of the project. You can switch between read-only and editable views of the **Project Profile** tab.

> [!TIP]
> When you select a product, the page shows the product's capabilities.

To save your changes, choose the **Done** action. A notification at the top of the page tells you that implementation guidance is based on the changes you made. When the message *Guidance is generated successfully* appears, choose the **Implementation guidance** tab to view refreshed recommendations.

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

## Telemetry insights

This tab is visible for all projects created with the onboarding wizard. Telemetry insights detects optimization opportunities and provides actionable guidance based on usage patterns within customer environments. Learn more at [Telemetry insights overview](telemetry-insights.md).

## Admin

The **Admin** tab on the project page has the following sections:

1. **Project Users**  

    This section displays the following set of users:

    |Type|Description|
    |----|----|
    |**Project Users**|Users who are part of the project and can view/edit the details of the Project|
    |**Project Admins**|Users who have administrative access to perform actions such as Add/Remove users and admins from the project|

    Project admins can perform the following actions:

    * Select **Add new user** to join a project user to the project.
    * Select **Add new admin user** join a project admin to the project.
    * Select **Delete** (the trashcan icon on the user card) to remove a user or admin from the project.
    * Select **Set as admin** to make a project user an admin.

2. **Data Consent**  

    This section displays the data sharing consent that the customer has granted (if applicable) for the given project. Learn more at [Data Consent](data-sharing-consent.md).

3. **Center of Excellence Users**  

    This section only shows if the current user is part of the Center of Excellence (CoE) partner team as part of the partner portfolio engagement. This section displays other CoE users who are part of the project.

## Next steps

If you update the project in the Implementation Portal as you move through the implementation process, review the new suggested content on the **Implementation guidance** tab.

[Project reviews](conduct-project-reviews.md) can help you get ready for the final go-live readiness review.
