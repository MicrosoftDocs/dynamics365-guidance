---
title:  Transition to support - support scope
description: This article is illustrates the importance of defining the support scope and the different aspects involved in a support model in Dynamics 365 implementation projects.
author: taksatoms
ms.author: tsato
ms.date: 03/30/2023
ms.topic: conceptual
---

# Support scope

Support scope activities should be started in the Initiate phase. It may be tempting to defer defining the scope until much later in the project because it's not seen as urgent compared to getting the project off the ground and creating the system solution. However, as this article discusses, early attention to this topic enables the support team to become engaged in the project from an early stage, which pays dividends during the project lifecycle.

## Enterprise architecture

In most organizations, the Dynamics 365 system is embedded within the wider enterprise system landscape. The Dynamics 365 application has connections to multiple systems and to underlying and coexisting technologies. When considering the strategy for defining the support model, the focus is often solely on the Dynamics 365 application architecture. It's worth accounting for the changes, constraints, procedures, and influences from the surrounding architecture on the Dynamics 365 applications, and vice versa; how will the enterprise architecture and environment be impacted by installing and operating the Dynamics 365 application?

Firstly, from the enterprise system architecture documents, confirm that you have identified all the various systems, software, and data that interact with Dynamics 365 applications. You should make a distinction between new systems being introduced into the enterprise architecture and those that may be influenced by the new systems.

During the project, the new Dynamics 365 system will probably be implemented within a special sandbox (test environment) and not necessarily be subject to all the influences and rules that the production system is subject to. This also applies to the third-party test systems that are part of the middleware or integrations. For example, production environments have more limited access to the Dynamics SQL database, and the process by which custom code is promoted to production or how the Microsoft system updates are applied isn't the same. You should specifically examine the implications of the production system environment on support operations and not rely solely on the experiences of the test environment.

Identify the specific, new, or changed support requirements impacted by the following:

- Enterprise-level architecture configurations in areas such as Microsoft Azure, operating systems, any existing Microsoft 365 tenants, Azure storage, and Azure Active Directory

- Dynamics 365 Azure environments managed by Microsoft (for example, the Dynamics 365 production environment)

- Identity and access management systems, such as operating systems, browsers, mobile devices, and firewall configurations

- If this is the first significant cloud, software as a service (SaaS) system in the enterprise, the related system architecture, and servicing needs

- Systems to which the Dynamics 365 application interfaces directly

- Middleware systems to which the Dynamics 365 application may connect

- Any systems that will be decommissioned but have residual tasks that may need to be reabsorbed elsewhere by the support team

- Any document management systems such as Microsoft SharePoint or third-party systems

- Any code configuration management systems such as Azure DevOps or third-party systems

- Reporting systems to which the Dynamics 365 application interfaces, including Azure Data Lake or data warehouse

The impact of, and on, the surrounding architecture can be difficult for the customer project team working on the Dynamics 365 business application to fully identify. In almost all cases, you need the enterprise architects from IT and the business to be involved in identifying the changes. Some changes may also impact the roles of individuals formally part of a support organization and those in peripheral organizations.

## Business and IT policies

All organizations need to think about how new systems will operate within the wider organization's policies and standards. When Dynamics 365 is introduced into the enterprise, it needs to follow the applicable policies already in place and may require new operating policies. In either case, you need to review the existing policies and standards to determine which policies to add, which to review and revise, and which to apply to the support model.

:::image type="content" source="media/transition-to-support-scope.png" alt-text="Support policies" :::

In many cases, the policies apply not only to the creation of the support model and its scope of responsibility, but also to how it operates as an organization and how it addresses the lifecycle of a support request.

### Group and company policies and standards

When evaluating group-level policies or standards, you may have to review the impact of business policies and procedures on various levels:

- **Contracting with and managing third-party vendors** The support model needs to include some type of contract with technology partners and with Microsoft

- **Operating hours** Current and future operating hours for the business can directly impact the working hours for support

- **Financial period end and seasonal deadlines** This may impact the level of service expected at times when the business has critical business activities

- **IT policies on change control on enterprise IT assets** This may impact the access and approval chain for changes required for the Dynamics 365 application troubleshooting or servicing (for example, creating new Azure virtual machines, copying databases between environments, and building IP allowlists)

The overall support model on Dynamics 365 business applications operates across many of the company's business processes and is therefore shaped by the relevant business policies.

