---
title: Custom work item type for business process-related tasks
description: Track your implementation of business process scenarios in your Dynamics 365 implementation with custom work item types for the six levels in the business process catalog in Azure DevOps.
author: edupont04
ms.author: edupont
ms.topic: concept-article 
ms.date: 12/10/2025
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-description
  - ai-seo-date:12/11/2025
#CustomerIntent: As a <type of user>, I want <what?> so that <why?>.
---
# Custom work item types for the six levels in the Dynamics 365 business process catalog

To use the Dynamics 365 business process catalog as a starting point for an implementation project that you manage in Azure DevOps, you must create custom work item types. Microsoft provides a template that you can import into Azure DevOps, which creates the work item types for you. This article describes the custom work item types that are in the template for the six levels in the business process catalog. The Azure DevOps template is designed to follow the Success by Design framework with a process-focused approach.

Learn more about using the business process catalog with Azure DevOps at [Use the business process catalog as a template in Azure DevOps Services](about-import-catalog-devops.md).

## The What of an implementation project

The business process catalog represents the *what* of a Dynamics 365 implementation. It provides a structured hierarchy of processes that define the scope of work for a project. When you import the customized template into Azure DevOps, you get work item types for the six levels in the business process catalog that support a connected *tree*. This tree is designed to ensure clarity and consistency across implementations by organizing processes into logical levels. At its core, the catalog helps teams understand business operations before diving into system configuration or customization. It supports a fit-to-standard approach that accelerates delivery and reduces risk.

Learn more at [Overview of the business process catalog levels](about-catalog-levels.md).  

## Levels in the catalog

The tree is organized into six levels with increasing granularity:

- **Level 1 – end-to-end processes:** Broad business capabilities such as [Order to Cash](order-to-cash-overview.md) or [Source to Pay](source-to-pay-overview.md).

- **Level 2 – process areas:** Logical groupings within an end-to-end process, such as*Manage Sales Orders*.

- **Level 3 – business processes:** Specific functions that describe what the business does, system-agnostic and reusable across industries.

- **Level 4 – scenarios or patterns:** Variations of processes for different industries or solution approaches.

- **Level 5 – system processes:** Detailed steps tied to specific forms or pages in Dynamics 365.

- **Level 6 – test cases:** Actions for validating functionality during testing phases.

This layered structure ensures that projects can start at a high level and drill down to detailed, actionable items as needed. Learn more at [Overview of the business process catalog levels](about-catalog-levels.md).  

## Using the tree in Azure DevOps

In Azure DevOps, you implement the catalog tree through custom work item types that mirror these levels. Each level corresponds to a work item type, such as **end-to-end**, **Process Area**, **Business Process**, and **Scenario**, and links hierarchically to maintain traceability. This structure enables teams to manage scope, track progress, and align deliverables with business objectives. By importing the catalog into Azure DevOps, your organization gains a standardized framework for planning, fit/gap analysis, and execution. It also supports integration with testing tools like RSAT, ensuring that processes documented in the tree flow seamlessly into test cases and quality assurance activities.

One of the primary functions of this tree is to define project scope. By mapping all business processes and their variations into a structured hierarchy, the catalog provides a clear view of what is in scope for the implementation. This view helps stakeholders agree on boundaries early in the project, reduces ambiguity, and ensures that any gaps or enhancements are identified and managed systematically. Scope definition at this level also supports governance and change control, as you can trace any additions or modifications back to specific processes and their related work items.

## Benefits

- Clear scope definition  

  Provides a single source of truth for what is included in the project, reducing misunderstandings and scope creep.

- Traceability and governance  

  Links every process to related work items, deliverables, and test cases, enabling better oversight and compliance.

- Accelerated fit/gap analysis  

  Helps teams quickly identify standard versus custom requirements, improving decision-making and reducing delays.

- Improved quality assurance  

  Ensures that test cases align with documented processes, supporting robust validation and minimizing defects.

- Consistency across projects  

  Establishes a repeatable framework that you can apply to multiple implementations, promoting best practices and efficiency.

## End-to-end process

The top-level node of the business process catalog represents a complete business capability that spans multiple functional domains, systems, and stakeholders. It provides the highest-level context for related Process Areas and clarifies business outcomes, boundaries, and dependencies.

