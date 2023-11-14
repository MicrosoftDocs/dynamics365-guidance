---
title: Security controls 
description: Some aspects of security are shared by both the customer and the provider. Other aspects are the responsibility of the customer, and others are the responsibility of the provider. For Dynamics 365 deployments, various core security controls are available.
author: riblack-microsoft
ms.author: riblack
ms.topic: conceptual
ms.date: 03/24/2023
ms.service: dynamics-365
---

# Security controls

Security is a shared responsibility in an online deployment. Microsoft owns some aspects, our customers own other aspects, and some aspects of security are shared by our customer, the reselling partner, and Microsoft. The following core security controls are available in Dynamics 365.  

## Security Development Lifecycle

The [Security Development Lifecycle (SDL)](https://www.microsoft.com/securityengineering/sdl) helps developers build more secure software. With SDL, they can address security compliance requirements by introducing security and privacy considerations throughout all phases of the development process. SDL consists of the following phases: *Training*, *requirements*, *design*, *implementation*, *verification*, *release*, and *response*.

<!--
Better as a table? 
Eva: Yes, please convert.
-->
:::image type="content" source="media/security-development-lifecycle.png" alt-text="The security development lifecycle consists of the following phases: training, requirements, design, implementation, verification, release, and response.":::

Learn more about [Microsoft Security Development Lifecycle](https://www.microsoft.com/securityengineering/sdl/)

## Datacenter security

Microsoft designs, builds, and operates datacenters in a way that strictly controls physical access to the areas where your data is stored. Microsoft understands the importance of protecting your data and is committed to helping secure the datacenters that host your data. We have an entire division at Microsoft devoted to designing, building, and operating the physical facilities that support Azure. This team is invested in maintaining state-of-the-art physical security.

:::image type="content" source="media/datacenter-security.png" alt-text="State of the art physical datacenter security features for perimeter, building, and computer rooms.":::

Learn more about [Datacenter security](/compliance/assurance/assurance-datacenter-security)

## DDoS defense system

A distributed denial of service (DDoS) is an attack in which multiple compromised computer systems attack a target, such as a server, website, or other network resource, and cause a denial of service for users of the targeted resource.

Azure has a defense system against DDoS attacks on its platform services. It uses standard detection and mitigation techniques and is designed to withstand attacks generated from outside and inside the platform.

Learn more about [Microsoft denial-of-service defense strategy](/compliance/assurance/assurance-microsoft-dos-defense-strategy)

## Data segregation

Dynamics 365 runs on Azure, so it's inherently a multi-tenant service, meaning that multiple customers' deployments and virtual machines are stored on the same physical hardware. Azure uses logical isolation to segregate each customer's data from others. This provides the scale and economic benefits of multi-tenant services while rigorously preventing customers from accessing one another's data.

Learn more about [Protection of customer data in Azure](/azure/security/fundamentals/protection-customer-data)

## Encryption

Data is an organization's most valuable and irreplaceable assets, and encryption serves as the last and strongest line of defense in a multi-layered data security strategy. Microsoft business cloud services and products use encryption in transit and at rest to safeguard customer data and help maintain control over it.

Learn more about [Azure encryption](/azure/security/fundamentals/encryption-overview)

### At-rest data protection

At minimum, Dynamics 365 environment databases use SQL TDE (Transparent Data Encryption, compliant with FIPS 140-2) to provide real-time I/O encryption and decryption of the data and log files for data encryption at rest.

:::image type="content" source="media/database-encryption.png" alt-text="Features of full database encryption using SQL Transparent Database Encryption":::"

By default, Microsoft stores and manages the database encryption keys for your Dynamics 365 deployments. Finance and operations apps use server-side encryption using service-managed keys. All key management aspects such as key issuance, rotation, and backup are handled by Microsoft. For customer engagement apps, the optional customer managed encryption key capability provides administrators the ability to self-manage the database encryption key for all the instances in their tenant.

Learn more about Customer Managed Keys [Manage the encryption key](/power-platform/admin/manage-encryption-key)

### In-transit data protection

Your data in transit is protected in several ways. Dynamics 365 uses HTTPS encryption so that you can enable encryption for traffic between Dynamics 365 and end users. Azure protects data in transit to or from outside components, and data in transit internally, such as between two virtual networks. Azure uses industry standard transport protocols such as TLS between user devices and Microsoft datacenters, and within datacenters themselves.

:::image type="content" source="media/encryption-in-transit.png" alt-text="Data is protected in transit between a user and the service, between datacenters, and by end-to-end encryption of communications between users.":::

## Secure identity

Identity and access management are critical to every organization. Microsoft Entra is a complete identity and access management solution with integrated security that connects more than 425 million people to their apps, devices, and data each month. Dynamics 365 applications are safeguarded using Microsoft Entra ID as a seamless identity solution.

[!INCLUDE [azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

Learn more about [Azure security features that help with identity management](/azure/security/fundamentals/identity-management-overview)

### Authentication: Users

Authentication is the process of proving an identity. The Microsoft identity platform uses the OpenID Connect protocol for handling authentication. By default, only authenticated users can access Dynamics 365.

Solutions that are implemented on Azure use Microsoft Entra as a centralized identity provider. Dynamics 365 applications are associated with a specific instance of Microsoft Entra, a *tenant*. To access Dynamics 365 applications, users must have an Microsoft Entra ID account in the associated tenant and be provisioned into a Dynamics 365 environment with a valid license. In scenarios where an organization spans multiple Microsoft Entra tenants, external users must be represented in the associated tenant. Those external users should be added to the tenant as guest users, and then assigned the appropriate licenses.  

> [!NOTE]
> Power Pages are accessible to external users either anonymously or as external users logged in to the portal through additional common identity provider options. Learn more at [What is Power Pages?](/power-pages/introduction).  

Microsoft Entra is built to work for apps in the cloud, on mobile, or on-premises, and delegating authentication and authorization to enable scenarios such as the following:

- Conditional access policies that require a user to be in a specific location

- Multi-factor authentication (MFA)

- Single sign-on (SSO), in which a user can sign in once and then be automatically signed into all the web apps that share the same centralized directory

Azure provides [fully secured identity federation with Active Directory on-premises](/azure/architecture/reference-architectures/identity/azure-ad). Federation with Microsoft Entra or Microsoft 365 enables users to authenticate using on-premises credentials and access all resources in the cloud.  

:::image type="content" source="media/authentication-for-online-services.png" alt-text="Microsoft Entra is built to provide authentication and authorization for PCs and devices, apps such as Microsoft 365 and Dynamics 365, other directory services, and multi-factor authentication.":::

### Authentication: Conditional access

Users can access cloud applications from anywhere and from any device such as mobile phones, tablets, or laptops from the office or home. As a result, there are many scenarios in which access control decisions shouldn't be made based solely on who can access a resource—you also need to consider how a resource is accessed. With Microsoft Entra External Identities, you can address this requirement.

With conditional access, you can implement automated access control decisions for accessing your cloud apps that are based on conditions.

:::image type="content" source="media/conditional-access.png" alt-text="Conditional access automates decisions for allowing or blocking access to your apps based on conditions.":::

Learn more at [Overview of Microsoft Entra External ID](/entra/external-id/external-identities-overview).  

### Authorization

Authorization is the control of access to Dynamics 365 applications. It allows you to control the functionality and data accessible to the users. Dynamics 365 uses security roles for authorization. Once a user is authenticated, the security roles assigned to the user or groups of users authorizes access to data, services, menus, or other Dynamics 365 features and capabilities.  

> [!NOTE]
> The concept of security roles is different for customer engagement apps and finance and operations apps. Learn more at [customer engagement apps security](security-strategy-product-ce.md) and [Finance and operations apps security](security-strategy-product-oa.md), repsectively.

### Auditing and monitoring

All Dynamic 365 applications provide audit functionality. Auditing provides a log of events related to activity for secure datastores, logins, or other important events. As with authorization, there are differences related to auditing in [customer engagement apps](security-strategy-product-ce.md) and [finance and operations apps](security-strategy-product-oa.md). Choose either link to learn more.  

## Customer responsibility for security controls

As a customer, you're responsible for:

- Account and identity management

- Creating and configuring conditional access policies

- Creating and assigning security roles

- Enabling and configuring auditing and monitoring

- Authentication and security of components of the solutions other than Dynamics 365

### Security for Dynamics 365 integrations

Most Dynamic 365 implementations have integrations with a range of Azure services, on-premises systems, and cloud systems.

:::image type="content" source="media/common-integrations.png" alt-text="Dynamics 365 implementations are commonly integrated with various cloud systems, on-premises systems, and a range of Azure services.":::

Consider the out-of-the-box integrations before building custom solutions. The native integration with the other Microsoft services is a tried, tested, and recommended solution for these scenarios. The following are examples of native integration options available in Dynamics 365:

- Dynamics 365 and Microsoft SharePoint integration

- Dynamics 365 and Microsoft Exchange Online integration

- Dual write for integration between customer engagement apps and finance and operations apps.

Use server-to-server (S2S) authentication to integrate Dynamics 365 securely and seamlessly with your custom websites and services. Some of the native integrations we mentioned such as Dynamics 365 and SharePoint also use [S2S authentication](/powerapps/developer/data-platform/use-single-tenant-server-server-authentication).

Regarding your on-premises systems, Microsoft recommends you deploy an [on-premises data gateway](/data-integration/gateway/service-gateway-onprem) connected to an [Azure hybrid connection](/azure/app-service/app-service-hybrid-connections) where possible.

Azure Service Bus is a fully managed enterprise message broker with message queues and publish-subscribe articles. Service Bus is used to decouple applications and services from each other. In many cases, we recommend integrating line-of business applications with cloud services by using Service Bus, which provides a secure channel for communicating between different on-premises or cloud-based line of business applications.

Many customers implement an allowlist for IP ranges that are permitted for outbound connections. Modern cloud services such as Dynamics 365 don't have static and specific IP ranges for Dynamics 365 solutions. We recommend you include the whole [Azure region](https://www.microsoft.com/download/details.aspx?id=56519) on the IP allowlist for the system to work properly.  

> [!NOTE]
> The list of IPs to allow is considerably shorter for [Azure Logic Apps](/azure/logic-apps/logic-apps-overview). Also, the use of the on-premises data gateways previously mentioned can reduce or eliminate this need.

### Azure Services availability

The customer should check that any Azure solution that is part of your architecture is available in the desired cloud and region here [Azure products by region \| Microsoft Azure](https://azure.microsoft.com/global-infrastructure/services/#select-product)

## Next steps

- [Learn more about foundational principles of the Microsoft Trusted Cloud](security.md#foundational-principles)
