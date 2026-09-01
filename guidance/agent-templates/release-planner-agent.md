---
title: Roadmap Planner Helper Agent
description: Learn about the agent template that can help you streamline Dynamics 365 roadmap planning with automated feature discovery, impact analysis, and work item creation.
author: ahmetziyayildirim
ms.author: ahyildir
ms.date: 08/26/2026
ms.topic: concept-article
---

# Agent for roadmap planning

***Applies to***: ***Dynamics 365 Supply Chain Management, Dynamics 365 Finance, Dynamics 365 Commerce***

This agent streamlines Dynamics 365 roadmap planning by autonomously searching upcoming features, providing detailed status and business value analysis, and automating work item creation in project management tools. It reduces the manual effort of tracking continuously delivered updates, ensures teams stay informed on feature availability, and improves traceability from roadmap to implementation.

> [!TIP]
> Get the agent template from the [Release Planner](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Agents/Implementation%20Agents/Release%20Planner) folder in the Dynamics 365 FastTrack Implementation Assets repo on GitHub. The GitHub folder still uses the earlier *Release Planner* name.

## Overview

The roadmap planner helper agent integrates with Microsoft's official roadmap sources to search, retrieve, and analyze upcoming Dynamics 365 features across apps such as Supply Chain Management, Finance, and Commerce. Because Microsoft now delivers features continuously rather than in fixed release waves, the agent helps teams keep pace with a roadmap that changes throughout the year. It provides contextual recommendations based on current feature status, availability timelines, and geographic or language availability. It supports visual analysis of roadmap data, identifies high-priority features, and automates the creation of work items in Azure DevOps or Jira with step-by-step implementation details for testing and deployment cycles.

## Key benefits

- Automated feature discovery across the Dynamics 365 roadmap
- Detailed feature status, timeline, and business value analysis
- Roadmap planning recommendations based on current dates and availability timelines
- Geographic and language availability insights per feature
- Automated work item creation in Azure DevOps and Jira with implementation steps
- Visual analysis of roadmap data with priority identification
- Integration with official Microsoft documentation and roadmap resources
- Adaptable architecture with support for integrating other MCP tools
- Lightweight deployment with minimal setup requirements

## Scenarios

- Dynamics 365 Supply Chain Management, Finance, and Commerce roadmap tracking
- Feature impact assessment and business value analysis
- Compliance and technical team release readiness reviews
- Automated test cycle work item generation
- Cross-app roadmap planning coordination
- Geographic and language feature availability checks
- Roadmap briefing and stakeholder reporting

## Supported channels

- Chat

## Industries

- Financial Services
- Manufacturing
- Retail
- Distribution
- Public Sector
- Professional Services
- Supply Chain & Logistics

## Licensing requirements

- Dynamics 365 Finance, Supply Chain Management, or Commerce license
- Microsoft Copilot Studio
- Copilot Studio Credits Capacity
- Azure DevOps or Jira (optional, for work item creation)

## Related content

- [Implementation agent templates overview](implementation-agents-overview.md)
- [Dynamics 365 release plans](/dynamics365/release-plans/)
- [Microsoft Copilot Studio documentation](/microsoft-copilot-studio/)
