---
title: Create or join a project in the Implementation Portal
description: Learn how to use the onboarding wizard to create projects, join projects, and add and remove users from projects. 
author: edupont04
ms.author: jiebai
ms.topic: how-to
ms.date: 06/02/2026
---

# Create or join a project in the Implementation Portal

This article explains how to use the onboarding wizard to create or join a project in the Dynamics 365 Implementation Portal. The updated onboarding wizard has a guided flow that helps you quickly create an implementation project, add users, and build a project profile so you can receive tailored guidance, telemetry insights, and reviews throughout the delivery lifecycle.

You can also automate project creation based on settings in the Power Platform admin center. For more information, see [Create new projects automatically based on environment groups](#create-new-projects-automatically-based-on-environment-groups).

You can also [join an existing project](#join-an-existing-project) in your tenant if you're invited or if the project was created through another Microsoft tool.

## Project overview

The Dynamics 365 Implementation Portal is the central hub for managing Dynamics 365 implementation projects. The portal supports the following tasks:

- Create new implementation projects by using a streamlined onboarding experience.

- View and join existing projects within your tenant.

- Accept project invitations and complete onboarding steps.

- Access implementation guidance, reviews, telemetry recommendations, and support.

## Create a new project

The onboarding experience guides you through three main stages:

1. **Project details** – Define the core attributes of your project. Find a description of the required fields at [Project details](#project-details).  

1. **Add users** – Assign project admins and users. Find a description of the required fields at [Add users](#add-users).  

1. **Project profiling** – Describe products, features, and business processes in scope. Find a description of the required fields at [Project profiling](#project-profiling).  

### Project details

The first step in creating a project is to provide the core details of your implementation. The following table describes the available fields on this tab.

| **Field** | **Description** |
| ---- | ---- |
| **Project name** | Enter a clear, descriptive name that reflects the scope of the implementation, such as *Contoso Marketing Digital Transformation*. |
| **Project type** | Select the type of implementation based on your deployment scenario. Select one of the following project types:<br><br> - **New Production Environment Implementation**  if you're implementing new products or solutions in a new production environment.<br><br> - **New Workload for an Existing Production Environment**  if you're adding or enhancing workloads in an environment that is already live.<br><br> - **Cloud Migration** if you're migrating an existing solution to the cloud. |
| **Tenant ID** | Specify whether the project is for your organization's tenant or another tenant, and enter the tenant ID. |
| **Estimated go‑live date** | Provide your best estimate of the production go‑live date. |
| **Implementation team location** | Select the country or region where most of the implementation team is located. |
| **Project phase** | Select the current phase of the project in the delivery lifecycle.<br><br>- **Discover** if you're defining business objectives, assessing solution fit, and identifying high‑level requirements and risks. <br><br>- **Initiate** if you're establishing governance, project plans, team structure, and environments. <br><br>- **Implement** if you're building and configuring the solution, including customizations, integrations, data migration, and testing.  <br><br>- **Prepare**  if you're completing user acceptance testing, performance validation, and operational readiness for go‑live. <br><br>- **Operate** for monitoring, supporting, and optimizing the solution after go‑live. |
| **Project purpose** | Specify the purpose of the project to help tailor guidance and insights. |

If your project includes finance and operations apps, provide the **Lifecycle Services (LCS) Project ID** during project creation. This ID value enables organizations and partners to join an existing related project rather than creating a duplicate project.

### Add users

On the **Add users** step, add everyone who needs access to the project. The following table describes the available fields at this stage.

| **Role** | **Description** |
| ---- | ---- |
| **Project Admin** | Full access to manage users, permissions, and join requests. |
| **Project User** | Standard access to project guidance, reviews, and insights. |
| **Partner Resource** | Enter partner email address and include the Partner Organization MPN ID to ensure correct linking. |

> [!NOTE]
> Every project must have at least two Project Admins from the organization to ensure continuity, visibility, and telemetry enablement.

Invitation emails are sent automatically when you proceed to the next step.

### Project profiling

Project profiling is the final stage of creating a project. It's critical for receiving relevant guidance and insights. Profiling includes the following tasks:

- Select **products and features** in scope.

- Define **project characteristics**, such as complexity, extensions, integrations, and deployment model.

- Select **business processes** supported by the solution.

You must select at least one product to continue. A well‑maintained project profile directly impacts the quality of guidance, telemetry insights, and reviews you receive.

To learn more, see [What is a good profile in the Dynamics 365 Implementation Portal?](project-profiling.md)

## Create new projects automatically based on environment groups

You can automatically generate implementation projects based on rules at the environment group level in the Power Platform admin center. This approach standardizes onboarding and connects your environments to the Implementation Portal for guidance, insights, and reviews.  

Environment group rules provide centralized governance across environments. When you publish a rule, it enforces consistent configuration across all environments in the group, ensuring standardized configuration and reducing manual setup effort. Learn more at [Create and manage environments](/power-platform/admin/create-environment) in the Power Platform admin center documentation.

### Prerequisites

- A Dynamics 365 environment created in the Power Platform admin center. Learn more at [Create and manage environments](/power-platform/admin/create-environment).  
- Permission to manage environments and environment groups.  

### Step 1: Create an environment group

1. Sign in to the Power Platform admin center, and then, in the navigation pane, select **Manage** > **Environment groups**, and then select **New group**.  

1. Enter a name and description, and then select **Create**. Learn more at [Environment groups](/power-platform/admin/environment-groups).  

Once you create the environment group, it's empty, and no rules are defined yet.  

### Step 2: Add environments to the group

Environments that you add to the group inherit any rules that you configure and publish at the group level. Learn more at [Environment groups](/power-platform/admin/environment-groups). 

1. In the environment group you created, add one or more Dynamics 365 environments to the group.  

### Step 3: Configure the Dynamics 365 Implementation Project rule

1. In the environment group, open the **Rules** tab.  

1. Locate the **Dynamics 365 Implementation Project** rule.  

1. Open the rule configuration panel.  

1. Provide the required onboarding details, such as initial project user email addresses.  

### Step 4: Enable and publish the rule

To take effect across all environments in the group, the rule requires publishing. Learn more at [Environment groups](/power-platform/admin/environment-groups).  

1. Enable the **Dynamics 365 Implementation Project** rule.  

1. Select **Publish rules** to apply the configuration.  

When you enable and publish the rule, the Implementation Portal automatically creates a new project in the Dynamics 365 Implementation Portal. Project users receive onboarding emails.

## Join an existing project

From the **Join Project** page, you can view all active projects in your tenant. You can request access to a project or join any projects you were invited to. If you receive an email with an invitation to join a project, either because you created the project in the Power Platform admin center or directly in the Implementation Portal, you land on this page to join the project. Select the project and, based on its status, either complete the required onboarding steps or go directly to the project workspace.

If you don't see a project you expect to join, contact a project admin to request access.

## Next step

- [Manage projects](manage-projects.md)  

## Feedback or questions?

Send your feedback or questions to [ftd365ip-support@microsoft.com](mailto:ftd365ip-support@microsoft.com).

## Additional resources

- [Manage projects in Dynamics 365 Implementation Portal](manage-projects.md)  

- [Conduct project reviews for your implementation projects](conduct-project-reviews.md)  

- [Prepare for go-live (finance and operations apps)](/dynamics365/fin-ops-core/dev-itpro/organization-administration/prepare-go-live)  

- [Solution Architect: Design Microsoft Power Platform solutions](/training/paths/solution-architect-data)  

- [Microsoft Certified: Power Platform Functional Consultant Associate](/credentials/certifications/power-platform-functional-consultant-associate)
