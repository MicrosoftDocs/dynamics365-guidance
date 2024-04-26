---
title: UI/UX component details for model-driven apps
description: Learn about components that constitute the layout of model-driven apps, including outlines of component purposes, design considerations, and best practices.
author: dereklh77
ms.author: riasif
ms.topic: article
ms.date: 04/12/2024
---

# UI/UX component details for model-driven apps

In this article, we dive into the various components that constitute the layout of model-driven apps and explore their purposes, design considerations, and best practices.

### Navigation bar/site map

The navigation bar in model-driven apps is the primary means by which users access different modules and areas of the application. It provides a top-level menu structure that guides users to various functionalities.

Ensure that the navigation bar is logically organized, with clear labels and icons. Customize the application site map to prioritize the most frequently used modules for your users. Use security roles and rules to display items for the various personas that use the application. Designing a navigation bar requires careful consideration of user needs and efficient access to critical features. Here are some best practices for designing a navigation bar:

- **Prioritize essential modules**: Identify and prioritize the most frequently used modules and features within your app implementation. Ensure that these are easily accessible from the navigation bar.

- **Keep it simple**: A cluttered navigation bar can overwhelm users. Keep it simple and uncluttered. Avoid overloading it with too many options and less vertical scrolling.

- **Role-based navigation**: Customize the navigation bar based on user roles. Users should see only the modules and features relevant to their roles. This enhances efficiency and reduces cognitive load.

- **Logical grouping**: Group related modules together. For example, sales-related modules like Leads, Opportunities, and Contacts can be grouped under a "Sales" Area. This logical grouping aids user understanding and navigation.

- **User-friendly labels**: Use clear and concise labels for modules and features. Avoid jargon or abbreviations that may confuse users. Labels should be easy to understand for all users.

- **Iconography**: Icons can be used alongside labels for visual recognition. Choose universally recognized icons or provide tooltips to explain their meaning.

- **Adaptive design**: Ensure that the navigation bar adapts to different screen sizes, including mobile devices. The menu should remain usable and accessible on smaller screens. This is by default available as part of the product – however you want to ensure that with all the added options, it shows the top priority items to the users in the right fashion.

- **Consistency across areas**: Maintain a consistent navigation structure across different modules. Users should have a similar experience when moving between different parts of the application.

- **User training and onboarding**: Provide training and onboarding materials to help users understand how to use the navigation bar effectively. Clear documentation and user guides can be invaluable.

- **Accessibility**: Ensure that navigation/sitemap is designed while keeping the accessibility aspect in mind. By default, it's navigable using keyboard and compatible with screen readers for users with disabilities, ensure the correct labels and

- **User feedback**: Gather feedback from users about the navigation bar's usability. Periodically review its effectiveness and make improvements based on user input.

- **Test with real users and supported devices**: Before finalizing the navigation bar design, conduct usability testing with actual users. This helps identify any usability issues and ensures that the navigation is intuitive.

- **Continuous improvement**: The navigation bar isn't a one-time design element. Continuously review and refine it based on user feedback and changing business needs.

Remember that the navigation bar is a critical element in user experience design for model-driven app. A well-designed navigation bar can significantly enhance user productivity and satisfaction while navigating the system.

The navigation bar can be customized by updating the site map. This can be done by adding it to a custom solution in your maker portal. There can be multiple site maps for various applications created in your system so ensure the correct sit emap for the application is selected before editing.

:::image type="content" source="media\ui-ux-component-details-1.svg" alt-text="Screenshot showing options populating from the Site Map option, including Edit, Object checker, Published, Advanced, and Delete from this environment." lightbox="media\ui-ux-component-details-1.svg":::

Learn more at [Create a model-driven app site map using the site map designer](/power-apps/maker/model-driven-apps/create-site-map-app) <!--about customizing your sitemap at [Customize SiteMaps (Developer Guide for Dynamics 365 Customer Engagement)](/dynamics365/customerengagement/on-premises/developer/customize-dev/customize-sitemaps)-->.

### Dashboards

Dashboards in model-driven apps allow users to visualize key data and metrics at a glance. They're essential for providing users with a personalized overview of their work and performance.

It's important to design dashboards that are tailored to the roles and responsibilities of users as they play a pivotal role in enhancing user experience by allowing users to quickly access and comprehend important information within the application.

Dashboards are highly customizable and enable users to create a personalized workspace where they can monitor their daily tasks, track progress, and make data-driven decisions. These dashboards are composed of various components such as charts, lists, and web resources, all of which can be arranged and configured according to individual preferences. In addition, Power BI reports can be embedded directly into dashboards and forms directly from the workspace.

