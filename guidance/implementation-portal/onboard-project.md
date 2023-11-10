---
title:  Join and onboard projects in Dynamics 365 Implementation Portal
description: Learn how to join or onboard a project in Dynamics 365 Implementation Portal.
ms.date: 03/27/2023
ms.topic: how-to
author: edupont04
ms.author: edupont
ms.reviewer: edupont
ms.custom: bap-template
---

# Join and onboard projects in Dynamics 365 Implementation Portal

Join an existing project or onboard a new one in [Dynamics 365 Implementation Portal](https://aka.ms/D365ImplementationPortal).

> [!IMPORTANT]
> The project onboarding capability, which helps you onboard new projects to the Implementation Portal, is currently in pre-release format. If you want to onboard a new project to Dynamics 365 Implementation Portal, fill in this form: [https://aka.ms/D365ImplementationPortalOnboarding](https://aka.ms/D365ImplementationPortalOnboarding).

## Join a project

The project you want to join and information in your user profile determine how you join a project.

### Join a finance and operations apps project

The FastTrack team creates a project in the Implementation Portal for each finance and operations apps implementation. Submit a project in the [https://aka.ms/D365ImplementationPortalOnboarding](https://aka.ms/D365ImplementationPortalOnboarding) form to add a project to the portal. If you're a user in a project that's managed in Dynamics 365 Lifecycle Services, you can join the project in the Implementation Portal.<!-- EDITOR'S NOTE: The Cloud+AI Style Guide forbids abbreviating "Lifecycle Services." Also, is it immediately obvious in the portal UI where to find the onboarding wizard? If not, please describe where to find it. Eva: Consulted with Olga who says it auto-launches from a link the admin receives after filling in the request form. I'm commenting out some paras because that is only possible in private previews-->

<!--Open the onboarding wizard and specify the project's Lifecycle Services ID and region. The wizard presents you with matching projects. Select **Join** to be added to the project.-->
<!--
> [!TIP]
> After the initial go-live of a project, use the same onboarding wizard to onboard a project for updates to the same solution. Create a new project, and then capture its scope and go-live timeline.-->

### Join a project linked to your tenant if you're a tenant administrator

If you're a tenant administrator, you can join any project in the Implementation Portal that's associated with your tenant.  

1. Sign in to the Implementation Portal with your work account.

2. Open the onboarding wizard from the link that you received from Microsoft. [!INCLUDE [daf-implportal-preview](../includes/daf-implportal-preview.md)]

3. In the list of projects that are linked to your tenant, find your project and select **Join**.

## Create a project

> [!IMPORTANT]
> Only admins can create projects in the Implementation Portal. [!INCLUDE [daf-implportal-admin-roles](../includes/daf-implportal-admin-roles.md)]

For projects with finance and operations apps in scope, the FastTrack team creates a project in the portal for the initial go-live. You can [join the project](#join-a-finance-and-operations-apps-project), but you can't create one for the initial go-live. You *can* create projects for later rollouts of finance and operations apps in an implementation. To add a project to the portal, submit the project in the [https://aka.ms/D365ImplementationPortalOnboarding](https://aka.ms/D365ImplementationPortalOnboarding) form.  

When you create a project in the Implementation Portal, keep the following best practices in mind:  

* If you're implementing multiple apps in parallel, all with a similar timeline and go-live date, and one team is working on the implementation, create one project with multiple products.  

* If you're implementing multiple apps in parallel but they have different go-live timelines, create separate projects and specify the estimated go-live date for each.  

* Create separate projects for later rollouts with different workloads and timelines after the initial rollout.  

### Create a project in the Implementation Portal

Currently, you must submit a request for a new implementation project in the [https://aka.ms/D365ImplementationPortalOnboarding](https://aka.ms/D365ImplementationPortalOnboarding) form.  

You'll get an email from Microsoft with a link to the project in the Implementation Portal. The link launches an onboarding wizard that takes you through a few steps to get access to the project.  

You'll need the following information about the project:

* Project name (required)
* Email address of another project user (required)
* Email address of another project admin (as the project's creator, you automatically become an admin)
* Products in scope
* Implementation partner details
* Estimated go-live date
* Implementation team country/region
* Project phase

Users added as other project users receive an email notification that contains a link to the project in the Implementation Portal.

## Next steps

[Manage the project](manage-projects.md).
