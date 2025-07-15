---
title: Secure your Dynamics 365 project from day one
description: Discover why security is vital for Dynamics 365 projects and how to create a strategy that ensures compliance, scalability, and risk mitigation.
author: riblack-microsoft
ms.author: riblack
ms.topic: concept-article
ms.date: 05/12/2025
ms.update-cycle: 1095-days
ms.custom:
  - evergreen
  - ai-seo-date: 01/22/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Secure your Dynamics 365 project from day one

Don't wait until the last minute to think about security for your Dynamics 365 project. Security is a key factor that affects many aspects of your solution, such as compliance, scalability, performance, reporting, and rollout. Neglecting security requirements can lead to serious legal, financial, and business risks, as well as delays in your implementation project. This article explains how security impacts Dynamics 365 and provides actionable steps to plan a security strategy that meets your needs.

Before you design a solution, you should ask yourself some questions, such as:

- What legal, policy, or compliance certification requirements do you have to follow?

- What data privacy or residency requirements do you have to meet?

- What security validation or other compliance requirements do you have to pass, and how will you do that?

- How will you ensure compliance with the applicable legal requirements?

The answers to these questions will help you shape your security strategy. You should consult with the compliance and audit stakeholders in your organization and gather their requirements as early as possible. This way, you can make sure your solution complies with your rules and regulations, and you have enough time to validate your compliance. Dynamics 365 provides frameworks and tools that can help you implement secure processes, but software packages alone don't guarantee compliance.

