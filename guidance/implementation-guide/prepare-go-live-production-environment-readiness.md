---
title: Prepare production environments for successful deployment of Dynamics 365 solutions
description: Learn how to prepare the production environment for the successful deployment of a Microsoft Dynamics 365 solution, including assigning security roles, setting configurations, and running integrations.
ms.date: 06/06/2023
ms.topic: conceptual
author: vaniusca
ms.author: vaniaf
ms.custom:
 - ai-gen-docs-bap
 - ai-gen-desc
 - ai-seo-date:08/23/2023
 - bap-template
---

# Prepare production environments for successful deployment of your Dynamics 365 solutions

It's critical to make sure the production environment is ready before your Dynamics 365 solution goes live. Your [strategy for preparing a production environment](environment-strategy-overview.md) depends on the applications in the scope of the deployment. For some applications, you can create the production environment from an initial phase without any dependencies. For other applications, you must follow a formal process to create the production environment.

Regardless of how you create it, you must complete several milestones before you can deploy the production environment. These milestones help with sizing the environment and its effect on factors like the environment's performance and scalability.

Slightly different recommendations apply, depending on the Dynamics 365 apps that are part of the project. Review the guidance for [going live with finance and operations apps](prepare-go-live-finance-and-operations-apps.md) and for [going live with customer engagement apps](prepare-go-live-dynamics-365-customer-engagement.md).

## Readiness activities

Establish a plan for how you'll prepare the environment for production. Planning ahead avoids last-minute issues and provides more time to make sure tasks are completed successfully. Your plan should include the following activities:

- Deploy applications and update them to the latest version.
- Create users in the environments to which they should have access and assign security roles.
- Assign security groups to environments and add users to them.
- Get stakeholder sign-off on the security and compliance strategy, including penetration testing when applicable, compliance requirements, and data sovereignty requirements.
- Tune the environment when applicable.
- Create, import, and validate configurations.
- Run and validate integrations.
- Make sure specific configurations for applications are completed ahead of time, especially configurations that take a while to complete. For example, setting up an integration with an email engine such as Outlook might depend on the size of a user's mailbox, with bigger mailboxes taking longer to complete.

Finally, keep in mind that production environment readiness is also a significant dependency for other activities during the [cutover](prepare-go-live-cutover-strategy.md). For example, the final data can't be migrated and validated until there's a production environment in which to start those activities.

## Next steps

- Review the [cutover process](prepare-go-live-cutover-strategy.md).
- Review specific guidelines for [finance and operations apps](prepare-go-live-finance-and-operations-apps.md) and [customer engagement apps](prepare-go-live-dynamics-365-customer-engagement.md).
- Review the [go-live checklist](prepare-go-live-checklist.md).
