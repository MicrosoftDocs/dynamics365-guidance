---
title:  Extend finance and operations apps
description: Find guidance on how we can extend functionality to accommodate your organization’s specific processes and requirements, with a focus on Dynamics 365 finance and operations apps.
author: abunduc-ms
ms.author: abunduc
ms.date: 05/11/2023
ms.topic: conceptual

---

# Extend finance and operations apps in Dynamics 365 implementation projects

When you're implementing a solution that includes Dynamics 365, you often have to extend the default capabilities. This article looks at some of the specifics for Dynamics 365 finance and operations apps, such as Dynamics 365 Finance, Dynamics 365 Supply Chain Management, and Dynamics 365 Commerce. For solutions with customer engagements apps, you get more capabilities of the Power Platform. Learn more at [Extend customer engagement apps](extend-your-solution-guidance-product-ce.md).  

## Overview

The Dynamics 365 finance and operations apps have an extensibility model so that you can extend the out-of-box functionality to fit other requirements.  

The extension model itself is a toolset, Application Lifecycle Management (ALM) in Azure DevOps. The SDK is well described in Microsoft Learn, Microsoft Training, and in multiple community sources. Learn more at these two great entry points for learning about extensions and development in Dynamics 365 finance and operations apps:  

- Learn more at [Extensibility home page](/dynamics365/fin-ops-core/dev-itpro/extensibility/extensibility-home-page) in the finance and operations documentation  
- Follow the learning path at [Introduction to developing with Dynamics 365 finance and operations apps](/training/paths/introduction-develop-finance-operations/)  

