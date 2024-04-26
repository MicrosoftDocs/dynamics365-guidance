---
title: Key UI/UX design principles
description: Learn about UI/UX design principles, including overviews on various principles including consistency, simplicity, user-centricity, and efficiency.
author: dereklh77
ms.author: riasif
ms.topic: article
ms.date: 04/12/2024
---

# Key UI/UX design principles

In Power Apps, successful UX/UI design relies on key principles that impact aesthetics, functionality, and usability. The article discusses consistency, simplicity, user-centricity, efficiency, accessibility, and feedback's role in enhancing the user experience. We also focus on scalability and design for future growth.

By the end of this article, you'll understand these principles and learn how to apply them effectively for a user-friendly and productive interface. Let's explore these UI/UX design principles to enhance your system.

## Consistency

Consistency in UI/UX design is about maintaining uniformity in design elements and patterns throughout the user interface. It ensures that users can predict how different parts of the application behave based on their prior interactions. Let's start by looking at building themes in your application.

### Power Apps themes

#### Model-driven apps

The recommended way to move forward is to use Modern UI. Once you make the switch, you can use the new theming capability. At the time of publishing this article, the new theme only supports updating the header color; however, more capabilities are now delivered as part of the 2024 Wave 1 release. Learn more about how to override header color using modern themes at [Use modern themes - Power Apps](/power-apps/maker/model-driven-apps/modern-theme-overrides). Learn more about modern UI at [Modern, refreshed look for model-driven apps is generally available](https://powerapps.microsoft.com/blog/modern-refreshed-look-for-model-driven-apps-is-generally-available-ga/).

If you didn't yet switch to [New UI](/power-apps/user/modern-fluent-design), then classic theming is an option for you. You can customize the various aspects of the application via classic theme. Learn more at [Change the color scheme or add a logo to match your brand](/power-apps/maker/model-driven-apps/create-themes-organization-branding).

Themes are an excellent way to achieve visual consistency in model-driven apps. It allows organizations to customize the interface to align with their branding and visuals. However, it's crucial to consider accessibility principles alongside consistency. For example, suppose your company's primary color is blue. The header primary color can be matched with your brand's blue hue consistently across all modules, making the interface instantly recognizable as part of your brand. If

#### Canvas apps

In the context of canvas apps, a design scheme, often referred to as a theme, is a collection of styles that define multiple design properties for controls and components such as colors, fonts, and borders.

The theme of a canvas app includes the following elements:

- **Colors**: A color palette defines which colors are used in the theme. The colors in the palette are organized into categories like primary, secondary, tertiary colors and should be accessible by all user groups.

- **Fonts uniformity**: Selecting appropriate fonts and sizes for the text in the canvas app ensures it's consistently applied through the app and is readable in all the intended devices

- **Control styles**: This is determined by the controls that are being used in the canvas app. There is a rich set of existing controls and a new set of modern controls based on [Microsoft Fluent 2 design system](https://fluent2.microsoft.design/).

- **Border thickness & padding**: Ensure consistent layout across all components in the canvas app

### Accessibility considerations

- **Contrast ratios**: Ensure that the chosen color scheme maintains adequate contrast ratios between text and background elements. This is vital for users with visual impairments who rely on good contrast for readability.

- **Tooltip text**: Provide a tooltip on individual fields where necessary in model-driven Apps to ensure there's an accurate description of the field. This can help screen readers to accurately state the context to visually impaired users.

For example, on the Account field, you can add the tooltip text in the description field.

- **Accessible label for canvas apps**: Label is intended for screen readers and should be set appropriately on controls within the app [Accessibility properties for Power Apps](/power-apps/maker/canvas-apps/controls/properties-accessibility)

### Best practices

- **Alignment with brand guidelines**: When creating custom themes, adhere to your organization's brand guidelines. Ensure that the chosen colors align with your brand while considering accessibility requirements.

- [Theming - Power Platform](/power-platform/guidance/creator-kit/theme)

- [Theming components - Power Platform](/power-platform/guidance/coe/theming-components)

### User feedback

Gather feedback from users, including those with disabilities, about the customized themes. Ensure that the themes don't compromise usability or accessibility and adjust as needed based on user input.

## Simplicity

Simplicity in design means keeping the interface clean, uncluttered, and straightforward.

*"Millers Law (George Miller, Princeton, Capacity for Processing Information): ​Humans can process 7+/- 2 chunks of information at a time."*

A simple design makes it easier for users to focus on their tasks without distractions. Streamline the interface by removing unnecessary elements, features, or fields. Prioritize essential information and actions to minimize complexity and ensure a user-friendly experience.

### Model-driven & canvas apps

- **Reduce cognitive load**: A simple design helps reduce cognitive load for users. When a dashboard in model-driven apps is clean and uncluttered, it allows users to focus on essential information. For instance, displaying key metrics and recent activities prominently while removing unnecessary widgets ensures that users can quickly get an overview without distractions.

- **Streamlining the interface**: To achieve simplicity, streamline custom table layouts by carefully selecting which fields to display. In a Customer Management System, primary contact information is readily visible, while less frequently used fields can be placed in expandable sections or accessed through a secondary tab. This approach reduces cognitive load and keeps the form visually tidy.

- **Prioritizing essential information**: Not all information or actions are of equal importance. Prioritize essential information and actions prominently. For example, when designing process flows, ensure that the steps and actions are clear and straightforward. Eliminate unnecessary field duplication or redundant steps to streamline the user's journey.

- **User-friendly experience**: The ultimate goal is to provide a user-friendly experience. Reports and charts within Power Apps should also adhere to simplicity principles. A cluttered chart with too many data points or an overcrowded report can hinder understanding. Simplify the data presentation and highlight key trends or metrics to provide actionable insights.

- **Navigation**: Navigation in Power Apps should follow simplicity principles. Group related modules together and provide a clear hierarchy between navigation flows. Users often remember navigation through the application through the structure of menus or sitemap in the app so simplicity helps the user easily find the module/screen they need without being overwhelmed by an extensive menu list.

- **Optimize for create and consume experiences**: Creating or consuming information is a different model of working for the user. Ensure minimal information is displayed on screens for the current mode of working in the application.

:::image type="content" source="media\ui-ux-design-principles-1.svg" alt-text="Diagram showing arrows connecting the create, compare, and update sections." lightbox="media\ui-ux-design-principles-1.svg":::

**Intuitive navigation flow**: Allow for flow through the application by designing the screen navigation to follow the flow of the business process rather than forcing a business process onto the user experience of the application. Avoid transitions or delays that conflict with the next activity a user expects when they're expected to mentally transition to the next action in a business flow a transition in the UI is a natural reflection of that. However, if a user wants to just keep doing the same task, a UI transition or a longer delay, for example in getting data, can also make them lose focus or forget what they were doing which will make the user less efficient and less happy with the application.

### Canvas apps

- **Balance and alignment**: By using a visual hierarchy of elements and equal distribution of elements on either axis of a screen helps draw users attention to more important information. This can be further enhanced by varying the scale, by changing their size, of components and further establishing an importance and hierarchy in the UI.

- **Fonts**: Keep a consistent font in the application and create a Font Hierarchy to help draw users' attention to the right information within a screen. You can read more about Fluent 2 typography here. [Typography - Fluent 2 Design System (microsoft.design)](https://fluent2.microsoft.design/typography)

:::image type="content" source="media\ui-ux-design-principles-2.svg" alt-text="Diagram showing two versions of Heading, Subheading, and Body text with the left column being incorrect and the right column being correct." lightbox="media\ui-ux-design-principles-2.svg":::

- **Buttons and alignment**: Create the buttons once and assign their properties using Global Variables (helps ensure consistency).

:::image type="content" source="media\ui-ux-design-principles-3.svg" alt-text="Diagram showing a green Primary button, a white Secondary button, and a gray Disabled button." lightbox="media\ui-ux-design-principles-3.svg":::

Don't confuse the user with misleading choices and be consistent with your alignment of buttons on screens.

:::image type="content" source="media\ui-ux-design-principles-4.svg" alt-text="Diagram showing a Cancel your changes prompt with the Sure, No, and Cancel options with an X below. There's a second column with a Would you like to cancel your changes prompt with Yes and No options, with a checkmark below." lightbox="media\ui-ux-design-principles-4.svg":::

- **Build responsively**: Responsive Design in canvas apps refers to the ability of an app to automatically adjust to different screen sizes and form factors to use the available screen space efficiently. It ensures that the app optimally utilizes the available screen space, irrespective of the device used to access it. The key focus is on maintaining user-friendly consistency. Adopting these responsive design principles in canvas apps not only enhances the flexibility of the apps but also improves their user-friendliness, benefiting all users.

Responsive apps can be created quickly using [AI Copilot](/power-apps/maker/canvas-apps/ai-overview) or from existing [templates](/power-apps/maker/canvas-apps/get-started-test-drive) or [data](/power-apps/maker/canvas-apps/get-started-create-from-data). The app created is already responsive and conforms to large and small form factors. Also when creating a new app (in preview at time of writing) and adding a new screen to the application there's a choice of various [responsive screen layout templates](/power-platform/release-plan/2023wave2/power-apps/modern-screen-templates-canvas-designers), which adapt to size of the devices screen by default and [auto-layout container controls](/power-apps/maker/canvas-apps/build-responsive-apps#auto-layout-containers) for a more responsive UI. More information on building responsive canvas apps can be found here:

- [Building responsive canvas apps - Power Apps](/power-apps/maker/canvas-apps/build-responsive-apps)

- [Create responsive layouts in canvas apps - Power Apps](/power-apps/maker/canvas-apps/create-responsive-layout)

## User-centricity

User-centric design is fundamental in creating a successful Power App. It prioritizes the needs, preferences, and experiences of business users, and then tailors the system to their specific requirements. Here's a deeper look into the significance of user-centric design:

### Understanding user needs

User empathy and user research are foundational components of user-centric design, particularly when applied to Power Apps (model-driven and canvas apps).

User empathy involves putting oneself in the shoes of the business user, to genuinely understand their challenges, pain points, and objectives. This empathetic approach ensures that design decisions are driven by a deep understanding of the user's perspective, fostering a more user-friendly and efficient application. In addition, it's also important to address a common challenge encountered during projects implementation.

It's advisable to educate end users about the capabilities and limitations of the Power Platform. Specifically, emphasize the importance of aligning user needs with the platform's features, rather than attempting to replicate designs from previous systems. This proactive approach can help mitigate confusion and ensure a smoother transition for users.

User research takes user-centric design a step further by conducting comprehensive investigations into user behaviors, preferences, and pain points. This research dives into the specifics of how users interact with the Power App, what features they rely on, and where they encounter difficulties.

By collecting user feedback and conducting usability tests, designers gain valuable insights that guide the development of interfaces, workflows, and features tailored to meet user needs effectively. This user-focused approach ultimately leads to Power Apps that aren't only user-friendly but also aligned with the specific requirements and expectations of the users, ensuring a positive and productive user experience.

In the context of user-centric design for Power Apps, several key strategies come into play. First, the development of user personas is essential. These personas are crafted based on extensive research findings, representing various user segments, each with their unique goals and challenges. This allows for more tailored and personalized user experience. Additionally, customized forms and views in model-driven apps and screens in canvas apps are created to present data and actions that are directly relevant to specific user groups. This ensures that users have quick and easy access to the information and functionality they need, enhancing their efficiency.

Furthermore, workflow optimization through automation is a critical aspect of this approach. Automations and transparent integration of data from various systems using connectors, embedded Power Apps, custom pages, or virtual entities can be used to streamline and refine processes based on user needs, improving overall efficiency. Together, these strategies work harmoniously to create Power Apps that aren't only user-friendly but also highly effective in addressing the specific requirements of diverse user groups.

### User-centric benefits

A user-centric design approach for Power Apps offers various benefits. Improved adoption rates create a collaborative work environment, while enhanced productivity results from streamlined tasks. Higher user satisfaction contributes to a motivated workforce, and reduced training time accelerates the onboarding process for new users. These benefits collectively lead to a more efficient, effective, and user-friendly Power App.

- **Improved adoption**: When a Power App is designed with a user-centric approach, it aligns closely with the specific needs and preferences of its users. This alignment fosters a sense of ownership and engagement among employees, making them more likely to adopt the system willingly. Improved adoption rates reduce resistance to change and lead to a more collaborative work environment. In the end, this approach offers greater flexibility for change management. Adjusting requirements for one user group has minimal impact on other groups by maintaining separate experiences for each persona, such as utilizing different apps or distinct model-driven apps.

- **Enhanced productivity**: User-centric design eliminates unnecessary complexities and streamlines tasks within the application. By minimizing cognitive load and reducing the steps required to complete common tasks, users can work more efficiently. This results in increased productivity as users spend less time navigating the system and more time focused on their core responsibilities.

**Higher user satisfaction**: A Power App designed with users in mind leads to higher levels of user satisfaction. Users appreciate interfaces that are intuitive, user-friendly, and closely aligned with their work patterns. A positive user experience fosters motivation and engagement among users, contributing to a more productive and harmonious work environment.

**Reduced training time**: Intuitive interfaces require less training, significantly reducing the onboarding time for new users. When the system is designed with simplicity and user-friendliness in mind, employees can quickly adapt to new application. This is particularly beneficial in dynamic business settings where rapid onboarding is essential to meet operational demands.

## Efficiency

Efficiency in UI/UX design plays a crucial role in improving user productivity and optimizing their interactions with a Power App. An efficient design aims to reduce friction and streamline the user experience, ultimately making it easier and more productive for users to accomplish their tasks. Here's a closer look at the key principles of efficiency in UI/UX design:

### Minimizing steps

- **Task streamlining**: One of the core objectives of an efficient UI/UX design is to minimize the number of steps required to complete tasks. Users should be able to accomplish their goals with as few selections or interactions as possible. This reduction in steps not only saves time but also reduces the chances of errors or frustration.

- **Common user workflows**: To achieve efficiency, it's essential to identify and understand the most common user workflows within the Power App based on the user's persona. These workflows often represent the core activities of users, such as data entry, lead conversion, or customer inquiries. It's recommended to tailor the UI specifically for the user persona. In model-driven apps, this can be achieved through specific pages, forms, and view designed for specific Security roles. In canvas app, it's often more efficient to have separate apps for each persona.

### Optimizing workflows

- **Workflow optimization**: Once common user workflows are identified for each persona, the next step is to optimize them for efficiency. This involves redesigning processes to eliminate bottlenecks, redundant steps, or unnecessary complexity.

- **Use of features**: UI/UX designers can use features provided by the Power Apps to enhance efficiency. This may include:

  - Implement and test field traversing by using the keyboard.

  - Making comprehensive guide available to users on keyboard shortcuts provided by Power Apps. You can find more details in the reference section.

  - Implement automation where needed. Examples could be to focus on reducing manual data entry and repetitive tasks, automated data validation or rule-based triggers. All these can save users significant time and effort.

  - Use of Copilot assistance for filling in forms in model-driven apps. Learn more at [Introducing Copilot assistance for filling in forms in model-driven apps](https://powerapps.microsoft.com/blog/introducing-copilot-assistance-for-filling-forms-in-model-driven-apps/).

- **User feedback**: Collect user feedback and insights to continuously refine and optimize workflows. User feedback can provide valuable information on pain points and opportunities for further efficiency improvements.

- **Design for performance**: Designing with performance in mind ensures that user flows aren't interrupted by long waits for the application to react.

  For **model-driven apps**, learn more in the [Scalability](#scalability) section.

  For **canvas apps**, learn more at [Overview on how to create performant Power Apps](/power-apps/maker/canvas-apps/create-performant-apps-overview).

- Avoid Large Data Set Loads where possible and make use of the `Concurrent()` function.

- Optimize data query patterns [Optimized query data patterns in Power Apps](/power-apps/maker/canvas-apps/optimized-query-data-patterns)

- Using Power Automate to populate collections will inherently have a performance overhead to invoke and run the flow. It's therefore recommended to avoid this if possible, however if there's a need then ensure that queries within the flow are filtered and data returned by the flow is kept to a minimum.

- Avoid using too many data connections (including collection variables) in applications.

- Ensure delegation of filters of data sources wherever possible

- Avoid Control Overload as the more objects and controls on any given screen take longer to load. The [modern Controls](/power-apps/maker/canvas-apps/controls/modern-controls/modern-controls-reference) are built to reduce the complexity in apps and target higher performance, using/migrating apps to use these should be considered.

**Optimizing app build and maintenance**: For canvas apps, applying [Power Apps canvas app coding standards](https://powerapps.microsoft.com/en-us/blog/powerapps-canvas-app-coding-standards-and-guidelines/) optimizes the build and maintenance of the application. This helps accelerate improvements in UI/UX based on user feedback and guidance to further increase adoption of the app through iterative improvements.

Let's also take a look at some new innovative capabilities that can further help ensure smooth experience while working with Power Platform apps. One such capability is Copilot.

### Copilot

Copilot in Dynamics 365 is a collection of innovative AI based tools designed to bring in more relevant information, which eventually enriches user experience within the Dynamics 365 ecosystem. Its integration into Dynamics 365 applications can significantly improve the efficiency and effectiveness of information availability, creating a more intuitive and seamless experience for users. These copilots also make user experience better by providing intelligent suggestions, generating insights, and helping with reducing overall time spent on repetitive tasks.

Various copilots are designed for different business application suites within Dynamics 365. You can find the full list of Dynamics 365 copilots at the link provided below. As Microsoft continues to innovate, it's expected that this list will expand with the development of more copilots in the future.

Learn more at [Copilot for Dynamics 365](/microsoft-cloud/dev/copilot/copilot-for-dynamics365).

You can explore our blog post on Microsoft Copilot, which shares more details into bringing the next generation of AI into business applications: [Introducing Microsoft Dynamics 365 Copilot, the world's first copilot in both CRM and ERP, that brings next-generation AI to every line of business - The Official Microsoft Blog](https://blogs.microsoft.com/blog/2023/03/06/introducing-microsoft-dynamics-365-copilot/)

Find more information in the following resources:

- [Introducing Microsoft Dynamics 365 Copilot](https://www.youtube.com/watch?v=GMwtXDx-JUI), a video that introduces the features and benefits of Copilot.

- [Copilot for Dynamics 365](/microsoft-cloud/dev/copilot/copilot-for-dynamics365), an article that provides an overview of Copilot for different Dynamics 365 apps.

- [Use Copilot in Dynamics 365 apps](/dynamics365/sales/use-sales-copilot), an article that shows you how to use Copilot in Dynamics 365 Sales, with examples of predefined prompts and chat scenarios.

In addition, if you're looking to enhance efficiency and harness AI tailored to your specific business requirements that generate greater efficiency for your users, Microsoft Copilot Studio offers a solution. This platform enables the customization and development of your own Copilots or the extension of existing ones for Dynamics 365 and Microsoft 365. It serves as a unified platform for creating Copilot experiences within Power Apps, facilitating access to your organization's resources such as websites, knowledge bases, and documentation. This integration significantly boosts productivity within applications by streamlining access to relevant information and tools.

Adding to its capabilities, Microsoft Copilot Studio can be instrumental in scenarios like customer support. By using AI, you can develop Copilots that offer real-time assistance, automate responses to frequently asked questions, and guide users through troubleshooting processes. This not only empowers your workforce by freeing up resources to focus on complex queries but also elevates the customer's experience through swift and effective support. Ultimately, Microsoft Copilot Studio can be a pivotal tool in transforming your organization by integrating advanced AI functionalities to meet a wide array of business needs, while ensuring that user experience and efficiency is at the top of mind.

Use the following resources to learn more:

- [Microsoft Copilot Studio \| Extend Copilots or Create Your Own](https://www.microsoft.com/microsoft-copilot/microsoft-copilot-studio), a website that introduces the features and benefits of Copilot Studio.

- [QuickStart: Create and deploy a Microsoft Copilot Studio copilot](/microsoft-copilot-studio/fundamentals-get-started), an article that guides you through the steps to create and deploy a copilot on the portal.

- [Overview of Microsoft Copilot Studio 2023 release wave 2](/power-platform/release-plan/2023wave2/microsoft-copilot-studio/), an article that provides an overview of Copilot Studio and its capabilities.

- [Microsoft Copilot Studio Expands Region Availability For Generative AI](https://microsoftcopilotstudio.microsoft.com/blog/microsoft-copilot-studio-expands-region-availability-for-generative-ai/), a blog post that announces the expansion of region availability for generative AI in Copilot Studio.

- [Announcing Microsoft Copilot Studio](https://www.microsoft.com/microsoft-365/blog/2023/11/15/announcing-microsoft-copilot-studio-customize-copilot-for-microsoft-365-and-build-your-own-standalone-copilots/), a blog post that announces the launch of Copilot Studio and showcases some of its features and benefits.

### Efficiency benefits

Efficiency-driven UI/UX design offers several benefits to users and organizations:

- **Time savings**: Streamlined workflows and reduced steps lead to significant time savings for users. This allows them to focus on more value-added tasks and be more productive overall.

- **Reduced errors**: Fewer manual interactions and simplified processes reduce the likelihood of errors, improving data accuracy and the quality of records.

- **Enhanced user satisfaction**: Users appreciate systems that are easy and efficient to use. A positive user experience fosters satisfaction, boosts morale, and encourages higher system adoption rates.

- **Increased productivity**: Efficiency-driven design enables users to accomplish more in less time, translating into increased overall productivity for the organization.

## Feedback and guidance

Providing feedback and guidance is essential to guide users through their interactions with the Power Apps. Feedback informs users about the outcomes of their actions, while guidance assists them in making informed choices. Let's dive into more details on various aspects of it.

### Enhancing user experience

Incorporating robust feedback and guidance mechanisms into the UI/UX design of Power Apps is fundamental to ensuring a user-centric and supportive environment. It empowers users by providing clarity, assistance, and the resources needed to navigate the system effectively. By prioritizing feedback and guidance, organizations can cultivate a positive user experience, reduce user frustration, and foster confidence in their system.

### Clarity and reassurance

Providing timely and clear feedback assures users that their actions are being acknowledged and processed by the system. For example, when users submit a form or initiate a process, a well-designed interface should offer immediate feedback, such as confirmation messages or progress indicators. This reassures users that their input has been received and is being acted upon.

### Error handling

Effective feedback is equally crucial when users encounter errors or make mistakes. Instead of vague error messages, the system should provide specific guidance on what went wrong and how to rectify it. Clear error messages and actionable recommendations empower users to correct their actions promptly, reducing frustration, and enhancing the overall user experience.

- **Model-driven apps**: Ensuring correct input values on all [controls](/power-apps/maker/data-platform/types-of-fields), [required fields](/power-apps/maker/data-platform/create-edit-field-solution-explorer#column-requirement-options) are appropriately set and if more complicated validation is required make use of [Business Rules](/power-apps/maker/model-driven-apps/create-business-rules-recommendations-apply-logic-form) and [Client Side scripting](/power-apps/developer/model-driven-apps/client-scripting) with the [Form Notification](/power-apps/developer/model-driven-apps/clientapi/reference/formcontext-ui/setformnotification) ensures consistency in how errors/notification are surfaced to users.

- **Canvas apps**: Error handling and validation need to be designed into your application. It's therefore advisable to enable [Formula-Level Error Management](/power-platform/power-fx/reference/function-iferror) and ensure that code is added to check for:

  - Patch Function errors

  - Power Automate Flow errors

  - Submit Form errors

    For unexpected errors, use the canvas app's `OnError´ property to give a detailed description of the error to the user.

### Onboarding and training

Feedback and guidance play a significant role in onboarding new users. The system should offer intuitive tooltips, walkthroughs, or guided tours to help users understand its features and functionalities. This proactive guidance not only accelerates the learning curve but also instills confidence in users as they navigate the system.

### User support

Users may have questions or require assistance while using the system. A well-designed interface should provide easily accessible help resources, such as knowledge base links, contextual help buttons, or chat support options. This availability of support reinforces the idea that users aren't alone and can seek assistance when needed.

#### Copilots and custom chat bots

The recommended approach is to use Copilot Studio to build custom chat bots and integrate it with your model-driven or canvas apps. Copilot studio is a low-code platform that lets you create intelligent chatbots for various user support scenarios. Some of the benefits of using Copilot Studio are:

- You can use generative AI to create natural and contextual conversations that can answer common questions, provide guidance, and resolve issues.

- You can customize your chatbots with your own data, logic, and branding, and integrate them with various Microsoft products and services, such as Dynamics 365, Power Platform, Teams, and Outlook.

- You can deploy your chatbots across multiple channels, such as websites, mobile apps, Facebook, and any channel supported by the Azure Bot Framework.

- You can manage and secure your chatbots with central administration tools, built-in security roles, and comprehensive analytics.

The classic approach would be to use [Custom help panes and guided tasks](/power-apps/maker/data-platform/create-custom-help-pages) for model-driven apps. For canvas apps, see [Create custom help pages - Power Apps](/power-apps/maker/data-platform/create-custom-help-pages).

In addition, help screens and links to help material should be designed into your application.

### Continuous improvement

Feedback mechanisms, such as user surveys or feedback forms, should be integrated into the Power App. These tools allow users to provide feedback on their experiences and suggest improvements. Collecting user feedback is invaluable for iterative design enhancements and demonstrates a commitment to ongoing improvement.

Understanding how users are interacting with a Power App can provide deep insights into how to improve user engagement. This can be achieved by using Application Insights with Power Apps to analyze system-generated logs and understand user interactions with your app. Before you can send system-generated logs from an app, you need to create an Application Insights resource.

- **Model-driven apps**: Connect the [environment to Application Insights](/power-platform/admin/set-up-export-application-insights) to log the events [for model-driven apps](/power-platform/admin/telemetry-events-model-driven-apps) and [Dataverse](/power-platform/admin/telemetry-events-dataverse), extra [custom telemetry](/power-apps/developer/data-platform/application-insights-ilogger) can be added to enrich server side plugin monitoring.

- **Canvas apps**: Connect the [app to Application Insights](/power-apps/maker/canvas-apps/application-insights) to log events from the canvas app, more [custom telemetry](/power-apps/maker/canvas-apps/application-insights#create-custom-trace-events) can be added in the app using the [Trace](/power-platform/power-fx/reference/function-trace) function.

As the user browses the app screens, events are automatically logged to Application Insights, including usage details such as where the app is accessed from, which devices are used, and the browser types used.

Once the data is collected, you can use the powerful analytics tools in [Application Insights](/azure/azure-monitor/app/app-insights-overview) to diagnose issues and understand what users actually do with your apps. This can help you drive better business decisions and improve the quality of your apps.

## Scalability

Scalability in UI/UX design means to design the system to accommodate growth and change. It ensures that the interface can handle increased data, users, and functionality without a significant drop in performance or usability.

Design a flexible architecture that allows for easy expansion. Consider future data volumes and user loads when designing Dataverse tables and schemas and UI components.

### Future proofing

Scalable design anticipates the dynamic nature of businesses. It considers that organizations evolve over time, necessitating modifications, additions, or expansions within the system. A scalable interface is built with flexibility in mind, ensuring that it can accommodate new features, data volumes, or workflows without a complete overhaul.

### Efficiency amidst growth

A scalable design minimizes disruptions caused by growth. It ensures that as the system scales up, it doesn't become sluggish or convoluted. Users should continue to experience smooth performance and efficient interactions, even as the system handles increased data loads or more complex processes.

- **Model-driven apps**: [Design forms for performance in model-driven apps - Power Apps](/power-apps/maker/model-driven-apps/design-performant-forms)

- **Canvas apps**: [Common canvas apps performance issues and resolutions - Power Apps](/power-apps/maker/canvas-apps/common-performance-issue-resolutions)

### Adapting to changing needs

Scalability encompasses adaptability. As business processes evolve or new user groups emerge, the interface should be easily configurable to cater to these changes. This adaptability may involve the addition of custom views, dashboards, or workflow automations to meet evolving requirements.

### User-friendly scaling

Scalability shouldn't compromise user-friendliness. The interface must maintain its intuitive nature as it grows. New features or functionalities should be seamlessly integrated without overwhelming users with unnecessary complexity.

### Cost efficiency

A scalable design often leads to cost savings. Instead of having to invest in a complete system overhaul when growth occurs, organizations can make targeted enhancements and adjustments. This approach is not only cost-effective but also reduces downtime and disruption.

### Data management

Scalability in Power Apps also relates to data management. The system should efficiently handle larger datasets, offer advanced data filtering options, and facilitate data archiving or purging to keep the system responsive and organized.

### Cross-platform scalability

With the increasing use of various devices, including mobile and tablets, scalability also involves ensuring that the system remains accessible and functional across different screen sizes and platforms. A responsive design is essential to maintain usability on various devices.

## Accessibility

Accessibility is the practice of designing interfaces to be usable by individuals with disabilities. It ensures that all users, regardless of their abilities, can access and interact with the system.

Implementation of accessibility standards in the Power Platform is crucial and by default part of all business application suits out of the box functionality. This also ensures that all users, regardless of their abilities, can effectively use and interact with applications built on the Power Platform. Microsoft recognizes the importance of accessibility and provides extensive documentation and resources to support developers in creating accessible experiences.

One key reference for accessibility in the Power Platform is Microsoft Accessibility Documentation, which provides guidelines and best practices for designing accessible applications. This documentation covers various aspects of accessibility, including keyboard navigation, screen reader compatibility, and ensuring content is perceivable, operable, and understandable for all users.

Model-driven apps adhere to accessibility standards such as WCAG (Web Content Accessibility Guidelines) to make the interface screen-reader friendly, keyboard navigable, and compatible with assistive technologies.

Learn more about accessibility implementation in Power Apps with [Dynamics 365 accessibility and ADA compliance](/dynamics365/get-started/accessibility/).

Canvas apps provide the properties to support accessibility the following guidance on [making apps accessible](/power-apps/maker/canvas-apps/accessible-apps) should be followed and the inbuilt [accessibility checker](/power-apps/maker/canvas-apps/accessibility-checker) should be checked during application development.

By following accessibility guidelines and incorporating accessibility features into Power Platform custom applications, developers can create more inclusive and user-friendly experiences for all users. This not only aligns with ethical considerations but also helps organizations comply with accessibility regulations and standards, such as the Web Content Accessibility Guidelines (WCAG), ensuring that their applications are usable by everyone.

### Related resources

- Blog for [Power Apps Canvas App Accessibility Guidelines](https://powerapps.microsoft.com/blog/powerapps-canvas-app-accessibility-guidelines/)

- [Microsoft Accessibility](https://www.microsoft.com/en-us/accessibility/)

- [Web Content Accessibility Guidelines (WCAG) 2 requirements](https://www.w3.org/WAI/WCAG21/quickref/)  
