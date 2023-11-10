---
title:  Environment lifecycle scenarios
description: In this article, we explore the various states during an environment lifecycle, from creation until decommissioning.
author: abunduc-ms
ms.author: abunduc
ms.date: 02/25/2023
ms.topic: conceptual

---

# Environment lifecycle scenarios

Environments transition through various states before they're decommissioned. Some of these transitions are natural to support application lifecycle management (ALM), but there could be business, compliance, and technical reasons that trigger these transitions. As described earlier, environment-related changes are complex, and they require significant planning and (usually) downtime.

There are multiple factors that could trigger environment transitions, ranging from the overall ALM process to changes in business structure. Let's explore the various types of transitions that you might see throughout the lifecycle of an environment. These transitions could require admins with appropriate roles to self-serve and, in some cases, seek assistance from product support teams.

## Creation

An organization might create a new environment for several reasons. The purpose of the environment should be well defined and understood before its creation. Considerations include the environment type, country or region, apps required, access security groups, URL and agreed-upon naming conventions, and tiers and service levels.  

## Environment transition

An organization might have multiple types of environments, each targeting specific use cases, including trial environments, default environments, sandboxes, and production environments. Be aware of possible transitions between types, as there could be limitations and implications to the service. For instance, in customer engagement apps, changing a production environment to a sandbox might change the data-retention policy and applicable service-level agreements (SLAs).

## Copy

Most often used in troubleshooting scenarios, environment copy lets you create a copy of an existing environment with all its data or only the customizations and configuration. Be aware of the effect of storage capacity and compliance requirements, which could restrict copying of customer data. Sometimes copy is also used to support ALM instead of using the source control. This pattern should be avoided, and environments should never be used as a repository for code and customizations.

## Restore

Sometimes, you might need to restore an environment. Depending on the type of environment and service, there could be several restore points or a feature allowing you to restore an environment to a precise time. Restore could lead to data loss, so it's not really an option for production environments unless performed in a limited window.

## Geo-migration

Changes in regulations might trigger a geo-migration. Another example is a need to move an environment to a lower-latency region for a better user experience. It's not a common request and it involves more effort from the project team and the business. It would normally involve creating a copy of an environment and then physically moving it to a different region. It almost certainly will involve downtime for users, and requires approval from the compliance and security teams. It also could lead to change in service URLs and IP ranges, affecting integrations and network security.

## Tenant-to-tenant move

Any change in tenant strategy might trigger a request to move an environment from one customer tenant to another. it's not a common request and will require several steps before the actual move. Most importantly, users must be correctly mapped between tenants and the record ownerships must be restored. It might require a regional migration first and could involve several hours of downtime.

## Merge environments

It takes substantial planning to merge multiple environments into a single environment, and it can be extraordinarily complex. Merging involves the data model and the processes in the app. Next comes the actual data with necessary transformations and deduplication, then the security model and, finally, the integrations.

## Split environments

You might have to split an environment if an organization transitions to a multiple-environment strategy. The task could involve provisioning new environments and migrating all previous customizations, along with the relevant data subset. For customer engagement apps, alternatively, an organization could create the split by copying the environment and moving it to another region.

## Migration from on-premises to cloud

Many organizations with on-premises infrastructure are now considering a move to the cloud due to the evolving needs of businesses and the potential and benefits of the cloud. Such a move involves creation of new cloud environments, running a cloud-compatibility assessment, moving the solution components and data, and redesigning parts of the solution to take advantage of the latest cloud features. To help speed up this process, Dynamics 365 services offer a "lift and shift" solution to move data into the cloud. It's fast and cost-effective, but by moving a legacy solution into the cloud, organizations may miss an opportunity to optimize their processes. Learn more at [Overview of Dynamics 365 migration program for on-premises solutions](/dynamics365/get-started/migration/migration-overview)

## Administration mode

[Administration mode](/power-platform/admin/admin-mode) or [maintenance mode](/dynamics365/fin-ops-core/dev-itpro/deployment/maintenanceoperationsguide-newinfrastructure) can be used for maintenance when only selected users can access the environment. Before you start, assess the systems that will be affected by putting an environment in administration or maintenance mode, such as a public-facing portal that connects to the environment.

## Deletion

Deleting an environment removes all the data and customizations, as well as the option to restore and recover. The process of decommissioning or deleting an environment needs gated approvals.

## Next steps

- Review recommendations for Azure Active Directory at [Tenant strategy](environment-strategy-tenant-strategy.md)  
- Find a checklist at [Environment strategy checklist](environment-strategy-checklist.md)  
- Get an overview at [Environment strategy](environment-strategy-overview.md)  
