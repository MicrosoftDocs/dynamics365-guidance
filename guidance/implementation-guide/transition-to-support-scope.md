---
title: Define the support scope
description: Learn how to plan the support model for your Dynamics 365 solution, including overviews on enterprise achitecture and business and IT policies.
author: taksatoms
ms.author: tsato
ms.date: 01/31/2024
ms.topic: conceptual
ms.custom:
 - ai-seo-date: 01/31/2024
 - ai-gen-docs-bap
 - ai-gen-title
 - ai-gen-desc
content_well_notification: AI-contribution
---

# Define the support scope

The support scope is what you support, who supports it, when they support it, and how they support it. You should start defining the support scope in the **Initiate** phase of your project. You might be tempted to delay this task until later because it seems less urgent than getting the project started and creating the system solution. But as this article explains, defining the support scope early helps you engage the support team in the project from the beginning. This pays off during the project lifecycle.

## Enterprise architecture

Your Dynamics 365 system is part of a larger enterprise system landscape. It connects to multiple systems and technologies. When you design your support model, don't focus only on the Dynamics 365 application architecture. Think about how the surrounding architecture affects the Dynamics 365 applications, and how they affect it. For example, how will installing and running the Dynamics 365 application affect the enterprise architecture and environment?

First, use the enterprise system architecture documents to identify all the systems, software, and data that interact with Dynamics 365 applications. Make a distinction between new systems that you're introducing into the enterprise architecture and those that might be affected by them.

During the project, you'll probably implement the new Dynamics 365 system in a special sandbox or test environment. This environment might not have all the influences and rules that apply to the production system. This also applies to partner test systems that are part of integrations. For example, production environments have more limited access to the Dynamics SQL database, and you don't apply custom code or Microsoft system updates in the same way. You should examine how the production system environment affects support operations. Don't rely only on what you learn from the test environment.

Identify any new or changed support requirements that are affected by these areas:

- Enterprise-level architecture configurations such as Microsoft Azure, operating systems, Microsoft 365 tenants, and Microsoft Entra ID

- Dynamics 365 Azure environments that are managed by Microsoft, such as production

- Identity and access management systems such as operating systems, browsers, mobile devices, and firewall configurations

- If this is your first major cloud or software as a service (SaaS) system in the enterprise, the related system architecture and servicing needs

- Systems that connect directly to Dynamics 365 applications

- Middleware systems that Dynamics 365 applications might connect to

- Any systems that you'll decommission but that have leftover tasks that the support team might need to take over

- Any document management systems such as Microsoft SharePoint or non-Microsoft systems

- Any code configuration management systems such as Azure DevOps or non-Microsoft systems

- Reporting systems that connect to Dynamics 365 applications, including Azure Data Lake or data warehouse

The impact of and on the surrounding architecture can be hard for the customer project team working on the Dynamics 365 business application to fully identify. In most cases, you need the enterprise architects from IT and the business to help you identify the changes. Some changes might also affect the roles of people who are part of a support organization or other organizations.

## Business and IT policies

All organizations need to think about how new systems will work within their policies and standards. When you introduce Dynamics 365 into your enterprise, it needs to follow existing policies and standards that apply, and you might need some new policies for it. In either case, you need to review the existing policies and standards to decide which ones to add, change, or apply to your support model.

:::image type="content" source="media/transition-to-support-scope.png" alt-text="Diagram of support policies and standards hierarchy, showing group and company policies, Dynamics 365 app policies, and Dynamics 365 security and access policies." lightbox="media/transition-to-support-scope.png":::

In many cases, the policies apply not only to creating the support model and its scope of responsibility, but also to how it works as an organization and how it handles the lifecycle of a support request.

### Group and company policies and standards

When you evaluate group-level policies or standards, you might have to consider how business policies and procedures affect different levels:

- **Contracting with and managing partner vendors**: Your support model needs some kind of contract with technology partners and Microsoft.

- **Operating hours**: Your current and future operating hours can affect when you need support.

