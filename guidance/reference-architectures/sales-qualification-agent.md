---
title: Secure Architecture for Sales Qualification Agent
description: Understand how the Sales Qualification Agent (SQA) in Dynamics 365 Sales uses Dataverse, Power Automate, and Azure OpenAI to streamline lead qualification securely and efficiently.
#customer intent: As an IT architect, I want to know how the SQA integrates with Dataverse and Azure OpenAI so that I can ensure secure and scalable implementation.
author: edupont04
ms.author: edupont
ms.reviewer: edupont
ms.date: 01/19/2026
ms.topic: concept-article
ms.collection: bap-ai-copilot
---

# Architecture and compliance safeguards for Sales Qualification Agent

Your organization can try out the Sales Qualification Agent in Dynamics 365 Sales. But the people who are responsible for security or IT might want more than what Microsoft talks about in the [Sales Qualification Agent overview](/dynamics365/sales/sales-qualification-agent). Implementing a Sales Qualification Agent (SQA) touches on crucial security, data privacy, and compliance requirements. To address stakeholder concerns, provide clear documentation of how the agent works within your IT environment, and demonstrate that it meets (or exceeds) all corporate and regulatory policies. This article summarizes the main points your CISO, IT architects, and compliance officers care about.

> [!TIP]
> Download the role-specific Sales Qualification Agent guidance at [https://aka.ms/sqaguidance](https://aka.ms/sqaguidance).

## Component overview

The following diagram illustrates how the four layers of the Sales Qualification Agent (SQA) interact to deliver secure, scalable, and AI-driven functionality within the Microsoft ecosystem.  

:::image type="content" source="media/sales-qualification-agent-architecture.png" alt-text="Screenshot of the four layers of the Sales Qualification Agent architecture diagram showing UI Experiences, Orchestration Layer, Data Layer, and Agent Layer interactions.":::

SQA is composed of four distinct layers, each designed to ensure modularity, reliability, and compliance: 

- UI experiences  

  This layer provides intuitive user interfaces and controls that enable configuration, monitoring, and consumption of SQA outputs. The unified Dataverse interface implements these experiences as UI components, ensuring consistency and ease of use. 

- Orchestration layer  

  This layer triggers and manages agent workflows. It uses Power Automate flows. The **Sales Backend Service** hosts business logic, data integration, and flow control, providing centralized governance and operational reliability. 

- Data layer  

  At the core of SQA's data management is Dataverse, which serves as the primary data store. It houses sales records, configuration data, and the results of agent runs. Additionally, agents access email data through Dataverse through the server-side synchronization feature, ensuring secure and compliant data handling.  

- Agent layer  

  Agents form the crux of SQA functionality. They act as intelligent intermediaries between Power Platform and Azure OpenAI, enabling advanced AI-driven capabilities while maintaining enterprise-grade security and control. The following agents are available today, each designed to streamline specific stages of the sales qualification process:  

    1. **TCP Prefill Agent**  

        Generates the [target customer profile](/dynamics365/sales/sales-qualification-agent-concepts#what-is-the-target-customer-profile-and-how-is-the-fit-determined) (qualification criteria) based on the company and product value proposition that the administrator defined. This helps the administrator set up the criteria for which leads the agent considers a good fit for the team.

    1. **Research agent**  

        Conducts account-level research to provide deeper insights into the lead's organization.  

    1. **Competitor agent**  

        Analyzes the competitors and drafts talking points the seller can use when engaging this lead, using any preconfigured knowledge such as battle cards.  

    1. **Email validation agent**  

        Verifies the accuracy and validity of the lead's email address.  

    1. **Readiness agent**  

        Evaluates leads against predefined qualification criteria and intent to purchase expressed during email engagement, to determine which leads are hot.  

    1. **Outreach agent**  

        Drafts a personalized outreach email based on the research agent's findings. It then initiates the first point of contact with potential customers when the agent is set up in research + engage mode.  

    1. **Engage autonomous agent**  

        In research + engage mode, manages ongoing email engagement with potential customers in a fully automated manner. It can answer questions the lead asks about your products. In exchange, it can ask questions to assess the lead's budget, ability, need, and timeline to buy (also known as BANT).  

    1. **Summary synthesizer**  

        When the agent hands off a lead to a seller or disqualifies a lead, it assesses and summarizes a lead's sales readiness. 

## Dataflow

The following diagram illustrates the data flow for *Initial Outreach*, which is the first time that SQA emails the lead after validating their email and performing thorough research to help personalize the outreach.  

:::image type="content" source="media/sales-qualification-agent-flow.png" alt-text="Screenshot of the Initial Outreach data flow diagram from email validation and research to personalized outreach.":::

The second diagram illustrates the process for the **Engage agent**.  

:::image type="content" source="media/sales-qualification-agent-flow-two.png" alt-text="Screenshot of the Engage Agent data flow diagram showing automated email engagement and lead qualification.":::

As shown, all data remains within the Power Apps boundary until the point of agent invocation. Access to data in Dynamics 365 Sales, both read and write, is managed through real-time integrations with Dataverse and Copilot Agents, ensuring secure and compliant operations.

Importantly, SQA doesn't create or maintain copies of data. Instead, it only passes the relevant fields as input to the Copilot Agents for processing. This approach minimizes data exposure and aligns with enterprise security best practices.

> [!NOTE]
> Data never leaves the enterprise boundary. Minimal controlled payloads are sent to Azure OpenAI for inference, but these payloads aren't used to train the foundation models. Your prompts (inputs), completions (outputs), and embeddings aren't shared with other customers. These payloads are strictly limited to the fields necessary for the agent's function, and all transfers occur over secure, encrypted channels.

The subsequent section describes how these agents interface with Azure OpenAI, including safeguards that protect sensitive information during AI-driven operations.  

## Azure OpenAI Service and data residency

This section provides more information about data residency.  

### Where the data resides and is processed

The Copilot agents form the SQA's "brain" and are powered by [Microsoft Foundry](/azure/ai-foundry/foundry-models/concepts/models-sold-directly-by-azure) that includes Azure OpenAI models, Microsoft's enterprise version of OpenAI's large-language models. All SQA processing goes through Azure's secure endpoints so that, unlike consumer ChatGPT, your data never leaves Microsoft's network to a public server. The agent calls Azure OpenAI in the cloud region associated with your Dynamics 365 data residency. If your region, such as parts of South America or Asia, doesn't yet have a local Azure OpenAI instance, you can explicitly [opt-in to allow temporary data transfer](/microsoft-sales-copilot/copilot-data-movement) to the nearest supported region's endpoint. You make this request in the Power Platform admin center. If you choose not to opt in, the Copilot and agent features remain disabled to avoid any cross-border data flow. In all cases, Azure OpenAI processes your data with full encryption in transit and at rest, and no data is stored long-term outside your tenant.  

### Data use for inference not training

Azure OpenAI doesn't use your inputs or outputs to train the underlying AI models – your business data remains private. Learn more at [Sales app data movement across geographies](/microsoft-sales-copilot/copilot-data-movement). Also, Azure OpenAI implements automatic content filters and abuse detection. Prompts or responses that trigger policy violations might be retained for up to 24 hours for automated review, with human review only if required by the system's flags. The agent has no human from Microsoft that reads your sales data – the process is governed by strict privacy guardrails.

### Authentication and access control

The SQA uses Microsoft Entra ID authentication. [The agent is set up as an app user in Dataverse](/dynamics365/sales/configure-requirements-for-sqa-agent#create-an-app-user-in-dataverse-and-assign-aisalesperson-role). It has its own ID and security roles attached to it, including the required *AISalesperson* role, which the admin can customize. The agent uses these permissions when performing actions such as querying and updating data records. The output of the agent (such as research insights) that the sellers see is governed by the seller's permissions, based on their security roles. This way, the sellers can't view information that they don't have permission to read.  

No other data repository is created. Instead, the agent interacts with Dynamics 365 through standard APIs, mirroring the behavior of the user. All read and write operations occur within the same security and compliance boundaries as the user's activities.  

For email communications, the system sends messages by using the application user account associated with the mailbox configured for the agent.

### Data access and storage

The SQA is designed with a minimal data footprint. It doesn't siphon your Dynamics 365 or mailbox data into an external database. Instead, the agent does the following:

- When the agent *reads* data (for example, it retrieves an email thread to gauge a lead's interest level), it processes that data in memory to generate an insight and immediately discards it after analysis. 

- When the agent *accesses* data from an external knowledge source or connector in Copilot Studio, it uses the administrator's ID (the one who set up that knowledge source) to retrieve the requested information. If the retrieved insight is part of the research output that it's configured to generate, it stores that insight in Dataverse, in custom tables generated for the sole purpose of the agent, so it can be loaded on the research page.  

- When the agent *creates* or updates data, it writes back into Dynamics 365  through supported mechanisms. For example, if the agent sends an email, that email is stored in Exchange like any other sent item. If it generates a lead score or qualification recommendation, that score or recommendation can be written to a field in Dynamics 365 for your team to review. 

- Any email data the agent reads is currently limited to just the emails it sends and receives via its own mailbox, to which it already has the necessary permissions. 

In short, most of your data stays where it already is – the agent just "reads" and "writes" via secure API calls. As a result, the existing compliance, audit, and retention policies you have in place for Dynamics 365 and Office 365 remain applicable. For instance, if you have a DLP policy that prevents customer credit card numbers from being stored in Dynamics 365, the agent doesn't override that. If you have email retention policies or encryption, the agent's actions comply because it uses the same Exchange/Graph interface.  

## Monitoring  

All interactions that the agent makes can be logged and monitored through existing tools. This way, three key personas can monitor what's going on as described in the following list:  

- **IT**  

  All agent runs are stored in the *Sales Agent Runs* table in Dataverse so that the IT department can review the steps the agent took for each lead. Email logs show that the agent (acting as an app user) sent an email, and audit logs can trace actions in Dynamics 365. This way, IT can monitor the agent's activity and quickly address any aberrations or security issues.  

  > [!TIP]
  > Here's a takeaway for Security/IT roles: The SQA is built on Microsoft's secure, compliant infrastructure and is designed to conform to your enterprise policies.  

- **Supervisor**  

  AI hub is a new area Dynamics 365 Sales \> Settings that enable [supervisors and admins to monitor the agent's activities](/dynamics365/sales/monitor-leads-by-sales-qualification-agent) in a user friendly manner. They can see insights such as leads processed and qualified by the agent and the Sankey view of how many leads are in each stage.  

- **Sellers**  

  By default, the agent creates a new view for sellers in their leads grid, called [Leads handed over by the AI agent](/dynamics365/sales/use-sales-qualification-agent). This way, the sellers stay focused only on leads that the agent recommends actioning. When the agent reviews a handed-over lead, it provides sellers with clear visibility into the current status of each lead it has acted upon. Sellers can easily monitor progress and gain actionable insights, including the reasons behind a lead's current status and contributing factors. This transparency helps sellers understand outcomes and make informed decisions for next steps. For other leads that aren't handed off, the seller or a supervisor can use another view, **Leads disqualified by the agent**. Sellers can continue using their existing views and workflows as well, without needing to switch to these new views.  

## Consent

When the agent engages autonomously with your leads, it gives them a way to control communications and opt-out/unsubscribe if they need to. [The built-in consent management system](/dynamics365/sales/consent-management-overview) enables you to manage opt-outs separately for the agent so that other communications from your company aren't affected. Consent logs are available for auditing.

## Customer managed key

SQA stores data in Dataverse and supports *customer-managed encryption*. By default, all data at rest is encrypted with a Microsoft-managed key (MMK). Some organizations decide to increase the security of their data-at-rest by using customer-managed key (CMK) encryption. That approach allows the organization to manage the database encryption key associated with the Dataverse environment. Learn more about CMK encryption at [Manage your customer-managed encryption key](/power-platform/admin/customer-managed-key).  

## Lockbox

SQA stores data in Dataverse. If an organization enables Customer Lockbox policies on the environment where Copilot is enabled, administrators receive an approval request for data access when support requests to access data.  

Most operations, support, and troubleshooting that Microsoft performs don't require access to customer data. However, when access to data is required, and the environment uses Customer Lockbox, a data access request is sent to the organization for approval. 

Learn more about Customer Lockbox at [Securely access customer data using Customer Lockbox in Power Platform and Dynamics 365](/power-platform/admin/about-lockbox).

## Bing search

SQA uses Bing to crawl the public web for its lead research, specifically to uncover insights about the lead's company. It does this research for its default insights, such as strategic priorities, finances, and news, and for any insights you configure as custom insights. SQA ensures privacy by never sharing personal or confidential data with Bing. When SQA uses Bing for research, only the search query (a dynamically generated query each time) is sent. User identifiers, such as names, tenant IDs, or other sensitive data, are never sent. You generate queries based on business context you configure, such as company names, websites, and value propositions. Queries might include lead-related details such as company name or industry. No sensitive customer data, credentials, or internal information is transmitted. All queries are anonymized. While Bing might process them in global data centers, the content remains limited to publicly relevant terms for research purposes.  

## Related content

- [Download the role-specific Sales Qualification Agent guidance](https://aka.ms/sqaguidance)  
- [Microsoft's AI Agent adoption framework](/azure/cloud-adoption-framework/ai-agents/technology-solutions-plan-strategy)  
- [Sales Qualification Agent overview](/dynamics365/sales/sales-qualification-agent)  
- [Understand the Sales Qualification Agent concepts](/dynamics365/sales/sales-qualification-agent-concepts)  
