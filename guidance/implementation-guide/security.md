---
title:  Security strategy overview
description: Review the fundamental security principles for Dynamics 365 implementations. Read the security measures that Microsoft includes in Dynamics 365.
author: riblack-microsoft
ms.author: riblack
ms.topic: overview
ms.date: 09/06/2023
---

# Security strategy overview

>"Businesses and users are going to embrace technology only if they can trust it."
– Satya Nadella, Chief Executive Officer of Microsoft

Security is the protection of IT systems and networks from theft or damage to their hardware, software, or data and disruption of the service. Dynamics 365 is a cloud offering from Microsoft. In software-as-a-service deployments, data and applications are hosted with a provider (Microsoft) and accessed over the internet. In this deployment model, our customer maintains ownership of the data, but shares application control with Microsoft. Therefore, security, compliance, privacy, and data protection are shared responsibilities between Microsoft and our customers.

:::image type="content" source="media/shared-responsibility.png" alt-text="Matrix of the areas of responsibility between customer and Microsoft based on deployment type." lightbox="media/shared-responsibility.png":::

Here we'll outline the fundamental security principles applicable toDynamics 365 implementations and describe the security measures that Microsoft includes in Dynamics 365.

## Key objectives

This article provides an overview with the following key objectives:  

- Learn how we can help you meet compliance standards

- Review data ownership and how Microsoft can and can't use your data

- Explore security options and how we're working to protect you  

- Understand what level of transparency to expect when using our services

- Learn more about how our customer engagement apps are kept secure

- Explore the use of Power Apps Portals

- Learn about how to use security features of finance and operations apps

- Find out how to make security a day one priority for your implementation

- Understand the tools available to help you secure your data and implement solutions that meet your security requirements

- Explore examples of security anti-patterns

## Foundational principles

Microsoft has been defending against threats and providing security protections for our online services since 1994, and we invest over $1 billion dollars per year to continue our commitment to protecting our customers. For these reasons, we say that our products and services run on trust. You can place your trust in our expertise. This confidence allows you to focus on running your business. Ninety-five percent of Fortune 500 businesses run on the trusted Microsoft Cloud.

Microsoft takes its commitment seriously to safeguard customers' data, to protect their right to make decisions about that data, and to be transparent about what happens to that data. On our mission to empower everyone to achieve more, we partner with organizations, empowering them to achieve their vision on a trusted platform. The Microsoft Trusted Cloud was built on the foundational principles of security, privacy, compliance, and transparency. These four key principles guide the way we do business in the cloud.

We apply these principles to your data as follows:

- [Security](security-strategy-security-controls.md) - Implement strong security measures to safeguard your data

