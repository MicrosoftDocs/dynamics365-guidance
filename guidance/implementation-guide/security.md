---
title: Secure your Dynamics 365 data and apps
description: Learn how Microsoft helps you protect your Dynamics 365 data and apps with security, privacy, compliance, and transparency principles and practices.
author: riblack-microsoft
ms.author: riblack
ms.topic: overview
ms.date: 01/08/2024
ms.custom:
  - ai-seo-date: 01/08/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification:
  - AI-contribution
ai-usage: ai-assisted
---

# Secure your Dynamics 365 data and apps

"Businesses and users are going to embrace technology only if they can trust it."&mdash;Satya Nadella, Chief Executive Officer of Microsoft

Security is the protection of IT systems and networks from theft, damage, or disruption. Dynamics 365 is a cloud offering from Microsoft, which means that you can access Dynamics 365 data and apps that are hosted by Microsoft over the internet. In this model, you own your data, but share some control over the apps with Microsoft. So, security, compliance, privacy, and data protection are shared responsibilities between you and Microsoft.

:::image type="content" source="media/shared-responsibility.png" alt-text="Matrix of the areas of responsibility between customer and Microsoft based on deployment type." lightbox="media/shared-responsibility.png":::

This article explains the security principles and practices that apply to Dynamics 365 implementations. It also describes the security features that Microsoft includes in Dynamics 365.

## Key objectives

This article helps you:

- Understand how Microsoft helps you meet compliance standards
- Know your data ownership and how Microsoft can and can't use your data
- Explore security options and how Microsoft protects you
- Learn what to expect from Microsoft's transparency about its cloud services
- Find out how to secure your customer engagement apps
- Learn about the security of Power Pages
- Use the security features of finance and operations apps
- Make security a priority for your implementation
- Use the tools to secure your data and meet your security needs
- Avoid common security mistakes

## Foundational principles

Microsoft has been defending against threats and providing security protections for its online services since 1994. We invest more than $1 billion dollars per year to protect our customers. We say that our products and services run on trust. You can trust our expertise and focus on running your business. Ninety-five percent of Fortune 500 businesses run on the trusted Microsoft Cloud.

Microsoft is committed to safeguarding your data, protecting your right to make decisions about it, and being transparent about what happens to it. We empower you to achieve your vision on a trusted platform. The Microsoft Trusted Cloud is built on the foundational principles of security, privacy, compliance, and transparency. These four key principles guide how we do business in the cloud.

We apply these principles to your data:

