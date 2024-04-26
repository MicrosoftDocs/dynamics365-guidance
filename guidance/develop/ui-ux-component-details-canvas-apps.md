---
title: UI/UX component details for canvas apps
description: Learn about components that constitute the layout of canvas apps, including outlines of component purposes, design considerations, and best practices.
author: dereklh77
ms.author: riasif
ms.topic: article
ms.date: 04/12/2024
---

# UI/UX component details for canvas apps

In this article, we dive into the various components that constitute the layout of canvas apps and explore their purposes, design considerations, and best practices.

## Overview

One of the quickest and easiest ways to build a canvas app is to automatically generate an app from simply describing the app to existing UI designs and driving it from data that already exists:

- **Existing data**: This can be existing tables in Dataverse or uploaded from an excel file or using external data in SharePoint or SQL. Learn more with [Create a canvas app with data from Microsoft Dataverse](/power-apps/maker/canvas-apps/data-platform-create-app).

- **Existing template**: There's a large library of full-functional business app templates, which can be used as is or customized to fit requirements. Learn more with [Create a canvas app from a template](/power-apps/maker/canvas-apps/get-started-test-drive).

- **AI Copilot**: Describe what the application should, including the data behind and the AI that designs the app. Learn more with [AI Copilot overview](/power-apps/maker/canvas-apps/ai-overview).

- **Express design**: Using an Image or a Figma design to instantly transform the visual design into an app. Learn more with [Express design](/power-apps/maker/canvas-apps/express-design).

- **Page designs**: Choose from an existing set of initial page designs or a blank canvas.

There's no right or wrong decision when choosing a starting point for a canvas app as this will depend on several factors:

- The purpose of the app and the availability/type of data sources that the app uses.

- The level of customization and control that the maker needs over the UI/UX, and functionality required in the app.

- The amount of time and effort that the maker is willing to invest in the app development process.

- The existing knowledge and skills of the maker in UI/UX design and app development.

With Power Apps, makers can quickly create a usable version of the app that allows users to experience the actual working app early in the develop process, which means the best practice is to produce a minimal viable product and quick iterate new versions with more features. Learn more at [Introduction to Planning a Power Apps project](/power-apps/guidance/planning/introduction).

:::image type="content" source="media\ui-ux-component-details-2.svg" alt-text="Diagram showing the Agile V 2 development pipeline, showing the connection between Design, First M V P, Version 2, 3, 4, and 5." lightbox="media\ui-ux-component-details-2.svg":::

### Screens

A screen in a canvas app is the area where you can add your controls (like buttons, labels, etc.). Through navigation, you can also build a user experience to various features and data. When you add a new screen, there are various screen layouts and templates to choose from. Learn more at [Add a screen to a canvas app and navigate between screens](/power-apps/maker/canvas-apps/add-screen-context-variables).

Most users use canvas apps on devices with different form factors, which means it's necessary to create apps with a responsive layout. This means that the controls can respond to different devices or window sizes, making the user experience feel more natural. This means that the **Scale to fit** setting in the app should be turned off and the application should be designed for changing screen sizes and orientations. Learn more about building responsive applications at [Building responsive canvas apps](/power-apps/maker/canvas-apps/build-responsive-apps) and [Create responsive layouts in canvas apps](/power-apps/maker/canvas-apps/create-responsive-layout).

When considering the screens in canvas apps, it's best practice to:

- **Minimize the number of screens**: Keeping the number of screens to a minimum reduces the overall footprint of the app. This is especially important for users with older devices, or users in locales where there's a higher latency or reduced bandwidth. Be sure to delete any screens that aren't used in the app.

- **Consider splitting apps with multiple personas**: For example, having both admin and client screens in the same app won't only increase the app size and but also its complexity. Consider splitting these into individuals' apps as this will improve performance, allow multiple makers to work on the apps simultaneously, and reduce regression testing when making app changes.

- **Screen names**: These shouldn't only reflect the purpose of the screen in the app but should use plain language and include spaces. Don't use abbreviations as these are read aloud by screen readers for users who have vision accessibility needs. We recommend that they end with the word *Screen*, so the context is understood when the name is announced.

- **Hidden screens**: Hidden screens are a part of many apps because they provide a quick place for developers to capture important information without allowing users to change anything. They're hidden from your app's users but not from the makers. It's common to add hidden screens for documentation for makers or as a template to maintain consistency for look and branding for controls.

- **Maintain consistent navigation between screens**: The key to effective navigation in canvas apps is to ensure that it's intuitive, responsive, and consistent across all screens. This enhances the user experience and makes your app more efficient and user-friendly. Therefore, ensure apps have the same navigation on each screen, such as providing next and back buttons in the header or footer.

### Controls

Controls in Power Apps are essential for building interactive and user-friendly applications. They allow users to interact with the app and perform various actions, such as inputting data, navigating through the app, and triggering specific functions. As part of the continuous update and improvements a new set of modern controls are being released based on the Microsoft Fluent 2 design system, proving a more cohesive and visually appealing experience for end-users. We recommend that makers make use of newer controls when building the apps as they provide many benefits:

