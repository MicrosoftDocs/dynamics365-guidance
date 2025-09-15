---
title: Contact Deduplication Agent in Dynamics 365 Sales and Dynamics 365 Customer Insights
description: Learn how to resolve duplicate contacts in Dynamics 365 Sales and Customer Insights with Copilot Studio for seamless workflows.
#customer intent: As a data administrator, I want to configure deduplication rules in Dynamics 365 Customer Insights so that I can ensure data consistency across systems.
author: edupont04
ms.author: tchilaud
ms.reviewer: edupont
ms.date: 09/15/2025
ms.topic: concept-article
---

# Agent for contact deduplication in Dynamics 365 Sales and Dynamics 365 Customer Insights with Power Apps component framework and Copilot Studio

***Applies to***:***Dynamics 365 Sales, Dynamics 365 Customer Insights - Data, Power Apps, Copilot Studio***

This solution combines Dynamics 365 Customer Insights - Data, Power Apps component framework (PCF), and Copilot Studio to help sales teams find and fix duplicate Contacts easily in their usual workflow.

## Introduction

You can create contacts from many touchpoints, like when a customer service representative adds one during a call or when someone fills out a form to register for an event.

This process can create duplicate records for the same person, with different levels of completeness and accuracy in the contact table. Duplicate records create noise, confusion, and poor data quality, which can undermine communication and relationships with the contact.

Dataverse offers native duplicate detection, but it's limited in what it can find. It also doesn't let you fix duplicate entries (that is, merge) at the right time, like when a seller is looking at a specific contact record.

Keeping your contact data clean is crucial, especially if you want to get the most from your marketing and sales efforts. Clean data helps you reach the right person with the right context.

With the profile unification engine in Dynamics 365 Customer Insights - Data, you can easily find duplicate contacts. A Power Apps component framework (*PCF*) control can show the duplicated contacts in Dynamics 365 Sales to help the seller act on it. With Copilot APIs in PCF controls, a custom topic in Copilot in Dynamics 365 Sales can suggest the best merge option for each field across the duplicates.

This approach can make it much easier to keep your contact table clean by making the deduplication process almost effortless for the seller.

The following short video shows what the experience looks like for a seller. In this example, a potential duplicate shows up in the seller's workflow when they view a contact form, and the agent helps them accept or change the suggested merge.

