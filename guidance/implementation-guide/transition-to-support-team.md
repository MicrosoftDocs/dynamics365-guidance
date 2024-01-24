---
title: Set up a technical support team for your Dynamics 365 implementation projects
description: This article is covers guidance for how to set up the team that handles technical support for your Dynamics 365 implementation.
author: taksatoms
ms.author: tsato
ms.date: 04/12/2023
ms.topic: conceptual
---

# Set up a technical support team for your Dynamics 365 implementation projects

During the *Implement* phase, you identify the [support model](transition-to-support-models.md) that your Dynamics 365 implementation project will use. Multiple operating models exist, and within each model a spectrum of sub-options. Therefore, the specific organization structure is influenced by the variant of the model that is chosen. In this section, we explore some common patterns for roles and structures.

## Support team responsibilities

Any organization looking to support a business application system of a reasonably-sized footprint needs to make sure that they have the necessary skills and resources, not just across the business process areas and technical topics, but also to manage data quality, maintain and improve user proficiency in the system, and help the organization remain compliant with processes and procedures.

Each of these areas needs to be defined in more detail to ensure the planning for the support model is sufficient.

### Support for business process areas

Support for business processes is usually defined by the main workstreams and includes the following responsibilities:

- Liaising with process owners on the overall health of the process

- Keeping up to date with the current business priorities in this area

- Gaining and maintaining a deep understanding of the steps and relative criticality of the various functions within a business process

- Gaining and maintaining a deep understanding of how the Dynamics 365 application and related systems deliver this process, so they can provide how-to advice and analyze potential problems

- Analyzing, triaging, and recording potential issues

- Communicating with the originator of an issue throughout its lifecycle to maintain user satisfaction, promote business awareness, and manage expectations

- Curating issues through multiple resolving authorities until resolution within agreed SLAs

- Liaising with internal and third-party resolving authorities (such as any partner organizations, ISVs, or Microsoft)

- Monitoring the lifecycle of a defect resolution from registering to promoting a fix

### Support for technical areas

Support for technical areas is usually defined by the following categories:

- Service operations (database copies, new environment creation, managing system downtime windows, maintaining Dynamics 365 system quality update calendar, etc.)

- System operations via services (integrations, batch processes, reporting, business intelligence, etc.)

- System maintenance and monitoring (system health monitoring, security role maintenance, security certificate rotations, periodic system cleanup of log files etc)

- Dynamics 365 application management related to break or fix errors reported by users

- Dynamics 365 application management such as updating system administration parameters

- Dynamics 365 application system update management (code branching, any software development, unit testing new changes, etc.)

Responsibilities may also overlap with those for business process support, with the following distinctions for the expected areas of understanding:

- Gaining and maintaining a sufficient understanding of the relative criticality of the various functions within a business process

- Gaining and maintaining a deep understanding of the underlying technical processes involved in the system functions (especially integrations, custom code, and critical processes)

### Support for data quality maintenance

In many organizations, some of the business data maintenance responsibilities are passed to the support team by the business data stewards or owners. This type of support includes the following areas:

- Core business data and configuration in the system as well as IT and system administration parameters

- Liaising with business data stewards to determine priorities and actions

- Periodic audits and reports to confirm the data quality

### Support for user proficiency in the system

In some organizations, the functional experts within the support team act as a default team to provide user training both formally and on an ad-hoc basis. This level of support includes the following:

- Monitoring user proficiency within the system by reviewing the number of how-to queries and issues created by not following the agreed business process in the system

- Creating training content and conducting formal end-to-end training of new users

- Creating training content and conducting informal specific functional training of users on request or as needed

- Conducting change management activities to help improve user adoption

### New features and developments

In addition to managing the day-to-day and periodic maintenance tasks and addressing queries and issues in the preceding areas, the support team may also be expected to keep track of new features and developments (positive and otherwise) that may impact the system.

Often, the planning for the break/fix part of a support team's organization is well thought through, but the planning for other areas of responsibility may be neglected. For example, many support team members may also need to be involved in helping with the lifecycle of the next system update. This may include the following duties:

- Helping with assessing the impact of proposed changes on the current system

- Providing insights into areas that need reinforcement based on statistical analysis of the areas with the most issues

- Testing the changes

- Updating documentation to reflect process and system changes

- Training in any new processes

- Sending communications of the system update

- Managing the next release through the development, test, and production environments

- Refreshing the support environments with the latest production environment

Dynamics 365 business applications are cloud-based SaaS applications, so Microsoft handles a lot of the traditional effort (for on-premises systems) of managing all the layers of the production infrastructure hardware, operating system, and application software, and much of the monitoring of the underlying system health.

The duties and responsibilities outlined in this section aren't meant to be exhaustive, but rather prompt you to make sure you have sufficient definition of the coverage, skills, and effort needed to maintain and support a business application. Later in this article, we discuss the special considerations in the transition period and in the early days of a new system implementation (sometimes called hypercare).

