---
title: UI/UX guidance for Dynamics 365 Sales
description: Discover how to design Dynamics 365 Sales apps for maximum adoption success and avoid common UX pitfalls.
ms.date: 03/05/2025
ms.topic: best-practice
contributors: kpetire
author: edupont04
ms.author: edupont
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-description
  - ai-seo-date:03/05/2025
# customerIntent: As an implementation partner, I want to know the best practices for customizing Dynamics 365 Sales forms to enhance user adoption.
---

# UI/UX guidance for implementations with Dynamics 365 Sales

This document helps implementation partners design their app experience for Dynamics 365 Sales to maximize adoption success, avoid common mistakes, and ensure future capability adoption. Many adoption challenges boil down to the user experience and overcomplicated applications. Problems can include cluttered or messy forms, forms and views not relevant to the seller, and users spending too much time searching for the information they need.

In this document, we list several considerations for sales scenarios with recommendations and advice. Find guidance for the five most common user profiles at [Sales personas to include in UI/UX design for implementations with Dynamics 365 Sales](ui-ux-guidance-sales-personas.md).  

## Sales Hub versus custom apps

Organizations that build a solution with Sales often face the question about building the solution in the existing Sales Hub app or building separate apps for different personas. We recommend that you start by considering building in Sales Hub. This preinstalled app module is tailored for Sales scenarios, and it's the best starting point for any sales personas you intend to equip with a new app for sales. It makes it easier for users to adopt new features that Microsoft adds to the app automatically without further customization required and take advantage of advanced capabilities automatically.  

Learn more at [Sales Hub app versus custom app](/dynamics365/sales/saleshub-customapp).

## Data model

Dynamics 365 Sales provides a rich and extensible data model built on top of the Common Data Model in Dataverse. Makers with an industry standard, Sales tailored, data model can jump start their development along with a feature rich application, Sales Hub, designed to meet most customer needs with minimal customization. This means that there are tables in the app that any implementation should use to help make sure that the final solution uses the continued improvements to current capabilities and new capabilities that become available at a regular pace. The following list shows the key core tables to Dynamics 365 Sales:

- **Contact**  
- **Opportunity**  
- **Lead**  
- **Account**  

We highly recommend that you use these tables in your designs and don't create custom tables with a similar purpose.  

Learn more at [Common Data Model](/common-data-model/).

## UI/UX for model-driven apps

Dynamics 365 Sales is a model-driven application, built on Power Platform. We recommend that you review and apply the key principles of [UI/UX design for model-driven applications](ui-ux-component-details-model-driven-apps.md) to your designs and customization of Dynamics 365 Sales.  

If you customize the default forms for sellers, prioritize simplicity and efficiency to ensure high adoption rates. Sellers often view data entry as a time-consuming task that detracts from their primary goal of selling. Therefore, it's essential to keep forms as simple as possible, minimizing data maintenance to avoid overwhelming the sellers with unnecessary fields. This means careful consideration about adding extra fields based on managerial reporting needs, as these can clutter the interface and reduce usability. It's a best practice to start designs using the out of the box forms and adding custom forms when role-based forms are required. This approach has the advantage of quickly adopting new features via the provided admin switches rather than having more customization of new custom forms to include new capability.  

> [!TIP]
> Always keep in mind how the seller adopts the application; the design should focus on enhancing their workflow and making their tasks easier.  

Unlike customer service agents who rely heavily on CRM systems for detailed customer interactions, sellers can often get their job done without extensive CRM input, relying more on direct customer engagement and relationship-building. Thus, the customization for sellers should be more streamlined and user-friendly, emphasizing the importance of simplicity and relevance in their daily tasks.

Learn more at [UI/UX design components for Power Apps model-driven apps](ui-ux-component-details-model-driven-apps.md).  

## Reporting and dashboards

Reports and dashboards are essential tools for visualizing and analyzing sales data in Dynamics 365. They can help sales managers and reps to monitor performance, identify trends, and discover insights that can improve decision-making and customer satisfaction. When you start such a discussion with sellers, remember that many sellers just require an overview of their pipelines with the ability to quickly update data or take key actions. They rarely ask for extensive dashboards and reports, and they also rarely need to navigate to forms or views to make edits. During design discussions with sellers, consider starting with the *Pipeline View* for actor-level insights and pipeline management.  

