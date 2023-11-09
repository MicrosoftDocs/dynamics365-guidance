---
title: Pattern - Create a functional and technical design document
description: Read about the template for functional and technical design documents that you can use in Dynamics 365 implementation projects.
ms.date: 09/06/2023
ms.topic: conceptual
author: edupont04
ms.author: nikolaipopov
---

# Pattern: Create a functional and technical design document

***Applies to: Dynamics 365***

This article describes how to use our template to create functional design documents (FDDs) and technical design documents (TDDs) for a Dynamics 365 implementation project. You can also create a combined design document (FDD/TDD) for the entire solution.

The template can help you capture a detailed description of the functional and technical design of an implementation project that involves Dynamics 365 apps. It covers the following areas:

- Scope of the project
- Organization structure and functional responsibilities
- Description of business processes
- Architecture solution design
- Security requirements
- Extra functionality for the solution
- Reporting
- Integration
- Data migration

## Context and issue

In implementations that involve Dynamics 365 apps, the solution must often be extended to meet the business requirements. For example, you add independent software vendor (ISV) solutions, extensions, plugins, new tables, fields, entities, integrations, and so on. You must ensure that the customer and implementation partner agree on the scope and design of the solution before development work begins. The design documents also serve as documentation that supports the application after the solution is developed, and can help create training materials, and so on. For this reason, we recommend that you create design documents that clearly outline all aspects of the solution and are agreed on by all parties.

## When to use this pattern

Use this pattern in the following scenarios:

