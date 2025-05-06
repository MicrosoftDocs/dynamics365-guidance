---
title: Set up your tools and infrastructure for using Copilot in your contact center 
description: Learn how to set up your contact center environment to use Copilot by making sure your solutions are optimized to use it.
ms.date: 08/29/2024
ms.topic: concept-article
author: edupont04
ms.author: ktaylor
---

# Set up your tools and infrastructure for using Copilot in your contact center

This article provides guidance on preparing your contact center environment to make sure your solutions are optimized to use Copilot.

- Configure the Customer Service admin center with the Copilot features your organization wants to use.
- Map custom fields for case and conversation summaries.
- Set up app profiles for agents.
- Set up security roles for Copilot users.
- Use integrated search providers (optional).
- Use Copilot in custom forms and apps (optional).  

## Configure the environment

Many of our customers go live with their business solution with Dynamics 365 apps and services through a series of steps and environments. Learn more at [Dynamics 365 implementation guide](../implementation-guide/introduction.md). For example, you might want four environments as the following example shows:  

DEV > TEST > PRE-PROD > PROD  

Based on our best practices and guidance, many organizations create unmanaged solutions in a lower environment, such as DEV. Then, as part of their application lifecycle management (ALM), they export managed solutions to a higher environment, such as PROD. Copilot in Customer Service should be part of the same process when moving the configuration between environments.

Learn more at [Solution concepts - Power Platform](/power-platform/alm/solution-concepts-alm#managed-and-unmanaged-solutions) and [Application lifecycle management (ALM) strategies](../implementation-guide/application-lifecycle-management.md).

## Help pane settings

You configure this item in the Customer Service admin center's **Productivity** section. Learn more at [Get started with Customer Service admin center](/dynamics365/customer-service/implement/cs-admin-center?toc=%2Fdynamics365%2Fcustomer-service%2Fadminister%2Ftoc.json&bc=..%2F..%2Fbreadcrumb%2Ftoc.yml).

There are three settings that you can configure in this panel:

- **Global Copilot help pane settings**  

  In this section, you specify if you want to make Copilot available to agents, and whether they can use AI during conversations with customers.  
- **Knowledge sources (trusted web sites)**  

  In this section, you specify links to the trusted websites that you want Copilot to use as its knowledge source.  
- **Transcript of agent interactions**  

  In this section, you specify if you want to record transcripts of your agents' interactions with Copilot.  

## Summaries settings

You configure this item in the Customer Service admin center's **Productivity** section.

There are three settings that you can configure in this panel:

- **Case summary**

  This section includes a section for managing data for case summaries. Here, you can override the default mapping to entities and include or exclude entities that Copilot will use to summarize cases.  
- **Conversation summary**
- **Transcript of agent interactions**

## Agent experience profiles

Agent experience profiles are relevant for Copilot as they allow an admin to enable different sets of copilot features for different groups of agents. You manage agent experience profiles in the Customer Service admin center under **Agent experience** and **Workspaces**.  

Agent experience profiles are solution-aware, and you can add an app profile as a component in an unmanaged solution. To add an app profile, choose the icon next to the **Add existing** menu, choose the **More** menu item, choose the **Other** menu item, and choose the **App profile** menu item.  
<!-- :::image type="content" source="media/image6.png" alt-text="Screenshot of adding Agent experience profiles to an unmanaged solution.":::  
:::image type="content" source="media/image7.png" alt-text="Screenshot of adding Agent experience profiles to an unmanaged solution.":::  
:::image type="content" source="media/image8.png" alt-text="Screenshot of adding Agent experience profiles to an unmanaged solution."::: -->

Once added to the unmanaged solution, profiles can be part of a standard ALM process and exported as managed in higher environments, where they're then read-only.

## Copilot settings in agent profiles

This section describes our recommended approach to set up agent profiles. Learn more in the articles [Overview of agent experience profiles](/dynamics365/customer-service/administer/overview) and [Configure agent experience profiles](/dynamics365/customer-service/administer/create-agent-experience-profile).

1. For the pilot (or production) user group, create a copy of the existing agent experience profile with necessary components (channels, inbox, and so on). For this cloned profile, switch on the relevant Copilot components.  

    For example, in the cloned profile, switch on the **Productivity** pane if it's not already on, and then select the **Copilot help pane** setting. You can then switch on all or some of the Copilot AI capabilities as outlined in the [Help pane settings](#help-pane-settings) section of this article.  
2. Move pilot users from the original profile to the new Copilot-enabled profile.  

    The agents can then explore the new experience with Copilot and provide feedback.  
3. When testing is complete, move these users back to the original profile, and then switch on Copilot in that profile for all relevant agents.

Other existing profiles can remain as-is with Copilot not switched on. Users in these profiles don't have access to or see Copilot, even when you switch it on in the **Productivity** settings.

> [!CAUTION]
> Users who aren't part of a specific profile will fall back to a default profile, which is determined by the system based on the components enabled and is one of the out-of-the-box default profiles. These default profiles are not editable and might have Copilot enabled by default. We recommend that you make sure all agents are included in a profile so that Copilot features are available only to those who are intended to have access.

Once you define agent experience profiles, for each profile, you can now configure two kinds of Copilot settings:

- Switch Copilot on or off in the **Productivity** pane.  
- Switch specific Copilot features on or off.  

These settings are currently not included in a solution when the parent profile is added as a component. As a result, when the parent profile is exported in a higher environment, the profile misses all Copilot enablement flags. Because it's exported as managed, it's read-only, locking any admin from configuring Copilot in the target environment.

The underlying Dataverse table is `msdyn\_appcopilotconfiguration`. [Learn more about Dataverse](/power-apps/maker/data-platform/data-platform-intro).

## Security roles

For Copilot to work properly, users must have the relevant privileges. You can assign users one of the out-of-the-box security roles, or by adding the required privileges to custom security roles. Learn more at [Enable Copilot features in Customer Service](/dynamics365/customer-service/administer/configure-copilot-features#assign-roles-and-privileges).  

Since security roles are fully solution-aware, this item can be easily included in ALM flows.  

<!-- ## Integrated providers

If your knowledge base is handled by a third-party application, and you want to consume that content with Copilot in Dynamics 365 Customer Service, you can configure a connection to it as an integrated search provider. Learn more at [Manage integrated search providers](/dynamics365/customer-service/administer/add-search-provider). 

The configured providers are saved on the `msdyn\_integratedsearchprovider` Dataverse table.  

## Copilot in custom forms and apps

If you include the case summary in a custom case form, or enable Copilot features in custom model-driven apps, review this related article: [Configure copilot features for custom case forms and custom apps](/dynamics365/customer-service/administer/copilot-powerapps-settings).  

Custom forms can already be included in an ALM flow, so any changes to the form that are required to add Copilot are automatically included in the solution with the form itself.  

Application settings are already solution-aware and can also be included in an unmanaged solution to be part of the ALM flow. For more information, review this related article: [Use settings to provide customized app experiences - Power Apps](/power-apps/maker/data-platform/create-edit-configure-settings#adding-an-existing-setting-definition).  -->

## Next step

> [!div class="nextstepaction"]
> [Onboard your users to use Copilot in your digital contact center](cs-contact-center-copilot-onboard-users.md)  

## Related information

[Copilot onboarding guide for digital contact centers](cs-contact-center-copilot-onboarding-guide.md)  