Learn more at [Configure the opportunity pipeline view](/dynamics365/sales/opportunity-pipeline-view-for-admins#set-the-pipeline-view-as-the-default-opportunities-view) and [Manage opportunities using pipeline view](/dynamics365/sales/use-opportunity-pipeline-view).  

Other considerations should be given to providing common system views and charts and training users on using the advance filtering capabilities available on all grids reducing their need to go to reports to gain access to the data they need.  

Learn more in the following articles:

- [Create and manage personal views on a grid page - Power Apps](/power-apps/user/grid-filters-advanced)  
- [View data with visualizations (charts) (model-driven apps) - Power Apps](/power-apps/developer/model-driven-apps/view-data-with-visualizations-charts)  

If more insights are needed, creating effective reports and dashboards requires careful attention to the design and usability aspects of the user interface (UI) and user experience (UX).  

Here are some best practices to follow when designing reports and dashboards in Dynamics 365 Sales: 

- **Define the purpose and audience of the report or dashboard**  

  Before you start building a report or dashboard, you should have a clear idea of what problem or question you're trying to solve or answer, who will use the report or dashboard, and what actions or outcomes you expect from them. This helps you to choose the right data sources, metrics, filters, and layout for your report or dashboard.

- **Use the right chart type for your data**  

  Charts are powerful ways to visualize data, but not all charts are suitable for all types of data. You should choose a chart type that matches the nature and complexity of your data, and the message you want to convey. For example, use pie charts to show proportions, bar charts to compare categories, line charts to show trends, and scatter plots to show correlations. Avoid using too many chart types in one report or dashboard, as this can confuse or overwhelm the users.

- **Simplify and prioritize your data**  

  Reports and dashboards should provide clear and concise information that users can easily understand and act upon. You should avoid cluttering your reports and dashboards with too much data, unnecessary details, or redundant information. Instead, you should focus on the most relevant and important data, and use filters, drill-downs, or interactive features to allow users to access more details if needed. You should also arrange your data in a logical and consistent order, and use labels, legends, titles, and tooltips to explain your data clearly.

- **Apply consistent and appealing aesthetics**  

  The appearance and style of your reports and dashboards can affect the users' perception and engagement with your data. You should apply consistent and appealing colors, fonts, sizes, and shapes to your reports and dashboards, and follow the branding and theme guidelines of your organization. Use white space, grids, and alignment to create a balanced and organized layout. You should also use contrast, highlights, and icons to draw attention to key data points or actions.

- **Test and refine your reports and dashboards**  

  Before you publish or share your reports and dashboards, test them with real data and real users. Collect their feedback on functionality, accuracy, and usability. You should also monitor the usage and performance of your reports and dashboards, and update them regularly to reflect changes in data, business goals, or user needs.

Learn more in the following articles:  

- [Create and configure model-driven app interactive experience dashboards in Power Apps - Power Apps](/power-apps/maker/model-driven-apps/configure-interactive-experience-dashboards?context=%2Fdynamics365%2Fcontext%2Fsales-context)  
- [Analyze your sales data with Power BI](/dynamics365/sales/introduction-sales-template-apps)  

## Copilot in Dynamics 365 Sales

Copilot in Dynamics 365 Sales is a seller companion app infused with AI-powered capabilities, which can help sellers unlock productivity and up-level their skills. It integrates with Dynamics 365 Sales and also Outlook and Teams, bringing customer engagement data into the seller's workflow. This allows sellers to be more efficient and productive, as they can access the information that they need without having to switch context.  

By being available across the apps that sellers use the most, Copilot in Dynamics 365 Sales brings benefits to sellers that primarily work in the Dynamics 365 Sales app, analyzing forecast data and opportunity data. Copilot can also help sellers that spend most of their time meeting and communicating with customers in Microsoft Teams and Outlook.  

The AI-powered capabilities of Copilot in Dynamics 365 Sales can greatly benefit sellers by providing insights, recommendations, and automation right in their flow of work:

- Copilot can help sellers stay on top of their sales records by summarizing any changes that were made to their leads, opportunities, and accounts. Instead of asking users to consult the audit or implement customizations on the sales record form, this information is readily available via the Copilot side tab ensuring the users don't have to navigate between multiple tabs to get caught up with changes.  

- Copilot can help sellers to compose professional-looking emails, summarize email conversations to add to the customer notes, and give reminders to follow up on emails.  

- Copilot can help to stay current with the latest news about customers. News updates can be great conversation starters and help understand the dynamics of your customers' organizations.  

All sales implementations should consider adopting Copilot as it provides organizations with a competitive advantage by optimizing sales processes, improving customer relationships, and staying ahead in terms of innovation and efficiency. It's important to understand that to achieve these benefits user adoption is key as users expect the Copilot to help them save time, make them better at their job, and provide accurate quality output. Ensure that there's a smooth onboarding process so that users understand what Copilot can do for them. Include clear guidance and support of how to use Copilot in your business processes.  

## AI-ready design for Copilot for Sales

For your Dynamics 365 Sales projects, review the considerations in the following table for a solution ready to adopt Copilot for Sales.  

| Considerations  | Details  |
|-------------------------|-------------------------|
| [Licensing](/microsoft-sales-copilot/license-info) | Minimum Microsoft 365 E3 + Minimum Dynamics 365 Sales Enterprise + Copilot for Sales license for full set of features. If using with Dynamics 365 Sales enterprise license, only a subset of the features are available – see the comparison[here](/microsoft-sales-copilot/sales-copilot-faq#when-is-copilot-for-sales-available-for-purchase). |
| [Server-Side Synchronization (SSS)](/microsoft-sales-copilot/use-server-side-sync#mailbox-configuration-for-saving-outlook-activities-to-dynamics-365)  | SSS is required for Copilot for Sales tracking Outlook activities to Dynamics 365 app. |
| [Data model](/microsoft-sales-copilot/customize-forms-and-fields)  | While there's support for configuration and enhancing Copilot for Sales with custom tables, the core functionality does rely on the core tables **Contact**, **Opportunity**, **Lead**, **Account (COLA)** and **Activity (Email, Appointment)**. Therefore, try to adopt COLA tables as per your scenarios and avoid schema deviations. Try to avoid custom activity table, and use the appointment table. As a minimum contact table should be used. |
| **Data quality**  | Is the data in Dynamics 365 consistent and of good quality? To assess this, consider if the users are persisting their customers, activities, and deals in Dynamics (either via Copilot for Sales UI, Dynamics UI in browser or mobile or other integrations) and if there are mechanisms in place to ensure data quality and prevent duplicates for example, [duplicate lead detection](/dynamics365/sales/enable-duplicate-lead-detection) |
| [Security model](/microsoft-sales-copilot/install-viva-sales#additional-privileges-required-for-dynamics-365-customers)  | Copilot for Sales works in the context of the current user and their Dynamics Sales security permissions are honored. <br /></br>If you use custom security roles, these should include access to the necessary tables, fields, and operations. These privileges are included out of the box in Salesperson and Sales manager security roles. |
| **Automation and integration**  | Any server-side customizations implemented are triggered by Copilot for Sales operations such as create and update. As such, do consider the flows, plugins, integrations triggered by Copilot for Sales initiated events and the potential impact these might have. For example, triggering a long running sync plugin on contact create or opportunity update might dissuade users from tracking data to CRM in general. <br /><br />Consider approval processes which might be in scope of record creation such as contacts or accounts and how would those impact Copilot for Sales experience. <br /><br />Client-side customizations such as business rules, JavaScript aren't currently supported in Copilot for Sales. Do consider if these are required for creating or updating objects – if yes, users can be redirected to Dynamics for those operations. However, there are client-side rules such as making fields required or read-only only in Copilot for Sales that could be sufficient. |

For your Dynamics 365 Sales projects, review the considerations in the following table for a solution ready to adopt Copilot in Dynamics 365 Sales.  

| Considerations  | Details  |
|-------------------------|-------------------------|
| **Licensing** | Minimum Dynamics 365 Sales Enterprise  |
| [Data model](/dynamics365/sales/copilot-configure-summary-fields)  | While there's support for configuration and enhancing Copilot in Dynamics Sales with custom fields for summarization feature, the core functionality does rely on the core tables **Contact**, **Opportunity**, **Lead**, **Account (COLA)** and **Activity (Email, Appointment, Phone Call, Task)**. Therefore, try to adopt COLA tables as per your scenarios and avoid schema deviations. Try to avoid custom activity table and use the appointment table. |
| **Data quality**  | Is the data in Dynamics 365 consistent and of good quality? To assess this question, consider if the users are persisting their customers, activities, and deals in Dynamics 365. Also consider if there are mechanisms in place to ensure data quality and prevent duplicates. |
| **Security model**  | Copilot in Dynamics 365 Sales works in the context of the current user and their security permissions are honored. The **OOB owner** field is used to define record ownership. The ownership is is relevant for some of the prompts, such as `show my pipeline`. If you use custom ownership fields, then evaluate the [glossary](/dynamics365/sales/enable-setup-copilot#train-copilot-to-understand-your-business-terms-preview) feature. |
| **[App Strategy](/dynamics365/sales/enable-setup-copilot)**  | If the solution uses custom apps: </br><ul><li>Has Copilot been enabled for this app?<li>Has the [immersive experience](/dynamics365/sales/enable-setup-copilot#add-the-copilot-page-site-map-entry-to-custom-sales-app)custom page been added to the app site map? </li></ul></br>If the solution uses custom opportunity forms: </br><ul><li>Has the [opportunity summary widget](/dynamics365/sales/copilot-configure-summary-fields#add-the-opportunity-summary-widget-to-custom-forms) been added to this form?</li></ul> |
| **[Auditing](/dynamics365/sales/copilot-ask-questions#get-recent-changes)**  | Has audit been enabled for lead and opportunity tables and do the users have [access to the audit history](/dynamics365/sales/copilot-configure-summary-fields#grant-audit-access-to-your-sellers)? This is necessary for the Recent changes feature.  |

Consider extending Copilot to provide more value to sellers. For example, enrich the summaries and information that's available through Copilot with more information from other systems, and documentation that helps users be more productive.  

Learn more at [Copilot in Dynamics 365 Sales overview](/dynamics365/sales/copilot-overview).  

## Related content

- [UI/UX components for Sales-specific experiences](ui-ux-guidance-sales-components.md)  
- [Sales personas to include in UI/UX design](ui-ux-guidance-sales-personas.md)  
- [UI/UX Design for Dynamics 365](introduction-customer-engagement-ui-ux-design-guide.md)  
- [UI/UX design components for Power Apps model-driven apps](ui-ux-component-details-model-driven-apps.md)  
- [Who knows whom in Dynamics 365 Sales](/dynamics365/sales/who-knows-whom)  
- [Overview of Relationship intelligence](/dynamics365/sales/ri-overview)  
- [Relationship analytics and KPIs overview](/dynamics365/sales/relationship-analytics-overview)  
- [Understand the up next widget on records](/dynamics365/sales/understand-the-up-next-widget)  
- [Configure forecasts in your organization](/dynamics365/sales/configure-forecast#how-does-forecasting-help-organizations)  
- [Understand organization charts](/dynamics365/sales/organization-charts)  
- [View and manage records in focused view](/dynamics365/sales/focused-view)  
- [What is sales accelerator?](/dynamics365/sales/sales-accelerator-intro)  
- [Manage opportunities using pipeline view](/dynamics365/sales/use-opportunity-pipeline-view)  
- [Sales Hub app versus custom app](/dynamics365/sales/saleshub-customapp)  
- [Configure the opportunity pipeline view](/dynamics365/sales/opportunity-pipeline-view-for-admins#set-the-pipeline-view-as-the-default-opportunities-view)  
- [Manage opportunities using pipeline view](/dynamics365/sales/use-opportunity-pipeline-view)  
- [Create and manage personal views on a grid page - Power Apps](/power-apps/user/grid-filters-advanced)  
- [View data with visualizations (charts) (model-driven apps) - Power Apps](/power-apps/developer/model-driven-apps/view-data-with-visualizations-charts)  
