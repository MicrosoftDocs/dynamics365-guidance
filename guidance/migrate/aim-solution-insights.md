---
title: Solution-specific insights
description: Review the specific product pages when evaluating whether to transition from on-premises to the cloud.
author: ReneeW-CPub
ms.author: renwe
ms.date: 05/03/2024
ms.topic: overview
ms.service: dynamics-365
ms.reviewer: renwe
---
# Solution-specific insights

Is your organization evaluating whether to transition your Dynamics AX solution to Dynamics 365 online or stay on-premises? Review the specific product pages listed here for more information.

Talk to your Microsoft representative or partner today to see if you qualify for various migration offers. The [AIM migration assessment](aim-assessment.md) can help you determine if it's the right move.

## Dynamics AX

[AX Code Upgrade Analysis Tool (LCS)](/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/analyze-code-upgrade) is a Dynamics Lifecycle Services project to upgrade custom AX 2012 code and metadata to the Dynamics 365 finance and operations apps format. Provides the Migration summary report, where you find the code analysis summary, including customization information to review high-level estimates for the efforts required to convert over layering to extensions.

[Upgrade Analysis Tool (SQL Script) for AX](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/AX2012DataUpgrade/UpgradeAnalysisReport.SQL) contains scripts to gather data on Dynamics AX environment and system usage with spotlights on new features and improvements. Automated recommendations and resources based on module and functionality used.

Learn more at [Upgrades, updates, and hotfixes resources](/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/upgrade-home-page).

## Dynamics NAV

Learn more at [Migrate on-premises data to Business Central online](/dynamics365/business-central/dev-itpro/administration/migrate-data).

## Dynamics GP

Learn more at [Dynamics GP migration to Business Central online: End-to-end overview](/dynamics365/business-central/dev-itpro/administration/migrate-gp-overview).

## Dynamics SL

Learn more at [Cloud Migration Extensions for Migrating to Business Central Online](/dynamics365/business-central/ui-extensions-data-replication).  

## Dynamics CRM

To determine whether it's the right move, learn more at [Dynamics CRM (on-premises) to Dynamics 365 migration](/dynamics365/fasttrack/migration).

### CRM platform assessment tool

The CRM platform assessment tool is used to collect relevant technical information about your CRM deployment and assist Microsoft with requisite data in performing your assessment. 

[**Download the platform assessment tool.**](https://aka.ms/DynamicsOnlineAssessmentCollector)

The tool queries the metadata within an on-premises CRM instance and extracts relevant information used to determine the risks and effort involved with moving online. A companion tool renders the output of this tool and can populate predefined templates for use in the standard migration assessment. 

Your Microsoft solution architect or database administrator runs the tool via a desktop sharing session, or by a staff member of your choosing who has sysadmin and public roles access to your CRM SQL database. Once the tool connects to your CRM SQL database, the Collect Data feature of the tool runs a series of SQL queries that generate output files that Microsoft collects to run our analysis.

The CRM platform assessment tool supports Dynamics CRM 2015 and later.

### Why are we running the tool?

- **Migration readiness**: Identifying your organization's readiness for a migration.
- **Cloud platform readiness**: Identifying your organization's readiness for life in the cloud.
- **Customization readiness**: Identifying customizations that will need attention after your Dynamics 365 upgrade.
- **Your CRM overview**: An executive-level overview of your CRM system.

### Prerequisites for running the tool

Before you run the platform assessment tool, we advise that you take the following steps:

- Read the instructions before you unzip the downloaded package file.
- Run the tool as a local administrator on a computer that can browse to your SQL Server.
- Run the tool as a user that has sysadmin and public roles on your CRM database, or provide SQL credentials for a SQL user with the required credentials.

> [!IMPORTANT]
> To successfully run the platform assessment tool, we advise the client ***not*** to stop the tool while it's running.
