---
title:  Make security a day one priority
description: Address the importance of making security a priority from day one, with specific examples from each product that build upon the concepts discussed in the Implementation Guide.
author: riblack-microsoft
ms.author: riblack
ms.topic: conceptual
ms.date: 04/12/2023
ms.service: dynamics-365
---

# Make security a day one priority

Security should be at the forefront when you start a Dynamics 365 project, not an afterthought. Negligence of security requirements can lead to significant legal, financial, and business risks, and delays in your implementation project. It can also impact the overall scalability and performance of the solution. In this section, we discuss some of the security impacts on Dynamics 365.

The following are examples of questions that should be addressed before you design a solution:

- Are there specific legal, policy, and/or compliance certification requirements with which you must comply?

- Are there data privacy or residency requirements?

- Are there requirements for security validation or other compliance requirements, and what are the plans to address them?

- What steps have you taken to ensure compliance with the applicable legal requirements?

Legal and regulatory compliance requirements and answers to the questions above typically form the underpinnings of your security strategy. Consult with compliance and audit stakeholders in your organization and gather their requirements as early as possible to ensure the solution complies with your rules and regulations, and that you have ample opportunity to validate that compliance. Dynamics 365 provides frameworks and tools that can be used to help you implement secure processes, but software packages alone don't provide compliance.

> [!IMPORTANT]
> Data privacy or residency requirements are a foundational consideration for solution design and can impact where your solution may be deployed.  
>