- **Financial period end and seasonal deadlines**: You might need a higher level of service at times when you have critical business activities.

- **IT policies on change control on enterprise IT assets**: These policies might affect how you access and approve changes for troubleshooting or servicing Dynamics 365 applications, such as creating new Azure virtual machines, copying databases between environments, or building IP allowlists.

Your overall support model for Dynamics 365 business applications covers many of your business processes, so it's shaped by the relevant business policies.

### Dynamics 365 app-level policies

Some policies are managed in the system by the business administrators. Some might be delegated to the support team. Even if the business leads are responsible for administering a policy, the support team might need to help with monitoring or compliance.

You can set up some of these policies within Dynamics 365 applications, such as new vendor approval policies, customer credit limits, purchase order approval thresholds, and travel and expense policies. The support team might need to help enforce these policies or monitor compliance.

### Dynamics 365 application-level security and access management

The support team is usually responsible for administering and reviewing application-level security. The support team needs to understand the Dynamics 365 role-based application security model and the related access policies.

### Group- and company-level security and access management

In addition to the security and access policies and procedures that you need for Dynamics 365 applications, you might have to consider enterprise-level security policies that intersect with the application-level security requirements.

In larger organizations, a separate IT organization or team might handle enterprise-level security and access management. Some of the support team members will need higher access not only at the application level, but also for other systems in the enterprise.

The Dynamics 365 support team needs to work with these other IT and business teams to define the rules and procedures for managing some of the security topics that might affect Dynamics 365 applications:

- Microsoft Entra ID groups and identities

- Single sign-on (SSO)

- Multifactor authentication

- Mobile device authentication and management

- Authentication and management for custom applications working on Microsoft Dataverse, such as Power Platform apps, which requires an understanding of [Dataverse security concepts](/power-platform/admin/wp-security-cds)

- Application access for third parties such as vendors and customers

- Application access for partner support organizations such as technology partners and Microsoft

- Service account and administrator account use and management

- Password renewals and security certificate rotations

- Secure and encrypted communications within and outside the enterprise, such as those involved with integrations with internal systems or external web services or banking systems

