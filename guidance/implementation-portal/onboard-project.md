---
title: Create or join a project in the Implementation Portal
description: Learn how to use the onboarding wizard to create projects, join projects, and add and remove users from projects. 
author: dereklh77
ms.author: goantu
ms.topic: how-to
ms.date: 12/19/2024
---

# Create or join a project in the Implementation Portal

This article shows you how to use the onboarding wizard to create or join a project in the Dynamics 365 Implementation Portal. The onboarding wizard makes it easier to create an implementation project in real time, so that you can receive implementation guidance and create reviews. You can also join an existing project if you're already part of it. The wizard guides you through the process of creating a project, adding users, and setting up the project details.

## Project overview

The first step in the onboarding wizard is to provide the basic details of your project.

1. Specify your role.

    - **Partner**: Choose this option if you're a partner and you're onboarding the project for your customer.

    - **Customer**: Choose this option if you don't have an implementation partner, or if you're running the implementation project as a customer of Microsoft.

2. Specify the type and the ID of the Microsoft Entra tenant that your implementation project is for.

    | Type | Description|
    |------|------------|
    | **My Tenant**| Select this option if you're signed in to your implementation project as your tenant. The tenant ID appears in the **Your Tenant ID** field. |
    | **Different Tenant** |Select this option if you're creating a project in a different tenant than the one you're signed in to.|

    For projects with finance and operations apps, you can [find the tenant ID in Lifecycle Services](/dynamics365/fin-ops-core/dev-itpro/get-started/subscription-overview#how-can-i-find-the-tenant-name-and-tenant-id-within-lcs). You can also [find the tenant ID in the Azure portal](/azure/azure-portal/get-subscription-tenant-id#find-your-microsoft-entra-tenant). Make sure that you're signed in to the tenant that you want to get the ID for.

    [!INCLUDE [impl-portal-data-sharing-consent-link](../includes/impl-portal-data-sharing-consent-link.md)]

3. Specify the purpose of the project.

    | Type | Description |
    |------|-------------|
    | **Customer implementation** | Choose this option if you're a Microsoft partner that implements the implementation project for a customer. Also choose this option if you're a customer of Microsoft, and you implement Dynamics 365 without a Microsoft partner.|
    | **Partner implementation** | Choose this option if your project is being implemented for a Microsoft partner, such as when you implement Dynamics 365 for your own organization as a Microsoft partner.|
   | **Pre-sales**| Choose this option if the project is being created as part of the pre-sales phase.|
    | **Test/trial/training** | Choose this option if your implementation project is created as a trial, for testing, or for training purposes.|

4. Select the type of project.

    | Type | Description |
    |------|-------------|
    | **New project** | Select this option if it's a new implementation.|
    | **New workload on existing project** | Select this option if you're implementing a new workload on an existing project. If there's already a project that is live in production, and you're adding another app to the existing implementation, choose the *New workload on existing project* option.|
   | **Cloud Migration for Dynamics 365 CE only**| Select this option if the project is for a cloud migration project for a Dynamics 365 Customer Engagement (on-premises) solution.|

5. Is it a Dynamics 365 finance and operations apps implementation?

    - Select **No** if you don't have any finance and operation apps in scope (such as Finance, Commerce, Supply Chain Management, or Human Resources).
    - Select **Yes** if you have one or more finance and operation apps in scope.

    If you select **Yes**, a new section appears, the *Finance and Operations Lifecycle Services Project* section. If you select **No**, move forward to step 7.

6. *Finance and Operations LCS Project* - For the initial rollout of an implementation project with finance and operations apps in scope, a project is created in Dynamics 365 Lifecycle Services. In the background, the FastTrack team automatically creates a project in the Dynamics 365 Implementation Portal, and customers and partners can join that project. Don't create the project again if it already exists.  

    | Type | Description |
    |------|-------------|
    | LCS Geo | Select the right GEO where Lifecycle Services is deployed.|
    | LCS Project ID | Provide the Lifecycle Services project ID related to this implementation project. If you proceed to create a new project, this Lifecycle Services ID is linked to the newly created project.|

    > [!NOTE]
    > Existing project users in Dynamics 365 Lifecycle Services can join the related project in the Implementation Portal (if one exists). If you are not a project user in Dynamics 365 Lifecycle Services, then the related implementation project will not show up in the next screen. You will need someone with the necessary permissions to add you in LCS before you can join the project in this portal.

7. Choose the **Next** button to proceed to the **Existing Projects** page.

## Existing projects

This page displays the existing projects based on the tenant ID and Lifecycle Services ID, if provided. This page is divided into two sections.

### View existing projects

This section displays the list existing implementation projects that you're already part of. You can select *View Details* across each project to open project-specific information.

### Join existing project

This section only appears if you chose **Yes** for finance and operations and provided a valid Lifecycle Services ID. There are two conditions that are validated:  

1. If the logged-in user ID (UPN) is a project user in the given Lifecycle Services instance.

2. If there's a related implementation project linked to the Lifecycle Services ID, which the logged-in user isn't part of.

If both conditions are met, then the projects are displayed with a **Join Project** button. Select the button to add users to the project and open the Project Summary screen.

If you're not a project user in the given Lifecycle Services ID and a related project exists, then the project details aren't visible. You must reach out to someone with relevant access to add you to Lifecycle Services and revisit the onboarding wizard to join the implementation project.

## Create new project

If your implementation portal project doesn't exist and/or if you want to create a new project, proceed to the third step of the wizard. This page collects the project details and creates the project.

### Project details

The following table describes the available fields on this tab.  

|Field|Description|
|-|-|
|**Project name**|Provide a descriptive name that reflects components such as the customer's project name, deployment region, and main apps that are in scope.|
|**Products in-scope for this project**|Select all products and apps that are in scope for the implementation. The implementation guidance in the portal populates depending on the products selected here.|
|**Implementation team country**|Select the country or region where the bulk of the implementation team is located. This information helps the FastTrack team scope the project.|
|**Estimate go-live date**|Select the planned/best estimate of the go-live date. This date should be a future date and can't be in the past.|
|**Select current project phase**|The project phase follows [Success By Design phases](../implementation-guide/success-by-design.md#success-by-design-phases). Once the project is created, this field isn't editable for finance and operation apps' implementation project but would be editable for all other projects.|

> [!NOTE]
> If required, you can update all the above details in the portal after the project gets created using the **View/Edit Project Details** option.

### Project users and admins

The following table describes the available fields on this tab.  

|Field|Description|
|-|-|
|**Email address of additional project user**|Enter email address of another user in the format `name@company.com`. This user is added as a project user in the newly created project.|
|**Email address of additional project admin**|Enter email address of another user in the format `name@company.com`. This user is as a project admin in the newly created project in addition to the user creating the project. This is to ensure that there's coverage for the admin activities.|

> [!NOTE]
> You (or any Project Admin) will be able to add/remove users from the project using the Admin tab &gt; Project Users page once the project gets created.

### Partner details

The following table describes the available fields on this tab.  

|Field|Description|
|-|-|
|**Do you have an implementation partner?**|Toggle this option to *No* if you don't have any implementation partner. If you choose *Yes*, the next field becomes mandatory.|
|**MPN ID of the implementation partner**|Specify the MPN ID of the partner who's implementing the project. This ID is linked to the project.|

> [!NOTE]
> Both fields can be edited once the project has been created via the **View/Edit Project Details** option. The **Do you have an Implementation Partner?** toggle is not visible if you are a partner, or if you are creating the project as a partner and the MPN ID is a mandatory field in these scenarios.

### Consent for data sharing

[!INCLUDE [impl-portal-data-sharing-consent-note](../includes/impl-portal-data-sharing-consent-note.md)]

## Create project

Once the details are entered, choose the **Create Project** button. If you requested consent to data sharing, an email is sent to both target tenant reviewers for them to approve the project access along with the direct link and other details. The project is created. However, details such as the name of the customer tenant and telemetry insights won't be resolved until the customer tenant reviewers approve the access. The person that creates the project can cancel the request and change approver emails from the **Data Consent** page after the project is created. Learn more at [Give or get consent to data sharing](data-sharing-consent.md).

## Next step

- [Manage projects](manage-projects.md)

## Feedback or questions?

Send your feedback or questions to [ftd365ip-support@microsoft.com](mailto:ftd365ip-support@microsoft.com).
