---
title: Create a functional and technical design document
description: Learn how to use our template to document the functional and technical design of your Dynamics 365 solution.
ms.date: 01/11/2024
ms.topic: conceptual
author: edupont04
ms.author: nikolaipopov
ms.custom:
  - ai-seo-date: 01/11/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Create a functional and technical design document

***Applies to: Dynamics 365***

This article shows you how to use our template to document the functional and technical design of your Dynamics 365 solution. You can create a combined design document for the whole solution or separate design documents for each business process.

The template helps you capture a detailed description of the functional and technical design of your Dynamics 365 solution. It covers these areas:

- Scope of the project
- Organization structure and functional responsibilities
- Description of business processes
- Architecture solution design
- Security requirements
- Extra functionality for the solution
- Reporting
- Integration
- Data migration

## Problem and context

In Dynamics 365 solutions, you often need to extend the solution to meet the business requirements. For example, you add components like independent software vendor (ISV) solutions, extensions, plug-ins, new tables, fields, entities, and integrations. You need to make sure that the customer and implementation partner agree on the scope and design of the solution before you start developing. The design documents also help you create training materials and support the solution after you develop it. For these reasons, we recommend that you create design documents that clearly outline all aspects of the solution and are agreed on by all parties.

## When to use this pattern

Use this pattern in these scenarios:

