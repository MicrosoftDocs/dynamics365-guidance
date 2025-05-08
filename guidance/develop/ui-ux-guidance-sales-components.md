---
title: UI/UX components for Sales-specific experiences
description: Get an overview of UI/UX components for Dynamics 365 Sales to enhance your sales app design.
ms.date: 03/05/2025
ms.topic: concept-article
contributors: kpetire
author: edupont04
ms.author: edupont
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-description
  - ai-seo-date:03/05/2025
# customerIntent: As an implementation partner, I want to know the UI/UX components that I can use to design a good experience as part of our customization of Dynamics 365 Sales.
---

# UI/UX components for Sales-specific experiences

In Dynamics 365 Sales, several experiences tailored for sales are prebuilt to give customers a head start when designing their sales apps. They're also designed to accelerate sales engagement and improved by feedback from many customers. So before building custom pages or components, evaluate the OOB controls – these are configurable so you can tailor the UI to the specific needs of your sellers.

> [!TIP]
> Get an overview and general guidance at [UI/UX guidance for implementations with Dynamics 365 Sales](ui-ux-guidance-sales-implementations.md). Find a description of user profiles at [Sales personas to include in UI/UX design for implementations with Dynamics 365 Sales](ui-ux-guidance-sales-personas.md).

## Pipeline view

*Pipeline view* in Dynamics 365 Sales helps the seller to visualize the entire sales pipeline while allowing them to manage it. It contains charts that assist the seller to visualize the sales pipeline and prioritize the most impactful deal, or the deal that is closest to completion.  

With pipeline view, the seller can simply select an opportunity in the chart to update key information, add notes, or create tasks. This improves seller efficiency by avoiding unnecessary navigation and lost context.  

KPIs in Pipeline View helps the seller understand the sales pipeline on aggregate level such as how many opportunities, total value of the pipeline, average deal size, and so on. The metrics can be adjusted to the sellers' needs ensuring the right view of KPIs you want the seller to track.  

The pipeline view experience can also be personalized to fit the sales scenarios better. Many personalization options are available to the seller in the workspace and the system administrator can also influence what the pipeline view includes and shows.  

Sellers always ask for great sales dashboards, simplicity in opportunity updates, and a way to manage opportunities while staying in the context of the sales pipeline. Pipeline view combines both great visualization of the sales pipeline with the ability to update opportunities, making it a tailored workspace for the seller.  

The recommendation is for any new sales implementation project to test, assess, and consider Pipeline View as part of requirement grooming.  

Learn more at [Manage opportunities using pipeline view](/dynamics365/sales/use-opportunity-pipeline-view).  

## Sales Accelerator

The *Sales Accelerator* provides a tailored experience for high-velocity selling to enable users to spend more time identifying the best customers to target from their prioritized work lists. It gathers information from multiples sources helping them to sell smartly by building a strong and prioritized pipeline, offering data driven context, and surfacing AI-generated insights. These recommendations are based on customer events and needs throughout a sales sequence that helps to speed up the sales process by providing the user the ability to view and manage accounts, contacts, leads, opportunities, quotes, and even custom records and their associated activities on one page. This user centric design makes it easier for the user to stay focused on their task and be more productive by bringing relevant information to the user so they spend less time navigating through multiple screens to achieve the desired business outcomes, moving quickly from one customer to another. 

Do use the Sales Accelerator to assist sellers with the next best actions to be productive in their jobs and focus on selling. You can configure multiple sets of actions or sequences as per your company's specific sales processes, such as based on location, product, or any custom conditions. 

Do use Sales Accelerator for sales managers to assign most efficiently leads and opportunities.  

Learn more at [Understand what is sales accelerator](/dynamics365/sales/sales-accelerator-intro).  

## Focus view

Focused View is a lightweight version of Sales Accelerator providing a view of a single table whereas Sales Accelerator can provide a prioritized list of actions across tables. Sellers can use the search, filters, and sorting to quickly focus on the records they want to view and the worklist card can be customized to ensure the right information is displayed for sellers to prioritize work.  

Do use the focus view when your sales users need to work through most efficiently to advance or complete sales activities related to OOB or custom entities. The activities available to sellers can be both manually created and generated from sales sequences.  

