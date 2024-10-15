---
title: TechTalk Extending Copilot in Dynamics 365 finance and operations apps
description:  Summary of TechTalk video that talks about extending the capabilities of Copilot to meet diverse business needs and provide more tailored solutions for customers and partners.
ms.date: 10/03/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Extending Copilot in Dynamics 365 finance and operations apps

As artificial intelligence continues to reshape industries and workflows, Microsoft Copilot in Dynamics 365 finance and operations apps offers exciting potential for businesses to use AI in managing finance operations. This Dynamics 365 TechTalk focuses on extending the capabilities of Copilot to meet diverse business needs and provide more tailored solutions for customers and partners.

We based this article on [a TechTalk](https://youtu.be/hc8dl5-v_Ro?si=Zs2vBU1fHXJsjFjr) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/DTV041EXT-slide.png" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/hc8dl5-v_Ro":::

## The shift to AI-driven interactions

With the rise of large language models (LLMs) and the increasing reliance on AI-driven technologies like GPT (Generative Pretrained Transformer), the way we interact with enterprise resource planning (ERP) systems is rapidly changing. The introduction of Copilot in Dynamics 365 represents a fundamental shift in how users can engage with business applications through natural language, moving beyond traditional user interfaces to conversational AI. Copilot serves as an intelligent guide, making the system more accessible by providing natural language assistance for tasks, insights, and automation.

The following image explains how AI-powered assistance helps business professionals in their work. AI capabilities can help by generating ideas and content faster, performing and automating tasks, and providing insights and next best actions, all through natural language. It highlights the key differentiators of Dynamics 365 Copilot, including its GPT-powered capabilities for every job role, integration with Dynamics 365, use of Azure OpenAI Service, focus on responsible AI practices, and secure handling of enterprise data. The right side of the image shows diverse business professionals working in various settings, including offices, industrial environments, and collaborative spaces.

:::image type="content" source="media/DTV041EXT-1.png" alt-text="Screenshot of a slide with pictures to the right and text to the left that is repeated in the text before the image." lightbox="media/DTV041EXT-1.png":::

The goal of this initiative is clear: to enhance user experiences by integrating AI deeply into the fabric of the application, enabling more efficient workflows, from generating ideas to automating tasks, all while maintaining the highest security standards.

## Understanding Copilot's core features

At its core, Copilot in Dynamics 365 apps acts as a powerful assistant. The system provides AI-driven insights, automates processes, and helps generating content—all through natural language commands. But what sets Copilot apart is its ability to be extended and customized for specific organizational needs.

### Three main surfaces for Copilot

There are three key surfaces where Copilot comes into play within Dynamics 365:

1. **App sidecar chat**  

    A panel in the app that allows users to interact with Copilot directly through chat, enabling conversational commands and responses.

2. **Embedded AI**  

    Already familiar to many users, this feature integrates AI directly into existing workflows, such as collection summaries or purchase order confirmations, offering real-time insights and assistance.

3. **Microsoft 365 chat integration**  

    A dynamic connection with data from Dynamics 365. This way, users can ask questions directly from Microsoft 365 services, such as Teams or Outlook, and still access relevant finance and operations data.

While these capabilities are impressive, one of the standout aspects of Copilot is its extensibility. Companies can tailor these features to their unique requirements, enriching the overall user experience.

## A deeper dive

One of the primary topics discussed was how businesses can extend the functionalities of Copilot to suit their specific needs. This extensibility allows partners and customers to add new features and customize Copilot's capabilities, ensuring that it aligns with the intricacies of their operations.

Copilot can act as a guide for application features, troubleshoot issues, and answer data-specific questions—all in natural language. This capability is especially useful for complex ERP environments, where navigating through numerous forms and datasets can become overwhelming. The vision is to continue building out Copilot's abilities until it serves as a comprehensive guide for all users, offering context-aware assistance within the app.

Though the vision is ambitious, it's still in progress. Many of the current features are base functionalities that will expand over time. However, the extensibility options available today already offer significant customization opportunities.

### The architecture of Copilot

To fully understand how Copilot works and how to extend it, it's essential to break down its architecture. Copilot consists of two main components:

1. **The AI Copilot control** in the Dynamics 365 app, which manages the user's interaction with the app and executes client actions.

2. **Microsoft Copilot Studio** serves as the orchestration hub, understanding user inputs and running the necessary AI models or retrieving data from connected sources, such as Microsoft Dataverse.

The following image illustrates the architecture and components of Dynamics 365 Copilot for finance and operations apps  It highlights how different layers interact. At the top, the *Finance and operations apps* section includes X++ execution and ad-hoc query execution. That box connects to the *App Copilot* section that is responsible for running client actions. The middle layer involves Dataverse where Copilot handles data and connectors, as well as AI logic for Dataverse search and questions and answers (Q&A). The *Microsoft Copilot Studio* section manages AI orchestration, conversation history, memory, and context for the Copilot, with data grounding and plugin execution at the base.

:::image type="content" source="media/DTV041EXT-2.png" alt-text="Screenshot of a slide with four boxes with text that is repeated in the text before the image." lightbox="media/DTV041EXT-2.png":::

At the heart of this extensibility is **Copilot Studio**, where developers can add plugins that teach Copilot how to perform specific tasks. For example, if you want Copilot to summarize text, retrieve customer balances, or execute workflows, a corresponding plugin can be added within Copilot Studio to enable that functionality.

## Real-world examples of extending Copilot

Several real-world use cases were explored during the TechTalk. For example, a simple query such as asking Copilot for the current time can be extended into more complex capabilities. Examples include retrieving specific datasets, running custom business logic, or translating and summarizing content in real-time. These examples highlight the flexibility of Copilot Studio and its ability to integrate AI-powered assistance into various workflows within Dynamics 365.

The low-code nature of Copilot Studio makes it accessible to a wide range of users. Developers can create plugins and build new capabilities using Power Platform tools, without needing to rely on traditional development methods. This democratizes the process of extending Copilot, empowering more team members to contribute to creating custom experiences.

## The future of Copilot in Dynamics 365

While the current extensibility options available in Copilot are already powerful, Microsoft continues to enhance these capabilities. The focus is on evolving from prescriptive step-by-step processes to dynamic chaining of plugins, where Copilot can intelligently determine which actions to take based on user input.

In the future, we can expect even more sophisticated orchestration of Copilot's capabilities, where AI can dynamically chain together various actions based on the intent of the user's prompt, without requiring the user to define the steps manually. This would allow for more seamless, intelligent workflows that adapt to the specific needs of the organization.

Additionally, Microsoft is working on expanding the variables that Copilot can access, such as current record context or page metadata, allowing for even richer contextual experiences within the app.

### Moving towards a pro-code experience

While much of Copilot's extensibility relies on low-code solutions, more advanced users can take advantage of pro-code experiences by integrating Copilot with existing X++ business logic. This allows organizations to expose their existing business logic to Copilot, enabling natural language interactions with complex ERP data and processes.

The following image is from a slide with the title **Client actions**. The left section shows a visual interface from Microsoft Copilot Studio with an event activity box where an action is named and assigned a color selection input. Below that, a message box includes a prewritten text message that uses the selected color as part of the response. On the right side, there's a block of code in X++, the programming language used in Dynamics 365 finance and operations apps. The sample code shows how to implement client actions in code, including logic for fetching user information and applying the selected color theme to a user's session.

:::image type="content" source="media/DTV041EXT-3.png" alt-text="Screenshot of a slide with a screenshot and a code sample that is described in the text before the image." lightbox="media/DTV041EXT-3.png":::

With the ability to invoke X++ code, users can execute client actions, run workflows, and access business-critical data—all through simple conversational inputs. This brings an unprecedented level of automation and intelligence to Dynamics 365, making it an even more valuable tool for organizations looking to streamline their finance operations.

## Conclusion

The introduction and extension of Copilot in Dynamics 365 finance and operations apps is an exciting development for businesses seeking to use AI in their workflows. With the ability to customize and extend Copilot's capabilities, organizations can create tailored experiences that address their unique needs, ultimately enhancing productivity and efficiency.

As Microsoft continues to build on this foundation, the future of Copilot in Dynamics 365 looks incredibly promising. From dynamic orchestration of AI-driven tasks to deeper integration with X++ business logic, the possibilities are endless for how Copilot can be used to transform finance operations. Learn more about Copilot and AI capabilities in Dynamics 365 at [Copilots and generative AI in Dynamics 365](/dynamics365/copilot/).

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [TechTalk for copilot capabilities in Dynamics 365 Finance and Supply Chain Management](dynamics-365-finance-supply-chain-management-copilot-capabilities.md)  

- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)

- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)

- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)

- [Azure Synapse Link for Dataverse documentation](/powerapps/maker/data-platform/export-to-data-lake)
