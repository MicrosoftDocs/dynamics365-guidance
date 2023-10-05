---
title: Finance and operations apps security
description: Finance and operations applications use Azure AD as a primary identity provider and utilizes the security capabilities of Azure in addition to extensive native security features. This section shares product-specific guidance for security measures customers should consider.
author: riblack-microsoft
ms.author: riblack
ms.topic: conceptual
ms.date: 04/12/2023
ms.service: dynamics-365
---

# Finance and operations apps security

Finance and operations applications use Azure Active Directory (Azure AD) as the primary identity provider. The security capabilities of Azure support and extend the native security features. To access these applications, users must have a valid Azure AD account in the associated tenant and be provisioned into a Dynamics 365 environment with a valid license. Once authenticated, these applications use role-based security to authorize user access to individual elements of the applications. Additionally, you can use extensible data security policies to restrict access to a subset of data.

[!INCLUDE [azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

The [security architecture of finance and operations apps](/dynamics365/fin-ops-core/dev-itpro/sysadmin/security-architecture) consists of the following components (Figure 12-17):

- Authentication  

  Only authenticated users with user rights in Dynamics 365 can connect

- Authorization  

  Permissions form privileges that define duties, which are collected in security roles to determine authentication  

- Security roles  

  Roles grant access to finance and operations apps

- Duties  

  Duties allow access to parts of business processes

- Privileges  

  Privileges allow access to individual tasks

- Permissions  

  Permissions grant access to individual securable objects

- Data security  

  You use data security to deny access to tables, fields, and rows in the database (extensible data security framework)

- Auditing  

  The system logs when a user signs in or out of the application

:::image type="content" source="media/oa-security-architecture.png" alt-text="Security architecture of operations apps includes authentication, authorization, security roles, duties, privileges, and permissions, and data security, and auditing" lightbox="media/oa-security-architecture.png":::

## Role-based security

In [role-based security](/dynamics365/fin-ops-core/dev-itpro/sysadmin/role-based-security), a user who is assigned to a security role has access to the set of duties that are associated with that role, which is comprised of various granular privileges. A user who isn't assigned to any role has no privileges. Privileges are composed of permissions and represent access to tasks, such as canceling payments and processing deposits. Duties are composed of privileges and represent parts of a business process, such as maintaining bank transactions. Roles are assigned to users in either all legal entities or within specific legal entities to grant access to finance and operations application functionality.

By default, approximately 100 standard security roles are provided within the solution. All functionality is associated with at least one of the standard security roles. The administrator can duplicate and modify the sample security roles to fit the needs of the business or create entirely new security roles.

> [!IMPORTANT]
> We recommend duplicating the sample security roles and using these for role assignments for all users before you start creating custom roles. This will enable you to facilitate access to your implementation team sooner, will avoid any risks associated with 'temporarily' using admin roles, and will be more expedient than waiting to create completely custom roles.

Customers with basic security requirements may find the standard roles to be sufficient for most of their needs and use the standard roles directly. 

> [!NOTE]
> Standard security roles are subject to changes in future application updates to accommodate new and updated functionality.

If standard security roles are used and are later modified, it can be difficult to later discern the difference between standard and modified roles. It might require comparison with another, unmodified, environment. For organizations with enhanced security requirements, it may be preferable to work with copies of standard roles and refrain from directly modifying the standard roles.

Customers with more advanced security requirements may opt to create custom roles. While this approach is right for some customers, it's not recommended to start with completely custom roles. Standard security roles provide access to required functionality, while still accommodating some separation of functions. Customers are encouraged to use the standard roles as templates to be copied to form the basis of modified roles that may be tailored to specific requirements. These standard roles incorporate segregation of duties in their design and using them to facilitate role assignments that enable end users to complete required tasks enables implementation teams to provide access to end users earlier in an implementation than if they were to attempt to create completely custom roles created from scratch.

Learn how to [Implement role-based security in finance and operations apps](/training/modules/role-security-finance-operations)

## Security diagnostics for task recordings

The Task recorder for finance and operations apps is a utility that lets users record business processes for several different use cases. It's an invaluable tool for many purposes, including process definition, training, testing, and security. The security diagnostics for the Task recorder allows implementers to analyze and manage [security permission requirements in any task recording](/dynamics365/fin-ops-core/dev-itpro/sysadmin/tasks/security-diagstics-task-recordings). When you use the Task recorder to define and document business processes for testing or training purposes, the security requirements for implementing those tasks are also captured. Implementers can then use this tool to tailor duplicated copies of the sample security roles to better meet their needs.

> [!NOTE]
> The standard security roles included in finance and operations apps incorporate segregation of duties. If a user needs full access, they often need a combination of roles (such as an HR assistant and HR manager for full access to HR features).

Learn more about [Security diagnostics for task recordings](/dynamics365/fin-ops-core/dev-itpro/sysadmin/tasks/security-diagstics-task-recordings)

## Segregation of duties

Some organizations may require some tasks to be separated and performed by different users. For example, you might not want the same person to maintain vendor information, acknowledge the receipt of goods, and to process payment to the vendor. This concept is sometimes referred to as separation of function, and the standard security roles included in finance and operations applications have been created with this separation in mind. To cite the previous example, different security role assignments are required in Dynamics 365 Finance to maintain vendor information, acknowledge the receipt of goods, and to process payment to the vendor.

In addition to the separation of functions described above, finance and operations applications also facilitate the segregation of duties. Segregation of duties helps you with tasks such as the following list:

- Reduce the risk of fraud  
- Enforce internal control policies
- Detect errors or irregularities  

This way, you can identify specific duties in your organization that must not be performed by the same personnel, and creating rules to detect and prevent the assignment of security roles that would conflict with those rules.

When an organization defines rules for segregation of duties, you should evaluate existing role definitions and role assignments for compliance, thereby preventing role definitions or role assignments that don't comply. Future role assignments that result in conflicts with existing rules are logged and must be allowed or denied by an administrator.

Learn more about how to [Set up segregation of duties](/dynamics365/fin-ops-core/dev-itpro/sysadmin/tasks/set-up-segregation-duties)

## Security reports

Dynamics 365 provides a set of rich security reports to help you understand the set of security roles running in your environment and the set of users assigned to each role. Familiarize yourself with these reports during implementation and engage your compliance team early. There's no benefit to waiting for an audit to use these reports for the first time.

- User role assignments report  

  Generates a view of the current user role assignments in your system. By default, the report includes all users with roles assigned. You can optionally limit the report to a specific set of users by entering a list of users when generating the report. In the User role assignments parameters pane, under Records, choose Filter. From here, you can add or remove filters to the list of users the report will be generated for.

- Role to user assignment report  

  Provides an aggregation of role assignments. Expanding a role in the report shows the list of users assigned to the role, and expanding the username shows any restrictions the role has applied. You can apply the same method for filtering the set of users to this report as described for the User role assignments report.

- Security role access report Provides a view of the effective permissions for each security role. This report provides a flattened list of permissions grouped by type across all sub-roles, duties, and privileges contained in the role.

- Security duty assignments report  

  Provides a view of all the duties contained within a role. You can configure this report to run on any collection of roles to ensure that segregation of duties is maintained between roles. By default, the report includes all the roles. To limit the roles included, use the filtering provided in the Records to include section.

- In addition to the security reports, developers can generate a workbook containing all user security privileges for all roles. The workbook provides a comprehensive list specific to your implementation, including customizations and software modules from third parties.

- To aid compliance with the requirements of privacy laws and regulations, you can use the [person search report](/dynamics365/fin-ops-core/dev-itpro/gdpr/gdpr-person-search-report) when a data subject requests a copy of their personal data.

- Finance and operations apps provide a default set of [asset classifications](/dynamics365/fin-ops-core/dev-itpro/gdpr/gdpr-asset-classification-values) for the kinds of data that are stored in each table. Through customization, you can change the classification of the following data to meet your own classification and tracking needs.

- System administrators can use the User log page to keep an audit log of users who have logged on to the system. The user logging capability allows administrators to identify roles that provide access to sensitive data. An organization can define what constitutes sensitive data in whatever way serves its needs. This capability is helpful for organizations that want a detailed level of auditing to track users who have had access to data that has been identified as sensitive data. Learn more at [Manage access to sensitive data](/dynamics365/fin-ops-core/dev-itpro/gdpr/gdpr-auditing-sensitive-data)

## Extensible data security policies

With [Extensible Data Security (XDS) policies](/dynamics365/fin-ops-core/dev-itpro/sysadmin/extensible-data-security-policies), developers can supplement role-based security by restricting access to table records based on security policies. That might be useful if there are unusual or extraordinary requirements for row-level security. Policies can be created that contain a query to select information and a table or tables that will be constrained by the policy. The query in the policy applies a filter and only records that satisfy the conditions of the filter are accessible from the restricted tables. XDS provides a powerful data security tool for advanced requirements, but you should use it judiciously to avoid unanticipated impacts on performance or usability.

## Database logging

[Database logging](/dynamics365/fin-ops-core/dev-itpro/sysadmin/configure-manage-database-log) provides a way to track specific types of changes to the tables and fields in finance and operations apps, including insert, update, delete, and rename key operations. When you configure logging for a table or field, a record of every change to that table or field is stored in the database log table (`sysdatabaselog`) in the environment database.

You can use database logging to create an auditable record of changes to specific tables that contain sensitive information, or to monitor the use of electronic signatures.  

> [!NOTE]
> This feature is in addition to audit trail capabilities already available in many modules.  

Database logging is intended to track individual changes to specific, sensitive information or configurations. It's not intended to track automated transactions that are run in batch jobs and isn't recommended for transactions. Although database logging can be valuable from a business perspective, it can be expensive regarding resource use and management, so it too should be used judiciously.

Microsoft recommends the following steps when implementing database logging:

- Create a plan for reviewing and using your database logs

- Limit log entries and help improve performance by selecting specific fields to log instead of whole tables

- Create a plan for how long you'll retain logged data and use the included cleanup job

## Next steps

- [Plan and implement security in finance and operations apps](/training/modules/plan-implement-security-finance-operations)
- [Dynamics 365 solution architecture best practices for security](/training/modules/solution-architecture-security/)
- Learn more about [Power Pages Security](security-strategy-product-portals.md)
- Learn more about [customer engagement apps security](security-strategy-product-ce.md)
- [Make security a day one priority](security-strategy-day-one-priority.md)
