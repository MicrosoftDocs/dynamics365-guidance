---
title: Event Registration Agent
description: Uses AI to process inbound email replies to event invitations, automatically creating registration, guest, or decline records in Customer Insights - Journeys. The agent eliminates the need for manual registration forms.
author: ecaraza
ms.author: emancar
ms.date: 05/11/2026
ms.topic: concept-article
---

# Agent for event registration

***Applies to***: ***Dynamics 365 Customer Insights - Journeys***

This template creates an agent that transforms the event registration experience by enabling customers to register, add guests, or decline event invitations directly by replying to an email - with no external form required. The agent uses AI to detect intent from email replies, automates the creation of registration records in Dynamics 365 Customer Insights - Journeys via Dataverse APIs, and emits journey triggers to dispatch confirmation communications automatically.

> [!NOTE]
> The agent templates aren't yet available for download. If you're interested in the customer insights agent templates, [fill in this form](https://aka.ms/ci-agent-templates).

## Overview

The Event Registration agent removes the friction of manual registration forms by processing inbound email replies to event invitations. The agent uses AI-powered intent detection to classify each reply as a registration, a guest seat reservation, a decline, or a non-actionable message. It then calls Customer Insights and Dataverse APIs to create the appropriate records, such as attendee registrations, guest registrations, or event decline entries that link to the correct event, session, and contact. When details are missing, the agent prompts the customer via email or chat before proceeding. Once registration or decline records are written, the agent emits Dynamics 365 triggers to initiate confirmation or suppression journeys automatically, ensuring customers receive accurate follow-up communications and event managers gain reliable attendance intelligence.

## Key benefits

- Formless, email-based registration eliminates repetitive data entry for customers who already received a personalized invitation.
- Guest seat reservation without new contact creation supports flexible attendance scenarios in a single email reply.
- Automated decline capture writes standardized records to Dataverse, enabling suppression segments that stop unnecessary follow-up communications.
- AI intent detection and guided clarification collects only the minimum information needed before executing any action.
- Journey trigger emission ensures confirmation and follow-up communications are dispatched automatically without manual intervention.

## Scenarios

- Customer registers for an event by replying to an invitation email, with the agent extracting event and contact context from the original message and creating the registration record automatically.
- Attendee reserves other seats for guests in a single reply; the agent creates guest registration records linked to the primary contact without generating new contact records.
- Customer declines an event invitation via email; the agent records the decline in Dynamics 365 tables, enabling the event manager to use it as a journey suppression signal and improve capacity forecasting.
- Event manager configures invitation emails so that customer replies are routed to the agent, removing the need for manual form-based registration workflows.

## Industries

- Professional Services
- Associations and Membership Organizations
- Financial Services
- Any industry using Dynamics 365 Customer Insights - Journeys for event-driven customer engagement

## Required products and services

- Dynamics 365 Customer Insights - Journeys
- Microsoft Dataverse
- Microsoft Copilot Studio
- Copilot Studio Credits Capacity
- Power Platform services
- Microsoft 365 (for email channel integration)

## Related content

- [Event Management Agent](event-management-agent.md)  
- [Customer Insights agent templates](customer-insights-agent-templates.md)  
- [Introduction to the Dynamics 365 agent templates](overview.md)  
- [Dynamics 365 Customer Insights - Journeys overview](/dynamics365/customer-insights/journeys)
- [Microsoft Copilot Studio documentation](/microsoft-copilot-studio/)
