---
title: Customer engagement apps security
description: The customer engagement apps such as Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation use Dataverse to provide a rich security model that can adapt to many business scenarios. This section shares product-specific guidance for security measures customers should consider.
author: riblack-microsoft
ms.author: riblack
ms.topic: conceptual
ms.date: 03/14/2023
ms.service: dynamics-365
---

# Customer engagement apps security

The customer engagement apps (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation) use the [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro) to provide a rich security model that can adapt to many business scenarios. This section shares product-specific guidance for security measures customers should consider.

The goals of Dataverse security model are as follows:

- Provide users with access only to the appropriate levels of information that is required to do their jobs

- Categorize users by role and restrict access based on those roles

- Support data sharing so that users and teams can be granted access to records that they don't own for a specified collaborative effort

- Prevent a user's access to records the user doesn't own or share

Learn more about [Security in Microsoft Dataverse](/power-platform/admin/wp-security)

## Security features

We use three main categories of security features to provide appropriate end-user access (Figure 12-15): fundamental security controls, other security controls, and manual sharing. Most of the security requirements should be addressed using fundamental security controls; other options should be used to manage the exceptions and edge scenarios.

<!--
better to make a table?
-->

:::image type="content" source="media/security-feature-categories.png" alt-text="Three main categories of security features used to provide appropriate end-user access" lightbox="media/security-feature-categories.png":::

### Record ownership

Dataverse supports two types of [record ownership](/power-platform/admin/wp-security-cds):

- Organization owned  

  When a record is assigned to Organization, everyone in the environment can access the record

- User or Team owned  

  If not assigned to the organization, a record is assigned to User, Team, or Business Unit

Some out of the box tables are exceptions to the above two types, for example, system user record is owned by a Business Unit.

### Business units

[Business units](/power-platform/admin/wp-security-cds) are a security modeling building block that helps in managing users and the data they can access. The name "business unit" can be misleading because the term doesn't necessarily have any direct relationship with an organization's operating business units. In Dataverse, business units provide a framework to define the organizational structure of users, teams, and records. Business units group users and teams by organizational hierarchy and can work with security roles to grant or restrict access to data.

The real power of business units comes from their hierarchical nature. Users can be given access to records just in their business unit, or their business unit and the business units under their unit. For example, the hierarchical nature of business units can allow you to limit access to records at the site, district, region, and corporate levels. Business units are useful to segment data into ownership containers for access control.

### New changes in business units

Dynamics 365 has modernized the security model for business units since 2021. Security roles from different business units can now be assigned to a user. This allows a user to access data from different business units based on their security roles.

This change will address some of the following limitations in the current model.

- Users are required to move to the appropriate business unit upon creation in Dataverse (requires special coding/handling).​

- To allow users to access cross-business unit data outside of their BU, owner teams are required.​

- User-owned records follow the user to the new business unit when a user moves from one business unit to another business unit.​

- When an Azure Active Directory (Azure AD) group team is used to manage user access, it can't be used across different busines units.

- Existing business unit is focused on hierarchical organization structure that makes matrix organization data access structure challenging to implement. ​

> [!NOTE]
> As a best practice, minimize the number of business units in your implementation based on access control requirements instead of mapping the organizational chart into business units.

### Security roles

A privilege is permission to perform an action in Dynamics 365. A [security role](/power-platform/admin/security-roles-privileges) is a set of privileges that defines a set of actions that a user can do. Some privileges apply in general (such as the ability to use the export to a Microsoft Excel feature) and some to a specific table (such as the ability to read all accounts).

To access Dynamics 365, users must be assigned one or more predefined or custom security roles, either assigned directly to their user or inherited from a team they're a member of.

For example, the salesperson role is assigned a set of privileges that are relevant to the performance of the tasks defined for that role.

> [!NOTE]
> customer engagement apps come with several out-of-the-box security roles. If you need additional or different security roles, start by copying existing ones.

> [!TIP]
> It is a best practice to create security roles at the root business unit level, as these roles are automatically duplicated for all child business units and can be included in solutions.

Here are some best practices to work with privileged accounts and service accounts.

- Limit and regularly review the list of elevated user and service accounts

- Consider a Just-In-Time access approach to grant elevated privileges

