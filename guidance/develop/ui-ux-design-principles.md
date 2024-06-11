---
title: Key UI/UX design principles
description: Explore the UI/UX design principles that shape the user interface and experience of Dynamics 365 apps, and how to use them in the design of your model-driven apps and canvas apps.
author: dereklh77
ms.author: riasif
ms.topic: conceptual
ms.date: 06/03/2024
---

# Key UI/UX design principles

UI/UX design is the process of creating a user interface and experience that meets the needs and goals of users. A good UI/UX design helps users complete tasks efficiently, effectively, and enjoyably.

Dynamics 365 apps follow a set of UI/UX design principles that guide their development. These principles are based on research, best practices, and user feedback. They help ensure that Dynamics 365 apps provide a consistent, intuitive, and engaging user experience across different devices, platforms, and scenarios. You can use these principles as a reference when you design your own apps with Power Apps. They can help you make design decisions that align with user expectations and enhance user satisfaction.

## Consistency

Consistency in UI/UX design is about maintaining uniformity in design elements and patterns throughout the user interface. It ensures that users can predict how different parts of the app behave based on their prior interactions with it. Themes and branding are key components of consistency in UI/UX design.

Learn more in:

- [Theming](/power-platform/guidance/creator-kit/theme)
- [Use theming components](/power-platform/guidance/coe/theming-components)

### Themes in model-driven apps

Themes are an excellent way to achieve visual consistency in model-driven apps. Themes allow you to customize the interface to align with your organization's branding and visuals.

We recommend that you build your model-driven apps using the [Modern UI](/power-apps/user/modern-fluent-design), which supports app theming. For now, modern themes support changing the header color only. Learn more in [Use modern themes](/power-apps/maker/model-driven-apps/modern-theme-overrides).

If you haven't switched to the new UI, then classic theming is an option for you. You can customize other aspects of the app using a classic theme. Learn more in [Use a theme to create a custom look for your app](/power-apps/maker/model-driven-apps/create-themes-organization-branding).

### Themes in canvas apps

In the context of canvas apps, a design scheme or theme is a collection of styles that define design properties of controls and components. The theme of a canvas app includes the following elements:

- **Colors**: A color palette defines which colors are used in the theme. The colors in the palette are organized into categories like primary, secondary, and tertiary. Make sure that the colors you choose are accessible by all users.

- **Fonts**: Select fonts and sizes for the text in the app that are readable on all devices your users might use the app on.

