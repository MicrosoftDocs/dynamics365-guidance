---
title: Best practices for Dynamics 365 environment maintenance
description: Learn how to plan and execute maintenance tasks for your Dynamics 365 environment, such as managing user access, security roles, archiving, and deletion.
author: taksatoms
ms.author: edupont
ms.date: 01/30/2024
ms.topic: best-practice
ms.custom:
  - evergreen
  - ai-seo-date: 01/30/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Best practices for Dynamics 365 environment maintenance

As a system administrator, you want to protect your solution and keep it running smoothly. In a cloud environment, many maintenance jobs are automated for you. But you still need a strategy to configure and schedule these jobs according to your needs. Sometimes, you might also need to do some tasks manually. In this article, we'll show you how to plan and execute maintenance tasks for your Dynamics 365 environment.

## User access and security

Your business and technical teams might change over time. New employees join, existing ones move or leave. As an administrator, you need to work with other teams to manage user access and assign the right licenses and security roles. You might want to delegate some of these tasks to business and IT managers who know their users better.

Your organization's data is one of the most valuable assets that you're responsible for safeguarding. Power Apps and Power Automate make it easy to build apps and automation that use that data. But apps and automation can also connect to multiple data sources and services. Some of these might be external, or even social networks. Users might not realize the risk of exposing organizational data to unauthorized parties.

We recommend that you create [data loss prevention (DLP) policies](/power-platform/admin/wp-data-loss-prevention) to prevent users from accidentally sharing sensitive data. You can apply DLP policies at the environment level or at the tenant level. This gives you flexibility to balance protection and productivity. For tenant-level policies, you can choose which environments to include or exclude. For environment-level policies, you can set them up one by one.

Learn more:

- [Manage users and licenses in finance and operations apps](/dynamics365/fin-ops-core/dev-itpro/sysadmin/tasks/create-new-users).
- [Manage users and licenses in customer engagement apps](/microsoft-365/admin/add-users/?view=o365-worldwide&preserve-view=true).
- [Use Microsoft Entra groups to simplify user management and provisioning](/power-platform/admin/manage-group-teams).

[!INCLUDE [azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

## Dynamics 365 environment management

Dynamics 365 backs up your databases automatically and keeps them for a set number of days. This means that you can restore your database from any backup if something goes wrong. The backup and restore system is reliable and easy to use.

But if you want to take backups manually (for example, before deploying a new release of your solution), you might need to do it yourself. You should follow your organization's environment strategy when you do these tasks.

The backup and restore operation can take a long time depending on the size of the backup. If a solution import to customer engagement apps fails, it might be faster to fix the import issue than to restore from a backup.

## Data management

Data is central to all applications. It drives business decisions through analytics and artificial intelligence. It also shows you the health of your system and what you need to do for maintenance. You should be proactive in planning and strategizing around data maintenance. In this section, we'll talk about the service aspects of data management. [Learn more about managing data](data-management.md).

Data volume grows quickly. Dynamics 365 has routine jobs to manage data that optimize system performance at the platform level. You can also do maintenance jobs like reindexing databases that adjust to variations in transactional data. But you can always do more to fit your data usage better. Developing a strategy to archive and delete data is an important step to keep your system in good shape.

[Learn why you need a strategy for creating and maintaining environments](environment-strategy-overview.md).

Learn more about [database movement operations in finance and operations apps](/dynamics365/fin-ops-core/dev-itpro/database/dbmovement-operations) and [managing environments for customer engagement apps](/power-platform/admin/environments-overview).

### How fast is the data growing?

You need to know how fast your data is growing in your environment. The growth rate is a key metric to monitor. Set alerts to notify you when the growth rate exceeds a threshold set by your organization.

The growth rate can vary depending on the number of users or the time of year. Monitoring storage growth and using historical trends will help you estimate data growth. This information can help you decide how often to archive and delete data.

Get more information about storage allocation and buying extra storage for finance and operations apps in the [Dynamics 365 Licensing Guide](https://go.microsoft.com/fwlink/?LinkId=866544&clcid=0x409).

[Learn about the storage capacity model for Dataverse and how to check storage growth](/power-platform/admin/capacity-storage).

### What data can be removed?

Planning starts with identifying the types of data that you need to store and for how long. Besides cost, there are performance implications of having a large dataset. Building a data removal and retention strategy will help you decide what to do with old or unused data.

Transactional data might help you make key business decisions, assist customers, and use AI to determine the next best action. But after years of inactivity, the data might be taking up storage space and not providing any value.

You might have logging requirements like auditing customer records to see which users have access to personal information. But too much data auditing can fill up your storage quickly and affect performance. Storing large files and attachments to emails is also an area where datasets can grow fast. Planning what to store and for how long should be done deliberately and conservatively.

You might have logs, notifications, and other system records that you can delete without affecting the business. You might also have other transactional data that you can delete. But be careful when deleting records that have parent-child relationships with other records. Check for triggers that run code or workflows when a record is changed or deleted. A delete operation could also create a new entry in the audit log. You need to account for all these things when planning for bulk deletion.

Review the [cleanup routines for Finance and Supply Chain Management](/dynamics365/fin-ops-core/dev-itpro/sysadmin/cleanuproutines) to delete historical logs and notifications. You should only run these cleanup routines after the business has confirmed that the data is no longer needed.

You can also [free up storage space](/dynamics365/customerengagement/on-premises/admin/free-storage-space) for customer engagement apps.

### Archive and retention strategy

What if your database is too large, and it affects your performance, but you can't delete records? You might need to keep the data because of organizational, compliance, or regulatory requirements. In this case, you can archive the data instead.

We recommend the following strategy:

- **Identify retention requirements**: Find out what records you need to keep and for how long.

- **Develop an archiving strategy**: When you know what data to keep, plan how to archive these records. Where will you store the archived data? How will you access it when needed? What's the process to regularly move records from Dynamics 365 systems to the archives?

- **Remove the data**: For any data that doesn't meet the retention criteria, plan how to remove it from the archives.

> [!TIP]
> Understand the data backup and retention policy for finance and operations apps. Your organization might be subject to rules that give users specific rights to their personal data. To comply with privacy and security regulations, you might need to respond to requests to delete a user's personal data. We recommend reviewing the guidelines for [privacy and personal data in Dynamics 365](/dynamics365/get-started/privacy/).

## Next steps

- Find more resources to [continue your business application journey](service-solution-continue-the-business-application-journey.md)
- Read [the case study](service-solution-case-study.md) to understand how servicing your solution can make a difference for your organization
