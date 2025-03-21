---
title: Map Unified Service Desk to Customer Service workspace
description: Learn how to map components in Unified Service Desk to Customer Service workspace features for enhanced productivity.
author: avi-k-mishra
ms.author: avinam
ms.topic: conceptual
ms.date: 03/21/2025
ms.custom:
  - bap-template
  - O25-Service
  - ai-gen-docs-bap
  - ai-gen-description
  - ai-seo-date:03/21/2025
ms.reviewer: edupont
---

# Map components in Unified Service Desk to Customer Service workspace capabilities

***Applies to: Dynamics 365 Customer Service***

This article helps you map components between Customer Service workspace and the components in Unified Service Desk to help with the migration process to Customer Service.

> [!TIP]
> For scenarios without a direct mapping in Customer Service workspace, follow the patterns that we outline here, or use Dynamics 365 capabilities to implement the required business flow.

Here, we provide a detailed component mapping between Unified Service Desk and Customer Service workspace, outlining how various features and functionalities align across both platforms. The article facilitates the migration process by helping the transition of Unified Service Desk components to their counterparts in Customer Service workspace or identifying alternative solutions to achieve similar business workflows. In cases where certain Unified Service Desk scenarios don't have a direct mapping in Customer Service workspace, a strategic approach can be designed to optimize the business flow by using the platform's capabilities.

## Search

Entity searches are FetchXML definitions that query Microsoft Dataverse web services to return data. You can also use replacement parameters within the FetchXML queries in an entity search. Learn more at [Search data using entity searches in Unified Service Desk](/dynamics365/unified-service-desk/search-data-entity-searches).

Customer Service workspace uses Dataverse search. The search box is always available at the top of every page in your app. You can start a new search and quickly find the information that you're looking for.

The following list links to articles about built-in features that you can use to replace custom search implementation:  

- [Dataverse Search](/power-apps/user/relevance-search)
- [Quick Find](/power-apps/user/quick-find)

## Hosted controls

The hosted control concept is central to the Unified Service Desk implementation, and is the primary element used for building agent applications using Unified Service Desk. A hosted control in Unified Service Desk is a .NET component or a model-driven app/external webpage that is hosted within an agent application.

For example, a **CRM Page** type of hosted control is used to display a model-driven apps page in your agent application and a **Standard Web Application** type of hosted control is used of external web pages.

The following table compares the capabilities.

| Component in Unified Service Desk | Customer Service workspace | Purpose |
|---|---|---|
| CRM Page | Application Tab template with a CRM form, such as case, contact, account. | Display and interact with Dynamics 365 entities. |
| Web Hosted Control | Application Tab template | Load external web applications or websites within a session. |
| USD Hosted Control | Custom pages | Replace with Power Apps custom pages. |

Learn more in the following articles:

- [Unified Service Desk Hosted Controls](/dynamics365/unified-service-desk/unified-service-desk-hosted-controls)
- [Manage application tab templates](/dynamics365/customer-service/administer/application-tab-templates)

## Custom hosted control

You might have developed custom Unified Service Desk hosted controls if you had a special requirement that the predefined hosted control types didn't give you. Dataverse provides a Visual Studio template for creating a custom Unified Service Desk hosted control. The template provides basic code as comments to help you get started quickly with creating a custom hosted control.

The following table compares the capabilities.

| Component in Unified Service Desk | Customer Service workspace | Purpose |
|---|---|---|
| Custom Hosted Control                  | Custom Pages                        | Use custom pages to develop tailored applications with intuitive interfaces and complex workflows. |
| Host External and Web Applications      | Session and Application tabs        | Create generic session templates and include an application tab to host the external application. |

Learn more in the following articles:

- [Use custom hosted control in Unified Service Desk](/dynamics365/unified-service-desk/use-custom-hosted-control-unified-service-desk)
- [Converge model-driven and canvas apps using the custom page](/power-apps/maker/model-driven-apps/model-app-page-overview)

## Customer Care Accelerator hosted control

A Customer Care Accelerator (CCA) hosted application hosted control enables you to host an external application or web application in Unified Service Desk and interact with it by using the UII adapters.

The following table compares the capabilities.

| Component in Unified Service Desk | Customer Service workspace | Purpose |
|---|---|---|
| Custom Applications                    | Custom Pages                        | Use custom pages to develop tailored applications with intuitive interfaces and complex workflows. Enhance functionality by using Power Fx formulas, Power Apps code components, and custom connectors for greater flexibility and extensibility. |
| Host External and Web Applications      | Session and Application tabs        | Create generic session templates and include an application tab to host the external application. |

Learn more in the following articles:

