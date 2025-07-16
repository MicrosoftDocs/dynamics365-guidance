---
title: Secure customer engagement apps to adapt to business scenarios
description: Learn how to use Dataverse to secure customer engagement apps with product-specific guidance, including an outline on security features.
author: riblack-microsoft
ms.author: riblack
ms.topic: concept-article
ms.date: 01/19/2024
ms.update-cycle: 1095-days
ms.service: dynamics-365
ms.custom:
  - evergreen
  - ai-seo-date: 01/19/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Secure customer engagement apps

Customer engagement apps use [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro) to provide a rich security model that can adapt to many business scenarios. This section gives you product-specific guidance for security measures that you should consider.

The Dataverse security model has these goals:

- Give users access only to the information they need to do their jobs.
- Group users by role and limit access based on those roles.
- Support data sharing so that users and teams can access records they don't own for a specific collaborative effort.
- Prevent users from accessing records they don't own or share.

[Learn more about security in Microsoft Dataverse](/power-platform/admin/wp-security).

## Security features

We use three main categories of security features to provide appropriate user access: fundamental security controls, other security controls, and manual sharing. You should address most of the security requirements using fundamental security controls. Use the other options to manage exceptions and edge scenarios.

| Category | Description | Benefits | Limitations |
| --- | --- | --- | --- |
| Fundamental security controls | These include record ownership, business unit hierarchy, security roles, and users and teams. They define the basic access level and permissions for users and records. | They're easy to set up and manage. They provide a clear and consistent security model. | They can't handle complex or dynamic scenarios. |
| Other security controls | These include field-level security, hierarchy security, access teams, and table relationships. They add more granularity and flexibility to the security model. | They can handle specific or exceptional cases. They can accommodate different organizational structures and data access needs. | They can increase the complexity and maintenance of the security model. |
| Manual sharing | This allows a user to share a record with another user or team. The user must have the share privilege on the record. | It's a simple and quick way to grant access to a record. It can handle unplanned or temporary scenarios. | It can't be automated or scaled. It can cause performance issues if used extensively. |

### Record ownership

Dataverse supports two types of [record ownership](/power-platform/admin/wp-security-cds):

- Organization owned: When a record belongs to the organization, everyone in the environment can access the record.

- User or team owned: If the organization doesn't own the record, a user, team, or business unit owns it. When a record is owned by a user or team, only the owner and users with the appropriate security roles can access the record.

Some out-of-the-box tables are exceptions to these two types. For example, a business unit owns the system user record.

### Business units

[Business units](/power-platform/admin/wp-security-cds) are a security building block that helps you manage users and the data they can access. The term "business unit" doesn't necessarily relate to an organization's operating business units. In Dataverse, business units provide a framework to define the organizational structure of users, teams, and records. Business units group users and teams by organizational hierarchy and can work with security roles to grant or restrict access to data.

Business units have a hierarchical nature. You can give users access to records in their business unit, or in their business unit and the business units under their unit. For example, you can use the hierarchical nature of business units to limit access to records at the site, district, region, and corporate levels. Business units are useful to segment data into ownership containers for access control.

It's a best practice to minimize the number of business units in your implementation. Base them on access control requirements instead of mapping the organizational chart to business units.

### Security roles

A privilege is permission to perform an action in Dynamics 365. A [security role](/power-platform/admin/security-roles-privileges) is a set of privileges that defines a set of actions that a user can do. Some privileges apply in general, such as the ability to use the export to Microsoft Excel feature. Others apply to a specific table, such as the ability to read all accounts.

You must assign one or more predefined or custom security roles to users, either directly or inherited from a team they're a member of, to allow them to access Dynamics 365. You can assign multiple security roles to a user. The user's effective security role is the sum of all the privileges from all the security roles assigned they're assigned. For example, if one security role allows a user to read accounts and another security role allows the user to read contacts, the user can read both accounts and contacts.

Customer engagement apps come with several out-of-the-box security roles. If you need more or different security roles, start by copying existing ones.

It's a best practice to create security roles at the root business unit level, since these roles are automatically duplicated for all child business units and can be included in solutions.

Here are some best practices to work with privileged accounts and service accounts:

- Limit and regularly review the list of elevated user and service accounts.

- Consider a just-in-time access approach to grant elevated privileges.