In this section, we first look at what we can do to enhance functionality and UI [without extending the application](#personalization-and-no-code-options). Then we give a brief overview of [the extension model](#extending-the-application), and finally highlight some of [the tools and practices](#advanced-practices-and-tools) that are available for professional developers when they extend the application.  

## Examples

Let's take a look at what we can extend without changing the application components:

||Extension example 1| Extension example 2 |Extension example 3 |
|-| --- | --- | --- |
| **Requirement**| Create a custom workspace with tiles and lists from multiple forms and queries across the manufacturing module.| Add a table to hold a list of food allergens. Add the allergen field to the sales line record for the user to indicate that a product contains the specific allergen | Add code to automatically change the status of the new production order to *Started* when the user firms a planned production order. |
| **Tools and components**| Use the personalization feature and *add to workspace* functionality in the UI to put together the desired workspace and components. No change to code or application components is needed.| Use Visual Studio to add the extended data types, the tables and fields, and the extensions to the **Sales line** table and the **Sales Order** form. This change requires new and changed application components and must follow software development lifecycle (SDLC), build, and deployment guidelines. | Use Visual Studio to extend the X++ business logic, add appropriate event handlers, class, methods, and X++ code to catch the event that the planned order is firmed. You can then run the correct code pattern to bring the new production order to started status. This change requires new and changed application components and X++ code, and must follow SDLC, build, and deployment guidelines. Considerations about scalability and performance when large numbers of planned orders are firmed using appropriate developer tools should be considered |
|**Skills required**|Requires user-level experience with navigation of the relevant module, navigation, and personalization.| Requires entry-level professional developer experience in Dynamics 365 finance and operations apps. Also requires familiarity with Visual Studio, building procedures, and best practices. | Requires medium- to expert-level professional developer experience in Dynamics 365 finance and operations apps. Also requires familiarity with Visual Studio, build procedure, best practices, and, ideally, frameworks like SysOperations Framework, Multithreading, and performance-checking tools and patterns. |

## Personalization and no-code options

Dynamics 365 finance and operations apps offer a rich extension model with minimal impact on future updates. However, we recommend that implementations don't extend the default experiences through code. This approach lowers risk, maintenance, and project complexity.

It's a best practice to consider if noninvasive personalization or configuration can meet the required functionality before you decide to meet a certain requirement through an extension. Dynamics 365 finance and operations apps offer wide options for personalizing the UI, creating user specific experiences, and automating processes without any programming.

As the following table shows, many options are available to find alternative approaches to extending Dynamics 365. The table doesn't show an exhaustive list. More options for low code and no code options are mentioned in [Integrate with other solutions](integrate-other-solutions.md). The decision of whether to extend comes down to user efficiency and value for your customers.

| Tools | What is it? | Description | Characteristics |
| --- | --- | --- | --- |
| **Restricted personalization** | The application remembers the last settings for sorting, column width, critical values in queries and dialogs. | While personalization isn't really extension as such, users can store selections in dialogs, expansion of relevant fast tables, and aligning the column width so that more columns are visible on a given form. | Users can share personalizations, and admins can manage personalization from the **Personalization** page. |
| **Personalization of forms/UI** | Personalization bar in forms and workspaces. | With personalization, users or admins can add or hide fields or sections, change labels, change the order of columns, and edit the tab order for skipping fields. | Personalizations can be shared by users or managed centrally by an admin from the **Personalization** page. |
| **Saved views** | Saved views combine personalization of a form with filtering and sorting of the form's data source.  | A saved view is a powerful tool to quickly switch between tailored views of columns. A saved view can also capture different filters and sorting on the same form, depending on the specific task at hand. For example, a buyer in a pharmaceutical company wants a simple view of the purchase order screen for nonregulated materials when they purchase regulated materials for manufacturing. | Users can share saved views. Admins can manage them centrally from the **Personalization** page. May require the *Saved views* feature to be turned on. |
| **Custom Workspaces** | Users can use personalization and the “add to workspace” button to add tiles, views, or links to an existing or custom workspace. | This functionality allows users to tailor their experience to their needs. Workspaces provide glanceable information about the most important measures, actionable items, and relevant links to other pages.  | Users can share custom and personalized workspaces, and admins can manage workspaces centrally from the **Personalization** page. |
| **Custom fields** | Users with certain security roles can add up to 20 custom fields to tables | Dynamics 365 finance and operations apps have a rich set of features that apply across a wide set of industries. Some organizations require more fields on certain tables; for example, the item or customer master data, or the sales order header. This feature allows the user to create these fields. These fields are specific to the environment that they're created in. They can't be reached by developer tools. | Users can share custom fields and the personalized forms to show the fields. Admins can manage custom fields centrally from the **Personalization** page. **Caution**: Deleting a custom field is irreversible and results in the loss of the data in the custom column. |
| **Grid capabilities** | The grids on forms have capabilities that can eliminate the need for an extension. | The grid offers the following capabilities: <ul><li> Calculating totals for columns in the grid footer </li><li> Pasting from Excel </li><li> Calculating math expressions. For example, if the user enters 3*8 in a numeric field and presses tab, the system calculates and enters the result of 24 </li><li> Grouping tabular data in one or more levels in expandable groups </li><li> Freeze panes so important information doesn't scroll out of view when scrolling horizontally </li></ul>| The admin can enable the New Grid Control feature from feature management. There are certain limitations, see the reference at the bottom of the section. |
| **Embedded canvas apps** | The user can add a canvas app to a form or workspace as embedded into the UI or as a menu item that can pull up the app from the Power Apps menu. | By embedding a canvas Power App, citizen developers can use low-code/no-code options for interacting with data in Dataverse directly from the Dynamics 365 finance and operations apps. **Important**: If the app must interact with Dynamics 365 finance and operations apps data, integration to Dataverse must be in place, and the app must support the required actions. | Learn more at [Integrate with other solutions](integrate-other-solutions.md).
| **Excel integration** | Users can extract or edit data on most forms in the system by clicking on the office icon. | The Excel integration allows for a wide variety of scenarios for entering, presenting, and interacting with data in way that isn't possible from the UI. In addition to the export-to and open-in Excel option, the user can create workbooks and templates for specific purposes. Excel has many features for presentation and offers data manipulation capabilities for larger datasets that users can't do in the system UI. | With great power comes great responsibility. While it's easy to change a whole column of data and publish that data into the system, it's equally easy to make a mistake. |
<!-- DEPRECATED> | **Mobile workspaces** | Users can view, edit, and act on business data, even if they have intermittent network connectivity on an app for iPhone and Android. | IT admins can build and publish mobile workspaces that have been tailored to their organization. The app uses existing code assets. IT admins can easily design mobile workspaces by using the point-and-click workspace designer that is included with the web client. The application has 13 predefined workspaces out-of-the-box that cover Finance, AR, AP, and HR functions. | Simple actions can be done from the mobile workspaces. Most more advanced actions require extension. | -->

## Extending the application

In this section, we provide a high-level introduction to the extension model and discuss required skill set and practices used when extending. We also highlight some of the tools and techniques that we recommend that you use to ensure a clean, high-performing, and future-proof solution.

The following table is an overview of the components, the consideration for extensions, and the related characteristics.

| Component | Editor | Considerations | Don't |
| --- | --- | --- | --- |
| **User interface** | Graphical editor in Visual Studio with preview.  | Forms must adhere to patterns. The editor in Visual Studio has a rich modeler that helps the developer applying the right structure to the screens. This ensures performance when loading the form, adaptability across different resolutions and screen sizes and consistency across the UI. | Deviate from the predefined patterns and create monster all-in-one screen style forms. They're often a result of the designer trying to replicate a legacy system experience. |
| **Data model and queries** | Metadata editor in Visual Studio for Tables, Fields, Extended Data Types, Enums Queries and Views | Follow best practices and frameworks. Apply indexes and define delete actions. Normalize. Use effective date framework when applicable. Keep performance in mind. Use field lists when performance is a risk. | Create redundancy or replicate poor modeling from legacy apps. |
| **Business logic** | X++ Editor in Visual Studio. | Adjust compiler setting to alert about best practices, code with the goal of zero deviations. Use code patterns and frameworks. Practice good developer citizenship. Write clean easily readable code. Run CAR report and use `compatibility checker.Unit` to test the code | Ignore best practices, write long methods or over comment the code. |
| **Reporting** | SSRS report editor in Visual Studio | SSRS reports are good for certain precision designs and tabular lists. Learn more at [Business intelligence, reporting, and analytics](business-intelligence-reporting-analytics-overview.md). | Reach for the SSRS report option if there's a better way. |
| **Data entities** | Metadata editor in Visual Studio  | The out-of-the-box data entities are general purpose entities are built to support a wide variety of features surrounding business entity. In scenarios where a high volume, low latency interface is required it's recommended to build custom data entities with targeted and specific features needed to support high volume interfaces in the implementation. | Create data source proliferation. Learn more at [Integrate with other solutions](integrate-other-solutions.md). |

## Development architecture

The architecture of the development environment includes the software development kit (SDK), which consists of Visual Studio development tools and other components. Source control through Azure DevOps allows multi-developer scenarios, where each developer uses a separate development environment. Deployable packages are compiled and packaged in a build environment or a build service and uploaded to Dynamics Lifecycle Services (LCS) for deployment to nonproduction environments. Deployment to the production environment happens after proper testing has been done in the UAT environment and users/stakeholders have signed off as described in the SDLC.

:::image type="content" source="media/extend_solution_dev_environment_architecture.png" alt-text="A sample of a development architecture" lightbox="media/extend_solution_dev_environment_architecture.png":::

Learn more at [Application lifecycle management](application-lifecycle-management.md).

## Cross-app integration

Cross-app integration options include Dual-Write, Virtual Tables, and Business and Data events. This way, developers can use all the capabilities of Dataverse and Microsoft Power Platform to make extensions. The Dataverse components are easy to install and configure, and the extension itself can often be made with low code-no code options. For the IT professional, the integration options allow for a single workspace, Visual Studio, and familiar languages, C\#, to develop extensions.

With the connection between Dynamics 365 and Dataverse, you get access to the Power Platform and can use low-code/no-code developer models on Dynamics 365 data.

Examples include embedded Power Apps, Power BI reports or dashboards, in standalone apps or portals, or integrated with other Dynamics 365 apps, without making changes through extensions to the finance and operations app and data layer.

For example, an implementation project requires a lightweight product catalog in Dynamics 365 Supply Chain Management with crisp, high-resolution images in a form, or the ability to take pictures to such a catalog with a phone app. These extensions could be made by integrating Dataverse through virtual tables and then embedding a canvas app in the Dynamics 365 user interface to show the catalog and another app to snap the picture and save it to the catalog.

See more details about integration to Dataverse in [Integrate with other solutions](integrate-other-solutions.md).

## Advanced practices and tools

As we mentioned earlier, it's always sound advice to be good citizen developers. In Dynamics 365 finance and operations apps, you can make sure that you follow that principle by understanding, learning, and using the following tools and best practices as shown in the following table.

| Tools | What is it? | Description | Characteristics |
| --- | --- | --- | --- |
| **Best practice check** | Best practice checks for X++ and application components are built into Visual Studio. They can be errors, warnings, or informational. | Developers should strive for zero deviations. The best practices are made to ensure and updatable, performing and user friendly solution | You can stop developers from checking in code with best practice deviations. |
| **Compatibility report** | The compatibility checker tool can detect metadata breaking changes against a specified baseline release or update. | The compatibility checker tool is available as one of the dev tools. You can use it to ensure that your solutions are backward-compatible with earlier releases before you install or push updates | The tool can't detect all breaking changes. Learn more at [Compatibility checker tool](/dynamics365/fin-ops-core/dev-itpro/extensibility/compatibility-checker-tool). |
| **Traces and trace parser** | The users can take a trace of runtime execution directly from the UI. The trace parser can be used to read the trace. | You can use the trace parser to consume traces and analyze performance in your deployment. The trace parser can find and diagnose various types of errors. You can also use the tool to visualize execution of X++ methods, and the execution call tree. | The trace parser tool can be found in the PerfSDK folder in your development environments. |
| **Performance timer** | Performance timer is a tool in the web client that can help you to determine why your system’s performance might act slow. | To open the Performance timer, open your web page with the added parameter debug=develop. You can see counters for client time and server time, and the total time. You can also see a set of performance counters, a list of expensive server calls, how many SQL queries were triggered by this individual call, and which SQL query was the most expensive. | The tool itself has a performance impact. |
| **LCS Logs** | Under Environment Monitoring in LCS there a comprehensive collection of tools and information that you can use to analyze and diagnose your cloud environment. | The logs provide for example: <ul> <li> Activity Monitoring: A visualization of the activity that has happened in the environment for given timeline in terms of user load, interaction and activity. </li><li> Information about slow queries, deadlocks, etc.</li></ul> | The tools under Environment Monitoring are effective at diagnosing potential or growing performance issues. Keeping an eye on these metrics can help pinpoint problems with extensions. |
| **Customization Analysis Report (CAR Report)** | The CAR report is an advanced best practice check tool. | You can run the CAR report from the command line in a development environment. The output is an Excel workbook with recommendations issues and warnings. | A clean CAR report is a requirement for the go-live readiness review prior to enabling production. |
| **Understand and avoid breaking changes** | A breaking change is a change that breaks all or some of the consumers of your code that already exist. | Breaking changes are, for example, changes to data model and extended data types, changes to access modifiers on classes and methods and many others. It's especially important in heavily extended solutions, such as if you're making a basis for a global rollout, if you're building an ISV solution, or if you have multiple developers sharing common custom APIs or constructs. But always take breaking changes into consideration. | That although the application is massive, we tend to only extend the same relatively small subset of elements. It isn't as unlikely that you may think that other developers use your components or code. |
| **Log extensibility requests early** | If you find a need for an extension point that is currently not available, log the request early. You can submit an extensibility request in Lifecycle Services. | Extensibility requests are logged to a backlog. Microsoft engineers prioritize all requests, and then work on them in priority order. Microsoft doesn't guarantee that all requests are met. Requests that are intrusive by nature aren't supported, as they prevent a seamless upgrade. | Extensibility requests are following the same cadence as the platform updates. |
| **Proper unit testing** | Sometimes developers put much effort into building the extension, but little effort into unit testing it before determining whether it's ready to deliver. | Developers are the first line of defense against bugs, performance issues and semantic issues that may exist in the specification. By going through the intended functionality from perspectives such as: <ul><li> Will this code scale with high volumes? </li><li> Does it do what I expect? </li><li> Can I do things I'm not supposed to? </li><li> Could the user accidentally do something unwanted? </li> <li> Does the requirement make sense or force me to break best practices or patterns? </li></ul> | It's a lot easier and more cost effective for the developer to find and fix a problem before it's checked in, built and deployed. |

Learn more in the [Reference links](#reference-links) section.  

## Additional components

It's important to note that the extended product architecture contains several other components. There are multiple avenues and tiers for approaching a requirement for extension. It depends on the specific area and nature of the requirement.

In addition to the components in Dynamics 365 Finance and Supply Chain Management, there are components for Commerce and WMS that require different technologies as well as developer toolsets and skill set. Examples include the Point of Sale (POS), the Commerce Scale Unit (CSU), the eCommerce components, the Warehousing mobile app, and the Finance and Operations mobile app.

That means separate requirements for extensions may have to be applied to different components. Slightly different approaches may also be needed, and the complexity and skill set required may vary. Before deciding to extend the component, developers and administrators must familiarize themselves with each of the specific SDKs, guidelines, application lifecycles, builds, and deployment methods and the skill set required.

## Reference links

- [Extensibility home page](/dynamics365/fin-ops-core/dev-itpro/extensibility/extensibility-home-page)

- [Application stack and server architecture](/dynamics365/fin-ops-core/dev-itpro/dev-tools/application-stack-server-architecture)

- [Microsoft Power Platform integration with Finance and Operations](/dynamics365/fin-ops-core/dev-itpro/power-platform/overview)

- [The Microsoft commercial marketplace](https://appsource.microsoft.com/)

- [Commerce for IT pros and developers](/dynamics365/commerce/dev-itpro/dev-retail-home-page)

- [Write extensible code](/dynamics365/fin-ops-core/dev-itpro/extensibility/writing-extensible-code)

- [Breaking changes](/dynamics365/fin-ops-core/dev-itpro/extensibility/breaking-changes)

- [Extensibility requests](/dynamics365/fin-ops-core/dev-itpro/extensibility/extensibility-requests)

- [Grid capabilities](/dynamics365/fin-ops-core/fin-ops/get-started/grid-capabilities)

<!-- Deprecated -   [Mobile app home page](/dynamics365/fin-ops-core/dev-itpro/mobile-apps/mobile-app-home-page) -->

- [Take traces by using Trace parser](/dynamics365/fin-ops-core/dev-itpro/perf-test/trace-trace-tutorial)

- [Testing and validations](/dynamics365/fin-ops-core/dev-itpro/perf-test/testing-validation)

## Next steps

- View the case study at [Extend your solution: Case study](extend-your-solution-case-study.md)  
- Return to the overview at [Extend your solution](extend-your-solution.md)  
- Learn about extending other Dynamics apps at [Extend customer engagement apps](extend-your-solution-guidance-product-ce.md)  
