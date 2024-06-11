---
title: UI/UX design components for Power Apps model-driven apps
description: Discover how to use the navigation bar, dashboards, forms, views, and other visual components to create user-friendly and responsive layouts for your model-driven apps.
author: dereklh77
ms.author: riasif
ms.topic: conceptual
ms.date: 06/03/2024
---

# UI/UX design components for Power Apps model-driven apps

This article discusses the components that you can use to design the layout of your model-driven apps in Power Apps. You'll learn about their purposes, design considerations, and best practices.

## Navigation bar

The navigation bar is a top-level menu structure that guides users to a model-driven app's modules and functionalities. Customize the navigation bar by updating the site map. Multiple site maps for various applications can be created in your environment, so make sure that you select the correct site map for your app before editing. Learn more in [Create a model-driven app site map using the site map designer](/power-apps/maker/model-driven-apps/create-site-map-app).

Here are some best practices for designing an effective navigation bar:

- **Prioritize essential modules.** Identify and prioritize the most frequently used modules and features in your app. Make sure that they're easily accessible from the navigation bar.

- **Keep it simple.** A cluttered navigation bar can overwhelm users. Keep it simple. Avoid overloading it with too many options and design for a little vertical scrolling as possible.

- **Design for role-based navigation.** Customize the navigation bar based on user roles. Users should see only the modules and features that are relevant to their roles, enhancing efficiency and reducing cognitive load.

- **Group logically.** Group related modules together in the menu. Logical grouping aids user understanding and navigation. For example, sales-related modules like Leads, Opportunities, and Contacts can be grouped under a "Sales" area.

- **Create user-friendly labels.** Use clear and concise labels for modules and features. Avoid jargon or abbreviations that might confuse users. Labels should be easy for all users to understand.

- **Iconography.** Use icons with labels for visual recognition. Choose universally recognized icons or provide tooltips to explain their meaning.

- **Apply adaptive design principles.** Make sure that the navigation bar adapts to different screen sizes, including mobile devices. The menu should remain usable and accessible on smaller screens.

- **Be consistent across areas.** Maintain a consistent navigation structure across all modules in the app. Users should have a similar experience when moving between different parts of the application.

- **Plan user training and onboarding.** Provide training and onboarding materials to help users understand how to use the navigation bar effectively. Clear documentation and user guides can be invaluable.

- **Design for accessibility.** Make sure that the navigation bar can be used with a keyboard and is compatible with screen readers.

- **Collect and apply user feedback for continuous improvement.** Gather feedback from users about the navigation bar's usability. Periodically review its effectiveness and make improvements based on user input.

- **Test with real users and supported devices.** Before finalizing the navigation bar design, conduct usability testing with actual users. Such real-world testing helps identify any usability issues and ensures that the navigation is intuitive.

Remember that the navigation bar is a critical element in user experience design for model-driven apps. A well-designed navigation bar can significantly enhance user productivity and satisfaction.

## Dashboards

In model-driven apps, dashboards allow users to visualize key data and metrics at a glance. Because dashboards are highly customizable, users can create a personalized workspace where they can monitor their daily tasks, track progress and performance, and make data-driven decisions. Dashboards aren't just informative but also interactive, allowing users to drill down into details, access related records, and take actions directly from the dashboard.

Dashboards are composed of components such as charts, lists, web resources, and even embedded Power BI reports, all of which can be arranged and configured according to each user's individual preferences. Learn more in [Create or edit model-driven app dashboards](/power-apps/maker/model-driven-apps/create-edit-dashboards).