The current version of the business process catalog contains 15 end-to-end processes. Learn more at [Overview of the business process catalog levels](about-catalog-levels.md).

> [!IMPORTANT]
> Don't add new end-to-end processes as part of your implementation project. Instead, align to these existing processes to maintain consistency and leverage standard guidance. You can rename existing processes.

### Scoping the end-to-end processes

Scope the relevant end-to-end processes early in the implementation project, preferably during the sales and pre-sales phases before an Azure DevOps project even exists. This early alignment ensures clarity on project boundaries, accelerates fit/gap analysis, and supports accurate solution design.

By default, all end-to-end process work items have the **Scope** field set to **10-Unspecified**. Teams can update this field to one of three values:

|Field value  |Description  |
|---------|---------|
|**20-In Scope** |The process is part of the implementation. |
|**30-Out of Scope** |The process exists but isn't implemented.|
|**40-Not Applicable**|The business doesn't perform this process at all.  |

For example, a retailer might mark the entire *Plan to Produce* process as **40-Not Applicable** because they don't manufacture products.

[*Administer to Operate*](administer-to-operate-overview.md) is a critical end-to-end process that should be in scope for every Dynamics 365 project. This process represents the IT and operational backbone of an organization, encompassing activities such as environment management, security administration, monitoring, and compliance. It's where the entire [Success by Design framework](../implementation-guide/success-by-design.md) is embedded, particularly under the *Implement Solutions* area. These activities ensure that the solution is deployed, governed, and maintained according to best practices. Treating *Administer to Operate* as a formal process guarantees that technical and operational readiness isn't overlooked, reducing risk and enabling sustainable operations post go-live.

## Process area

A *process area* is the second level in the business process catalog hierarchy. It represents a logical grouping of related activities within an end-to-end process, making the catalog easier to navigate and consume. Each process area contributes to the overall objective of the end-to-end process and often aligns loosely with certain roles or personas in the organization, helping clarify accountability.

### Standard process areas

The catalog includes more than 90 predefined process areas across the 15 end-to-end processes. These areas cover common business functions and you should use them as-is for consistency.

> [!IMPORTANT]
> Don't create new process areas unless the Business Process Excellence team approves. Aligning to the standard set ensures governance and compatibility with Success by Design principles.

#### Strategy areas

Every end-to-end process includes a strategy area that focuses on planning, setup, and configuration activities. While these activities might seem technical, they're true business processes because they have defined inputs, outputs, and governance requirements. For example, setting up financial dimensions or defining security roles involves decision-making, approvals, and alignment with organizational policies. These activities aren't ad hoc—they follow structured steps, require stakeholder involvement, and impact downstream processes.

Moreover, many strategy-related processes occur only during major technology implementations or transformations, making them critical for success. Without proper governance and controls, misconfigured setups can lead to compliance risks, operational inefficiencies, and costly rework. Treating these activities as formal processes ensures accountability, traceability, and alignment with business objectives.

#### Analytics areas

Similarly, each end-to-end process includes an analytics area that represents activities performed after execution to measure performance, identify trends, and inform decisions. These processes are cyclical: insights from analytics often trigger changes in earlier processes, such as adjusting procurement strategies based on spend analysis or refining pricing models based on sales performance.

Analytics processes have clear inputs (transactional data), defined steps (aggregation, reporting, interpretation), and outputs (recommendations, dashboards, KPIs). They're essential for continuous improvement and strategic planning. By recognizing analytics as a formal process, organizations can ensure these activities are governed, documented, and linked to measurable outcomes rather than treated as informal reporting tasks.

### Scoping the process areas

Scope the process areas early in the project lifecycle, ideally during discovery workshops and fit/gap analysis. This approach ensures clarity on which functional areas are included and helps prioritize solution design. Like end-to-end processes, the **Scope** field defaults to 10-Unspecified and you can update it to:

|Field value  |Description  |
|---------|---------|
|**20-In Scope** |The process area is part of the implementation. |
|**30-Out of Scope** |The process area exists but isn't part of the implementation.|
|**40-Not Applicable**|The business doesn't perform this process area.  |

Within *Administer to Operate*, the [Implement Solutions process area](administer-to-operate-implement-solutions.md) plays a pivotal role in project success. It includes tasks such as environment provisioning, deployment planning, and configuration management—all of which require structured governance. These tasks aren't optional technical steps; they're business-critical processes with defined inputs, outputs, and dependencies. Properly managing this area ensures alignment with organizational policies, compliance standards, and performance objectives. By documenting and scoping these areas early, teams can avoid last-minute surprises and maintain control throughout the implementation lifecycle.

