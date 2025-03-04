---
title: Unified Service Desk Migration Guide
description: Provides a structured approach for transitioning from Unified Service Desk (USD) to the Customer Service Workspace (CSW) in Dynamics 365.
author: avi-k-mishra
ms.author: avinam
ms.topic: how-to #Required; don't change.
ms.date: 03/03/2025
ms.custom: 
    - bap-template
    - O25-Service
ms.reviewer: edupont
ms.collection: #Required; don't change.
---

# Transitioning from Unified Service Desk (USD)

***Applies to: Dynamics 365 Customer Service***

This article details the necessary steps and component mapping between Unified Service Desk (USD) and Customer Service Workspace (CSW) to assist with the migration process.

> [!NOTE]
> This document provides guidance on migrating from Unified Service Desk (USD) to Customer Service Workspace (CSW). For scenarios without a direct mapping in CSW, follow the patterns outlined below or leverage Dynamics 365 capabilities to implement the required business flow.

## Unified Service Desk Depreciation

On April 1, 2026, we are deprecating the [Microsoft Dynamics 365 Unified Service Desk (USD) with CRM Online application](https://www.microsoft.com/en-us/dynamics-365/blog/it-professional/2025/01/22/transition-from-unified-service-desk-to-customer-service-workspace/). Its end of support date will be June 30, 2028. We are encouraging customers to use this extended deprecation period to transition to the [Customer Service Workspace](https://learn.microsoft.com/en-us/dynamics365/customer-service/implement/csw-overview?tabs=customerserviceadmincenter)

Timeline
-	**Deprecation announced in January 2025** : Date of communication to affected customers and partners we are planning to deprecate the Unified Service Desk
-	**Deprecated in April 2026** : Date after which we are no longer going to invest in Unified Service Desk
-	**End of Service in April 2027** : Date after which we are no longer going to support Unified Service Desk
-	**End of Support in June 2028** : Date the Unified Service Desk is going to be taken out of service

**Important!** We will release a new version of USD that supports the new security protocol for customers who may not be able to migrate to CSW by April 2026. Its mandatory that all customers’ needs to migrate to this latest version of USD to be in complaint with our SFI initiative.

## Transition to Customer Service Workspace (CSW)

Unified Service Desk (USD) has been a cornerstone in optimizing customer service operations by centralizing tools, automating workflows, and empowering agents to resolve issues more efficiently. However, as we strive to stay ahead in delivering exceptional customer experience, transitioning to Customer Service Workspace (CSW) offers a strategic advantage. CSW provides a modern, scalable, and web-based platform that integrates seamlessly with the latest Dynamics 365 innovations. This transition ensures faster adoption of new features, reduced maintenance overhead, and enhanced agent productivity, all while aligning with our organizational goals for innovation, customer satisfaction, and operational excellence.
Customer Service workspace provides modern customer service experience that optimizes agent productivity. By migrating from the Unified Service Desk to Customer Service workspace, you can:
-	Modernize your customer service with a cloud-based workspace for faster deployment.
-	Focus on your business processes.
-	Connect with your customers with simplified channel integration for enhanced omnichannel experiences.
-	Personalize your customer experience using AI.
-	Enhance collaboration with native Microsoft Teams integration.

## Prerequisites

- Access to both USD and CSW environments
- Familiarity of both USD and CSW
- For more information about licensing and system requirements, refer to [Customer Service workspace system requirements](https://learn.microsoft.com/en-us/dynamics365/customer-service/implement/customer-service-workspace-system-requirements).

## Transition Guidance
The migration from the Unified Service Desk (USD) to Customer Service Workspace (CSW) involves five key steps:

1. Review Current USD Setup
    - Access and analyze the existing Unified Service Desk (USD) environment.
    - Document technical implementation details, including hosted controls, actions, events, and configurations.
    - Identify integrations, customizations, and dependencies critical to business operations.
2. Map USD Features to CSW
   - Identify equivalent Customer Service Workspace (CSW) features for USD components.
   - Map USD Hosted Controls, Actions, and Navigation Rules to CSW Session Templates, Application Tab Templates, and Custom Pages.
   - Determine if any additional customization is required to replicate USD functionality.
3. Build & Configure CSW
   - Set up Session Templates and Application Tab Templates in CSW.
   - Configure navigation, form layouts, and entity-based workstreams to replicate USD behavior.
   - Develop custom pages, Power Automate flows, web resources, or other components if needed.
4. Test & Validate
   - Conduct comprehensive testing in a sandbox environment before deployment.
   - Verify that CSW meets all business and user experience requirements.
   - Perform a feature-by-feature comparison with USD to ensure parity.
   - Gather feedback from key users and make necessary adjustments.
5. Deploy & Monitor
   - Deploy CSW solution components, including session templates, application templates, custom pages, web resources, and any dependencies, to the production environment.
   - Conduct a phased rollout, allowing gradual adoption and issue resolution.
   - Monitor agent feedback, system performance, and error logs to ensure a smooth transition.
   - Provide training and support to end-users for improved adoption.

By following this structured migration process, organizations can efficiently transition from USD to CSW while ensuring a **feature-rich, scalable, and user-friendly** environment for agents. Continuous monitoring and feedback loops will help optimize CSW for improved productivity and user satisfaction.

## Transitioning Components: Mapping USD to CSW

This section provides a detailed component mapping between Unified Service Desk (USD) and Customer Service Workspace (CSW), outlining how various features and functionalities align across both platforms. It serves as a guide to facilitate the migration process by assisting in the transition of USD components to their CSW counterparts or identifying alternative solutions to achieve similar business workflows. In cases where certain USD scenarios do not have a direct mapping in CSW, a strategic approach can be designed to optimize the business flow by leveraging the platform's capabilities.

## Search
Entity searches are FetchXML definitions that query Microsoft Dataverse web services to return data. You can also use replacement parameters within the FetchXML queries in an entity search.

- [Search data using entity searches in Unified Service Desk](https://learn.microsoft.com/en-us/dynamics365/unified-service-desk/search-data-entity-searches?view=dynamics-usd-4.2)

**CSW equivalent**

With Dataverse search, the search box is always available at the top of every page in your app. You can start a new search and quickly find the information that you're looking for.
Out of the box features which can be leveraged to replace custom search implementation -
- [Dataverse Search](https://learn.microsoft.com/en-us/power-apps/user/relevance-search)
- [Quick Find](https://learn.microsoft.com/en-us/power-apps/user/quick-find)

## Hosted Controls
The hosted control concept is central to the Unified Service Desk implementation, and is the primary element used for building agent applications using Unified Service Desk. A hosted control in Unified Service Desk is a .NET component or a model-driven app/external webpage that is hosted within an agent application.

For example, a **CRM Page** type of hosted control is used to display a model-driven apps page in your agent application and a **Standard Web Application** type of hosted control is used of external web pages.

- [Unified Service Desk Hosted Controls](https://learn.microsoft.com/en-us/dynamics365/unified-service-desk/unified-service-desk-hosted-controls?view=dynamics-usd-4.2)
- [Manage application tab templates](https://learn.microsoft.com/en-us/dynamics365/customer-service/administer/application-tab-templates)

**USD to CSW equivalent**
| USD Component | CSW Equivalent | Purpose |
|--------------------------------|--------------------------------------|---------|
| CRM Page | Application Tab template with a CRM form (e.g., case, contact, account) | Display and interact with Dynamics 365 entities. |
| Web Hosted Control | Application Tab template | Load external web applications or websites within a session. |
| USD Hosted Control | Custom Pages within Customer Service Workspace | Replace with Power Apps custom pages. |

## Custom Hosted Control
You can develop custom Unified Service Desk hosted controls if you have a special requirement that isn’t addressed by the predefined hosted control types. Microsoft Dataverse provides a Visual Studio template for creating a custom Unified Service Desk hosted control. The template provides basic code as comments to help you get started quickly with creating a custom hosted control.

- [Use custom hosted control in Unified Service Desk](https://learn.microsoft.com/en-us/dynamics365/unified-service-desk/use-custom-hosted-control-unified-service-desk?view=dynamics-usd-4.2)
- [Converge model-driven and canvas apps using the custom page](https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/model-app-page-overview)

**USD to CSW equivalent**
| USD Component | CSW Equivalent | Purpose |
|--------------------------------|--------------------------------------|---------|
| Custom Hosted Control                  | Custom Pages                        | Use custom pages to develop tailored applications with intuitive interfaces and complex workflows. |
| Host External and Web Applications      | Session and Application tabs        | Create generic session templates and include an application tab to host the external application. |

## CCA Hosted Control
A Customer Care Accelerator (CCA) hosted application hosted control enables you to host an external application or web application in Unified Service Desk and interact with it by using the UII adapters.

- [UII Adapters](https://learn.microsoft.com/en-us/dynamics365/unified-service-desk/uii-adapters?view=dynamics-usd-4.2)
- [CCA Hosted Application hosted control](https://learn.microsoft.com/en-us/dynamics365/unified-service-desk/cca-hosted-application-hosted-control?view=dynamics-usd-4.2#create-a-cca-hosted-application-hosted-control)
- [Converge model-driven and canvas apps using the custom page](https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/model-app-page-overview)

**USD to CSW equivalent**
| USD Component         | CSW | Purpose |
|----------------------------------------|--------------------------------------|---------|
| Custom Applications                    | Custom Pages                        | Use custom pages to develop tailored applications with intuitive interfaces and complex workflows. Enhance functionality by leveraging Power Fx formulas, PowerApps code components, and custom connectors for greater flexibility and extensibility. |
| Host External and Web Applications      | Session and Application tabs        | Create generic session templates and include an application tab to host the external application. |

## Agent Scripts
Agent scripting in Unified Service Desk provides guidance to agents about what they should say on calls or what they should type on chat conversations. It includes a script that can use values from any loaded entity on the agent application, hosted control, or the Unified Service Desk context (using replacement parameters).

- [Guide customer interactions with agent scripts in Unified Service Desk](https://learn.microsoft.com/en-us/dynamics365/unified-service-desk/guide-customer-interactions-agent-scripts?view=dynamics-usd-4.2)
- [Manage agent scripts](https://learn.microsoft.com/en-us/dynamics365/customer-service/administer/agent-scripts)

**USD to CSW equivalent**
| USD Component         | CSW | Purpose |
|---------------------------------|---------------------------------------|---------|
| Pages                           | Tabs                                  | CSW uses tabs to display information instead of separate USD pages. |
| Sections                        | Agent Script Steps                    | Steps in CSW scripts correspond to sections in USD scripts. |
| Steps                           | Agent Script Steps or Actions         | CSW consolidates steps and actions into a unified workflow for streamlined execution. |
| Actions                         | Macros or Power Automate Flows        | Replace USD actions with macros or Power Automate flows to achieve similar functionality. |
| Agent Scripts                   | Smart Assist & Custom Panels         | Redesign flows using Smart Assist and contextual panes. |
| Data Parameterization           | Context Variables                     | Use context variables in CSW to pass and retrieve dynamic data. |

## Scriptlets
Scriptlets are snippets of JavaScript that are executed when using a special syntax for your replacement parameter. Sometimes the system generated replacement parameters contain the proper data needed for these functions but might not contain the data in the desired format.

- [Execute scripts using scriptlets in Unified Service Desk](https://learn.microsoft.com/en-us/dynamics365/unified-service-desk/execute-scripts-using-scriptlets-unified-service-desk?view=dynamics-usd-4.2)
- [Apply business logic using client scripting in model-driven apps using JavaScript](https://learn.microsoft.com/en-us/power-apps/developer/model-driven-apps/client-scripting)

**USD to CSW equivalent**
| USD Component            | CSW Equivalent            |
|-------------------------------------------|------------------------------------------------|
| UI Automation (Set Field Values, Click Buttons) | Power Automate, Macros, or Custom JavaScript |
| Opening New Tabs/Forms                   | CSW Session Templates, App Tabs, or JavaScript |
| Fetching Data from CRM                   | Power Automate or Custom JavaScript in CSW     |
| Running Business Logic                   | Power Automate, Custom PCF Controls            |
| Integrating External Systems              | Power Automate, Custom Page, or API Calls      |

## Session Management
Whenever you search for customer information in Unified Service Desk, the system fetches the information from Microsoft Dataverse, and stores it in a session. Each session in the Unified Service Desk client is displayed in a tab in the main screen, and you can identify a session using the session name displayed on the tab.

- [Session management in Unified Service Desk](https://learn.microsoft.com/en-us/dynamics365/unified-service-desk/session-management-unified-service-desk?view=dynamics-usd-4.2)
- [Manage session templates](https://learn.microsoft.com/en-us/dynamics365/customer-service/administer/session-templates)

**USD to CSW equivalent**
| USD Component         | CSW | Purpose |
|----------------------------------------|--------------------------------------|---------|
| Session Lines                 | Native CSW Session tab              | In CSW, sessions are automatically created when you open case, contact, or custom records. |
| Session Tabs                  | CSW Sub tabs                        | Sub-tabs are defined by the relationships of the primary record. A case session automatically opens tabs for case details, related activities, etc. Configure entity forms and include tabs to display related records in the model-driven app. |
| Session Timers                | Session Management Entities or Microsoft APM | In CSW, session start and end times can be retrieved using Session Management Entities in Dataverse or by implementing custom JavaScript with the Microsoft APM SDK. |

## Toolbars
You can configure toolbars in Unified Service Desk to create or manage buttons in an existing toolbar, or create new toolbars altogether.

- [Execute scripts using scriptlets in Unified Service Desk](https://learn.microsoft.com/en-us/dynamics365/unified-service-desk/execute-scripts-using-scriptlets-unified-service-desk?view=dynamics-usd-4.2)
- [Customize commands and the ribbon](https://learn.microsoft.com/en-us/power-apps/developer/model-driven-apps/customize-commands-ribbon)

**USD to CSW equivalent**
| USD Component         | CSW | Purpose |
|-----------------------------------------|------------------------------------------|---------|
| Toolbar Container                       | Command Bar, Ribbon Bar, Navigation Bar  | The USD toolbar container is replaced by actions placed in the Command Bar or Navigation Bar in CSW. |
| Toolbar Hosted Control                  | Custom Buttons in Command Bar/Ribbon Bar | Any custom toolbar hosted control (buttons, actions) needs to be recreated using the Command Bar or Ribbon Bar in CSW. |
| Button Actions                          | Command Bar Button (JavaScript)          | Replicate each button's functionality using Command or Ribbon Bar buttons linked to JavaScript or Power FX formulas. |
| Navigation between entity list, dashboard | Sitemap Links / Navigation Bar          | Replace USD toolbar navigation with Sitemap configuration and the Navigation Bar in CSW for quick access to entities, custom pages, or dashboards. |

## Windows Navigation Rule
Window navigation rules define the interaction between various controls in Unified Service Desk. You can use the rules to define the location of the sessions or the model-driven app pages to appear in the Unified Service Desk client application when invoked from a hosted control or an entity search.

- [Use window navigation rules in Unified Service Desk](https://learn.microsoft.com/en-us/dynamics365/unified-service-desk/use-window-navigation-rules-unified-service-desk?view=dynamics-usd-4.2)
- [Customer Service workspace sessions and tabs](https://learn.microsoft.com/en-us/dynamics365/customer-service/implement/csw-overview?tabs=customerserviceadmincenter#customer-service-workspace-sessions-and-tabs)

**USD to CSW equivalent**
| USD Component         | CSW | Purpose |
|-------------------------------------|------------------------------------------|---------|
| Windows Navigation Rules           | Customer Service Workspace sessions and tabs | Helps agents increase productivity with a browser-like, tabbed experience. |

## KM Control
Use the KM Control type of hosted control to display knowledge base articles in your agent application. Using the new hosted control, your service agents can search for articles, associate or disassociate an article with a case, copy a link to an article, and send it through email or in chat without having to switch applications.

- [KM Control in Unified Service Desk](https://learn.microsoft.com/en-us/dynamics365/unified-service-desk/km-control-hosted-control?view=dynamics-usd-4.2#create-a-km-control-hosted-control)
- [Set up knowledge management](https://learn.microsoft.com/en-us/dynamics365/customer-service/administer/set-up-knowledge-management-embedded-knowledge-search#set-up-knowledge-management)

**USD to CSW equivalent**
| USD Component         | CSW | Purpose |
|-------------------------------------|------------------------------------------|---------|
| Create, search, associate, disassociate, and share knowledge base articles without switching applications           | Native Knowledge management | Agents can create, edit, search, publish, and translate knowledge articles directly within the customer service workspace. |

## Popup Notification
Use the Popup Notification hosted control type to display notifications in Unified Service Desk.

- [Popup Notification in Unified Service Desk](https://learn.microsoft.com/en-us/dynamics365/unified-service-desk/popup-notification-hosted-control?view=dynamics-usd-4.2)
- [Send in-app notification](https://learn.microsoft.com/en-us/power-apps/developer/model-driven-apps/clientapi/send-in-app-notifications?tabs=clientapi)
- [Add Global Notification](https://learn.microsoft.com/en-us/power-apps/developer/model-driven-apps/clientapi/reference/xrm-app/addglobalnotification)

**USD to CSW equivalent**
| USD Component | CSW Equivalent | Purpose |
|--------------------------------|--------------------------------------|---------|
| Popup Notification            | Global Notification & In-App Notification | To show error, warning, information, success, or user-specific messages. |

## Telephony integration
To integrate Unified Service Desk with your computer telephony integration (CTI) system, use a CTI adapter. The User Interface Integration (UII)CTI framework has components that you can use to build a CTI adapter.

- [Integrate Unified Service Desk with CTI systems using CTI adapters](https://learn.microsoft.com/en-us/dynamics365/unified-service-desk/integrate-cti-systems-cti-adapters?view=dynamics-usd-4.2)
- [Dynamics 365 Channel Integration Framework 2.0](https://learn.microsoft.com/en-us/dynamics365/channel-integration-framework/v2/administer/overview-channel-integration-framework)

**USD to CSW equivalent**
| USD Component            | CSW Equivalent | Purpose |
|-------------------------------------------|--------------------------------------|---------|
| CIF Hosted Control                        | CIF 2.0                             | For each CIF Hosted Control configured in USD, you need to create a channel in CSW with an adapter provided by the channel provider. |
| CTI Connector, CTI Desktop Manager, CTI Controls | CIF 2.0                             | For CTI integration, configure a channel in CSW with an adapter provided by the channel provider. |

## Listener Hosted Control
Use the Listener Hosted Control type of hosted control, introduced in Unified Service Desk 2.0, to configure a custom listener for your auditing, diagnostic, and trace logs.

- [Listener Hosted Control](https://learn.microsoft.com/en-us/dynamics365/unified-service-desk/listener-hosted-control-hosted-control?view=dynamics-usd-4.2)
- [Overview of integration with Application Insights](https://learn.microsoft.com/en-us/power-platform/admin/overview-integration-application-insights)

**USD to CSW equivalent**
| USD Component  | CSW Equivalent | Purpose |
|---------------------------------|--------------------------------------|---------|
| Listener Hosted Control        | Azure App Insights                 | All the custom logging done in the Listener assembly should be replaced by App Insights logging. |

## Learn more

- [Welcome to Dynamics 365 Customer Service](https://learn.microsoft.com/en-us/dynamics365/customer-service/implement/overview)  
- [Get started with Customer Service workspace](https://learn.microsoft.com/en-us/dynamics365/customer-service/implement/csw-overview?tabs=customerserviceadmincenter)
