---
title: Vendor self-service for technician management
description: Learn how to set up and use the Vendor self-service for technician management solution.
ms.topic: concept-article
ms.date: 05/09/2025
author: vibhutinair23
ms.author: vibhutinair
ms.reviewer: edupont
contributors: delhalawani
ms.custom:
    - O25-FieldService
---

# Vendor self-service for technician management

The Vendor self-service for technician management solution is a flexible foundation that helps organizations using Dynamics 365 Field Service efficiently manage external vendors and contractors. It also allows customization to meet specific business needs. This solution automates the process of setting up vendor resources, managing their characteristics, and handling their access to the system. These resources can then sign in to the Field Service mobile app to perform field work.

> [!NOTE]
> This solution is a sample and starting point for implementers to create vendor self-service management capabilities tailored to their business needs. It isn't a first-party Microsoft product feature and comes as-is. System implementers can extend the solution as needed.

Consider a scenario where your company works with multiple vendors who provide contractors to handle Field Service work orders. Each vendor can supply hundreds or even thousands of contractor resources to meet your work order needs. Properly setting up and managing these contractors involves ensuring they can sign in and use the Field Service mobile app. This process requires you to perform the following activities:

- Create an Entra ID user account.
- Apply appropriate licenses.
- Grant security permissions or groups.
- Set up a user account and a bookable resource record in Dynamics 365.
- Assign the correct bookable resource settings, characteristics, and skills.

Managing these activities manually for each contractor often requires one or more full-time resources. Offloading these tasks to the vendor companies themselves significantly reduces your company's workload. Vendors can self-serve their needs on their schedules, provisioning contractors, making resource changes, and deprovisioning them as needed. This approach saves time and money.

## Features

With the Vendor self-service for technician management solution, third-party vendors or in-house resource management can do the following tasks:

- Automated Entra B2B invites, Entra ID user creation, license application, security group addition, and bookable resource creation for new contractor setup.
- Manage contractors easily through a simple UI in the **Contact** table/forms, with real-time automated synchronization with bookable resources for Field Service settings, skills, and work hours.
- Automated license and security group removal for decommissioning contractors.
- Automated license and security group restoration for reactivating contractors.

## Disclaimer and extensibility

We provide this solution and code as-is for Dynamics 365 implementors. This solution isn't a first-party Microsoft product or code. Always test in a nonproduction environment. You can adjust and extend this solution as needed. All code is open source, and the Dynamics 365 solution file is unmanaged to give you full flexibility to adjust, add, or remove features.

## Prerequisites

To install and use this solution, you must have the following:

- An instance of Dynamics 365 Field Service.
- A user account with system administrator or system customizer permissions for the given instance.
- An Azure Function App, or the ability to provision a new Azure Function App.
- A service principal with the following Microsoft Graph permissions: `User.Invite.All`, `User.Read`, `User.Read.All`, `User.ReadBasic.All`, `User.ReadWrite.All`.

## Architecture overview

The following diagram illustrates how the various components—including Dynamics 365, Azure Functions, and Entra B2B—interact with each other.

:::image type="content" source="media/fs-vendor-self-service-for-technician-management/vendor-self-serve-architecture.svg" alt-text="Screenshot of architecture.":::

This solution uses a lightweight model-driven app that gives vendor administrators (the vendor representative responsible for managing their resources in your system) permission through [Entra B2B](/entra/external-id/b2b-fundamentals). Within this app, vendor admins use the **Contact** table as a portal to provision, manage, and deprovision their resources as needed. This solution has automations to handle the back-end tasks required for these scenarios based on interactions with the Contact record.





> [!NOTE]
> Contact records that vendor admins have access to are just a **window** into the Bookable resource for the given contractor. The Bookable resource has a resource type of **User** and links to a System User record.

## Components

This solution uses out-of-box Dynamics 365 configurations, plugins, Power Automate flows, and Azure Functions to implement the automation features explained earlier.

