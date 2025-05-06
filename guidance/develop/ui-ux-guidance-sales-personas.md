---
title: Sales personas to include in UI/UX design
description: Boost user adoption of Dynamics 365 Sales by customizing forms and workflows for different sales personas.
ms.date: 03/05/2025
ms.topic: concept-article
contributors: kpetire
author: edupont04
ms.author: edupont
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-description
  - ai-seo-date:03/03/2025
  - opti25-sales
# customerIntent: As an implementation partner, I want to learn about the expectations of the five most common user profiles of Dynamics 365 Sales. 
---

# Sales personas to include in UI/UX design for implementations with Dynamics 365 Sales

The sales experience you design should be closely aligned with the persona you are building the experience for. Dynamics 365 Sales supports several tailored experiences for different personas and scenarios. It's important to understand these experiences and their purpose to understand how to use them but also which experience to use for what persona.  

> [!TIP]
> Find general guidance for design at [UI/UX guidance for implementations with Dynamics 365 Sales](ui-ux-guidance-sales-implementations.md).

Sales implementations often start with requirement gathering followed by building a tailored experience based on the captured requirements. In many cases, the project is then going through a simplification exercise in which the customer is presented with the prebuilt experience for the first time.  

Our strong recommendation is to build based on the sales personas, equip them with the prebuilt experiences that the product offers out of the box, and then make customizations on top of that for what's necessary.  

## Account manager

:::image type="content" source="media/ui-ux-guidance-sales-implementations1.png" alt-text="Card with goals, pain points, capability needs, and must-haves for account managers." lightbox="media/ui-ux-guidance-sales-implementations1.png":::

The account manager manages one or more strategic accounts and wants to get a good view across the account including stakeholders, open opportunities, closed opportunities, recent activity.  

One of the key responsibilities for the account manager is also to manage the team working on the account. This requires rich collaboration on account and deal level.  

For the account manager, we recommend that you apply the following principles:  