The primary purpose of dashboards is to simplify complex data and present it in a comprehensible manner, helping users stay informed and efficient in their roles. Dashboards aren't just informative but also interactive, allowing users to drill down into details, access related records, and take actions directly from the dashboard.

Learn more from the following design considerations:

- **User-centric approach**: The design of dashboards should be user-centric, considering the specific roles and responsibilities of the audience. Understand the typical tasks and objectives of users within different departments, such as sales, marketing, customer service, or management, and tailor dashboards to their unique needs.

- **Relevant metrics**: Include only the most relevant metrics and data on each dashboard. Avoid clutter by focusing on the essential information that users need to make informed decisions. Keep in mind that less is often more when it comes to dashboard design.

- **Visual representation**: Utilize charts and visual elements to represent data effectively. Visualizations make it easier for users to grasp trends, patterns, and anomalies. Ensure that the chosen visualizations are appropriate for the type of data being displayed.

- **Personalization**: model-driven apps provide a selection of widgets to build dashboards. These widgets grant users the flexibility to build their dashboards according to their preferences when creating a layout. It's essential to ensure that when adding widgets to a dashboard, various widgets shouldn't be the representation of the same data in different format. Data widgets should complement other widgets, offering a holistic view of the business scenario. The tool empowers users to craft personalized data views tailored to their unique business requirements.

- **Data filtering and interactivity**: Default filtering and interactive features on dashboards empowers users to refine data according to specific criteria. These interactive elements enhance the user experience by allowing exploration of data from different angles with ease. To maximize the benefits of these features, it's crucial for users to have a clear understanding of how they work. Therefore, incorporating a guide on these aspects as part of user training is highly recommended. This ensures that users can make the most of the dashboard's capabilities and efficiently analyze data.

- **Important component prioritization on mobile devices**: Ensure that dashboards are responsive, prioritized, and optimized for mobile devices. In today's mobile workforce, users often access data on smartphones and tablets, so a mobile-friendly dashboard and interface design is crucial for accessibility.

- **Power BI dashboard integration**: Power BI dashboard integration can be enabled by using the feature flag in system settings. This allows users to connect to Power BI dashboards and directly access them from the app. Learn more about getting started with Power BI Dashboards integration with the following resources:

  - [Embed a Power BI report in a model-driven app main form - Power Apps](/power-apps/maker/model-driven-apps/embed-powerbi-report-in-system-form)

  - [Create or edit a Power BI embedded system dashboard - Power Apps](/power-apps/maker/model-driven-apps/create-edit-powerbi-embedded-page)

  - [Add or edit Power BI visualizations on your dashboard - Power Apps](/power-apps/user/add-powerbi-dashboards)

- **Feedback and iterative improvement**: Gather feedback from users on the effectiveness of dashboards. Monitor by applying various techniques such as filming or screen recording (if applicable) to learn user behavior. You can also learn how users interact with system dashboards and be prepared to iterate and improve their design based on user input.

Overall, effective dashboard design in model-driven app's is about delivering actionable insights in a visually appealing and user-friendly format. By considering user needs, data relevance, visual representation, and interactivity, you can create dashboards that empower users to maximize their productivity and make data-driven decisions within the system.

### Forms

Forms are where users enter and view data in the model-driven app. They play a central role in data management, and their design impacts the efficiency of data entry and retrieval. They provide a structured interface for users to input data, access historical records, and retrieve essential information about customers and their issues.

Take note of the following design considerations:

- **User-centric approach**: Start by understanding the needs and preferences of your users. Design forms that make it easy for users to input and retrieve information efficiently.

- **Keep it simple**: Avoid clutter and unnecessary complexity. Simplify the layout by only including essential fields and controls. Use tabs or sections to group related information logically.

- **Prioritize important information**: Place the most critical data at the top of the form, ensuring it's easily accessible without scrolling.

- **Consistency**: Maintain consistency in field labels, positioning, and styling across all forms within your Power Platform environment. This consistency enhances user familiarity and reduces cognitive load.

- **Responsive design**: By default, all forms model-driven forms are responsive. Ensure that your forms are still responsive and adapt well to different screen sizes and devices after performing customization of your form. Test how forms content look and function on both desktop and mobile devices after performing customization.

- **Customize for specific roles**: Tailor forms to match the specific roles of your users. Display fields and controls relevant to each user's responsibilities, hiding or disabling irrelevant ones. Forms can tie it to a security role to ensure relevant forms are visible to individual personas defined in the system.

