---
title: Onboard your users to use Copilot in your digital contact center
description: Implement Copilot in your digital contact center by creating a change management strategy, training agents, and refining knowledge content for optimal use.
ms.date: 09/10/2024
ms.topic: concept-article
author: edupont04
ms.author: ktaylor
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:08/23/2024
--- 

# Onboard your users to use Copilot in your digital contact center

Here are key activities to perform before you implement Copilot in your digital contact center. You might want to drive some of these operations concurrently depending on your organization's timeline and goals.

- Create a change management strategy
- Analyze your body of knowledge
- Train your agents on how to use Copilot effectively
- Create a testing strategy
- Gather feedback from your agents
- Measure ongoing performance  

## Create a change management strategy

To ensure a smooth transition as your agents begin working with Copilot, a change management plan is crucial. Work with each line of business that will use Copilot and gather questions and concerns. Different lines of business use Copilot in different ways. Try to involve as many teams as possible in your initial pilot phase. To help make sure your teams are using Copilot effectively, you can use first impressions and initial experiences with Copilot to create appropriate messaging and training materials.

## Analyze your body of knowledge

As you begin to onboard your first set of users, pay close attention to the quality of knowledge articles. Copilot is only as good as its sources. You might discover some content is used more or less frequently than expected, and some content is more or less useful than expected. Take this opportunity to revisit your knowledge content and make adjustments.

This is an especially critical time to gather feedback from your agents about which content is helpful. Some issues to check for:

- Content standardization
- Obsolete content
- Invalid content
- Conflicting content
- Incomplete content
- Content compliance

## Train your agents on how to use Copilot effectively

It might be tempting to use Copilot as a traditional search engine, but vague search terms and keywords aren't effective here. You should train agents to ask questions as if they're speaking with a colleague. When you provide specific prompts, Copilot responds with a more relatable, relevant answer.

Prompts are how you ask Copilot to do something for you, like answer a question, summarize a case, or create an email response. Your prompt should include four key ingredients:

- **Goal**  

  What response do you want? Example: `Write a step-by-step procedure.`.
- **Context**  

  Why do you need it and who is it for? Example: `For users of the SmartBrew coffeemaker to clean their machine.`.
- **Source**  

  Which sources should Copilot use? Example: `Look in company knowledge base.`.
- **Expectations**  

  How do you want Copilot to respond? Example: `Use casual, simple language.`.

When they use Copilot for answers, agents should use the following best practices:

- Chat with Copilot in natural language.
- Provide as many details as possible.
- Pay attention to grammar, spelling, and punctuation.
- Don't rely on document location to provide context.
- Avoid interrupting, and type `new topic` when you want to switch to a new task.

