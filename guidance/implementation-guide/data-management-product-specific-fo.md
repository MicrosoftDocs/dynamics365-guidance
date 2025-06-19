---
title: Manage data in finance and operations apps
description: Learn how to use data management tools and data maintenance cleanup schedules in Dynamics 365 Finance, Supply Chain Management, and Commerce.
author: vaniaf
ms.author: vaniaf
ms.date: 01/17/2024
ms.topic: concept-article
ms.custom:
  - evergreen
  - ai-seo-date: 01/17/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---
# Manage data in finance and operations apps

You can use data management tools and data maintenance cleanup schedules to optimize data storage and performance in Dynamics 365 Finance, Supply Chain Management, and Commerce. This article explains how to use these features and provides links to more resources.

## Data maintenance

Storing data requires space and resources. You don't need to keep all the data that your apps generate. For example, you can delete logs and staging data after a certain time. You should plan how to maintain your data regularly.

Dynamics 365 Finance, Supply Chain Management, and Commerce have cleanup routines that you can use to remove unnecessary data. Before you run these routines, make sure that you don't need the data for your business processes. Always test each routine in a test environment before you run it in production. [Learn more about cleanup routines in Dynamics 365 finance and operations apps](/archive/blogs/axsa/cleanup-routines-in-dynamics-365-for-finance-and-operations).

### Best practices for handling personal data

- Don't store personal data in Dynamics 365 finance and operations apps unless you need it.
- Identify, tag, and classify the personal data that you store.
- The Dynamics 365 Finance, Supply Chain Management, and Commerce apps use Azure SQL database, which encrypts data at rest and in transit.
- Use X++ APIs and patterns to encrypt and decrypt data at the column level for extra security.
- Use Microsoft Edge applications and integration to store and comply with data residency and personal data requirements.

## Data management tools

Microsoft provides a rich set of tools and processes to support data movement and migration in Dynamics 365 Finance, Supply Chain Management, and Commerce. You can use the features in the apps and Dynamics 365 Lifecycle Services to combine different approaches.

### Data management workspace

The data management framework is the primary tool for data-related tasks in Dynamics 365 Finance, Supply Chain Management, and Commerce. You can access it through the data management workspace. In this workspace, you can manage all data-related activities through data projects that use data entities, data templates, and data packages.

You can use this workspace for many scenarios, such as copying configurations between environments or loading data as part of data migration.

To learn more, see the following articles:

- [Data entities overview](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities)
- [Configuration data projects](/dynamics365/fin-ops-core/dev-itpro/data-entities/configuration-data-projects)
- [Configuration data templates](/dynamics365/fin-ops-core/dev-itpro/data-entities/configuration-data-templates)
- [Configuration data packages](/dynamics365/fin-ops-core/dev-itpro/data-entities/configuration-data-packages)

### Database operations

You can use data entities and data packages to move small configurations, but sometimes you might want to move entire databases. Database movement operations are a suite of self-service actions that you can use as part of data application lifecycle management (DataALM). These actions provide structured processes for common scenarios like these:

- Promoting golden configurations
- Debugging and diagnostics
- Destructive testing
- Refreshing data for training purposes

You can use database movement operations for refresh, export, import, and point-in-time restore. For example, when your golden configuration environment is ready and you've completed all testing cycles and sign-offs in SIT and UAT, you can use the **Sandbox to Production** database request to restore this database to production for go-live.

To learn more, see the following articles:

- [Database movement operations](/dynamics365/fin-ops-core/dev-itpro/database/dbmovement-operations)
- [Submit service requests to the Dynamics 365 Service Engineering team](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team)

### Data sharing framework

Cross-company sharing is a mechanism for sharing reference and group data among companies in a Dynamics 365 Finance, Supply Chain Management, and Commerce deployment. With this framework, you can share configurations and master data across multiple legal entities. It makes it easier to manage master data when you have multiple legal entities and want to designate one of them as the master for some configurations. For example, tax codes might not change from company to company, so you can set them up in one legal entity, and then use the cross-company data sharing framework and its policies to replicate the data across the rest.

[Learn more about cross-company data sharing](/dynamics365/fin-ops-core/dev-itpro/sysadmin/cross-company-data-sharing).

### Copy company configuration in an existing environment

If you have a phased rollout that involves multiple companies in one Dynamics 365 instance, you might find it useful to use the **Copy into legal entity** feature. You can designate one base company as the source template, and then automatically copy its setups to other companies or legal entities to create and set up new companies quickly and consistently. This strategy requires some upfront planning and effort in doing the setups, but depending on the scale of your rollouts, it can save time and reduce errors.

[Learn how to copy configuration data between companies or legal entities](/dynamics365/fin-ops-core/dev-itpro/data-entities/copy-configuration).

## References

- [Data Management/Data Warehousing information, news and tips - SearchDataManagement (techtarget.com)](https://searchdatamanagement.techtarget.com/)
- [Insights-Driven Businesses Set The Pace For Global Growth (forrester.com)](https://www.forrester.com/report/InsightsDriven+Businesses+Set+The+Pace+For+Global+Growth/-/E-RES130848)
- [DMBoK - Data Management Body of Knowledge (dama.org)](https://www.dama.org/cpages/body-of-knowledge)

## Next steps

- [Review the Data Management Success by Design checklist](data-management-check-list.md)
- [Read a case study in data management](data-management-case-study.md)