- A well-structured account form that allows the account manager to quickly understand what is happening at a high level. Including open opportunities and any account planning-related information is key to keep on the first tab.  

  Learn more at [UI/UX design components for Power Apps model-driven apps](ui-ux-component-details-model-driven-apps.md#forms)

- Sales Copilot to provide an account summary, recent changes, and news updates to quickly understand everything that is happening on the account across the organization 

  Learn more at [Get information from Copilot](/dynamics365/sales/copilot-get-information#summarize-an-account)

- Use organization charts to visualize the hierarchy and relationships between departments and roles in your customers' organizations. This helps sellers to better understand the decision-making process and identify the individuals who hold the most influence over purchasing decisions.  

  Learn more at [Understand organization charts](/dynamics365/sales/organization-charts)

- Teams integration and collaboration spaces for the account manager to manage the collaboration that is going on in each opportunity on the account. We recommend that you have one account team with multiple opportunity channels linked to the relevant opportunities.  

  Learn more at [Overview of Microsoft Teams integration with Dynamics 365 apps](/dynamics365/teams-integration/teams-integration)

- Use *Relationship Intelligence* to help relationship sellers stay on top of their customer relationships by providing insights around the relationship health and understanding who in your organization is already in contact with your customers.  

  Learn more at [Overview of Relationship intelligence](/dynamics365/sales/ri-overview)

- *Sales Accelerator* allows the account manager to quickly understand what is the next best action and any sales suggestions for the accounts that they are managing.  

  Make sure that the account managers understand how to configure their personal settings and create sequences to enforce best practices and help prioritize activities increasing their productivity while adhering to the organizations business processes. The recommendation is to pick from the Sequence Templates available by default and customize for business needs and to create new templates to cover other business scenarios.  

  Learn more at [Understand what is sales accelerator](/dynamics365/sales/sales-accelerator-intro) and [Sequence templates](/dynamics365/sales/sequence-templates)

- *Pipeline view* allows the account manager to stay on top of the strategic opportunities for the account in a highly visual experience.  

  Make sure that a pipeline view is the default control for opportunity and that the correct stages of the business process flow are associated with the opportunity table.  

  Learn more at [Configure the opportunity pipeline view](/dynamics365/sales/opportunity-pipeline-view-for-admins#set-the-pipeline-view-as-the-default-opportunities-view) and [Manage opportunities using pipeline view](/dynamics365/sales/use-opportunity-pipeline-view)

## Relationship or specialist seller

:::image type="content" source="media/ui-ux-guidance-sales-implementations2.png" alt-text="Card with goals, pain points, capability needs, and must-haves for relationship sellers." lightbox="media/ui-ux-guidance-sales-implementations2.png":::

The relationship or specialist seller is typically managing and closing multiple opportunities across multiple customers. It's common for this seller persona to be specialized in a specific offering or area of offerings but is being engaged by the Account Manager to drive the sales process with the customer for a certain need.  

The relationship seller typically prefers as little admin work as possible and would want the CRM updated automatically based on their activities, they often see data entry as a tax on their available time to sell. While they might accept some data entry, they expect the system in return to make suggestions from on what they should do next.  

This is further emphasized in their preference on UI which typically should provide clarity and simplicity to the opportunity. They want the opportunity to clearly state what activities and outcomes were achieved previously, and what the next steps should be for moving the opportunity forward.  

For the relationship seller, we recommend that you apply the following principles:

- Pipeline view for staying on top of the sellers sales pipeline while at the same time offering update of key details on the opportunities.  

  Learn more at [Manage opportunities using pipeline view](/dynamics365/sales/use-opportunity-pipeline-view)

- Relationship Intelligence helps you stay on top of your customer relationships by providing insights into relationship health and who knows whom within your organization in relation to customers.  

  Learn more at [Overview of Relationship intelligence](/dynamics365/sales/ri-overview)

- Automatic tracking of emails using Server Side Synchronization for emails sent by leads, contacts and accounts will ensure that the seller is kept up to date with any new communications from their customers.  

  Learn more at [Use server-side synchronization with Copilot for Sales](/microsoft-sales-copilot/use-server-side-sync) and [Specify which emails are automatically tracked - Power Platform](/power-platform/admin/email-message-filtering-correlation)

- Help relationship sellers follow the organizations approach to repeatable and predictable sales with sequences. This lets the relationship sellers focus on what to do next and maintain a standardized  process throughout the organization.  

  Learn more at [Sequence creation and activation in the sales accelerator](/dynamics365/sales/create-and-activate-a-sequence)

- Enable Copilot form fill assistance to assist the seller in completing data entry tasks minimizing their effort in maintaining vital Sales data.  

  Learn more at [Use Copilot's form fill assistance feature in model-driven apps - Power Apps](/power-apps/user/form-filling-assistance)

- Enable Copilot in Sales Copilot for Dynamics 365 but also in Outlook and Teams to get better CRM insights in the flow of work for the seller but also to assist with data entry and mundane tasks. The following list shows key Copilot capabilities for the relationship sellers:

  - Use Opportunity, Lead & Account Summary to understand what changed since they last visited the record.  

    Learn more at [View opportunity summary](/microsoft-sales-copilot/view-opportunity-summary), [Get information from Copilot](/dynamics365/sales/copilot-get-information#summarize-an-account), and [Get information from Copilot](/dynamics365/sales/copilot-get-information#summarize-a-lead)

  - Relationship/Specialist Sellers often require in-depth knowledge about products in the process of making sales. Valuable time can be saved by having Copilot recommend documents related to the products and accounts in your sales records and answer questions about the products from the documents stored in SharePoint.  

    Learn more at [Use Copilot to get content recommendations and answers from SharePoint](/dynamics365/sales/copilot-get-doc-suggestions)

  - Copilot for email suggests content while composing or replying to emails, saving you time and effort. It provides AI-generated drafts based on your input, recent emails, and related information.  

    Learn more at [Compose and send email messages using Copilot](/dynamics365/sales/compose-send-email-copilot)

  - Collaboration spaces using the Deal room template help bring together the right team members, contextual data, and productivity apps to boost collaboration and accelerate sales.  

    Learn more at [Collaborate in account and deal room teams](/microsoft-sales-copilot/collaborate-teams-newly-created-existing-team) and [Copilot for Sales features for Dynamics 365 Sales users](/microsoft-sales-copilot/features-d365-users).

- Prioritize the relationship sellers next tasks by enabling *predictive opportunity scoring* which uses a scoring model to prioritize opportunities based on their conversion potential.  

  Learn more at [Prioritize opportunities through predictive scores](/dynamics365/sales/work-predictive-opportunity-scoring#what-is-predictive-opportunity-scoring),

- Enabling Relationship Intelligence helps relationship sellers stay on top of their customer relationships. This capability provides insights around the relationship health and understanding who in your organization is already in contact with your customers.  

  Learn more at [Overview of Relationship intelligence](/dynamics365/sales/ri-overview).

- Simplify the UI/UX so that they have a clear view of the data they need and minimize the amount of navigation required to complete their tasks. The focus in design should be on seller efficiency rather than process compliance. If the seller is satisfied and efficient in making CRM updates, the updates become more frequent and sales process compliance easier to follow. Centralize visual elements like Timeline and Up Next widget so the relationship seller can quick access previous activities. Minimize navigation and simplify data entry by allowing relationship sellers to edit data directly from grids and quickly create records without losing context of the opportunity. 

  Learn more at [Key UI/UX design principles - Dynamics 365](/dynamics365/guidance/develop/ui-ux-design-principles#simplicity-in-model-driven-apps-and-canvas-apps), [Timeline Overview for Users - Power Apps](/power-apps/user/add-activities), [Understand the up next widget on records](/dynamics365/sales/understand-the-up-next-widget), and [Power Apps grid control - Power Apps](/power-apps/maker/model-driven-apps/the-power-apps-grid-control#configure-the-power-apps-grid-control).

- Use seller insights from your organizations own custom models to display contextual and intelligent insights about Dynamics 365 Sales records, based on specific criteria. These insight delivered in context of the records your relationship seller is working on will provide suggestions for next best actions to take for their deals.  

  Learn more at [View and work on seller insights](/dynamics365/sales/view-understand-insights)

- Sellers can also create and connect their own *sequences* to automate their work based on the way they prefer to sell and to personalize the communications to their own style.  

  Learn more at [Create and connect sequences for yourself](/dynamics365/sales/create-sequence-seller)

## Inside seller

:::image type="content" source="media/ui-ux-guidance-sales-implementations3.png" alt-text="Card with goals, pain points, capability needs, and must-haves for inside sellers." lightbox="media/ui-ux-guidance-sales-implementations3.png":::

The inside seller is typically managing high-velocity selling, managing many leads or opportunities per day and more focused on the next best step for an opportunity rather than the full picture, account development, and identifying new opportunities. 

The inside seller requires an experience where they can move quickly between tasks and activities, take action, and be reminded about what's next. It's also important both for the inside seller and the organization that the order of the task execution starts with the most probable sale first. The inside seller is typically stationary in front of a larger screen with phone integration connected so their UI/UX should be optimized for this form factor.  

For the inside seller, we recommend that you apply the following principles:

- Sales Accelerator/Focused View as the home cockpit experience to help the inside seller focus on what matters most with a prioritized list of upcoming activities and tasks. This helps inside sellers minimize the time to identify the next best customer to reach out to and maximize efficiency. 

  Learn more at [Use the sales accelerator with the Dynamics 365 Sales Enterprise license](/dynamics365/sales/digital-selling-sales-accelerator)

- Inside sellers often have a fixed process to follow when interacting with leads at volume which can be defined for them using sequences. This lets the inside sellers simply focus on what to do next and maintain a standardized  process throughout the organization. 

  Learn more at [Sequence creation and activation in the sales accelerator](/dynamics365/sales/create-and-activate-a-sequence)

- Enable Copilot in Sales Copilot for Dynamics 365 assist inside sellers in the flow of work with tasks like data entry and replying to customers. The following list shows key Copilot capabilities for the inside sellers:  

  - Use Opportunity Summary to understand what changed since they last visited the record  

    Learn more at [Configure fields for generating summaries and recent changes](/dynamics365/sales/copilot-configure-summary-fields).  

  - Collaboration spaces using the Deal room template help bring together the right team members, contextual data, and productivity apps to boost collaboration and accelerate sales.  

    Learn more at [Collaborate in account and deal room teams](/microsoft-sales-copilot/collaborate-teams-newly-created-existing-team).  

  - Copilot can help provide inside sellers gain access to information quickly and fetch answers to sales related questions from documents making them more efficient.  

    Learn more at [Copilot in Dynamics 365 Sales overview](/dynamics365/sales/copilot-overview#information-assistance) and [Turn on and set up Copilot in Dynamics 365 Sales](/dynamics365/sales/enable-setup-copilot)

- Prioritize the UI/UX so that the lead and opportunity forms are configured to meet the inside seller's needs.  

  The focus in design should be on efficiency of access to the information the inside seller needs on a call. Place vital data on the first tab of the form to avoid unnecessary clicks and navigation. Centralize visual elements like Timeline and Up Next widget so the inside seller can quick access previous activities and understand the next activity to undertake.  

  Learn more at [Key UI/UX design principles - Dynamics 365](/dynamics365/guidance/develop/ui-ux-design-principles#simplicity-in-model-driven-apps-and-canvas-apps), [Timeline Overview for Users - Power Apps](/power-apps/user/add-activities), [Understand the up next widget on records](/dynamics365/sales/understand-the-up-next-widget), and [Power Apps grid control - Power Apps](/power-apps/maker/model-driven-apps/the-power-apps-grid-control#configure-the-power-apps-grid-control).

- Using the Teams dialer enables the inside seller to quickly make calls directly from Sales accelerator cockpit avoiding the need to switch apps and manual record the calls in the relevant timeline.  

  Learn more at [Overview of Microsoft Teams integration with Dynamics 365 apps](/dynamics365/teams-integration/teams-integration#features-of-teams-integration).

## Sales development representative

:::image type="content" source="media/ui-ux-guidance-sales-implementations4.png" alt-text="Card with goals, pain points, capability needs, and must-haves for Sales development representatives." lightbox="media/ui-ux-guidance-sales-implementations4.png":::

The Sales development representative (SDR) is typically responsible for receiving Marketing Qualified Leads (MQL) and working to qualify them into Sales Qualified Leads (SQL). The SDR manages prospecting and outreach activities on the lead to clarify budget, the buying room, customer need, and timelines. When this is known, the lead can be handed over to sales.  

For the SDR, we recommend that you apply the following principles:

- Use Work Assignment rules to automatically assign new MQLs across the team of SDRs in the sales organization to prioritize leads and assignment rules to distribute these to the SDRs.  

  Learn more at [Work assignment overview](/dynamics365/sales/work-assignment-intro).

- Sales Accelerator as the home cockpit experience to help the SDR's focus on what matters most with a prioritized list of upcoming activities and tasks. This helps inside sellers minimize the time to identify the next best customer to reach out to and maximize efficiency.  

  Learn more at [Use the sales accelerator with the Dynamics 365 Sales Enterprise license](/dynamics365/sales/digital-selling-sales-accelerator).

- SDRs have a repeatable process to follow when qualifying the MQLs which can be defined for them using sequences. This lets the SDR's focus on what to do next and maintaining a standardized  process throughout the organization.  

  Learn more at [Sequence creation and activation in the sales accelerator](/dynamics365/sales/create-and-activate-a-sequence)

- Using predictive scoring, which uses a scoring model to prioritize leads based on their conversion potential, enables SDRs to efficiently prioritize leads so that those with the highest probability of being converted are looked at first.  

  Learn more at  [Prioritize leads through predictive scores](/dynamics365/sales/work-predictive-lead-scoring).  

- Customize the lead qualification experience to help the SDRs qualify leads more effectively.  

  Learn more at [Customize lead qualification experience in Dynamics 365 Sales](/dynamics365/sales/define-lead-qualification-experience#difference-between-new-lead-qualification-experience-and-legacy-experience).

- Enable email validation (preview) in Dynamics 365 Sales to identify and remove nonworking or invalid email addresses in leads. This proactive validation helps to prioritize potentials leads that have valid email addresses, which in turn results in lower email bounce rates, improved engagement, and increased value for your time.  

  Learn more at [Work with invalid email addresses (preview)](/dynamics365/sales/work-invalid-email-addresses).

## Sales manager

:::image type="content" source="media/ui-ux-guidance-sales-implementations5.png" alt-text="Card with goals, pain points, capability needs, and must-haves for sales managers." lightbox="media/ui-ux-guidance-sales-implementations5.png":::

A sales manager plays a crucial role in an organization by leading and overseeing the sales team. Their primary responsibilities include setting sales goals, developing sales strategies, and ensuring the team meets or exceeds these targets. They're also responsible for evaluating the performance of their salespeople, creating incentive plans to motivate the team, and sometimes directly engaging in sales activities themselves.  

Sales managers are tasked with creating sales reports, managing budgets, and analyzing performance data to identify opportunities for growth. They also play a strategic role in expanding the company's customer base and ensuring a strong market presence. Additionally, they provide mentorship and training to sales representatives, recruit and onboard new salespeople, and ensure customer satisfaction.  

For the sales manager, we recommend that you apply the following principles:

- Use *work assignment rules* to automatically assign new MQLs across the team of SDRs in the sales organization to prioritize leads and assignment rules to distribute these to the SDRs.  

  Learn more at [Work assignment overview](/dynamics365/sales/work-assignment-intro).

- Create sequences to automate the work for sellers, helping to enforce best practices and prioritize activities in line with the organizations business processes.  

  Learn more at [Manage conditional workflows with sequences](/dynamics365/sales/create-manage-sequences).

- Define and track *goals* for your organization and team. Using parent Goals for managers based on business priorities and child Goals assigned to individuals and teams. These help individuals keep track on progress towards their KPIs while providing an overall view of progress towards all up goals.  

  Learn more at [Define and track your sales goals](/dynamics365/sales/goals-overview).

- Forecasting to help you predict how much revenue your sales teams generate in a given timeframe. This helps sellers to track performance against targets and managers to track individual sales performance and provide proactive coaching.  

  Learn more at [Configure forecasts in your organization](/dynamics365/sales/configure-forecast#how-does-forecasting-help-organizations).

- Pipeline view for staying on top of the sales pipeline while at the same time offering update of key details on the opportunities.  

  Learn more at [Configure the opportunity pipeline view](/dynamics365/sales/opportunity-pipeline-view-for-admins).

- Interactive Dashboards configure for the various team members provides a one-stop workplace to provide users with workload information in real time. The also help minimize UI navigation as they users can directly navigate to their work quickly.  

  Learn more at [Create and configure model-driven app interactive experience dashboards in Power Apps - Power Apps](/power-apps/maker/model-driven-apps/configure-interactive-experience-dashboards?context=%2Fdynamics365%2Fcontext%2Fsales-context).

- View and analyze team operation metrics to help make decisions that improve sales performance using reports.  

  Learn more at [Analyze your sales data with Power BI](/dynamics365/sales/introduction-sales-template-apps).

- Relationship Intelligence helps you stay on top of your customer relationships by providing insights around relationship health and who knows whom within your organization in relation to customers.  

  Learn more at [Overview of Relationship intelligence](/dynamics365/sales/ri-overview).

- Enable Copilot to help sales teams be more productive and efficient in their daily work, this can also be extended to add more value unique to your organizational needs.  

  Learn more at [Copilot in Dynamics 365 Sales overview](/dynamics365/sales/copilot-overview) and [Extend Microsoft 365 Copilot for Sales with partner applications (preview)](/microsoft-sales-copilot/extend-copilot-for-sales).  

## Related content

- [UI/UX guidance for implementations with Dynamics 365 Sales](ui-ux-guidance-sales-implementations.md)  
- [UI/UX components for Sales-specific experiences](ui-ux-guidance-sales-components.md)  
- [UI/UX design components for Power Apps model-driven apps](ui-ux-component-details-model-driven-apps.md)  
- [Key UI/UX design principles](ui-ux-design-principles.md)  
