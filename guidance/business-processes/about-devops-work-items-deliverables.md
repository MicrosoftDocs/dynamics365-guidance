---
title: Dynamics 365 Deliverables Tree and Work Item Types
description: Understand how the Deliverables tree in Azure DevOps supports scaled agile planning, traceability, and streamlined reporting for ERP and CRM projects.
#customer intent: As a functional consultant, I want to learn how to configure out-of-the-box deliverables in Azure DevOps so that I can tailor Dynamics 365 to meet specific business needs.
author: edupont04
ms.author: edupont
ms.date: 01/13/2026
ms.topic: concept-article
---

# Deliverables in the business process catalog as Azure DevOps work items

This article describes how to use the business process catalog to create work items in Azure DevOps for concrete deliverables in an implementation project with Dynamics 365 apps. You can then assign the work items to team-specific Boards. We also describe the custom work item types included in the default template which you can use to help effectively manage a Dynamics 365 project by using Azure DevOps. The Azure DevOps template is designed to follow [the Success by Design framework](../implementation-guide/success-by-design.md) with a process-focused approach.

## Introduction

The *Deliverables* tree in Azure DevOps is a structured hierarchy designed to organize implementation work across multiple teams by using interconnected Boards. This approach transforms traditional flat lists of deliverables into a dynamic tree that mirrors the logical flow of a Dynamics 365 project. Each branch of the tree represents areas of an organization and typical separation of work for a Dynamics 365 project. For example, Finance, Human Resources, Information Technology, Operations, and Sales. Each functional area is then further broken down to sub areas to make the catalog and data easier to navigate. These areas are represented by Area paths in the Azure DevOps template.

