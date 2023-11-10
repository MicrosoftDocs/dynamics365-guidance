---
title:  Environment maintenance
description: Understand the needs for Dynamics 365 environment maintenance as application usage grows to ensure that actions can be proactively taken to maintain a healthy solution.
author: taksatoms
ms.author: tsato
ms.date: 03/31/2023
ms.topic: conceptual

---

# Environment maintenance

Protecting your solution and providing continuous availability of service is your primary goal as the system administrator. In a cloud environment, these maintenance jobs are automated, but it's critical for an organization to have a strategy so that these routine jobs are appropriately configured and scheduled. In some cases, you may need to perform these tasks manually but still in alignment with your overall planning and strategy.

## User access and security

Members of business and technical teams fluctuate. New employees are onboarded and existing ones may change roles or leave the company. As an administrator, you need to work with other teams to manage user access, assign the appropriate licenses, and assign security roles that meet their business and technical needs. You may want to hand over some of these responsibilities to business and IT managers who are more familiar with their resources' user profiles and know if any frequent changes in their roles require immediate changes.

Your organization's data is likely one of the most important assets you're responsible for safeguarding as an administrator. The ability to build apps and automation to use that data is a large part of your company's success. You can use Power Apps and Power Automate for rapid build and rollout of these high-value apps so that users can measure and act on the data in real time.

Apps and automation are becoming increasingly connected across multiple data sources and multiple services. Some of these might be external, third-party services, possibly even social networks. Users generally have good intentions, but they can easily overlook the potential for exposure from data leakage to services and audiences that shouldn't have access.

Microsoft recommends that you create [data loss prevention (DLP) policies](/power-platform/admin/wp-data-loss-prevention) to act as guardrails to help prevent users from unintentionally exposing organizational data. You can scope DLP policies at the environment level or tenant level, which provides the flexibility to craft sensible policies with the right balance between protection and productivity. For tenant-level policies, you can define the scope to be all environments, selected environments, or all environments except those you specifically exclude. You can define environment-level policies one environment at a time.

> [!TIP]
> You can manage users and licenses in both [finance and operations](/dynamics365/fin-ops-core/dev-itpro/sysadmin/tasks/create-new-users) apps and [customer engagement](/microsoft-365/admin/add-users/?view=o365-worldwide&preserve-view=true) apps. You can also use [Microsoft Entra groups](/power-platform/admin/manage-group-teams) to simplify user management and provision and deprovision users.