1. Dynamics 365 solution
   - Contact table metadata and limited custom entities for vendor management in a lightweight model-driven app
   - Plugins for automated resource setup and real-time syncing of Field Service configurations and characteristics

      > [!NOTE]
      > A synchronous plugin syncs the Contact record and Bookable resource record in real time. The plugin shows the business process error validation messages for invalid changes on the Bookable resource to the Contact record and vendor administrator making the change.

   - Power Automate flows for vendor lifecycle management through Azure Function calls

2. Azure Functions (.NET)
   - **InviteVendorResource**: HTTP Function to process the Entra B2B invites for new contractor setup
   - **AssignUserLicense**: HTTP Function to add a license to the contractor user
   - **RemoveUserLicense**: HTTP Function to remove a license from the contractor user
   - **AddToEntraIDGroup**: HTTP Function to add the contractor user to a security group for Dataverse/Dynamics 365 permissions

    > [!NOTE]
    > The Entra-centric operations used Azure Functions due to the simplicity of the code for these actions. However, an Entra connector exists in Power Automate for these actions. You can rearchitect the Power Automate flows to use this connector if you prefer a low-code experience instead of Azure Functions. Since the connector doesn't directly assign licenses, you need to use a security group with an attached license to achieve this low-code experience.

## Set up the solution

To set up the Vendor Self-Service for Technician Management solution, follow these steps:

1. Deploy the required Azure Functions to a Function App in your tenant.
2. Install the provided Dynamics 365 solution in your environment.
3. Configure the necessary environment variables for both.

## Set up Azure Functions

To set up the Azure Functions, follow these steps:

1. [Provision an Azure Function App](/azure/azure-functions/functions-create-function-app-portal?pivots=programming-language-csharp) or use an existing one.

   > [!NOTE]
   > Use the Consumption plan for the Function App to simplify deployment. Other Function plans may require more efforts or steps.

2. Download the [Azure Functions project ZIP file](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Field%20Service/Component%20Library/Vendor%20Self-Service/Azure%20Functions/FieldService.Optimize25.VendorIntegration.zip).

