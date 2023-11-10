---
title:  Dynamics CRM (on-premises) to Dynamics 365 migration
description: Microsoft provides guidance on migrating your Dynamics CRM (on-premises) database to Dynamics 365 and Microsoft Dataverse.
ms.author: jedinh
ms.date: 12/18/2020
ms.topic: article

ms.reviewer: edupont
author: ReneeW-CPub
---

# Dynamics CRM (on-premises) to Dynamics 365 migration
Microsoft provides guidance on migrating your Dynamics CRM (on-premises) database to [Dynamics 365 and Microsoft Dataverse](/powerapps/maker/common-data-service/data-platform-intro#dynamics-365-and-dataverse). We provide guidance in the form of tools and documentation and by performing configuration tasks where applicable and feasible. This is available for all eligible customers with Dynamics 365 services who are invited into the program.

The FastTrack Center benefit includes providing guidance with source environment migration to [Dynamics 365 and Dataverse](/powerapps/maker/common-data-service/data-platform-intro#dynamics-365-and-dataverse).

> [!Note]
> - Data migrated through the FastTrack services may be transferred to, stored, and processed anywhere that Microsoft maintains facilities (except as otherwise provided for your particular FastTrack engagement). The FastTrack services aren't designed or intended for data subject to special legal or regulatory requirements.
> - In order to perform the migration, your source environment must be a version of Dynamics CRM 2011, Dynamics CRM 2013, Dynamics CRM 2015, or Dynamics CRM 2016, and SQL Server must be a version of SQL Server 2008, SQL Server 2012, SQL Server 2014, or SQL Server 2016, whereas Dynamics CRM and SQL Server versions must be aligned with the documented supportability statements.
> - Unforeseen issues (including but not limited to unreadable or corrupt items in the source environment) may prevent some items from being migrated.
> - It is the customer's responsibility to perform the mitigation or fixing of unsupported customizations or SQL Server-level changes that might block the database migration via this method.

The following table describes what's expected for migration in your existing source environment.

| Activity  | Source environment expectation |
|----  | ---- |
| Dynamics 365 (online) migration | Dynamics CRM (on-premises) versions supported—Dynamics CRM 2011, Dynamics CRM 2013, Dynamics CRM 2015, Dynamics CRM 2016. |
|  | SQL Server versions supported—SQL Server 2008, SQL Server 2012, SQL Server 2014, SQL Server 2016. |
|  | Dynamics CRM and SQL Server versions must be aligned with documented version supportability statements. |
|  | SQL Server data to be in only one .mdf and one .ldf file. |
|  | Users belong to a single domain. |
|  | Other SQL Server prerequisites will apply once the migration project starts; these can be handled as migration progresses. |

## Migration to Microsoft Dataverse 

### Enable to migrate
If you use Microsoft to migrate your data, we might provide guidance to enable both Microsoft Dataverse and the source environment for migration. Depending on the source, we might perform various enable steps. We provide guidance for you by using a combination of tools and documentation and by performing configuration tasks where applicable and feasible.

You need to provide appropriate access and permissions to Microsoft to perform some activities.

### Migration policy and steps
-	The technical migration orchestration is carried out through tooling hosted in the Dynamics 365 Lifecycle Services portal. Microsoft will make the Dynamics 365 Lifecycle Services portal available to you in accordance with an agreement to use the migration tooling to manage the migration process.
-	All migrations require appropriate access and permissions to the source environment.

### End state
The expected end state after a migration batch includes:

-	Dynamics CRM environment from appropriately scheduled and eligible sources in the source environment is migrated to Microsoft Dataverse.
-	A post-migration report for the migration environment is provided by Microsoft.

The expected end state after all migrations are complete includes:

-	Data from the eligible source is migrated to [Microsoft Dataverse](/powerapps/maker/common-data-service/data-platform-intro) as defined in the following table.
-	The type of data to be migrated depends on the source environment as described in the following table.

| Source environment |Type of migration | What will migrate | What won’t migrate |
|----- |----- |----- |----- |
| Dynamics CRM (on-premises)  |  Upgrade and migration   | All data   | Disabled users will not be migrated.   |
|  |  | Ownership |Integration code is not migrated.  |
|  |  |Sharing  | Integrations are not migrated. |
|  |  | Audit history | Outlook sync. |
|  |  | Metadata |  Exchange sync.|

Microsoft performs the following during migrations:

- Conduct a migration walkthrough workshop covering the process and approach for the selected migration scenario.
- Provide prerequisites for assessment and migration tools as applicable for the scenario.
- Provide prerequisites for migration team access to the source and target environment for the purpose of assessment and migration.
- Make the Dynamics 365 Lifecycle Services portal and the Dynamics CRM On-premises to Dynamics 365 Online Migration Tool available to customers in accordance with the terms and conditions for such usage.
- Assist in running assessment and migration tools (if applicable).
- Configure migration infrastructure in preparation for content migration (when applicable).
- Conduct a limited test migration to validate the migration infrastructure and required prerequisites.
- Conduct one pilot migration prior to production CRM migration.
- Provide guidance on migration scheduling for the selected scenario.
- Participate in migration issues triage and provide guidance on potential remediation options.
- Provide a final migration report for each migration.
- Provide post-migration assistance during user acceptance testing up to five days past migration completion.

You perform the following during migrations:

- Provide project resources recommended for assessment and migration activities. These include:
  - Project management.
  - User acceptance testing (UAT).
  - Admins responsible for source and target content platforms.
- Provide infrastructure prerequisites for assessment and migration activities (if required).
- Provide access and permissions to the staging and target environments to Microsoft personnel to perform migration activities (if required).
- Complete assessment data gathering activities (if applicable).
- Complete remediation activities outlined in the FastTrack-provided remediation report (if applicable).
- Provide a migration schedule using FastTrack templates and guidance.
- Conduct migration quality assurance and user acceptance testing.
- Conduct post-migration remediation (if applicable).
- Plan and implement change management and user communications (if applicable).
- Administrate and configure any changes to the source system and devices required for successful completion of assessment and migration activities.

> [!Note]
> Migrations only use accounts that adhere to security requirements defined during onboarding. If you don't use such accounts, you might experience migration delays.
