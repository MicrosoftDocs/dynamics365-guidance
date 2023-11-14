---
title: Integration strategy checklist
description: Get a thorough checklist to help Dynamics 365 implementation teams with their integration strategy.
author: abunduc-ms
ms.author: abunduc
ms.date: 05/23/2023
ms.topic: conceptual

---
# Integration strategy checklist

Use this article to help you develop and manage your strategy for how to integrate with other solutions in a Dynamics 365 implementation project.

## Define business goals

- Document and define goals and expected benefits of integration being implemented in a business-centric way.

- Align the planned integration's purpose with short- and long-term organization goals.

- Ensure the overview of the integration architecture, systems, and integration points is clear and understandable.

- Ensure that stakeholders have a shared understanding of the purpose and scope of the integrations that are being implemented.

## Choose a platform

- Ensure the organization understands the concept of cloud versus on-premises platforms and the boundary between them.

- Plan to use either an integration middleware or messaging service.

- Ensure the integration architecture, platform, or middleware supports the expectations for monitoring, audit, notifications, and alerts.

- Ensure the integration architecture supports the expected level of security, availability, and disaster recovery.

- Ensure all components of the integration architecture support ALM and version control.

## Choose a design

- Align the designs of each integration with the overall integration architecture.

- Avoid unnecessary replication and transmission of data into the solution in integration designs.

- Clearly state the options and benefits of each of the following items: 

  - User interface look and feel  
  - Data  
  - Process integration  
  - Dataverse  

## Choose a pattern

- Design integrations to favor robust, asynchronous messaging-based patterns.

- Align patterns used for each integration with expectations for volumes, frequency, and service protection limitations.

- Set realistic estimates of the operating costs for services, platforms, and storage involved and be aware of how scaling affects them in the future.

## Project governance

- Plan each integration for user and performance testing under realistic loads, as well as the end-to-end process leading up to the integration, across the system boundary, and after the point of integration.

- Plan for testing the end-to-end process patterns used for each integration in line with recommendations for volumes, frequency, and service protection limitations.

- Have change management activities related to integrations that reflect and support overall business goals.

- Complete the impact analysis on upstream and downstream processes.

## Next steps

- [Define business goals](integrate-other-solutions-business-goals.md)  
- [Choose a platform](integrate-other-solutions-choose-platform.md)  
- [Choose a design](integrate-other-solutions-choose-design.md)  
- [Choose a pattern](integrate-other-solutions-choose-pattern.md)  
- [Challenges](integrate-other-solutions-challenges.md)  
- [Product-specific guidance for integration scenarios](integrate-other-solutions-guidance-product.md)  
- [Checklist](integrate-other-solutions-checklist.md)  
- [Case study](integrate-other-solutions-case-study.md)  
