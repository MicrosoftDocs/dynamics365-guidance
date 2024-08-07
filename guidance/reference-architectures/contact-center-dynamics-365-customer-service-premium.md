---
title: Contact center using Dynamics 365 Customer Service Premium
description: Learn about reference architectures for contact centers with Dynamics 365 Customer Service premium as the main solution for the contact center.
author: edupont04
ms.author: fredgraver
ms.topic: article
ms.date: 06/28/2024
---

# Contact center using Dynamics 365 Customer Service Premium

This architecture supports the broadest possible contact center scenarios. With this approach, you infuse generative AI on every step of the customer journey​ as part of your digital contact center.

- Customers reach you through their chosen channels​.

- Microsoft Telephony and interactive voice response (IVR) capabilities handle voice calls​.

- Dynamics 365 Customer Service provides customer relationship management (CRM) that is built on Azure. ​

- Self-service bots are customized, built, and deployed in a low-code environment in [Copilot Studio](/microsoft-copilot-studio/), which also supports customization of every copilot used in the contact center.​

- [Unified routing in Dynamics 365 Customer Service](/dynamics365/customer-service/administer/overview-unified-routing?) is infused with generative AI and sends the call to the right agent with the full context, based on the CRM, conversation history, and so on. ​

- The agent experience is enhanced by Copilot AI, including case summaries, prompt suggestions, email drafts, and the ability to reach and collaborate across the organization, during the call, through Microsoft Teams (if licensed).​

- Follow-up is optimized with conversation summaries, case-to-knowledge generation, and suggested activities, such as meetings.​

- Supervisors and managers have access to contact center health, agent performance, "whisper" or barge-in, as well as analytics and reports with AI generated suggestions for coaching, training, and contact center optimization.

## Architecture

[!INCLUDE [daf-mag-diagram](../includes/daf-mag-diagram.md)]

:::image type="content" source="../media/ccaas-architecture1.svg" alt-text="A architecture diagram with Dynamics 365 Customer Service Premium." lightbox="../media/ccaas-architecture1.svg":::

## Dataflow

1. Customers engage via the channel of their choice, including Microsoft Teams as a channel for internal facing contact centers (such as employee helpdesks).

2. Azure Communications Services provides Public Switched Telephone Network (PSTN) services for both voice and SMS channels.

3. Microsoft Dataverse houses your CRM, informing self-service bots, IVR, case management, knowledge management, and the agent experience.

4. Microsoft Copilot Studio provides self-service Automation in the form of IVR and/or messaging chat bots. Full Conversational AI for digital and voice bots. Gen AI answers and actions.

5. Work is routed to agents using AI-infused Unified Intelligent Routing. Routing includes sentiment, predicted effort, skills, presence, capacity, and customer parameters.

6. Agent workspaces include Copilot for knowledge chat / search, agent prompting.

7. Connectors enable collaboration between agents and Teams users, including the ability to collaborate one-on-one or through swarms. Users can also consult or transfer calls to Teams users. (If Microsoft 365 Licensed)

8. AI generates follow-up for agents with email drafts, communications, and suggestions for meetings. AI generates case summaries and suggests case-to-knowledge articles.

9. Both the agent and supervisor experiences are built upon and integrated with Power Platform. Dataverse stores all core data and events for the customer data platform.

10. Supervisors interact with the built-in capabilities of Dynamics 365 Contact Center, including contact center and call monitoring, "whisper"/barge in for assistance, insights, forecasting and scheduling.

<!-- (To come: Components, Related Resources. I don't have access to how the Dynamics 365 Contact Center Learn pages are being laid out, so we'll have to wait for this.) -->

## Assumptions

In this Dynamics 365 Contact Center architecture, we **do not** assume that the solution uses the core capabilities of Microsoft Azure.

## Related information

- [Introduction to reference architectures for digital contact centers](contact-center-overview.md)  
- [Dynamics 365 Contact Center documentation](/dynamics365/contact-center/)  