- As part of the design phase of your project, you must create a deliverable for the functional and technical design of your solution. Learn more in the [Solution: Create a combined FDD/TDD for entire solution](#solution-create-a-combined-fddtdd-for-the-entire-solution) section.
- You have many business requirements and want to create a separate design document for each business process. Learn more in the [Solution: Create a separate FDD/TDD for each business process](#solution-create-a-separate-fddtdd-for-each-business-process) section.

This pattern might not be suitable in the following scenarios:

- Separate teams are working on different lines of businesses, and you must create separate designs for each solution.
- A project has multiple phases, and you must create multiple design documents for each phase or for a minimum viable product (MVP).

## Solution: Create a combined FDD/TDD for the entire solution

As part of the design phase of your Dynamics 365 implementation project, you must create deliverables that document the functional and technical design of your solution. These deliverables are known as *functional design documents* (FDDs) and *technical design documents* (TDDs).

- An FDD describes the design from a business perspective, including business processes, use cases, and requirements. It specifies how the solution must *work*.
- A TDD describes the design from a technical perspective, including the architecture, data model, and system interfaces. It specifies how to *build* the solution.

Both documents are critical for ensuring that your solution is designed and built in a way that meets the business needs and technical requirements. They also serve as a reference for developers, testers, and other stakeholders throughout the project lifecycle.

When you create these deliverables, you're closer to ensuring that the Dynamics 365 implementation project is well planned, documented, and run. As a result, the project delivers a solution that meets the business goals and objectives.

### Complete the combined FDD/TDD

Follow these steps to complete a combined FDD/TDD:

1. Download the template from the [dynamics365patternspractices GitHub repo](https://github.com/microsoft/dynamics365patternspractices/tree/main/templates/implementation-projects).

    The Word template is in the *implementation-projects* folder. It contains no branding or copyright notices.

1. Complete the "Introduction" section.

    This section outlines the structure and purpose of the document. It includes abbreviations that are used throughout the document and an index of symbols that are used in the process flow diagrams. The template includes samples that you can delete or update as appropriate for your project.

1. Complete the "Project overview" section.

    This section includes the scope. If the project is large, you can break down the project scope into smaller subsections. The template includes a sample that shows how to break down the project scope by department. However, you can use workstreams, business units, or companies, for example, depending on the size and complexity of your project.

1. Complete the "Organization structure and functional responsibilities in the solution" section.

    We recommend that you include an organizational diagram like the sample that is included in the template. Then use the subsections to describe the organization structure.

1. Complete the "Description of business processes" section.

    This section first outlines the business processes. For each business process, there is then a separate subsection that includes a flow diagram and text to outline flow and requirements.
    
    For example, when a flowchart describes a process that involves different people, departments, or functional areas, it's more difficult to keep track of who is responsible for each step. An alternative way to track this information and analyze the number of times that a process is "handed over" to different people is to divide the flowchart into columns. In the heading of each column, indicate the name of the person or function that is involved in the process. Then, each time that a person or function performs an action, show it in the corresponding column. Use cross-functional flowcharts to show the relationship between a business process and the functional units (such as departments) that are responsible for that process. Bands represent the functional units. Shapes that represent steps in the process are then put in the bands that correspond to the functional units that are responsible for those steps.

1. Complete the "Architecture solution design" section.

    This section includes details of the data architecture. Make sure that you cover the following subsections:

    - Key design decisions
    - Scalability and performance considerations
    - Usability and user interface considerations
    - Optional: A section for future considerations

    The template includes a sample of some Dataverse out-of-band tables for customer engagement solutions.

1. Complete the "Security requirements" section.

    This section should outline any built-in security that you plan to apply. It should also provide details about any custom security roles that you define for the solution. Each custom role should have a separate subsection that outlines the full requirements.

1. Complete the "Additional functionality" section.

    The template includes some sample subsections. You can add more subsections if the project requires them. You can also remove any subsections that aren't relevant. This section can include more nonfunctional requirements, add-ins, ISV solutions, other or advanced functionality that must be specified or configured separately.

1. Complete the "Reporting and analytics" section.

    This section outlines the reporting and analytics approach. Include your approach for exporting data to external data warehouses, such as Azure Synapse Link or the bring your own database (BYOD) option for finance and operations apps. Also provide details about each custom report and dashboard that you plan to build. Include the security requirements for the custom reports and dashboards.

1. Complete the "Integration" section.

    This section outlines the details of the integration architecture, including the design of each interface.

1. Complete the "Migration" section.

    This section outlines the details of the migration of data. It's broken down into several subsections, one for each type of data that must be migrated. If data is being migrated from multiple sources, consider including the field-level mapping for each source.

### Issues and considerations for a combined document

Consider the following points when you're deciding how to implement this pattern:

- Creation of a combined FDD/TDD for the entire solution can be a time-consuming process, especially for large and complex projects. Therefore, it's important to allocate enough time and resources to ensure that the document is thorough and accurate.
- It can be challenging to maintain consistency between the FDD and TDD sections, because the functional and technical requirements might overlap or contradict each other. It's essential to have a clear and defined process for reconciling any discrepancies between the two documents.
- The combined FDD/TDD can become outdated if it isn't properly maintained and updated throughout the project lifecycle. It's crucial to establish a process for keeping the document up to date as changes occur, and for adding new requirements as they are identified.
- Because the combined FDD/TDD covers the entire solution, it can be challenging to track progress and assign responsibilities for individual requirements. It's important to establish a clear process for tracking progress and ensuring that team members are aware of their responsibilities for each requirement.
- It's important to ensure that the combined FDD/TDD is written in language that all stakeholders, including both technical and nontechnical team members, can understand. It's essential to strike a balance between technical accuracy and accessibility.

## Solution: Create a separate FDD/TDD for each business process

When you have many different requirements across the business processes that the solution supports, it's essential to keep track of all of them in a structured and organized manner. One approach is to create separate design documents for each business process. This approach ensures that each process is documented in detail, and that specific design considerations and technical specifications are included. It also allows for easier tracking of progress and helps prevent confusion and overlap between requirements.

By creating separate design documents, you can also assign specific team members to each requirement and track their progress independently. This approach is especially important for larger projects where multiple teams are involved. Additionally, separate design documents can help with risk management, by identifying potential issues or conflicts early in the project.

When you create these design documents, follow a consistent format, and include all necessary information, such as the following list:

- Requirement description
- Design considerations
- Technical specifications
- Acceptance criteria

A standardized template for these documents can help ensure consistency and make it easier to compare and review requirements across the project.

Overall, the creation of separate design documents for each business requirement can be a valuable tool for managing large projects and ensuring that all requirements are appropriately documented and tracked.

### Complete each FDD/TDD

Follow these steps to complete the FDD/TDD for each requirement:

1. Download the template from the [dynamics365patternspractices GitHub repo](https://github.com/microsoft/dynamics365patternspractices/tree/main/templates/implementation-projects).

    The Word template is in the *implementation-projects* folder. It contains no branding or copyright notices. It's the same template that is described in the [Solution: Create a combined FDD/TDD for the entire solution](#solution-create-a-combined-fddtdd-for-the-entire-solution) section.

1. Complete the "Introduction" section.
1. Complete the "Project overview" section.
1. Complete the "Organization structure and functional responsibilities in the solution" section.
1. Complete the "Description of business processes" section.
1. Complete the "Architecture solution design" section.
1. Complete the "Security requirements" section.
1. Complete the "Additional functionality" section.
1. Complete the "Reporting and analytics" section.
1. Complete the "Integration" section.
1. Complete the "Migration" section.

### Issues and considerations for multiple documents

Consider the following points when you're deciding how to implement this pattern:

- When you create separate design documents for each business process, extra time and resources might be required to manage and track each document. It's important to have a clear process for organizing and accessing these documents, to help prevent confusion or duplication of effort.
- Requirements might overlap or depend on each other in ways that aren't immediately apparent when each process is considered in isolation. It's important to review and validate the requirements holistically, to ensure that they work together as intended.
- When you create standardized templates for these documents, it's important to ensure that they are flexible enough to accommodate variations in requirements and design considerations. It might be necessary to create multiple templates or variations to account for different types of requirements or design approaches.
- Communication and collaboration between team members are critical when you create and manage separate design documents. It's important to establish clear expectations about how team members should communicate and share information. In this way, you ensure that all requirements are addressed, and that any issues are identified and promptly addressed.
- It's important to ensure that the FDD/TDD documents are kept up to date throughout the project lifecycle. As requirements change or evolve, the design documents should be updated to reflect those changes and ensure that everyone is working from the same information.

Overall, although the creation of separate design documents for each business requirement can be a valuable tool, it's important to approach this process thoughtfully and to have a clear plan for managing and tracking the documents throughout the project.

## Related resources

Use the following resources to learn more.

- [Introduction to Success by Design](../implementation-guide/success-by-design.md)
- [Overview of business processes in Dynamics 365](../business-processes/index.yml)
- [Security strategy overview](../implementation-guide/security.md)

## Next steps

Learn more about the context for FDDs and TDDs in the following articles.

- [Solution architecture design pillars](../implementation-guide/solution-architecture-design-pillars.md)
- [Process-focused solution](../implementation-guide/process-focused-solution.md)
- [The Fit-to-standard and Fit-gap analysis](../implementation-guide/process-focused-solution-fit-to-standard-fit-gap-analysis.md)

<!--## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Accounts payable, Accounts receivable, Administrative, Audit, Customer services, Engineering, Finance, Human Resources, IT, Marketing, Merchandising, Operations, Production, Project Management, Purchasing, Retail store operations, Sales, Service operations, Transportation, Treasury, Warehouse

*Products:* Dynamics 365-->
