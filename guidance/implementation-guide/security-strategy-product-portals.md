---
title: Power Pages Security
description: Power Pages allow internal and external users access to the Dataverse. Security in Power Pages has two parts \:\ authentication and authorization.
author: riblack-microsoft
ms.author: riblack
ms.topic: conceptual
ms.date: 03/14/2023
ms.service: dynamics-365
---

# Power Pages Security

[Power Pages](/power-pages/introduction) allow internal and external users access to the Dataverse data through external-facing websites. Portal data can be exposed anonymously or only to authenticated users. Examples of anonymous access are an unauthenticated landing page or home page. Security in Power Pages has two parts: authentication and authorization.

## Authentication

For users to access any Power Apps portal, they must exist in Dataverse as contacts. This rule applies to both internal and external users. Power Pages support Microsoft Entra ID, Azure B2C, ADFS and third-party providers such as LinkedIn, Facebook, and Google. Learn more about authentication configuration details and the complete list of identity providers at [Get started with configuring your portal authentication](/powerapps/maker/portals/configure/use-simplified-authentication-configuration).

[Configure authentication in Power Pages](/power-pages/security/configure-portal-authentication)

## Sign-up

There are two common ways to control sign-ups for the Power App portals

- [Open Registration](/powerapps/maker/portals/configure/configure-portal-authentication#open-registration) is the least restrictive option to sign up for portal access. Configuration portal allows a user account to be registered by providing a user identity. A new contact is created in Dataverse on signup.

- The alternative option is by [invitation](/powerapps/maker/portals/configure/invite-contacts). The invitation feature of portals allows you to invite contacts to your portal through automated email(s) created in your Microsoft Dataverse. The people you invite receive an email, fully customizable by you, with a link to your portal and an invitation code.

> [!TIP]
>
> 1. Azure B2C is the preferred authentication provider for portals. It separates Authentication from authorization.
> 2. Azure B2C supports third-party authentication providers such as LinkedIn, Facebook, Google, and many more with custom policies. Use Azure B2C as a bridge to other Identity providers as it will support more options, and Microsoft won't be duplicating these investments in the portal.
> 3. Local Authentication is deprecated but not removed yet. It cannot be extended to other systems like Azure B2C, and Microsoft is not investing in new local authentication features. Its use is limited and short-lived.
> 4. For B2B scenarios, consider guest users with Microsoft Entra ID authentication. Learn more at [B2B collaboration overview](/entra/external-id/what-is-b2b)

[!INCLUDE [azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

## Authorization

Authorization is a control to provide access to data and web pages in the Power Apps portal. The authorization is managed through web roles.

### Web Roles

[Web roles](/powerapps/maker/portals/configure/create-web-roles) allow portal users to perform special actions and access protected Dataverse contents. It's similar to security roles in Dynamics CE apps. A contact can have multiple web roles

A Power Apps portal website can have multiple web roles but can only have one default role for authenticated users and one for anonymous users.

Web roles control the following permissions:

- [Dataverse table permissions](/powerapps/maker/portals/configure/assign-entity-permissions) allow access to individual records in the Dataverse tables. It allows you to set a scope for access such as global, contact level, account level, parental level, etc. Customers can control the granular access on a record such as read, write, delete, append, and append to.

- [Page permissions](/powerapps/maker/portals/configure/webpage-access-control) allow access to portal webpages. For example, you can allow pages to be available anonymously for public access or restrict access to users who have specific roles.

- [Website access permissions](/powerapps/maker/portals/configure/website-access-permission) allow portal users to manage front side editing of some portal contents, such as content snippets and weblink sets.

:::image type="content" source="media/b2c-authentication.png" alt-text="Diagram depicting portal security using Azure B2C authentication for external users" lightbox="media/b2c-authentication.png":::

### Best Practice

Use [Portal Checker](/powerapps/maker/portals/admin/portal-checker) in your portal deployments. It lists forms, entity lists, and OData feeds exposed anonymously. Make sure no data is exposed to anonymous users by mistake.

## Other security options

- [Overview of Microsoft Entra External ID](/entra/external-id/external-identities-overview)  

  You can use External Identities to control the access to the portal.

- Power Pages allow the administrations to set up IP restrictions to the portal. [Restrict portal access by IP address](/powerapps/maker/portals/admin/ip-address-restrict)

- Power Apps portal also allows customers to use WAF (Web Application Firewall) to enhance their perimeter security.

## Next steps

- Learn more about [Finance and operations apps security](security-strategy-product-oa.md)
- Learn more about [Customer engagement apps security](security-strategy-product-ce.md)
- [Make security a day one priority](security-strategy-day-one-priority.md)