- As part of the design phase of your project, you need to create a deliverable for the functional and technical design of your solution. To learn more, see the [Solution: Create a combined design document for the whole solution](#solution-create-a-combined-design-document-for-the-whole-solution) section.
- You have many business requirements and want to create a separate design document for each business process. To learn more, see the [Solution: Create a separate design document for each business process](#solution-create-a-separate-design-document-for-each-business-process) section.

This pattern might not work in these scenarios:

- Separate teams are working on different lines of businesses, and you need to create separate designs for each solution.
- A project has multiple phases, and you need to create multiple design documents for each phase or for a minimum viable product (MVP).

## Solution: Create a combined design document for the whole solution

As part of the design phase of your Dynamics 365 project, you need to create deliverables that document the functional and technical design of your solution. These deliverables are called *functional design documents* (FDDs) and *technical design documents* (TDDs).

- An FDD describes the design from a business perspective, including business processes, use cases, and requirements. It tells you how the solution should *work*.
- A TDD describes the design from a technical perspective, including the architecture, data model, and system interfaces. It tells you how to *build* the solution.

Both documents are important for making sure that your solution is designed and built to meet the business needs and technical requirements. They also serve as a reference for developers, testers, and other stakeholders throughout the project lifecycle.

When you create these deliverables, you help make sure that the Dynamics 365 project is well planned, documented, and run. As a result, the project delivers a solution that meets the business goals and objectives.

### Complete the combined design document

Follow these steps to complete a combined design document (an FDD/TDD):

1. Download the template from the [dynamics365patternspractices GitHub repo](https://github.com/microsoft/dynamics365patternspractices/tree/main/templates/implementation-projects).

    The Word template is in the *implementation-projects* folder. It doesn't have any branding or copyright notices.

1. Complete the "Introduction" section.

    This section explains the structure and purpose of the document. It includes abbreviations that are used throughout the document and an index of symbols that are used in the process flow diagrams. The template includes samples that you can delete or update as needed for your project.

1. Complete the "Project overview" section.

    This section includes the scope. If the project is large, you can break down the project scope into smaller subsections. The template includes a sample that shows how to break down the project scope by department. You can also use workstreams, business units, or companies, depending on the size and complexity of your project.

1. Complete the "Organization structure and functional responsibilities in the solution" section.

    We recommend that you include an organizational diagram like the sample in the template. Then use the subsections to describe the organization structure.

1. Complete the "Description of business processes" section.

    This section first outlines the business processes. For each business process, there is then a separate subsection that includes a flow diagram and text to outline flow and requirements.

    For example, when a flowchart describes a process that involves different people, departments, or functional areas, it can be hard to keep track of who is responsible for each step. Another way to track this information and analyze how often a process is "handed over" to different people is to divide the flowchart into columns. In the heading of each column, show the name of the person or function that's involved in the process. Then, each time that a person or function does an action, show it in the corresponding column. Use cross-functional flowcharts to show the relationship between a business process and the functional units (such as departments) that are responsible for that process. Bands represent the functional units. Shapes that represent steps in the process are then put in the bands that match the functional units that are responsible for those steps.

1. Complete the "Architecture solution design" section.

    This section includes details of the data architecture. Make sure that you cover these subsections:

    - Key design decisions
    - Scalability and performance considerations
    - Usability and user interface considerations
    - Optional: A section for future considerations

    The template includes a sample of some Dataverse out-of-band tables for customer engagement solutions.

1. Complete the "Security requirements" section.

    This section should outline any built-in security that you plan to apply. It should also give details about any custom security roles that you define for the solution. Each custom role should have a separate subsection that outlines the full requirements.

1. Complete the "Extra functionality" section.

    The template includes some sample subsections. You can add more subsections if the project needs them. You can also remove any subsections that aren't relevant. This section can include more nonfunctional requirements, add-ins, ISV solutions, other or advanced functionality that needs to be specified or configured separately.

1. Complete the "Reporting and analytics" section.

    This section outlines the reporting and analytics approach. Include your approach for exporting data to external data warehouses, such as Azure Synapse Link or the bring your own database (BYOD) option for finance and operations apps. Also give details about each custom report and dashboard that you plan to build. Include the security requirements for the custom reports and dashboards.

1. Complete the "Integration" section.

    This section outlines the details of the integration architecture, including the design of each interface.

1. Complete the "Migration" section.

    This section outlines the details of the data migration. It's broken down into several subsections, one for each type of data that needs to be migrated. If data is being migrated from multiple sources, consider including the field-level mapping for each source.

### Issues and considerations for a combined FDD/TDD

Consider these points when you're deciding how to use this pattern:

- Creating a combined design document for the whole solution can take a lot of time, especially for large and complex projects. So it's important to plan enough time and resources to make sure that the document is thorough and accurate.

- It can be hard to keep the design document sections consistent, because the functional and technical requirements might overlap or contradict each other. It's important to have a clear and defined process for resolving any differences between the two documents.

- The combined design document can become outdated if it isn't properly maintained and updated throughout the project lifecycle. It's important to have a process for keeping the document up to date as changes happen, and for adding new requirements as they're identified.

- Because the combined design document covers the whole solution, it can be hard to track progress and assign responsibilities for individual requirements. It's important to have a clear process for tracking progress and making sure that team members know their responsibilities for each requirement.

- It's important to make sure that the combined design document is written in language that all stakeholders, including both technical and nontechnical team members, can understand. It's important to balance technical accuracy and accessibility.

## Solution: Create a separate design document for each business process

When you have many different requirements across the business processes that the solution supports, it's important to keep track of all of them in a structured and organized way. One approach is to create separate design documents for each business process. This approach makes sure that each process is documented in detail, and that specific design considerations and technical specifications are included. It also allows for easier tracking of progress and helps prevent confusion and overlap between requirements.

By creating separate design documents, you can also assign specific team members to each requirement and track their progress independently. This approach is especially important for larger projects where multiple teams are involved. Additionally, separate design documents can help with risk management, by identifying potential issues or conflicts early in the project.

When you create these design documents, follow a consistent format, and include all necessary information, such as the following list:

- Requirement description
- Design considerations
- Technical specifications
- Acceptance criteria

A standardized template for these documents can help ensure consistency and make it easier to compare and review requirements across the project.

Overall, the creation of separate design documents for each business requirement can be a valuable tool for managing large projects and ensuring that all requirements are appropriately documented and tracked.

### Complete each design document

Follow these steps to complete the FDD/TDD for each requirement:

1. Download the template from the [dynamics365patternspractices GitHub repo](https://github.com/microsoft/dynamics365patternspractices/tree/main/templates/implementation-projects).

    The Word template is in the *implementation-projects* folder. It's the same template that's described in the [Solution: Create a combined design document for the entire solution](#solution-create-a-combined-design-document-for-the-whole-solution) section.

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

Consider these points when you're deciding how to use this pattern:

- When you create separate design documents for each business process, extra time and resources might be needed to manage and track each document. It's important to have a clear process for organizing and accessing these documents, to help prevent confusion or duplication of effort.

- Requirements might overlap or depend on each other in ways that aren't clear when each process is considered separately. It's important to review and validate the requirements as a whole, to make sure that they work together as intended.

- When you create standardized templates for these documents, it's important to make sure that they're flexible enough to accommodate variations in requirements and design considerations. You might need to create multiple templates or variations to account for different types of requirements or design approaches.

- Communication and collaboration between team members are critical when you create and manage separate design documents. It's important to set clear expectations about how team members should communicate and share information. This way, you make sure that all requirements are addressed, and that any issues are identified and resolved quickly.

- It's important to make sure that the design documents are kept up to date throughout the project lifecycle. As requirements change or evolve, the design documents should be updated to reflect those changes and make sure that everyone is working from the same information.

Overall, although the creation of separate design documents for each business requirement can be a valuable tool, it's important to approach this process carefully and to have a clear plan for managing and tracking the documents throughout the project.

## Next steps

- [How to use the solution design pillars](../implementation-guide/solution-architecture-design-pillars.md)
- [How to create a process-focused solution](../implementation-guide/process-focused-solution.md)
- [How to do a fit-to-standard and fit-gap analysis](../implementation-guide/process-focused-solution-fit-to-standard-fit-gap-analysis.md)

### See also

- [Introduction to Success by Design](../implementation-guide/success-by-design.md)
- [Overview of business processes in Dynamics 365](../business-processes/index.yml)
- [Security strategy overview](../implementation-guide/security.md)
