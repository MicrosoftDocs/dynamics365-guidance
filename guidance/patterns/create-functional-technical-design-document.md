---
title: Pattern Create a functional and technical design document
description: Read about the template for functional and technical design documents that you can use in Dynamics 365 implementation projects.
ms.date: 09/06/2023
ms.topic: conceptual
author: edupont04
ms.author: nikolaipopov
---

# Pattern: Create a functional and technical design document

***Applies to: Dynamics 365***

This article describes how to use our template for functional or technical design documents (FDD/TDD) that you can use to create a combined design document for a Dynamics 365 implementation project.  

The template can help you capture a detailed description of the functional and technical design of an implementation project with Dynamics 365 apps. It covers the following areas:

- The scope of the project  
- Organization structure and functional responsibilities  
- Description of business processes  
- Architecture solution design  
- Security requirements  
- Extra functionality for the solution  
- Reporting  
- Integration  
- Data migration  

## Context and problem

In implementations with Dynamics 365 apps, the solution must often be extended to meet the business requirements. For example, you add ISV solutions, extensions, plugins, new tables, fields, entities, integrations, and so on. Make sure that the customer and implementation partner agree on the scope and design of the solution before the development work begins. The functional and technical design (FDD/TDD) also serves as documentation to support the application once the solution is developed, can help create training materials, and so on. For this reason, we recommend that you create a functional and technical design document that clearly outlines all aspects of the solution and is agreed upon by all parties.

## When to use this pattern

Use this pattern in the following scenarios:

