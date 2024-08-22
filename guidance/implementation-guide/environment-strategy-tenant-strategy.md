---

title: Choose the best tenant strategy for your organization
description: Learn how to decide on a tenant strategy for your Microsoft cloud services based on data isolation, application management, and other factors.
author: abunduc-ms
ms.author: abunduc
ms.date: 08/22/2024
ms.topic: conceptual
ms.custom:
  - ai-seo-date: 01/16/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Choose the best tenant strategy for your organization

A tenant strategy is a plan for how you use your Microsoft Entra ID tenant to organize your Microsoft cloud services. A tenant is an instance of Microsoft Entra ID that represents your organization and differentiates it from other customers. To choose the best tenant strategy, you must understand how each service isolates code, configuration, data, and users. In this article, we use the term *tenant* for your Microsoft Entra ID tenant, which is required for solutions with Dynamics 365 online.

> [!IMPORTANT]
> The isolation that services provide doesn't necessarily reflect the underlying infrastructure or design of a cloud service. A separate tenant doesn't mean it's a separate server farm, and a separate environment doesn't give you a different front end.

[!INCLUDE [azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

Different services might have different isolation approaches. For example, as shown in the following diagram, you can have different subscriptions in Azure within the same tenant, and each subscription can host different applications and have a different set of users. Dynamics 365 and Microsoft Power Platform have environments that isolate data and manage user access.

:::image type="content" source="media/admin_contoso_tenant.svg" alt-text="Diagram of Dynamics 365, Power Platform, Microsoft 365, and Azure subscriptions distributed within a tenant." lightbox="media/admin_contoso_tenant.svg":::

The Microsoft Entra ID tenant provides the highest level of isolation for a cloud service, as it never shares resources or licenses with other tenants. A tenant is meant to represent an organization and not a department or business unit. However, in some cases, subsidiaries can share a tenant with the parent organization, depending on the organization structure, and the tenant model can mirror that structure.

## Global single-tenant setup

A common setup is to use a single Microsoft tenant to represent your organization in the Microsoft cloud. This setup gives you unified administration for user access and licenses, seamless integration between services, and the ability to share tenant resources. That's the setup that the diagram in the previous section shows.

All Dynamics 365 and Power Platform environments belong to the same tenant. You can deploy different apps in different environments, or have different users for each app and environment, but they all use the same Microsoft Entra ID that's associated with the tenant. With a multi-geo setup, you can create production environments in different countries or regions to meet your compliance and application needs, but they remain part of the same organization-wide tenant. Sovereign cloud deployment requires a separate Microsoft Entra ID and might have additional regulatory restrictions that limit your ability to create environments in different countries or regions.

Here are some of the pros and cons of a global single-tenant setup.

Pros of a global single-tenant setup:

- It aligns with the concept of tenant and the way cloud products are licensed.

- It lets you share licenses and quotas across the tenant for each service, as with Microsoft Dataverse storage.

- It gives you a central place to manage the services, users, and licenses.

- It makes it easier to deploy organization-wide IT policies, such as data loss prevention (DLP) and conditional access.

- It simplifies the management of service account configurations and connections when you move from one environment to another in the same tenant.

- It makes for easier and safer integrations between tenant services, without the need to elevate privileges to cross service boundaries.

Cons of a global single-tenant setup:

- A tenant can only be associated with a single Microsoft Entra ID. If you have independent subsidiaries that use a separate Microsoft Entra ID, you can't add them to that tenant, but you can use alternatives such as Azure business-to-business (B2B) for guest-user access.

- All environments, including the production environment, are governed by the same policies at the tenant level. Creating exceptions for trying out new services or testing might require you to go through multiple information security steps. For example, a proof of concept or pilot that requires a different Microsoft Entra ID conditional access policy will attract scrutiny from security.

## Global multitenant setup

Usually, the tenant structure for the Microsoft cloud software as a service (SaaS) mirrors the structure of your organization. But some organizations operate as separate business entities in a country or region, even though they might be part of a single umbrella brand. In such cases, you might adopt a multitenant setup, as each business entity might have its own contractual needs, regulatory constraints, and licensing agreements.

The following diagram illustrates an organization with two Entra ID tenants with two environments each.

:::image type="content" source="media/admin_contoso_tenant2.svg" alt-text="Diagram with Contoso Holding and Contoso Germany with each their Entra ID tenant. Each tenant has a production environment and a sandbox environment." lightbox="media/admin_contoso_tenant2.svg":::

Alternatively, you can have separate tenants for development, testing, and live systems. This mainly supports the information security requirements to isolate data and prevent users who aren't involved in production from accessing production systems. However, using separate tenants is generally not recommended, because you can have data and access isolation at the service level to meet information security requirements. For example, you can use security groups on environments to limit access.

User accounts, identities, security groups, subscriptions, licenses, and storage can't be shared among different tenants. So, using separate tenants might require you to replicate all other services or create stubs for external systems, per tenant, for all the integrations. You might also need to duplicate licenses and quotas across tenants to support application lifecycle management (ALM) and performance testing. Admins have the additional responsibility of ensuring that all the policies and settings between tenants are in sync to avoid deployment failure between tenants. Some organizations do go down this path because of their historical setup or a lack of understanding of the controls available to restrict access at the service level.

Here are some of the pros and cons of a global multitenant setup.

Pros of a global multitenant setup:

- It works when different subsidiaries are fully independent, with different systems to manage user identities in separate domains, and have separate licensing needs.

- It provides the highest level of isolation that might simplify the security approvals, but isn't usually required.

- It makes it easier to manage and monitor the cost per tenant, without the need for internal cross-charging and tracking usage of shared resources on a single tenant. For example, storage is shared on a single tenant.

Cons of a global multitenant setup:

- Licenses can't be shared across different tenants, which means that storage, API add-ons, and other tenant-level quotas must be purchased for each tenant. You might also have to purchase separate licenses for the same user to access separate tenants.

- The overhead to maintain tenant-level Microsoft Entra ID and DLP policies consistently across tenants can lead to surprises during production deployment.

- Service-level admin actions, such as the ability to copy an environment, might not be available across tenants, which can make testing or troubleshooting difficult.

- The build automation and continuous integration and continuous delivery (CI/CD) pipelines that span multiple tenants can be more complicated and might require manual intervention, especially when managing connections to the service.

- You might have to purchase a large number of licenses to conduct testing. For example, you can't reliably simulate a load from 1,000 users using five test-user accounts.

- If you're using capacity add-ons, you might have to make duplicate purchases for each tenant to develop and test your solutions.

- Integrations with other services and applications, including between customer engagement apps and finance and operations apps, can't be done across tenants. This means you might have to purchase licenses for other Microsoft services for each tenant.

Overall, managing your ALM process across several tenants adds unnecessary complexity to licensing and technology for not much gain in security. You might already have the necessary controls at the service level to limit access to business data.

## Next steps

- Learn about the [key factors that are affected by an environment strategy](environment-strategy-key-factors-affected.md)
- Learn about [global deployment scenarios](environment-strategy-global-deployment-scenarios.md)
- Understand [environment lifecycle scenarios](environment-strategy-lifecycle-scenarios.md)
- Get [product-specific guidance](environment-strategy-guidance-product.md)
- Follow the [environment strategy checklist](environment-strategy-checklist.md)
- Read a [case study](environment-strategy-case-study.md) of a company that learned the importance of a good environment strategy