- **Controls**: Power Apps provides a rich set of classic controls and a new set of modern controls that are based on the [Microsoft Fluent 2 design system](https://fluent2.microsoft.design/).

- **Border thickness & padding**: Define the thickness of borders and the amount of padding around controls.

### Accessibility considerations

- **Contrast ratios**: Make sure that the color scheme you choose maintains adequate contrast ratios between text and background elements. Users with visual impairments rely on good contrast for readability.

- **Tooltip text**: In model-driven apps, provide a tooltip in the description of fields and controls to allow screen readers to accurately state the context.

- **AccessibleLabel**: In canvas apps, set the [`AccessibleLabel` property](/power-apps/maker/canvas-apps/controls/properties-accessibility) of controls for screen readers.

- **Alignment with brand guidelines**: When creating custom themes, adhere to your organization's brand guidelines. Make sure that the chosen colors align with your brand while meeting accessibility requirements.

- **User feedback**: Gather feedback from users, including users with disabilities, about the customized themes. Make sure that the themes don't compromise usability or accessibility and adjust as needed based on user input.

## Simplicity

Simplicity in design means keeping the interface clean, uncluttered, and straightforward. A simple design makes it easier for users to focus on their tasks without distractions. Streamline the interface by removing unnecessary elements, features, or fields. Prioritize essential information and actions to minimize complexity and ensure a user-friendly experience.

### Simplicity in model-driven apps and canvas apps

- **Reduce cognitive load.** A simple design helps reduce cognitive load for users. When a dashboard in model-driven apps is clean and uncluttered, it allows users to focus on essential information. Similarly, in canvas apps, a streamlined layout with fewer controls and elements makes it easier for users to navigate the app.

- **Streamline the interface.** To streamline custom table layouts, carefully select which fields to display and which fields can be placed in expandable sections or accessed through a secondary tab. This approach reduces cognitive load and keeps the form visually tidy. Eliminate unnecessary field duplication or redundant steps to streamline the user's journey.

- **Prioritize essential information.** Not all information or actions are of equal importance. Place essential information and actions prominently.

- **Prioritize a user-friendly experience.** The ultimate goal is to provide a user-friendly experience. Reports and charts should be uncluttered and easy to understand. Simplify the presentation of data and highlight key trends or metrics to provide actionable insights.

- **Simplify navigation.** Navigation in your model-driven apps and canvas apps should be simple. Group related modules together and provide a clear hierarchy between navigation flows. Users often remember navigation using the structure of menus or the sitemap. Simplicity helps them easily find the module or screen they need without being overwhelmed by an extensive list of menu options.

- **Make navigation intuitive.** Navigation should also follow the flow of the business process rather than forcing a business process to adapt to the user experience. Avoid transitions or delays that conflict with the next activity that users expect or that make them forget what they were doing.

- **Optimize for create and consume experiences.** Creating and consuming information are different ways of working. Make sure that the least information possible is displayed on screens for the current mode of working in the app. For example, create experiences should be optimized for data entry, while consume experiences should be optimized for the role of the user who's viewing the data. Update experiences should balance the needs of both reading and editing.

### Simplicity in canvas apps

- **Balance and align.** A visual hierarchy of elements and equal distribution of elements on either axis of a screen help draw users' attention to more important information. Use the size of components to help establish their importance and place in the UI hierarchy.

- **Indicate hierarchy with fonts.**: Use a consistent font in the app, and create a font hierarchy to help draw users' attention to the right information. Learn more in [Typography](https://fluent2.microsoft.design/typography).

- **Use consistent visual style and alignments on buttons.**: Create buttons once and assign their properties using global variables to ensure consistency. Don't confuse the user with misleading choices and be consistent with your alignment of buttons on screens. For instance, if you have a primary action button, place it in the same location on every screen.

- **Build responsively.** Responsive design refers to the ability of an app to automatically adjust to different screen sizes and orientations. The key focus is on maintaining user-friendly consistency. Adopting responsive design principles in canvas apps not only enhances the flexibility of the apps but also improves their user-friendliness. Learn more in [Building responsive canvas apps](/power-apps/maker/canvas-apps/build-responsive-apps).

## User-centricity

User-centric design is fundamental in creating a successful app. It prioritizes the needs, preferences, and experiences of business users, and then tailors the system to their specific requirements. By understanding user needs and behaviors, you can create interfaces that are intuitive, efficient, and aligned with user expectations.

A user-centric design approach for Power Apps offers several benefits. Improved adoption rates create a collaborative work environment. Enhanced productivity results from streamlined tasks. Higher user satisfaction contributes to a motivated workforce, and reduced training time accelerates the onboarding process for new users. These benefits collectively lead to a more efficient, effective, and user-friendly app.

### Understand user needs

User empathy and user research are foundational components of user-centric design, particularly when applied to model-driven and canvas apps.

User empathy involves putting yourself in the place of users to genuinely understand their challenges, pain points, and objectives. This empathetic approach ensures that design decisions are driven by a deep understanding of the user's perspective, fostering a more user-friendly and efficient application.

A key component of understanding user needs is educating users about the capabilities and limitations of Power Platform. Emphasize the importance of aligning user needs with the platform's features, rather than attempting to replicate designs from previous systems. This proactive approach can help mitigate confusion and ensure a smoother transition for users.

User research takes user-centric design a step further by conducting comprehensive investigations into user behaviors, preferences, and pain points. This research dives into the specifics of how users interact with the app, what features they rely on, and where they encounter difficulties.

By collecting user feedback and conducting usability tests, you gain valuable insights that guide the development of interfaces, workflows, and features that are tailored to meet user needs effectively. This user-focused approach ultimately leads to apps that aren't only user-friendly but also aligned with the specific requirements and expectations of their users, ensuring a positive and productive user experience.

Developing user personas should be an essential part of your strategy. Users personas are crafted based on extensive research findings and represent various user segments, each with their unique goals and challenges. They help you craft a more personalized user experience. Customized forms and views in model-driven apps and screens in canvas apps are created to present data and actions that are directly relevant to specific user groups. This approach ensures that users have quick and easy access to the information and functionality they need, enhancing their efficiency.

Workflow optimization through automation is another critical aspect of this approach. Automations and transparent integration of data from various systems using connectors, embedded apps, custom pages, or virtual entities can be used to streamline and refine processes based on user needs, improving overall efficiency.

Together, these strategies work harmoniously to create model-driven and canvas apps that aren't only user-friendly but also highly effective in addressing the specific requirements of diverse user groups.

## Efficiency

Efficiency in UI/UX design plays a crucial role in improving user productivity and optimizing users' interactions with your app. An efficient design aims to reduce friction and streamline the user experience, ultimately making it easier for users to accomplish their tasks.

Efficiency-driven UI/UX design offers several benefits to users and organizations:

- **Time savings**: Streamlined workflows and reduced steps lead to significant time savings for users, allowing them to focus on more value-added tasks and be more productive overall.

- **Reduced errors**: Fewer manual interactions and simplified processes reduce the likelihood of errors, improving data accuracy and the quality of records.

- **Enhanced user satisfaction**: Users appreciate systems that are easy and efficient to use. A positive user experience fosters satisfaction, boosts morale, and encourages higher system adoption rates.

- **Increased productivity**: Efficiency-driven design enables users to accomplish more in less time, translating into increased overall productivity for the organization.

Here are some key strategies to enhance the efficiency of your model-driven apps and canvas apps:

### Minimize steps

- **Task streamlining**: One of the core objectives of an efficient UI/UX design is to minimize the number of steps required to complete tasks. Users should be able to accomplish their goals with as few selections or interactions as possible. Reducing steps not only saves time but also reduces the chances of errors or frustration.

- **Common user workflows**: It's essential to identify and understand the most common user workflows based on the user's persona. These workflows often represent the core activities of users, such as data entry, lead conversion, or customer inquiries. Tailor the UI specifically for the user persona. In model-driven apps, use specific pages, forms, and views that are designed for specific security roles. In canvas apps, it's often more efficient to have separate apps for each persona.

### Optimize workflows

- **Workflow optimization**: After common user workflows are identified for each persona, the next step is to optimize them for efficiency. This step involves redesigning processes to eliminate bottlenecks, redundant steps, or unnecessary complexity.

- **Use of features**: Use features provided by Power Apps to enhance efficiency. Keyboard shortcuts can help users quickly navigate the app, fill out forms, or trigger actions. Automation can reduce manual data entry and repetitive tasks, saving users time and effort. [Copilot assistance](https://powerapps.microsoft.com/blog/introducing-copilot-assistance-for-filling-forms-in-model-driven-apps/) can provide intelligent suggestions, generate insights, and help with reducing time spent on repetitive tasks.

- **User feedback**: Collect user feedback and insights to continuously refine and optimize workflows. User feedback can provide valuable information on pain points and opportunities for further efficiency improvements.

- **Design for performance**: Designing with performance in mind ensures that user flows aren't interrupted by long waits for the application to react.

  - **Model-driven apps**: Learn more in [Scalability](#scalability).

  - **Canvas apps**: Learn more in [Overview of creating performant apps](/power-apps/maker/canvas-apps/create-performant-apps-overview).

- Avoid large data loads where possible and use the [`Concurrent()` function](/power-platform/power-fx/reference/function-concurrent).

- [Optimize data query patterns](/power-apps/maker/canvas-apps/optimized-query-data-patterns).

- We recommend that you avoid using Power Automate to populate collections because of the inherent performance overhead to invoke and run the flow. However, if you need to do so, then make sure that queries in the flow are filtered to return the minimum amount of data.

- Avoid using too many data connections, including collection variables, in your apps.

- Make sure to delegate filters of data sources wherever possible.

- Avoid control overload. The more objects and controls on a screen, the longer the screen takes to load. Use [modern controls](/power-apps/maker/canvas-apps/controls/modern-controls/modern-controls-reference) when possible, because they're designed to reduce complexity in canvas apps and target higher performance.

## Feedback and guidance

Providing feedback and guidance is essential to guide users through their interactions with your apps. Feedback informs users about the outcomes of their actions, while guidance assists them in making informed choices. By incorporating robust feedback and guidance mechanisms into your UI/UX design, you can enhance the user experience and empower users to navigate the system effectively.

Providing timely and clear feedback assures users that their actions are being acknowledged and processed by the system. For example, when users submit a form or initiate a process, a well-designed interface should offer immediate feedback, such as confirmation messages or progress indicators. This feedback reassures users that their input has been received and is being acted upon.

### Error handling

Effective feedback is equally crucial when users encounter errors or make mistakes. Instead of vague error messages, the app should provide specific guidance on what went wrong and how to correct it. Clear error messages and actionable recommendations empower users to correct their actions promptly, reducing frustration and enhancing the user experience.

- **Model-driven apps**: Make sure that input values are correct on all [controls](/power-apps/maker/data-platform/types-of-fields) and that [required fields](/power-apps/maker/data-platform/create-edit-field-solution-explorer#column-requirement-options) are appropriately set. If more complicated validation is required, use [business rules](/power-apps/maker/model-driven-apps/create-business-rules-recommendations-apply-logic-form) and [client-side scripting](/power-apps/developer/model-driven-apps/client-scripting) with [form notification](/power-apps/developer/model-driven-apps/clientapi/reference/formcontext-ui/setformnotification) to ensure consistency in how errors and notifications are shown to users.

- **Canvas apps**: Design error handling and validation into your app. [Formula-level error management](/power-platform/power-fx/reference/function-iferror) can help make sure that code is added to check for Patch function errors, Power Automate flow errors, and Submit Form errors. For unexpected errors, use the canvas app's `OnError` property to give a detailed description of the error to the user.

### Onboarding, training, and support

Feedback and guidance play a significant role in onboarding new users. The app should offer intuitive tooltips, walkthroughs, or guided tours to help users understand its features and functionalities. This proactive guidance not only accelerates the learning curve but also instills confidence in users as they navigate the system.

Users might have questions or require assistance while using the app. A well-designed interface should provide easily accessible help resources, such as knowledge base links, contextual help buttons, or chat support options. Easy availability of support reinforces the idea that users aren't alone and can seek assistance when needed.

We recommend using Copilot Studio to build custom chatbots and integrate them with your model-driven or canvas apps. Copilot studio is a low-code platform that lets you create intelligent chatbots for various user support scenarios. Some of the benefits of using Copilot Studio are:

- You can use generative AI to create natural and contextual conversations that can answer common questions, provide guidance, and resolve issues.

- You can customize your chatbots with your own data, logic, and branding, and integrate them with Microsoft products and services such as Dynamics 365, Power Platform, Teams, and Outlook.

- You can deploy your chatbots across multiple channels, such as websites, mobile apps, Facebook, and any channel supported by the Azure Bot Framework.

- You can manage and secure your chatbots with central administration tools, built-in security roles, and comprehensive analytics.

Learn more at [Microsoft Copilot Studio](https://www.microsoft.com/microsoft-copilot/microsoft-copilot-studio).

The classic approach would be to use [custom help panes and guided tasks](/power-apps/maker/data-platform/create-custom-help-pages) for model-driven apps or [custom help pages](/power-apps/maker/data-platform/create-custom-help-pages) for canvas apps.

### Continuous improvement

Integrate feedback mechanisms, such as user surveys or feedback forms, into your app to allow users to provide feedback on their experiences and suggest improvements. Collecting user feedback is invaluable for iterative design enhancements and demonstrates a commitment to ongoing improvement.

Understanding how users are interacting with your app can provide deep insights into how to improve user engagement. Use Application Insights to analyze system-generated logs and understand user interactions with your app. Before you can send system-generated logs from the app, you need to create an Application Insights resource.

- **Model-driven apps**: [Connect the environment to Application Insights](/power-platform/admin/set-up-export-application-insights) to log the events [for model-driven apps](/power-platform/admin/telemetry-events-model-driven-apps) and [Dataverse](/power-platform/admin/telemetry-events-dataverse). Add [custom telemetry](/power-apps/developer/data-platform/application-insights-ilogger) to enrich server-side plug-in monitoring.

- **Canvas apps**: [Connect the app to Application Insights](/power-apps/maker/canvas-apps/application-insights) to log events. Add [custom telemetry](/power-apps/maker/canvas-apps/application-insights#create-custom-trace-events) in the app using the [Trace()](/power-platform/power-fx/reference/function-trace) function.

As users browse the app, events are automatically logged to Application Insights, including usage details such as where the app is accessed from, which devices are used, and which browser is used.

After the data is collected, you can use the powerful analytics tools in Application Insights to diagnose issues and understand what users actually do with your apps. This information can help you drive better design decisions and improve the quality of your apps. Learn more in [Application Insights overview](/azure/azure-monitor/app/app-insights-overview).

## Scalability

Scalability in UI/UX design means designing the app to accommodate growth and change. Scalable design anticipates the dynamic nature of businesses. It considers that organizations evolve over time, necessitating modifications, additions, or expansions. A scalable interface is built with flexibility in mind, ensuring that it can accommodate new features, data volumes, or workflows without a complete overhaul or a significant drop in performance or usability.

- **Model-driven apps**: Learn more in [Design forms for performance in model-driven apps](/power-apps/maker/model-driven-apps/design-performant-forms).

- **Canvas apps**: Learn more in [Common canvas apps performance issues and resolutions](/power-apps/maker/canvas-apps/common-performance-issue-resolutions).

Scalability shouldn't compromise user-friendliness. The interface must maintain its intuitive nature as it grows. New features or functionalities should be seamlessly integrated without overwhelming users with unnecessary complexity.

A scalable design often leads to cost savings. Instead of having to invest in a complete system overhaul when growth occurs, organizations can make targeted enhancements and adjustments. This approach is not only cost-effective but also reduces downtime and disruption.

Scalability also relates to data management. The app should efficiently handle larger datasets, offer advanced data filtering options, and facilitate data archiving or purging to keep the app responsive and organized.

With the increasing use of various devices, including mobile and tablets, scalability also involves ensuring that the system remains accessible and functional across different screen sizes and platforms. A responsive design is essential to maintain usability on all the devices your app's users might rely on.

## Accessibility

Accessibility is the practice of designing interfaces to be usable by individuals with disabilities. It ensures that all users, regardless of their abilities, can effectively interact with and navigate the app. Accessibility is a critical consideration in UI/UX design, as it promotes inclusivity and ensures that all users can access and benefit from your app's features.

Accessibility is built into Power Platform. Microsoft recognizes the importance of accessibility and provides extensive documentation and resources to support developers in creating accessible experiences. Learn more in [Accessibility in Dynamics 365](/dynamics365/get-started/accessibility/).

- **Model-driven apps**: Learn more in [Shortcuts and accessibility in app designer and site map designer](/power-apps/maker/model-driven-apps/accessibility-app-designer-site-map-designer-my-apps-page).

- **Canvas apps**: Learn more in [Create accessible canvas apps](/power-apps/maker/canvas-apps/accessible-apps) and [Review a canvas app for accessibility in Power Apps](/power-apps/maker/canvas-apps/accessibility-checker).

Learn more:

- [Microsoft Accessibility](https://www.microsoft.com/accessibility/)
- [Web Content Accessibility Guidelines (WCAG) 2 requirements](https://www.w3.org/WAI/WCAG21/quickref/)

## Related resources

- [UI/UX design components for model-driven apps](ui-ux-component-details-model-driven-apps.md)  
- [UI/UX design components for canvas apps](ui-ux-component-details-canvas-apps.md)  
- [Tests and user feedback in UI/UX design](ui-ux-component-details-testing-feedback.md)  
- [Introduction to UI/UX design for customer engagement apps](introduction-customer-engagement-ui-ux-design-guide.md)  