- [Privacy](#privacy) - Protect your right to control and make decisions about your data to help keep it private

- [Compliance](#compliance) - Manage your data in compliance with the law and help you meet your compliance needs

- [Transparency](#transparency) - Be transparent about our enterprise cloud services and explain what we do with your data in clear, plain language

<!-- :::image type="content" source="media/trustedcloud.png" alt-text="Boxes that say the same words as in the list before the image."::: removed image as providing little value.-->

### Security

Security is a shared responsibility in online deployments. Some aspects of security are shared by both the customer and the provider. Other aspects are the responsibility of the customer, and others are the responsibility of the provider. For Dynamics 365 deployments, Microsoft as the cloud provider is responsible for security aspects including physical datacenter security, the operating system, network controls, and providing a secure application framework.

:::image type="content" source="media/security-overview.png" alt-text="Complex illustration with Microsoft’s many levels of security practices that provide a secure application framework." lightbox="media/security-overview.png":::

The following list describes core [security controls available in Dynamics 365](security-strategy-security-controls.md):

- Security Development Lifecycle

- Datacenter security

- Data segregation

- Encryption

- Secure Identity

- Authorization

- Auditing and monitoring

[Learn more about each of these core security controls](security-strategy-security-controls.md)

### Privacy

You're the owner of your data; we don't mine your data for advertising. If you ever choose to end the service, you can take your data with you.

Standard privacy goals and their implementation in Dynamics 365 include the following items:

- Privacy goals
  - You own your data
  - You know where your data is located
  - You control your customer data
- Implementation details
  - All data is classified
  - Role-based security puts the customer in charge
  - Your own logically isolated data repository helps maximize the security and integrity of your data
  - Documented data-handling practices in the Microsoft Online Services in the Trust Center

#### How we use your data

Your data is your business, and you can access, modify, or delete it at any time. Microsoft won't use your data without your agreement. With your consent, we use your data to provide only the services you have chosen. We only process your data based on your agreement and in accordance with the strict policies and procedures that we've contractually agreed to. We don't share your data with advertiser-supported services, nor do we mine it for any purposes like marketing research or advertising. Learn more about how [Microsoft categorizes data in the delivery of online services](https://www.microsoft.com/trust-center/privacy/customer-data-definitions?rtc=1).

We believe you should have control over your data. The Trust Center can tell you more about how we [handle data requests from government and law enforcement agencies](https://www.microsoft.com/trust-center/privacy).

#### Customer responsibility for privacy

As a customer, you're responsible for data classification, identity management, and assigning appropriate security roles to secure the data.

Learn more about [Microsoft privacy](https://privacy.microsoft.com/).

### Compliance

Every organization must comply with the legal and regulatory standards of the industry and region they operate in, and many are also subject to more contractual requirements and corporate policies.

Some standard compliance goals and their implementation in Dynamics 365 include the following items:

- Compliance goals
  - Define and document standard operating procedures that meet multiple certification requirements
  - Run the system in a compliant fashion and collect evidence
  - Control and audit access to environments and actions to data
- Implementation details
  - Adhere to strict privacy and security practices when building features and when operating the service
  - Pass internal and external audits
  - Prioritize cross-industry certifications
  - Authentication and authorization

Microsoft is responsible for the platform, including the services it offers, and provides a cloud service that can meet or exceed the security, privacy, and compliance needs of your organization. Microsoft complies with data protection and privacy laws applicable to cloud services, and our compliance with world-class industry standards is verified. Detailed information about compliance for our cloud services and solutions that help organizations meet regulatory requirements for data security is available at our online [Microsoft Trust Center](https://www.microsoft.com/trust-center).

As noted earlier, compliance is a shared responsibility. To comply with laws and regulations, cloud service providers and their customers enter a shared responsibility. Tools available at the Trust Center include compliance offerings that help you comply with national, regional, and industry-specific requirements governing the collection and use of data, and audit reports that help you verify technical compliance and control requirements. Specific tools you can access at the Trust Center include:

- [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager/V3)  

  A cross-Microsoft cloud services solution designed to help organizations meet complex compliance obligations. It performs real-time risk assessment that reflects compliance posture against data protection regulations when you use Microsoft cloud services. It also provides recommended actions and step-by-step guidance.

- [Service Trust Portal](https://servicetrust.microsoft.com/)  

  This portal contains details and documents such as whitepapers, ISO reports, and other resources detailing Microsoft's implementation of controls and processes that protect cloud services and customer data.

Learn more about managing compliance in the cloud at [Microsoft Trust Center](https://www.microsoft.com/trust-center/compliance/compliance-overview).  

#### Personal data

[!INCLUDE [gdpr-intro](~/../shared-content/shared/privacy-includes/gdpr-intro.md)]

The following table provides links to help you respond to requests for personal data.

| **Platform feature area** | **Link to learn more** |
|--|--|
| Power Apps | [Responding to Data Subject Rights (DSR) requests to export Power Apps customer data](/power-platform/admin/powerapps-gdpr-export-dsr) |
| Dataverse | [Responding to Data Subject Rights (DSR) requests for Dataverse customer data](/power-platform/admin/common-data-service-gdpr-dsr-guide) |
| Power Automate | [Respond to personal data requests (work or school account)](/power-automate/gdpr-dsr-summary) |
| Microsoft Accounts (MSAs) | [Respond to personal data requests (Microsoft account)](/power-automate/gdpr-dsr-summary-msa) |
| Dynamics 365 apps | [Dynamics 365 Data Subject Requests](/compliance/regulatory/gdpr-dsr-Dynamics365) |

Microsoft's trust center has resources and information that can be helpful. Learn more at [https://www.microsoft.com/TrustCenter](https://www.microsoft.com/TrustCenter).

#### Customer responsibility for compliance

As Microsoft's customer, you must identify which controls apply to your business and understand how to implement and configure them to manage security and compliance within the applicable regulatory requirements of your nation, region, and industry.

> [!TIP]
> Learn more about regulatory compliance standards and Microsoft products at [Managing compliance in the cloud (microsoft.com)](https://www.microsoft.com/trust-center/compliance/compliance-overview?rtc=1)

### Transparency

Microsoft is transparent about where your data is located. You know where your data is stored, who can access it, and under what conditions. Dynamics 365 customers can specify the Azure datacenter region where their [customer data](https://www.microsoft.com/trustcenter/Privacy/How-Microsoft-defines-customer-data) is stored. Microsoft may replicate customer data to other regions available within the same geography for data durability, except in specific scenarios, including the following cases:

- [Microsoft Entra ID](/entra/identity/), which may store AD data globally

  [!INCLUDE [azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

- [Azure multi-factor authentication](/azure/active-directory/authentication/concept-mfa-howitworks), which may store MFA data globally

- Customer data collected during the onboarding process by the [Microsoft 365 admin center](/microsoft-365/admin/admin-overview/about-the-admin-center)

Microsoft imposes carefully defined requirements on government and law enforcement requests for customer data. As described at the [Microsoft Privacy Principles](https://www.microsoft.com/trust-center/privacy), if Microsoft receives a demand for a customer's data, we direct the requesting party to seek the data directly from the customer. If compelled to disclose or give access to any customer's data, Microsoft promptly notifies the customer and provides a copy of the demand unless legally prohibited from doing so.

Some standard transparency goals and their implementation in Dynamics 365 include the following:

- Transparency goals
  - Choose where your data is stored
  - Transparent about how we respond to government requests for your data
- Implementation details
  - You select the region where your Dynamics 365 data is stored
  - No third-party (including law enforcement, other government entity, or civil litigant) is given direct or unfettered access to customer data except as you direct

## Product-specific security guidance

This section discusses how security principles apply to different Dynamics 365 applications and shares product-specific guidance for security measures customers should consider.

[Customer engagement apps security](security-strategy-product-ce.md)

[Power Pages Security](security-strategy-product-portals.md)

[Finance and operations apps security](security-strategy-product-oa.md)

## Make security a day one priority

Security should be at the forefront when you start a Dynamics 365 project, not an afterthought. Negligence of security requirements can lead to significant legal, financial, and business risks, and delays in your implementation project. It can also impact the overall scalability and performance of the solution. [Make security a day one priority](security-strategy-day-one-priority.md) and consider some of the security impacts on scalability, performance, compliance, rollout plans, reporting, and operational aspects, along with specific examples from each product that build upon the concepts we've discussed.

## Security anti-patterns

Avoid common mistakes by examining some key anti-patterns. An anti-pattern is a frequently implemented, ineffective response to a problem. Several security anti-patterns should be avoided for scaling, performance, and security reasons. We shared a few in the previous section, such as using Organization owned entities for reference data tables in customer engagement apps, or indiscriminately logging transactional tables in finance and operations apps. In this section, we discuss a few more anti-patterns to avoid.

### Security through obscurity

Project teams may try to implement security through obscurity. One example is hiding the fields from forms and views through custom code. This isn't security, because anyone with a proper security role can access those fields in several ways such as with the use of Advance Find, Power Automate, and APIs.

Always consider all the ramifications of avoiding default security controls.

### Credentials stored in Dynamics 365

This is also one of the more common anti-patterns. Projects often use calls to external systems through plugins and JavaScript. Calling external services through plugins is recommended, but the credentials to call these services are stored in the code of some configuration entities in the system. This practice creates a significant security risk because the credentials could be discovered by numerous roles not directly related to the use of the service. In addition, if the credentials change, the call to the external service fails. As a best practice, don't store any credentials in the system.

> [!NOTE]
> Azure Key Vault allows you to securely store and manage application credentials such as secrets, keys, and certificates in a central and secure cloud repository. Key Vault eliminates the need to store credentials in your applications. Your applications can authenticate to Key Vault at run time to retrieve credentials.
>

## Resources

In this article, we introduced how the Trusted Cloud is built on the foundational principles of security, privacy, compliance, and transparency, and outlined basic concepts of information security as they apply to Dynamics 365. We then took a closer, product-specific look at how these security concepts are applied to Dynamics 365. With that as a foundation, we then examined why it's crucial to the success of your implementation to make security a priority from day one, citing some specific examples and considering the impact of security on performance. Finally, we wrapped up with a handful of anti-patterns to avoid.

Equipped with this information, you can be confident in the security considerations and capabilities of Dynamics 365 products and better ensure the security of your implementation. Use the following resources to learn more about these topics.

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

## Checklist

Use the Success by Design [Security Checklist](security-strategy-checklist.md) to help identify and prioritize key requirements and implementation activities in the areas of privacy and compliance, identify and access, and application security.

## Next steps

Visit the next section of the implementation guide.

- [Business intelligence, reporting, and analytics](business-intelligence-reporting-analytics-overview.md)
