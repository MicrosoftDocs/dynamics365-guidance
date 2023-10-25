---
title: Security Checklist
description: The security checklist helps organizations identify and prioritize their key requirements and implementation activities in the areas of privacy and compliance, identify and access, and application security. 
author: riblack-microsoft
ms.author: riblack
ms.topic: conceptual 
ms.date: 03/14/2023
ms.service: dynamics-365
---

# Security Checklist

Use the Success by Design security checklist to identify and prioritize key activities in the areas of privacy and compliance, identify and access, and application security.

## Privacy and compliance

|Done?  |Task  |
|---------|---------|
|&check;|Understand the responsibilities of the service provider as a data processor versus the customer responsibilities as the owner and data controller to ensure compliance on both sides.         |
|&check;|Refer to the Dynamics 365 cloud service agreements and compliance documentation to understand the policies, procedures for handling data, disaster recovery strategy, data residency, encryption, and more.         |

## Identity and access

|Done?  |Task  |
|---------|---------|
|&check;|Establish an identity management strategy covering user access, service accounts, application users, along with federation requirements for SSO and conditional access policies.|
|&check;|Establish administrative access policies targeting different admin roles on the platform, such as service admin and global admin.|
|&check;|Enforce relevant DLP policies and procedures to make changes or request exceptions.|
|&check;|Have necessary controls to manage access to specific environments.|

## Application security

|Done?  |Task  |
|---------|---------|
|&check;|Understand the app-specific security constructs and model your security based on the native access control mechanisms rather than customizing the build.|
|&check;|Understand that hiding information from the view doesn't necessarily remove access—there are alternate mechanisms to access and extract information.|
|&check;|Understand the impact of losing the security context when the data is exported.|
|&check;|Ensure the security model is optimized to perform and provides the foundation for further expansion and scale by following the security model best practices.|
|&check;|Have a process to map changes in the organization structure to the security model in Dynamics 365. Do it cautiously in a serial way due to the downstream cascading effect.|

## Next steps

Visit the next section of the Implementation Guide

- [Business intelligence, reporting, and analytics](business-intelligence-reporting-analytics-overview.md)

Return to learn more about Security

- [Security strategy overview](security.md)