[!INCLUDE [azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

## Dynamics 365 environment management

Dynamics 365 provides point-in-time restore (PITR) capabilities for databases. This means that all databases are backed up automatically by the system and retained for a set number of days. In the event of accidental corruption or deletion, administrators can choose to restore the database from any of the backups taken. The automated backup system and PITR provides a zero-admin way to protect databases.

If your organizations require a proactive approach to manually take backups (such as before a deployment of a new release of your solution), the administrator may be called on to assist. You should perform these tasks in line with your organization's environment strategy.

> [!NOTE]
> Although the backup and recovery operation is dependable, it could also be time-consuming depending on the size of the backup. In a customer engagement apps scenario when solution imports fail, it's often better to fix the import issue instead of restoring from a backup. Fixing the import should take significantly less time than restoring.

## Data management

Data is central to all applications. It drives business decisions through analytics and artificial intelligence. It also reveals crucial information about the overall health of the system and what administrators need to do for maintenance. The theme of this article is to be proactive in planning and strategizing around the upkeep of your system. Data maintenance is no different. In this section, we discuss the service aspects of data management. To explore the broader topic, refer to the article [Data management](data-management.md).

Data volume grows quickly. Dynamics 365 has routine jobs in place to manage data that maximizes system performance at the platform level. You can also perform maintenance jobs like reindexing databases that adjust to variations in transactional data. But more improvements can always be done to better fit how you use the services. Developing a strategy to archive and delete data is an important step toward maintaining a well-functioning system.

> [!TIP]
> Refer to the article [Environment strategy](environment-strategy-overview.md) to explore the importance of having a strategy for creating and maintaining environments.

> [!TIP]
> Learn more about [database movement operations](/dynamics365/fin-ops-core/dev-itpro/database/dbmovement-operations) in finance and operations apps and review [environments](/power-platform/admin/environments-overview) for more information about managing instances for customer engagement apps.

### How fast is the data growing?

You first need to understand how fast data is growing in your environment. The rate of growth is a key metric to monitor. Set alerts to let you know when this growth rate exceeds a threshold determined by your organization.

The rate of growth can fluctuate depending on the number of users or even during certain times of the year if your business practice has special circumstances that may impact record creation. Monitoring storage growth and using historical trends will help estimate data growth. This information can help you determine how often the data archiving and removal process should take place.

> [!TIP]
> You can find details on storage allocation and purchasing additional storage for finance and operations apps in the Dynamics 365 Licensing Guide.

> [!TIP]
> Read about the [storage capacity model for Dataverse and how to check storage growth](/power-platform/admin/capacity-storage).

### What data can be removed?

Planning starts with identifying the types of data that need to be stored over particular timeframe. Besides cost, there are performance implications of having a large dataset. Building a data removal and retention strategy will help determine what to do when data is no longer useful.

Transactional data may help you make key business decisions, assist customers, and use AI to determine the next best action. But after years of inactivity, the data may be taking up storage space and not providing any value.

You may have logging requirements like auditing customer records to understand which users have access to read and modify personally identifiable information. But excessive data auditing leads to rapid storage growth and can negatively impact performance. Storing large files and attachments to emails is also an area in which datasets can quickly expand. Planning around what needs to be stored and for how long should be done deliberately and conservatively.

You may have logs, notifications, and other system records that you can delete with no impact to the business. You may also have other transactional data that can be deleted. Because Dynamics 365 applications have heavy parent-child relationships between records, pay careful attention to how records are deleted and any impact to related records. Look for triggers that run extension code or workflows when a record is modified or deleted. A delete operation could potentially write a new entry in the audit log to record the transaction. You must account for all these things when planning for bulk deletion.

> [!TIP]
> Review the [cleanup routines for Finance and Supply Chain Management](/dynamics365/fin-ops-core/dev-itpro/sysadmin/cleanuproutines) to delete historical logs and notifications. You should only run these cleanup routines after the business has completed a detailed analysis and confirmed that the data is no longer required.

> [!TIP]
> You can also [free up storage space](/dynamics365/customerengagement/on-premises/admin/free-storage-space) for customer engagement apps.

### Archive and retention strategy

What happens if the database is growing too large, and you're seeing the impact of it, but deleting records isn't an option? You may need to retain the data due to organizational, compliance, or regulatory requirements. In this case, you can archive the data instead.

We recommend the following strategy:

- **Identify retention requirements** Get a full understanding of the requirements for the types of records that you need to retain and how long you need to do so.

- **Develop an archiving strategy** Once you have a clear understanding of what data to retain, plan for how to archive these records. Where will you store the archived data? How will you access this data when needed? What is the process to periodically move records from the Dynamics 365 systems into the archives?

- **Remove the data** For any data that doesn't meet the retention criteria, plan out your process to remove it from the archives.

> [!TIP]
> Understand the data backup and retention policy for finance and operations apps. Your organization may be subject to rules that give users specific rights to their personal data. To comply with privacy and security regulations, you may need to respond to DSRs to delete a user's personal data. We recommend reviewing the guidelines for [privacy and personal data for Dynamics 365](/dynamics365/get-started/privacy/).

## Next steps

- Understand the importance to service the solution by reviewing the [overview](service-solution.md)
- Review how to best [monitor the service health](service-solution-monitor-service-health.md) of your Dynamics 365 solution
- Review how [Service Updates](service-solution-service-updates.md) work in Dynamics 365 and best practices for readiness  
- Find additional resources to [continue the business application journey](service-solution-continue-the-business-application-journey.md)
- Read the [case study](service-solution-case-study.md) to understand the impact to an organization when servicing the solution is not top of mind