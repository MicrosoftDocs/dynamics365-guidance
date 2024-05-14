---
title: Manage the lifecycle of your Dynamics 365 environments
description: Learn about the states and transitions of your Dynamics 365 environments, from creation to deletion, and the reasons for and implications of each change.
author: abunduc-ms
ms.author: abunduc
ms.date: 01/16/2024
ms.topic: conceptual
ms.custom:
  - ai-seo-date: 01/16/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Manage the lifecycle of your Dynamics 365 environments

Your Dynamics 365 environments can go through different states and transitions before they're deleted. Some of these changes are natural to support application lifecycle management (ALM), but others can be triggered by business, compliance, or technical reasons. As we mentioned in earlier sections of this guide, environment-related changes are complex and they require careful planning and often downtime.

Many factors can trigger environment changes, ranging from the overall ALM process to changes in business structure. Let's explore the various types of changes that you might see throughout the lifecycle of an environment. These changes might require admins with appropriate roles to self-serve or seek assistance from product support teams.

## Creation

You might create a new environment for several reasons. The purpose of the environment should be clear and understood before you create it. You should consider the following aspects:

- The environment type, such as trial, sandbox, or production
- The country or region where the environment is located
- The apps that you need in the environment
- Access and security groups
- The URL and naming conventions
- Tiers and service levels

## Environment transition

You might have different types of environments for different use cases, such as trial environments, default environments, sandboxes, and production environments. Be aware of the possible transitions between types, because they could have limitations and implications for the service. For example, in customer engagement apps, changing a production environment to a sandbox might change the data retention policy and service-level agreements (SLAs).

## Copy

You can use environment copy to create a copy of an existing environment with all its data or only the customizations and configuration. It's often used for troubleshooting. Be aware of the effect on storage capacity and compliance requirements, which could restrict copying of customer data. Sometimes copy is also used to support ALM instead of using source control. This pattern should be avoided, and you should never use environments as a repository for code and customizations.

## Restore

Sometimes, you might need to restore an environment. Depending on the type of environment and service, you might have several restore points or a feature that lets you restore an environment to a specific time. Restore could lead to data loss, so it's not a good option for production environments unless you do it in a limited window.

## Geo-migration

You might need a geo-migration if there are changes in regulations or if you want to move an environment to a lower-latency region for a better user experience. This isn't a common request and it involves more effort from the project team and the business. It usually involves creating a copy of an environment and then physically moving it to a different region. It almost certainly will involve downtime for users, and requires approval from the compliance and security teams. It also could change the service URLs and IP ranges, affecting integrations and network security.

## Tenant-to-tenant move

You might need to move an environment from one customer tenant to another if your tenant strategy changes. This isn't a common request and it requires several steps before the actual move. Most importantly, you must map the users correctly between tenants and restore the record ownerships. You might also need a regional migration first and it could involve several hours of downtime.

## Merge environments

You might need to merge multiple environments into a single environment if your business structure or environment strategy changes. It requires planning and it can be extraordinarily complex. First, you merge the data model and the processes in the app, then the actual data with necessary transformations and deduplication, then the security model and, finally, integrations.

## Split environments

You might need to split an environment if you transition to a multiple-environment strategy. This could involve provisioning new environments and migrating all the previous customizations, along with the relevant data subset. For customer engagement apps, you could also create the split by copying the environment and moving it to another region.

## Migration from on-premises to cloud

Many organizations with on-premises infrastructure are now considering a move to the cloud because of the evolving needs of businesses and the potential and benefits of the cloud. Such a move involves creating new cloud environments, running a cloud-compatibility assessment, moving the solution components and data, and redesigning parts of the solution to take advantage of the latest cloud features.

To help speed up this process, Dynamics 365 services offer a "lift and shift" solution to move data into the cloud. It's fast and cost-effective, but by moving a legacy solution into the cloud, you might miss an opportunity to optimize your processes. Learn more at [Migrate to Dynamics 365 online from Dynamics on-premises products](../migrate/overview.md).

## Administration mode

[Administration mode](/power-platform/admin/admin-mode) or [maintenance mode](/dynamics365/fin-ops-core/dev-itpro/deployment/maintenanceoperationsguide-newinfrastructure) can be used for maintenance when only selected users can access the environment. Before you start, assess the systems that will be affected by putting an environment in administration or maintenance mode, such as a public-facing portal that connects to the environment.

## Deletion

Deleting an environment removes all the data and customizations, as well as the option to restore and recover. The process of decommissioning or deleting an environment needs gated approvals.

## Next steps

- Get [product-specific guidance](environment-strategy-guidance-product.md)
- Follow the [environment strategy checklist](environment-strategy-checklist.md)
- Read a [case study](environment-strategy-case-study.md) of a company that learned the importance of a good environment strategy
