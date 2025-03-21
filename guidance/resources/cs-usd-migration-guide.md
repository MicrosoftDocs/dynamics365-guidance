---
title: Migrate from Unified Service Desk to Customer Service workspace
description: Learn how to replace Unified Service Desk functionalities with Customer Service workspace features for enhanced productivity.
author: avi-k-mishra
ms.author: avinam
ms.topic: how-to
ms.date: 03/21/2025
ms.custom:
  - bap-template
  - O25-Service
  - ai-gen-docs-bap
  - ai-gen-description
  - ai-seo-date:03/21/2025
ms.reviewer: edupont
---

# Migrate from Unified Service Desk to Customer Service workspace

***Applies to: Dynamics 365 Customer Service***

This article details the steps to migrate from Unified Service Desk (USD) to Customer Service workspace (CSW).  

> [!TIP]
> This article provides guidance on migrating from Unified Service Desk to Customer Service workspace. For scenarios without a direct mapping in Customer Service workspace, follow the patterns that we outline here, or use Dynamics 365 capabilities to implement the required business flow.

Find tips for how to map capabilities between the two experiences at [Map components in Unified Service Desk to Customer Service workspace capabilities](cs-usd-migration-guide-map-components.md).  

## Deprecation of Unified Service Desk

Find the deprecation notices for Unified Service Desk here:

- [Microsoft Dynamics 365 Unified Service Desk with CRM Online application](https://www.microsoft.com/dynamics-365/blog/it-professional/2025/01/22/transition-from-unified-service-desk-to-customer-service-workspace/)  
- [A deprecation notice in the Customer Service documentation](/dynamics365/customer-service/implement/deprecations-customer-service#dynamics-365-unified-service-desk-to-be-deprecated-in-april-2026)  

Use the extended deprecation period to transition to [Customer Service Workspace](/dynamics365/customer-service/implement/csw-overview?tabs=customerserviceadmincenter).

Timeline:

- Deprecation announced in January 2025 to affected customers and partners.
- Deprecated in April 2026. Microsoft stops investing in Unified Service Desk after this date.
- End of service in April 2027. Unified Service Desk isn't supported by Microsoft after this date.
- End of support in June 2028. Unified Service Desk is taken out of service at this date.

> [!IMPORTANT]
> Unified Service Desk 4.3.0 supports the new security protocol in Microsoft Authentication Library. Due to security updates, customers who can't migrate to Customer Service workspace by April 2026 must update to the latest version of Unified Service Desk.

## Transition to Customer Service workspace

Unified Service Desk optimizes customer service operations by centralizing tools, automating workflows, and empowering agents to resolve issues efficiently. Transitioning to Customer Service workspace offers a strategic advantage by providing a modern, scalable, web-based platform that integrates with the latest Dynamics 365 innovations. A managed transition helps you achieve the following benefits:

- Faster adoption of new features  
- Reduced maintenance overhead  
- Enhanced agent productivity  

At the same time, the transition can align with organizational goals for innovation, customer satisfaction, and operational excellence.  

Learn more at [Get started with Customer Service workspace](/dynamics365/customer-service/implement/csw-overview?tabs=customerserviceadmincenter).

Customer Service workspace provides a modern customer service experience that optimizes agent productivity. It offers the following improvements:

- Modernize customer service with a cloud-based workspace for faster deployment.
- Streamline business processes.
- Simplify channel integration for enhanced omnichannel experiences.
- Personalize customer experiences using AI.
- Improve collaboration with native Microsoft Teams integration.

Learn more at [Get started with Customer Service workspace](/dynamics365/customer-service/implement/csw-overview?tabs=customerserviceadmincenter).  

## Prerequisites

- Access to an environment with Unified Service Desk and an environment with Customer Service workspace  
- Familiarity with both Unified Service Desk and Customer Service workspace  

Learn more about licensing and system requirements at [Customer Service workspace system requirements](/dynamics365/customer-service/implement/customer-service-workspace-system-requirements)  

## Transition guide

The migration from Unified Service Desk to Customer Service workspace involves five key steps:

1. Review the current Unified Service Desk configuration  

    a. Access and analyze the existing Unified Service Desk environment.  
    b. Document technical implementation details, including hosted controls, actions, events, and configurations.  
    c. Identify integrations, customizations, and dependencies critical to business operations.  
1. Map Unified Service Desk capabilities to Customer Service workspace  

    a. Identify capabilities in Customer Service workspace that replace capabilities in Unified Service Desk.  
    b. Map hosted controls, actions, and navigation rules  in Unified Service Desk to session templates, application tab templates, and custom pages in Customer Service workspace.  
    c. Perform a feature-by-feature comparison with Unified Service Desk to ensure parity.  
    d. Determine if any other customization is required to replicate Unified Service Desk functionality.  
1. Build and configure Customer Service workspace

    a. Set up session templates and application tab templates in Customer Service workspace. Learn more at [Customer Service workspace sessions and tabs](/dynamics365/customer-service/implement/csw-overview#customer-service-workspace-sessions-and-tabs).  
    b. Configure navigation, form layouts, and entity-based workstreams to replicate Unified Service Desk behavior.  
    c. Develop custom pages, Power Automate flows, web resources, or other components if needed.  
1. Test and validate

    a. Conduct comprehensive testing in a sandbox environment before deployment.  
    b. Verify that Customer Service workspace meets all business and user experience requirements.  
    c. Gather feedback from key users and make necessary adjustments.  
1. Deploy and monitor

    a. Deploy Customer Service workspace solution components to the production environment, including session templates, application templates, custom pages, web resources, and any dependencies.  
    b. Conduct a phased rollout, allowing gradual adoption and issue resolution.  
    c. Monitor agent feedback, system performance, and error logs to ensure a smooth transition.  
    d. Provide training and support to end-users for improved adoption.  

By following this structured migration process, organizations can efficiently transition from Unified Service Desk to Customer Service workspace while ensuring a **feature-rich, scalable, and user-friendly** environment for agents. Continuous monitoring and feedback loops help optimize Customer Service workspace for improved productivity and user satisfaction.

> [!div class="nextstepaction"]
>[Map components in Unified Service Desk to Customer Service workspace capabilities](cs-usd-migration-guide-map-components.md)  

## Related content

- [Map components in Unified Service Desk to Customer Service workspace capabilities](cs-usd-migration-guide-map-components.md)  
- [Welcome to Dynamics 365 Customer Service](/dynamics365/customer-service/implement/overview)  
- [Get started with Customer Service workspace](/dynamics365/customer-service/implement/csw-overview?tabs=customerserviceadmincenter)  
- [Use the productivity pane to help resolve customer issues](/dynamics365/customer-service/use/csw-productivity-pane)