- You must create a deliverable as a part of the design phase of your project for the functional and technical design of your solution. Learn more at [Solution: Create a combined FDD/TDD for entire solution](#solution-create-a-combined-fddtdd-for-the-entire-solution).  

- When you have a large number of business requirements, you can create a separate design document for each business process. Learn more at [Solution: Create a separate FDD/TDD for each business process](#solution-create-a-separate-fddtdd-for-each-business-process).  

This pattern might not be suitable in the following cases:

- When you have separate teams working on different lines of businesses and must create separate designs for each solution  

- When you have multiple phases in a project and must create multiple design documents for each phase or for a minimum viable product (MVP)  

## Solution: Create a combined FDD/TDD for the entire solution

As a part of the design phase of your Dynamics 365 implementation project, you need to create deliverables that document the functional and technical design of your solution. These deliverables are known as *Functional Design Documents* (FDD) and *Technical Design Documents* (TDD).  

- The FDD describes the design from a business perspective, including business processes, use cases, and requirements. It specifies how the solution must *work*.  
- The TDD describes the design from a technical perspective, including the architecture, data model, and system interfaces. It specifies how to *build* the solution.  

Both documents are critical to make sure that your solution is designed and built to meet the business needs and technical requirements. They also serve as a reference for developers, testers, and other stakeholders throughout the project lifecycle. When you create these deliverables, you're closer to making sure that the Dynamics 365 implementation project is well-planned, documented, and run. As a result, the project delivers a solution that meets the business goals and objectives.  

### Complete the combined FDD/TDD

Use the following steps to complete a combined FDD/TDD:

1. Download the template from the [dynamics365patternspractices GitHub repo](https://github.com/microsoft/dynamics365patternspractices/tree/main/templates/implementation-projects).  

    The Word template is in the implementation-projects folder. It contains no branding or copyright notices.  

2. Complete the *Introduction* section  

    This section outlines the structure and purpose of the document. It includes abbreviations that are used throughout the document, and an index of symbols used in the process flow diagram. The template includes samples that can be deleted or updated as appropriate for your project.

3. Complete the *Project overview*  

    This section includes the scope. When the project is large, you may break down the project scope into smaller section. The template includes a sample for breaking down by department, but you can use workstreams, business units, or companies, for example, depending on the size and complexity of your project.

4. Complete the *Organization structure and functional responsibilities* section  

    We recommend that you include an organizational diagram like the sample included in the template, and then use the following subsections to describe the organization structure.

5. Complete the *Description of business processes* section  

    This section starts by outlining the business processes and includes a subsection for each business process with a flow diagram and text to outline flow and requirements. For example, it's more difficult to keep track of who is responsible for each step when a flowchart describes a process that involves different people, departments, or functional areas. Another useful technique for tracking this information, and for analyzing the number of times a process is 'handed over' to different people, is to divide the flowchart into columns. Head up each column with the name of the person or function involved in the process. And each time they carry out an action, show it in their column. Use cross-functional flowcharts to show the relationship between a business process and the functional units (such as departments) responsible for that process. Bands represent the functional units. Shapes representing steps in the process are placed in bands that correspond to the functional units responsible for those steps.

6. Complete the *Architecture solution design* section  

    This section includes details of the data architecture. Make sure that you have covered the following subsections:

    - Key design decisions  
    - Scalability and performance considerations  
    - Usability and user interface considerations  
    - Optionally, a section for Future considerations  

    The template includes a sample of some Dataverse out-of-band tables for customer engagement solutions.

7. Complete the *Security requirements* section  

    This section should outline any built-in security that you plan to apply, and details for any custom security roles that you define for the solution. Each custom role should have a subsection outlining the full requirements.

8. Complete the *Additional functionality* section  

    The template provided includes some sample sections in it. You can add more sections if the project requires it. You can also remove sections if they're not relevant. This section could include more nonfunctional requirements, add-ins, ISV solutions, other or advanced functionality that needed to be specified/configured separately.

9. Complete the *Reporting and analytics* section  

    This section outlines the reporting and analytics approach. Include your approach for exporting data to external data warehouses, such as the Azure Synapse Link or the BYOD (Bring Your Own Database) option for finance and operations apps, for example. Also outline in detail each custom report and dashboard that you plan to build. Include the security requirements for the customs reports and dashboards.  

10. Complete the *Integration* section  

    This section outlines the details for the integration architecture including the design of each interface.

11. Complete the *Migration* section  

    This section outlines the detail for migration the data. It's broken down into several subsections for each type or data to be migrated. If there are multiple sources where data is being migrations from, consider including the field level mapping for each source.

### Issues and considerations for one document for the solution

Consider the following points when deciding how to implement this pattern:

- Creating a combined FDD/TDD for the entire solution can be a time-consuming process, especially for large and complex projects. As such, it's important to allocate sufficient time and resources to ensure that the document is thorough and accurate.

- It can be challenging to maintain consistency between the FDD and TDD sections, as the functional and technical requirements may overlap or contradict each other. It's essential to have a clear and defined process for reconciling any discrepancies between the two documents.

- The combined FDD/TDD can become outdated if not properly maintained and updated throughout the project lifecycle. It's crucial to establish a process for keeping the document up-to-date as changes occur, and add new requirements as they're identified.

- As the combined FDD/TDD covers the entire solution, it can be challenging to track progress and assign responsibilities for individual requirements. It's important to establish a clear process for tracking progress and ensuring that team members are aware of their responsibilities for each requirement.

Finally, it's important to ensure that the combined FDD/TDD is written in a language that all stakeholders understand, including technical and nontechnical team members. It's essential to strike a balance between technical accuracy and accessibility.

## Solution: Create a separate FDD/TDD for each business process

When you have many different requirements across the business processes that the solution supports, it's essential to keep track of them all in a structured and organized manner. One way is to create separate design documents for each business process. This approach ensures that each process is documented in detail, with specific design considerations and technical specifications included. It also allows for easier tracking of progress and helps to avoid confusion and overlapping between requirements.

By creating separate design documents, you can also assign specific team members to each requirement and track their progress independently. This approach is especially important for larger projects where multiple teams are involved. Additionally, having separate design documents can help with risk management by identifying potential issues or conflicts early in the project.

When you create these design documents, follow a consistent format, and include all necessary information, such as the following list:

- the requirement description  
- Design considerations  
- Technical specifications  
- Acceptance criteria  

Having a standardized template for these documents can help ensure consistency and make it easier to compare and review requirements across the project.

Overall, creating separate design documents for each business requirement can be a valuable tool for managing large projects and ensuring that all requirements are documented and tracked appropriately.

### Complete each FDD/TDD

Use the following steps to complete the FDD/TDD for each requirement.

1. Download the template from the [dynamics365patternspractices GitHub repo](https://github.com/microsoft/dynamics365patternspractices/tree/main/templates/implementation-projects).  

    The Word template is in the implementation-projects folder. It contains no branding or copyright notices. It's the same template that we described in the [Solution: Create a combined FDD/TDD for the entire solution](#solution-create-a-combined-fddtdd-for-the-entire-solution) section. 

2. Complete the *Introduction* section.

3. Complete the *Project* overview.

4. Complete the *Organization structure and functional responsibilities* section.

5. Complete the *Description of business processes* section.

6. Complete the *Architecture Solution Design* section.

7. Complete the *Security Requirements* section.

8. Complete the *Additional Functionality of the System* section.

9. Complete the *Reporting* section.

10. Complete the *Integration* section.

11. Complete the *Migration* section.

### Issues and considerations for multiple documents

Consider the following points when deciding how to implement this pattern:

- One potential issue to consider when creating separate design documents for each business process is the extra time and resources required to manage and track each document. It's important to have a clear process in place for organizing and accessing these documents to avoid confusion or duplication of effort.

- Another consideration is the potential for overlap or dependencies between requirements that may not be immediately apparent when each process is considered in isolation. It's important to review and validate the requirements holistically to ensure that they work together as intended.

- When creating standardized templates for these documents, it's important to ensure that they're flexible enough to accommodate variations in requirements and design considerations. It may be necessary to create multiple templates or variations to account for different types of requirements or design approaches.

- Communication and collaboration between team members is critical when creating and managing separate design documents. It's important to establish clear expectations for how team members should communicate and share information. This way, you make sure that all requirements are addressed, and that any issues are identified and addressed promptly.

Finally, it's important to ensure that the FDD/TDD documents are kept up to date throughout the project lifecycle. As requirements change or evolve, the design documents should be updated to reflect those changes and ensure that everyone is working from the same information.

Overall, while creating separate design documents for each business requirement can be a valuable tool, it's important to approach this process thoughtfully and with a clear plan for how to manage and track these documents throughout the project.

## Related resources

Use the following resources to learn more.

- [Introduction to Success by Design](../implementation-guide/success-by-design.md)  

- [Overview of business processes in Dynamics 365](../business-processes/index.yml)  

- [Security strategy overview](../implementation-guide/security.md)  

## Next steps

Learn more about the context for FDD and TDD in the following articles.

- [Solution architecture design pillars](../implementation-guide/solution-architecture-design-pillars.md)  

- [Process-focused solution](../implementation-guide/process-focused-solution.md)  

- [The Fit-to-standard and Fit-gap analysis](../implementation-guide/process-focused-solution-fit-to-standard-fit-gap-analysis.md)  

<!--## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Accounts payable, Accounts receivable, Administrative, Audit, Customer services, Engineering, Finance, Human Resources, IT, Marketing, Merchandising, Operations, Production, Project Management, Purchasing, Retail store operations, Sales, Service operations, Transportation, Treasury, Warehouse

*Products:* Dynamics 365-->

