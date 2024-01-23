---
title: Protect your data with Dynamics 365 security controls
description: Learn how Dynamics 365 uses security controls to help you protect your data in the cloud and meet your compliance requirements.
author: riblack-microsoft
ms.author: riblack
ms.topic: conceptual
ms.date: 01/19/2024
ms.service: dynamics-365
ms.custom:
  - ai-seo-date: 01/19/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Protect your data with Dynamics 365 security controls

Security is a shared responsibility when you use online services. Microsoft, our customers, and our reselling partners all have roles to play in protecting data and meeting compliance requirements. Dynamics 365 offers various security controls to help you safeguard your data in the cloud. This article explains the core security controls in Dynamics 365 and your responsibilities as a customer.

## Security Development Lifecycle

The [Security Development Lifecycle (SDL)](https://www.microsoft.com/securityengineering/sdl) is a process that helps developers build more secure software. It helps them meet security compliance requirements by integrating security and privacy considerations into every phase of the development process.

| Phase | Description |
| ----- | ----------- |
| Training | Developers learn about security best practices and tools. |
| Requirements | Developers define security and privacy requirements for the software, create quality gates and bug bars, and perform rich assessments of security and privacy. |
| Design | Developers create a secure design and threat model for the software. |
| Implementation | Developers write secure code and use approved tools to detect and fix vulnerabilities. |
| Verification | Developers test and review the software for security and privacy issues. |
| Release | Developers create a security response plan, conduct a final security review, and certify the software for release. |
| Response | Developers monitor and respond to security incidents and feedback. |

[Learn more about the Microsoft Security Development Lifecycle](https://www.microsoft.com/securityengineering/sdl/).

## Datacenter security

Microsoft designs, builds, and operates datacenters that strictly control physical access to the areas where your data is stored. We understand the importance of protecting your data and we're committed to securing the datacenters that host it. We have a dedicated team at Microsoft that focuses on designing, building, and operating the physical facilities that support Azure. As shown in the following illustration, this team invests in state-of-the-art physical security features like these:

- Perimeter barriers and fencing
- Seismic bracing, round-the-clock security staff, and backup power in the buildings
- Cameras, alarms, and two-factor access control systems in the computer rooms

:::image type="content" source="media/datacenter-security.png" alt-text="Illustration of state-of-the-art physical datacenter security features for perimeter, building, and computer rooms.":::

[Learn more about datacenter security](/compliance/assurance/assurance-datacenter-security).

## DDoS defense system

A distributed denial of service (DDoS) attack is an attempt to overwhelm a target, such as a server, website, or other network resource, with traffic from multiple compromised computer systems to prevent users from accessing it. Azure has a defense system that protects its platform services from DDoS attacks. It uses standard detection and mitigation techniques and can withstand attacks from inside and outside the platform.

[Learn more about our denial-of-service defense strategy](/compliance/assurance/assurance-microsoft-dos-defense-strategy).

## Data segregation

Dynamics 365 runs on Azure, so it's a multitenant service by nature. This means that multiple customers' deployments and virtual machines share the same physical hardware. Azure uses logical isolation to separate each customer's data from others. This gives you the scale and economic benefits of multitenant services while preventing customers from accessing one another's data.

[Learn more about protection of customer data in Azure](/azure/security/fundamentals/protection-customer-data).

## Encryption

Data is one of your most valuable and irreplaceable assets, and encryption is the last and strongest line of defense in a multi-layered data security strategy. Microsoft business cloud services and products use encryption in transit and at rest to protect your data and help you maintain control over it.

[Learn more about Azure encryption](/azure/security/fundamentals/encryption-overview).

### At-rest data protection

At a minimum, Dynamics 365 environment databases use SQL TDE (Transparent Data Encryption, compliant with FIPS 140-2) to encrypt and decrypt the data and log files in real time. This provides data encryption at rest.

:::image type="content" source="media/database-encryption.png" alt-text="Illustration of features of full database encryption using SQL Transparent Database Encryption.":::

By default, Microsoft stores and manages the database encryption keys for your Dynamics 365 deployments. Finance and operations apps use server-side encryption with service-managed keys. Microsoft handles all aspects of key management, such as key issuance, rotation, and backup.

For customer engagement apps, you can choose to manage the database encryption key yourself for all the instances in your tenant. [Learn more about customer-managed encryption key](/power-platform/admin/manage-encryption-key).

### In-transit data protection

Your data in transit is protected in several ways. Dynamics 365 uses HTTPS encryption to secure the traffic between Dynamics 365 and users. Azure protects data in transit to or from external components, and data in transit internally, such as between two virtual networks. Azure uses industry-standard transport protocols such as TLS between user devices and Microsoft datacenters, and within datacenters themselves.

:::image type="content" source="media/encryption-in-transit.png" alt-text="Illustration of how data is protected in transit between a user and the service, between datacenters, and by end-to-end encryption of communications between users.":::

## Secure identity

Identity and access management are critical for every organization. Microsoft Entra is a complete identity and access management solution with integrated security that connects more than 425 million people to their apps, devices, and data each month. Dynamics 365 applications use Microsoft Entra ID as a seamless identity solution.

[!INCLUDE [azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

[Learn more about Azure security features that help with identity management](/azure/security/fundamentals/identity-management-overview).

### Authentication of users

Authentication is the process of proving an identity. The Microsoft identity platform uses the OpenID Connect protocol for handling authentication. By default, only authenticated users can access Dynamics 365.

Solutions that run on Azure use Microsoft Entra as a centralized identity provider. Dynamics 365 applications are associated with a specific instance of Microsoft Entra, a *tenant*. To access Dynamics 365 applications, users must have a Microsoft Entra ID account in the associated tenant and be assigned to a Dynamics 365 environment with a valid license. In scenarios where an organization spans multiple Microsoft Entra tenants, external users must be represented in the associated tenant. You should add those external users to the tenant as guest users, and then assign them the appropriate licenses.

> [!NOTE]
> Power Pages are accessible to external users either anonymously or as external users who sign in to the portal through additional common identity provider options. Learn more at [What is Power Pages?](/power-pages/introduction).

Microsoft Entra works for apps in the cloud, on mobile, or on-premises. It delegates authentication and authorization to enable scenarios such as these:

- Conditional access policies that require a user to be in a specific location
- Multifactor authentication (MFA)
- Single sign-on (SSO), in which a user can sign in once and then be automatically signed in to all the web apps that share the same centralized directory

Azure provides [fully secured identity federation with Active Directory on-premises](/azure/architecture/reference-architectures/identity/azure-ad). Federation with Microsoft Entra or Microsoft 365 lets users authenticate using their on-premises credentials and access all resources in the cloud.

:::image type="content" source="media/authentication-for-online-services.png" alt-text="Diagram illustrating how Microsoft Entra provides authentication and authorization for PCs and devices, apps such as Microsoft 365 and Dynamics 365, other directory services, and multifactor authentication.":::

### Authentication for conditional access

Users can access cloud applications from anywhere and from any device, such as mobile phones, tablets, or laptops from the office or home. As a result, access control decisions shouldn't be based only on who can access a resource. You also need to consider how a resource is accessed. Microsoft Entra External Identities addresses this requirement by providing conditional access policies. With conditional access, you can implement automated access control decisions for accessing your cloud apps that are based on conditions.

:::image type="content" source="media/conditional-access.png" alt-text="Illustration of how conditional access automates decisions for allowing or blocking access to your apps based on conditions.":::

[Learn more about Microsoft Entra External ID](/entra/external-id/external-identities-overview).

### Authorization

Authorization is the control of access to Dynamics 365 applications. It lets you control the functionality and data that users can access. Dynamics 365 uses security roles for authorization. After a user is authenticated, the security roles assigned to the user or groups of users authorize access to data, services, menus, and other Dynamics 365 features and capabilities.

The concept of security roles is different for customer engagement apps and finance and operations apps. Learn more about [customer engagement apps security](security-strategy-product-ce.md) and [finance and operations apps security](security-strategy-product-oa.md).

### Auditing and monitoring

All Dynamics 365 applications provide audit functionality. Auditing creates a log of events related to activity for secure datastores, logins, or other important events.

As with authorization, auditing is different for customer engagement apps and finance and operations apps. Learn more about [customer engagement apps security](security-strategy-product-ce.md) and [finance and operations apps security](security-strategy-product-oa.md).

## Customer responsibility for security controls

As a customer, you're responsible for:

- Account and identity management
- Creating and configuring conditional access policies
- Creating and assigning security roles
- Enabling and configuring auditing and monitoring
- Authentication and security of components of the solutions other than Dynamics 365

### Security for Dynamics 365 integrations

Most Dynamics 365 implementations have integrations with a range of Azure services, on-premises systems, and cloud systems.

:::image type="content" source="media/common-integrations.png" alt-text="Illustration of Dynamics 365 implementations integrated with various cloud systems, on-premises systems, and a range of Azure services.":::

Consider the out-of-the-box integrations before building custom solutions. The native integration with other Microsoft services is a tried, tested, and recommended approach. Some examples of native integration options available in Dynamics 365 include:

- Dynamics 365 and Microsoft SharePoint
- Dynamics 365 and Microsoft Exchange Online
- Dual-write for integration between customer engagement apps and finance and operations apps

Use [server-to-server (S2S) authentication](/powerapps/developer/data-platform/use-single-tenant-server-server-authentication) to integrate Dynamics 365 securely and seamlessly with your custom websites and services. Some of the native integrations we mentioned, such as Dynamics 365 and SharePoint, also use S2S authentication.

For your on-premises systems, we recommend that you deploy an [on-premises data gateway](/data-integration/gateway/service-gateway-onprem) connected to an [Azure hybrid connection](/azure/app-service/app-service-hybrid-connections) where possible.

Azure Service Bus is a fully managed enterprise message broker with message queues and publish-subscribe articles. Service Bus is used to decouple applications and services from each other. In many cases, we recommend integrating line-of-business applications with cloud services by using Service Bus, which provides a secure channel for communicating between different on-premises or cloud-based line-of-business applications.

Many customers use an allowlist for IP ranges that are allowed for outbound connections. Modern cloud services such as Dynamics 365 don't have static and specific IP ranges for their solutions. We recommend that you include the whole [Azure region](https://www.microsoft.com/download/details.aspx?id=56519) on the IP allowlist for the system to work properly.

The list of IPs to allow is considerably shorter for [Azure Logic Apps](/azure/logic-apps/logic-apps-overview). Using an on-premises data gateway can reduce or eliminate the need for an allowlist.

### Azure Services availability

You should check that any Azure solution that's part of your architecture is available in the cloud and region you need it. [Learn more about Azure product availability by region](https://azure.microsoft.com/global-infrastructure/services/#select-product).

## Next steps

- Learn about [security features](security-strategy-product-ce.md) in customer engagement apps
- Learn about [security features](security-strategy-product-portals.md) in Power Pages
- Learn about [security features](security-strategy-product-oa.md) in finance and operations apps
- Learn how to [make security a priority](security-strategy-day-one-priority.md) from day one
- Use the Success by Design [security checklist](security-strategy-checklist.md) to help identify and prioritize key requirements and implementation activities in the areas of privacy and compliance, identity and access, and application security