- Consider using an administrative user account to grant access to settings and administration features but not to functionality. Learn more about [privileged identity management](/entra/id-governance/privileged-identity-management) and [administrative users in Power Platform](/power-platform/admin/prevent-elevation-security-role-privilege).

- Use application accounts for integration and deployment. Learn more about [application users](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user) and [non-interactive user accounts](/power-platform/admin/create-users-assign-online-security-roles#create-a-non-interactive-user-account).

- Use server-to-server (S2S) authentication to allow secure and seamless communication between applications and services.

[!INCLUDE [azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

### Teams

[Teams](/power-platform/admin/wp-security-cds) provide a straightforward way to share records, collaborate with other people across business units, and assign security roles. Although a team belongs to one business unit, it can include users from other business units. You can associate a user with more than one team, which is a convenient way to grant rights to a user who crosses business units.

Dataverse has three types of teams:

- Owner teams: You can make an owner team the owner of a record, which is a useful way to link a record to a specific business unit. Owner teams can also share records and have security roles.

- Microsoft Entra security group teams and office group teams: These are special types of owner teams. You can't manage their membership within Dynamics 365. Instead, they're linked to a Microsoft Entra security group or [Microsoft 365 groups](/microsoft-365/admin/create-groups/compare-groups). Users who have the appropriate license and are added to the Microsoft Entra group are automatically enabled in the system and added to the team when they connect to the environment. Using Microsoft Entra ID is useful because the groups and permissions also extend to Microsoft Entra-enabled apps outside of Dynamics 365.

- Access teams: These teams are unique because they can't own records and can't have a security role association. However, just like owner teams, access teams can have records shared with them. When you enable access teams at the table level, they can grant specific record-level permissions to the members of a record's access team. This is an alternative to manually sharing the record with a user or a team.

Use owner teams when:

- You need team-level record ownership, rather than user.
- You need to assign security roles to users through teams.
- You need to report on team progress.

Use access teams when the team members need different permissions on individual records than the same permission on the record type. For example, you can use access teams to grant read access to a specific account record to a user who doesn't have read access to all accounts.

### Field-level security

You can use [field-level security](/power-platform/admin/field-level-security) to restrict access to fields that have a high business impact to specific users or teams. For example, you can allow only certain users to read or update the credit score of a business customer.

Field-level security is available for the default fields on most out-of-the-box tables, custom fields, and custom fields on custom tables. Field-level security is managed by the security profiles. The scope of field-level security is organization-wide and applies to all data access requests.

### Sharing

[Record sharing](/power-platform/admin/wp-security-cds) lets a user give access to a table record to other users or teams. The user must have the share privilege on the record to be able to share it. Sharing should be seen as a way for users to manually manage exceptions to the default security model.

Keep in mind the following recommended practices:

- Share only the necessary records with the smallest set of users or teams possible. Extensive sharing can cause performance issues at scale.
- Grant the minimum access required for users to do their jobs.
- Don't automate sharing.
- Turn off share rights in security roles where possible.

### Hierarchy security

You can use a [hierarchy security](/power-platform/admin/hierarchy-security) model to access data from a user or position hierarchy perspective. With this extra security, you can give managers access to the records owned by their reports for approval or to perform tasks on their behalf.

### Summary of access control features

The following table summarizes the access control features available in Dataverse.

| Type | Benefits |
| --- | --- |
| Organization | Allows open access to all records in the environment. Bypasses the need for security checking, which improves performance. |
| Business unit | Great for large volumes of data accessed by large groups of users. Allows for optimal access checking. Reduces maintenance overhead. Can be used for management and oversight access with more granular access at lower levels. |
| User ownership | Ideal for large volumes of overall. data but individual granular access to a smaller subset of the data. Optimized access checks combine memory cache and record data directly. Enables combination business unit access. |
| Team ownership | Ideal for large volumes of overall data but group granular access to a smaller subset of the data. Optimized access checks combine memory cache and record data directly. Reduces cascading impact as user involvement changes. Isolates users from record business unit structure, enabling user movement with data impact. |
| Sharing | Ideal for modeling exceptions over standard model using other features. Provides specific unique permissions per record, but at a cost&mdash;checking a lot of rules increases performance, storage, and maintenance overhead. Sharing with teams mitigates cost. |
| Inheritance | Builds on ownership and sharing models. Use to support immediate managers in chains above individual granular access. Not intended to replace business unit access at more senior or broad scope levels. |

## Environment security group

You can [associate a Microsoft Entra security group with a Dataverse environment to control user access](/power-platform/admin/control-user-access). Unless they have specific, highly privileged Microsoft 365 admin roles, users in Microsoft Entra ID can't access any information in Dynamics 365 even with a valid authentication and security role assigned unless they're also a member of the correct environment security group in Dynamics 365.

It's a best practice to associate a security group with an environment. This prevents all the Microsoft Entra-eligible and appropriately licensed users from appearing as active users in the Dynamics 365 environment.

## Audit

Auditing helps you comply with internal policies, government regulations, and consumer demands for better control over confidential data. Organizations audit various aspects of their business systems to verify that system and data access controls operate effectively and identify suspicious or noncompliant activity.

### Dataverse audit

[Audit logs](/power-platform/admin/audit-data-user-activity) help you ensure the data integrity of the system and meet certain security and compliance requirements. The auditing feature logs the changes that users and admins make to records and user access so that you can review the activity later.

You can enable auditing on the table level, the field level, and on user access. You can view data auditing in three ways:

- Contextually, at the record level, on the form
- Globally, from the audit summary view
- From the APIs

Don't enable auditing for all tables and columns. Do your due diligence to determine which tables and fields you need to audit. Excessive auditing can affect performance and consume large volumes of log storage.

### Microsoft 365 audit log

[Activity logging](/power-platform/admin/enable-use-comprehensive-auditing) records user and admin activities across Microsoft 365 and Dynamics 365 apps. Data is stored in a Microsoft 365 unified audit log, which has a smaller footprint on system resources compared to previous Dataverse audit functionality.

Microsoft 365 audit logs have several other benefits:

- Microsoft 365 admins can manage settings and access activity reporting for all environments within the Microsoft 365 [security](https://security.microsoft.com/) and [compliance portals](https://compliance.microsoft.com/). Dataverse auditing is set up and stored separately within each Dynamics 365 environment.

- All data in the system is logged, including read operations, plug-in operations, table operations, bulk operations, user sign in and sign out, and even Microsoft Support operations.

-You can set up the system to notify administrators or compliance officers of certain events according to configurable settings.

- Administrators can easily search audit logs using predefined or custom filters.

- Admins can use Security Information and Event Management (SIEM) functions in near&ndash;real-time to analyze and get alerts about possible suspicious behavior within the system, and provide actions to address it.

- Dynamics 365 provides out-of-the-box integration with multiple SIEM vendors, such as ArcLight, Microsoft OMS, Okta, SumoLogic, BetterCloud, and standard CEF format integration for many others. Microsoft also released a [connector to integrate activity logs into Azure Sentinel](/azure/sentinel/connect-dynamics-365).

By default, activity logging data is retained for 90 days or one year based on the Microsoft 365 license type. We recommend changing the retention policy or moving these logs to external stores if you need to retain the data for longer periods.

### Lockbox for Microsoft Power Platform

[Lockbox for Microsoft Power Platform](/power-platform-release-plan/2021wave2/power-platform-governance-administration/lockbox-power-platform) lets you give temporary, just-in-time access to your environments to Microsoft engineers to help solve critical support requests.

Lockbox has these core capabilities:

- Administrators can choose which Microsoft Dataverse databases need to be protected by lockbox.

- On the rare occasion that Microsoft needs to temporarily access data in a lockbox-protected database to resolve a critical issue, administrators are notified and can visit the Power Platform admin center to approve or reject the request.

- Once access is granted to Microsoft, any action taking place in the lockbox-protected database during the temporary access period is recorded and made available to your organization as SQL audit logs. You can export these logs to an Azure data lake for further analysis.

### Customer-managed keys

By default, Microsoft manages encryption keys for all Dynamics 365 environments. You can choose to manage your encryption keys yourself, but you should be aware of the potential risks. [Learn more about customer-managed encryption keys](/power-platform/admin/manage-encryption-key).

## Next steps

- Learn about [security features](security-strategy-product-portals.md) in Power Pages
- Learn about [security features](security-strategy-product-oa.md) in finance and operations apps
- Learn how to [make security a priority](security-strategy-day-one-priority.md) from day one
- Use the Success by Design [security checklist](security-strategy-checklist.md) to help identify and prioritize key requirements and implementation activities in the areas of privacy and compliance, identity and access, and application security