3. [Deploy](/azure/azure-functions/functions-create-your-first-function-visual-studio#publish-the-project-to-azure) the Azure Functions project to your Function App.

   > [!NOTE]
   > The deployment process works best if you open the Functions project in Visual Studio and publish it to your Function App. To connect to your Function App, follow the guided steps in Visual Studio.

   :::image type="content" source="media/fs-vendor-self-service-for-technician-management/publish-azure-functions.svg" alt-text="Screenshot of publishing the Azure Functions.":::

4. Once you published your Azure Functions, go to the Function App in the Azure portal. In the Settings area on the left, select Environment variables and create three new environment variables with the following names:
   - `ClientId`
   - `ClientSecret`
   - `TenantId`

5. Populate the `ClientId`, `ClientSecret`, and `TenantId` environment variables with values from a service principal. Ensure the service principal has permissions to send Entra B2B invites, create users, add users to Entra security groups, and apply or remove Microsoft 365 licenses. Refer to the [permissions to add](/entra/identity-platform/quickstart-configure-app-access-web-apis#application-permission-to-microsoft-graph) in the following screenshot or in the [Prerequisites](#prerequisites) section.

   :::image type="content" source="media/fs-vendor-self-service-for-technician-management/permissions.svg" alt-text="Screenshot showing permissions to add.":::

6. Turn on the Azure Functions and make them available for invocation from Power Automate flows in your tenant.

   :::image type="content" source="media/fs-vendor-self-service-for-technician-management/turn-on-functions.svg" alt-text="Screenshot showing turned on Azure Functions.":::

## Install and set up Dynamics 365 solution

To install and set up the Dynamics 365 solution, follow these steps:

1. Download the [VendorIntegration](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Field%20Service/Component%20Library/Vendor%20Self-Service) solution ZIP file.

2. Import the unmanaged solution into your environment. Review the [solution dependencies](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Field%20Service/Component%20Library/Vendor%20Self-Service#dynamics-365-solution) listed in the repository.

3. Set the following environment variables during the solution import:

   | Environment variable | Description |
   |----------------------|-------------|
   | **Invite Vendor Resource URI** | The URI for the *Invite Vendor Resource* API. |
   | **Assign User License URI** | The URI for the *AssignUserLicense* API. |
   | **Remove User License URI** | The URI for the *Remove User License* API. |
   | **Add To Entra ID Group URI** | The URI for the *AddToEntraIDGroupURI* API. |
   | **License SKU Id** | The SKU ID of the license for the vendor self-service resources. |
   | **Entra Group ID** | The Entra security group ID to add vendor self-service resources to. |

   To obtain the values for the environment variables listed in the table, follow these steps:

   - Azure Function URIs: Obtain Azure Function Uniform Resource Identifiers (URIs) from the Azure portal Functions. Navigate to each Function in the Azure portal through the Function App, click **Get function URL**, copy the default (Function key) URI, and paste it into the designated environment variable.
   - License SKU ID (the GUID of the license applied to vendor resources): Get the License SKU ID from the Microsoft 365 admin portal's licensing page or Microsoft Entra admin center. Select the desired license and copy the GUID at the end of the URL in your browser.
   - Entra Security Group ID (the GUID of the security group that provides Dynamics 365 privileges through security roles): Find the Entra Security Group ID in the Entra or Azure portals by navigating to the security group and copying the displayed Object ID value.

4. Since it's an unmanaged solution, publish all customizations after importing the solution. Ensure to turn on the three Power Automate flows.

   :::image type="content" source="media/fs-vendor-self-service-for-technician-management/cloud-flows.svg" alt-text="Screenshot showing the list of Power Automate flows.":::

## Set up a new vendor administrator

Vendor administrators use this solution to manage their resources. This vendor administrator must set up themselves as a licensed user in your Dynamics 365 environment. Invite this user through Entra B2B, like the contractors. They can log in to your environment using their email address and the password they create during the invitation process. Vendor administrators must have licenses that allow them to interact with Contact and Bookable resource records through a custom model-driven app.

System administrators in Dynamics 365 have access to all functionalities. To set up a new vendor administrator, assign them the included Field Service - Vendor Admin security role and grant access to the Vendor Administration model-driven app. Use bulk edit features to set up multiple resources simultaneously, if needed.

## Provision new vendor resources

To provision new vendor resources, follow these steps:

1. Open the new Contact form by clicking **+New** in the command bar.
2. Fill in resource information.
   - Populate at least the **First Name**, **Last Name**, and **Email** fields.
   - Include the **Technician Address** field if location-aware scheduling is needed.
   - Save the record. If you filled in the **Technician Address** field, the system geocodes the address and populates the coordinates in the **Address 1: Latitude** and **Address 1: Longitude** fields.

   > [!NOTE]
   > Changes to the **Name** and **Email** fields don't sync to the Entra user record after creating the user. Make these changes manually in the Microsoft Entra admin center if needed.

   :::image type="content" source="media/fs-vendor-self-service-for-technician-management/resource-information.svg" alt-text="Screenshot showing resource information to be filled.":::

3. Set fields on the **Field Service** tab. These fields sync directly to the Bookable resource record when created but can also be changed after creating the Bookable resource.
4. Add **Technician Characteristics** to the resource. These characteristics apply to the Bookable resource as Bookable resource characteristics. When creating a new Technician Characteristic record, you don't need to populate the **Rating** field.

   > [!NOTE]
   > The **Work Hours** tab doesn't display the Work Hours control until the system creates the Bookable resource.

5. Toggle the **Setup Technician** flag to **Yes** to start provisioning automations for the resource.
6. The system invokes a Power Automate flow that calls Azure Functions to:
   - Send an [invitation through Entra B2B](/entra/external-id/invitation-email-elements) to the email on the Contact and create a [Guest-type user](/entra/external-id/user-properties) in Entra.

      > [!NOTE]
      > The Entra B2B invitation doesn't need to be accepted before continuing. The invitation can be [accepted at any time](/entra/external-id/user-properties#before-invitation-redemption) without impeding resource provisioning and setup.

   - Assign your designated license to the new user.
   - Add the new user to your designated security group.
   - Create a Bookable resource upon creation of user record and link it to the Contact through a hidden Bookable resource lookup field on the Contact form.

      > [!NOTE]
      > The [user creation process](/power-platform/admin/create-users?tabs=new#add-users-to-dataverse) for Dynamics 365 is asynchronous and may take some time after license assignment.

7. After the user [accepts their invitation](/entra/external-id/user-properties#after-invitation-redemption), they can log in to the Field Service mobile app to perform fieldwork.

   > [!NOTE]
   > The username that the resource uses for logging in to the Field Service mobile app depends on whether the email address is a work/school account. If the email address is a work/school account, the user resource logs in to the app with their email address. If the email address isn't a work/school account (for example, Gmail, Yahoo, or Outlook.com), the user resource must use their fully qualified username to log in. This username follows the schema `emailaddress#EXT#@domain`, where the `@` in the email address is replaced with an underscore (`_`). You can view this username in the Microsoft 365 admin portal or the Microsoft Entra admin center.

## Sync changes from vendor resources to backend Bookable resources

The following changes made to the Contact record sync to the Bookable resource record:

- A plugin automatically syncs fields on the Contact in the **Field Service** tab with matching fields on the Bookable resource. The plugin operates synchronously, so it presents any errors surfaced on the Bookable resource to the vendor administrator.

   :::image type="content" source="media/fs-vendor-self-service-for-technician-management/fields-sync.svg" alt-text="Screenshot showing changes synced from vendor resource to Bookable resource.":::

- When you create or delete Vendor Technician Characteristics on the Contact, the system syncs them to the Bookable resource characteristics for the Bookable resource.

   > [!NOTE]
   > Synchronization flows one way from the Contact to the Bookable resource. Avoid modifying the synced Fields and Characteristics on the Bookable resource directly unless you manually update the corresponding Contact fields to match. Additionally, only create or delete Technician Characteristics; don't deactivate or reactivate them.

- If the address changes from the initial values set on the Contact form, manually regeocode the record by clicking **Geo Code** in the Contact's command bar.

   > [!NOTE]
   > To ensure that the vendor admin's address entry on the Contact form takes precedence, the solution inherently ignores changes to the Latitude and Longitude fields on the System User record. A plugin registered on updates to the System User table enforces this behavior. This behavior prevents address changes in Entra for the user from affecting the System User record if a matching Contact exists for that user (not for all System Users), based on email address. You can disable this plugin step if you don't need this functionality.

- Work Hours surface with a [form-within-a-form out-of-box (OOB) control](/power-apps/maker/model-driven-apps/form-component-control) and function the same as adjusting work hours through the Bookable resource form.

## Deprovision and reprovision existing vendor resources

> [!IMPORTANT]
> Keep the **Setup Technician** toggle on. Turning it off and then reenabling it causes the Power Automate flow to throw an error because the user is already created.

To deprovision and reprovision existing vendor resources, follow these steps:

- To deprovision a resource, deactivate the Contact record. This action unassigns the license from the respective Entra user and deactivates the system user shortly after.
- To reprovision an existing resource, reactivate the Contact record. This action reassigns the license to the respective Entra user and reactivates the system user.

> [!NOTE]
> Removing a license from a user triggers an asynchronous process to deactivate the user in Dataverse, which may take some time to reflect. The same applies to reactivating the user after reapplying the license.
