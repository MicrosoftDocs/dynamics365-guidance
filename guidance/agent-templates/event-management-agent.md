---
title: Event Management Agent
description: Learn about the template you can use to automate event lifecycle tasks, such as creating events and sending personalized invitations to contact segments, by reading configurable, natural-language operation instructions.
author: ecaraza
ms.author: emancar
ms.date: 05/11/2026
ms.topic: concept-article
---

# Agent for event management

***Applies to***: ***Dynamics 365 Customer Insights - Journeys***

This template creates an agent that automates event management tasks by using a model-first, operations-driven approach. The agent reads its available operations from a Dataverse table and uses natural language instructions to plan and execute tasks - such as creating events and distributing invitations - directly within Dynamics 365 Customer Insights - Journeys. All actions occur in the user's context and respect the organization's policies for role-based security and governance.

> [!NOTE]
> The agent templates aren't yet available for download. If you're interested in the Customer Insights agent templates, [fill in this form](https://aka.ms/ci-agent-templates).

## Overview

The agent for event management automates routine event operations by combining a configurable operations catalog stored in Dataverse with the Dataverse MCP server and Microsoft Copilot Studio. Users interact with the agent through Microsoft 365 Copilot or Microsoft Teams, describing what they want to do. The agent identifies the appropriate operation, gathers the necessary inputs, and executes the required steps - from creating event records through to sending personalized invitations to contact segments via Customer Insights - Journeys triggers.

> [!NOTE]
> We provide this agent template to help you in implementation projects. Adapt the agent template to fit the relevant application lifecycle management (ALM) policies, development standards, and guidelines for Responsible AI.

## Key benefits

- Model-first, operations-driven execution with a customer-maintained catalog of approved actions
- Tool-based integration with the Dataverse MCP server for both read and write operations
- End-user credential enforcement to ensure Dataverse role-based access control is respected
- Configurable, natural-language operation instructions that you can extend without code changes
- Seamless availability through Microsoft 365 Copilot and Microsoft Teams channels

## Scenarios

- Quickly create an event record with minimal inputs, with the agent prompting for any missing details such as start date, end date, or duration.
- Automatically publish a newly created event to make it live in Dynamics 365.
- Send personalized event invitations to a segment of contacts by triggering a journey in Customer Insights for each member of the selected segment.
- Guide users through selecting an appropriate contact segment.
- Extend the agent with additional operations by adding new records to the Event Operations table in Dataverse with no redeployment required.

## Industries

- Events and Conferences
- Professional Services
- Associations and Membership Organizations
- Any industry using Dynamics 365 Customer Insights - Journeys for event marketing

## Required products and services

- Dynamics 365 Customer Insights - Journeys
- Microsoft Dataverse
- Microsoft Copilot Studio
- Copilot Studio Credits Capacity
- Power Platform services (Power Automate for the invitation trigger flow)
- Microsoft 365 Copilot (for Teams and Microsoft 365 Copilot channel deployment)

## Related content

- [Event registration agent](event-registration-agent.md)  
- [Customer Insights agent templates](customer-insights-agent-templates.md)  
- [Introduction to the Dynamics 365 agent templates](overview.md)  
- [Event planning and management](/dynamics365/customer-insights/journeys/event-management)  
- [Dynamics 365 Customer Insights - Journeys overview](/dynamics365/customer-insights/journeys)
- [Connect to Dataverse with Model Context Protocol](/power-apps/maker/data-platform/data-platform-mcp)  
- [Microsoft Copilot Studio documentation](/microsoft-copilot-studio/)
