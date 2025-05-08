---
title: Success by design security checklist in application security
description: Use the Success by Design security checklist to plan and prioritize your key activities for privacy and compliance, identity and access, and application security.
author: riblack-microsoft
ms.author: riblack
ms.topic: checklist
ms.date: 01/22/2024
ms.service: dynamics-365
ms.custom:
  - ai-seo-date: 01/22/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Success by design security checklist for key activities in application security

## Privacy and compliance

| Done? | Task |
| :-----: | ---- |
| &check; | Understand the responsibilities of the service provider as a data processor and the customer responsibilities as the owner and data controller. Make sure both sides comply with the relevant laws and regulations. |
| &check; | Review the Dynamics 365 cloud service agreements and compliance documentation. Learn about the policies and procedures for handling data, disaster recovery, data residency, and encryption. |

## Identity and access

| Done? | Task |
| :-----: | ---- |
| &check; | Create an identity management strategy that covers user access, service accounts, application users, federation requirements for single sign-on, and conditional access policies. |
| &check; | Create administrative access policies for different admin roles on the platform, such as service admin and Microsoft 365 admin. |
| &check; | Apply and follow the relevant data loss prevention policies and procedures to make changes or request exceptions. |
| &check; | Have the necessary controls to manage access to specific environments. |

## Application security

| Done? | Task |
| :-----: | ---- |
| &check; | Understand the app-specific security features and use the native access control mechanisms instead of customizing the build. |
| &check; | Understand that hiding information from the view doesn't remove access. There are other ways to access and extract information. |
| &check; | Understand the impact of losing the security context when you export the data. |
| &check; | Optimize the security model for performance and scalability by following the security model best practices. |
| &check; | Have a process to map changes in the organization structure to the security model in Dynamics 365. Do it carefully and sequentially to avoid unwanted cascading effects. |

## Next steps

- Learn about [security controls](security-strategy-security-controls.md) in Dynamics 365
- Learn about [security features](security-strategy-product-ce.md) in customer engagement apps
- Learn about [security features](security-strategy-product-portals.md) in Power Pages
- Learn about [security features](security-strategy-product-oa.md) in finance and operations apps
- Learn how to [make security a priority](security-strategy-day-one-priority.md) from day one