Each branch has work item types that represent a category of work, such as [configuration](#configuration-work-item-type), [migration](#migration-work-item-type), or [testing](#testing-work-item-type). By mapping these deliverables to team-specific Boards, organizations gain clear visibility into ownership, dependencies, and progress across functional areas. This structure not only supports scaled agile planning but also ensures consistency in naming conventions, field groups, and governance across environments. Ultimately, the Deliverables tree enables collaborative execution, traceability from requirements to outcomes, and streamlined reporting for complex ERP implementations while still supporting smaller simple CRM projects.

Deliverables represent the concrete work and tasks that consultants must execute as part of a Dynamics 365 project. They serve as actionable items that drive project progress. The catalog offers thousands of predefined deliverables that you can filter based on the scope of the business process. Teams are encouraged to create custom work items throughout the project to address unique or evolving requirements.

The following sections outline each of the work items types included in the template with recommendations for how each should be used. After you add the work item types to the relevant Azure DevOps project, you can create new work items based on the different types of deliverables. The Excel workbook that we provided as part of the download of the December 2025 version of the business process catalog, *Deliverables (What) Tree DEC 2025.xlsx*, is a template that you can import, and it includes concrete work items. To manually create a work item based on these work item types, fill in the required fields.

> [!TIP]
> Find short descriptions of the fields that we recommend you use on the different work item types at [Fields for Azure DevOps work items from the business process catalog template](about-devops-work-items-deliverables-fields.md).

## Requirement work item type

Requirements define the functional and non-functional needs that Dynamics 365 must fulfill. They serve as the foundation for solution design and traceability throughout the implementation lifecycle. In a Dynamics 365 project, requirements help align business objectives with system capabilities and ensure that gaps are identified early.

The business process catalog doesn't include requirements by default because they represent a higher-level definition of business needs rather than a specific deliverable. Use the Requirement work item type as a triage mechanism to capture and organize the initial business need. Then, link it to other deliverable types such as configurations, workflows, reports, or integrations that fulfill that requirement. To maintain clarity and traceability, always associate requirements with the lowest-level business process possible. This association ensures that each requirement is contextually tied to a specific process step, making it easier to identify dependencies and validate coverage during design and testing. This approach supports Success by Design principles for structured planning and governance.

> [!NOTE]
> Some industries and regions have regulatory compliance rules that define how requirements are tracked and the level of detail that is required for the organization. Consider these industry and regulatory compliance requirements carefully and follow their approach to documenting requirements in favor of any guidance provided here.

### Examples of requirements

- The system supports multicurrency invoicing for global operations.

- Enable automated tax calculation for multiple jurisdictions.

- The system allows sales reps to create quotes directly from opportunities.

- Enable case routing based on customer priority and SLA.

- Technicians can capture customer signatures on mobile devices.

- The system processes 1,000 sales orders per minute during peak load without errors.

- Case routing occurs within 2 seconds of case creation for high-priority customers.

- The mobile app syncs work orders within 30 seconds after connectivity is restored.

- The system maintains 99.9% uptime during business hours.

- Encrypt all customer data at rest and in transit by using AES-256.

- The application supports accessibility standards (WCAG 2.1) for visually impaired users.

- Response time for dashboards doesn't exceed 3 seconds for datasets under 10,000 records.

### Success by Design guidelines for requirements

- Use the Requirement work item type as a triage mechanism to capture business needs and link them to deliverables such as configurations, workflows, reports, or integrations.

- Always associate requirements with the lowest-level business process possible to ensure contextual relevance and traceability.

- Include clear acceptance criteria and prioritize requirements based on business value and risk.

- Maintain relationships between requirements and related work items in Azure DevOps for end-to-end visibility.

- Validate requirements during Fit/Gap workshops and ensure alignment with Success by Design phases (Envision, Design, Build).

- Document dependencies and assumptions to support governance and change management.

## Workflow work item type

Workflows represent automated or manual process flows that can span Dynamics 365 apps, Power Automate flows, or Agent flows that connect processes across systems. These workflows streamline business operations by defining triggers, conditions, and actions that ensure consistency and compliance. In the business process catalog, include out-of-the-box workflows for all finance and operations workflows, and plan to add standard business process flows for customer engagement apps in a future release. You can also document Power Automate flows as deliverables when they're part of the solution design.

For each workflow, business process flow, Power Automate flow, or Agent flow, create a single work item that's directly related to the business process the flow supports. This approach ensures clear alignment between the process and its automation, making it easier to manage dependencies and traceability. If there are multiple configurations of the same workflow in Dynamics 365, such as two distinct approval workflows for purchase orders, duplicate the work item and name each according to its specific configuration. You can document the requirements and configuration details for each variation. This approach helps you manage associated testing, migration, and governance activities effectively.

Document Agent flows, which automate tasks by using Copilot, as individual work items. For example, an Agent flow that automatically responds to customer inquiries about order status in Dynamics 365 Customer Service should have its own work item linked to the order management business process. This approach ensures visibility into AI-driven automation and supports testing and compliance requirements.

### Examples of workflows

- Purchase Order Approval Workflow

- Leads Business Process Flow

- Automated case escalation using Power Automate

### Success by Design guidelines for workflows

- Use the built-in workflows and business process flows as much as possible to minimize customization and reduce upgrade risk.

- Keep naming standards by using the workflow name from the relevant Dynamics 365 app for work item titles.

- For Power Automate and Agent flows:

  - Document triggers, connectors, and governance policies.

  - Include AI-driven automation details such as intent, scope, and fallback actions.

  - Validate compliance with data privacy and security standards.

- Link each flow to the lowest-level business process for traceability.

- Capture dependencies and testing requirements for all automation types, including Agent flows.

- Ensure workflows and flows align with performance, compliance, and accessibility requirements before deployment.

## Report work item type

Reports and inquiries provide visibility into business data to support decision-making, compliance, and operational efficiency. They can take multiple forms, including:

- **Operational reports:** Real-time transactional insights for daily operations, such as open orders and pending invoices.

- **Analytical reports:** Trend analysis and predictive dashboards for strategic planning, such as sales pipeline and inventory aging.

- **Regulatory reports:** Compliance-driven outputs for audits and statutory filings, such as tax filings and audit trails.

- **Ad-hoc inquiries:** Flexible, on-demand queries for specific data points.

- **Live dashboards:** Interactive, real-time visualizations aggregating key performance indicators (KPIs) for quick insights, such as Power BI dashboards.

- **Copilot summaries:** AI-generated narratives that interpret data trends and suggest actions.

Currently, the business process catalog doesn't include any reports. However, future releases will expand the catalog to include standard reports and dashboards that align with common business processes. By providing predefined reporting templates and governance guidelines, you can accelerate implementations.

For standard out-of-the-box (OOB) reports, create a single work item to indicate that the report is in scope and meets the business requirements. Use this work item as a central artifact to link related deliverables such as testing, security, documentation, user training, and any required configuration activities. For custom reports or any report customization, create a dedicated work item to document both the functional and technical design of the report. This approach ensures traceability, supports governance, and provides a clear reference for testing, migration, and future enhancements.

### Examples of reports

- Monthly financial summary report for CFO dashboard.

- Inventory aging report for warehouse management.

- Pipeline report showing opportunities by stage and probability.

- Case resolution time report segmented by agent and queue.

- Technician productivity report with completed work orders per day.

### Success by Design guidelines for reports

- Define KPIs and data sources upfront.

- Ensure security roles for report access.

- Validate reports against regulatory requirements and business needs.

## Integration work item type

Integrations connect Dynamics 365 applications with external systems or services to enable seamless data exchange and process automation. They're critical for maintaining data consistency across enterprise applications and supporting end-to-end business processes. Integrations can include real-time APIs, batch interfaces, middleware-based connections, or low-code solutions such as Power Automate.

Currently, the business process catalog includes **Dual Write maps as standard integrations**, but it doesn't include any other integrations out of the box.

Create **one work item for each interface** to align with the Success by Design approach. This approach ensures traceability and provides a single artifact for linking related deliverables such as testing, security, and migration activities. Each integration work item should capture the technical and functional details required for the **Solution Blueprint review**, including interface model, technology, and performance considerations. This practice supports governance, accelerates design reviews, and simplifies change management.

### Examples of integrations

- Integrate Dynamics 365 SCM with SAP for inventory sync.

- Connect CRM with marketing automation platform.

- Integrate Dynamics 365 Sales with LinkedIn Sales Navigator for lead enrichment.

- Connect Customer Service with Power Virtual Agents for chatbot escalation.

- Integrate IoT sensors with Field Service to trigger work orders automatically.

### Success by Design guidelines for integrations

- Document endpoints, authentication, and data mapping.

- Include retry and error-handling strategies.

- Validate performance under peak loads and ensure security compliance.

## Configuration work item type

Configurations represent system setups that enable processes without custom development. They include parameters, number sequences, feature management keys, and other settings that tailor Dynamics 365 applications to meet business requirements.

The business process catalog includes hundreds of out-of-the-box configurations that cover all Dynamics 365 apps. Each release regularly updates these configurations to reflect new features. If you identify missing configurations, report them as a GitHub issue at [https://aka.ms/businessprocesscatalogrequests](https://aka.ms/businessprocesscatalogrequests).

Use the following guidance for the configuration work item type in the Azure DevOps template.

- For **standard out-of-the-box configurations**, the catalog provides one work item for each setup, parameter, or number sequence in Dynamics 365 finance and operations apps and customer engagement apps.

- For **customizations that require configuration**, create a dedicated work item to document the functional and technical details.

- If a configuration is implemented differently across legal entities, business units, or geographies, **duplicate the work item** and name each copy to reflect its context (for example, include legal entity, department, or region in the title).

This approach ensures traceability, supports governance, and provides a clear reference for testing, migration, and cutover activities.

### Examples of configurations

- Set up manufacturing accounting policies in Cost Management.

- Configure tax codes for multiple jurisdictions.

- Configure lead scoring model based on engagement and demographics.

- Set up SLA policies for premium customers.

- Configure resource scheduling optimization for technician availability.

### Success by Design guidelines for configurations

- Follow catalog mapping to menu paths and modules.

- Use configuration templates for consistency.

- Avoid direct edits; follow governance for changes.

## Enhancement work item type

Enhancements are customizations that extend or modify standard Dynamics 365 functionality to meet unique business requirements. These customizations can include code changes, custom plugins, extensions, or low-code solutions such as Power Apps. Enhancements are project-specific and vary by customer, so it's important to document technical and functional design details.

The business process catalog from Microsoft doesn't include any enhancements, because these custom deliverables are tailored to each implementation. Future catalog updates focus on standard processes, while enhancements remain customer-specific.

Document enhancements as individual work items to ensure traceability and governance throughout the project lifecycle. Each enhancement work item should capture both the functional design, which explains the business need and expected behavior, and the technical design, which details the implementation approach and technology stack. Linking enhancements to related business processes, requirements, workflows, configurations, and testing activities provides end-to-end visibility and supports quality assurance. Because enhancements are custom and specific to each customer, naming conventions should clearly reflect the process or feature being extended. This clarity makes it easier to manage dependencies and review during solution design and testing phases.

### Examples of enhancements

- Add custom field for sustainability score in product master in Dynamics 365 Supply Chain Management

- Develop custom workflow for vendor onboarding in Dynamics 365 Finance

- Add custom field for competitor name on opportunity form in Dynamics 365 Sales

- Create custom ribbon button for quick case reassignment in Dynamics 365 Customer Service

- Develop custom plugin to auto-calculate travel time for work orders in Dynamics 365 Field Service

### Success by Design guidelines for enhancements

- Justify every enhancement with clear business value and Fit/Gap analysis to ensure alignment with project scope and measurable outcomes.

- Prioritize low-code or no-code solutions (such as Power Apps, Power Automate, or AI-driven or agentic solution) over heavy customizations to reduce complexity and upgrade risk.

- Document both functional and technical design details, including dependencies, integration points, assumptions, test cases, and architectural decisions. Use ADRs for transparency and traceability.

- Plan lifecycle management for upgrades and maintenance, noting potential impacts on future releases and ISV solutions.

- Validate compliance and security implications, especially for enhancements involving sensitive data or automated decision-making.

- Apply Responsible AI principles (Fairness, Reliability and Safety, Privacy and Security, Inclusiveness, Transparency, Accountability) when building AI-driven or agentic enhancements.

- Ensure human oversight for autonomous or semi-autonomous agentic features. Include mechanisms to pause or shut down execution if needed.

- Implement transparency and traceability for AI agents by logging prompts, decisions, and actions to support debugging, compliance, and ethical reviews.

- Perform risk assessments for emergent behaviors and multi-agent collaboration, and define clear boundaries for agent capabilities.

- Link enhancements to related requirements, workflows, configurations, and testing work items to maintain end-to-end governance and support Solution Blueprint reviews.

- Conduct performance and scalability checks for enhancements that introduce automation or AI-driven logic to ensure operational reliability.

## Documentation work item type

Documentation deliverables provide essential guidance and reference materials that support implementation, governance, and ongoing operations. They include user guides, strategy documents, and solution design artifacts that align with the Success by Design framework.

The business process catalog includes a small number of documentation deliverables, such as the *Solution Blueprint*, and strategy documents for key Success by Design topics, such as Environment Strategy, ALM Strategy, and Integration Strategy. These deliverables serve as foundational artifacts for governance and quality assurance. Create additional documentation deliverables as needed to capture project-specific details and ensure traceability.

Use documentation work items to catalog all critical reference materials that support the implementation and governance of Dynamics 365 projects. For standard Success by Design documents included in the catalog, use the provided work items to track completion and updates. For custom documentation, create a dedicated work item to capture the purpose, scope, and links to the actual content. This approach ensures visibility, supports audits, and provides a central artifact for linking related deliverables such as workshops, configurations, and testing activities.

### Examples of documentation

- Solution Blueprint

- Environment Strategy

- Application Lifecycle Management (ALM) Strategy

- User guide for purchase order approval process

- Technical design document for integration architecture

- User guide for creating and managing quotes in Sales Hub

- Knowledge article for resolving common billing disputes

- Step-by-step guide for technicians to use the mobile app offline

### Success by Design guidelines for documentation

- Ensure documentation aligns with **Success by Design phases** and supports governance checkpoints.

- Use standard templates for strategy documents and solution design artifacts to maintain consistency.

- Include links to authoritative sources such as Microsoft Learn and internal best practices.

- Keep documentation updated throughout the project lifecycle to reflect design changes and decisions.

- Store documentation in a centralized repository with version control for auditability.

- Link documentation work items to related deliverables, such as workshops, configurations, and testing, for traceability.

## Job work item type

Jobs represent scheduled or automated processes that execute background tasks across Dynamics 365 applications. These jobs ensure operational efficiency by automating repetitive tasks, reducing manual intervention, and maintaining system performance.

In finance and operations apps, jobs typically include batch jobs implemented through the SysOperation or RunBaseBatch frameworks for asynchronous processing. In customer engagement apps, jobs often involve scheduled Power Automate flows, asynchronous plugins, and workflow executions that run in the background. For Business Central, you manage jobs with job queues and background runs of codeunits to support recurring tasks and integrations.

You can configure jobs for recurrence and scheduling, such as flow recurrence, workflow scheduler, or job queue recurrence. Monitoring and troubleshooting are critical, and logs, flow run history, plugin trace logs, and job queue status reports support these activities.

The business process catalog currently includes all standard out-of-the-box (OOB) jobs for finance and operations apps in the December 2025 release. The catalog plans to include standard jobs for other applications in future releases.

Use job work items to catalog both standard and custom jobs that are essential for process execution. For OOB jobs, use the provided work items to confirm scope and link related deliverables such as testing and security. For custom jobs, create a dedicated work item to capture the purpose, recurrence, execution type, and monitoring details. Relate the custom item to the business process and enhancement that supports the job. This approach ensures visibility, supports audits, and provides a central artifact for linking to related configurations, integrations, and cutover activities.

### Examples of jobs

- Nightly batch job for posting inventory journals.

- Scheduled job for updating currency exchange rates.

- Nightly job to sync product catalog updates from ERP to Sales.

- Batch job to close inactive cases older than 90 days.

- Scheduled job to refresh resource availability calendars.

### Success by Design guidelines for jobs

- Confirm that all standard out-of-the-box jobs are in scope and linked to relevant processes.

- Document custom jobs with a clear purpose, recurrence, and dependencies.

- Validate job configurations during design workshops and include them in cutover planning.

- Ensure that you test jobs in non-production environments before deployment.

- Link job work items to related deliverables such as integrations, configurations, and testing for traceability.

- Plan the overall job schedule across environments to avoid conflicts and ensure sequencing aligns with business processes and cutover timelines.

- Consider performance and timing requirements:

- Define acceptable execution windows for high-volume jobs.

- Schedule resource-intensive jobs during off-peak hours to minimize system impact.

- Use recurrence settings and throttling options to balance load.

- Monitor and optimize job performance:

- Track execution times and success or failure rates.

- Implement retry and error-handling strategies for resilience.

- Introduce Agentic AI where appropriate:

- Use AI agents to monitor job health, predict failures, and recommend optimizations.

- Enable adaptive scheduling where AI dynamically adjusts job timing based on system load or business priorities.

- Apply Responsible AI principles (Fairness, Reliability and Safety, Privacy and Security, Transparency, Accountability) when automating decisions about job execution.

- Ensure human oversight for autonomous scheduling or orchestration features.

- Log AI-driven decisions for transparency and compliance.

- Review job dependencies and ensure they don't block critical processes or integrations.

## Migration work item type

Migration work items represent the transfer of data from legacy systems or external sources into Dynamics 365 applications. This transfer includes master data, transactional data, and historical records required for continuity and compliance.

The business process catalog includes migration work items for standard master data entities such as customers, vendors, and suppliers. For all other migrations, create new work items to document the scope, source system, and technical approach. Each migration work item should focus on one source system. For example, if you're migrating customers from two different systems, create separate work items following a naming standard such as "Migrate Customers from \[Source System\]."

Use migration work items to catalog all data migration activities, whether standard or custom. For out-of-the-box master data migrations, confirm scope and link related deliverables such as testing and validation. For custom migrations, create dedicated work items to capture source and target details, migration strategy, and validation methods. This approach ensures traceability and supports governance during cutover. Naming conventions should clearly indicate the data entity and source system to simplify tracking and reporting.

> [!NOTE]
> For master data with multiple related tables or entities, create one parent work item to represent the logical entity, such as Customer/Partner. Then take one of the following approaches.

- Add child work items for each related entity, such as *Customer Addresses*, *Customer Contacts*, or *Customer Bank Accounts*.
- Document the details of each related entity on the parent work item itself.

This approach ensures clarity, supports governance, and simplifies linking to testing and validation activities.

### Examples of migrations

- Migrate vendor master data from SAP to Dynamics 365.

- Import historical sales transactions into CRM.

- Migrate historical opportunities from Salesforce to Dynamics 365 Sales.

- Import legacy case data from Zendesk.

- Load historical work orders from legacy field service system.

### Success by Design guidelines for migrations

- Confirm that all standard out-of-the-box migration work items for master data are in scope and linked to relevant processes.

- Create new migration work items for extra data entities and custom scenarios.

- Use one source system per migration work item for clarity and governance.

- Validate migration strategy and method during design workshops and include them in cutover planning.

- Document dependencies and ensure sequencing aligns with the overall cutover timeline.

- Perform data quality checks and define rollback procedures for risk mitigation.

- Link migration work items to related deliverables such as integrations, configurations, and testing for traceability.

- Plan performance and timing considerations:

- Schedule large-volume migrations during off-peak hours.

- Define acceptable execution windows and monitor throughput.

- Agentic AI considerations:

- Use AI agents to **predict migration risks**, optimize sequencing, and recommend retry strategies.

- Apply **Responsible AI principles** (Fairness, Reliability, Privacy, Transparency, Accountability) when automating migration decisions.

- Enable **adaptive migration scheduling** where AI adjusts timing based on system load or data quality checks.

- Log AI-driven decisions for compliance and auditability.

## Personalization work item type

Personalization work items represent adjustments to the user experience in the relevant Dynamics 365 apps. These adjustments improve usability and efficiency for specific roles or individuals. Typically, these changes involve modifying forms, views, dashboards, or workspace layouts without altering core functionality.

The business process catalog doesn't currently include personalization work items, but the product team is evaluating whether to include standard personalization templates in future releases. For now, document personalization deliverables as custom work items when they're part of the implementation scope.

Use personalization work items to capture all UI adjustments that optimize user experience for specific roles or business scenarios. Document the purpose, affected areas, and any dependencies on configurations or workflows for each work item. Linking personalization work items to related requirements and testing ensures traceability and supports governance. If you need multiple variations for different legal entities, departments, or regions, create separate work items and name them accordingly.

### Examples of personalizations

- Customize workspace for Accounts Payable clerk.

- Add quick links for frequently used reports in Finance dashboard.

- Migrate historical opportunities from Salesforce to Dynamics 365 Sales.

- Import legacy case data from Zendesk.

- Load historical work orders from legacy field service system.

### Success by Design guidelines for personalizations

- Validate personalization requirements during design workshops and confirm alignment with business roles.

- Use standard personalization features before considering custom development to minimize complexity.

- Document all changes for governance and audit purposes.

- Link personalization work items to related requirements, workflows, and testing deliverables for traceability.

- Ensure accessibility compliance and performance impact are assessed before deployment.

- If personalization involves automation or adaptive UI changes, apply **Responsible AI principles** and ensure transparency and user control.

## Security work item type

Security work items represent the measures required to protect data, enforce compliance, and manage access in Dynamics 365 projects. This protection includes role-based security, data access controls, environment-level security, and compliance configurations. Security deliverables ensure that only authorized users can perform specific actions, sensitive data is protected, and organizational policies are enforced across all environments.

Currently, the business process catalog doesn't include security work items, but Microsoft is evaluating how to incorporate standard security templates in a future release. For now, document security deliverables as custom work items when they're part of the implementation scope.

Use security work items to capture all aspects of security configuration for a project. This use includes defining security roles, field-level permissions, data privacy settings, and environment access controls. Each work item should document the purpose, compliance requirements, and dependencies on workflows, integrations, or configurations. Linking security work items to related deliverables such as testing and documentation ensures traceability and supports governance. If multiple variations are required for different legal entities or regions, create separate work items and name them accordingly.

As organizations adopt AI agents and agentic automation in Dynamics 365, security becomes even more critical. Agents often interact with sensitive data, invoke tools, and execute actions autonomously or semi-autonomously. This interaction introduces new risks such as data leakage, prompt injection attacks, and unauthorized tool usage. To mitigate these risks, extend security measures beyond traditional role-based access to include agent identity management, real-time monitoring, and policy enforcement.

Implement agent-specific identities, such as Azure AD service principals. Apply Microsoft Purview Data Security Posture Management for AI, and enable Defender for AI agents for real-time threat detection and blocking of suspicious actions. Additionally, apply Responsible AI principles—Fairness, Reliability and Safety, Privacy and Security, Transparency, and Accountability—when designing and deploying agentic workflows. This application includes logging agent decisions, enforcing compliance policies, and ensuring human oversight for critical operations.

### Examples of security tasks

- Create a security role for warehouse manager.

- Implement segregation of duties for finance roles.

- Create a security role for regional sales managers with access to their territory only.

- Restrict case visibility to assigned queues.

- Ensure technicians can only view work orders assigned to them.

### Success by Design guidelines for security

- Validate security requirements during design workshops and confirm alignment with organizational policies and compliance standards.

- Implement role-based security by using least-privilege principles to minimize risk.

- Configure field-level and record-level security for sensitive data and enforce environment-level access controls.

- Document compliance requirements, such as GDPR and SOX, and ensure configurations meet regulatory standards.

- Link security work items to related deliverables, such as workflows, integrations, and testing, for traceability.

- Perform penetration testing and vulnerability assessments before go-live.

- Agentic AI considerations:

- Apply Responsible AI principles (Fairness, Reliability & Safety, Privacy & Security, Transparency, Accountability) when designing agentic workflows or AI-driven security monitoring.

- Implement agent-specific identities, such as Azure AD service principals, and enforce strict access policies for AI agents.

- Enable real-time monitoring and anomaly detection for agent actions by using Microsoft Defender for AI and Purview Data Security Posture Management.

- Ensure human oversight for autonomous or semi-autonomous agents performing security-sensitive tasks.

- Log all AI-driven decisions and actions for transparency, compliance, and auditability.

- Define clear boundaries for agent capabilities and perform risk assessments for emergent behaviors or multi-agent collaboration.

## Workshop work item type

Workshops are interactive sessions designed for requirements gathering, solution design, process mapping, and decision-making. They foster collaboration and alignment among stakeholders and are a cornerstone of the Success by Design framework. The business process catalog includes several types of workshops, such as scenario board discovery workshops, storyline design review workshops, and detailed design workshops for each business process area. Additionally, generic workshops like the [Solution Blueprint Review](../fasttrack/solution-workshops.md) and [the environment strategy](../implementation-guide/environment-strategy-overview.md) support key Success by Design topics.

Learn about the default workshops and their structure at [Workshops for Dynamics 365 implementation projects](about-workshops.md). The catalog's workshop list isn't exhaustive. Partners supplement these workshops with workshops tailored to their industry expertise and methodology. The partner's approach aligns with the Success by Design framework and incorporates Microsoft's recommended workshops, but also expands to address unique project needs.

Use workshop work items to catalog all critical collaborative sessions throughout the project lifecycle. For standard workshops included in the catalog, use the provided work items to track planning, delivery, and outcomes. For custom or partner-specific workshops, create dedicated work items to capture objectives, agenda, key questions, and decisions. This approach ensures visibility, supports audits, and provides a central artifact for linking related deliverables such as requirements, configurations, and testing activities.

### Workshops for agents and agentic automation

As organizations adopt AI agents and agentic automation, approach workshops with a process-first mindset. While it's appropriate to conduct detailed workshops about a specific agent when necessary (for example, designing a Copilot for a particular business scenario), prioritize workshops that focus on reshaping and optimizing business processes to become frontier firms. The goal is to identify opportunities where agents and AI can drive transformation, streamline workflows, and elevate business outcomes - not simply to implement a specific agent or feature.

Workshops should encourage stakeholders to think holistically about how automation, AI, and agents can be embedded within end-to-end processes in support of strategic objectives and organizational change. By focusing on process innovation, teams can ensure that agentic solutions are aligned with business goals, scalable across the enterprise, and governed by responsible AI principles. Partners and project teams use workshops to challenge existing practices, explore new operating models, and design processes that leverage the full potential of AI and automation - rather than limiting the conversation to the technical details of a single agent.

### Examples of workshops

- Fit/gap workshop for the *Order to Cash* end-to-end process.

- Design workshop for integration architecture.

- Workshop to define lead qualification criteria and scoring model.

- Session to design case escalation paths and SLA rules.

- Workshop to plan preventive maintenance schedules and resource allocation.

### Success by Design guidelines for workshops

- Prepare a clear agenda and key questions in advance to drive focused discussion.

- Capture decisions, assumptions, and action items in Azure DevOps work items for traceability.

- Align workshops with Success by Design phases (Envision, Design, Build, Test).

- Reference standard workshop templates and objectives from the catalog, but tailor sessions to project and industry needs.

- Encourage partner teams to supplement catalog workshops with additional sessions that reflect their methodology and expertise.

- Document outcomes, risks, and follow-up actions for each workshop to support governance and continuous improvement.

- Apply agentic principles:

- Prioritize process-focused workshops that explore how AI agents and automation can reshape business processes, rather than focusing solely on individual agent features.

- Use workshops to identify opportunities for responsible AI adoption, process innovation, and frontier firm transformation.

- Ensure workshops address Responsible AI principles—Fairness, Reliability & Safety, Privacy & Security, Transparency, and Accountability—when designing agentic workflows or automation.

- Promote human oversight, transparency, and traceability for agent-driven decisions and actions.

- Challenge existing practices and encourage stakeholders to design processes that leverage AI and automation for strategic business outcomes.

## Deliverable work item type

Deliverables are tangible outputs produced as part of a Dynamics 365 project. They represent key milestones, artifacts, or work products that drive project progress and quality assurance. The business process catalog includes standard and mandatory Success by Design deliverables, such as the **Solution Blueprint** and **Environment Strategy**. These deliverables are foundational for governance and are required for every implementation.

### Difference between Documentation and Deliverable work item types

To help you understand why there are separate work items for documentation and deliverables, the following list provides context.

- *Deliverable* work items track major project outputs that typically align with the statement of work (SOW) and contractual commitments to the customer. Examples include the Solution Blueprint, Environment Strategy, and other milestone artifacts.

- *Documentation* work items catalog supporting materials, reference guides, strategy documents, and other documentation that might not be contractual deliverables but are essential for implementation, governance, or user enablement.

Use Deliverable work items for anything that the contract, SOW, or Success by Design explicitly promises. Use Document work items for additional materials, guides, or reference content created throughout the project.

Partners typically align deliverables with the contract they have with the customer. However, they might create extra deliverables as the project evolves to address new requirements, risks, or opportunities.

Use deliverable work items to catalog all major outputs and milestones required by the project, especially those specified in the SOW or Success by Design framework. For standard deliverables included in the catalog, use the provided work items to track completion and updates. For custom or extra deliverables, create dedicated work items to capture the purpose, scope, and links to related documentation, testing, and configuration activities. This approach ensures visibility, supports audits, and provides a central artifact for linking to requirements, workshops, and other deliverables.

### Examples of deliverables

- Solution blueprint document for Concept to Market.

- Configuration workbook for Finance module.

- Configuration workbook for SLA and routing rules.

- Blueprint for resource scheduling optimization.

### Success by Design guidelines for deliverables

- Link deliverables to workstreams and acceptance criteria.

- Use standard naming conventions for traceability.

- Validate completeness before sign-off.

## Testing work item type

Use testing work items to triage and plan validation activities for Dynamics 365 implementations. These work items help teams organize and track the scope of testing before creating actual test cases, test plans, or test suites. Testing ensures that solution functionality, performance, security, and compliance requirements are met before go-live.

The business process catalog from Microsoft doesn't include any testing work items. Instead, create testing work items as needed to capture requirements, plan scenarios, and link to related deliverables. These work items serve as a bridge between requirements and formal test artifacts, supporting traceability and governance.

Use testing work items to catalog all planned validation activities, including functional, performance, security, integration, and user acceptance testing. When you identify a requirement or need for testing throughout the project, create a testing work item to document the scope, objectives, and acceptance criteria. As the project progresses, link these work items to actual test cases, test plans, or test suites for execution and reporting. This approach ensures comprehensive coverage and supports auditability.

### Examples of tests

- Test case for purchase order registration workflow.

- Performance test for high-volume transaction posting.

- Test case for quote creation from opportunity with discount approval.

- Scenario to validate SLA breach escalation workflow.

- Test mobile app functionality for offline work order updates.

### Success by Design guidelines for tests

- Include unit, integration, performance, security, and user acceptance scenarios in the testing plan.

- Map tests to requirements, configurations, workflows, and enhancements for traceability.

- Automate testing where possible by using RSAT, Power Platform test tools, or similar frameworks.

- Document acceptance criteria and expected results for each test.

- Link testing work items to related deliverables for auditability and governance.

- For agentic AI and automation, design tests to evaluate:

- AI agent reliability, safety, and compliance with Responsible AI principles.

- Transparency and traceability of agent decisions and actions.

- Human oversight for autonomous or semi-autonomous features.

- Performance and scalability of agentic workflows under real-world conditions.

- Security and privacy risks associated with AI-driven automation.

- Use testing work items to plan and document evaluations of AI models, prompts, and agentic features, ensuring ethical and responsible deployment.

## Related content

- [Recommended fields for Azure DevOps work items from the business process catalog template](about-devops-work-items-deliverables-fields.md)  
- [Custom work item type for configuration deliverables in the Dynamics 365 business process catalog](about-import-catalog-devops-configuration-deliverable-work-item-type.md)  
- [Custom work item type for workshops in the Dynamics 365 business process catalog](about-import-catalog-devops-workshop-work-item-type.md)  
- [Other work item types in the business process catalog](about-devops-work-items-other.md)  
- [Use the business process catalog as a template in Azure DevOps Services](about-import-catalog-devops.md)  
- [Overview of the business process catalog levels](about-catalog-levels.md)  