- [Security](security-strategy-security-controls.md) - We use strong security measures to safeguard your data.
- [Privacy](#privacy) - We respect your right to control and decide about your data and keep it private.
- [Compliance](#compliance) - We manage your data in compliance with the law and help you meet your compliance needs.
- [Transparency](#transparency) - We are transparent about our cloud services and explain what we do with your data in clear, simple language.

### Security

Security is a shared responsibility in online deployments. You and Microsoft share some aspects of security. Other aspects are your responsibility, and others are Microsoft's responsibility. For Dynamics 365 deployments, Microsoft is responsible for physical datacenter security, the operating system, network controls, and a secure application framework.

[Core security features in Dynamics 365](security-strategy-security-controls.md) include:

- Security Development Lifecycle
- Datacenter security
- Data segregation
- Encryption
- Secure identity
- Authorization
- Auditing and monitoring

### Privacy

You own your data. We don't use your data for advertising. If you ever choose to end the service, you can take your data with you.

We follow these privacy goals and practices in Dynamics 365:

- Privacy goals
  - You own your data
  - You know where your data is located
  - You control your customer data
- Practices
  - We classify all data
  - We use role-based security to let you decide
  - We store your data in your own isolated data repository to maximize its security and integrity
  - We document our data-handling practices in the Microsoft Online Services in the Trust Center

#### How we use your data

Your data is your business, and you can access, modify, or delete it at any time. Microsoft won't use your data without your agreement. With your consent, we use your data to provide only the services you choose. We process your data based on your agreement and in accordance with our strict policies and procedures. We don't share your data with advertiser-supported services, nor do we use it for any purposes like marketing research or advertising. [Learn more about how Microsoft categorizes data in the delivery of online services](https://www.microsoft.com/trust-center/privacy/customer-data-definitions?rtc=1).

We believe you should have control over your data. [Learn how we handle data requests from government and law enforcement agencies](https://www.microsoft.com/trust-center/privacy).

#### Your responsibility for privacy

As a customer, you're responsible for data classification, identity management, and assigning appropriate security roles to protect the data.

[Learn more about Microsoft privacy](https://privacy.microsoft.com/).

### Compliance

Every organization must comply with the legal and regulatory standards of the industry and region they operate in. They may also have more contractual requirements and corporate policies.

We follow these compliance goals and practices in Dynamics 365:

- Compliance goals
  - Define and document standard operating procedures that meet multiple certification requirements
  - Run the system in a compliant way and collect evidence
  - Control and audit access to environments and data
- Practices
  - We follow strict privacy and security practices when building features and operating the service
  - We pass internal and external audits
  - We prioritize cross-industry certifications
  - We use authentication and authorization

Microsoft is responsible for the platform, including the services it offers. We provide a cloud service that can meet or exceed your security, privacy, and compliance needs. Microsoft complies with data protection and privacy laws for cloud services, and our compliance with world-class industry standards is verified. Detailed information about compliance for our cloud services and solutions that help you meet regulatory requirements for data security is available in our [Microsoft Trust Center](https://www.microsoft.com/trust-center).

As with security and privacy, compliance with laws and regulations is a shared responsibility of cloud service providers and their customers. The Trust Center offers tools that help you comply with national, regional, and industry-specific requirements for data collection and use, and audit reports that help you verify technical compliance and control requirements.

- [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager/V3): A cross-Microsoft cloud services solution that helps you meet complex compliance obligations. It performs real-time risk assessment that shows your compliance posture against data protection regulations when you use Microsoft cloud services. It also gives you recommended actions and step-by-step guidance.

- [Service Trust Portal](https://servicetrust.microsoft.com/): This portal has details and documents such as whitepapers, ISO reports, and other resources that explain Microsoft's implementation of controls and processes that protect cloud services and customer data.

[Learn more about managing compliance in the cloud at Microsoft Trust Center](https://www.microsoft.com/trust-center/compliance/compliance-overview).  

#### Personal data

[!INCLUDE [gdpr-intro](~/../shared-content/shared/privacy-includes/gdpr-intro.md)]

Use the links in the following table to help you respond to requests for personal data.

| **Platform feature area** | **Link to learn more** |
|--|--|
| Power Apps | [Responding to Data Subject Rights (DSR) requests to export Power Apps customer data](/power-platform/admin/powerapps-gdpr-export-dsr) |
| Dataverse | [Responding to Data Subject Rights (DSR) requests for Dataverse customer data](/power-platform/admin/common-data-service-gdpr-dsr-guide) |
| Power Automate | [Respond to personal data requests (work or school account)](/power-automate/gdpr-dsr-summary) |
| Microsoft Accounts (MSAs) | [Respond to personal data requests (Microsoft account)](/power-automate/gdpr-dsr-summary-msa) |
| Dynamics 365 apps | [Dynamics 365 Data Subject Requests](/compliance/regulatory/gdpr-dsr-Dynamics365) |

Learn more at [https://www.microsoft.com/TrustCenter](https://www.microsoft.com/TrustCenter).

#### Your responsibility for compliance

As Microsoft's customer, you must identify which controls apply to your business and understand how to implement and configure them to manage security and compliance with the legal and regulatory requirements of your nation, region, and industry.

[Learn more about regulatory compliance standards and Microsoft products](https://www.microsoft.com/trust-center/compliance/compliance-overview?rtc=1).

### Transparency

Microsoft is transparent about where your data is located. You know where your data is stored, who can access it, and under what conditions. You can specify the Azure datacenter region where your [customer data](https://www.microsoft.com/trust-center/Privacy/How-Microsoft-defines-customer-data) is stored. Microsoft might copy your data to other regions in the same geography for data durability, except in cases like these:

- [Microsoft Entra ID](/entra/identity/), which may store Microsoft Entra ID data globally

  [!INCLUDE [azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

- [Azure multi-factor authentication (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks), which may store MFA data globally

- Customer data collected during the onboarding process by the [Microsoft 365 admin center](/microsoft-365/admin/admin-overview/about-the-admin-center)

Microsoft has strict requirements for government and law enforcement requests for customer data. As described in the [Microsoft Privacy Principles](https://www.microsoft.com/trust-center/privacy), if Microsoft receives a request for your data, we direct the requester to get the data from you. If we have to disclose or give access to any of your data, we notify you and give you a copy of the request unless we are legally prohibited from doing so.

We follow these transparency goals and practices in Dynamics 365:

- Transparency goals
  - You choose where your data is stored
  - You know how we respond to government requests for your data
- Practices
  - You select the region where your Dynamics 365 data is stored
  - We don't give direct or unrestricted access to your data to any third party (including law enforcement, other government entity, or civil party) unless you direct us to

## Product-specific security guidance

This section explains how security principles apply to different Dynamics 365 applications and gives product-specific guidance for security measures you should consider.

[Customer engagement apps security](security-strategy-product-ce.md)

[Power Pages security](security-strategy-product-portals.md)

[Finance and operations apps security](security-strategy-product-oa.md)

## Make security a priority

Security should be your first concern when you start a Dynamics 365 project, not an afterthought. Ignoring security requirements can lead to serious legal, financial, and business risks and delays in your project. It can also affect the overall scalability and performance of the solution. [Make security a priority from day one](security-strategy-day-one-priority.md) and consider some of the security impacts on scalability, performance, compliance, rollout plans, reporting, and operational aspects, along with specific examples from each product that build on the concepts we've discussed.

## Security mistakes to avoid

Avoid common mistakes by looking at some key examples of security *anti-patterns*, or what not to do. An anti-pattern is a frequently implemented, ineffective response to a problem. Several security mistakes should be avoided for scaling, performance, and security reasons. We shared a few in the previous section, such as using organization-owned entities for reference data tables in customer engagement apps, or logging transactional tables in finance and operations apps. In this section, we discuss a few more mistakes to avoid.

### Security through obscurity

Project teams sometimes try to implement "security through obscurity." One example is hiding fields from forms and views with custom code. This isn't security, because anyone with the right security role can access those fields in several ways, such as with Advance Find, Power Automate, and APIs.

Always consider all the consequences of avoiding default security features.

### Credentials stored in Dynamics 365

Storing credentials improperly is one of the more common mistakes. Projects often use calls to external systems through plug-ins and JavaScript. Calling external services through plug-ins is recommended. However, the credentials to call these services are often stored in the code of some configuration entities in the system. This practice creates a significant security risk because the credentials could be exposed to many roles that aren't related to the use of the service. Also, if the credentials change, the call to the external service fails. As a best practice, don't store any credentials in the system.

> [!NOTE]
> Azure Key Vault lets you securely store and manage application credentials such as secrets, keys, and certificates in a central and secure cloud repository. Key Vault eliminates the need to store credentials in your applications. Your applications can authenticate to Key Vault at run time to get credentials.

## Resources

In this article, we introduced how the Trusted Cloud is built on security, privacy, compliance, and transparency principles, and outlined basic concepts of information security for Dynamics 365. We then looked at how these security concepts apply to different Dynamics 365 products. With that as a foundation, we then explained why it's crucial to make security a priority from the start, giving some specific examples and considering the impact of security on performance. Finally, we wrapped up with some examples of what not to do.

With this information, you can be confident in the security of Dynamics 365 products and your implementation. Use the following resources to learn more about these topics.

### General resources

- [Microsoft Dynamics 365 Cloud Services Compliance (download)](https://aka.ms/d365-compliance-list)  
- [Dynamics 365 - Security and Compliance Guide (download)](https://servicetrust.microsoft.com/DocumentPage/a67eb07f-a1cb-4c54-afd6-f93c1fd67ef1)  

### Compliance resources

- [An Introduction to Cloud Computing for Legal and Compliance Professionals (download)](https://download.microsoft.com/download/0/D/6/0D68AE95-6414-4074-B4B8-34039831E2BF/Introduction-to-Cloud-Computing-for-Legal-and-Compliance-Professionals.pdf)
- [Achieving Trust and Compliance in the Cloud](https://aka.ms/cloud-trust-compliance)

### Privacy resources

- [Privacy at Microsoft](https://privacy.microsoft.com/)
- [Protecting Data and Privacy in the Cloud (download)](https://download.microsoft.com/download/2/0/A/20A1529E-65CB-4266-8651-1B57B0E42DAA/Protecting-Data-and-Privacy-in-the-Cloud.pdf)

### Security resources

- [Dynamics 365 Security Assessment](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=25aa47b1-c510-43f2-84de-6b78ed3b1258&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_Pen%20Test%20and%20Security%20Assessments)
- [Security Incident Management in Microsoft Dynamics 365 (download)](https://www.microsoft.com/download/details.aspx?id=55110)
- [Encryption in the Microsoft Cloud](https://aka.ms/MCSCE)
- [Get started with security for Dynamics 365 solutions](/dynamics365/get-started/security)  
- [Security in Dataverse](/power-platform/admin/wp-security)
- [Security architecture for finance and operations apps](/dynamics365/fin-ops-core/dev-itpro/sysadmin/security-architecture)
- [Plan and implement security in finance and operations apps](/training/modules/plan-implement-security-finance-operations/)
- [Review the security model for your Dynamics 365 solutions (training)](/training/modules/fast-track-security/)

## Next steps

- Learn about [security controls](security-strategy-security-controls.md) in Dynamics 365
- Learn about [security features](security-strategy-product-ce.md) in customer engagement apps
- Learn about [security features](security-strategy-product-portals.md) in Power Pages
- Learn about [security features](security-strategy-product-oa.md) in finance and operations apps
- Learn how to [make security a priority](security-strategy-day-one-priority.md) from day one
- Use the Success by Design [security checklist](security-strategy-checklist.md) to help identify and prioritize key requirements and implementation activities in the areas of privacy and compliance, identity and access, and application security
