---
title: Copilot onboarding guide for digital contact centers
description: Learn how to successfully deploy Copilot in Dynamics 365 Customer Service for your digital contact center.
ms.date: 09/10/2024
ms.topic: concept-article
author: edupont04
ms.author: ktaylor
---

# Copilot onboarding guide for digital contact centers

This article is the start of a practical guide for businesses and professionals preparing to implement Copilot in Dynamics 365 Customer Service for their operational support frameworks. The onboarding guide describes best practices, strategies, and key milestones to ensure a successful deployment process.

CIOs, IT decision-makers, customer service executives, operations managers, and technology leaders should use this guide to evaluate their current operations and create a plan to smoothly integrate Copilot capabilities in their digital contact center.

## Responsible AI

Microsoft supports and encourages responsible use of Microsoft Copilot and generative AI. Get started at the [Copilot learning hub](/copilot/) and [FAQ for Copilot data security and privacy for Dynamics 365 and Power Platform](/dynamics365/faqs-copilot-data-security-privacy).  

Make sure you design your system to keep data secure and compliant with policies and standards. For example, [Microsoft's responsible AI principles](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) include fairness, reliability and safety, privacy and security, inclusiveness, and transparency and accountability.

## Copilot capabilities for customer service

The best way to test and measure Copilot's success is through real scenarios, real agents, and real customers in the production environment. Our recommended approach is to start quickly with a pilot or initial phase, and then gradually roll out Copilot to the rest of the organization. You can closely monitor the results and feedback during the initial phase. 

We chose the name *Copilot* and not *Autopilot* because Copilot acts as an assistant to the agents. While it proves useful in some situations, there are instances when questions or requests become too complex, requiring human expertise. However, even in these scenarios, business operations continue seamlessly, thanks to the human agents.  

While generative AI presents numerous possibilities, the following list shows the customer service-related Copilot capabilities available today. The first two features require a knowledge base, and the summarization features use existing data in your customer relationship management (CRM) solution.

- **Ask a question**

   Provides contextual responses to the agents' questions through a conversational interface. Copilot's responses are based on knowledge sources provided by your organization during setup.
- **Write an email**

   Helps agents quickly create email responses based on the context of the case, reducing the time users need to spend creating emails.
- **Summarize a case**

   Provides agents with a summary of a case right on the case form, so they can quickly catch up on the important details of a case.
- **Summarize a conversation**

   Provides agents with a summary of a conversation at key points throughout the customer journey such as virtual agent handoffs, transfers, and on-demand.

## Prepare your organization

To unlock the full potential of this solution, it's important to engage stakeholders early in the process. Find out how they measure success, how they manage their organizational knowledge, and what processes they use.

Here are some key activities to perform before you implement Copilot:

- Identify metrics to measure your success.
- Create a knowledge management strategy.
- Set up your tools and infrastructure.

Learn more at [Set up your tools and infrastructure for using Copilot in your contact center](cs-contact-center-copilot-setup.md).  

### Identify metrics to measure your success

Set business goals to determine the metrics to help you measure your success. You can gather metrics in one or more of the following ways:

- Use out-of-the-box reports in Dynamics 365 Customer Service Historical Analytics.  

  You can see these reports when you turn them on in the Customer Service admin center with Copilot enabled. Learn more at [Use and customize analytics and insights](/dynamics365/customer-service/administer/analytics_overview).  
- Incorporate feedback from Dataverse tables.  

  In Dynamics 365 Customer Service, go to **Advanced Settings** > **Advanced find**, and create custom views.
- Create custom Power BI reports using a scripting language such as SQL to extract data from Dynamics 365.  
- Engage with the Microsoft product team to explore how your organization can capture and use Copilot metrics. For more information, contact [D365experiment@microsoft.com](mailto:D365experiment@microsoft.com).  

However you choose to gather metrics, it's crucial to establish a success matrix for Copilot. Most enterprise customers follow a standard process for introducing new tools or features. While this approach is recommended and applicable to almost all new Dynamics 365 features, the success criteria for Copilot need to address several specific factors, due to its unique functionalities and impact:

- **Time efficiency**

  Measure the amount of time Copilot saves agents in performing their tasks. You can quantify this time by comparing the time taken to complete tasks with and without the assistance of Copilot.
- **Relevance and helpfulness of Copilot responses**

  This point is crucial because evaluating Copilot's responses isn't as straightforward as just saying they're right or wrong. Their effectiveness should be measured with a percentage that shows how relevant and helpful these responses really are. You can evaluate a response from Copilot by categorizing it as one of the following:  
  - **Totally irrelevant**

    The response doesn't address the agent's inquiry at all and provides no useful information for handling customer queries.  
  - **Partially helpful**

    The response offers some relevant information but might not fully equip the agent to resolve the customer's issue, possibly requiring further clarification or more resources.  
  - **Mostly helpful**

    The response provides substantial information and guidance toward resolving the inquiry, with minimal need for further action.  
  - **Completely helpful**

    The response fully equips the agent with the necessary information and resources to address and resolve the customer's issue without any need for more support or clarification.
- **Agent satisfaction and ease of use**

  Assess how user-friendly and intuitive Copilot is for customer service agents. Agent satisfaction with the tool can be a key indicator of its usability and effectiveness in a real-world setting.
- **Impact on customer satisfaction**

  Monitor changes in customer satisfaction metrics. This can be done through surveys or customer feedback analysis to see if there's a noticeable improvement attributed to the implementation of Copilot.
- **Return on investment**

  Consider the overall costs versus the benefits of implementing Copilot. This evaluation is crucial, as it's important to test and evaluate any feature intended for user adoption. It's essential to remember that Copilot is not a new product but a feature in Dynamics 365 Customer Service, which incurs no extra cost for most customers.

### Adjust your knowledge management strategy

Copilot provides a new way to use knowledge content, and you'll want to make sure the content is consumable by Copilot to ensure accuracy. Before agents can use Copilot to answer questions and draft emails, you need to ensure Copilot is using accurate knowledge content.

Good knowledge hygiene is key to bringing Copilot capabilities to life. For Copilot to successfully ingest, index, and find the right knowledge asset, it's important to ensure each asset meets defined ingestion criteria. Also, preparing knowledge assets for Copilot ingestion isn't a finite process. It's essential to keep ingested knowledge assets in sync with upstream sources and use proper curation and governance practices.

While every organization has its own unique systems, we aim to provide a general set of best practices for creating and maintaining your Copilot corpus. Here's a general list of must-haves for high-performing knowledge content:

- Intuitive title and description.
- Separate sections with descriptive subheadings.
- Plain language and no technical jargon.
- No knowledge asset attachments; convert them into individual knowledge assets.
- No excessively long knowledge assets; break them into individual knowledge assets.
- No broken or missing hyperlinks in the content body.
- Descriptions for all images; Copilot can't read text on images.
- No customer or personal information about employees, vendors, and so on.
- A review process for authoring, reviewing, and publishing articles.
- A log of all actions related to ingesting, checking, and removing knowledge assets.

If you store knowledge assets in Dataverse, make sure that they're always the latest version and have a status of *Published*.  

If a knowledge asset has multiple sections that apply to different audiences, it's a best practice to create multiple assets, and then tag each asset with the relevant audience.  

#### Tag knowledge content

You can create structured content tags that will help your organization categorize and label content for version control, easy updates, retrieval, and ingestion. Tags will also help agents quickly understand what the content is about. For example, you can define a set of tags for function, such as *training*, *reference*, or *troubleshooting*, and business area, such as *orders*, *billing*, *promotions*. It  makes it easier for you to manage your content over time when you standardize tags without getting too granular.  

#### Filter knowledge content

Administrators can switch on email filtering to improve the quality of Copilot responses. For example, some organizations send automated emails that appear on the customer timeline but aren't necessary for summarization. On the **Summaries** page of the Customer Service admin center, you can specify up to 10 email addresses to exclude. Emails from those addresses will not be included in the case and conversation summaries.  

## Next step

> [!div class="nextstepaction"]
> [Set up your tools and infrastructure for using Copilot in your contact center](cs-contact-center-copilot-setup.md)  

## Related information

- [Onboard your users to use Copilot in your digital contact center](cs-contact-center-copilot-onboard-users.md)  
- [Use Copilot to solve customer issues](/dynamics365/customer-service/use/use-copilot-features)  
- [Welcome to Dynamics 365 Customer Service](/dynamics365/customer-service/implement/overview)  
- [Use and customize analytics and insights in Dynamics 365 Customer Service](/dynamics365/customer-service/administer/analytics_overview)  
- [Dynamics 365 Contact Center documentation](/dynamics365/contact-center/)  
