---
title: Add DTMF aggregation to Copilot Studio classic 
description: Learn about the sample solution to add DTMF aggregation to Copilot Studio for voice support by using Bot Framework skills.
ms.date: 03/15/2024
ms.topic: conceptual
author: edupont04
ms.author: viange
---

# Using Bot Framework Composer skill to add DTMF aggregation to Copilot Studio classic for voice support

***Applies to: Dynamics 365 Customer Service***

[!INCLUDE[pva-rebrand](../includes/pva-rebrand.md)]

With Copilot Studio, you can extend your bot with Microsoft Bot Framework skills. You'll need such Bot Framework skills to aggregate data for DTMF. 
<!--No idea what the acronym stands for, but it's something about voice interaction./Eva -->

> [!NOTE]
> For brevity, we refer to `Microsoft.Bot.Components.Telephony` as *Telephony Extensions*.


> [!NOTE]
> This article refers to Copilot Studio classic for voice support. Use Copilot Studio to develop semi-pro-code solutions that leverage the Bot Framework Composer, and the Bot Framework Telephony Package. Find a guide to develop a skill by Bot Framework Composer and add the custom skill to your copilot at [https://aka.ms/pvavoiceskills](https://aka.ms/pvavoiceskills).

Learn more at [Add skills](/microsoft-copilot-studio/configuration-add-skills), where you also find links that include the errors you may get when adding your skill to Copilot Studio classic bot.  

The intent of this article is to provide a sample code of the custom skill that uses [Aggregate DTMF Input (#)](https://github.com/microsoft/botframework-components/tree/main/packages/Telephony#aggregate-dtmf-input-) included in the *Telephony Extensions* sample.  

**Aggregate DTMF Input (#)** prompts the user for multiple inputs that are aggregated until the *Termination Character*  is received.  

:::image type="content" source="media/aggregateDTMFSkill/copilot-studio-bot-framework-composer-skill-1.png" alt-text="Screenshot of the Aggregate D T M F screen, showing the Aggregate event activity." lightbox="media/aggregateDTMFSkill/copilot-studio-bot-framework-composer-skill-1.png":::

## Sample code

Find the sample code at [Bot Framework Skill](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Customer%20Service/ComponentLibrary/PVA/DTMFAggreationSkill/sampleartifacts/aggregateDTMFSkill.zip). The ZIP file contains a sample Bot Framework Skill project.  

Find another sample at [Copilot Studio classic bot solution](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Customer%20Service/ComponentLibrary/PVA/DTMFAggreationSkill/sampleartifacts/AggregateDTMF_1_0_0_0.zip). This ZIP file contains the PowerApps solution that contains the Power Virtual Agents bot.  

> [!IMPORTANT]
> Sample codes, components (solutions), and documents created by the community are not supported by Microsoft.
>
> If you have questions or issues with community tools, contact the publisher of them.  

## Set up the environment

To work on the bot framework skill sample code, you need a set of things to be successful:

- An [Azure Account](https://azure.microsoft.com/free/)
- The [Bot Framework Composer](https://aka.ms/bf-composer-download-win) (optional, but assumed for this document)
- A Copilot Studio classic bot integrated with Omnichannel for Dynamics 365 Customer Service Omnichannel for voice channels

For a copilot that is integrated with a voice channel in Omnichannel for Customer Service, you can import the sample solution [Copilot Studio classic bot solution](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Customer%20Service/ComponentLibrary/PVA/DTMFAggreationSkill/sampleartifacts/AggregateDTMF_1_0_0_0.zip) in your Customer Service environment.

As soon as the solution is imported, you can open the Copilot Studio classic bot.  

:::image type="content" source="media/aggregateDTMFSkill/copilot-studio-bot-framework-composer-skill-4.png" alt-text="Screenshot of the Aggregate D T M F screen, which shows a list of objects for the Open Skill Project." lightbox="media/aggregateDTMFSkill/copilot-studio-bot-framework-composer-skill-4.png":::

From the bot you need to take the Bot ID that will be used in the Skill publishing step.
 
:::image type="content" source="media/aggregateDTMFSkill/copilot-studio-bot-framework-composer-skill-5.png" alt-text="Screenshot of the Add a Skill screen containing the Your bot I D and Skill manifest U R L fields." lightbox="media/aggregateDTMFSkill/copilot-studio-bot-framework-composer-skill-5.png":::

Assuming you have the items listed in the requirements above, our basic flow is to open the sample project with Bot Framework Composer; author a basic skill; and then publish the skill to Azure.  

First, open Composer and open the Skill Sample project.  

:::image type="content" source="media/aggregateDTMFSkill/copilot-studio-bot-framework-composer-skill-2.png" alt-text="Screenshot of the Select a Bot pane, showing a list of available bots, with Name, Date modified, and Edit columns." lightbox="media/aggregateDTMFSkill/copilot-studio-bot-framework-composer-skill-2.png":::

After this, you'll be taken to the composer authoring canvas, which is similar to that in Power Virtual Agents. In this sample, the Telephony Package extension is used. From the left nav of the Composer UI, choose **Package Manager**, and from within that UI go to Installed tab.  

:::image type="content" source="media/aggregateDTMFSkill/copilot-studio-bot-framework-composer-skill-3.png" alt-text="Screenshot of the Package Manager screen, showing available options under the Installed tab." lightbox="media/aggregateDTMFSkill/copilot-studio-bot-framework-composer-skill-3.png":::

Once you're familiar with the Bot Framework Composer, authoring the skill, publish the Skill, please flow the guide in the link posted at the beginning of [Publishing to Azure including creating Azure resources](https://github.com/microsoft/botframework-components/blob/main/packages/Telephony/UsingComposerToBuildPVAVoiceSkills.md#publishing-to-azure-including-creating-azure-resources).  

Once the skill is published, a last step before leaving Azure. To further ensure security, Copilot Studio requires that a skill be in the same AAD Tenant as the Copilot Studio classic Bot. First go to the Azure portal in the browser at [https://portal.azure.com](https://portal.azure.com). Sign in, and navigate to the App Registration section.

:::image type="content" source="media/aggregateDTMFSkill/copilot-studio-bot-framework-composer-skill-9.png" alt-text="Screenshot of the Copilot Studio App Registration with the owned applications tab selected." lightbox="media/aggregateDTMFSkill/copilot-studio-bot-framework-composer-skill-9.png":::

Within here, search for the app registration using the name for the skill. Once found, choose the Branding and Properties element in the left hand menu. From here, either the Home Page URL must match the domain of the skill or the Publisher Domain must match the AAD tenant of the Copilot Studio classic Bot. The latter is the more secure solution.

:::image type="content" source="media/aggregateDTMFSkill/copilot-studio-bot-framework-composer-skill-10.png" alt-text="Screenshot of the Copilot Studio App Registration with the branding and properties tab being highlighted." lightbox="media/aggregateDTMFSkill/copilot-studio-bot-framework-composer-skill-10.png":::

## Skill in Copilot Studio

In the Copilot Studio Bot included in the solution the skill is already added, so you need to refresh that one.

:::image type="content" source="media/aggregateDTMFSkill/copilot-studio-bot-framework-composer-skill-6.png" alt-text="Screenshot of the Skills tab, showing the aggregate D T M F option." lightbox="media/aggregateDTMFSkill/copilot-studio-bot-framework-composer-skill-6.png":::

Inserting the Skill Manifest URL you got after the skill publishing.  

:::image type="content" source="media/aggregateDTMFSkill/copilot-studio-bot-framework-composer-skill-7.png" alt-text="Screenshot of the Update skill pane, showing the Your bot I D and Skill manifest U R L fields." lightbox="media/aggregateDTMFSkill/copilot-studio-bot-framework-composer-skill-7.png":::

## Test your skill

You're now ready to interact with the bot on the test canvas. Run the skill as a step just like any other dialog step in the bot.

:::image type="content" source="media/aggregateDTMFSkill/copilot-studio-bot-framework-composer-skill-8.png" alt-text="Screenshot of the test bot in design mode with the decision flow chart." lightbox="media/aggregateDTMFSkill/copilot-studio-bot-framework-composer-skill-8.png":::
