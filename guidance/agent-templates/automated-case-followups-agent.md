---
title: "Automated Case Follow-ups Agent"
description: "Reduce manual communication overhead with automatic follow-up tracking and email generation"
author: aloking
ms.date: 02/03/2026
ms.topic: how-to
ms.service: dynamics-365-customer-service
---

# Automated Case Follow-ups Agent

Reduces manual communication overhead and streamlines case closure by automatically tracking cases needing attention and sending periodic follow-up emails based on SLA criteria or business rules. Eliminates administrative burden of monitoring aging cases and manually drafting follow-up communications.

## Overview

Agent autonomously monitors cases matching configured conditions and sends periodic follow-up emails to customers awaiting response. Administrators define rules specifying conditions (case age, status, category), automation level, number of follow-ups, wait times between attempts, and email templates. Agent drafts contextual follow-up emails requesting customer response. If no response after final follow-up, agent automatically populates resolution details and closes case.

## Key benefits

- Automated follow-up email generation and sending
- SLA-driven tracking of cases requiring attention
- Configurable follow-up frequency and number of attempts
- Full or semi-automation modes (autonomous sending or representative review)
- Automatic case closure when customers don't respond after final follow-up
- Rule-based triggering using conditions (case age, status reason, category, product)
- Reduces case backlog and improves closure rates
- Email template customization per rule

## Scenarios

- Pending customer response cases
- On-hold case monitoring
- SLA breach prevention
- Awaiting information follow-ups
- Abandoned case closure
- Post-resolution satisfaction checks

## Supported channels

- Email

## Industries

- All sectors requiring systematic case follow-up and closure management

## Licensing requirements

- Dynamics 365 Customer Service or Contact Center license
- Microsoft Copilot Studio
- Copilot Studio Credits Capacity

## Next steps

- [Configure service agents](/dynamics365/customer-service/configure-agents)
- [Test your agent deployment](/dynamics365/customer-service/test-agents)
- [Monitor agent performance](/dynamics365/customer-service/agent-analytics)

## Related content

- [Service agent templates overview](service-agent-templates.md)
- [Dynamics 365 Customer Service overview](/dynamics365/customer-service/overview)
- [Microsoft Copilot Studio documentation](/microsoft-copilot-studio/)
