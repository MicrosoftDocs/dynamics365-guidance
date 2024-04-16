---
title: Onboarding wizard
description: Learn about the onboarding wizard and its capabilities including creating new projects, joining existing projects, and adding and removing users to projects. 
author: dereklh77
ms.author: goantu
ms.topic: how-to
ms.date: 04/11/2024
---

# Onboarding wizard

This article describes how you can onboard a project in the Dynamics 365 Implementation Portal by following the steps in the onboarding guide. The onboarding guide provides an easy way to add an implementation project to the portal in real time, so that you can receive implementation guidance and create reviews. The following main sections take you through the steps of the onboarding guide.

## Project overview

The first main step in the Onboarding Wizard is to submit the basic details of the project.

1. Specify your role.

    - **Partner** - Choose this option if you're a partner and you're onboarding the project on behalf of your customer.
    - **Customer** - Choose this option if you don't have an implementation partner, or if you're running the implementation project as a customer of Microsoft.

2. Specify the type and the ID of the Microsoft Entra tenant that this implementation project is for.

    | Type | Description|
    |------|------------|
    | My Tenant | Select this option if you're logged into your implementation project as your tenant. The Tenant ID is displayed in the **Your Tenant ID** field. |
    | Different Tenant | Select this option if you're creating a project on a different tenant than the one you're currently logged into.

    > [!TIP]
    > For projects with finance and operations apps, you can find the tenant ID in Lifecycle Services. Learn more at [Subscriptions, LCS projects, and Azure Active Directory tenants FAQ](/dynamics365/fin-ops-core/dev-itpro/get-started/subscription-overview#how-can-i-find-the-tenant-name-and-tenant-id-within-lcs). You can also get this information from the Azure portal. Learn more at [Get subscription and tenant IDs in the Azure portal](/azure/azure-portal/get-subscription-tenant-id#find-your-microsoft-entra-tenant).
    >
    > Make sure that you are signed into the tenant that you want to retrieve the ID for.

3. Specify the purpose of the project.


    | Type | Description |
    |------|-------------|
    | Test/trial/training | Choose this option if your implementation project is created as a trial, for testing, or for training purposes.|
    | Partner implementation | Choose this option if your project is being implemented by a partner organization.|
    | Customer implementation | Choose this option if your project is being implemented by you as a customer and you do no have a partner involved.|

    > [!NOTE]
    > If you are a partner who's creating the implementation project on behalf of their customer, choose the *Partner implementation* option.

4. Select the type of project.

    | Type | Description |
    |------|-------------|
    | New project | Select this option if this is a new implementation.|
    | New workload on existing project | Select this option if you're implementing a new workload on an existing project.|

    If there's already a project that has gone live, and you are adding another app to the existing implementation, choose the *New workload on existing project* option.

5. Is this a Dynamics 365 finance and operations apps implementation?

    - Select **No** if you don't have any finance and operation apps in scope (such as Finance, Commerce, Supply Chain Management, or Human Resources).
    - Select **Yes** if you have one or more finance and operation apps in scope.

    Selecting *Yes* in the above option loads the *Finance and Operations LCS Project* section. If you select *No*, move forward to step 7.

6. Finance and LCS Project - For the initial rollout of the implementation project with finance and operations apps in scope, when a project is created in LCS, the FastTrack team automatically creates a project in the portal and customers and partners can join them. It's not required to create the project again if it already exists. 

    | Type | Description |
    |------|-------------|
    | LCS Geo | Select the right GEO where Lifecycle Services is deployed.|
    | LCS Project ID | Provide the Lifecycle Services project ID related to this implementation project. If you proceed to create a new project, this Lifecycle Services ID is linked to the newly created project.|

    > [!NOTE]
    > Existing project users in Lifecycle Services can join the related project in the Implementation Portal (if one exists). If you are not a project user in Lifecycle Services, then the related implementation project will not show up in the next screen. You will need someone with the necessary permissions to add you in LCS before you can join the project in this portal.

7. Choose the **Next** button to proceed to the **Existing Projects** page.

## Existing projects

This page displays the existing projects based on the Tenant ID and LCS ID, if provided. This page is divided into two sections.

### View existing projects

This section displays the list existing implementation projects that you're already part of. You can select *View Details* across each project to open project-specific information.

### Join existing project

This section is displayed only if you select **Yes** for Finance and Operations and provided a valid Lifecycle Services ID. There are two conditions that are validated:  

1. If the logged-in user ID (UPN) is a project user in the given Lifecycle Services instance.

2. If there's a related implementation project linked to the Lifecycle Services ID, which the logged-in user isn't part of.

If both conditions are met, then the projects are displayed with a **Join Project** button. Select the button to add users to the project and open the Project Summary screen.

If you're not a project user in the given Lifecycle Services ID and a related project exists, then the project details won't be visible. You'll need to reach out to someone with relevant access to add you to LCS and revisit the onboarding wizard to join the implementation project.

## Create new project

If your implementation portal project doesn't exist and/or if you want to create a new project, proceed to the third step of the wizard. This page collects the project details and creates the project.

### Project details

1. **Project name** - Provide a descriptive name that reflects components such as the customer's project name, deployment region, and main apps that are in scope.

2. **Products in-scope for this project** - Select all products and apps that are in scope for the implementation. The implementation guidance in the portal populates depending on the products selected here.

3. **Implementation team country** - Select the country where the bulk of the implementation team is located. This helps us scope the project.

4. **Estimate go-live date** - Please select the planned/best estimate of the go-live date. This date should be a future date and can't be in the past.

    > [!NOTE]
    > If required, you will be able to update all the above details in the portal after the project gets created using the "View/Edit Project Details" option.

5. **Select current project phase** - The project phase follows [Success By Design phases](/dynamics365/guidance/implementation-guide/success-by-design#success-by-design-phases). Once the project is created, this field isn't editable for finance and operation apps' implementation project but would be editable for all other projects.

### Project users and admins

1. **Email address of additional project user** - Enter email address of another user in the format `name@company.com`. This user will be added as a project user in the newly created project.

2. **Email address of additional project admin** - Enter email address of another user in the format `name@company.com`. This user will be added as a project admin in the newly created project in addition to the user creating the project. This is to ensure that there's coverage for the admin activities.

> [!NOTE]
> You (or any Project Admin) will be able to add/remove users from the project using the Admin tab &gt; Project Users page once the project gets created.

### Partner details

1. **Do you have an implementation partner?** - Toggle this option to *No* if you don't have any implementation partner. Marking this as *Yes* will make the next field mandatory.

2. **MPN ID of the implementation partner** - Please fill the MPN ID of the partner who's implementing the project. This ID will be linked to the project.

> [!NOTE]
> Both fields can be edited once the project has been created via the **View/Edit Project Details** option. The **Do you have an Implementation Partner?** toggle is not visible if you are a partner, or if you are creating the project as a partner and the MPN ID is a mandatory field in these scenarios.

### Consent for data sharing

> [!NOTE]
> This section loads only if you have selected **Different Tenant** as the tenant type at the start of the onboarding guide, and it's **not** a test/trial/training project. As part of data privacy principles, we need consent from two customer contacts who are active users of the project's tenant.

There are two fields for this section and accepts one email/field in the format `name@company.com`.

1. Target Tenant Reviewer 1 Email

2. Target Tenant Reviewer 2 Email

After providing the email addresses, select the **Click here to confirm the emails provided are real organization users from the company that owns the target tenant, not out-sourced users** field. Learn more at [Data sharing consent](data-sharing-consent.md).

Once the details are entered, choose the **Create Project** button.

> [!NOTE]
> When you choose the **Create Project** button, an email is sent to both target tenant reviewers for them to approve the project access along with the direct link and other details. While the project is created in the background, the details such as the name of the customer tenant and telemetry insights will not be resolved until the customer tenant reviewers approve the access. The person that creates the project will be able to cancel the request and change approver emails from the **Admin &gt; Data Consent** option page after the project has been created.

## Feedback or questions?

Send your feedback/queries to [ftd365ip-support@microsoft.com](mailto:ftd365ip-support@microsoft.com).