## Process

A *business process* is the third level in the business process catalog hierarchy, and the corresponding work item type is a **Process**. It represents a specific function or activity that the business performs to achieve a defined outcome. Unlike end-to-end processes or process areas, Level 3 processes are more granular and actionable, making them essential for fit/gap analysis and solution design. These processes are system-agnostic, meaning they describe what the business does rather than how a specific application performs the task. This system-agnostic approach ensures they can be reused across industries and technologies.

For example, in the *Manage Sales Orders* process area, one business process is *Validate Order Pricing*, which includes steps for checking discounts, taxes, and compliance before confirming an order.

Business processes form the foundation for **fit/gap analysis** because they define what the business needs before mapping to system capabilities. They enable traceability from high-level objectives down to detailed requirements, ensuring that every customization or enhancement is justified. By documenting these processes, teams can link them to test cases, KPIs, and compliance checks, creating a closed loop for governance and quality assurance.

In Azure DevOps, you can link business processes directly to test cases and test plans, enabling automated validation. This approach ensures that every scoped process is tested against its intended outcome, reducing risk and improving confidence in the solution.

### Standard business processes

The catalog includes over 600 predefined business processes across all end-to-end processes and process areas. These processes cover common operational activities and you should use them as-is for consistency.

> [!IMPORTANT]
> Don't create new business processes unless absolutely necessary. When you need new processes, submit them to the Business Process Excellence team at Microsoft for evaluation and possible addition to the standard catalog. You can submit requests for changes to the catalog at [https://aka.ms/businessprocesscatalogrequests](https://aka.ms/businessprocesscatalogrequests]). Aligning to the standard set ensures governance, accelerates implementation, and supports Success by Design principles.

### Key fields on the processes

The **Process** work item type has some fields that you should give special attention to. The Azure DevOps template arranges these fields into three key field groups:

1. Business Assignments

    - **Business Process Owner** – Accountable for the process outcome.

    - **Workstream Lead** – Oversees implementation activities for the process.

    - **Subject Matter Expert (SME)** – Provides detailed knowledge and validation.

1. Solution Details

    - **Fit/Gap Status** – Indicates whether the process is supported out of the box or requires customization.

    - **Gap Solution Approach** – Documents how gaps are addressed (for example, configuration, extension, ISV solution).

1. Planning Details

    - **Baseline Complexity** – Standard complexity rating for the process.

    - **Estimated Complexity** – Adjusted complexity based on project specifics.

    - **Estimate** – Effort required to implement the process (hours or story points).

    - **Estimated Project Impact** – Qualitative measure of how critical this process is to project success.

### Success by Design guidelines for business processes

- Always start with the assumption that the standard Dynamics 365 capabilities meet business needs. Consider customizations only when a clear business value and compliance requirement justify deviation.

- For each business process, document whether it's supported out-of-the-box (Fit) or requires a solution approach (Gap). Use the Fit/Gap Status and Gap Solution Approach fields to maintain transparency and traceability.

- Push back on unnecessary extensions by validating against KPIs, regulatory requirements, and strategic objectives. Encourage configuration over code wherever possible.

- Document a rationale tied to measurable outcomes for every gap. Avoid "nice-to-have" customizations that increase complexity without delivering tangible benefits.

- Link gaps and their solutions back to the business process and higher-level objectives. This approach supports governance and change control throughout the project lifecycle.

- Connect business processes to test cases in Azure DevOps to validate that fit/gap decisions are implemented correctly and meet business requirements.

## Scenario

A *Scenario* is the fourth level in the business process catalog hierarchy and is always product-specific. It represents a concrete way of completing a Level 3 business process by using a specific Microsoft product or feature. If multiple products or features support the same business process, the catalog includes one scenario for each product-feature combination. This approach ensures clarity on how the solution is implemented and provides flexibility for customers and partners to choose the best fit.

Scenarios are the most common level for customers and partners to extend with industry-specific or organization-specific requirements. They allow tailoring without altering higher-level catalog nodes, maintaining governance while enabling innovation. Adding an agent to support a business process, such as an AI-driven pricing assistant, also occurs at this level.

