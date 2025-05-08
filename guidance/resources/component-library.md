---
title: Sample library for Customer Service
description: Read about the library of sample components in GitHub that can help customers and partners create and deploy solutions quickly and easily.
ms.date: 09/04/2024
ms.topic: concept-article
author: edupont04
ms.author: viange
---

# Sample library for Dynamics 365 Customer Service

***Applies to: Dynamics 365 Customer Service***

This collection of sample code, components (solutions), and documents has been created to help your Customer Service projects with tasks such as customization, configuration, and operation of the platform. The library offers reusable and easy-to-follow resources for Customer Service developers and users.  

Some of the components are hosted in the GitHub repo [https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/ComponentLibrary). You can contribute to this project by reporting issues, suggesting features, or submitting pull requests.

> [!IMPORTANT]
> Sample codes, components (solutions), and documents created by the community aren't supported by Microsoft. If you have questions or issues with community tools, contact the tool's publisher.

## Areas

The following sections outline the content of the collection. Each section includes links to the corresponding articles and samples.

### Unified routing

- Channel-based presence

    A core feature of this scenario is the flexibility of channel presence management for agents. Depending on the volume and urgency of different types of customer inquiries, agents can adjust the flow of incoming channel requests to suit their preferences and availability. For instance, an agent can pause the incoming calls channel if they want to focus on chats or cases, or the other way around. This way, agents can optimize their productivity and customer satisfaction.

    This sample approach is to use a channel-centric solution by setting up a separate Advanced Queue for each relevant channel. This allows for the use of the native Assignment MethodAssignment Ruleset functionality and reduces latency between Agent Channel selection and assignments. Learn more at [Overview of unified routing](/dynamics365/customer-service/overview-unified-routing) and [Channel-based presence](cs-channel-based-presence.md).

- Set up agent capacity for custom entities

    In Dynamics 365 Customer Service, you can configure capacity-based routing for entities to supplement the case (incident) entity. Learn more at [Set up agent capacity for custom entities](cs-route-release-capacity-in-ur.md), where we provide two approaches—one no-code and one low-code—to perform the previously mentioned actions.

### Omnichannel

- Custom record identification

    To identify a customer in the contact center, you might have to apply custom search criteria, based on the information that the customer provides. This approach will help you quickly and efficiently find the customer's profile and access their records. In OOB, you can search by name, phone number, and email address. However, you might want to search by account number or other relevant data. This article explains how to customize the search criteria.

    Learn more at [Custom Record Identification](cs-omnichannel-custom-record-identification-rule.md).

- Sample context parsing in JavaScript

    Context variables play a crucial role in optimizing customer service workflows and enhancing agent productivity. They provide essential context for effective communication and decision-making.  

    If you're working with web resources, you can access context variables from custom JavaScript code. This allows you to enhance the user experience by dynamically adjusting behavior based on the context.  

    Learn more at [JavaScript Sample Context parsing](cs-omnichannel-sample-context-parsing.md).

- LiveChat Widget customization samples

    This is a collection of ready-to-use JavaScript code examples for customizing the Omnichannel LiveChat Widget.  

    Learn more at [LiveChat Widget customization samples](cs-omnichannel-live-chat-widget-samples.md).

- AgentScript and macro samples

    Agent scripts are essential tools for minimizing human errors during customer interactions. They provide structured guidance to agents, ensuring consistent and efficient resolution processes. These scripts come in two main forms: text-based guidance and macros. Macros simplify repetitive tasks, allowing agents to handle complex actions with a single click. By incorporating these elements, teams can optimize workflows and improve overall operational efficiency.  

    Learn more at [AgentScript and Macro samples](cs-agent-script-macro-sample.md).

### AI

- AI case deflection

    Emails have unstructured content. Routing rules based on subject/body text aren't effective.

    Human intervention is required for proper categorization. The case would need to be re-assigned to the right owner. The customer might want to implement a custom AI model before engaging Unified Routing.

    This content describes a proposal approach by using ARC rules and AI Builder.  

    Learn more at [Route or deflect cases using AI Builder](cs-ai-case-deflection.md).

- Summarize Dynamics 365 Knowledge Base articles with ChatGPT

    The current integration of Copilot Studio with Knowledge Base articles only offers article links without providing a summary that can be used in chat conversations.

    By integrating ChatGPT with Copilot Studio, the gap is bridged. This way, knowledge articles are summarized directly within the chat conversation.  

    Learn more at [Summarize Dynamics 365 Knowledge Base with ChatGPT for efficient customer support](ai-summarize-knowledge-base-articles.md).
