---
title: Manage configuration and migration data for Dynamics 365 projects
description: Learn how to plan, import, and test configuration and migration data for your Dynamics 365 solution.
author: vaniaf
ms.author: vaniaf
ms.date: 01/17/2024
ms.topic: conceptual
ms.custom:
  - ai-seo-date: 01/17/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Manage configuration and migration data for Dynamics 365 projects

Data management is a crucial part of any Dynamics 365 implementation project. You need to import the right data to your Dynamics 365 solution before you can go live and use it for your business processes. You need to consider two types of data:

- Configuration data
- Migration data

Configuration data is the data that sets up your Dynamics 365 environment for your specific needs, such as currencies, tax codes, and parameters. Migration data is the data that you move from your legacy system to your Dynamics 365 application, such as customers, products, and open transactions.

Both types of data require careful planning, testing, and monitoring throughout the project lifecycle. If you don't manage your data properly, you might face errors, delays, or data loss. In this article, we'll cover the following topics:

- How to plan and import configuration data
- How to use a golden configuration environment and a configuration plan
- How to plan and import migration data
- How to define a migration strategy and use ETL tools
- How to assign roles and responsibilities for data management

## Configuration data

You should start preparing for importing configuration data as soon as you have a clear understanding of your business requirements and data governance. Configuration data is the data that defines how your Dynamics 365 solution works for your specific scenarios.

Managing configuration data is an activity that you need to perform throughout the project. As you design and develop your solution, you'll discover new configuration requirements and dependencies. For example, if you want to create purchase orders, you need to set up vendors and accounts. You need to keep track of all the configuration data your solution needs and how to import it correctly.

For Dynamics 365 Finance, Supply Chain Management, and Commerce, we recommend that you set up a dedicated golden configuration environment to store and maintain your configuration data. A golden configuration environment is a separate environment that you use only for configuration data. You don't create any transactions or test data in this environment. You should restrict access to it and keep it up to date. Use it as a source of truth for your configurations and restore it to other environments as needed.

### Use a configuration plan

A configuration plan is a tool that helps you organize and manage your configuration data. It's especially useful if you have a phased rollout strategy, where you plan to set up multiple environments, legal entities, or business units. A configuration plan is a structured list of all the configuration data you need to import for each phase of your project. It shows the sequence, dependencies, and redundancy of your configuration data. For example, you can use a configuration plan to:

- Identify which configuration data is shared across business units or legal entities, and which configuration data is unique for each one.
- Avoid duplicating or missing configuration data that might cause errors or inconsistencies.
- Use data-sharing features to copy configuration data across companies instead of importing it manually.
- Track the progress and status of your configuration data imports.
- Estimate the time and resources needed for your configuration data imports.
- Prepare for cutover and go-live by testing and validating your configuration data.

A configuration plan is your configuration playbook. It shows the scope, requirements, and best practices for your configuration data. You should update your configuration plan regularly as you discover new configuration data needs or changes. You should also attach the data entities or files that contain your configuration data to your configuration plan for easy reference.

Since it's basically a list, you can create and maintain your configuration plan in familiar tools such as Microsoft Excel or Azure DevOps. It doesn't matter which tool you choose, as long as your team members can access and update the list when necessary.

## Migration data

Migration data is the data that you move from your legacy system to your Dynamics 365 application. Your legacy system can be another business application or a collection of Excel spreadsheets. You need to migrate the data that's relevant and useful for your Dynamics 365 solution. Migration data can be either master data, such as customers, products, and vendors, or open transactions, such as sales orders, purchase orders, stock on hand, and open balances.

Migrating data is a complex and time-consuming process. It requires a lot of coordination, testing, and validation. You should include data migration activities in your project plan and allocate enough time and people to them. For example, you need to plan for:

- Discovering and analyzing the data sources, types, and volumes that you need to migrate.
- Defining and documenting the data migration scope, strategy, and cutover plans.
- Sizing and provisioning the environments and databases that you need for data migration.
- Mapping and transforming the data fields and values between the source and target systems.
- Extracting, loading, and testing the data using ETL tools and methods.
- Verifying and validating the data quality and accuracy in your Dynamics 365 solution.

### Define a migration strategy

A migration strategy is a plan that outlines how you'll migrate your data from your legacy system to your Dynamics 365 solution. It covers the following aspects:

- The source and target systems and databases that you'll use for data migration
- The data entities and tables that you'll migrate and their volumes and characteristics, such as direction relative to Dynamics 365 (from, to, or both), mode (full push or incremental), and frequency (one-time or recurring)
- The tools and methods that you'll use to extract, transform, and load the data
- The sequence and dependencies that you'll follow to migrate the data correctly
- The roles and responsibilities that you'll assign to your data migration team members
- The pre-cutover and post-cutover data migration activities that you'll perform

When you're building a migration plan, keep in mind that data migration activities can be a disruptive task and shouldn't coexist with other testing activities. You should define your migration strategy before you start your project and update it as your project progresses. You should also communicate your migration strategy to your stakeholders and team members and get their feedback and approval.

Don't forget to include environment considerations in your planning, like the size of the import and staging databases needed to migrate and cleanse the data. We recommend that you procure a dedicated high-tier data migration environment that's sized appropriately to handle the volume of data in scope. We also recommend that you have all databases and environments running under the same location and region and with [acceptable latency](https://www.azurespeed.com/Azure/Latency). You should also test and verify your data migration at least once in your system integration testing (SIT) and user acceptance testing (UAT) environments.

### Use ETL tools

*ETL* stands for extract, transform, and load. It's a process for moving data from one system to another and transforming it as needed; that is, *extracting* the data from the source, *transforming* the data for the target, and *loading* the data into the target.

ETL tools and methods to move your data from your legacy system to your Dynamics 365 application vary, depending on your data sources, types, and volumes. Some of the common options include:

- Data import/export wizards
- Azure Data Factory or Azure Synapse Analytics
- SQL Server Integration Services (SSIS)
- Non-Microsoft integration products

You should choose the ETL tools and methods that best suit your data migration needs and requirements. You should also follow the best practices and guidance for using the ETL tools and methods that you choose.

### How to assign roles and responsibilities

Data migration is a team effort that requires different skills and expertise. You should staff your project team with the right resources who understand data and the tools in Dynamics 365. The following table lists some of the important roles and responsibilities for data migration.

| Role | Responsibility |
|--|--|
| Data migration analyst | Helps design, plan, and manage the data migration process. Works with subject matter experts and project teams to identify, define, document, and communicate data migration requirements. |
| Data steward | Maintains and manages data according to data properties and standards. Coordinates with stakeholders. Provides definitions and rules for data. |
| Data migration architect/developer | Designs and develops the environments and packages for data migration. Transforms and tests data. Validates and verifies data quality and accuracy. |

## Next steps

- Review product-specific guidelines for data management: [Guidelines for customer engagement apps](data-management-product-specific-ce.md) and [Guidelines for finance and operations apps](data-management-product-specific-fo.md)
- [Review the Data Management Success by Design checklist](data-management-check-list.md)
- [Read a case study in data management](data-management-case-study.md)