- **Improved accessibility and usability**: Modern controls are designed with a focus on accessibility and usability, making them highly functional and intuitive to use.

- **Performance**: Modern controls are built for performance, not only ensuring faster and more fluid app experiences for users but also quicker and simpler for makers to configure.

- **Modern theming system**: Modern controls include a new modern theming system that allows an app's look and feel to be modified from a central place.

- **Composite controls**: These controls combine multiple basic controls into one, providing more complex interactions out of the box that reduce the number of controls needed in an app.

At the time of writing, not all of the modern controls are generally available and transitioned over the coming year. Learn more about modern controls at [Recap of modern controls evolution in 2023 and a glimpse into 2024 innovations](https://powerapps.microsoft.com/blog/recap-of-modern-controls-evolution-in-2023-and-a-glimpse-into-2024-innovations/).

For a full list of all of the modern controls, see [Overview of modern controls and theming in canvas apps](/power-apps/maker/canvas-apps/controls/modern-controls/overview-modern-controls).

For a full list of all the existing controls, see [Controls and properties in canvas apps](/power-apps/maker/canvas-apps/reference-properties).

There are two more controls that can be added to enhance canvas Apps:

- **Chatbot control**: Allows a maker to embed a published Copilot Studio chatbot's into canvas apps. This can assist end-users with various requests from providing simple answers to common questions to resolving issues requiring complex conversations. Learn more at [Add Chatbot control to your canvas app](/power-apps/maker/canvas-apps/add-ai-chatbot).

- **Copilot control**: The Copilot control is a next-generation AI assistant that makers can add to their canvas apps for end-users. This AI-powered experience allows app users to get insights about the data in their apps through conversation in natural language. Learn more at [Add Copilot control for canvas app users](/power-apps/maker/canvas-apps/add-ai-copilot).

## Related resources

- [UI/UX component details for tests and user feedback](ui-ux-component-details-testing-feedback.md)  
- [UI/UX component details for model-driven apps](ui-ux-component-details-model-driven-apps.md)  
- [Key UI/UX design principles](ui-ux-design-principles.md)  
- [Introduction to UI/UX design for customer engagement apps](introduction-customer-engagement-ui-ux-design-guide.md)  

<!--

## Conclusion

In conclusion, this document has provided a comprehensive overview of UI/UX design principles specific to Power Apps here are the key takeaways:

1\. **Consistency**: Maintain uniformity in design elements, ensuring a cohesive and familiar user experience.

2\. **Simplicity**: Keep the interface clean and straightforward to enhance usability.

3\. **User-Centricity**: Prioritize user needs and preferences to create an interface aligned with user workflows.

4\. **Efficiency**: Streamline workflows and optimize data entry processes to improve productivity.

5\. **Accessibility**: Ensure the interface is accessible to users with diverse needs for inclusivity and compliance.

6\. **Feedback and Guidance**: Collect user feedback and provide context-aware guidance for continuous improvement.

7\. **Scalability**: Design with future growth and changes in mind to adapt to evolving business requirements.

8\. **Usability Testing**: Conduct usability tests and gather feedback to refine the user experience over time.

Remember that UI/UX design is an ongoing process, and the pursuit of excellence in user experience is a continuous journey. By applying these principles, seeking user input, and staying informed about the latest design trends and technologies, you can ensure that your interface remains user-centric and optimally efficient. -->

<!-- # References

For ongoing learning and adherence to design principles, consider the following resources:

Explore Microsoft's official learning platform for a wide range of tutorials and courses on Power Platform, Power Apps CE and UX design.

<https://learn.microsoft.com>

User Feedback Platforms: Implement feedback collection systems like Microsoft Forms (https://forms.microsoft.com/) or UserVoice https://www.uservoice.com/ to gather insights directly from users.

[App design best practices checklist (PowerApps) - Power Platform \| Microsoft Learn](https://learn.microsoft.com/en-us/power-platform/developer/appsource/appendix-app-design-best-practices-checklist)

Modern UI:

[Use modern themes - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/modern-theme-overrides)

[Modern, refreshed look for model-driven apps is generally available (GA) \| Microsoft Power Apps](https://powerapps.microsoft.com/en-us/blog/modern-refreshed-look-for-model-driven-apps-is-generally-available-ga/)

Controls and Theming:

[Modern theming - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-gb/power-apps/maker/canvas-apps/controls/modern-controls/modern-theming)

[Theming components - Power Platform \| Microsoft Learn](https://learn.microsoft.com/en-us/power-platform/guidance/coe/theming-components)

[Theming - Power Platform \| Microsoft Learn](https://learn.microsoft.com/en-us/power-platform/guidance/creator-kit/theme)

Responsive Design

[Add a screen to a canvas app and navigate between screens - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/add-screen-context-variables)

[Building responsive canvas apps - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-gb/power-apps/maker/canvas-apps/build-responsive-apps)

[Create responsive layouts in canvas apps - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-gb/power-apps/maker/canvas-apps/create-responsive-layout)

Controls

[Modern controls and properties in canvas apps - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-gb/power-apps/maker/canvas-apps/controls/modern-controls/modern-controls-reference)

[Controls and properties in canvas apps - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-gb/power-apps/maker/canvas-apps/reference-properties)

Accessibility

[Create accessible canvas apps - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/accessible-apps)

[Review a canvas app for accessibility in Power Apps - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/accessibility-checker)

[Dynamics 365 accessibility and ADA compliance - Dynamics 365 \| Microsoft Learn](https://learn.microsoft.com/en-us/dynamics365/get-started/accessibility/)

Coding Standards

[PowerApps Canvas App Coding Standards](https://powerapps.microsoft.com/en-us/blog/powerapps-canvas-app-coding-standards-and-guidelines/)

Error Handling

[Column data types in Microsoft Dataverse (contains video) - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-us/power-apps/maker/data-platform/types-of-fields)

[Create and edit columns for Microsoft Dataverse using Power Apps solution explorer - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-us/power-apps/maker/data-platform/create-edit-field-solution-explorer#column-requirement-options)

[Apply business logic using client scripting in model-driven apps using JavaScript - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-us/power-apps/developer/model-driven-apps/client-scripting)

[Error, IfError, IsError, and IsBlankOrError functions - Power Platform \| Microsoft Learn](https://learn.microsoft.com/en-us/power-platform/power-fx/reference/function-iferror)

User Support

[Create custom help pages - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-us/power-apps/maker/data-platform/create-custom-help-pages)

Application Insights

[Application Insights overview - Azure Monitor \| Microsoft Learn](https://learn.microsoft.com/en-us/azure/azure-monitor/app/app-insights-overview)

[Trace function - Power Platform \| Microsoft Learn](https://learn.microsoft.com/en-us/power-platform/power-fx/reference/function-trace) [Analyze system-generated logs using Application Insights - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/application-insights#create-custom-trace-events) [Write Telemetry to your Application Insights resource using ILogger (Microsoft Dataverse) - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-us/power-apps/developer/data-platform/application-insights-ilogger)

[Export data to Application Insights - Power Platform \| Microsoft Learn](https://learn.microsoft.com/en-us/power-platform/admin/set-up-export-application-insights)

[Analyze model-driven apps and Dataverse telemetry with Application Insights - Power Platform \| Microsoft Learn](https://learn.microsoft.com/en-us/power-platform/admin/analyze-telemetry)

Navigation Bar customization:

[Customize SiteMaps (Developer Guide for Dynamics 365 Customer Engagement) \| Microsoft Learn](https://learn.microsoft.com/en-us/dynamics365/customerengagement/on-premises/developer/customize-dev/customize-sitemaps?view=op-9-1) 

[Use keyboard shortcuts in Power Apps - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-us/power-apps/user/keyboard-shortcuts)

PowerBI dashboards integration

[Embed a Power BI report in a model-driven app main form - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/embed-powerbi-report-in-system-form)

[Create or edit a Power BI embedded system dashboard - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/create-edit-powerbi-embedded-page)

[Add or edit Power BI visualizations on your dashboard - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-us/power-apps/user/add-powerbi-dashboards)

Permissions

[Use record-based security to control access to records (Developer Guide for Dynamics 365 Customer Engagement) \| Microsoft Learn](https://learn.microsoft.com/en-us/dynamics365/customerengagement/on-premises/developer/security-dev/use-record-based-security-control-access-records?view=op-9-1)

[Field level security \| Microsoft Learn](https://learn.microsoft.com/en-us/dynamics365/customerengagement/on-premises/admin/field-level-security?view=op-9-1)

Performance

[Interact with HTTP and HTTPS resources asynchronously - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-us/power-apps/developer/model-driven-apps/best-practices/business-logic/interact-http-https-resources-asynchronously)

Component details

[Advanced find - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-us/power-apps/user/advanced-find)

[Use Advanced Find search in Dynamics 365 Customer Engagement (on-premises) \| Microsoft Learn](https://learn.microsoft.com/en-us/dynamics365/customerengagement/on-premises/basics/save-advanced-find-search?view=op-9-1)

[Customize the command bar - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/use-command-designer)

[Customize commands and the ribbon (model-driven apps) - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-us/power-apps/developer/model-driven-apps/customize-commands-ribbon)

[Ribbons available in model-driven apps - Power Apps \| Microsoft Learn](https://learn.microsoft.com/en-us/power-apps/developer/model-driven-apps/ribbons-available)

Designing business processes

Business process flow table metadata - Power Apps \| Microsoft Docs [https://docs.microsoft.com/powerapps/developer/common-data-service/business-process-flows-table-metadata](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/business-process-flows-table-metadata)

Create a branching business process flow - Power Apps \| Microsoft Docs [https://docs.microsoft.com/powerapps/developer/model-driven-apps/create-business-process-flows](https://docs.microsoft.com/en-us/powerapps/developer/model-driven-apps/create-business-process-flows)

Configure security roles for business process flows - Power Apps \| Microsoft Docs [https://docs.microsoft.com/powerapps/developer/model-driven-apps/configure-security-business-process-flows](https://docs.microsoft.com/en-us/powerapps/developer/model-driven-apps/configure-security-business-process-flows)
-->