### Dynamics 365 application-level policies

Some policies are managed in the system by the business administrators, and some may be delegated to the support team. Even if the administration of a policy is the responsibility of the business leads, the monitoring and auditing of the business process is often the support team's responsibility.

You could set up some of these policies within the Dynamics 365 application, such as new vendor approval policies, customer credit limits, purchase order approval thresholds, and travel and expense policies. The support team may need to help provide information on compliance or enforce compliance as part of their duties.

### Dynamics 365 application-level security and access management

Administration and review of application-level security is usually an area of responsibility of the support team. The support team needs to prepare by gaining an understanding of the Dynamics 365 role-based application security model and the related access policies.

### Group and company-level security and access management

In addition to the security and access policies and procedures that you need to define for Dynamics 365 applications, you may have to consider enterprise-level security policies that intersect with the application-level security requirements.

In larger organizations, enterprise-level security and access management may be handled by a separate IT organization or a separate IT team. Some of the support team members will need elevated access not just at the application level, but possibly for other systems within the enterprise.

The Dynamics 365 support team needs to work with these other enterprise IT and business teams to define the rules and procedures for managing some of the security topics that may impact Dynamics 365 applications:

- Azure Active Directory groups and identities

- Single sign-on (SSO)

- Multifactor authentication

- Mobile device authentication and management

- Authentication and management for custom applications working on Microsoft Dataverse (such as Power Platform apps), which requires an understanding of [Dataverse security concepts](/power-platform/admin/wp-security-cds)

- Application access for third parties (such as vendors and customers)

- Application access for third-party partner support organizations (such as technology partners and Microsoft)

- Service account and administrator account use and management

- Password renewals and security certificate rotations

- Secure and encrypted communications within the enterprise and outside the enterprise (such as those involved with integrations with internal systems, or with external web services or banking systems)

