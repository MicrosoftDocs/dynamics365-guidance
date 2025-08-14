---
title: Contact center using Dynamics 365 Customer Service Enterprise
description: Learn about reference architectures for contact centers with Dynamics 365 Customer Service Enterprise and a non-Microsoft contact center solution.
author: edupont04
ms.author: edupont
ms.topic: reference-architecture
ms.date: 06/28/2024
---

# Contact center using Dynamics 365 Customer Service Enterprise

In this scenario, you retain your contact center as a service (CCaaS) solution and use Dynamics 365 Customer Service for customer relationship management (CRM). Customer Service provides a standalone agent desktop. Agents can search knowledge in a questions-and-answers format rather than search by keyword. Copilot generates case management, Knowledge Management, Unified Intelligent Routing, reporting and analytics. Copilot generates case to knowledge draft, summaries of cases and conversations, and email drafts.

- Customers reach you through your CCaaS channels and provided telephony.  

- You manage your self-service bots with the environments supplied by your CCaaS provider.  

- You manage customer relations (CRM) in Dynamics 365 Customer Service Enterprise.  

- Gen AI-infused Unified Intelligent Routing sends the call to the right agent with full context, including Data from your existing CRM.  

- The agent experience is enhanced by Copilot, including prompt suggestions, email drafts, and the ability to use embedded Teams to collaborate across the organization, during the call, or through Microsoft Teams (if licensed).

- Follow-up is optimized with case summaries, and suggested activities, such as meetings.  

- Supervisors and managers monitor the contact center and calls through the CCaaS solution.

## Architecture

[!INCLUDE [daf-mag-diagram](../includes/daf-mag-diagram.md)]

:::image type="content" source="../media/ccaas-architecture2.svg" alt-text="A architecture diagram with Dynamics 365 Contact Center that connects to a non-Microsoft CRM solution." lightbox="../media/ccaas-architecture2.svg":::

## Dataflow

1. Customers engage via CCaaS channels and voice.

2. Bots are customized and built in CCaaS supplied environments.

3. Dynamics 365 Customer Service includes Unified Intelligent Routing.

4. Agent workspaces include Copilot for knowledge chat / search, agent prompting, and suggested collaboration with subject matter experts across the organization via Teams (if licensed).

5. Connectors enable collaboration between agents and Teams users, including the ability to collaborate one-on-one or through swarms. Users can also consult or transfer calls to Teams users. (If Microsoft 365 Licensed)

6. AI generates follow-up for agents with email drafts, case summaries and suggests case-to-knowledge articles.

7. Supervisor monitoring, analytics and reporting are supplied by the CCaaS provider.

<!-- (To come: Components -->

## Assumptions

In this Dynamics 365 Contact Center architecture, we **do not** assume that the solution uses the core capabilities of Microsoft Azure.

## Related information

- [Welcome to Dynamics 365 Customer Service](/dynamics365/customer-service/implement/overview)  
- [Get started with Customer Service workspace](/dynamics365/customer-service/implement/csw-overview)  
- [Introduction to reference architectures for digital contact centers](contact-center-overview.md)  
- [Dynamics 365 Contact Center documentation](/dynamics365/contact-center/)  