Learn more at [Learn about Copilot prompts - Microsoft Support](https://support.microsoft.com/topic/learn-about-copilot-prompts-f6c3b467-f07c-4db1-ae54-ffac96184dd5).  

## Create a testing strategy

The introduction of a new tool like Copilot to customer service agents must be well-tested and validated. In the era of AI and generative AI, organizations face the critical question of how to build their testing strategy for these innovative tools.

In the pilot phase of Copilot, you document the results and collect feedback from your agents. The best candidates for the pilot phase are the highly skilled agents. They have the expertise to deal with customer questions efficiently, allowing them to give thorough feedback without affecting the normal call center functions. Moreover, they help ensure Copilot is used properly, avoiding any incorrect or unverified information being passed from Copilot to customers.

During the pilot phase, you need to keep track of your success metrics and aim for ongoing improvement. This mainly involves improving the knowledge base articles. Copilot isn't a magic tool; its performance depends on the quality of the information it can access. When you provide Copilot with clear and complete knowledge articles, you help it to produce clear and correct results.

## Extend your solution

For a more robust experience, you might want to customize various parts of your solution, or bring in external sources for Copilot to access. This section discusses some of those customization options.

### Copilot in custom forms and apps

If you want to include the case summary in a custom case form, or enable Copilot features in custom model-driven apps, you can [Configure copilot features for custom case forms and custom apps](/dynamics365/customer-service/administer/copilot-powerapps-settings).

Custom forms can already be included in an application lifecycle management (ALM) flow, so any changes to the form that are required to add Copilot are automatically included in the solution with the form itself.

Application settings are already solution-aware and can also be included in an unmanaged solution to be part of the ALM flow. Learn more at [Use settings to provide customized app experiences](/power-apps/maker/data-platform/create-edit-configure-settings#adding-an-existing-setting-definition).

### Plugins

You can use two types of plugins in Copilot in Customer Service: prompt and connector. The prompt plugin allows you to connect Copilot to Dataverse to enable your agents to securely access data. The custom connector plugin lets you connect to external systems and pull relevant data to be used by an agent. Learn more at [Enable plugins for generative AI (preview)](/dynamics365/customer-service/administer/enable-copilot-plugins-for-generative-ai).

### Custom case summary mappings

You can modify the source case fields that Copilot uses to generate summaries or draft emails, which can improve the context and accuracy of the results. You can also select a custom field that Copilot should use to generate responses. This item is a subset of the **Summaries** settings, which you can access from the **Case summary** section.  

Learn more at [Manage fields Copilot uses for case summaries](/dynamics365/customer-service/administer/copilot-map-custom-fields).  

### Conversation summary format

You can customize the structure of conversation summaries along with the information that Copilot captures. You can choose a paragraph or structured format. The paragraph format provides a narrative conversation summary, while the structured format lets you choose what information to capture and change the arrangement of that information. Additionally, you can provide examples of error codes for Copilot to capture in conversations.  

Learn more at [Customize Copilot conversation summaries](/dynamics365/customer-service/administer/customize-copilot-conv-summary).

### Filters

Filters enable Copilot to generate a response based on a specific set of topics. You can set up filters for two Copilot capabilities: ask a question and draft a response. These filters are applied automatically without agents having to select from a list of options, reducing effort and cognitive load. Based on the rules you set up in the admin experience, filters can get updated when a new record is opened, and agents are then notified.  

Learn more about setting up filters at [Enable features in Copilot pane](/dynamics365/customer-service/administer/copilot-enable-help-pane#set-up-filters).

### Extend the out-of-the-box Copilot dashboard

With the dashboard, you can view Copilot usage alongside your primary operational metrics such as AHT, throughput, and more. You can track the adoption of Copilot-generated responses by agents and review how often agents end up using a response, summary, or email generated by Copilot. Also, agents should be able to improve how efficiently they can handle customer conversations, cases, or emails by looking at their productivity improvements.  

Learn more about the dashboard at [View copilot analytics report](/dynamics365/customer-service/use/copilot-analytics-report).

### How to access interaction feedback data

When agents use Copilot, agent interactions with Copilot such as copying summaries, using a suggested reply, feedback, and chat transcripts are stored in tables in Dataverse. You can download the transcripts and interaction data using Web API requests. Learn more at [Download Copilot transcripts](/dynamics365/customer-service/develop/download-copilot-transcript-data).  

## Gather feedback from your agents

You can use the *helpful response rate* (HRR) to gather initial agent feedback. HRR is the number of positive (thumbs-up) ratings for each interaction divided by the total ratings (thumbs up + thumbs down). You can correlate this feedback with the knowledge assets Copilot cites in its responses. Gather more detailed feedback by creating a system that enables users to request reviews, report issues, or suggest improvements.

## Measure ongoing performance

While knowledge management is an ongoing process, so is its measurement. Track usage and performance periodically to verify if Copilot is useful to agents, and identify areas for improvement.

### Tracking analytics

First, measure the performance of your knowledge content based on the purpose you outlined at the beginning. You can view some metrics directly within your Customer Service environment.

If you built your own Copilot interaction reports, you can see measurements such as number of page views for each knowledge asset, the age of the asset, and whether the agent used the cited asset. The asset age is based on the date Copilot consumed it, so it's important to ensure publication and ingestion cycles align.

### Serving business processes

Some other key metrics to consider are more closely tied to your organization's business processes, such as the following examples:

- Number of cases related to a knowledge article

- Number of escalations prevented

- Time saved when agents access these articles

- Costs saved from reduced escalations and troubleshooting time

In general, it's an iterative and ongoing process to introduce and expand Copilot capabilities in your CRM. Include stakeholders from every role to ensure your organization is using Copilot to help solve the right problems and enhance the agent experience.

## Related information

- [Set up your tools and infrastructure for using Copilot in your contact center](cs-contact-center-copilot-setup.md)  
- [Copilot onboarding guide for digital contact centers](cs-contact-center-copilot-onboarding-guide.md)  
