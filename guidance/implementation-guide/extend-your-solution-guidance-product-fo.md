---
title: Extend Dynamics 365 finance and operations apps
description: Learn how to use the extensibility model, the development architecture, and the advanced tools for extending Dynamics 365 finance and operations apps.
author: abunduc-ms
ms.author: abunduc
ms.date: 01/24/2024
ms.topic: concept-article
ms.custom:
  - evergreen
  - ai-seo-date: 01/24/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Extend Dynamics 365 finance and operations apps

When you implement a solution that includes Dynamics 365, you might need to extend the default capabilities to meet your specific needs. This article focuses on some of the details for extending Dynamics 365 finance and operations apps, such as Dynamics 365 Finance, Supply Chain Management, and Commerce. For solutions with customer engagement apps, you can use more features of the Power Platform. [Learn more about extending customer engagement apps](extend-your-solution-guidance-product-ce.md).

## Overview

Dynamics 365 finance and operations apps have an extensibility model that lets you extend the built-in functionality to fit different requirements.

The extensibility model is a toolset that includes application lifecycle management (ALM) in Azure DevOps. Learn more about extensions and development in Dynamics 365 finance and operations apps:

- [Extensibility home page](/dynamics365/fin-ops-core/dev-itpro/extensibility/extensibility-home-page) in the finance and operations documentation
- [Introduction to developing with Dynamics 365 finance and operations apps](/training/paths/introduction-develop-finance-operations/) learning path