### Key fields on the scenarios

Similar to processes, give special consideration to the following fields for the scenario work items. The Azure DevOps template arranges these fields into three key field groups:

1. Business Assignments

    - **Business Process Owner** – Accountable for the process outcome.

    - **Workstream Lead** – Oversees implementation activities for the process.

    - **Subject Matter Expert (SME)** – Provides detailed knowledge and validation.

1. Solution Details

    - **Fit/Gap Status** – Indicates whether the process is supported out of the box or requires customization.

    - **Gap Solution Approach** – Documents how gaps are addressed (for example, configuration, extension, ISV solution).

1. Planning Details

    - **Baseline Complexity** – Standard complexity rating for the process.

    - **Estimated Complexity** – Adjusted complexity based on project specifics.

    - **Estimate** – Effort required to implement the process (hours or story points).

    - **Estimated Project Impact** – Qualitative measure of how critical this process is to project success.

### Scoping scenarios

Scope scenarios during solution architecture and design workshops, after you confirm the relevant business processes. Scoping scenarios is critical for defining how the system meets specific requirements and for estimating effort accurately.

### Success by Design guidelines for scenarios

- Extend at the scenario level for industry or company-specific needs. Avoid altering higher-level nodes.

- Clearly document product and feature details, including any AI agents introduced for automation or decision support.

- Validate scenarios against fit-to-standard principles. Prefer configuration and standard features before custom code.

- Link scenarios to KPIs and compliance requirements to justify any extensions.

- For agent scenarios:

  - Define the agent's role, inputs, and outputs.

  - Ensure responsible AI principles are applied (transparency, fairness, security).

  - Document governance for agent lifecycle (training, monitoring, updates).

## System process

A *system process* is the fifth level in the business process catalog hierarchy. It represents high-level steps tied to specific forms, pages, or system components in Dynamics 365 or related Microsoft technologies. These steps aren't detailed click-by-click instructions but provide enough granularity to connect business requirements to technical execution. System processes are product-specific, unlike business processes that are system-agnostic, and they focus on major actions rather than UI details. Currently, system processes are available for some end-to-end processes. Future releases expand coverage to ensure full alignment across the catalog.

System processes help ensure:

- **Traceability:** Linking business requirements to technical execution.

- **Testing integration:** Connecting to test cases for validation and automation.

- **Governance:** Providing transparency for compliance and audit requirements.

- **Future readiness:** Supporting agent-driven automation and RSAT integration.

### Success by Design guidelines for system processes

- Document every system process that supports a scenario to ensure traceability.

- Include form and page references and configuration details for clarity.

- Validate against fit-to-standard principles—avoid unnecessary customizations.

- Link system processes to test cases for automated validation.

- For agent-driven automation, define governance for lifecycle management and monitoring.

## Test case

A *test case* is the sixth level in the business process catalog hierarchy. It represents a series of specific validation steps or actions you perform within a system process to confirm that the system behaves as expected. Test cases can be manual or automated, depending on the complexity, frequency, and criticality of the process you're validating. Use manual test cases for exploratory or one-time validations or configurations that don't change frequently. Use automated test cases for business critical, regression, performance, and repetitive scenarios.

There are different types of test cases, including the following list:

- **Functional test cases** – Validate that a feature or process works as intended.

- **Integration test cases** – Ensure that multiple components or systems interact correctly.

- **Performance test cases** – Measure system responsiveness and scalability under load.

- **Security test cases** – Validate access controls, data protection, and compliance.

- **AI/Agent evaluation** – Assess accuracy, fairness, explainability, and reliability of AI-driven processes or agents.

This diversity ensures comprehensive coverage of both deterministic system behaviors and probabilistic AI outcomes, supporting robust quality assurance and compliance.

Test cases are critical in any Dynamics 365 deployment as they help you achieve the following goals:

- **Functional assurance:** Validate that configurations and customizations deliver the intended outcome.

- **AI/Agent evaluation:** For agent-driven scenarios, test cases include evaluation metrics and benchmarks to measure performance, fairness, and reliability across versions.

- **Continuous monitoring:** AI agents require ongoing evaluation because their behavior can change over time. Test cases provide a structured way to benchmark and monitor these changes.

> [!NOTE]
> Currently, test cases are available for selected end-to-end processes. Future releases expand coverage to ensure full alignment across the catalog.