The [Microsoft Trust Center](https://www.microsoft.com/trust-center) can help your organization consider [overall security](https://www.microsoft.com/security) and [managing compliance](https://www.microsoft.com/trust-center/compliance/compliance-overview) in the cloud. Learn more at [Security Strategy](security.md).

### Data classification and retention

Consider how the organization's data classification and retention policies reflect on and need to be expanded to include the new Dynamics 365 application:

- How is the support team expected to enable and enforce these policies?

- What is the impact on the backup, restore, and archive process?

- What is the impact on creating and managing database copies?

- Do any data classification properties flow between systems, or do they need to be recreated or audited by the support team?

### Regulatory compliance and policies

In addition to any data retention policies, the organization's businesses may be subject to national and supranational regulations. Some may impact business processes that are expected to be assisted by the support team (such as e-invoicing and digital tax).

The support team may be expected to support, monitor, and audit other regulations on a regular or ad-hoc basis, such as General Data Protection Regulation (GDPR) or Health Insurance Portability and Accountability Act (HIPAA).

All of these different areas of business and IT policies shape the nature, size, and scope of the support organization. Early examination of these factors will help the team be effective from the start.

## Dynamics 365-specific considerations

In this section, we examine some topics specific to Dynamics 365 business applications that we should consider when designing the support model. These can be broadly grouped by operational and maintenance topics and business process topics.

### Operational and maintenance topics

We can further divide operational and maintenance areas into the management and support of the following:

- Dynamics 365 environments

- Integrations

- System and data maintenance

- Performance

### Dynamics 365 environments

When Dynamics 365 is in production, various aspects involved in supporting the system environments need to be factored into the support model preparation:

- Maintenance and operational tasks (both scheduled and ad hoc) such as environment data refresh, database movements between environments, configuration moves, and code promotion

- Support organization roles and resources needed

- Skills required to support the environments

- Resulting budget impact

Typically, you need to apply these tasks and considerations for the following environments:

- Dynamics 365 application support environments, which are recent copies of the production system

- Test environment for testing the next versions of the application software

- Development environments

- Any related data migration, training, or integration environments

- Test environments for integrated systems

This is not an exhaustive list of environments, but should help prompt the right discussions related to supporting the environments. Learn more at [Environment strategy](environment-strategy-overview.md).  

### Integrations

In addition to defining the environments required for supported operations, it's worth delving a little deeper into the support requirements specific to managing integrations. When defining the support requirements for all the integrations, consider what areas are in scope for the support organization:

- Data management at either ends of the integration

- Security of the integration services

- Performance of the integration

- Auditing or monitoring of the integration

- General troubleshooting analysis and stopping and starting of integration services

The level of skill and effort required to manage integrations depends on their complexity, criticality, and robustness. Designs of custom integrations that are tolerant of variations of data distribution and variations in volumes, are resilient to errors, and have automated self-healing mechanisms will require less support.

### System maintenance requirements

As part of the definition of the system, the definition of maintainability requirements is an area that doesn't always get the attention it deserves. This can manifest itself in unplanned activity for the support organization. So, during the Initiate phase of the project, the current support organization should look to derive the specific maintenance requirements for managing the new Dynamics 365 implementation.

Because Dynamics 365 applications are cloud and SaaS-based, many maintenance tasks and responsibilities that are common to on-premises solutions are now managed by Microsoft. In general, the burden of infrastructure provision and maintenance for production systems is reduced, which leaves more time to focus on managing and improving business process performance.

Define the system maintenance requirements and what is within the scope of responsibilities for the support teams. Typically, these are in the following areas:

- Servicing the non-production environments, which can include:

  - Requesting and configuring new Dynamics 365 environments

  - Requesting and configuring database copies and restores between environments

  - Managing any customer-managed, cloud-hosted environments

  - Performing specifically requested backups

- Managing system operations, which can include:

  - Assigning users to security roles

  - Reviewing and running periodic system cleanup jobs

  - Managing system administration messages and notifications

  - Batch calendar management

  - System update calendar

### Data maintenance requirements

Data maintenance is a significant part of operating a business system, and it's essential that the scope of data management is clearly defined for the support team. Much of the data maintenance will be the responsibility of data stewards from the operating business, but the support team may be expected to manage some critical areas.

Typically, in a Dynamics 365 application, a support team may be managing system administrator data, some types of primary data, security and access data, data related to periodic processes, and so on; for example, assigning a user to a security role, or adding or revising a new customer attribute.

### Performance management

Performance management for a Dynamics 365 business application is a mix of tasks and responsibilities for Microsoft and for the customer. In this section, we consider the implications on the support model.

The support team needs to have some way to proactively monitor and respond to any questions from the users on performance. Therefore, the support team needs to be able to do the following:

- Understand the impact of the reported performance issue on the business

- Assign the relevant priority

- Diagnose the issue across the potential root causes from configuration, data, custom code, independent software vendor (ISV) code, standard code, and so on to determine the root cause, or to hand it off to a specialist team (internal or external) with a meaningful starting point

- Reproduce the steps and circumstances to demonstrate the performance issue (and have the necessary resources to do so)

- Communicate the problem to other more technical specialists and work with them to resolve the issue

To better detect processes beginning to show poor performance, it's important to have a baseline definition of required performance for critical processes, expressed as performance goals. Having actionable performance goals enables more focused monitoring and proactive actions to identify and quickly stop any decline in performance.

Because performance troubleshooting is a specialist skill, the internal support team may not have all the skills and experience to examine and correct the performance of custom development. It's also a skill that may only be needed sporadically, so you may need to consider planning for access to external teams that can use specialist performance tools, interpret the results, and decide on corrective actions.

## Business processes

As a business application, supporting the users in the day-to-day processes is a key function of a Dynamics 365 support organization. The support organization is expected to provide coverage across all the key business process, or at a minimum, know where to direct questions and issues that were agreed as being outside their support scope.

Based on the definition of the key business processes in scope, consider the following for each process:

- What is the level of expertise needed in the business process?

- What are the likely support tasks and queries related to this process?

- What is the type of usage, frequency, and volume?

- How critical is this business process to the business outcomes, and what degree of priority do the support issues need?

- What is the type and level of skills needed to support this process?

- What processes require resources aggregated at a department, workstream, or value chain level?

- What are the interactions with other systems and communication protocols required?

- Does this process require the support personnel to have specialist security or compliance training or certification?

- Do any special requirements need support services outside of the anticipated support hours (outside of business hours or during holiday periods)?

An important factor when determining resources and escalation procedures is the level of ownership and responsibility that the business process leaders are expected to take from their own organization to support the day-to-day operations for their processes.

These questions and more will help shape the operating model for the support team.

## Business continuity

Many organizations need to have a business continuity strategy and exercise regular checks of business continuity in case of a service outage. This may be required by external regulations or by internal policies. In any case, the support organization is probably expected to play a major role.

Depending on the size and complexity of the system landscape and the types of service outage scenarios being exercised, this may need a significant amount of preparation, coordination, and timely communication between multiple parties.

As part of preparing for the establishment of the support organization, you should consider the definition of the business continuity strategy and what resources, skills, and tooling are required.

As a cloud-based SaaS service, Microsoft provides the production infrastructure, platform, and application-level business continuity services. For Dynamics 365 Finance and Dynamics 365 Supply Chain Management applications, the operations as listed in the [Service description for finance and operations apps](https://aka.ms/D365-Cloud-Service-Operations) provide details of the services and service-level agreements (SLAs) from Microsoft and the expected responsibilities and actions from the customer. You should bear this in mind when you build your business continuity planning, which should reflect your specific systems landscape and scenarios.

Of course, the Dynamics 365 business application may not be an isolated system, it may be connected to other enterprise systems, and your business continuity planning will need to consider your entire enterprise architecture when defining your strategy and the related support requirements.

### Dynamics 365 Finance and Supply Chain Management

Dynamics 365 Finance and Supply Chain Management applications have specific [high availability (HA) and disaster recovery (DR)](/dynamics365/fin-ops-core/dev-itpro/deployment/cloud-deployment-overview#availability) features for cloud deployment. To ensure service availability, all production environments are protected by using default Azure HA features. HA functionality provides ways to avoid downtime caused by the failure of a single node within a datacenter, and DR features protect against outages broadly impacting an entire datacenter. When planning support requirements and procedures, consider the implications if the disaster is severe enough for the primary production site to be forced to switch over to the secondary site and the DR features are warranted. In such extreme cases, you would experience downtime for production access while access to the secondary site is being established, and the customer team is responsible for several actions. For more information about business continuity with HA and DR, see the [Service description for Dynamics 365 finance and operations apps](https://aka.ms/D365-Cloud-Service-Operations) and [Business continuity and disaster recovery](/dynamics365/fin-ops-core/dev-itpro/sysadmin/business-continuity-disaster-recovery)

If the production system is running on the secondary site (while the primary site is being repaired), you may have restrictions (such as the inability to perform package deployments) and limitations (such as performance reduction) that the support team needs to be aware of and help mitigate to reduce the impact on the business. You may also need to apply specific setups (such as IP allowlists) to the secondary site.

In summary, you should have a business continuity plan that includes how the support team should plan, perform, and communicate during a service outage, including during a severe disaster.

### Dynamics 365 customer engagement apps

For Dynamics 365 customer engagement apps, HA provides mechanisms that can reroute requests in case of failures, planned downtime (patching and updates), and more. On the database side (relational storage), the Recovery Time Objective (RTO) for failover is dictated by the timings from Azure SQL Database. With diverse storage, the scheme extends to other storage components. For DR, Power Platform brings the ability to fail over and fail back in seconds. You can do this at the granularity of an organization (environment). There is no data loss in the case of planned DR failovers. In the extreme circumstances of an unplanned DR, well-defined processes are applied by the administrators of the Dynamics 365 (online) datacenter to recover from a service interruption; however, the support team needs to help with any potential data loss.

## System update cycles

Microsoft Dynamics 365 application updates are one of the changes that the support team probably needs to manage. From the perspective of defining the scope of responsibilities for the support organization, you must understand what is involved and plan for the updates.

Creating a calendar for the Microsoft updates helps the support team plan for the resources and effort associated with the following:

- Microsoft Dynamics 365 updates

- ISV updates

- Updates for custom code

- Associated testing, including any regression testing and release management

We saw in the previous section that the solution is unlikely to remain static for long, and the solution functionality can change because of new and backlog requirements. For details on Microsoft system updates, refer to the article [Service the solution](service-solution.md).

## Next steps

- Review how to construct a strategy to help you prepare, define, and operate a support model in the section [overview](transition-to-support.md)
- Understand key aspects when deciding on [support models](transition-to-support-models.md)
- Uncover the requirements related to [support operations](transition-to-support-operations.md)
- Review the [checklist](transition-to-support-checklist.md) to help with implementing your support model
- Read the [case study](service-solution-case-study.md) to understand the need to develop and continually audit an organization's support strategy in the cloud world  
