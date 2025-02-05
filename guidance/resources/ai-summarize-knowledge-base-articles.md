---
title: Summarize Dynamics 365 Knowledge Base articles with ChatGPT
description: Sample implementation to summarize Dynamics 365 Knowledge Base articles with ChatGPT from Copilot Studio.
author: edupont04
ms.author: viange
ms.topic: conceptual
ms.date: 03/15/2024
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:3/12/2024
  - O25-Service
# CustomerIntent: As an admin, I want to provide a summary of Knowledge article to agents or clients.
---

# Summarize Knowledge Base articles with GPT for efficient customer support  

***Applies to: Dynamics 365 Customer Service***

[!INCLUDE[pva-rebrand](../includes/pva-rebrand.md)]

In today's fast-paced world, customers expect quick and efficient solutions to their queries. Integrating a knowledge base search into your bots can provide customers with self-service options, allowing them to find the information they need quickly and easily.  

In our [blog post](https://cloudblogs.microsoft.com/dynamics365/it/2022/09/07/empower-self-service-by-adding-knowledge-base-search-to-your-bots), we discussed the benefits of knowledge base integration and provided step-by-step instructions for adding this feature to your bots using Copilot Studio.  

In this article, we take things a step further and explore how you can integrate the knowledge base from Dynamics 365 with ChatGPT for even more efficient and effective summarization. By combining the power of Dynamics 365's knowledge base with ChatGPT's natural language processing capabilities, you can provide customers with even more accurate and personalized responses to their queries.  

Watch the video from GitHub at [https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/ComponentLibrary/AI/SummarizingD365KBAwithChatGPT/videos/Sumarrizaing%20Recording.mp4).

## Add the action to your topic in your self-service bots

In our previous article, we added the search flow action to the "Greetings" topic in our bot. The "Greetings" topic has preconfigured trigger phrases and a question. At the output of the question, we had called the "Search Dynamics 365 knowledge articles" flow action, as shown in the following figure.

:::image type="content" source="media/SummarizeArticleChatGPT/ai-summarize-knowledge-base-articles-1.png" alt-text="Screenshot of the Search Dynamics 365 knowledge articles flow action, diverting into multiple conditions." lightbox="media/SummarizeArticleChatGPT/ai-summarize-knowledge-base-articles-1.png":::

The action's output is the result of the knowledge base search. The value is stored in the variable `bot.jsonResult1 (text)`, and the count of the articles that were returned in the search result is stored in the variable `articleCount1 (number)`, which is redirected to condition to check if the search returned any article or not, such as in *articleCount1 (number) is greater than 0*.

## Create a Power Automate for summarizing the article using ChatGPT

In this example, we'll demonstrate how to use an HTTP action to process text received from the PVA bot and invoke ChatGPT's API for article summarization. The result of the action is then returned to the PVA bot.  

:::image type="content" source="media/SummarizeArticleChatGPT/ai-summarize-knowledge-base-articles-2.png" alt-text="Screenshot of the Summarize Text using Chat G P T screen, showing the connection between Copilot Studio to Input Text." lightbox="media/SummarizeArticleChatGPT/ai-summarize-knowledge-base-articles-2.png":::

The following are the specifics of the HTTP action required to invoke ChatGPT's API. To use this action, you must obtain your own secret from the OpenAI portal and substitute the value of the "Authorization" header with "Bearer (replace with the actual token)". Use the following URL to go to [OpenAI portal](https://platform.openai.com/docs/api-reference) and select view API keys and follow the steps to obtain and key.

:::image type="content" source="media/SummarizeArticleChatGPT/ai-summarize-knowledge-base-articles-3.png"  alt-text="Screenshot of the H T T P screen, showing the Method, U R I, Headers, Queries, Body, and Cookie fields." lightbox="media/SummarizeArticleChatGPT/ai-summarize-knowledge-base-articles-3.png":::

## Incorporate an action into your self-service bots that triggers Power Automate

Next, we'll incorporate an action that triggers Power Automate to invoke ChatGPT's API for article summarization based on the output of the condition. The output of the flow is then redirected to the **Result-dialog** to display the result in an adaptive card.

:::image type="content" source="media/SummarizeArticleChatGPT/ai-summarize-knowledge-base-articles-4.png"  alt-text="Screenshot of the Greeting screen, showing the Action and Redirect fields that appear after setting conditions." lightbox="media/SummarizeArticleChatGPT/ai-summarize-knowledge-base-articles-4.png":::

## Save the topic and publish the bot

The following illustration shows the output from our example.

:::image type="content" source="media/SummarizeArticleChatGPT/ai-summarize-knowledge-base-articles-5.png"  alt-text="Screenshot of a test bot chat window with example output for booking a travel." lightbox="media/SummarizeArticleChatGPT/ai-summarize-knowledge-base-articles-5.png":::

When the business user chooses the **Show Content** action, the chat displays a summary of the knowledge article with a link to view it in the portal.

:::image type="content" source="media/SummarizeArticleChatGPT/ai-summarize-knowledge-base-articles-6.png"  alt-text="Screenshot of a test bot chat window showing a message with details for booking a travel." lightbox="media/SummarizeArticleChatGPT/ai-summarize-knowledge-base-articles-6.png":::

For more information about showing the results in an adaptive card, go to **Render results** in the documentation.

## Artifacts

Download the solution zip file from [https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/ComponentLibrary/AI/SummarizingD365KBAwithChatGPT/sampleartifacts/SummarizeKBArticleusingGPT_1_0_0_1.zip).