In this section, we'll first explore what you can do to improve functionality and the user interface (UI) [without extending the app](#personalization-and-no-code-options). Then we'll give a brief overview of [the extensibility model](#extending-the-app), and finally highlight some of [the tools and practices](#advanced-practices-and-tools) that professional developers can use when they extend the app.

## Examples of extensions that don't require changing app components

Let's look at some examples of what you can extend without changing the app components:

| | Extension example 1 | Extension example 2 | Extension example 3 |
| - | --- | --- | --- |
| **Requirement** | Create a custom workspace with tiles and lists from multiple forms and queries across the manufacturing module. | Add a table to store a list of food allergens. Add the allergen field to the sales line record so the user can indicate if a product contains a specific allergen. | Add code to automatically change the status of the new production order to **Started** when the user confirms a planned production order. |
| **Tools and components** | Use the personalization feature and *add to workspace* function in the UI to create the workspace and components you want. You don't need to change any code or app components. | Use Visual Studio to add the extended data types, the tables and fields, and the extensions to the **Sales line** table and the **Sales order** form. This change requires new and changed app components and must follow software development lifecycle (SDLC), build, and deployment guidelines. | Use Visual Studio to extend the X++ business logic, add appropriate event handlers, class, methods, and X++ code to catch the event when the planned order is confirmed. You can then run the correct code pattern to set the new production order to **Started** status. This change requires new and changed app components and X++ code, and must follow SDLC, build, and deployment guidelines. Consider scalability and performance when you confirm many planned orders using appropriate developer tools. |
| **Skills required** | You need user-level experience with navigation of the relevant module, navigation, and personalization. | You need entry-level professional developer experience in Dynamics 365 finance and operations apps. You also need familiarity with Visual Studio, building procedures, and best practices. | You need medium- to expert-level professional developer experience in Dynamics 365 finance and operations apps. You also need familiarity with Visual Studio, build procedure, best practices, and frameworks like SysOperations Framework, multithreading, and performance-checking tools and patterns. |

## Personalization and no-code options

Dynamics 365 finance and operations apps offer a rich extensibility model with minimal impact on future updates. However, we recommend that you don't extend the default experiences through code to lower risk, maintenance, and project complexity.

Before you decide to extend an app with code, check if you can meet your needs with personalization or configuration. Dynamics 365 finance and operations apps have many options for personalizing the UI, creating user-specific experiences, and automating processes without any programming.

As the following table shows, you have many alternatives to extending Dynamics 365 with code. The table doesn't list all of them. [Learn about more low-code and no-code options when you integrate with other solutions](integrate-other-solutions.md). The decision to extend depends on user efficiency and value for your customers.

| Tool | What is it? | Description | Characteristics |
| --- | --- | --- | --- |
| **Restricted personalization** | The app remembers the last settings for sorting, column width, and critical values in queries and dialogs. | Personalization isn't really an extension, but users can save selections in dialogs, expand relevant fast tables, and adjust the column width to show more columns on a form. | Users can share personalizations, and admins can manage personalization from the **Personalization** page. |
| **Personalization of forms/UI** | Personalization bar in forms and workspaces. | With personalization, users or admins can add or hide fields or sections, change labels, change the order of columns, and edit the tab order for skipping fields. | Personalizations can be shared by users or managed centrally by an admin from the **Personalization** page. |
| **Saved views** | Saved views combine personalization of a form with filtering and sorting of the form's data source. | A saved view is a powerful tool to quickly switch between customized views of columns. A saved view can also capture different filters and sorting on the same form, depending on the specific task. | Users can share saved views. Admins can manage them centrally from the **Personalization** page. You might need to turn on the **Saved views** feature. |
| **Custom workspaces** | Users can use personalization and the "add to workspace" button to add tiles, views, or links to an existing or custom workspace. | This function lets users tailor their experience to their needs. Workspaces provide quick information about the most important measures, actions, and links to other pages. | Users can share custom and personalized workspaces, and admins can manage workspaces centrally from the **Personalization** page. |
| **Custom fields** | Users with certain security roles can add up to 20 custom fields to tables. | Dynamics 365 finance and operations apps have many features that apply across a wide range of industries. Some organizations need more fields in certain tables, and this feature lets users create them. These fields are specific to the environment where you create them. You can't access them with developer tools. | Users can share custom fields and the personalized forms that show the fields. Admins can manage custom fields centrally from the **Personalization** page. **Caution**: Deleting a custom field is irreversible and results in losing the data in the custom column. |
| **Grid capabilities** | The grids on forms have functions that can avoid the need for an extension. | The grid offers these functions: <ul><li> Calculate totals for columns in the grid footer </li><li> Paste from Excel </li><li> Calculate math expressions </li><li> Group tabular data in one or more levels in expandable groups </li><li> Freeze panes so that important information doesn't scroll out of view when you scroll horizontally </li></ul> | Admins can turn on the New Grid Control feature from feature management. |
| **Embedded canvas apps** | You can add a canvas app to a form or workspace as embedded in the UI or as a menu item that can open the app from the Power Apps menu. | By embedding a canvas app, you can use low-code/no-code options to interact with data in Dataverse directly from Dynamics 365 finance and operations apps. **Important**: If the app needs to interact with Dynamics 365 finance and operations apps data, you must set up integration to Dataverse and make sure the app supports the required actions. | Learn more about [integrating with other solutions](integrate-other-solutions.md). |
| **Excel integration** | You can extract or edit data on most forms in the app by selecting the Office icon. | The Excel integration lets you do things with data that you can't do from the UI. Besides exporting to and opening in Excel, you can create workbooks and templates for specific purposes. Excel has many features for presentation and data manipulation for large datasets. | With great power comes great responsibility. It's easy to change a whole column of data and publish it to the app, but it's also easy to make a mistake. |

## Extending the app

In this section, we'll introduce the extensibility model at a high level and talk about the required skill set and practices for extending. We'll also highlight some of the tools and techniques that we recommend you use to ensure a clean, high-performing, and future-proof solution.

The following table shows an overview of the components, the considerations for extensions, and their characteristics.

| Component | Editor | Considerations | Don't |
| --- | --- | --- | --- |
| **User interface** | Graphical editor in Visual Studio with preview. | Forms must follow patterns. The editor in Visual Studio has a rich modeler that helps you apply the right structure to the screens. This ensures performance when loading the form, adaptability across different resolutions and screen sizes, and consistency across the UI. | Deviate from the predefined patterns and create monster all-in-one forms&mdash;often the result of trying to copy a legacy system experience. |
| **Data model and queries** | Metadata editor in Visual Studio for tables, fields, extended data types, enums queries, and views. | Follow best practices and frameworks. Apply indexes and define delete actions. Normalize. Use effective date framework when applicable. Keep performance in mind. Use field lists when performance is a risk. | Create redundancy or copy poor modeling from legacy apps. |
| **Business logic** | X++ Editor in Visual Studio. | Adjust compiler settings to alert about best practices, and code with the goal of zero deviations. Use code patterns and frameworks. Be a good citizen developer. Write clean, easily readable code. Run the CAR report and use `compatibility checker.Unit` to test your code. | Ignore best practices, write long methods, or over comment your code. |
| **Reporting** | SSRS report editor in Visual Studio. | SSRS reports are good for certain precision designs and tabular lists. [Learn more about business intelligence, reporting, and analytics](business-intelligence-reporting-analytics-overview.md). | Use the SSRS report option if there's a better way. |
| **Data entities** | Metadata editor in Visual Studio. | The built-in data entities are general-purpose tables that support a wide variety of features around a business entity. In scenarios where you need a high-volume, low-latency interface, we recommend that you build custom data entities with specific features to support high-volume interfaces in your implementation. | Create data source proliferation. [Learn more about integrating with other solutions](integrate-other-solutions.md). |

## Development architecture

The development environment architecture includes the software development kit (SDK), which consists of Visual Studio development tools and other components. Source control through Azure DevOps allows multiple developers to work on the same project, with each developer using a separate development environment. Deployable packages are compiled and packaged in a build environment or a build service and uploaded to Dynamics Lifecycle Services for deployment to nonproduction environments. Deployment to the production environment happens after proper testing in the UAT environment and users and stakeholders have signed off as described in the SDLC.

:::image type="content" source="media/extend_solution_dev_environment_architecture.png" alt-text="Diagram showing the development environment architecture for Dynamics 365 finance and operations apps." lightbox="media/extend_solution_dev_environment_architecture.png":::

[Learn more about aApplication lifecycle management](application-lifecycle-management.md).

## Cross-app integration

Cross-app integration options include dual-write, virtual tables, and business and data events. These options let developers use all the capabilities of Dataverse and Microsoft Power Platform to make extensions. The Dataverse components are easy to install and configure, and the extension itself can often be done with low-code/no-code options. For IT professionals, the integration options allow for a single workspace, Visual Studio, and familiar languages like C\# to develop extensions.

With the connection between Dynamics 365 and Dataverse, you can access Power Platform and use low-code/no-code developer models on Dynamics 365 data. Examples include embedded Power Apps, Power BI reports or dashboards, standalone apps or portals, and integration with other Dynamics 365 apps, without making changes through extensions to the finance and operations app and data layer.

For example, suppose you need a lightweight product catalog in Dynamics 365 Supply Chain Management with high-quality images in a form, or the ability to take pictures for such a catalog with a phone app. You could make these extensions by integrating Dataverse through virtual tables and then embedding a canvas app in the Dynamics 365 UI to show the catalog and another app to snap the picture and save it to the catalog.

[Learn more about integrating with Dataverse](integrate-other-solutions.md).

## Advanced practices and tools

As we mentioned earlier, it's always good advice to be a good citizen developer. In Dynamics 365 finance and operations apps, you can do that by understanding, learning, and using the tools and best practices shown in the following table.

| Tool | What is it? | Description | Characteristics |
| --- | --- | --- | --- |
| **Best practice check** | Best practice checks for X++ and app components are built into Visual Studio. They can be errors, warnings, or informational. | You should aim for zero deviations. The best practices help you ensure an updatable, performing, and user-friendly solution. | You can prevent developers from checking in code with best practice deviations. |
| **Compatibility report** | The compatibility checker tool can detect metadata breaking changes against a specified baseline release or update. | The compatibility checker tool is available as one of the dev tools. You can use it to make sure that your solutions are backward-compatible with earlier releases before you install or push updates. | The tool can't detect all breaking changes. [Learn more about the compatibility checker tool](/dynamics365/fin-ops-core/dev-itpro/extensibility/compatibility-checker-tool). |
| **Traces and trace parser** | Users can take a trace of runtime execution directly from the UI that the trace parser can read. | You can use the trace parser to analyze performance in your deployment. The trace parser can find and diagnose various types of errors. You can also use it to visualize execution of X++ methods and the execution call tree. | You can find the trace parser tool in the PerfSDK folder in your development environments. |
| **Performance timer** | Performance timer is a tool in the web client that can help you determine why your system's performance might be slow. | To open Performance timer, open your web page with the added parameter `debug=develop`. You can see counters for client time, server time, and the total time. You can also see a set of performance counters, a list of expensive server calls, how many SQL queries were triggered by this individual call, and which SQL query was the most expensive. | The tool itself has a performance impact. |
| **Lifecycle Services Logs** | Under Environment Monitoring in Lifecycle Services is a comprehensive collection of tools and information that you can use to analyze and diagnose your cloud environment. | The logs provide information such as: <ul> <li> Activity Monitoring: A visualization of the activity in the environment for a given timeline in terms of user load, interaction, and activity. </li><li> Information about slow queries, deadlocks, and similar problems.</li></ul> | The tools under Environment Monitoring are effective at diagnosing potential or growing performance issues. Monitoring these metrics can help you identify problems with extensions. |
| **Customization Analysis Report (CAR report)** | The CAR report is an advanced best practice check tool. | You can run the CAR report from the command line in a development environment. The output is an Excel workbook with recommendations, issues, and warnings. | A clean CAR report is a requirement for the go-live readiness review before deploying to production. |
| **Understand and avoid breaking changes** | A breaking change is a change that breaks all or some of the consumers of your code that already exist. | Breaking changes are changes such as data model and extended data types and access modifiers on classes and methods. They're especially important in heavily extended solutions, such as if you're making a basis for a global rollout, if you're building an vertical or horizontal solution, or if you have multiple developers sharing common custom APIs or constructs. But always consider breaking changes. | Don't assume that other developers don't use your components or code. Although the app is massive, we tend to only extend the same relatively small subset of elements. |
| **Log extensibility requests early** | If you need an extension point that isn't available, log the request early. You can submit an extensibility request in Lifecycle Services. | Extensibility requests are added to a backlog. Microsoft engineers prioritize all requests and work on them in priority order. Microsoft doesn't guarantee that all requests are met. Requests that are intrusive by nature aren't supported, because they prevent a seamless upgrade. | Extensibility requests follow the same cadence as the platform updates. |
| **Proper unit testing** | Sometimes developers put a lot of effort into building the extension, but little effort into unit testing it before deciding whether it's ready to deliver. | Developers are the first line of defense against bugs, performance issues, and semantic issues that might exist in the specification. Test the intended functionality from perspectives such as: <ul><li> Will this code scale with high volumes? </li><li> Does it do what I expect? </li><li> Can I do things I'm not supposed to? </li><li> Could the user accidentally do something unwanted? </li> <li> Does the requirement make sense or force me to break best practices or patterns? </li></ul> | It's easier and more cost-effective for the developer to find and fix a problem before checking in, building, and deploying it. |

## More components

The extended product architecture has several other components. You can approach a requirement for extension in multiple ways and at multiple levels, depending on the area and nature of the requirement.

Besides the components in Dynamics 365 Finance and Supply Chain Management, Commerce and Warehouse Management have components that require different technologies and developer toolsets and skills. Examples include the Point of Sale, the Commerce Scale Unit, the e-commerce components, and the Warehouse Management mobile app. That means different requirements for extensions might have to apply to different components. You might also need slightly different approaches, and the complexity and skill set required might vary.

Before deciding to extend a component, developers and administrators must familiarize themselves with each of the specific SDKs, guidelines, application lifecycles, builds, and deployment methods and the skill set required.

## Next steps

- Learn more about the specific considerations and best practices for [extending customer engagement apps](extend-your-solution-guidance-product-ce.md)
- Read the [case study](extend-your-solution-case-study.md) of how a company extended its Dynamics 365 app to improve its customer service
- Use the Success by Design [checklist](extend-your-solution-checklist.md) to plan and implement your extensions effectively

### See also

- [Extensibility home page](/dynamics365/fin-ops-core/dev-itpro/extensibility/extensibility-home-page)
- [Application stack and server architecture](/dynamics365/fin-ops-core/dev-itpro/dev-tools/application-stack-server-architecture)
- [Microsoft Power Platform integration with Finance and Operations](/dynamics365/fin-ops-core/dev-itpro/power-platform/overview)
- [The Microsoft commercial marketplace](https://appsource.microsoft.com/)
- [Commerce for IT pros and developers](/dynamics365/commerce/dev-itpro/dev-retail-home-page)
- [Write extensible code](/dynamics365/fin-ops-core/dev-itpro/extensibility/writing-extensible-code)
- [Breaking changes](/dynamics365/fin-ops-core/dev-itpro/extensibility/breaking-changes)
- [Extensibility requests](/dynamics365/fin-ops-core/dev-itpro/extensibility/extensibility-requests)
- [Grid capabilities](/dynamics365/fin-ops-core/fin-ops/get-started/grid-capabilities)
- [Take traces by using Trace parser](/dynamics365/fin-ops-core/dev-itpro/perf-test/trace-trace-tutorial)
- [Testing and validations](/dynamics365/fin-ops-core/dev-itpro/perf-test/testing-validation)