Learn more [View and manage records in focused view](/dynamics365/sales/focused-view).

## Stakeholder map

Organization charts help visualize the hierarchy and relationships between departments and roles in a customer organization or buying room. You can better understand the decision-making process and identify the individuals who hold the most influence over purchasing decisions. With this information, you can tailor your sales approach to your customer's specific needs and preferences, resulting in better outcomes for both you and your customer. 

Do use Stakeholder map for sellers and sales managers to build an organization chart with ease and precision with simple drag-and-drop actions. 

Learn more at [Understand organization charts](/dynamics365/sales/organization-charts).  

## Forecasting

With the forecasting feature, sellers can assess the health of their pipeline and progress versus their target. Predictive forecasting helps sellers and managers improve their forecast accuracy by providing forecast projections based on historical data.

Forecasting features in Dynamics 365 Sales can help you create accurate and flexible sales forecasts based on revenue or quantity. Some of the advantages of using these features are: 

- You can choose from different templates to suit your organization's needs, such as org chart, product, or territory forecasting.  
- You can configure the forecast hierarchy, access permissions, columns, layouts, and drill-down entities to customize the forecast grid.  
- You can view the forecast trends, performance against targets, pipeline risks, and individual sales performance in a user-friendly and interactive interface.  
- You can update the forecast data manually or automatically, and schedule the forecast model to run at regular intervals.  
- You can use the artificial intelligence capabilities of Dynamics 365 Sales to get insights and recommendations on how to improve your sales forecast accuracy.  

Learn more at [Configure forecasts in your organization](/dynamics365/sales/configure-forecast#how-does-forecasting-help-organizations).  

## Up next widget

The *up next* widget is a control for viewing and managing activities such as email, tasks, appointments, and so on, on any first-party or custom record. The widget displays the current activity, upcoming activity, and completed activities. You can add these activities to a record manually or by using a sequence.  

In combination with *Focused View* or *Prioritized List* from Sales Accelerator, the *up next widget* is another productivity boost as it keeps sellers in one screen for managing their sales activities.  

Learn more at [Understand the up next widget on records](/dynamics365/sales/understand-the-up-next-widget).  

## Relationship Analytics

*Relationship Analytics* provide key KPIs on the history of interactions with an **Account** or **Contact**. The KPIs are available for display on **Contacts**, **Accounts**, **Opportunities**, and **Leads** and are displayed as a graph to help sellers quickly identify relationships that need to be nurtured/improved.  

All up views are also provided on grids so sellers can see the current health of a relationship for a given record and also as a historical trend to easily identify those which may be in decline.  

Relationship Analytics is another productivity tool for sellers to help them understand the current status of an organizations relationship with customers and enables them to quick to focus the sellers next actions in improving their connections with customers.  

Learn more at [Overview of Relationship intelligence](/dynamics365/sales/ri-overview) and [Relationship analytics and KPIs overview](/dynamics365/sales/relationship-analytics-overview).  

The *who knows whom* feature helps sellers quickly identify colleagues who can introduce them to leads or contacts based on their previous interactions through emails and meetings. The widget shows up to five people in your organization who have communicated with a lead or contact through calls and emails along with an indication of how strong their connection is.

The *who knows whom* feature helps sellers quickly identify colleagues who can introduce them to leads or contacts based on their previous interactions through emails and meetings. The widget shows up to five people in your organization who have communicated with a lead or contract through calls and emails along with an indication of how strong their connection is.  

This increases sellers productivity as they spend less time looking for ways to be introduced to a lead/contact and also can see which colleagues in their organization they can reach out to in relation to a lead or contact.  

Learn more [Who knows whom in Dynamics 365 Sales](/dynamics365/sales/who-knows-whom).  

## Related content

- [UI/UX guidance for implementations with Dynamics 365 Sales](ui-ux-guidance-sales-implementations.md)  
- [Sales personas to include in UI/UX design](ui-ux-guidance-sales-personas.md)  
- [UI/UX design components for Power Apps model-driven apps](ui-ux-component-details-model-driven-apps.md)  
- [Key UI/UX design principles](ui-ux-design-principles.md)  
