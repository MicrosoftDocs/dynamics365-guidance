---
title: Architecture for contact center with existing CRM
description: Learn about reference architectures for contact centers with Dynamics 365 Contact Center and a non-Microsoft CRM solution.
author: edupont04
ms.author: edupont
ms.topic: reference-architecture
ms.date: 06/28/2024
---

# Contact center retaining existing CRM and using Dynamics 365 Contact Center

In this scenario, you retain your existing solution for customer relationship management (CRM), but replace your contact center as a service (CCaaS) solution with Microsoft services. Dynamics 365 brings [routing](/dynamics365/customer-service/administer/overview-unified-routing), [channels](/dynamics365/customer-service/implement/try-channels), [bots](/microsoft-copilot-studio/), and [business intelligence](/dynamics365/customer-service/use/omnichannel-analytics-insights), while also adding generative AI to your contact center. ​

- Customers reach you through their chosen channels​

- Microsoft Telephony and interactive voice response (IVR) capabilities handle voice calls​.

- Self-service bots are customized, built, and deployed in a low-code environment in Copilot Studio, which also enables the customization of every Copilots used in the contact center.​

- Your contact center relies on your existing CRM solution. ​

- AI-generated Unified Intelligent Routing incorporates your existing CRM, delivering calls to agents with full context.  ​

- The agent experience is enhanced by Copilot AI, including prompt suggestions, email drafts, and the ability to reach and collaborate across the organization, during the call, through Microsoft Teams (if licensed).​

- Follow-up is optimized with case summaries, case-to-knowledge generation and suggested activities, such as meetings.​

- Supervisors and managers have access to contact center health, agent performance, "whisper" or barge-in, as well as analytics and reports with AI generated suggestions for coaching, training, and contact center optimization.

## Architecture

[!INCLUDE [daf-mag-diagram](../includes/daf-mag-diagram.md)]

:::image type="content" source="../media/ccaas-architecture3.svg" alt-text="A architecture diagram with Dynamics 365 Customer Service Premium." lightbox="../media/ccaas-architecture3.svg":::

## Dataflow

1. Customers engage via the channel of their choice, including Microsoft Teams as a channel for internal facing contact centers (such as employee helpdesks). ​

2. Azure Communications Services provides Public Switched Telephone Network (PSTN) services for both voice and SMS channels. ​

3. Dynamics 365 Contact Center works with your existing CRM, and incorporates your CRM into self-service bots, and IVR. Delivers calls to agents with full context. ​

4. Microsoft Copilot Studio provides self-service Automation in the form of IVR and/or messaging chat bots. ​

5. Work is routed to agents using AI-infused Unified Intelligent Routing.​

6. Agent workspaces include Copilot for knowledge chat / search, agent prompting, and suggested collaboration with subject matter experts across the organization. ​

7. Connectors enable collaboration between agents and Teams users, including the ability to collaborate one-on-one or through swarms. Users can also consult or transfer calls to Teams users, provided you have a Microsoft 365 license.

8. AI generates follow-up for agents with email drafts, communications, and suggestions for meetings. AI generates case summaries and suggests case-to-knowledge articles. ​

9. Both the agent and supervisor experiences are built upon and integrated with Power Platform. Dataverse stores all core data and events for the customer data platform.​

10. Supervisors interact with the built-in capabilities of Dynamics 365 Contact Center, including contact center and call monitoring, "whisper"/barge in for assistance, insights, forecasting and scheduling.

<!-- (To come: Components, Related Resources. I don't have access to how the Dynamics 365 Contact Center Learn pages are being laid out, so we'll have to wait for this.) -->

## Assumptions

[!INCLUDE [daf-azure](../includes/daf-azure.md)]

## Related information

- [Introduction to reference architectures for digital contact centers](contact-center-overview.md)  
- [Dynamics 365 Contact Center documentation](/dynamics365/contact-center/)  
