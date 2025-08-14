---
title: Contact center using existing CRM and CCaaS solution with Copilot for Service and Copilot Studio 
description: Learn about reference architectures for contact centers with external customer service solutions and Microsoft Copilot for Service or Copilot Studio.
author: edupont04
ms.author: edupont
ms.topic: reference-architecture
ms.date: 06/27/2024
---

# Contact center using existing CRM and CCaaS solution with Copilot for Service and Copilot Studio

This architecture retains your existing solution for customer relationship management (CRM) and contact center as a service (CCaaS). But it helps you improve or add channels and self-service bots with Microsoft Copilot Studio, and enhance your agent experience with AI through Copilot for Service.  

- Customers reach you through your CCaaS channels and telephony.  

- Copilot for Service embeds within your existing CRM.  

- Copilot Studio enables you to manage dialog flow for self-service, including customizing, building, and deploying digital and voice bots.  

- Routing is through your CRM / CCaaS provider.  

- The agent experience is enhanced by [Copilot for Service](/microsoft-copilot-service/about-microsoft-copilot-for-service), including case summaries, email drafts, and knowledge chats. Agents can reach out and collaborate across the organization, during the call, through Microsoft Teams (if licensed).  

- Follow-up is provided by your CCaaS provider or CRM.  

- Supervisors and managers work with your existing CRM or CCaaS provider.  

## Architecture

[!INCLUDE [daf-mag-diagram](../includes/daf-mag-diagram.md)]

:::image type="content" source="../media/ccaas-architecture4.svg" alt-text="A architecture diagram with Copilot for Service or Copilot Studio that connects to a non-Microsoft CRM solution." lightbox="../media/ccaas-architecture4.svg":::

## Dataflow

1. Customers engage through the channels for your contact center, such as Omnichannel and Voice.

2. Copilot for Service embeds within your existing CRM and incorporates your CRM into self-service bots and interactive voice response (IVR). Delivers calls to agents with full context.

3. Microsoft Copilot Studio provides self-service automation in the form of [interactive voice response (IVR)](/microsoft-copilot-studio/voice-overview) and/or messaging chat bots.

4. Work is routed to agents using your CRM and routing capabilities.

5. Agent workspaces include Copilot for knowledge chat / search, and suggested collaboration with subject matter experts across the organization, provided you have a Microsoft 365 license.

6. Connectors enable collaboration between agents and Teams users, including the ability to collaborate one-on-one or through swarms. Users can also consult or transfer calls to Teams users, provided you have a Microsoft 365 license.

7. Follow-up, agent supervision and management, as well as reporting and analytics, is supplied by your CCaaS and CRM providers.
<!-- 
(To come: Components, Related Resources. I don't have access to how the Dynamics 365 Contact Center Learn pages are being laid out, so we'll have to wait for this.) -->

## Assumptions

In this Dynamics 365 Contact Center architecture, we **do not** assume that the solution uses the core capabilities of Microsoft Azure.

## Related information

- [Introduction to reference architectures for digital contact centers](contact-center-overview.md)  
- [Dynamics 365 Contact Center documentation](/dynamics365/contact-center/)  