> [!IMPORTANT]
> Data privacy or residency requirements are a foundational consideration for solution design and can affect where you can deploy your solution.
>
> - Check the availability of the Dynamics 365 apps and Power Platform components that you want to use in the desired cloud: [Product Availability by Geography](https://dynamics.microsoft.com/availability-reports/)
> - Check the availability of the Azure solution that's part of your architecture in the desired cloud and region: [Azure Products by Region](https://azure.microsoft.com/explore/global-infrastructure/products-by-region/)

## How security affects scalability

Your security design significantly impacts how your solution scales, especially for multi-phased and global deployments. To ensure future growth, consider scalability early when designing your security model. Avoid short-sighted decisions that could limit expansion. The following sections provide examples to guide your planning.

### Example 1: Business unit access

In multi-phased global deployments, different regions might have different compliance, business process, and security requirements. The same security model might not work for all regions. You should think about your security model holistically at the start of the project.

For example, suppose you have a global deployment where you create all users in the root business unit with business unit-level access in security roles. This works for the first region (Phase one), but when you roll out the solution to the next region (Phase two), you run into a problem. The Phase two users can access the users in the first region, which might cause some regulatory or compliance issues.

### Example 2: Entity ownership

Some businesses use [Organization owned entities](/power-platform/admin/wp-security-cds) for reference data tables, which means security roles don't apply to them. In multi-phased deployments, some departments might not want other departments to see their reference data, or they might want to see only their reference data when they create records. This segmentation is hard to achieve with Organization owned entities and easier to achieve with User or Team owned entities that have business unit access. Entity ownership is a choice that you make when you create the entity and you can't change it later. Your choice controls who can access the entity. If you want to change the access to these entities, your only option is to delete and recreate them with a different owner.

Follow best practices when you design role-based access control. Otherwise, subsequent rollouts won't be able to use and build on established security roles. Design security roles based on business processes, and incorporate segregation of duties, not individual personas. Don't create a single role for each user, and don't create nested security roles. The resulting modular security roles can be assigned to users as they cumulatively give the access needed for a user's duties, and no more. This approach makes it easier to manage security roles and reduces the number of security roles that you need to create and maintain.

## How security affects performance

Your security design can also affect the system performance. Dynamics 365 has multiple access control mechanisms, each with its own advantages and disadvantages. The ideal security design is a combination of one or more of these controls, based on your requirements and the granularity, simplicity, and scalability they offer. The wrong choice can lead to poor performance. Here are some examples:

### Example 1: Sharing

Sharing lets you grant specific and unique permissions on a specific record, but sharing a large number of records can be costly. For example, to check access for a user, the system checks the user's security roles and team memberships, and the shared records. Checking many rules can lead to performance, storage, and maintenance overhead.

Sharing can also trigger cascading rules that can be costly if not set properly. You should use sharing for edge cases and exceptions, not for regular access.
<!-- To learn more, download our [Modeling Scalable Security with Microsoft Dynamics CRM](https://www.microsoft.com/download/confirmation.aspx?id=40861) whitepaper. It's an older document and talks about products that are out of mainstream support, but it's still relevant for Dynamics 365 security. -->

The volume of data also affects performance in the end. You should have a well-defined archival strategy. You can make the archived data available through other channels.

### Example 2: Database logging

Database logging in finance and operations apps can be valuable from a business perspective, but it can be expensive in terms of resource use and management. Here are some of the performance implications of database logging:

- The database log table can grow quickly and increase the size of the database. The amount of growth depends on how much logged data you keep.

- When you turn on logging for a transaction type, each instance of that transaction type causes multiple records to be written to the SQL Server transaction log file. Specifically, one record is written for the initial transaction, and one record logs the transaction in the database log table. Therefore, the transaction log file grows faster and might require more maintenance.

- Database logging can adversely affect long-running automated processes, such as inventory close, calculations for bills of materials, master planning, and long-running data imports.

- When you turn on logging for a table, all set-based database operations are downgraded to row-based operations. For example, if you're logging inserts for a table, each insert is a row-based insert.

When you implement database logging, make sure you have a plan for how long you'll keep the logged data. Don't keep data indefinitely. You should also limit the log entries by selecting specific fields to log instead of whole tables.

[Extensible Data Security (XDS) policies](/dynamics365/fin-ops-core/dev-itpro/sysadmin/extensible-data-security-policies) let developers supplement role-based security by restricting access to table records based on security policies. The query in the policy (the policy query) applies a filter so only records that satisfy the conditions of the filter are accessible from the restricted tables. The policy query is added to the WHERE clause, or ON clause, on SELECT, UPDATE, DELETE, and INSERT operations on the specified constrained tables.

Unless you design and test them carefully, policy queries can have a significant performance impact. Therefore, you should follow the important guidelines when you develop an XDS policy. Poorly performing queries can have a serious impact on performance. As a best practice, avoid many joins, consider adding lookup tables to improve performance, tune queries for optimal performance, and test any XDS policies thoroughly when you use this feature.

## How security affects regulation and compliance

Depending on your industry and region, you might have different security controls that you need to meet for regulation and compliance. These controls can include duty separation, data categorization, identity management, access control, log management, and auditing. If you miss any of these controls, your solution might not be compliant.

Governance takes time to understand, roll out, and adopt. The sooner you start the process, the easier compliance becomes.

### Example: Activity logging

The activity logging data is retained between 90 days and 1 year, depending on the Microsoft 365 license type. For compliance reasons, if you need to keep these records longer, you should move this data to an external store.

## How security affects rollout

In many projects, security design is created late in the implementation process. This can lead to many issues, from system design to inadequate testing. You should keep the following best practices in mind:

- Test the system using the right security roles from the very beginning.

- Use the correct security profile during test cycles. Don't give everyone an administrator role.

- When you train people, make sure they have access to do all the required actions. They shouldn't have access to more information than they need to complete those actions.

- Validate security before and after data migration.

### Example: Role-based access control

Design your security roles with both compliance and scalability in mind. By engaging your security and compliance team early in your implementation, you can use the segregation of duties framework to identify conflicts and create rules that enforce separation of duties.

For example, a global company has standardized business processes and is planning to roll out a new functionality in multiple phases globally. Rules that segregate duties in its large legal entities prevent assignments that might result in conflicts.

However, in smaller legal entities, users might need to do the same tasks with a smaller staff, which makes it hard to construct declarative rules that enforce segregation of duties. In this case, modular security roles enforce the same segregation of duties rules, but by assigning multiple roles to some users and applying documented overrides to the detected conflicts. This way, the global rollout can reuse modular security components, and the organization has a robust segregation of duties framework in place for entities of different sizes, allowing them to grow without introducing the need to redesign the security implementation.

## How security affects reporting

Your security design can have a significant impact on reporting. For example, your security design might identify sensitive data that requires restricted access and monitoring. You might need to create auditing reports related to access and changes on sensitive data, and designated personnel responsible for oversight might need to review them periodically.

In addition to built-in reporting capabilities, you have multiple options for exporting Dynamics 365 data into external stores for reporting and analytics. The two native options are exporting to a data lake or using the Data Export Service (not available for finance and operations apps). When data is in external stores, it doesn't honor Dynamics 365 security permissions (and it wouldn't be useful to do so in many cases). You need to apply your own security mechanism for reporting. We recommend having a data management strategy for all data that's stored outside a core application. This strategy should include security requirements like encryption, access controls, row level, and personal data, and data residency and retention requirements. The strategy should consider the future state of Dynamics 365 data in the analytical platform and its legacy and other applications.

You can use [Tabular Data Stream (TDS)](/powerapps/maker/data-platform/view-entity-data-power-bi) endpoints for direct query scenarios with customer engagement apps. It supports the Dynamics 365 security context.

## Operational aspects of security

Operational aspects can have a significant impact on security design. Operational aspects can determine which access mechanisms are the best fit for the solution, such as in cases of organizational changes or maintenance.

### Organizational changes

What happens if a user moves to another team or business unit? Do you need to reassign the records the user owns? What should the process be? Do you reassign all records or just the active ones? What's the effect of changing the ownership on the child records, especially closed activities, closed cases, and won or lost opportunities? Based on these questions, you can come up with a process and cascading rules in Dynamics 365.

Reassigning a large number of records can take a long time and affect the system's performance. [Learn more about assigning or sharing records](/powerapps/user/assign-or-share-records).

### Maintenance overhead

Plan how to assign security roles to new users. Will you automate a process? For example, use [group teams](/power-platform/admin/manage-group-teams) in Dynamics 365 to assign roles to new team members. This way, it's easier to assign licenses and security roles to new team members.

[!INCLUDE [azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

## Next steps

- Use the Success by Design [security checklist](security-strategy-checklist.md) to identify and prioritize key requirements for privacy, compliance, identity, and application security.  
- Explore related topics here on Microsoft Learn to deepen your understanding of security strategies for Dynamics 365.  