- Consider administrative user to grant access to settings and administration features but not to functionality

- Learn more on [Privileged Identity Management in Azure AD](/azure/active-directory/privileged-identity-management) and [Administrative User in the Power Platform](/power-platform/admin/prevent-elevation-security-role-privilege)

  [!INCLUDE [azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

- Use application accounts for integration and deployment

- Server-to-server (S2S) authentication allows secure and seamless communication between applications and services.

- Learn more on [application users](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user) and [non-interactive user accounts](/power-platform/admin/create-users-assign-online-security-roles#create-a-non-interactive-user-account%c2%a0)

### Teams

[Teams](/power-platform/admin/wp-security-cds) provide a straightforward way to share records, collaborate with other people across business units, and assign security roles. While a team belongs to one business unit, it can include users from other business units. You can associate a user with more than one team, which is a convenient way to grant rights to a user that crosses business units.

Multiple types of teams available are in Dataverse:

- Owner teams  

  You can make an owner team the owner of a record, which is a useful way to link a record to a specific business unit. Owner teams can also share records and be assigned to security roles.

- Azure AD security group teams and Azure AD office group teams  

  These are special types of owner teams. Their membership can't be managed within Dynamics 365, instead they're linked to an Azure AD security group or [Microsoft 365 groups](/microsoft-365/admin/create-groups/compare-groups). If the users are appropriately licensed and part of the environment security group (optional), users who are added to the Azure AD group are automatically enabled in the system and added to the team when they connect to the environment. Using Azure AD is useful because the groups and permissions also extend to Azure AD-enabled apps outside of Dynamics 365.

  [!INCLUDE [azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

- Access teams  

  These teams are unique because they can't own records and can't have a security role association. However, just like owner teams, access teams can have records shared with them. When enabled at the table level, access teams can grant specific record-level permissions to the members of a record's access team. This is an alternative to manually sharing the record with a user or a team.

Use owner teams when:

- Team-level record ownership is required, rather than user

- You need to assign security roles to users through teams

- Reporting on team progress is required

Use access teams when:

- The team members need different permissions on individual records than the same permission on the record type

### Field-level security

You can use [field-level security](/power-platform/admin/field-level-security) to restrict access to high business impact fields to specific users or teams. For example, you can enable only certain users to read or update the credit score of a business customer.

Field-level security is available for the default fields on most out-of-the-box tables, custom fields, and custom fields on custom tables. Field-level security is managed by the security profiles. The scope of field-level security is organization-wide and applies to all data access requests.

### Sharing

[Record sharing](/power-platform/admin/wp-security-cds) lets a user give access to a table record to other users or team. The user must have a share privilege on the record to be able to share it. Sharing should be seen as a way for users to manually manage exceptions to the default security model.

Keep in mind the following recommended practices:

- Share only the necessary records with the smallest set of users or teams possible

- Grant the minimum access required for users to do their jobs

- Disable share rights in security roles where possible

- Extensive sharing can cause performance issues at scale

- Microsoft recommends that you don't automate sharing

### Hierarchy security

You can use a [hierarchy security](/power-platform/admin/hierarchy-security) model for accessing data from a user or position hierarchy perspective. With this extra security, you gain more granular access to records, for example by allowing managers to access the records owned by their reports for approval or to perform tasks on reports' behalf.

:::image type="content" source="media/access-control.png" alt-text="Summary of different access control mechanisms discussed in this section, highlighting the ideal scenarios, benefits, and limitations of each option." lightbox="media/access-control.png":::

## Environment security group

You can [associate an Azure AD security group with a Dataverse environment to control user access](/power-platform/admin/control-user-access). Unless users have specific, highly privileged Microsoft 365 admin roles, a user in Azure AD can't access any information in Dynamics 365 even with a valid authentication and security role assigned unless they're also a member of the correct environment security group in Dynamics 365.

> [!TIP]
> It's a best practice to associate a security group with an environment. This prevents all the Azure AD-eligible (appropriately licensed) users from appearing as active users in the Dynamics 365 environment.

## Audit

Auditing helps you comply with internal policies, government regulations, and consumer demands for better control over confidential data. Organizations audit various aspects of their business systems to verify that system and data access controls operate effectively and identify suspicious or non-compliant activity.

### Dataverse audit

[Audit logs](/power-platform/admin/audit-data-user-activity) are provided to ensure the data integrity of the system and to meet certain security and compliance requirements. The auditing feature logs the changes that are made to records and user access so the activity can be reviewed later.

Auditing can be enabled on:

- Table level (you can select specific fields in a table for auditing)

- User access

Data auditing can be viewed:

- Contextually, at the record level, on the form

- Globally, from the audit summary view

- From the APIs

Don't enable auditing for all tables and columns. Do your due diligence to determine which tables and fields are required for auditing. Excessive auditing can affect performance and consume large volumes of log storage.

### Microsoft 365 audit log

[Activity logging](/power-platform/admin/enable-use-comprehensive-auditing) records user and admin activities across Microsoft 365 and Dynamics 365 apps. Data is stored in a Microsoft 365 unified audit log. It has a smaller footprint on system resources compared to the previous Dataverse audit functionality. Microsoft 365 audit logs have several other benefits:

- Management in a central location on the Microsoft 365 security and compliance portals  

  Microsoft 365 admins can manage settings and access activity reporting for all environments within the Microsoft 365 [security](https://security.microsoft.com/) and [compliance portals](https://compliance.microsoft.com/). Dataverse auditing is set up and stored separately within each Dynamics 365 environment.

- All data in the system is logged  

  This functionality logs all data transactions, including read operations, plug-in operations, table operations, bulk operations, user sign in and sign out sessions, and even Microsoft Support operations.

- Configurable alert policies  

  You can set up the system to notify administrators or compliance officers of certain events according to configurable settings.

- Audit log search capability  

 Administrators can easily query audit logs via predefined or custom filters.

- Analyze suspicious behavior with Security Information and Event Management (SIEM)  

  Use SIEM functions in near-real time to analyze and alert administrators of possible suspicious behavior within the system and provide actions to address these events.

- SIEM vendor integration Dynamics 365 now provides out-of-the-box integration with multiple SIEM vendors such as ArcLight, Microsoft OMS, Okta, SumoLogic, BetterCloud, and standard CEF format integration for many others. Microsoft has also released a [connector to integrate activity logs into Azure Sentinel](/azure/sentinel/connect-dynamics-365).

By default, activity logging data is retained for 90 days or one year based on the Microsoft 365 license type. We recommend changing the retention policy or moving these logs to external stores if you need to retain the data for longer periods.

### Lockbox for Microsoft Power Platform

[Lockbox for Microsoft Power Platform](/power-platform-release-plan/2021wave2/power-platform-governance-administration/lockbox-power-platform) (Dynamics 365 CE apps) provides interface for organizations to control temporary just-in-time access to their environments for Microsoft engineers to help solve critical support requests. It's important for the compliance needs of customers.

There are three core capabilities included with lockbox:

- Administrators can choose which Microsoft Dataverse databases need to be protected by lockbox.

- On the rare occasion that Microsoft needs to temporarily access data in those lockbox-protected databases to resolve a critical issue, administrators will be notified and can visit the Power Platform admin center to approve or reject the data access request.

- Once access is granted to Microsoft, any action taking place in the lockbox-protected database during the temporary access period is recorded and made available to your organization as SQL audit logs. These logs can be exported to an Azure data lake for further analysis.

### Customer Managed Keys (CMK)

Dynamics 365 uses heterogenous storage (Dataverse) to store the data. The data is distributed across different storage types:

- Azure SQL Database for relational data

- Azure Blob storage for binary data, such as images and documents

- Azure Search for search indexing

- Microsoft 365 Activity Log and Azure Cosmos DB for audit data

By default, Microsoft manages encryption keys for all the Dynamics 365 environments. Customer Managed Keys provide another option for key management. For detailed information, including some of the potential risks associated with CMK, refer to [Manage the encryption key](/power-platform/admin/manage-encryption-key)

## Next steps

- Learn more about [Security in Microsoft Power Platform](/power-platform/admin/security/overview)
- Learn more about [Power Pages Security](security-strategy-product-portals.md)
- Learn more about [finance and operations apps security](security-strategy-product-oa.md)
- [Make security a day one priority](security-strategy-day-one-priority.md)