Check that the desired Dynamics 365 apps and Power Platform components are available in the desired cloud: [Product Availability by Geography](https://dynamics.microsoft.com/availability-reports/)

Check any Azure solution that is part of your architecture is available in the desired cloud and region here: [Azure Products by Region](https://azure.microsoft.com/explore/global-infrastructure/products-by-region/)

## Impact on scalability

Security design can have a significant impact on scalability and should consider scalability especially for multi-phased and global deployments. Consider the following examples:

### Example 1 of security impact on scalability

In multi-phased global deployments, short-sighted security design can affect the rollout to other regions. The different regions may have their own compliance, business process, and security requirements. The same model may not work for all the regions. So think about the security model holistically at the beginning of the project.

One such example can be a global deployment where in the first region (Phase one) you create all users in the root business unit with business unit-level access in security roles. Because Phase one users were placed in the root business unit, when you roll out the solution to the next region (Phase two), Phase two users have access to the users in the first region. This setup may cause some regulatory or compliance issues.

Several businesses use [Organization owned entities](/power-platform/admin/wp-security-cds) for reference data tables, which means security roles don't apply to these entities. In multi-phased deployments, some departments may not want other departments to see their reference data. Or they just want to see their reference data appear when creating records. This segmentation is hard to achieve using Organization owned entities and simpler to achieve when User or Team owned entities have Business Unit access. Entity ownership is a choice that happens at the time the entity is created and can't be changed. This assignment controls who can access the entity. If you want to change who has access to these entities, the only option you have is to delete these entities and recreate them in an owner (Organization, Team, Business Unit, and so on) that is properly scoped.

### Example 2 of security impact on scalability

Similarly, different legal entities may have distinct functions and purposes, be subject to different security constraints, and have different security requirements. Even if legal entities, subsidiaries, or regions have a high degree of standardization and centralization and are good candidates for streamlined security implementation, failing to source requirements from the right stakeholders, design security as modular building blocks, or otherwise fail to take a long-term view of security needs can result in subsequent rollouts struggling with ill-fitting global templates or a need to start over from scratch.

Design of role-based access control should follow best practices. Otherwise, subsequent rollouts will be unable to use and further build upon established security roles. Design security roles based on business processes, and incorporate segregation of duties, not individual personas. Don't create a single role for each user, and don't create nested security roles. The resulting modular security roles can be assigned to users as they cumulatively give the access needed for a user's duties, and no more.  

Tools such as the [Task recorder](/dynamics365/fin-ops-core/dev-itpro/user-interface/task-recorder-training-docs) <!--and the [Regression suite automation tool](/dynamics365/fin-ops-core/dev-itpro/perf-test/rsat/rsat-overview) -->for finance and operations apps support the testing of individual user permissions, which facilitate this approach. We also recommend following recommended practices for the initial rollout (such as copying standard roles rather than directly assigning them). This gives subsequent rollouts the flexibility of building upon existing role structures, while retaining access to standard roles for comparison. This way, subsequent rollouts don't have to choose between modifying roles already in use elsewhere or starting from scratch because existing roles are too specialized.

## Impact on performance

Security design can impact system performance. Dynamics 365 has multiple access control mechanisms, all with their own pros and cons. The ideal security design is a combination of one or more of these controls based on your requirements and the granularity, simplicity, and scalability they provide. The wrong choice can lead to poor performance. Consider the following examples:

### Example 1 of security impact on performance

Sharing provides particular and unique permissions on a specific record but sharing for large volumes of records comes at a cost. To check access for a user, the system checks user security roles, team memberships, and records shared with a user and their teams. Checking lots of rules is expensive in terms of performance, storage, and maintenance overhead.

Sharing can also trigger cascading rules that can be expensive if not set appropriately. Sharing should be for edge cases and exception scenarios.

Learn more in this download from the [Modeling Scalable Security with Microsoft Dynamics CRM](https://www.microsoft.com/download/confirmation.aspx?id=40861) whitepaper. It's an older document and talks of products out of mainstream support, but it's still relevant for Dynamics 365 security.

The volume of data will impact performance in the end. You should have a well-defined archival strategy. The archived data can be made available through some other channels.

### Example 2 of security impact on performance

Database logging in finance and operations apps can be valuable from a business perspective, but it can be expensive regarding resource use and management. Here are some of the performance implications of database logging:

- The database log table can grow quickly and increase the size of the database. The amount of growth depends on the amount of logged data that you retain.

- When logging is turned on for a transaction type, each instance of that transaction type causes multiple records to be written for the Microsoft SQL Server transaction log file. Specifically, one record is written for the initial transaction, and one record logs the transaction in the database log table. Therefore, the transaction log file grows more quickly and might require more maintenance.

- Database logging can adversely affect long-running automated processes, such as inventory close, calculations for bills of materials, master planning, and long-running data imports.

- When logging is turned on for a table, all set-based database operations are downgraded to row-based operations. For example, if you're logging inserts for a table, each insert a row-based insert.

When you implement database logging, make sure you have a plan for how long you'll retain logged data. Don't allow data to be retained indefinitely. You must also plan how you'll limit log entries; help improve performance by selecting specific fields to log instead of whole tables.

[Extensible Data Security policies](/dynamics365/fin-ops-core/dev-itpro/sysadmin/extensible-data-security-policies) allow developers to supplement role-based security by restricting access to table records based on security policies. The query in the policy (the policy query) applies a filter so only records that satisfy the conditions of the filter are accessible from the restricted tables. The policy query is added to the WHERE clause, or ON clause, on SELECT, UPDATE, DELETE and INSERT operations involving the specified constrained tables.

Unless carefully designed and tested, policy queries can have a significant performance impact. Therefore, make sure to follow the important guidelines when developing an XDS policy. Poorly performing queries have a serious impact on performance. As a best practice, avoid numerous joins, consider adding lookup tables to improve performance, carefully tune queries for optimal performance, and carefully and thoroughly test any XDS policies when using this feature.

## Impact on regulation and compliance

Several different security controls are required to meet regulations and compliance based on industry and region. These controls are a combination of duty separation, data categorization, identity management, access control, log management, and auditing. Missing any of these controls can make your solution noncompliant.

Governance takes time to understand, roll out, and adopt. The earlier you begin the process; the easier compliance becomes.

### Example of security impact on regulation and compliance

The activity logging data is retained between 90 days to 1 year based on the Microsoft 365 license type. For compliance reasons, if you need to keep these records for longer, you should move this data to an external store.

## Impact on rollout

In many projects, security design is created late in the implementation process. It can lead to many issues, ranging from system design to inadequate testing. Keep the following recommended practices in mind:

- Test the system using the right security roles from the very beginning.

- Use the correct security profile during test cycles. Don't provide an administrator role to everyone.

- When training people, make sure they have access to make all the required actions. They shouldn't have access to more information than required to complete those actions.

- Validate security before and after data migration occurs.

### Example of security impact on rollout

Design your security roles with both compliance and scalability in mind. By engaging your security and compliance team early in your implementation, you can use the segregation of duties framework to identify conflicts and create rules that enforce separation of duties that should be separated.

For example, a global company has made efforts to standardize business processes and is planning to roll out a new functionality in multiple phases to globally. Rules that segregate duties in your large legal entities prevent assignments that may result in conflicts.

However, in smaller legal entities, users may need to accomplish the same tasks with a smaller staff, which makes it challenging to construct declarative rules that enforce segregation of duties. In this case, modular security roles allow you to enforce the same segregation of duties rules but when assigning multiple roles to some users and apply documented overrides to the detected conflicts. In this manner, your global rollout can reuse modular security components, and you have a robust segregation of duties framework in place for entities of many sizes, allowing them to grow without introducing the need to redesign the security implementation.

## Impact on reporting

Security design can have a significant impact on reporting. For example, your security design identifies sensitive data that requires restricted access to be enforced and monitored. You need to create auditing reports related to access and changes on sensitive data, and designated personnel responsible for oversight need to review them periodically.

In addition to built-in reporting capabilities, you have multiple options for exporting Dynamics 365 data into external stores for reporting and analytics. The two native options are exporting to a data lake or using the Data Export Service (not available for finance and operations apps). When data is in external stores, it doesn't honor Dynamics 365 security permissions (nor would it be useful to do so in many cases). You need to apply your own security mechanism for reporting. We recommend having a data management strategy for all data that is stored outside of a core application. This strategy should include security requirements (encryption, access controls, row level, personal data) and data residency and retention requirements. The strategy should consider the future state of Dynamics 365 data in the analytical platform and its legacy and other applications.

You can use [Tabular Data Stream (TDS)](/powerapps/maker/data-platform/view-entity-data-power-bi) endpoints for direct query scenarios with customer engagement apps. It supports the Dynamics 365 security context.

## Operational aspects of security

Operational aspects can have a significant impact on security design. Operational aspects can decide which access mechanisms are the best fit for the solution, such as in cases of organizational changes or maintenance.

### Organizational changes

What happens if a user moves to another team or business unit? Do you need to reassign the records owned by the user? What should the process be?

Do you reassign all records or just the active record? What is the effect of changing the ownership on the child records, especially closed activities, closed cases, and won or lost opportunities? Based on these questions, you can come up with a process and cascading rules in Dynamics 365.

Reassigning a large volume of records can also take a long time and affect the system's performance. Learn more about [assigning or sharing rows](/powerapps/user/assign-or-share-records).

### Maintenance overhead

Plan out how to assign security roles to new users. Are you going to automate a process? For example, use [group teams](/power-platform/admin/manage-group-teams) in Dynamics 365 to assign roles to new team members. This way, it's easier to assign license and security roles to new team members.

[!INCLUDE [azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

## Next steps

- View more security [resources](security.md#resources)

Visit the next section of the Implementation Guide

- [Business intelligence, reporting, and analytics](business-intelligence-reporting-analytics-overview.md)

Return to learn more about security in Dynamics 365

- [Security strategy overview](security.md)
