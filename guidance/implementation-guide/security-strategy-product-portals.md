---
title: Secure your Power Pages
description: Learn how to use authentication and authorization to protect your data and web pages in Power Pages, which let you access Dataverse data through external websites.
author: riblack-microsoft
ms.author: riblack
ms.topic: conceptual
ms.date: 01/19/2024
ms.service: dynamics-365
ms.custom:
  - ai-seo-date: 01/29/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Secure your Power Pages

[Power Pages](/power-pages/introduction) let internal and external users access Dataverse data through external-facing websites. You can expose your data to anyone&mdash;that is, to anonymous users&mdash;or only to authenticated users. For example, you can create a landing page or a home page that anyone can see, or a page that's only for users in your organization. To secure your Power Pages sites, you need to use authentication and authorization.

## Authentication

Authentication verifies the identity of the users who access your Power Pages sites. All users, internal and external, must exist as contacts in Dataverse. Power Pages supports Microsoft Entra ID, Azure B2C, ADFS, and non-Microsoft providers such as LinkedIn, Facebook, and Google. [Learn how to configure authentication in Power Pages](/power-pages/security/configure-portal-authentication).

Azure B2C is the preferred authentication provider for Power Pages. It separates authentication from authorization and supports non-Microsoft authentication providers such as LinkedIn, Facebook, Google, and many more with custom policies. Use Azure B2C as a bridge to other identity providers because it supports more options, and Microsoft won't duplicate these investments in Power Pages.

For B2B scenarios, consider guest users with Microsoft Entra ID authentication. [Learn more about B2B collaboration](/entra/external-id/what-is-b2b).

[!INCLUDE [azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

## Sign-up

You can control how users sign up for your Power Pages sites in two common ways:

- [Open registration](/powerapps/maker/portals/configure/configure-portal-authentication#open-registration) lets anyone sign up for your Power Pages site by providing a user identity. A new contact is created in Dataverse when a user signs up.

- [Invitation](/powerapps/maker/portals/configure/invite-contacts) lets you invite contacts to your Power Pages through customized emails that you create in Dataverse. The contacts you invite receive an email with a link to your Power Pages site and an invitation code.

## Authorization

Authorization controls the access to data and web pages in your Power Pages sites. You manage authorization through web roles.

### Web roles

[Web roles](/powerapps/maker/portals/configure/create-web-roles) let you assign special actions and access rights to users. They're similar to security roles in Dynamics 365 apps. A contact can have multiple web roles.

A Power Pages website can have multiple web roles, but can only have one default role for authenticated users and one for anonymous users.

Web roles control the following permissions:

- [Dataverse table permissions](/power-pages/security/table-permissions) let you access individual records in the Dataverse tables. You can set a scope for access, such as global, contact level, account level, and parental level. You can also control the access to a record, such as read, write, delete, and append.

- [Page permissions](/power-pages/security/page-security) let you access Power Pages web pages. For example, you can make pages available to anyone or restrict access to users who have specific roles.

- [Website access permissions](/power-pages/security/website-access-permission) let Power Pages site users manage some portal contents, such as content snippets and weblink sets.

:::image type="content" source="media/b2c-authentication.png" alt-text="Diagram showing Power Pages site security using Azure B2C authentication for external users." lightbox="media/b2c-authentication.png":::

Learn more at [Power Pages security](/power-pages/security/power-pages-security). <!--Use [Site Checker](/powerapps/maker/portals/admin/site-checker) to make sure your Power Pages sites don't expose any data to anonymous users by mistake.-->

## Other security options

In addition to authentication and authorization, you can use other security options to protect your Power Pages sites:

- Consider [Microsoft Entra External ID](/entra/external-id/external-identities-overview) to control access to your Power Pages sites.

- [Restrict portal access by IP address](/power-pages/admin/ip-address-restrict).

- You can use WAF (Web Application Firewall) to enhance your perimeter security.

## Next steps

- Learn about [security features](security-strategy-product-oa.md) in finance and operations apps
- Learn how to [make security a priority](security-strategy-day-one-priority.md) from day one
- Use the Success by Design [security checklist](security-strategy-checklist.md) to help identify and prioritize key requirements and implementation activities in the areas of privacy and compliance, identity and access, and application security