- **Logical field ordering**: Arrange fields in a logical order that matches the sequence of tasks performed by users. For instance, start with contact details before moving to order information.

- **Use business rules**: Use business rules and conditional formatting to show or hide fields dynamically based on user input, reducing form complexity.

- **Validation rules**: Implement form level and field level validation rules to ensure data accuracy. Provide meaningful error messages when users input incorrect or incomplete data.

- **Avoid overloading**: Don't overload a single form with too many fields. Given the table's maximum field limits, be mindful of the number of fields you add to a table. This will greatly slow the progress of form loading and create bad use experience.

- **Use subgrids wisely**: Subgrids can display related records. Use them when needed but avoid overwhelming users with excessive subgrids on a single form. In addition, it's better to move some of the grids to other dedicated tabs based on the logical design and priority of the information.

- **Consider localization**: If your organization operates in multiple regions, ensure that it provides localizations for labels and messages and that UI is adaptable to different languages and cultural preferences. In general, this also applies to model-driven apps and canvas app in general.

- **Regular review**: Periodically review your forms to assess their effectiveness and user feedback. Make necessary adjustments to improve the user experience.

- **Security**: Implement proper security roles and permissions to control access to forms and data. Ensure that sensitive information is only visible to authorized users. You can logically group these fields to ensure that it provides consistent user experience. You can set up various scenarios with row-level permission and field-level permissions. Learn more about permissions for model-driven apps with the following overviews:

  - **Row-level permissions** control access to individual records or rows in Dataverse tables. They specify which users or teams can see and interact with specific records. This requires a good understanding of the security model available in Power Platform. Learn more with the following resources:

    - [Security concepts in Microsoft Dataverse - Power Platform](/power-platform/admin/wp-security-cds)
    - [Hierarchy security - Power Platform](/power-platform/admin/hierarchy-security)
    - [Mask sensitive data and fields using column-level security](/power-platform/release-plan/2024wave1/data-platform/mask-sensitive-data-fields-using-column-level-security#business-value)

    - **Use cases**: You can ensure that sales representatives can only access customer records assigned to them, or HR personnel can only view employee records for their department. This can be achieved in various ways by defining multiple security roles on same table in combination with level of access such as user, business unit, parent child business unit, and organization settings available within the security role.

    - **Integration with forms**: Row-level permissions are closely integrated with model-driven apps forms. When a user opens a form, API call is made to the associated record, Dataverse checks their permissions to determine whether they can view or edit that record. If they lack the necessary permissions, they aren't able to access the record through the form.

    - **Impact on forms**: Row-level permissions directly impact which records appear in subgrids on forms. Users will only see the records they have permission to access when selecting related records. Learn more at [Use record-based security to control access to records](/dynamics365/customerengagement/on-premises/developer/security-dev/use-record-based-security-control-access-records).

  - **Field-Level permissions** control who can view and edit specific fields within a record. They enable fine-grained control over which users or teams can access certain data fields.

    - **Use cases**: Field-level permissions are used to restrict access to sensitive or confidential information. For instance, you can limit access to salary information in employee records to HR managers only.

    - **Integration with forms**: Field-level permissions are also closely tied to forms via API. Users with appropriate permission can see and edit specific fields on the form, while those without the necessary permission don't have access to those fields.

    - **Impact on forms**: Field-level permissions don't affect the appearance of the forms. Users without permissions for certain field's data see those fields. However, data is masked as set in the field level security profile. In addition, field level security has impact on performance. As such, it's advisable to limit the use based on priority and data criticality for business.

    Learn more at [Field level security](/dynamics365/customerengagement/on-premises/admin/field-level-security)

- **Performance**: Pay attention to form load times, this can be monitored via the Application Insights telemetry for model-driven Apps, as outlined in [Telemetry events for model-driven apps](/power-platform/admin/telemetry-events-model-driven-apps). Excessive customization can slow down form loading and degrade UX therefore all forms should be optimized for performance. Although the purpose of this article isn't to cover performance in detail, however, we'll touch upon some of the important aspects while designing the app. Optimizing form load time in model-driven apps involves a combination of design and script best practices to ensure that your forms load quickly and provide smooth user experience. Here are some steps and recommendations to help you achieve this:

- **Keep forms simple and focused**: Limit the number of fields and controls on your forms to only what's necessary for the user's workflow. Excessive fields can slow down form loading including hidden fields on the form.

- **Use of quick view forms**: Quick View Forms can add overhead to form loading, especially if they contain a lot of data. Use them judiciously.

- **Optimize JavaScript code**: Review and optimize any JavaScript code used for form customizations. Inefficient code can significantly impact form load times. Avoid long-running scripts and consider asynchronous loading when possible.

- **Minimize web resources**: Use web resources (HTML, JavaScript, CSS) judiciously. Minimize their use if they aren't critical for the form's functionality. Compress and optimize web resource files for faster loading.

- **Adhere to your organization best practice guidelines**: Define rules for your organization and best practices for Dev team. This also includes following Form Load/Save rules to load and persist data asynchronously, prioritizing critical data over nonessential information.

- **Streamline sections**: Organize fields logically in sections. Prioritizing frequently used sections can help in providing better user experience.

- **Limit the number of subgrids and IFrames**: Each subgrid or IFrame adds to the overall experience. Evaluate their necessity and consider alternative ways to present the data.

- **Monitor and optimize plugins**: If you use plugins in your environment, ensure they're well-optimized and not causing bottlenecks.

- **Test cross-browser and cross-device**: Ensure that your forms perform well on different web browsers and devices. Test on popular browsers like Chrome, Firefox, Microsoft Edge, and mobile devices to identify any performance disparities.

Refer to the following scripting best practices:

- **Efficient use of JavaScript**: Don't perform DOM manipulation and prefer APIs for any UI changes. Learn more at [Interact with HTTP and HTTPS resources asynchronously - Power Apps](/power-apps/developer/model-driven-apps/best-practices/business-logic/interact-http-https-resources-asynchronously).

**Lazy loading of data**: Load data only when they're needed and use asynchronous web requests. Learn more at [Turbocharge your model-driven apps by transitioning away from synchronous requests](https://powerapps.microsoft.com/blog/turbocharge-your-model-driven-apps-by-transitioning-away-from-synchronous-requests/).

- **Reduce server-side calls**: Minimize the use of real-time data retrieval methods like OData or FetchXML.. Utilize Web API efficiently – batch requests and use filters to limit data retrieval.

- **Event optimization**: Carefully evaluate event handlers, especially `OnLoad` and `OnChange`. Minimize or remove where it's not essential. Use business rules to apply native capability. Learn more with the following resources:

  - [Create a business rule in Microsoft Dataverse - Power Apps](/power-apps/maker/data-platform/data-platform-create-business-rule)
  - [Form OnLoad event (Client API reference) in model-driven apps - Power Apps](/power-apps/developer/model-driven-apps/clientapi/reference/events/form-onload#asynchronous-onload-event-handler-support)
  - [Developers: Best practices and guidance for client-side scripting for model-driven apps - Power Apps](/power-apps/developer/model-driven-apps/best-practices/business-logic/)

- **Optimize business rules and workflows**: Use business rules and power automate where applicable. Ensure server-side workflows and plugins are optimized and only triggered when necessary.

- **Code review and profiling**: Regularly review and refactor JavaScript code. Use profiling tools to identify performance bottlenecks in scripts.

- **Mobile optimization**: For mobile clients, ensure only the correct set of fields are visible on the compact devices.

- **Regularly review and refactor**: Periodically review your form designs and associated customizations. Refactor or remove any components that are no longer necessary or causing performance issues.

- **Test latest release wave before PROD rollout**: Ensure to test new release wave on your test environment before making updates to PROD.

### Views and grids

In model-driven apps, views and grids are used to present data records related to customer interactions, service requests, cases, and more. They provide users with the means to browse through large datasets, filter records based on specific criteria, and access the information they need swiftly.

Refer to the following design considerations:

- **Readability and navigability**: Ensure that view or grid layouts prioritize readability. Use sufficient spacing between columns. Avoid overcrowding the grid with too much data. Make sure the first column has important information that users can act on. Clicking on the record should bring users to the right record details.

- **Column customization in saved views**: Users can customize column layouts to tailor the view to their specific needs. They can select which columns to display and in what order. This flexibility empowers users to focus on the most relevant information. For example, in a contact list personal view, users can customize columns to display the contact's name, email, phone number, and last interaction date, hiding less relevant fields like the mailing address. They can then save the view as personal view to and bookmark it to show as default view when they navigate to the table. By showing pertinent data fields, it can minimize cognitive overload for users and ensure that they can quickly identify and work with the records they require.

- **Sorting options**: Implement default sorting on system views to arrange data in ascending or descending order based on specific columns directed by the business need. Sorting helps users quickly find the data they need and identify trends. For example, in a sales opportunity list, users can choose the "Amount" column header to sort opportunities from the highest to lowest value.

- **Filtering capabilities**: Filtering options are available by default to help users refine data based on specific criteria. Filters allow users to narrow down records, reducing clutter and focusing on what's relevant. For example, in the case of customer support cases, users can apply a filter to display only open cases assigned to them.

- **Saved views**: Allow users to save their custom views for easy access. This feature enables users to create and save frequently used filters and column layouts, streamlining their daily workflows.

- **Sharing views**: Use view sharing options to enhance collaboration. Users should use the feature to share custom views with team, or individual members, ensuring consistent access to essential datasets across the organization.

- **Performance optimization**: Be mindful of performance when designing views, especially if dealing with large datasets. Ensure that views are optimized to load quickly, even when dealing with substantial data volumes. Adding lookups in views in can potentially impact performance, especially when dealing with large datasets. Here are some considerations and potential performance issues to be aware of when adding lookups to views:

  - **Data retrieval overhead**: Including lookup fields in views often requires retrieving more data from related tables. This can increase the volume of data retrieved and affect query performance.

  - **Join operations**: When lookups are added to views, the underlying SQL queries may involve join operations to retrieve related data. Joins can be resource-intensive and slow down query execution.

  - **Complexity**: As the number of lookups in a view increases, the complexity of the query grows. Complex queries can be slower to execute, especially when querying large datasets.

- **Responsive design**: Test and ensure that grids and views are responsive and adapt well to various screen sizes and orientations. Users should have consistent experience on both desktop and mobile devices. For example, A grid displaying customer orders should stack columns vertically on smaller screens to maintain readability.

- **Accessibility**: Test to ensure that grids and tables are accessible to all users, including those with disabilities. For example, test keyboard shortcuts for column sorting and filtering to assist users with mobility impairments.

- **User Training**: Provide training and guidance on using views effectively. Educate users on how to apply filters, sort records, and utilize Advanced Find to locate specific data. Effective training enhances user proficiency.

### Ribbon and command bar

The ribbon and command bar contain a set of contextual commands and actions that users can perform within specific tables and forms.

Refer to the following design considerations:

- **Quick access to frequent actions**: Customize the ribbon and command bar to prioritize quick access to frequently used actions. Identify the most common tasks that users perform within specific tables and ensure that these actions are readily available without unnecessary choices or navigation.

- **Logical grouping**: Group related commands logically within the ribbon and command bar. Commands should be organized in a way that makes sense to users, facilitating a natural flow of tasks. For instance, group actions related to case management under a "Case" tab.

- **Customization**: Implement customization of the ribbon and command bar. Different users or teams within your organization may have distinct roles and responsibilities. Customize these UI elements to align with the specific needs of different user roles, ensuring that each user sees only the commands relevant to their tasks.

- **Conditional visibility**: Utilize conditional visibility rules to show or hide commands based on specific criteria. For example, certain actions may be relevant only when a record is in a particular status or has specific attributes. Display commands contextually to reduce clutter and improve user experience.

- **Accessibility**: test and ensure that the ribbon and command bar are accessible to all users, including those with disabilities. Evaluate your customizations while considering keyboard navigation, screen reader compatibility, and adherence to accessibility standards.

- **Feedback mechanisms**: Incorporate feedback mechanisms within the ribbon and command bar. For instance, include tooltips or help text to provide users with additional information about each command. This helps users understand the purpose and functionality of each action.

- **User training**: Provide user training on how to use the ribbon and command bar effectively. Ensure that users understand the available commands and their significance within different contexts. Effective training enhances user proficiency and adoption.

Learn more about the command bar and ribbon with the following resources:

- [Customize the command bar - Power Apps](/power-apps/maker/model-driven-apps/use-command-designer)
- [Customize commands and the ribbon (model-driven apps) - Power Apps](/power-apps/developer/model-driven-apps/customize-commands-ribbon)
- [Ribbons available in model-driven apps - Power Apps](/power-apps/developer/model-driven-apps/ribbons-available)

### Charts and visualizations

Charts and visualizations are powerful tools in Power Apps, for presenting data in a visual and easily understandable format. They enable users to gain insights, identify trends, and make informed decisions based on the information presented.

Here, we delve into the significance of charts and visualizations and the design considerations associated with them:

- **Understanding data trends**: Charts and visualizations offer a visual representation of data, making it easier for users to comprehend complex information. They transform raw data into visual patterns, helping users identify trends, correlations, and anomalies more quickly than inspecting rows of numbers.

**Data-driven decision-making**: Charts and visualizations play a crucial role in data-driven decision-making. They empower users to make informed choices, prioritize tasks, and take actions based on data insights. For example, sales teams can analyze revenue trends, and support teams can monitor case resolution times.

- **Visual appeal**: Create visually appealing charts and visualizations that capture users' attention. Choose the appropriate widgets to make data visually engaging without overwhelming the viewer.

- **Customization**: Customize charts to match your organization's branding and preferences. Tailor chart types (for example, bar, line, pie) to convey specific meanings.

- **Clarity**: Ensure that your charts are clear and easy to interpret. Use clear labels, legends, and annotations to provide context and guide users in understanding the data. Avoid cluttered or overly complex visuals.

- **Data accuracy**: Charts should accurately represent the underlying data. Double-check data sources to prevent misinterpretation or inaccuracies in the visualizations.

- **Responsive design**: If your system is accessible on various devices, design charts to be responsive and effective in user context. Ensure that charts adapt to different screen sizes and orientations without losing their effectiveness.

- **Data drill-down**: Ensure the ability to drill down into charts for more detailed information is complying with the user experience. For instance, clicking on a data point in a chart could open a related record or a detailed report doesn't distort the user experience.

- **Consistency**: Maintain a consistent style and design language across your charts and visualizations within the system. This consistency helps users quickly understand and navigate different reports and dashboards.

- **User training**: Provide training to users on how to interpret and utilize charts effectively. Ensure that they understand the meanings of various chart types and visual cues.

### Business process flows

In model-driven apps, business process flows guide users through predefined workflows or processes, ensuring that they follow consistent and structured steps when entering data or completing tasks. Business process flows consist of stages and steps, where each stage represents a phase in a process, and each step corresponds to an action or data entry task. Keep in mind that BPFs are specific to screens providing guidance to the users. Making calls through API is independent from UI experience.

For example, suppose you're designing a sales process in model-driven app. Your business process flow could include stages such as *Lead Generation*, *Qualification*, *Proposal*, and *Closing. Within each stage, you define steps that guide users on what actions to take, such as *Create Lead*, *Qualify Lead*, *Generate Proposal*, and *Close Deal*.

In model-driven apps, the following factors should be considered.

- **Number of stages**: Business process flows (BPFs) are capped at a maximum of 30 stages. This limitation serves a crucial purpose - maintaining the manageability of BPFs and prevents them from becoming overly complex. However, it's not just about adhering to this limit; it's also a best practice to keep your BPFs as straightforward as possible. By doing so, you ensure a more streamlined and user-friendly experience for your users. Complexity can lead to confusion, so simplicity should always be a guiding principle when designing BPFs.

- **Number of steps**: Each stage within a BPF can contain multiple steps. There's no strict limit to the number of steps within a stage, but it's essential to strike a balance between providing detailed guidance and not overwhelming users.

- **Table relationships**: BPFs can be associated with specific tables, meaning that they guide users through processes related to those tables (for example, leads, opportunities, cases). Ensure that your BPF is associated with the appropriate table for seamless integration with your business processes.

- **BPF and Power Automate**: By integrating Power Automate, we can streamline processes in the background, allowing users to focus on key elements without compromising user experience or introducing unnecessary steps. This automation can handle various tasks on the user's behalf, ensuring efficiency and enhancing productivity.

- **Conditional branching**: Conditional branching is allowed in BPFs. This means you can design BPFs to dynamically change paths based on user inputs or conditions, ensuring that users are directed at the most relevant steps.

- **User roles and security**: Configure BPFs to align with user roles and security settings. You can control which users or teams have access to specific BPFs, ensuring that the process guidance is relevant to their roles.

By understanding these technical details and applying the design principles mentioned earlier, you can create BPFs within model-driven apps that optimize user interactions, enhance productivity, and contribute to a seamless user experience. These components serve as a foundation for crafting a user-centric system tailored to your organization's specific needs.

## Related resources

- [UI/UX component details for tests and user feedback](ui-ux-component-details-testing-feedback.md)  
- [UI/UX component details for canvas apps](ui-ux-component-details-canvas-apps.md)  
- [Key UI/UX design principles](ui-ux-design-principles.md)  
- [Introduction to UI/UX design for Dynamics 365 customer engagement apps](introduction-customer-engagement-ui-ux-design-guide.md)  