> [!VIDEO https://learn-video.azurefd.net/vod/player?id=d26c999b-8197-4df2-8460-e51a99cba75a]

## Architecture

This diagram shows the architecture for the solution.

:::image type="content" source="media/sales-customer-insights-contact-deduplication-agent-architecture.png" alt-text="Screenshot of the deduplication agent architecture diagram." lightbox="media/sales-customer-insights-contact-deduplication-agent-architecture.png":::

## Dataflow

1. Contacts from Dataverse (and optionally any other data source that can help identify them better) are ingested into Dynamics 365 Customer Insights - Data.

1. Set up *Profile Unification* in Dynamics 365 Customer Insights - Data with deduplication and matching rules that fit your business context.

1. The system automatically applies `CustomerId` backstamping, creating a relationship (`lookup` column) from contacts to their corresponding unified customer profile in Dynamics 365 Customer Insights - Data. Two contacts that are identified as duplicates share the same `CustomerId`, linking to the same unified customer profile.

1. When a Dynamics 365 Sales user browses a specific contact's form, the system shows a custom Power Apps Component Framework (PCF) control that surfaces potential duplicates identified earlier.

1. A custom topic in Copilot in Dynamics 365 Sales Agent compares the values of each field for the current and potential duplicate contact, and suggests the best value.

1. Through the PCF control, the Dynamics 365 Sales user can make corrections if needed, or accept the suggestion and trigger the merge operation.

1. The Dataverse merge API runs the merge operation using the provided values and deactivates the duplicate contact.

## Components

The following components are used in the reference architecture.

- [Dynamics 365 Customer Insights - Data](https://www.microsoft.com/dynamics-365/products/customer-insights) offers a powerful [profile unification](/dynamics365/customer-insights/data/data-unification) engine that helps identify duplicate contacts using [deduplication](/dynamics365/customer-insights/data/data-unification-duplicates) rules or [matching](/dynamics365/customer-insights/data/data-unification-match-tables) rules with external data sources. This approach offers advanced capabilities, such as:

  - Multi-condition rules and multiple rules
  - Standard [normalization](/dynamics365/customer-insights/data/data-unification-best-practices), like *Street*, *St*, *St.* or *st* in an address
  - [Custom normalization](/dynamics365/customer-insights/data/data-unification-match-tables), like alias mapping. For example, the name *Joe* can be set to equal *Joseph*.
  - [Fuzzy matching](/dynamics365/customer-insights/data/data-unification-best-practices#fuzzy-matching) to account for typos, like *bob@contoso.com* instead of *bob@contoso.cm*.

  Duplicate contacts identified this way are unified into the same Customer Insights customer profile and automatically [backstamped with the same CustomerProfileId](/dynamics365/customer-insights/data/integrate-d365-apps) in the corresponding Dataverse table.

- [Dynamics 365 Sales](https://www.microsoft.com/dynamics-365/products/sales) is the seller's app where the seller accesses contact details through dedicated model-driven app (MDA) forms and acts on them. Here, it's helpful to show potential duplicates and prompt the seller to address them with minimal effort.

- The [Power Apps Component Framework](/power-apps/developer/component-framework/overview) (PCF) lets you create a custom control that you embed in the contact form. The custom PCF control checks for identified potential duplicates (based on shared CustomerProfileId) and, if found, shows a side-by-side comparison of important field values for the current contact and its duplicate. When the user acts, the control triggers the merge operation for the two contacts using the [unbound action API](/power-apps/developer/data-platform/webapi/merge-entity-using-web-api).

  Using the [Copilot APIs](/power-apps/developer/component-framework/reference/copilot), the custom PCF control [executes an event](/power-apps/developer/component-framework/reference/copilot/executeevent) to call a custom Copilot topic, passing parameters and showing the result.

- In [Microsoft Copilot Studio](https://www.microsoft.com/microsoft-copilot/microsoft-copilot-studio), the Copilot in Dynamics 365 Sales agent is extended with a custom topic that receives the current contact and duplicate contact as parameters, and then uses a prompt node to compare them, identify the best values for each field, and return a predictable structured .json, as instructed in the prompt, which is shown as the default choice for merging in the custom PCF control.

## Scenario details

When duplicate contacts exist, they might not be easy to spot if they aren't obvious duplicates. Even if someone identifies them, merging duplicates can seem like an administrative task with no clear owner.

Having duplicate contacts leads to a fragmented and inaccurate view of the customer. This results in inefficient engagement, whether directly or through personalized marketing, and creates a poor customer experience.

Making it easy to surface duplicates to the right person at the right time—like the seller who owns the contact during their daily work—and letting them address it with the Copilot Agent makes keeping data clean effortless.

## Considerations

These considerations help implement a solution that includes Dynamics 365. Learn more at [Dynamics 365 guidance documentation](/dynamics365/guidance/).

### Cost optimization

Cost optimization means finding ways to reduce unnecessary expenses and improve operational efficiency. Learn more at [Overview of the cost optimization pillar](/azure/architecture/framework/cost/overview).

In this reference architecture, app components like Dynamics 365 Customer Insights - Data and Dynamics 365 Sales are online business applications with their own licensing model, so using this pattern doesn't affect costs.

However, [Microsoft Copilot Studio consumes credits](/microsoft-copilot-studio/billing-licensing) when used, either through packs or pay-as-you-go. For example, you can check if a potential duplicate exists for the current contact with a low-code approach in the custom Copilot topic. In many cases, it's better to use a pro-code approach in the PCF control, so it only calls the custom Copilot topic when there's an existing duplicate. This approach reduces the number of messages and credits used.

## Related resources

Review these related architecture guides, solutions, and other guidance content:

- [Data unification best practices - Dynamics 365 Customer Insights](/dynamics365/customer-insights/data/data-unification-best-practices)
- [CustomerId Backstamping with Dynamics 365 Customer Insights - Data](https://community.dynamics.com/blogs/post/?postid=21e6f72b-e79d-ef11-8a6a-6045bded8f52)
- [Create components with Power Apps Component Framework - Training](/training/paths/create-components-power-apps-component-framework/)
- [Copilot in Sales: Extensibility Part 1 | FastTrack Dynamics 365](https://www.youtube.com/watch?v=638gZ8yLCIc&t=1s) / [Extending Copilot in Sales Part 2 | Dynamics 365 Bites](https://www.youtube.com/watch?v=4u9h0OBFOiA)
<!-- 
## Tags

*Stakeholders:* Sales

*Products:* Dynamics 365 Sales, Dynamics 365 Customer Insights - Data,
Power Apps, Copilot Studio -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Thomas Chilaud](https://www.linkedin.com/in/thomas-chilaud) | Solution Architect
