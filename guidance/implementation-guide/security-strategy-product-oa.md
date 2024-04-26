---
title: Secure finance and operations apps
description: Learn how to use Microsoft Entra, role-based security, segregation of duties, and database logging to protect your data in finance and operations apps.
author: riblack-microsoft
ms.author: riblack
ms.topic: conceptual
ms.date: 01/22/2024
ms.service: dynamics-365
ms.custom:
  - ai-seo-date: 01/19/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Secure finance and operations apps

Finance and operations apps use Microsoft Entra as the primary identity provider. They also use the security capabilities of Azure to support and extend the native security features. To access these apps, users must have a valid Microsoft Entra ID account in the associated tenant and be provisioned into a Dynamics 365 environment with a valid license. After users are authenticated, these apps use role-based security to authorize access to individual elements of the apps. You can also use extensible data security policies to restrict access to a subset of data.

[!INCLUDE [azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

The [security architecture of finance and operations apps](/dynamics365/fin-ops-core/dev-itpro/sysadmin/security-architecture) consists of the following components:

- **Authentication**: Only users with rights in Dynamics 365 can connect.

- **Authorization**: Permissions form privileges that define duties, which are collected in security roles to determine authorization.

- **Security roles** grant access to finance and operations apps.

- **Duties** allow access to parts of business processes.

- **Privileges** allow access to individual tasks.

- **Permissions** grant access to individual securable objects.

- **Data security** is an extensible security framework that controls access to tables, fields, and rows in the database.

- **Auditing**: The system logs when a user signs in or out of the app.

:::image type="content" source="media/oa-security-architecture.png" alt-text="Diagram showing the security architecture of finance and operations apps." lightbox="media/oa-security-architecture.png":::

## Role-based security

In [role-based security](/dynamics365/fin-ops-core/dev-itpro/sysadmin/role-based-security), a user who is assigned to a security role has access to the set of duties that are associated with that role, which are composed of various granular privileges. A user who isn't assigned to any role has no privileges.

Privileges are composed of permissions and represent access to tasks, such as canceling payments and processing deposits. Duties are composed of privileges and represent parts of a business process, such as maintaining bank transactions. Roles are assigned to users in either all legal entities or within specific legal entities to grant access to finance and operations app functionality.

By default, about 100 standard security roles are provided within the solution. All functionality is associated with at least one of the standard security roles. The administrator can duplicate and modify the sample security roles to fit the needs of the business or create entirely new security roles.

> [!IMPORTANT]
> Before you start creating custom roles, we recommend duplicating the sample security roles and using them for role assignments for all users. This will help you provide access to your implementation team sooner, avoid any risks associated with "temporarily" using admin roles, and be faster than waiting to create completely custom roles.

If your organization has basic security requirements, you might find the standard roles are enough for most of your needs and use them directly. The standard security roles included in finance and operations apps incorporate segregation of duties. If a user needs full access to features, they often need a combination of roles.

Standard security roles are subject to changes in future app updates to accommodate new and updated functionality. If you use standard security roles and later modify them, it can be hard to tell the difference between standard and modified roles. You might need to compare them with another, unmodified, environment.

If your organization has enhanced security requirements, it might be better to work with copies of standard roles and avoid directly modifying the standard roles.

If your organization has more advanced security requirements, you might choose to create custom roles. While this approach is right for some customers, we don't recommend starting with completely custom roles. Standard security roles provide access to required functionality, while still allowing some separation of functions. We encourage you to use the standard roles as templates to copy and modify to meet your specific requirements.

[Learn how to implement role-based security in finance and operations apps](/training/modules/role-security-finance-operations).

## Security diagnostics for task recordings

The Task recorder for finance and operations apps is a utility that lets users record business processes for several different use cases. It's a valuable tool for many purposes, including process definition, training, testing, and security. You can use the Task recorder security diagnostics to [analyze and manage security permission requirements in any task recording](/dynamics365/fin-ops-core/dev-itpro/sysadmin/tasks/security-diagstics-task-recordings). When you use the Task recorder to define and document business processes for testing or training purposes, it also captures the security requirements for implementing those tasks. You can then use the tool to tailor duplicated copies of the sample security roles to better meet your needs.

[Learn more about security diagnostics for task recordings](/dynamics365/fin-ops-core/dev-itpro/sysadmin/tasks/security-diagstics-task-recordings).

## Segregation of duties

Some organizations might require some tasks to be separated and performed by different users. For example, you might not want the same person to maintain vendor information, acknowledge the receipt of goods, and process payment to the vendor. This concept is sometimes called *separation of function*, and the standard security roles included in finance and operations apps were created with this separation in mind. To cite the previous example, different security role assignments are required in Dynamics 365 Finance to maintain vendor information, acknowledge the receipt of goods, and process payment to the vendor.

In addition to the separation of functions, finance and operations apps also segregate duties. Segregation of duties helps you reduce the risk of fraud, enforce internal control policies, and detect errors or irregularities. You can identify specific duties in your organization that the same users must not perform, and create rules to detect and prevent the assignment of security roles that would conflict with those rules.

When you define rules for segregation of duties, you should evaluate existing role definitions and role assignments for compliance, and prevent role definitions or role assignments that don't comply. Future role assignments that result in conflicts with existing rules are logged and must be allowed or denied by an administrator.

[Learn how to set up segregation of duties](/dynamics365/fin-ops-core/dev-itpro/sysadmin/tasks/set-up-segregation-duties).

## Security reports

Dynamics 365 provides a set of rich security reports to help you understand the security roles in use in your environment and the users who are assigned to each role. Get familiar with these reports during implementation and involve your compliance team early. Don't wait for an audit to use these reports for the first time.

- The **User role assignments report** generates a view of the user role assignments in use in your system. By default, the report includes all users with roles assigned. You can optionally limit the report to a specific set of users by entering a list of users when you generate the report.

- The **Role to user assignment report** aggregates role assignments. Expanding a role in the report shows the list of users who are assigned to the role. Expanding the username shows any restrictions the role has applied. You can optionally limit the report to a specific set of users by entering a list of users when you generate the report.

- The **Security role access report** provides a list view of the effective permissions for each security role, grouped by type across all subroles, duties, and privileges contained in the role.

- The **Security duty assignments report** provides a view of all the duties contained within a role. You can configure this report to run on any collection of roles to make sure that segregation of duties is maintained among roles. By default, the report includes all roles, but you can filter the records to limit the roles in the report.

- In addition to the security reports, developers can generate a workbook that contains all user security privileges for all roles. The workbook provides a comprehensive list specific to your implementation, including customizations and software modules from partners.

- To comply with the requirements of privacy laws and regulations, you can use the [person search report](/dynamics365/fin-ops-core/dev-itpro/gdpr/gdpr-person-search-report) when a data subject requests a copy of their personal data.

- Finance and operations apps provide a default set of [asset classifications](/dynamics365/fin-ops-core/dev-itpro/gdpr/gdpr-asset-classification-values) for the kinds of data that are stored in each table. Through customization, you can change the classification of the data to meet your own classification and tracking needs.

- System administrators can use the **User log** page to keep an audit log of users who have signed in to the app. The user logging capability lets administrators identify roles that provide access to sensitive data. Your organization can define what constitutes sensitive data in whatever way serves its needs. This capability is useful if you want a detailed level of auditing to track users who have had access to data that has been identified as sensitive. [Learn more about managing access to sensitive data](/dynamics365/fin-ops-core/dev-itpro/gdpr/gdpr-auditing-sensitive-data).

## Extensible data security policies

With [Extensible Data Security (XDS) policies](/dynamics365/fin-ops-core/dev-itpro/sysadmin/extensible-data-security-policies), developers can supplement role-based security by restricting access to table records based on security policies. This might be useful if you have unusual or extraordinary requirements for row-level security. You can create policies that contain a query to select information and a table or tables that are constrained by the policy. The query in the policy applies a filter and only records that satisfy the conditions of the filter are accessible from the restricted tables. XDS provides a powerful data security tool for advanced requirements, but you should use it carefully to avoid unexpected effects on performance or usability.

## Database logging

[Database logging](/dynamics365/fin-ops-core/dev-itpro/sysadmin/configure-manage-database-log) provides a way to track specific types of changes to the tables and fields in finance and operations apps, including insert, update, delete, and rename key operations. When you configure logging for a table or field, a record of every change to that table or field is stored in the database log table `sysdatabaselog` in the environment database.

You can use database logging to create an auditable record of changes to specific tables that contain sensitive information, or to monitor the use of electronic signatures. You can also use database logging to track changes to specific tables or fields that are important to your business processes. For example, you might want to track changes to the vendor bank account number or the customer credit limit.

This feature is in addition to audit trail capabilities already available in many modules.

Database logging is intended to track individual changes to specific, sensitive information or configurations. It's not intended to track automated transactions that are run in batch jobs and isn't recommended for transactions. Although database logging can be valuable from a business perspective, it can be costly in terms of resource use and management, so it should be used carefully.

Microsoft recommends the following steps when you implement database logging:

- Create a plan for reviewing and using your database logs.

- Limit log entries and improve performance by selecting specific fields to log instead of whole tables.

- Create a plan for how long you'll keep logged data and use the included cleanup job.

## Next steps

- Learn how to [make security a priority](security-strategy-day-one-priority.md) from day one
- Use the Success by Design [security checklist](security-strategy-checklist.md) to help identify and prioritize key requirements and implementation activities in the areas of privacy and compliance, identity and access, and application security
