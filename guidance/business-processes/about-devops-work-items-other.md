---
title: Azure DevOps Work Item Types Overview
description: Discover how the Azure DevOps template supports structured project management with specialized work item types for trees, test suites, and others.
author: edupont04
ms.author: edupont
ms.reviewer: edupont
ms.date: 12/19/2025
ms.topic: concept-article
---

# Other work item types in the business process catalog

The business process catalog and Azure DevOps template use a variety of work item types beyond the business process catalog and deliverables. These other work item types help partners and customers effectively manage and track the progress of deliverables, delivery plans, and objectives. This article describes all the other work item types that are included in the [Azure DevOps template](https://github.com/microsoft/dynamics365patternspractices/tree/main/templates/Azure-DevOps-templates) that Microsoft provides as a downloadable Excel workbook. Together, these work item types provide the structure needed to support project governance, traceability, and efficient execution across all phases of the business process catalog.

> [!TIP]
> Import the work item types into your Azure DevOps based on the provided Excel workbook. For more information, see [Import, update, and export bulk work items with CSV files in Azure Boards](/azure/devops/boards/queries/import-work-items-from-csv?view=azure-devops&preserve-view=true). Once you import the work item types, users can create work items based on the new work item types. For more information, see [View and add work items](/azure/devops/boards/work-items/view-add-work-items).

## Tree

The **Tree** work item type serves as the structural backbone for organizing large groups of work items into logical hierarchies. It delineates top-level nodes for backlog types such as *business process catalog*, *Deliverables*, and *Delivery Plan*. Use it for navigation, governance, and clarity across workstreams to enable consistent reporting. Don't create new Tree nodes beyond those provided in the standard template. Instead, use existing hierarchy definitions to maintain consistency. Include Tree items as rows only when structural representation is required for catalog exports or visualization. Omit them to keep the catalog lean. Future recommendations might suggest adding or modifying Tree nodes to support advanced reporting and AI-driven navigation. Use Tree items to avoid unnecessary proliferation, consolidating nodes for clarity and aligning with approved hierarchy definitions. Additionally, Tree structures play a critical role in supporting scaled agile planning and governance for enterprise programs.

### Trees in the provided templates

- **Business process catalog**  

  This tree defines the "why". It defines implementation by capturing core business processes for operations. It provides a structured hierarchy starting with system-agnostic levels - end-to-end processes and process areas - into detailed processes and patterns. It ensures alignment with business objectives and serves as the foundation for scoping and solution design.
- **Deliverables**  

  This tree defines the "what". It represents tangible outputs required to tailor the solution, including configurations, workflows, integrations, and documentation. Deliverables align with Success by Design principles, helping track requirements and convert them into actionable outputs for visibility and traceability throughout the project lifecycle.
- **Delivery Plan**  

  This tree defines the "when and how". It outlines the project methodology and delivery approach. It organizes phases, workshops, timelines, milestones, and teams to plan and monitor execution. The plan integrates with visualization tools such as Gantt charts and roadmaps to track progress and dependencies.
- **Objectives**  

  This tree defines the "goals". It captures overarching goals and success criteria for the initiative. It includes executive objectives, program increments, and sprint-level targets. It aligns activities with strategic priorities by linking objectives to deliverables and processes, supporting governance and continuous progress tracking against business outcomes.

## Folder

The business process catalog includes predefined folders in certain trees to improve organization and navigation. For example, in the **Deliverables tree**, folders are provided for each **Area Path**, which represents functional areas. These folders help group related deliverables logically under their respective domains.  

Here's a list with examples from the Finance area:

- Finance
- Accounting
- Accounting
- Asset financials
- Inventory valuation
- Organization structure
- Accounts payable
- Accounts payable
- Expense management
- Supplier management
- Supplier trade allowances

This structure ensures clarity for stakeholders and simplifies reporting across functional areas. Partners should create folders in the Delivery Plan tree to organize work items by iteration paths, phases, key milestones, or project stages. These folders provide a clear visual structure for planning and tracking progress without altering the underlying process taxonomy. When adding new folders, ensure alignment with governance standards to maintain consistency and avoid unnecessary complexity.

### Success by Design guidelines for Folder

- Use Folder items for structure and discoverability, not for documenting procedural steps or outcomes.
- Minimize proliferation; prefer a stable taxonomy (capability → module → process → scenario).
- Consolidate overlapping groupings and avoid duplicate work item names for multiple folders.
- Maintain traceability by linking Folder items to their parent Tree node and applying consistent naming conventions.
- Agentic AI considerations: Design folder names as interpretable labels that convey scope and context for AI-driven navigation and summarization. Include lightweight metadata for AI agents to infer relationships and generate dynamic recommendations.

### Recommended fields for Folder

The following fields are recommended for the **Folder** work item type and included by default in the Azure DevOps template for the business process catalog:

|Name  |Description  |
|---------|---------|
|Title| Display name of the folder.|
|Parent Tree|Links the folder to its parent node in the catalog hierarchy for transparency's sake.|
|Folder Path|Specifies the logical path, such as *Deliverables\Finance\Accounting*.|
|Purpose|Brief description of the folder's scope.|
|Owner|Responsible person or team for folder contents.|
|Visibility/Permissions|Access scope for governance.|
|Review Cadence|Frequency for review and archival.|
|Catalog Status|Add the values *Active*, *Deprecated*, and *Future*.|

When users create new work items based on this work item type, recommend that they also take the following steps:

- Provide a clear, descriptive name for the folder, such as *Finance – Accounting*.  
- Add related work items  

  Link relevant deliverables, documentation, or other work items under the folder for structured navigation.
- Verify the hierarchy  

  Make sure that the folder appears correctly in the catalog hierarchy and supports roll-up reporting.

## Functional area

The Functional area work item type represents a finer-grained categorization under another node in the catalog, grouping related features or sub-capabilities typically aligned to application modules, departments, or functional domains. It provides additional structure for ownership, configuration deliverables, and reporting without duplicating the process taxonomy defined in the business process catalog. Functional Areas are not included out-of-the-box in the catalog. They are recommended for use in the Delivery Plan tree to help organize work into logical groupings that reflect the functional areas of the project. This approach improves visibility for governance, planning, and estimation, especially in large implementations with multiple modules or workstreams.

### When to use functional areas

- Use functional area rows when you need visibility into sub-domains for governance, configuration planning, or reporting.
- Omit them if Process Areas and tags provide sufficient granularity for organizing work.
- Use them for Delivery Plan organization, where they can map to iteration paths, phases, or key milestones for better tracking.

### Success by Design guidelines for Functional Area

- Use functional areas for structure and discoverability, not for documenting procedural steps or outcomes.
- Avoid unnecessary proliferation. Consolidate overlapping definitions and maintain alignment with approved catalog hierarchy.
- Apply consistent naming conventions aligned to application modules or organizational domains.
- For agentic AI considerations, design the names of functional areas as interpretable labels that convey scope and context for AI-driven navigation and summarization.

### Recommended fields for Functional Area

The following fields are recommended for the **Functional area** work item type and included by default in the Azure DevOps template for the business process catalog:

|Name  |Description  |
|---------|---------|
|Title|Display name of the functional area.|
|Parent Process Area|Reference for traceability.|
|Purpose|Brief description of the functional area's scope.|
| Owner|Responsible person or team.|

When users create new work items based on this work item type, recommend that they also take the following steps:

- Provide a clear, descriptive name for the functional area, such as *Accounts Payable*.
- Link relevant deliverables, configuration tasks, or documentation under the functional area for structured navigation.
- Make sure that the functional area appears correctly under its parent process area and supports roll-up reporting.

## Phase

The Phase work item type represents a major stage in the delivery lifecycle. It provides structure for planning, governance, and visibility across the project timeline. Phases anchor time-bound deliverables, reviews, and decision gates, ensuring alignment with the Success by Design methodology. They help teams visualize project stages (for example, *Initiate*, *Prepare*, *Execute*, *Optimize*) and link related tasks, deliverables, and status reports for traceability. The business process catalog doesn't include phases out of the box. Create these phases under the Delivery Plan tree to align with your methodology and project approach. This approach improves clarity for stakeholders and supports structured reporting.

### Recommendation on when to use phases

- Use Phase rows when you need to visualize project stages and organize work items by lifecycle.
- Map deliverables, tasks, and reviews to phases for traceability and governance.
- Avoid creating unnecessary custom phases. Adhere to the standard phase model for consistency.

### Success by Design Guidelines

- Adopt the organization's standard phase model (*Initiate, Prepare, Execute, Optimize*).
- Define **clear entry and exit criteria** for each phase.
- Map deliverables (tasks, test plans, status reports) to phases for visibility.
- Use **phase gates** for decisions and risk mitigation.

### Recommended fields for Phase

The following fields are recommended for the **Phase** work item type and included by default in the Azure DevOps template for the business process catalog:

|Name  |Description  |
|---------|---------|
|Title|Display name of the phase, such as *Prepare*.|
|Duration|Planned length of the phase, such as in days or weeks.|
|Estimate| Effort required for activities within the phase, such as hours or story points.|
|Start Date|Planned start date for the phase.|
|Target Date|Planned completion date for the phase.|

When users create new work items based on this work item type, recommend that they also take the following steps:

- Associate deliverables, tasks, and reviews under the phase for structured navigation and reporting.

- Ensure the phase appears correctly in the Delivery Plan tree and supports roll-up reporting.

## Task

The Task work item type represents a granular unit of work that advances a deliverable, configuration, or documentation item toward completion. It's action-oriented, time-bound, and traceable to parent catalog items such as Processes, Scenarios, or Workshops. The Azure DevOps template for the business process catalog includes tasks by default. Modify the template to align Task fields and workflow with catalog governance standards for consistency across implementations. Tasks ensure visibility and accountability throughout the delivery plan. Reserve them for work that impacts deliverables rather than minor notes or informal actions.

Here's an example of a task: *Configure price calculation parameters for sales orders in Dynamics 365 Finance and validate with sample data.*

### Success by Design guidelines for Task

- Start Task titles with a verb to indicate action.
- Define a clear Definition of Done (DoD) and due date for each Task.
- Assign a single accountable owner and include dependencies or blockers.
- Link the Task to its parent item (Process, Scenario, or System Process) for traceability.
- Attach evidence upon completion (screenshots, documents, logs).  
- Design Task metadata to support AI-driven prioritization and recommendations. Include clear labels and consistent taxonomy so AI agents can infer dependencies, predict delays, and suggest automation opportunities.

### Recommended fields for Task

The following fields are recommended for the **Task** work item type and included by default in the Azure DevOps template for the business process catalog:

|Name  |Description  |
|---------|---------|
| Title|Clear, action-oriented name for the task.|
|Parent Link|Reference to the parent deliverable or catalog item.|
|Owner|Person responsible for execution.|
|Due Date|Target completion date.|
|Dependencies| Work that must precede this Task.|
|Definition of Done (DoD)|Criteria for completion.|
|Status| Current state (New, Active, Closed).|
|Tags|Labels for capability, release phase, or priority.|

## Action item

An Action item represents a quick, discrete follow-up task that typically arises from meetings, workshops, or issue triage. It's short-lived and focused on ensuring completion of a specific action without requiring detailed estimation or complex planning. The business process catalog template doesn't include Action Items by default. Use them for commitments that impact deliverables or decisions. They're ideal for capturing immediate actions that need accountability and visibility. Avoid using Action Items for major tasks or configuration work. Reserve those tasks for Task work item types.

Here's an example of an action item: *Update the O2C workflow diagram to reflect new tax calculation service and circulate for review.*

### Success by Design guidelines for Action Item

- Use Action Items for quick actions that don't require detailed estimation or scheduling.
- Assign a single accountable owner and a clear due date for every Action Item.
- Capture context such as the originating meeting, decision, or issue to maintain traceability.
- Link Action Items to impacted catalog items (for example, Processes, Scenarios, Deliverables) for governance.
- Close promptly and record outcomes or residual risks.
- Agentic AI Considerations: Design Action Item metadata to support AI-driven recommendations for prioritization and follow-up. Include clear labels and consistent taxonomy so AI agents can infer urgency and dependencies.

### Recommended fields for Action Item

The following fields are recommended for the **Action Item** work item type. The Azure DevOps template for the business process catalog includes these fields by default:

|Name  |Description  |
|---------|---------|
|Title|Clear, action-oriented name for the item.|
|Owner|Person responsible for completion.|
|Due Date|Target completion date.|
|Context|Originating meeting, decision, or issue.|
|Impacted Items|References to related catalog items.|
|Status|Current state (New, Active, Closed).|
|Tags|Labels for capability, release phase, or priority.|

## Bug

A Bug represents a defect detected during testing or operation. It captures observed versus expected behavior, scope, and severity. It tracks the work required to correct the defect and verify the fix. The Azure DevOps template for the business process catalog doesn't include Bugs by default. Use Bug items for problems that impact functionality or compliance. Ensure traceability to related Test Cases and Scenarios. Don't use Bug items for minor cosmetic problems unless they affect user experience or business outcomes.

Here's an example of a bug: *Incorrect VAT rounding when posting sales orders for reduced-rate items.*

### Success by Design guidelines for Bug

- Provide reproducible steps and evidence (logs, screenshots). Note environment and build/version.
- Assess business impact and severity. Link to failing test case and impacted scenarios.
- Document fix verification and regression coverage.
- Maintain clear state transitions (New → Active → Resolved → Closed) for governance.
- Agentic AI Considerations: Design Bug metadata to support AI-driven triage and prioritization. Include structured fields for severity, priority, and repro steps so AI agents can infer risk, suggest fixes, and automate reporting.

### Recommended fields for Bug

The following fields are recommended for the **Bug** work item type and included by default in the Azure DevOps template for the business process catalog:

|Name  |Description  |
|---------|---------|
|Title|Clear, descriptive name of the defect.|
|Repro Steps |Detailed steps to reproduce the issue.|
|System Info|Environment details (build, version).|
|Severity/Priority|Impact and urgency indicators.|
|Linked Test Cases|References to associated validations.|
|Status|Current state (New, Active, Resolved, Closed).|
|Tags|Labels for capability, release phase, or module.|

## Risk

Risk represents a potential event or condition that could negatively impact project objectives such as timeline, scope, or budget. It requires proactive identification, probability and impact assessment, and mitigation planning to minimize adverse effects. Risks aren't included by default in the business process catalog Azure DevOps template. Use Risk items for significant uncertainties that could derail delivery or require contingency planning. Avoid using Risk for problems that already occurred. Log those problems as Issues.

Here's an example of a risk: *A delay in integration delivery might delay the start of UAT and affect go-live readiness.*

### Success by Design guidelines for Risk

- Use a scoring model (probability × impact) to quantify risk severity.
- Define clear triggers and early warning signs for monitoring.
- Assign an accountable owner and track mitigation and contingency actions with due dates.
- Review risks at phase gates and escalate high-severity risks promptly.
- Agentic AI Considerations: Design risk metadata to support AI-driven prioritization and predictive insights. Include structured fields for probability, impact, and mitigation status so AI agents can infer trends and recommend actions.

### Recommended fields for Risk

The following fields are recommended for the **Risk** work item type and included by default in the Azure DevOps template for the business process catalog:

|Name  |Description  |
|---------|---------|
|Title|Clear, descriptive name of the risk.|
|Probability / Impact|Numeric or categorical scoring for severity.|
|Mitigation Plan|Actions to reduce likelihood or impact.|
|Contingency Plan|Fallback actions if risk materializes.|
|Owner|Person accountable for monitoring and resolution.|
|Review Date|Next checkpoint for reassessment.|
|Status|Current state (Open, Mitigated, Closed).|
|Tags|Labels for capability, release phase, or priority.|

## Assumption

An assumption records a condition believed to be true for planning or design. Use it to surface dependencies and uncertainty early so teams can validate them during execution. It improves traceability by explicitly tying planning premises to the deliverables and schedules they affect. Business process catalog templates don't include assumptions by default. Keep the structure consistent across projects and avoid customizing the core workflow unless there's a clear governance need. When a template doesn't include assumptions, plan to add them to enable validation and risk transparency rather than modifying other work item types to carry these details.

Here's an example of an assumption: *Customer master data is migrated and validated before O2C testing begins.*

### Success by Design guidelines for Assumption

- Record the rationale and source for each assumption to make review and validation straightforward.
- Define the validation method and target date so owners know how and when confirmation happens.
- Link each assumption to all dependent deliverables, processes, tests, or milestones to preserve traceability.
- Convert the assumption to an issue immediately if it proves false, and update plans, owners, and dates accordingly.
- Establish a review cadence, such as phase gates or weekly checkpoints, to confirm status and retire stale entries.
- Agentic AI considerations: Use structured fields (rationale, validation date, dependencies, status) so AI can flag conflicts, predict impact when deadlines slip, and nudge owners before validation is due.

### Recommended fields for Assumption

The following fields are recommended for the **Assumption** work item type and included by default in the Azure DevOps template for the business process catalog:

|Name  |Description  |
|---------|---------|
|Title|Concise statement of the assumption.|
|Rationale / Source|Why this assumption is believed and where it originated.|
|Validation method|How the team confirms the assumption, such as data load, sign‑off, test.|
|Validation date|Target date to complete validation.|
|Dependencies|Linked deliverables or processes that rely on the assumption.|
|Status|Open, Validated, Invalidated.|
|Tags|Labels for capability, phase, priority, or domain classification.|

## Issue

An Issue represents a current problem that impacts project delivery, scope, or quality. It differs from a Risk because an Issue is something that already happened and requires immediate attention and resolution tracking. The business process catalog template doesn't include Issues by default. Use them for significant blockers or defects that can't be resolved through normal workflow. Don't log minor questions or clarifications as Issues. Reserve this type for items that require structured resolution and governance. Future enhancements might include AI-driven impact analysis and automated escalation recommendations.

Here's an example of an issue: *API documentation for tax service is incomplete, blocking integration testing.*

### Success by Design guidelines for Issue

- Assign a single accountable owner and a clear due date for resolution.
- Capture the impact and scope of the Issue, including affected deliverables or processes.
- Document resolution steps and decisions for auditability.
- Link the Issue to related Risks, Change Requests, or impacted catalog items for traceability.
- Agentic AI Considerations: Structure metadata to support AI-driven prioritization and escalation. Include fields for severity, dependencies, and deadlines so AI can predict delays and recommend corrective actions.

### Recommended fields for Issue

The following fields are recommended for the **Issue** work item type. They're included by default in the Azure DevOps template for the business process catalog:

|Name  |Description  |
|---------|---------|
|Title|Clear, descriptive name of the Issue.|
|Impact/Scope|Details of affected areas and severity.|
|Resolution Steps|Actions taken or planned to resolve the Issue.|
|Owner|Person accountable for resolution.|
|Due Date|Target date for closure.|
|Status|Current state (New, Active, Resolved, Closed).|
|Tags|Labels for capability, phase, or priority classification.|

## Decision

A Decision work item captures an agreed choice that impacts project scope, design, or delivery. It documents the context, options evaluated, and rationale to ensure downstream traceability and governance. The business process catalog template includes Decisions by default. Use them for significant choices that require auditability and linkage to impacted deliverables. Avoid logging minor clarifications or informal agreements. Reserve this type for decisions that influence requirements, timelines, or solution architecture. Future enhancements might include AI-driven recommendations for decision impact analysis and automated follow-up actions.

Here's an example of a decision: *Approve adoption of centralized tax calculation service across Order-to-Cash with phased rollout.*

### Success by Design guidelines for Decision

- Record the decision date, decision-makers, and options considered with rationale.
- Link impacted catalog items and define follow-up actions such as action items or change requests.
- Store supporting evidence (meeting notes, design documents) for auditability.
- Agentic AI Considerations: Structure metadata to support AI-driven insights for decision impact analysis and proactive recommendations. Include clear fields for context, rationale, and dependencies so AI can predict downstream effects and suggest mitigations.

### Recommended fields for Decision

The following fields are recommended for the **Decision** work item type and included by default in the Azure DevOps template for the business process catalog:

|Name  |Description  |
|---------|---------|
|Title|Clear descriptive name of the decision.|
|Decision Date|When the decision was made.|
| Approver(s)|Persons or roles who approved.|
|Options/Rationale|Alternatives considered and reasons for selection.|
|Impacted Items|References to related processes, deliverables, or work items.|
|Status|Current state (Open, Approved, Implemented).|
|Tags|Labels for capability, phase, or priority classification.|

When users create new work items based on this work item type, recommend that they also take the following steps:

- Define workflow states (New, Approved, Implemented) with transitions aligned to governance.
- Associate Decision work item type with relevant backlog levels for visibility.

## Change request

A change request represents a formal proposal to modify scope, design, configuration, or schedule after you establish the original baseline. It ensures structured impact analysis and governance approval before you implement changes. The business process catalog template doesn't include change requests by default. Generally, create them as needed for each project.

Change requests can vary in their financial impact. A **zero dollar change request** refers to a proposal that doesn't require any additional budget or funding. These change requests typically involve adjustments to schedule, configuration, or process that the existing project resources can accommodate. In contrast, a **funded change request** involves modifications that necessitate extra budget allocation, such as new feature development, increased scope, or resource additions. Properly distinguishing between these two types is important for governance, as budgeted changes might require additional approval steps or financial review.

Typically, change requests closely relate to a **Decision** work item in Azure DevOps. For example, a decision to approve a major process update or system enhancement often triggers a corresponding change request to document the required modifications, assess their impact, and track implementation. Linking change requests to relevant decision records enhances traceability and ensures that documented governance and rationale back every change.

Here's an example of a change request

|Name |Description|
|-|-|
|Expanding end-to-end business process scope|Requesting to incorporate additional business units or departments into the Dynamics 365 implementation beyond what the original project scope defined.|
|Adding a Marketplace solution to fill gaps| Proposing the integration of a third-party Marketplace app (not included in the original Statement of Work) to address a newly identified business need or functional gap.|
|Resource change (non-financial)|Requesting a change in project team composition, such as replacing a functional consultant with another team member, without affecting the overall project budget.|
|Integration architecture modification (non-financial)| Proposing an update to the planned integration architecture, such as switching from scheduled batch integrations to using real-time APIs, that doesn't require additional funding but might impact timelines or technical design.|

### Success by Design guidelines for Change Request

- Describe the change and its drivers, including business justification.
- Assess impact on processes, data, testing, and timeline before submission.
- Route through defined approval workflow and record decision outcomes.
- Track implementation tasks and validation tests.
- Agentic AI Considerations: Structure metadata to support AI-driven recommendations for impact analysis and prioritization. Include fields for dependencies, affected deliverables, and deadlines to predict downstream effects and suggest mitigations.

### Recommended fields for Change Request

The following fields are recommended for the **Change Request** work item type. The Azure DevOps template for the business process catalog includes these fields by default:

|Name  |Description  |
|---------|---------|
|Title|Concise description of requested change.|
|Requestor|Person initiating the change.|
|Description|Explanation of proposed change.|
|Impact Analysis|Effect on scope, schedule, cost, and risk.|
|Approval|Decision status and approvers.|
|Implementation Plan|Tasks, owners, and target dates.|
|Status|Current state (New, Approved, Implemented).|
|Tags|Labels for capability, phase, and priority classification.|

When users create new work items based on this work item type, recommend that they also take the following steps:

- Define workflow states (New → Approved → Implemented) with transitions aligned to governance.
- Associate Change request work item type with relevant backlog levels for visibility.

## Status report

The Status report work item type represents a structured summary of project progress, risks, issues, decisions, and outlook for a specific period or phase. It provides leadership with KPIs and actionable insights for governance and decision-making. The business process catalog template doesn't include status reports by default. Use them consistently for visibility and compliance. By using this work item type with other types such as the Risk, Issues, Assumption, Decision, and Change requests, you can automatically output and create the status report for your project in an automated way. The exact layout, format, and frequency of your status reports can be customized to meet your organization's governance requirements and audience needs.

Here's an example of a status report: *Steering committee status report*

### Success by Design guidelines for Status Report

- Use a standard template with quantitative metrics, such as burnup charts, defect density, or test pass rate.
- Highlight variances and corrective actions. Align reporting cadence with governance checkpoints, such as phase gates and steering meetings.
- Keep reports concise with visuals and archive for traceability.
- Agentic AI Considerations: Include structured fields for KPIs, risks, and decisions to enable AI-driven summarization and predictive analytics. Ensure data is normalized and tagged for trend detection, anomaly alerts, and automated executive summaries.

### Recommended fields for Status Report

The following fields are recommended for the **Status Report** work item type and included by default in the Azure DevOps template for the business process catalog:

|Name  |Description  |
|---------|---------|
|Title| Display name of the status report, such as *Week 47 Status Report*.|
|Reporting Period|Start and end dates.|
|Summary| Narrative of progress and outlook.|
|KPIs| Quantitative indicators (% completion, defect counts).|
|Risks / Issues / Decisions|Highlights by category.|
|Next Steps| Planned actions for upcoming period.|
|Status| Current state (Draft, Published, Archived).|
|Tags| Labels for capability, phase, priority classification.|

When users create new work items based on this work item type, recommend that they also take the following steps:

- Associate the Status Report work item type with relevant backlog levels for visibility.
- Save and publish the process.
- Verify in Boards by creating a sample Status Report linked to phase deliverables for traceability.

## Test plan

A test plan represents the structured approach for validating processes and scenarios during a specific milestone or release. It defines the overall testing strategy, scope, environments, schedules, and exit criteria to ensure quality and compliance. In the future, the business process catalog template will include test plans. You can use test plans consistently for governance and traceability. Future enhancements might include AI-driven predictive analytics for test coverage and automated readiness checks. Modify the test plan only to add organization-specific fields or reporting attributes. Don't alter the core workflow.

Here's an example of a test plan: *Regression test plan for sales scenarios covering pricing, taxation, availability, and returns across EU/US locales.*

### Success by Design guidelines for test plan

- Describe objectives, scope, and coverage clearly.
- Specify environments, data sets, and entry and exit criteria for each plan.
- Link test suites and test cases to maintain traceability.
- Track execution status and defects throughout the lifecycle.
- Agentic AI considerations: Structure metadata to enable AI-driven insights for coverage gaps, risk-based prioritization, and predictive readiness scoring. Include normalized fields for KPIs and tags to support automated dashboards and anomaly detection.

### Recommended fields for Test Plan

The following fields are recommended for the **Test Plan** work item type. They're included by default in the Azure DevOps template for the business process catalog:

|Name  |Description  |
|---------|---------|
|Title|Clear name for the test plan, such as *Regression Test Plan – Sales*.|
|Objectives/Scope|Purpose and boundaries of testing.|
|Environments/Data|Details of environments and data sets used.|
|Acceptance Criteria|Exit conditions for completion.|
|Linked Test Suites|References to associated suites.|
|Schedule|Timeline and milestones.|
|Status|Current state (Draft, Active, Completed).|
|Tags|Labels for capability, phase, or priority classification.|

## Test suite

A test suite is a structured grouping of related test cases within a test plan. Use it to validate a specific feature, requirement, or user story. By using a test suite, you can execute multiple test cases under a common objective. It improves traceability and reporting for quality assurance. Test suites are included by default in the business process catalog template. Use them consistently for organizing test coverage. Future enhancements might include AI-driven recommendations for suite composition and automated sequencing. Modify the test suite only to add organization-specific metadata fields. Don't alter the core workflow.

Here's an example of a test suite: *Sales Order Validation Suite containing tax, pricing, and availability test cases.*

### Success by Design guidelines for Test Suite

- Organize suites by scenario, capability, or feature for clarity.
- Avoid overlapping membership; keep suite contents mutually exclusive.
- Define sequencing and dependencies for execution order.
- Link each Test Suite to its parent Test plan for traceability.
- Agentic AI Considerations: Include structured metadata (scenario, priority, dependencies) to enable AI-driven optimization of suite composition, predictive coverage analysis, and automated execution planning.

### Recommended fields  for Test Suite

The following fields are recommended for the **Test Suite** work item type and included by default in the Azure DevOps template for the business process catalog:

|Name  |Description  |
|---------|---------|
|Title|Clear name for the test suite, such as *Sales Order Validation Suite*.|
|Parent Test Plan|Reference to the overarching test plan.|
|Membership|List of Test Cases included in the suite.|
|Sequence|Execution order and dependencies.|
|Run History|Pass/fail statistics across cycles.|
|Status|Current state (Draft, Active, Completed).|
|Tags|Labels for capability, phase, priority classification.|

## Ticket

A Ticket represents a support or service request raised by a user to address break/fix problems, configuration changes, or assistance related to catalog processes or environments. It facilitates triage, assignment, and resolution tracking under agreed SLAs. No Tickets are included by default in the business process catalog template. Use this work item type consistently for operational support and governance.

Here's an example of a ticket: *Provision access for test users to Dynamics 365 Finance UAT environment. Assign security roles per persona.*

### Success by Design guidelines for Ticket

- Use clear categories, such as access, environment, data, and defect, to speed routing.
- Capture SLA targets and priority. Link to impacted processes or deliverables for traceability.
- Record resolution notes and verification evidence for auditability.
- Maintain consistent naming conventions for easy query and reporting.
- Structure metadata to enable AI-driven triage, prioritization, and SLA compliance checks. Include normalized fields for category, priority, and impacted items so AI can predict delays and recommend escalation paths.

### Recommended fields for Ticket

The following fields are recommended for the **Ticket** work item type. The Azure DevOps template for the business process catalog includes these fields by default:

|Name  |Description  |
|---------|---------|
|Title|Clear description of the request.|
|Requester|Person initiating the ticket.|
|Category/Priority|Type and urgency for routing.|
|SLA|Target response and resolution times.|
|Resolution|Outcome and verification evidence.|
|Status|Current state (New, Active, Resolved, Closed).|

When users create new work items based on this work item type, recommend that they also take the following step:

- Associate the Ticket work item type with relevant backlog levels for visibility.

## Related content

- [Custom work item types for the six levels in the Dynamics 365 business process catalog](about-import-catalog-devops-process-work-item-types.md)  
- [Use the business process catalog as a template in Azure DevOps Services](about-import-catalog-devops.md)  