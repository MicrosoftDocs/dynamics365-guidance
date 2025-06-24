---
title: FAQ on Transition to Customer Service Workspace from Unified Service Desk
description: Find tips to help you migrate from Unified Service Desk to Customer Service workspace.
author: rajislearning
ms.author: rajeeku
ms.topic: concept-article
ms.date: 06/24/2025
ms.custom:
    - bap-template
    - O25-Service
    - ai-gen-docs-bap
    - ai-gen-description
    - ai-seo-date:06/24/2025
ms.reviewer: edupont
---

# FAQ on transition to Customer Service workspace from Unified Service Desk

We announced the upcoming deprecation of Dynamics 365 Unified Service Desk (USD) with CRM Online application. In this article, you can find information about how to migrate to Customer Service workspace.

Find the deprecation notices for Unified Service Desk here:

- [Dynamics 365 Unified Service Desk to be deprecated in April 2026](/dynamics365/customer-service/implement/deprecations-customer-service#dynamics-365-unified-service-desk-to-be-deprecated-in-april-2026)
- [Microsoft Dynamics 365 Unified Service Desk with CRM Online application](https://www.microsoft.com/dynamics-365/blog/it-professional/2025/01/22/transition-from-unified-service-desk-to-customer-service-workspace/)

## Why the transition to Customer Service workspace?

Microsoft's customer service platform is Dynamics 365 Customer Service. Customer Service is a cloud-based, modular, and flexible workspace that offers improved performance, usability, and integration with modern Dynamics 365 capabilities. The legacy Unified Service Desk doesn't fully support new cloud-based features and innovations.

### Benefits of Customer Service workspace over Unified Service Desk

Customer Service workspace provides a modern customer service experience that optimizes productivity for agents. With Customer Service workspace, you get an opportunity to achieve benefits such as the following list:

- Modernize your customer service with a cloud-based workspace for faster deployment.
- Focus on your business processes.
- Connect with your customers with simplified channel integration for enhanced omnichannel experiences.
- Personalize your customer experience using AI.
- Enhance collaboration with native Microsoft Teams integration.

## Will the configuration in Unified Service Desk migrate automatically to Customer Service workspace?

No. Unified Service Desk configurations must be re-evaluated and re-implemented in Customer Service workspace. While some components such as agent scripts and macros may be reused, Customer Service workspace uses a different architecture and customization approach.

The [Transition guide and component mapping](cs-usd-migration-guide.md) details how Unified Service Desk components map to capabilities in Customer Service workspace.

## What resources can assist with the transition?

Here are some resources you can use.

- **Migration Playbooks**

  The [Migration playbook](/dynamics365/unified-service-desk/admin/migrate-to-csw?view=dynamics-usd-4.3&preserve-view=true) helps you plan and execute the transition from Unified Service Desk to Customer Service workspace. This playbook gives in-depth planning and best practices and should serve as your primary guidelines.

- **Migration Guide**

  The [Migrate from USD to Customer Service workspace guide](cs-usd-migration-guide.md) outline step-by-step processes of transition in five key steps.

- **Map components reference**

  The [Map components in USD to Customer Service workspace](cs-usd-migration-guide-map-components.md) article is a comprehensive mapping table and covers hosted controls, scripts, toolbars, telephony, and so on. It shows exactly how you find the equivalent of each Unified Service Desk feature in Customer Service workspace.

## What are the architectural differences between Unified Service Desk and Customer Service workspace?

Customer Service workspace is a modern browser-based, multi-session agent app. Unlike the Windows client that Unified Service Desk uses (built on the .NET UII framework with WPF forms, hosted controls, and COM adapters), Customer Service workspace is a model-driven Dynamics 365 app accessed through supported browsers (latest Edge or Chrome).

Customer Service workspace runs only in cloud environments (no on-premises or mobile client) and requires the Dynamics 365 Customer Service app.

## Which Unified Service Desk capabilities don't have equivalent in Customer Service workspace?

In general, almost all core Unified Service Desk features have equivalents in Customer Service workspace, however features like the UII-specific hosted-control SDK and advanced desktop integration don't carry over. In some cases, you must use alternative Dynamics 365 features or Power Platform tools to achieve the same result. [Mapping guide](cs-usd-migration-guide-map-components.md) provides a 1:1 comparison of all major components.

Microsoft is continuously adding new features, so it's worth tracking release notes.

## Sample use cases and potential approach in Customer Service workspace

Here are some use cases and suggestions for how to do things in Customer Service workspace.

### How to perform contextual updates to third party web application

In this scenario, A customer service agent uses Unified Service Desk with Dynamics 365 to manage support tickets, while the company's external customer portal displays real-time status updates. Any change in case within Dynamics 365 should automatically sync and reflect on the external portal.

Learn more at [Update external web apps automatically from Customer Service workspace](customer-service-unified-service-desk-migration-contextual-update-external-app.md).

### How to perform process automation to a desktop application

In this scenario, most contact centers require agents to validate or authenticate customer identities before proceeding with the service engagement. By enhancing Dynamics 365 Customer Service with RPA, agents can automate steps of the validation process, streamline call times and help agents to troubleshoot and solve customer requests faster.

Learn more at [Use RPA with Dynamics 365 Customer Service - Power Automate](/power-automate/desktop-flows/dynamics365-cs-rpa).

### Initiate Agent Script conditionally on Field Change and Save

Agent scripts in Customer Service workspace provide step-by-step guidance to agents, ensuring consistent, compliant, and efficient handling of customer interactions. Based on customer input, different scripts can be used to guide the agent appropriately. Learn more at [Guide representatives with script](/dynamics365/customer-service/administer/agent-scripts).

To enhance agent productivity, it may be necessary to dynamically switch to a different agent script when a specific field is updated and the form is saved. This requirement can be accomplished by using a [Macro](/dynamics365/customer-service/administer/macros) which can evaluate the field value and update the agent script selection. The macro can be triggered on the form's save event using the [Microsoft.ProductivityMacros.runMacro](/dynamics365/customer-service/develop/reference/methods/runmacro) API.

Steps:

1. Define a Macro to Transition Agent Script.

    1. Navigate to: Customer Service Admin Center > Agent Experience > Macros
    1. Create a new macro.
    1. Add the following steps:

        1. Update Session Context - Use "Refresh the Session context" session connector action. This step ensures that current values are available in macro.
        1. Conditional Script Switch – Use Built-in control "Condition" to switch conditions based on field values.
        1. Change Agent Script selection – To select desired agent script, use "Set Script focus" from productivity automation action list.

1. Implement JavaScript to activate the macro on Save. Sample JavaScript reference:

    ```javascript
    function onSave() {
        setTimeout(() => {
                  Microsoft.ProductivityMacros.runMacro("Macro name")
                    .then(result => console.log("Macro executed:", result))
                    .catch(error => console.error("Macro failed:", error));
                  }, 200); // Delay ensures form updates are triggered before
    }
    ```

1. Register JavaScript method developed in above step on [OnSave](/power-apps/developer/model-driven-apps/clientapi/reference/events/form-onsave) event.

### Implement a scratch pad in Customer Service workspace through a custom page

A scratch pad can be implemented using a multiline text box embedded in a custom page, displayed within the [Productivity Pane](/dynamics365/customer-service/use/csw-productivity-pane). For more information see, [Custom productivity tool](/dynamics365/customer-service/administer/manage-custom-productivity-tools). 

For more information on creating and using custom pages in model-driven apps, see [Custom pages for model-driven apps](/power-apps/maker/model-driven-apps/model-app-page-overview). 

Steps:

1. Create a custom page with a text box

    1. Open an existing solution or create a new one in Power Apps.
    1. Add a new Custom Page to the solution.
    1. Design the page:
        1. Insert a Text Input control.
        1. Set the Multiline property to true.
        1. Resize the control to fill the available screen area, using flexible layout containers.
    1. Save and publish the custom page.
    1. Ensure the Customer Service Workspace app is updated with this new page.

- Add the Custom Page to Productivity Tools as a Pane.
    1. Go to Customer Service Admin Center.
    1. Navigate to: Support Experience → Productivity → Productivity Tools
    1. Click + Add Pane and configure:
        1. Name and Unique Name (for example, ScratchPadPane)
        1. Type: Select Custom Page
        1. Custom Page Name: Enter the name of the page created earlier
        1. Global: Set to Yes if the pane should appear across all sessions
        1. Optionally configure Icon, Description, and Learn more link

- Activate the Pane within the Agent Experience Profile
    1. In the Customer Service Admin Center, go to Support Experience → Workspaces → Experience Profiles
    1. Select the Agent Experience Profile to modify.  
    1. In the Productivity Pane section, enable the newly created pane.

## Related content

- [Migrate from Unified Service Desk to Customer Service workspace](cs-usd-migration-guide.md)  
- [Map components in Unified Service Desk to Customer Service workspace capabilities](cs-usd-migration-guide-map-components.md)  
- [Update external web apps automatically from Customer Service workspace](customer-service-unified-service-desk-migration-contextual-update-external-app.md)  