- [UII Adapters](/dynamics365/unified-service-desk/uii-adapters)
- [CCA Hosted Application hosted control](/dynamics365/unified-service-desk/cca-hosted-application-hosted-control#create-a-cca-hosted-application-hosted-control)
- [Converge model-driven and canvas apps using the custom page](/power-apps/maker/model-driven-apps/model-app-page-overview)

## Agent scripts

Agent scripting in Unified Service Desk provides guidance to agents about what they should say on calls or what they should type on chat conversations. It includes a script that can use values from any loaded entity on the agent application, hosted control, or the Unified Service Desk context (using replacement parameters).

The following table compares the capabilities.

| Component in Unified Service Desk | Customer Service workspace | Purpose |
|---|---|---|
| Pages                           | Tabs                                  | Customer Service workspace uses tabs to display information instead of separate pages. |
| Sections                        | Agent Script Steps                    | Steps in Customer Service workspace scripts correspond to sections in scripts. |
| Steps                           | Agent Script Steps or Actions         | Customer Service workspace consolidates steps and actions into a unified workflow for streamlined execution. |
| Actions                         | Macros or Power Automate Flows        | Replace Unified Service Desk actions with macros or Power Automate flows to achieve similar functionality. |
| Agent Scripts                   | Smart Assist & Custom Panels         | Redesign flows using Smart Assist and contextual panes. |
| Data Parameterization           | Context Variables                     | Use context variables in Customer Service workspace to pass and retrieve dynamic data. |

Learn more in the following articles:

- [Guide customer interactions with agent scripts in Unified Service Desk](/dynamics365/unified-service-desk/guide-customer-interactions-agent-scripts)
- [Manage agent scripts](/dynamics365/customer-service/administer/agent-scripts)

## Scriptlets

Scriptlets are snippets of JavaScript that are executed when using a special syntax for your replacement parameter. Sometimes the system generated replacement parameters contain the proper data needed for these functions but might not contain the data in the desired format.

The following table compares the capabilities.

| Component in Unified Service Desk | Customer Service workspace |
|---|---|
| UI Automation (Set Field Values, Click Buttons) | Power Automate, Macros, or Custom JavaScript |
| Opening New Tabs/Forms                   | Session templates, app tabs, or JavaScript |
| Fetching Data from CRM                   | Power Automate or Custom JavaScript     |
| Running Business Logic                   | Power Automate, Custom PCF Controls            |
| Integrating External Systems              | Power Automate, Custom Page, or API Calls      |

Learn more in the following articles:

- [Execute scripts using scriptlets in Unified Service Desk](/dynamics365/unified-service-desk/execute-scripts-using-scriptlets-unified-service-desk)
- [Apply business logic using client scripting in model-driven apps using JavaScript](/power-apps/developer/model-driven-apps/client-scripting)

## Session management

Whenever you search for customer information in Unified Service Desk, the system fetches the information from Microsoft Dataverse, and stores it in a session. Each session in the Unified Service Desk client is displayed in a tab in the main screen, and you can identify a session using the session name displayed on the tab.

The following table compares the capabilities.

| Component in Unified Service Desk | Customer Service workspace | Purpose |
|---|---|---|
| Session Lines                 | Native session tab              | In Customer Service workspace, sessions are automatically created when you open case, contact, or custom records. |
| Session Tabs                  | Sub tabs                        | Subtabs are defined by the relationships of the primary record. A case session automatically opens tabs for case details, related activities, etc. Configure entity forms and include tabs to display related records in the model-driven app. |
| Session Timers                | Session Management Entities or Microsoft APM | In Customer Service workspace, session start and end times can be retrieved using Session Management Entities in Dataverse or by implementing custom JavaScript with the Microsoft APM SDK. |

Learn more in the following articles:

- [Session management in Unified Service Desk](/dynamics365/unified-service-desk/session-management-unified-service-desk)
- [Manage session templates](/dynamics365/customer-service/administer/session-templates)

## Toolbars

You can configure toolbars in Unified Service Desk to create or manage buttons in an existing toolbar, or create new toolbars altogether.

The following table compares the capabilities.

| Component in Unified Service Desk | Customer Service workspace | Purpose |
|---|---|---|
| Toolbar Container                       | Command Bar, Ribbon Bar, Navigation Bar  | Actions in the Command Bar or Navigation Bar in Customer Service workspace replace the  toolbar container in Unified Service Desk. |
| Toolbar Hosted Control                  | Custom Buttons in Command Bar/Ribbon Bar | Any custom toolbar hosted control (buttons, actions) needs to be recreated using the Command Bar or Ribbon Bar in Customer Service workspace. |
| Button Actions                          | Command Bar Button (JavaScript)          | Replicate each button's functionality using Command or Ribbon Bar buttons linked to JavaScript or Power FX formulas. |
| Navigation between entity list, dashboard | Sitemap Links / Navigation Bar          | Replace Unified Service Desk toolbar navigation with Sitemap configuration and the Navigation Bar in Customer Service workspace for quick access to entities, custom pages, or dashboards. |

Learn more in the following articles:

- [Execute scripts using scriptlets in Unified Service Desk](/dynamics365/unified-service-desk/execute-scripts-using-scriptlets-unified-service-desk)
- [Customize commands and the ribbon](/power-apps/developer/model-driven-apps/customize-commands-ribbon)

## Windows navigation rule

Window navigation rules define the interaction between various controls in Unified Service Desk. You can use the rules to define the location of the sessions or the model-driven app pages to appear in the Unified Service Desk client application when invoked from a hosted control or an entity search.

The following table compares the capabilities.

| Component in Unified Service Desk | Customer Service workspace | Purpose |
|---|---|---|
| Windows Navigation Rules           | Sessions and tabs | Helps agents increase productivity with a browser-like, tabbed experience. |

Learn more in the following articles:

- [Use window navigation rules in Unified Service Desk](/dynamics365/unified-service-desk/use-window-navigation-rules-unified-service-desk)
- [Customer Service workspace sessions and tabs](/dynamics365/customer-service/implement/csw-overview?tabs=customerserviceadmincenter#customer-service-workspace-sessions-and-tabs)

## KM Control

Use the KM Control type of hosted control to display knowledge base articles in your agent application. Using the new hosted control, your service agents can search for articles, associate or disassociate an article with a case, copy a link to an article, and send it through email or in chat without having to switch applications.

The following table compares the capabilities.

| Component in Unified Service Desk | Customer Service workspace | Purpose |
|---|---|---|
| Create, search, associate, disassociate, and share knowledge base articles without switching applications           | Native Knowledge management | Agents can create, edit, search, publish, and translate knowledge articles directly within the customer service workspace. |

Learn more in the following articles:

- [KM Control in Unified Service Desk](/dynamics365/unified-service-desk/km-control-hosted-control#create-a-km-control-hosted-control)
- [Set up knowledge management](/dynamics365/customer-service/administer/set-up-knowledge-management-embedded-knowledge-search#set-up-knowledge-management)

## Popup notification

Use the Popup Notification hosted control type to display notifications in Unified Service Desk.

The following table compares the capabilities.

| Component in Unified Service Desk | Customer Service workspace | Purpose |
|---|---|---|
| Popup Notification | Global Notification & In-App Notification | To show error, warning, information, success, or user-specific messages. |

Learn more in the following articles:

- [Popup Notification in Unified Service Desk](/dynamics365/unified-service-desk/popup-notification-hosted-control)
- [Send in-app notification](/power-apps/developer/model-driven-apps/clientapi/send-in-app-notifications?tabs=clientapi)
- [Add Global Notification](/power-apps/developer/model-driven-apps/clientapi/reference/xrm-app/addglobalnotification)

## Telephony integration

To integrate Unified Service Desk with your computer telephony integration (CTI) system, use a CTI adapter. The User Interface Integration (UII)CTI framework has components that you can use to build a CTI adapter.

The following table compares the capabilities.

| Component in Unified Service Desk | Customer Service workspace | Purpose |
|---|---|---|
| CIF Hosted Control | CIF 2.0 | For each CIF Hosted Control configured in Unified Service Desk, you must create a channel in Customer Service workspace with an adapter provided by the channel provider. |
| CTI Connector, CTI Desktop Manager, CTI Controls | CIF 2.0 | For CTI integration, configure a channel in Customer Service workspace with an adapter provided by the channel provider. |

Learn more in the following articles:

- [Integrate Unified Service Desk with CTI systems using CTI adapters](/dynamics365/unified-service-desk/integrate-cti-systems-cti-adapters)  
- [Dynamics 365 Channel Integration Framework 2.0](/dynamics365/channel-integration-framework/v2/administer/overview-channel-integration-framework)  
- [Simulator for Channel Integration Framework v. 2.0 and Dynamics 365 Customer Service](cs-set-up-cif2-simulator.md)  

## Listener hosted control

Use the Listener Hosted Control type of hosted control, introduced in Unified Service Desk 2.0, to configure a custom listener for your auditing, diagnostic, and trace logs.

The following table compares the capabilities.

| Component in Unified Service Desk | Customer Service workspace | Purpose |
|---|---|---|
| Listener Hosted Control | Azure App Insights  | App Insights logging can replace all the custom logging you did in the Listener assembly. |

Learn more in the following articles:

- [Listener Hosted Control](/dynamics365/unified-service-desk/listener-hosted-control-hosted-control)
- [Overview of integration with Application Insights](/power-platform/admin/overview-integration-application-insights)

## Unified Service Desk configuration

Unified Service Desk configuration is a great way to filter things that you want your agents to see without having to manage their security roles. Agents can see only those Unified Service Desk components in the Unified Service Desk client application that are added in a configuration assigned to them.

The following table compares the capabilities.

| Component in Unified Service Desk | Customer Service workspace | Purpose |
|---|---|---|
| Unified Service Desk Configuration  | Agent experience profiles | With agent experience profiles, you can create targeted app experiences for agents and supervisors. They're an alternative to building and maintaining custom app. |

Learn more in the following articles:

- [Unified Service Desk configuration](/dynamics365/unified-service-desk/admin/manage-access-using-unified-service-desk-configuration)
- [Agent experience profiles](/dynamics365/customer-service/administer/overview)

## Related content

- [Migrate from Unified Service Desk to Customer Service workspace](cs-usd-migration-guide.md)  
- [Welcome to Dynamics 365 Customer Service](/dynamics365/customer-service/implement/overview)  
- [Get started with Customer Service workspace](/dynamics365/customer-service/implement/csw-overview?tabs=customerserviceadmincenter)  
- [Use the productivity pane to help resolve customer issues](/dynamics365/customer-service/use/csw-productivity-pane)