The [Microsoft Trust Center](https://www.microsoft.com/trust-center) can help your organization consider [overall security](https://www.microsoft.com/security) and [managing compliance](https://www.microsoft.com/trust-center/compliance/compliance-overview) in the cloud. [Learn more about security strategy](security.md).

### Data classification and retention

Think about how your data classification and retention policies apply to or need to include the new Dynamics 365 application:

- How will the support team enable and enforce these policies?

- How will they affect backup, restore, and archive processes?

- How will they affect creating and managing database copies?

- Do any data classification properties flow between systems? Or do they need to be recreated or audited by the support team?

### Regulatory compliance and policies

Besides any data retention policies, your business might be subject to national or international regulations. Some might affect business processes that the support team needs to help with, such as e-invoicing or digital tax. The support team might need to help monitor or audit other regulations regularly or occasionally.

All these different areas of business and IT policies shape the nature, size, and scope of your support organization. Examining these factors early will help your team be effective from the start.

## Dynamics 365-specific topics

In this section, we look at some topics specific to Dynamics 365 business applications that you should consider when you design your support model. You can group these topics broadly by operational and maintenance topics and business process topics.

### Operational and maintenance topics

You can divide operational and maintenance areas into managing and supporting these areas:

- Dynamics 365 environments
- Integrations
- System and data maintenance
- Performance

### Dynamics 365 environments

When Dynamics 365 is in production, you need to consider various aspects of supporting the system environments when you define your support scope. These include:

- Maintenance and operational tasks (both scheduled and unplanned), such as refreshing environment data, moving databases between environments, moving configurations, and promoting code

- Support organization roles and resources needed

- Skills required to support the environments

- Budget impact

You typically need to do these tasks and consider these factors for these environments:

- Dynamics 365 application support environments, which are recent copies of the production system

- Test environment for testing the next versions of the application software

- Test environments for integrated systems

- Development environments

- Any related data migration, training, or integration environments

This isn't a complete list of environments, but it should help you think about how to support them. [Learn more about environment strategies](environment-strategy-overview.md).

### Integrations

Besides defining the environments that you need for supported operations, it's worth looking deeper into the support requirements that are specific to managing integrations. When you define the support requirements for all the integrations, consider what areas are in scope for the support organization:

- Data management at both ends of the integration
- Security of the integration services
- Performance of the integration
- Auditing or monitoring of the integration
- General troubleshooting analysis and stopping and starting of integration services

The level of skill and effort that's required to manage integrations depends on their complexity, criticality, and robustness. Designs of custom integrations that can handle variations in data distribution and volume, that are resilient to errors, and that have self-healing mechanisms need less support.

### System maintenance requirements

As part of defining the system, you should also define the maintainability requirements. This is an area that sometimes doesn't get enough attention, and it can result in unplanned work for the support organization. During the **Initiate** phase of your project, your current support organization should look for the specific maintenance requirements for managing the new Dynamics 365 implementation.

Because Dynamics 365 apps are cloud- and SaaS-based, Microsoft manages many maintenance tasks and responsibilities that are common to on-premises solutions. In general, you have less work to do with infrastructure configuration and maintenance for production systems. This gives you more time to focus on managing and improving business process performance.

Define the system maintenance requirements and what is within your support team's responsibilities. These are typically in these areas:

- Servicing nonproduction environments, which can include:

  - Requesting and configuring new Dynamics 365 environments
  - Requesting and configuring database copies and restores between environments
  - Managing any customer-managed, cloud-hosted environments
  - Doing backups when requested

- Managing system operations, which can include:

  - Assigning users to security roles
  - Reviewing and running periodic system cleanup jobs
  - Managing system administration messages and notifications
  - Batch calendar management
  - System update calendar

### Data maintenance requirements

Data maintenance is a big part of running a business system, and it's essential that you clearly define the data management scope for your support team. Much of the data maintenance will be done by data stewards from your business, but the support team might need to manage some critical areas.

Typically, in a Dynamics 365 application, a support team might manage system administrator data, some types of primary data, security and access data, and data that's related to periodic processes.

### Performance management

Performance management for a Dynamics 365 business application is a mix of tasks and responsibilities for Microsoft and for you. In this section, we consider how this affects your support model.

Your support team needs some way to proactively monitor and respond to performance issues that users report. Your support team needs to be able to do these things:

- Understand how the performance issue affects the business

- Assign the right priority

- Diagnose the issue across the possible root causes to determine the root cause, or hand it off to a specialist team (internal or external) with a good starting point

- Reproduce the steps and circumstances that demonstrate the performance issue, and have the necessary resources to do this

- Communicate the problem to other more technical specialists and work with them to solve it

To better detect processes that start to show poor performance, it's important to have a baseline definition of required performance for critical processes, expressed as performance goals. Having actionable performance goals helps you monitor and act proactively to identify and stop any decline in performance.

Because performance troubleshooting is a specialist skill, your internal support team might not have all the skills and experience to examine and fix the performance of custom development. It's also a skill that you might need only occasionally. You might need to plan for access to external teams that can use specialist performance tools, interpret the results, and decide on corrective actions.

## Business processes

Supporting users in their daily processes is a key function of a Dynamics 365 support organization. Your support organization should provide coverage across all the key business processes&mdash;or at least, know where to direct questions and issues that are outside their support scope.

Based on the definition of the key business processes in scope, consider these things for each process:

- What level of expertise do you need in the business process?

- What are the likely support tasks and queries related to this process?

- What type of usage, frequency, and volume do you have?

- How critical is this business process for your business outcomes, and what degree of priority do you need for support issues?

- What type and level of skills do you need to support this process?

- What processes need resources at a department, workstream, or value chain level?

- What are the interactions with other systems and communication protocols required?

- Does this process require your support staff to have special security or compliance training or certification?

- Do you have any special requirements for support services outside your expected support hours, that is, outside normal business hours or during holidays?

An important factor when you determine resources and escalation procedures is how much ownership and responsibility your business process leaders will take from their own organization to support their daily operations.

## Business continuity

Many organizations need a business continuity strategy and regular checks of business continuity if there's a service outage. You might need this because of external regulations or internal policies. In any case, your support organization probably needs to play a major role.

Depending on the size and complexity of your system landscape and the types of service outage scenarios that you're testing, you might need a lot of preparation, coordination, and timely communication between multiple parties.

As part of preparing to set up your support organization, you should consider your business continuity strategy and what resources, skills, and tools you need.

As a cloud-based SaaS service, Microsoft provides the production infrastructure, platform, and application-level business continuity services. For Dynamics 365 Finance and Dynamics 365 Supply Chain Management apps, the operations listed in the [service description for finance and operations apps](https://aka.ms/D365-Cloud-Service-Operations) provide details of the services and service-level agreements (SLAs) from Microsoft and your expected responsibilities and actions. You should keep this in mind when you build your business continuity plan. It should reflect your specific system landscape and scenarios.

### Dynamics 365 Finance and Supply Chain Management

Dynamics 365 Finance and Supply Chain Management have specific [high-availability (HA) and disaster recovery (DR)](/dynamics365/fin-ops-core/dev-itpro/deployment/cloud-deployment-overview#availability) features for cloud deployment. To ensure service availability, all production environments are protected using default Azure HA features. HA functionality provides ways to avoid downtime caused by the failure of a single node within a datacenter. DR features protect against outages that affect an entire datacenter broadly. When you plan support requirements and procedures, consider what happens if the disaster is severe enough to force the primary production site to switch over to the secondary site and you need DR features. In these extreme cases, you'll have downtime for production access while you set up access to the secondary site, and your team is responsible for several actions. For more information about business continuity with HA and DR, see the [service description for Dynamics 365 finance and operations apps](https://aka.ms/D365-Cloud-Service-Operations) and [business continuity and disaster recovery](/dynamics365/fin-ops-core/dev-itpro/sysadmin/business-continuity-disaster-recovery).

If your production system is running on the secondary site while the primary site is being repaired, you might have restrictions, such as not being able to deploy packages, or limitations, such as reduced performance, that your support team needs to know about and help reduce their impact on the business. You might also need to apply specific setups such as IP allowlists to the secondary site.

In summary, you should have a business continuity plan that includes how your support team should plan, do, and communicate during a service outage, including during a severe disaster.

### Customer engagement apps

For customer engagement apps, HA provides mechanisms that can reroute requests when failures and planned downtime happen. On the database side, the Recovery Time Objective (RTO) for failover is based on the timings from Azure SQL Database. With diverse storage, the scheme extends to other storage components.

For DR, Power Platform lets you fail over and fail back in seconds. No data is lost in planned DR failovers. In unplanned DR, the administrators of the Dynamics 365 datacenter apply well-defined processes to recover from a service interruption, but your support team needs to help with any potential data loss.

## System updates

Dynamics 365 app updates are one of the changes that your support team might need to manage. When you define the scope of responsibilities for your support team, you must understand what system updates involve and how to plan for them.

Creating a calendar for Microsoft updates helps your support team prepare for the resources and effort that they need for Dynamics 365 updates, independent software vendor (ISV) updates, updates for custom code, and testing, including regression testing and release management.

As we saw in the previous section, your solution might change often because of new and backlog requirements. [Learn more about how Microsoft system updates affect your solution](service-solution.md).

## Next steps

- Understand key aspects when choosing [support models](transition-to-support-models.md)
- Discover the requirements for [support operations](transition-to-support-operations.md)
- Understand the roles and responsibilities of the [support team](transition-to-support-team.md)
- Review a [checklist](transition-to-support-checklist.md) for implementing your support model
- Read the [case study](service-solution-case-study.md) to understand why you need to develop and audit your support strategy in the cloud world
