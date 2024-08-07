---
title: UI/UX design components for Power Apps canvas apps
description: Discover how to use screens, controls, and other components to create user-friendly and responsive layouts for your Power Apps canvas apps.
author: dereklh77
ms.author: riasif
ms.topic: conceptual
ms.date: 06/03/2024
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
  - ai-seo-date: 05/29/2024
ai-usage: ai-assisted
---

# UI/UX design components for Power Apps canvas apps

This article discusses the components that you can use to design the layout of your canvas apps in Power Apps. You'll learn about their purposes, design considerations, and best practices.

You can build a canvas app in Power Apps quickly and easily from one of these options:

- **Existing data.** Use tables in Dataverse, upload data from an Excel file, or use external data in SharePoint or SQL. Learn more in [Create a canvas app with data from Microsoft Dataverse](/power-apps/maker/canvas-apps/data-platform-create-app).

- **A template.** Use a ready-made business app template or customize it to fit your requirements. Learn more in [Create a canvas app from a template](/power-apps/maker/canvas-apps/get-started-test-drive).

- **Copilot.** Describe what you want your app to do and the data that it needs, and the AI designs the app. Learn more in [Copilot in Power Apps overview](/power-apps/maker/canvas-apps/ai-overview).

- **Express design.** Transform an image or a Figma design into an app. Learn more in [Express design](/power-apps/maker/canvas-apps/express-design).

- **Page designs.** Choose from a set of initial page designs or start with a blank canvas.

The best option for you depends on several factors:

- The purpose of your app and the type and availability of data sources that your app uses.

- The level of customization and control that you need over the UI/UX and the functionality of your app.

- The amount of time and effort that you're willing to invest in the app development process.

- Your knowledge and skills in UI/UX design and app development.

With Power Apps, you can quickly create a working version of your app that lets users experience the actual app early in the development process. The best practice is to produce a minimum viable product and then iterate new versions with more features. Learn more in [Planning a Power Apps project](/power-apps/guidance/planning/introduction).

## Screens

A screen in a canvas app is the area where you add [controls](#controls) and navigation elements to create a user experience. When you add a new screen, you can choose from various screen layouts and templates. Learn more in [Add a screen](/power-apps/maker/canvas-apps/add-screen-context-variables).

Most users use canvas apps on devices with different sizes and shapes, so you need to create apps with a responsive layout. This means that the controls can adjust to different devices or window sizes, making the user experience more natural. To design a responsive layout, you need to turn off the **Scale to fit** setting in your app and design your app for changing screen sizes and orientations. Learn more in [Building responsive canvas apps](/power-apps/maker/canvas-apps/build-responsive-apps) and [Create responsive layouts in canvas apps](/power-apps/maker/canvas-apps/create-responsive-layout).

When you design the screens in your canvas apps, follow these best practices:

- **Minimize the number of screens.** Keeping the number of screens low reduces the overall size of your app. This is especially important for users with older devices or users in areas where there's high latency or low bandwidth. Be sure to delete any screens that you don't use in your app.

- **Consider splitting apps with multiple personas.** For example, having both admin and client screens in the same app not only increases the app's size but also its complexity. Consider splitting them into separate apps to improve performance, allow multiple makers to work on the apps at the same time, and reduce testing when you make changes to your apps.

- **Give screens descriptive names.** Your screen names should reflect the purpose of the screen in your app and use plain language and spaces. Don't use abbreviations. Screen names are read aloud by screen readers for users who have vision accessibility needs. We recommend that screen names end with the word *Screen*, so the context is clear when the name is announced.

- **Use hidden screens when needed.** Hidden screens are part of many apps because they provide a quick place for makers to capture important information without letting users change anything. They're hidden from your app's users but not from its makers. It's common to add hidden screens for documentation for makers or as a template to maintain consistency for the look and branding of your controls.

- **Maintain consistent navigation between screens.** The key to effective navigation in canvas apps is to make sure that it's intuitive, responsive, and consistent across all screens. Consistent, intuitive navigation enhances the user experience and makes your app more efficient and user-friendly. Make sure that your app has the same navigation on each screen, such as next and back buttons in the header or footer.

## Controls

Controls in Power Apps are essential for building interactive and user-friendly apps. They let users interact with your app and perform various actions, such as entering data, navigating through your app, and triggering specific functions.

As part of Microsoft's commitment to continuous improvement, we're releasing a new set of modern controls that are based on the Microsoft Fluent 2 design system. The new controls provide a more cohesive and visually appealing experience for users. We recommend that you use the newer controls when you build your apps because they provide many benefits:

- **Improved accessibility and usability**: Modern controls are designed with a focus on accessibility and usability, making them highly functional and intuitive to use.

- **Performance**: Modern controls are built for performance, ensuring faster and smoother app experiences for users and quicker and simpler configuration for makers.

- **Modern theming system**: Modern controls include a new modern theming system that lets you modify your app's look and feel from a central place.

- **Composite controls**: Some of the new controls combine multiple basic controls into one, providing more complex interactions out of the box that reduce the number of controls needed in your app.

At the time of writing, some of the modern controls are still rolling out. Learn more in [Recap of modern controls evolution in 2023 and a glimpse into 2024 innovations](https://powerapps.microsoft.com/blog/recap-of-modern-controls-evolution-in-2023-and-a-glimpse-into-2024-innovations/).

View the full list of modern controls in [Modern controls and properties in canvas apps](/power-apps/maker/canvas-apps/controls/modern-controls/modern-controls-reference).

For a full list of all the existing controls, see [Controls and properties in canvas apps](/power-apps/maker/canvas-apps/reference-properties).

There are two more controls that you can add to enhance your canvas apps:

- **Chatbot control**: The Chatbot control lets you embed a published Copilot Studio chatbot into your canvas apps. The chatbot can help users with various requests, from providing simple answers to common questions to resolving issues that require complex conversations. Learn more in [Add Chatbot control to your canvas app](/power-apps/maker/canvas-apps/add-ai-chatbot).

- **Copilot control**: The Copilot control is a next-generation AI assistant that you can add to your canvas apps. It's an AI-powered experience that lets app users get insights about the data in the apps through conversation in natural language. Learn more in [Add Copilot control for canvas app users](/power-apps/maker/canvas-apps/add-ai-copilot).

## Related information

- [UI/UX design components for model-driven apps](ui-ux-component-details-model-driven-apps.md)
- [UI/UX design components for tests and user feedback](ui-ux-component-details-testing-feedback.md)
- [Key UI/UX design principles](ui-ux-design-principles.md)
- [Introduction to UI/UX design for customer engagement apps](introduction-customer-engagement-ui-ux-design-guide.md)
