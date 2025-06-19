---
title: Get your production environment ready for deployment
description: Learn how to prepare your production environment for deploying Dynamics 365 solutions, including security, configuration, integration, and tuning tasks.
ms.date: 01/31/2024
ms.topic: concept-article
author: vaniusca
ms.author: vaniaf
ms.custom:
  - evergreen
  - ai-seo-date: 01/30/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
  - bap-template
content_well_notification: AI-contribution
---

# Get your production environment ready for deployment

Before you go live with your Dynamics 365 solution, you need to make sure that your production environment is set up correctly. The way you create your production environment depends on the apps you're deploying. For some apps, you can start with a basic environment and add features later. For others, you need to follow a specific process to create the environment.

No matter how you create it, you need to complete some tasks before you can deploy your solution. These tasks help you size your environment and optimize its performance and scalability.

Different apps have different requirements and best practices for going live. Check out the guidance for [finance and operations apps](prepare-to-go-live.md#go-live-with-finance-and-operations-apps) and [customer engagement apps](prepare-to-go-live.md#go-live-with-customer-engagement-apps), respectively, at [Prepare to go live](prepare-to-go-live.md).

## What to do before deployment

Plan ahead how you'll get your environment ready for production. This way, you can avoid problems at the last minute and have more time to make sure that everything works well. Your plan should include the following activities:

- Install the apps and update them to the latest version.

- Create users in the right environments and give them security roles.

- Create security groups for each environment and add users to them.

- Get approval from stakeholders on the security and compliance strategy. This includes penetration testing if needed, compliance requirements, and data location requirements.

- Tune the environment if needed.

- Create, import, and check configurations.

- Run and check integrations.

- Complete any app-specific configurations that take time. For example, if you want to integrate with an email service like Outlook, it might take longer for users with large mailboxes.

Remember that getting your production environment ready is also important for other activities during the [cutover](prepare-go-live-cutover-strategy.md). For example, you can't move and verify the final data until you have a production environment to do it in.

## Next steps

- [Plan your cutover to the new solution](prepare-go-live-cutover-strategy.md)
- Use the Success by Design [go-live checklist](prepare-go-live-checklist.md) to make sure that you don't miss any important tasks for go-live
- Read the [case study](prepare-go-live-case-study.md) for an example of a successful go-live project
