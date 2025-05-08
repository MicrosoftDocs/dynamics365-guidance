---
title: Manage system access and security overview
description: Learn about the importance of managing system access and security, including an overview of stakeholders and benefits.
author: harshbirla
ms.author: harshbir
ms.topic: concept-article
ms.date: 06/25/2024
---

# Manage system access and security overview

***Applies to: Dynamics 365***

This article describes the importance of managing system access and security when you operate Dynamics 365 products.  

Management of system access and security in Dynamics 365 is paramount for organizations that aim to maintain operational integrity, protect sensitive data, and comply with regulatory requirements. As a cloud-based solution from Microsoft, Dynamics 365 offers robust tools and frameworks to ensure that system compliance is aligned with legal, contractual, and corporate standards. This article delves into critical aspects of managing system access and security in Dynamics 365, and highlights the roles and responsibilities of key stakeholders across the organization.

Ensuring the security of Dynamics 365 implementations is essential not only for safeguarding organizational data but also for maintaining trust with stakeholders. Define clear security policies, apply policies, and regularly audit user access and permissions to mitigate risks that are associated with data breaches and unauthorized access.

Dynamics 365 operates within the Microsoft Trusted Cloud, which is built on the foundational principles of security, privacy, compliance, and transparency. The shared responsibility model between Microsoft and its customers ensures that both parties actively contribute toward maintaining system integrity and data protection.

## Stakeholders

Effective management of system access and security within Dynamics 365 requires coordinated efforts from various stakeholders across the organization:

- **Executive leadership**: Chief executive officers (CEOs), chief financial officers (CFOs), and chief information officers (CIOs) provide strategic oversight and align system security initiatives with broader organizational goals. Their guidance ensures that resources are effectively allocated, and that security measures support business resilience.
- **IT management**: This group includes CIOs, IT directors, and IT managers. It plays a pivotal role in implementing technical security measures and integrating IT resources with overall organizational resilience strategies.
- **Data protection officers (DPOs)/privacy officers**: These stakeholders focus on data privacy and protection, and ensure that Dynamics 365 compliance measures are aligned with relevant privacy laws. They manage data protection strategies and privacy impact assessments, and act as liaisons with data protection authorities.
- **Security officers/information security managers**: Chief information security officers (CISOs) and information security managers are responsible for safeguarding systems and data against potential threats. They develop security policies, conduct risk assessments, and oversee incident response procedures.
- **Quality assurance (QA) and testing team**: QA managers and test engineers validate security measures through rigorous testing of system functionality and configurations. They identify and address compliance issues to ensure that Dynamics 365 implementations meet regulatory requirements.
- **Business process owners/functional leads**: These stakeholders define the security requirements that are needed to run business processes within Dynamics 365.
- **Internal auditors/audit committee**: Internal auditors and audit committee members provide independent assurance of governance, risk management, and compliance. They assess the effectiveness of the security setup and recommend improvements.

## Manage system access and security process flow

The following diagram illustrates the *manage system access and security* business process area.

:::image type="content" source="media\administer-to-operate-manage-system-access-security-1.svg" alt-text="Diagram of the Manage system access and security business process area, illustrating the connection between multiple business processes." lightbox="media\administer-to-operate-manage-system-access-security-1.svg":::

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

1. Start
1. *Administer to operate*
1. *Manage system access and security*, which has 10 substeps:

    1. *Review access policies*: Review the security and access policies that were defined during implementation, to ensure that the existing policies are adequate. Make any necessary changes.
    1. *Onboard new users*: Create new user accounts, and assign the appropriate permissions to them on an ongoing basis.
    1. *Update user access*: Update existing user access as needed, to ensure that daily activities can be completed.
    1. *Revoke user access*: Remove access from users when they no longer need it.
    1. *Delete users*: Remove user accounts that are no longer needed.
    1. *Review audit logs*: Review audit logs to ensure that security policies are being adhered to.
    1. *Manage service accounts and certificates*: Review permissions on service accounts to ensure that only necessary permissions are assigned, and that credentials are still secure. Rotate certificates to prevent issues with expiry.
    1. *Manage data security*: Review the data landscape to ensure that only necessary staff can access sensitive data.
    1. *Manage authentication*: Review authentication methods, and ensure that they are up to date with current system requirements.
    1. *Manage encryption*

1. End

The diagram also includes business processes on each side.

- On the left side:

    - Acquire to dispose
    - Case to resolution
    - Concept to market
    - Design to resolution
    - Forecast to plan
    - Hire to retire
    - Inventory to deliver

- On the right side:

    - Order to cash
    - Plan to produce
    - Procure to pay
    - Project to profit
    - Prospect to quote
    - Record to report
    - Service to cash

These business processes are related to the steps for managing system access and security in the center of the diagram. However, they aren't directly part of the sequential flow that is described.

In addition, the two large, curved arrows indicate that the process is iterative.

All end-to-end business processes are shown on the left and right sides because management of system access and security is an integral part of all business processes.

## Manage system access and security benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the management of system access and security. The following sections outline the key benefits that an organization might monitor and measure for the *manage system access and security* business process area.

### Enhanced data security and privacy

Dynamics 365 provides robust security features, including data encryption and access controls, to ensure that sensitive information is protected. These features help organizations comply with regulations such as the General Data Protection Regulation (GDPR) and the Health Insurance Portability and Accountability Act of 1996 (HIPAA). They also help safeguard customer data against breaches and unauthorized access.

### Real-time monitoring and alerts

Dynamics 365 provides real-time monitoring and alerts for potential compliance issues. Therefore, organizations can promptly address issues and reduce the likelihood of noncompliance and fines.

### Comprehensive documentation and audit trails

Dynamics 365 maintains detailed records and audit trails of compliance-related activities. These features support audit readiness and transparency, and make it easier for organizations to demonstrate compliance to regulators and stakeholders.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *manage system access and security* business processes, you can use the following resources and steps to learn more. (Links are added when the articles are ready.)

1. [Define a business continuity plan](administer-to-operate-define-business-continuity-plan-overview.md)
1. *Manage licensing and entitlements*
1. *Administer system features*
1. *Manage system access and security* (the article that you're currently reading)
1. [Train users and increase adoption](administer-to-operate-train-users-increase-adoption-overview.md)
1. *Monitor systems, environments, and capacity*
1. *Manage background jobs*
1. *Manage notifications alerts*
1. *Uptake software releases*
1. [Manage data synchronization](administer-to-operate-manage-data-synchronization-overview.md)
1. [Manage system compliance](administer-to-operate-manage-system-compliance.md)
1. [Support systems](administer-to-operate-support-systems-overview.md)

## Related information

You can use the following resources to learn more about the *manage system access and security* process in Dynamics 365.

- [Secure your Dynamics 365 data and apps](../implementation-guide/security.md)
- [Protect your data with Dynamics 365 security controls](../implementation-guide/security-strategy-security-controls.md)
- [Security capabilities for finance and operations apps](../implementation-guide/security-strategy-product-oa.md)

<!-- ## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Administrative, Audit, Finance, Human Resources, IT, Project Management, Purchasing

*Products:* Dynamics 365 -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Phillip Seaton](https://www.linkedin.com/in/pbseaton) \| Senior Solutions Architect

Other contributors:

- [Harsh Birla](https://www.linkedin.com/in/harsh-birla-2519714) \| Principal Solutions Architect
- [Rachel Profitt](https://www.linkedin.com/in/rachelprofitt) \| Principal Program Manager
- [Pedro Ramalhinho](https://www.linkedin.com/in/pedroramalhinho) \| Senior Solutions Architect