- Copilot onboarding guide for digital contact centers

  The onboarding guide describes best practices, strategies, and key milestones to ensure a successful deployment process. Use this guide to evaluate your current operations and create a plan to smoothly integrate Copilot capabilities in your digital contact center.  

  Learn more at [Copilot onboarding guide for digital contact centers](cs-contact-center-copilot-onboarding-guide.md).  

### Microsoft Copilot Studio

[!INCLUDE[pva-rebrand](../includes/pva-rebrand.md)]

- DTMF aggregation by Bot Framework Skills

    This sample serves to explain how to use Bot Framework Composer skill to add DTMF aggregation to Copilot Studio classic for voice support. For DTMF aggregation on chatbots, Bot Framework Skills are required to develop semi-pro-code solutions with the Bot Framework Composer and the Bot Framework Telephony Package.

    Learn more at [Using Bot Framework Composer skill to add DTMF aggregation to Copilot Studio classic for voice support](copilot-studio-bot-framework-composer-skill.md).

- Multilingual voice bot in Microsoft Copilot Studio

    This sample solution contains a Copilot Studio bot that was implemented based on the guidance at [Set up a multilingual bot to use in voice channel](/dynamics365/customer-service/set-up-multilingual-pva-bot).

    Learn more at [Set up a multilingual bot in Copilot Studio for contact center](copilot-studio-multilanguage-bot.md).

- Play audio file in Copilot Studio voice bot

    This sample shows how to play audio files saved in secure data storage. With Bot Framework Composer and Azure Blob Storage, we can secure a custom audio clip and play it in a custom copilot.  

    Learn more at [Play secure audio file from Copilot Studio](copilot-studio-play-audio-file.md).

- Application Insights for Copilot Studio

    This article discusses how you can capture telemetry data from your Microsoft Copilot Studio bot for use in Application Insights. In addition to the native analytics features within Microsoft Copilot Studio, you can send telemetry data to Application Insights.

    Learn more at [Copilot Studio Application Insights Telemetry](copilot-studio-appinsights.md).

### Application Insights

- AppInsights telemetry with Microsoft Dataverse

    This article discusses how you can capture telemetry data for Microsoft Dataverse.  
    
    Learn more at [Application Insights telemetry with Microsoft Dataverse](cs-dataverse-appinsights.md)

### Dynamics 365 Channel Integration Framework 2.0

- CIF simulator

    The simulator is a collection of samples that we built using Dynamics 365 Channel Integration Framework.

    Learn more at [Simulator for Channel Integration Framework v. 2.0 ](cs-set-up-cif2-simulator.md).

- Set up Click to Outbound call

    This article outlines the steps to use a custom control so that users can make outbound calls from a Customer Interaction Center (CIF) provider in Omnichannel for Customer Service. The sample solution is a resource that helps optimize the Dynamics 365 implementation. It includes a custom control that provides the capability to format a phone number and initiate an outbound call from a text or phone number field.

    Learn more at [Set up outbound call](cs-set-up-outbound-calls.md).

- Sample Adaptor for Channel Integration Framework

    This article outlines guide on configuring and setting up an adaptor for Channel Integration Framework to receive notifications from external applications.

    The sample adaptor included in this guide demonstrates how an external application can notify a user about incoming notifications using the Channel Integration Framework API V2.0. By showcasing the adaptor code as a sample, this document offers insights into integrating an existing application seamlessly with the Channel Integration Framework, making it easier for developers to understand a one of the patterns to integrate with Channel Integration Framework. 

    Learn more at [Sample Adaptor](cs-set-up-cif2-sampleadaptor.md).

### Automation

- Automate agent tasks with Power Automate

    This sample shows how to run a Power Automate desktop flow from Customer Service workspace to automate tasks on a customer service representative's workstation.

    Learn more at [Automate agent tasks with Power Automate Desktop](cs-pad-automation.md). 

## Related information

- [Dynamics365 Customer Service](/dynamics365/customer-service/)
- [Unified Routing](/dynamics365/customer-service/administer/overview-unified-routing)
- [Omnichannel for Customer Service](/dynamics365/customer-service/implement/introduction-omnichannel)
- [Microsoft Copilot Studio](/microsoft-copilot-studio/)