### Key fields on the Test Case work item

- **Steps** – Detailed click-by-click actions for execution (including AI-generated steps where applicable).

- **Expected Result** – Criteria for success.

- **Automation Indicator** – Indicates if the test is to be conducted manually, if automation is planned, or if it is fully automated.

- **Evaluation Metrics** (for AI/agents) – Accuracy, latency, fairness, and compliance checks.

- **Run History** – Pass/fail statistics across cycles.

- **Status** – Draft, Active, Completed.

### Scoping test cases

Create test cases during the solution design and testing phases, after you finalize the system processes. For AI/agents, define evaluation test cases early and update them continuously as models evolve.

### Success by Design guidelines for test cases

- **Align Test Cases to Business Value:** Each test case should validate a critical business outcome or compliance requirement.

- **Leverage Automation:** Use RSAT for deterministic tests and Leapwork or similar tools for complex workflows.

- **For AI/Agents:**

  - Define evaluation criteria beyond functional correctness (for example, fairness, explainability, performance).

  - Include both **offline evaluations** (benchmarking against historical data) and **online monitoring** (continuous performance tracking).

  - Document governance for agent lifecycle, including retraining and version comparisons.

- **Maintain Traceability:** Link test cases to system processes, scenarios, and business processes for full visibility.

- **Plan for Scalability:** Use test suites and plans in Azure DevOps to organize large volumes of test cases efficiently.




OLD

## Prerequisites

Before you create the work item type described in this article, make sure you have the following prerequisites.

- [!INCLUDE [daf-bus-proces-download](~/../shared-content/shared/guidance-includes/daf-bus-proces-download.md)]
- Create a project in Azure DevOps. Learn more at [Create a project in Azure DevOps](/azure/devops/organizations/projects/create-project?view=azure-devops&preserve-view=true&tabs=browser) and [Agile process work item types](/azure/devops/boards/work-items/guidance/agile-process?view=azure-devops&preserve-view=true).  
- Create the required custom work item types, including the **End to end** type that we describe in this article.

## Required fields for the work item types

The **End-to-end**, **Process area**, **Process**, and **Scenario** work item types group all work items related to Level 1, 2, 3, and 4 in the catalog. Our template creates one work item for each of the entries.  

The following table outlines the required fields on these work item types.

|Field |Description|
|---------|----------|
|**Description** |Default field.|
|**Process Sequence ID** |Custom field. Add this field as a custom **Text (single line)** field, so that users can see the Microsoft assigned ID for the process. Don't modify or change the process sequence ID provided by Microsoft. When you need to add a custom process that isn't included in the standard catalog, suffix the ID with custom letters for your organization to ensure there's no conflict in uptaking future releases of the catalog. Learn more at [Add a custom field](/azure/devops/organizations/settings/work/customize-process-field?view=azure-devops&preserve-view=true#add-a-custom-field).|
|**Priority** |Default field.|
|**Risk** |Default field.|
|**Business value** |Default field.|
|**Time Criticality** |Default field.|
|**Effort** |Default field.|
|**Update comments** | Custom field.|

> [!NOTE]
> The business process catalog that Microsoft publishes has other fields for these work item types that you can optionally use. Learn more at [Review the optional fields in the business process catalog](about-import-catalog-devops.md#review-the-optional-fields-in-the-business-process-catalog).

### Required field for the Process area work item type

The **Process area** work item type groups all work items related to *business process areas* that are Level 2 in the catalog.  

The following table outlines the required field that this work item type adds to the other required fields outlined in the [Required fields for the work item types](#required-fields-for-the-work-item-types) section.

|Field |Description|
|---------|----------|
|**Associated Key Performance Indicators** |Custom field. It contains a list of key performance indicators that's formatted as HTML.|

## Related content

Find the related articles here:

- [Use the business process catalog as a template in Azure DevOps Services](about-import-catalog-devops.md)  
<!-- - [Custom work item type for configuration deliverables in the Dynamics 365 business process catalog](about-import-catalog-devops-configuration-deliverable-work-item-type.md)   -->

<!-- ## Next step

Learn about the next level of work item.

> [!div class="nextstepaction"]
> [Custom work item type for configuration deliverables in the Dynamics 365 business process catalog](about-import-catalog-devops-configuration-deliverable-work-item-type.md) -->