Here are some best practices for designing effective dashboards in model-driven apps. We offer [best practices for charts and visualizations](#charts-and-visualizations) in general in a later section.

- **Take a user-centric approach.** It's important to design dashboards that are tailored to the roles and responsibilities of your app's users. Understand the typical tasks and objectives of users in different departments, such as sales, marketing, customer service, or management, and tailor dashboards to their unique needs.

- **Show relevant metrics.** Include only the most relevant metrics and data on each dashboard. Avoid clutter by focusing on the essential information that users need to make informed decisions. Keep in mind that less is often more when it comes to dashboard design.

- **Represent data visually.** Use charts and visual elements to represent data effectively. Visualizations make it easier for users to grasp trends, patterns, and anomalies. Make sure that the visualizations are appropriate for the type of data that's being displayed.

- **Personalize strategically with widgets.** Power Apps provides a selection of widgets to build model-driven app dashboards. These widgets give users the flexibility to build dashboards in the layout they prefer, crafting personalized data views tailored to their unique business requirements. Make sure that widgets don't represent the same data in a different format. Widgets should complement each other and offer a holistic view of the business scenario.

- **Empower users with data filtering and interactivity.** Default filtering features empower users to refine the data that's shown on their dashboards according to specific criteria. Interactive elements enhance the user experience by allowing users to easily explore data from different angles.

  To maximize the benefits of filtering and interactivity features, it's crucial that users understand how they work. We highly recommend that you incorporate guidance as part of user training. The guidance should cover how to filter data, drill down into details, and interact with different dashboard components.

- **Prioritize important information on mobile devices.** In today's mobile workforce, users often access data on smartphones and tablets, so a mobile-friendly dashboard and interface design is crucial for accessibility. Make sure that dashboards are responsive, prioritized, and optimized for mobile devices.

- **Integrate Power BI reports.** A feature flag in Power Apps settings allows you to integrate Power BI dashboards in your app dashboards. Power BI dashboard integration allows users to access Power BI dashboards directly in the app. Learn more in:

  - [Embed a Power BI report in a model-driven app main form](/power-apps/maker/model-driven-apps/embed-powerbi-report-in-system-form)
  - [Create or edit a Power BI embedded system dashboard](/power-apps/maker/model-driven-apps/create-edit-powerbi-embedded-page)
  - [Add or edit Power BI visualizations on your dashboard](/power-apps/user/add-powerbi-dashboards)

- **Collect and apply user feedback for continuous improvement.** Gather feedback from users on the effectiveness of your dashboards and iterate and improve their design based on user input.

## Forms

Forms provide a structured interface where users enter and view data in a model-driven app. Because forms play a central role in data management, their design affects the efficiency of data entry and retrieval. Well-designed forms enhance user productivity and satisfaction by making it easy for users to interact with data in the app.

Here are some best practices for designing effective forms in model-driven apps:

- **Take a user-centric approach.** Start by understanding the needs and preferences of your users. Design forms that make it easy for them to enter and retrieve information efficiently.

- **Keep it simple.** Avoid clutter and unnecessary complexity. Simplify the layout by only including essential fields and controls. Use tabs or sections to group related information logically.

- **Prioritize important information.** Place the most critical data at the top of the form so that it's easily accessible without scrolling.

- **Be consistent across forms.** Maintain consistency in field labels, positioning, and styling across all forms in your app. Consistency in design enhances user familiarity and reduces cognitive load.

- **Apply responsive design principles.** All model-driven app forms are responsive by default. Make sure that your forms still adapt well to different screen sizes and devices after you customize them. Test how your forms look and work on both desktop and mobile devices after customization.

- **Customize forms for specific roles.** Tailor form display fields and controls for the specific roles and responsibilities of your app's users. Hide or disable irrelevant components. You can associate a security role to a form to make sure that relevant forms are visible to individual personas that are defined in the system.

- **Group and order fields logically by task.** Arrange fields in a logical order that matches the sequence of tasks that users perform. For instance, start with contact details before moving to order information.

- **Use business and formatting rules strategically.** Use business rules and conditional formatting to show or hide fields dynamically based on user input, reducing form complexity.

- **Validate data with rules.** Implement form-level and field-level validation rules to make sure that users enter data accurately. Provide meaningful error messages when users enter incorrect or incomplete data.

- **Avoid overloading a form.** Don't overload a form with too many fields. You might be able to add as many fields as a table allows, but it will greatly slow form loading and create a frustrating user experience.

- **Use subgrids sparingly.** Subgrids can display related records. Use them when needed but avoid overwhelming users with excessive subgrids on a single form. It's better to move some of the grids to other dedicated tabs based on the logical design and priority of the information.

- **Consider localization requirements.** If your organization operates in multiple regions, make sure that it provides localized strings for labels and messages and that the UI can adapt to different languages and cultural preferences.

- **Collect and apply user feedback for continuous improvement.** Periodically review your forms to assess their effectiveness and user feedback. Make necessary adjustments to improve the user experience.

### Secure data with roles and permissions

Make sure that sensitive information is only visible to authorized users. Logically group fields that contain sensitive data to provide a consistent user experience. Use security roles with row-level and field-level permissions to control access to forms and data.

#### Row-level permissions

Control access to individual records or rows in Dataverse tables with row-level permissions. They specify which users or teams can view and interact with specific records. Applying row-level permissions requires a good understanding of the Power Platform security model. Learn more in:

- [Security concepts in Microsoft Dataverse](/power-platform/admin/wp-security-cds)
- [Hierarchy security to control access](/power-platform/admin/hierarchy-security)
- [Use record-based security to control access to records](/dynamics365/customerengagement/on-premises/developer/security-dev/use-record-based-security-control-access-records)

Use security roles to make sure that sales representatives can only access customer records that are assigned to them or HR personnel can only view the records of employees in their department. You can define multiple security roles on a table and combine them with levels of access, such as user, business unit, parent-child business unit, and organization, in the security role settings.

Row-level permissions are closely integrated with model-driven apps forms and directly affect which records appear in tables and subgrids. Users only view the records they have permission to access when selecting primary records or related records. When a user opens a form, the app makes an API call to the associated record in Dataverse and checks the user's permissions. If the user isn't allowed to view or edit that record, it's not displayed in the form.

#### Field-level permissions

Use field-level permissions to control access to individual fields in a record. They specify which users or teams can view or edit specific columns.

Use field-level permissions to restrict access to sensitive information in records that otherwise are restricted at a higher level. For instance, although all HR personnel can view employee records, only HR managers can view salary information.

Field-level permissions are closely integrated with model-driven apps forms through API calls to Dataverse. Unlike row-level permissions, field-level permissions don't affect the appearance of the form. Records are shown as long as the user has the right row-level permissions. However, if a user doesn't have permission to view a field, the data in the column is masked as set in the field-level security profile.

Field-level security does have an impact on your app's performance. Limit its use based on priority and data criticality for the business.

Learn more in [Column-level security to control access](/power-platform/admin/set-up-security-permissions-field).

### Design for performance

Excessive customization can slow down form loading and degrade the user experience. Monitor form load time using [Application Insights telemetry for model-driven apps](/power-platform/admin/telemetry-events-model-driven-apps).

Here are some best practices for designing for performance in model-driven apps forms:

- **Define and follow best practice guidelines.** Define rules for your organization and best practices for the dev team, including rules to load and persist data asynchronously, prioritizing critical data over nonessential information.

- **Keep forms simple and focused.** Limit the number of fields and controls on your forms to only what's necessary for the user's workflow. Adding too many fields, including hidden fields, can slow down form loading.

- **Use quick view forms sparingly.** Quick view forms can add overhead to form loading, especially if they contain a lot of data. Use them judiciously.

- **Optimize JavaScript code.** Review and optimize any JavaScript code that's used for form customizations. Inefficient code can significantly affect form load time. Avoid long-running scripts and consider asynchronous loading when possible.

- **Minimize web resources.** Use web resources (HTML, JavaScript, CSS) judiciously. Minimize their use if they aren't critical for the form's functionality. Compress and optimize web resource files for faster loading.

- **Streamline sections.** Organize fields logically in sections. Prioritizing frequently used sections can help in providing a better user experience.

- **Limit the number of subgrids and iFrames.** Each subgrid or iFrame adds to form load time. Evaluate their necessity and consider alternative ways to present the data.

- **Monitor and optimize plug-ins.** If you use plug-ins in your environment, make sure that they're well-optimized and not causing bottlenecks.

- **Test cross-browser and cross-device.** Make sure that your forms perform well on different web browsers and devices. Test on popular browsers like Chrome, Firefox, Microsoft Edge, and mobile devices to identify any performance disparities.

Here are some scripting best practices for model-driven apps forms:

- **Write efficient JavaScript.** Don't perform DOM manipulation. Prefer APIs for UI changes. Learn more in [Interact with HTTP and HTTPS resources asynchronously](/power-apps/developer/model-driven-apps/best-practices/business-logic/interact-http-https-resources-asynchronously).

- **Load data when it's needed.** Don't load all the data up front if only a subset is needed. Use asynchronous web requests.

- **Reduce server-side calls.** Minimize the use of real-time data retrieval methods like OData or FetchXML. Use the Web API efficiently with batch requests and filters to limit the amount of data that's retrieved.

- **Optimize events.** Carefully evaluate event handlers, especially `OnLoad` and `OnChange`. Minimize or remove them where they're not essential. Use business rules to apply native capability. Learn more in:

  - [Create a business rule for a table](/power-apps/maker/data-platform/data-platform-create-business-rule)
  - [Asynchronous OnLoad event handler support](/power-apps/developer/model-driven-apps/clientapi/reference/events/form-onload#asynchronous-onload-event-handler-support)
  - [Best practices and guidance for client-side scripting for model-driven apps](/power-apps/developer/model-driven-apps/best-practices/business-logic/)

- **Optimize business rules and workflows.** Use business rules and Power Automate workflows where applicable. Make sure that server-side workflows and plug-ins are optimized and only trigger when necessary.

- **Review code and profiling.** Regularly review your form designs and customizations. Use profiling tools to identify performance bottlenecks in scripts. Refactor or remove JavaScript code and components that are no longer necessary or cause performance issues.

- **Optimize for mobile devices.** For mobile apps, make sure that only required fields are shown.

- **Test the latest release wave before rolling out to production.** Be sure to test each new release wave in your test environment before making updates in your production environment.

## Views and grids

In model-driven apps, records are displayed in views and grids that allow users to browse large datasets and filter records based on specific criteria.

Here are some best practices for designing effective views and grids in model-driven apps:

- **Design for readability and easy navigation.** Make sure that view and grid layouts prioritize readability. Avoid overcrowding the grid with too many columns, and use sufficient spacing between them. Make sure that the first column has important information that users can act on, such as selecting an account name to view the record details.

- **Add sorting options and filtering capabilities.** Sorting helps users quickly find the data they need and identify trends. Implement default sorting on system views, and allow users to sort based on specific columns in custom views. Filtering options are available by default to help users refine data based on specific criteria. Filters allow users to narrow down records, reducing clutter and focusing on what's relevant.

- **Allow users to customize and save views.** Users can tailor a view to their needs by using filters to narrow down the records that are displayed and by selecting which columns to display and in what order. They can then save the customization as a personal view for easy access, streamlining their daily workflows.

- **Allow users to share their custom views.** Users can use view sharing options to enhance collaboration by ensuring consistent access to essential datasets across the organization.

- **Apply responsive design.** Test and make sure that grids and views are responsive and adapt well to various screen sizes and orientations. Users should have a consistent experience on both desktop and mobile devices.

- **Design with accessibility in mind.** Test to make sure that grids are accessible to all users. For example, test keyboard shortcuts for column sorting and filtering to assist users with mobility impairments.

- **Provide user training.** Provide training and guidance on using views effectively. Educate users on how to apply filters, sort records, and use advanced find to locate specific data quickly.

### Optimize for performance

Be mindful of performance when you're designing views. Make sure that views are optimized to load quickly, especially if you're working with large datasets. Here are some considerations and potential performance issues to be aware of when you add lookups to views:

- Including lookup fields in views often requires retrieving more data from related tables. This practice can increase the volume of data that's retrieved and affect query performance.

- When lookups are added to views, the underlying SQL queries may involve join operations to retrieve related data. Joins can be resource-intensive and slow down query execution.

- As the number of lookups in a view increases, the complexity of the query grows. Complex queries can be slower to execute, especially when querying large datasets.

## Ribbon and command bar

The ribbon and command bar contain contextual commands and actions that users can perform in specific tables and forms. Here are some best practices for designing effective ribbons and command bars in model-driven apps:

- **Provide auick access to frequently used actions.** Customize the ribbon and command bar to prioritize quick access to actions and commands that users need most. Identify the most common tasks that users perform in specific tables and make sure that these actions are readily available without unnecessary choices or navigation.

- **Group logically.** Group related commands logically in the ribbon and command bar, in a way that makes sense to users and mirrors the natural flow of tasks.

- **Customize by role and responsibility.** Customize the ribbon and command bar to align with the specific needs of different user roles and responsibilities.

- **Use conditional visibility.** Use conditional visibility rules to show or hide commands based on specific criteria. For example, certain actions may be relevant only when a record is in a particular status or has specific attributes. Display commands contextually to reduce clutter and improve the user experience.

- **Design for accessibility.** Test and make sure that the ribbon and command bar are accessible to all users. Evaluate your customizations considering keyboard navigation, screen reader compatibility, and adherence to accessibility standards.

- **Provide user training.** Include tooltips or help text to understand the purpose and functionality of each action and command.

Learn more in:

- [Customize the command bar using command designer](/power-apps/maker/model-driven-apps/use-command-designer)
- [Customize commands and the ribbon](/power-apps/developer/model-driven-apps/customize-commands-ribbon)
- [Ribbons available](/power-apps/developer/model-driven-apps/ribbons-available)

## Charts and visualizations

Charts and visualizations are powerful tools for presenting data in an easily understandable way. They transform raw data into visual patterns, helping users identify trends, correlations, and anomalies more quickly than by inspecting rows of numbers. They make it easier for users to gain insights, identify trends, and make informed, data-driven decisions.

Here are some best practices for designing effective charts and visualizations in model-driven apps:

- **Capture attention with visual appeal.** Create visually appealing charts and visualizations that capture users' attention. Choose the appropriate widgets to make data visually engaging without overwhelming the user.

- **Customize to match branding or other preferences.** Customize charts and visualizations to match your organization's branding and preferences. Tailor chart types to convey specific meaning.

- **Present data clearly.** Make sure that charts and visualizations are easy to interpret without ambiguity. Use labels, legends, and annotations to provide context and guide users in understanding the data. Avoid cluttered or overly complex visuals.

- **Check data for accuracy.** Charts and visualizations should accurately represent the underlying data. Double-check data sources to prevent misinterpretation or inaccuracies in the visualizations.

- **Apply responsive design principles.** If your app is used on both desktop and mobile devices, design charts to be responsive and effective in the user's context. Make sure that charts and visualizations adapt to different screen sizes and orientations without losing their effectiveness.

- **Allow users to drill into the data.** Make sure that users can drill down into the underlying data in a way that doesn't detract from the user experience. Provide interactive elements that allow users to explore data further.

- **Be consistent.** Maintain a consistent style and design language across all the charts and visualizations in your app. This consistency helps users quickly understand and navigate different reports and dashboards.

- **Provide user training.** Provide training and guidance to users on how to use and interpret charts and visualizations effectively. Make sure that they understand the meanings of various chart types and visual cues.

## Business process flows

In model-driven apps, business process flows guide users through predefined workflows or processes, ensuring that they follow consistent and structured steps when entering data or completing tasks. Business process flows consist of stages and steps, where each stage represents a phase in a process, and each step corresponds to an action or data entry task.

For example, suppose you're designing a sales process in a model-driven app. Your business process flow could include stages such as *Lead Generation*, *Qualification*, *Proposal*, and *Closing*. Within each stage, you might define steps that guide users on what actions to take, such as *Create Lead*, *Qualify Lead*, *Generate Proposal*, and *Close Deal*.

Keep in mind that business process flows are specific to screens that provide guidance to the user. Making calls through an API is independent from the UI and the user experience.

Here are some best practices for designing effective business process flows in model-driven apps:

- **Limit the number of stages.** Business process flows can have a maximum of 30 stages. This limitation serves a crucial purpose, keeping business process flows manageable and preventing them from becoming overly complex. However, you shouldn't simply adhere to the limit. It's a best practice to keep your business process flows as simple and straightforward as possible. The user experience will be more streamlined and user-friendly.

- **Limit the number of steps.** Each stage in a business process flow can contain any number of steps. It's essential to provide guidance in sufficient detail without overwhelming users.

- **Associate business process flows with tables.** Business process flows can be associated with specific tables to guide users through processes that are related to those tables. Make sure that your business process flow is associated with the appropriate table for seamless integration with your business processes.

- **Integrate Power Automate workflows.** By integrating Power Automate workflows with your business process flows, you can streamline processes in the background. Automation allows users to focus on key elements without compromising the user experience by handling some tasks on the user's behalf, ensuring efficiency and enhancing productivity.

- **Use conditional branching for dynamic paths.** Conditional branching is allowed in business process flows. You can design your business process flows to dynamically change paths based on user inputs or conditions, ensuring that users are directed to the most relevant steps.

- **Take advantage of user roles and security.** Configure business process flows to align with user roles and security settings. You can control which users or teams have access to specific business process flows, ensuring that the process guidance is relevant to their roles.

## Related resources

- [UI/UX design components for canvas apps](ui-ux-component-details-model-driven-apps.md)
- [UI/UX design components for tests and user feedback](ui-ux-component-details-testing-feedback.md)
- [Key UI/UX design principles](ui-ux-design-principles.md)
- [Introduction to UI/UX design for customer engagement apps](introduction-customer-engagement-ui-ux-design-guide.md)