This section concentrated on the tasks and activities that your support organization may need to cover. For details on operational considerations, see [Service the solution](service-solution.md).  

## Support organization structures and roles

When considering the support organization, each business should consider the level of effort that is implied by the range of duties expected as part of support and determine how to distribute the various responsibilities.

The following is a typical set of roles (depending on the size and complexity of the implementation, sometimes multiple roles may be filled by a single individual):

- **Business super user(s)**  

  As we discussed earlier, super users serve as first-line support with some form of part-time role. The level of formal recognition of the role varies from customer to customer.

- **Business process expert(s)**  

  Also called SMEs or functional leads, these experts in the support team usually have a full-time or near-full-time role. A lead (technical architect) usually has oversight on the full solution architecture across all the business process workstreams.

- **Technical architect**  

  Also called system architect or solution architect, this role within the support team ensures the enterprise and Dynamics 365 technical standards are met. They have oversight across all the technical tasks and duties mentioned earlier in this article. The technical experts, developer, and release manager roles often report to the technical architect.

- **Technical expert(s)**  

  This role has expertise in the technical servicing and support duties that we discussed earlier.

- **Developer(s)** This role is responsible for bug fixes to custom code and writing code for new custom functionality.

- **Release manager**  

  This role is responsible for confirming that a release has been appropriately validated for release to production. They're also often responsible for other servicing and support tasks.

- **Support manager**  

  This manager is accountable for the support services for Dynamics 365 applications (and often other related systems).

- **Business and IT stakeholders**  

  You should consider these roles significant because their sponsorship, direction, prioritization, and decisions are key parts of establishing the right support organization, defining fit-for-purpose processes for support, and meeting business expectations.

Depending on the support model chosen (fully internal, fully external, or a mix) and regardless of the organization responsible, you will likely need these roles.

Organizations that are implementing across multiple business units or companies with an incremental rollout plan should consider setting up a Dynamics 365 CoE. This allows the organization to bring together specialist knowledge and make it available across different business, where each individual business or implementation may not have been able to justify it. This model gives economies of scale on constrained and specialist resources, and helps disseminate good practice across implementations. In a CoE model, you may have permanent internal roles or create sub-roles that have deep specialist knowledge in business and IT processes. Because the Dynamics 365 CoE can employ its own specialists, it can also help manage other specialist third-party organizations providing support and service.

:::image type="content" source="media/transition-to-support-structures.png" alt-text="Support structures and roles" :::

A common approach is to outsource some of the Dynamics 365 application functional and technical support to a Dynamics 365 partner. This is especially true if the application has a lot of customizations that were developed by that partner. In these circumstances, the customer may still elect to keep a small internal support team of a technical architect, developer, and release manager to help manage the outsourced services and maintain final control over the quality of the changes to the production system.

The size and nature of the support organization should be determined by analyzing the scope of the requirements for the support organization (as discussed earlier in this article) as well as the size, complexity, functional spread, and geographical (time zone, language, local data regulations) distribution of the implementation.

Standard Dynamics 365 platform and application support and servicing for production environments is also available.

:::image type="content" source="media/transition-to-support-ms-support.png" alt-text="Microsoft Support" :::

Microsoft offers [different levels of support for your Dynamics 365 products](/dynamics365/get-started/support/). Refer to the article [Service the solution](service-solution.md) for more details.

## Budgets, contracts, and agreements

When a new system is introduced into an existing enterprise architecture, some changes can impact related systems, such as the changes required to budgets and support agreements. A common issue that can occur is that the budgets and agreements aren't modified to reflect the new system environment and processes. This can cause delays when addressing issues that may span departments, or if the resolving authorities or third parties have their own budgets based on previous processes and agreements.

After you have a reasonable draft of the new system solution blueprint, to-be enterprise architecture, and support organization, you should start defining the budgets related to the new tasks and areas of responsibility.

Consider the full set of tasks and activities in scope for the support organization (as discussed earlier) and map these to the various roles and resolving authorities over the full lifecycle of a support job or request so that no gaps appear in the flow. You can use this to make sure that the specific responsibilities of all the roles and resolving authorities can be mapped to agreements and service-level expectations.

For internal parties, this may mean defining budget and resource splits and less formal service delivery agreements. For third parties, that may mean formal contracts with formal SLAs. Mismatched expectations between the customer and a third-party support provider in the middle of dealing with high-priority issues are not uncommon. A contract created based on a deeper understanding of the expected tasks and service expectations is much more likely to avoid misaligned expectations and provide a faster path through the process.

## Next steps

- Review how to construct a strategy to help you prepare, define, and operate a support model in the section [overview](transition-to-support.md)
- Learn about the importance of defining the [support scope](transition-to-support-scope.md)
- Uncover the requirements related to [support operations](transition-to-support-operations.md)
- Review the [checklist](transition-to-support-checklist.md) to help with implementing your support model
- Read the [case study](service-solution-case-study.md) to understand the need to develop and continually audit an organization's support strategy in the cloud world