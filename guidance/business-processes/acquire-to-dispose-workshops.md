---
title: Implementation workshops for Acquire to dispose 
description: Learn about the scenario board workshop, the storyline discovery workshop, and the detailed design workshop for the Acquire to dispose business processes in an implementation project with Dynamics 365.
author: edupont04
ms.author: edupont
ms.topic: conceptual
ms.collection: #Required; Leave the value blank.
ms.date: 12/02/2024
ms.custom: bap-template #Required; don't change.
---

# Implementation workshops for the Acquire to dispose business processes

This article outlines prerequisites, stakeholders, and key questions for three types of workshops that we recommend you include as part of an implementation project that covers the *acquire to dispose* end-to-end business process.

## Discovery workshop with a scenario board

The *acquire to dispose* scenario board discovery workshop is designed to help establish a comprehensive understanding of the end-to-end asset management process from acquisition to disposal for all key stakeholders in the implementation of Dynamics 365 to support these processes. This workshop will guide participants through the key scenarios and business process areas involved in the *acquire to dispose* process. By leveraging visual representations and interactive discussions, the workshop aims to align all stakeholders on the vision for the project and ensure that the new technology solution meets the needs of its users. Participants will engage in identifying key scenarios, goals, and key inputs and outputs for the processes. The workshop serves as a valuable tool for communication and collaboration, helping to refine the proposed scope and allows the partner to create an initial design proposal.  

### Assumptions for the discovery workshop  

- The *acquire to dispose* end-to-end business process is in scope for the Dynamics 365 project.  

- The *acquire to dispose* scenario board is available and leveraged to conduct the workshop.  

- The key stakeholders are available and actively contribute to the workshop. The following stakeholders are recommended:  

  - Asset managers - responsible for managing the lifecycle of assets from acquisition to disposal  

  - IT department - responsible for implementing and maintaining technology solutions to support the *acquire to dispose* process  

  - Finance department - responsible for tracking asset costs and depreciation  

  - Operations department - responsible for using assets to support business operations  

  - Maintenance department - responsible for ensuring assets are operational and performing maintenance on the assets  

  - Procurement department - responsible for purchasing assets and managing vendor relationships  

  - Legal and compliance department - responsible for ensuring regulatory compliance related to asset management and disposal  

  - Executive leadership - responsible for overseeing the acquisition and disposal of high-value assets and ensuring alignment with strategic goals.  

  - Human resources department – responsible for hiring and training users who will be operating the assets  

### Objectives for the discovery workshop

- Understand the customer's process: Gain a clear understanding of the customer's intended *acquire to dispose* process and process scope, including key steps, pain points, and challenges. 

- Identify key scenarios and requirements: Identify the most critical scenarios and requirements for the customer's *acquire to dispose* process.  

- Document agreed business scope: The partner understands the customer's scenarios and requirements well enough to propose a design to support the customer's scenario.  

### High-level agenda and key questions for the discovery workshop

1. Introduction and objectives (15 minutes)  

    1. What are your main objectives for implementing Dynamics 365 for asset management?
    2. What are the key challenges you currently face in your *acquire to dispose* process?
    3. Is the *acquire to dispose* process the same across your organization? Are there key differences between legal entities, business units, or departments that we must consider?
2. Overview of *acquire to dispose* process (20 minutes)  

    1. What are the key scenarios in your *acquire to dispose* process? Mark or highlight the primary scenario that you'll focus on in the next phase.
    2. Are there any scenarios that should not be included on this diagram? Mark or strike-through scenarios that are out of scope.
    3. Are there any other scenarios that are not included in this diagram but which we must include? Add the rows and document as potential gaps.
    4. What key differences do you see in your current *acquire to dispose* process and this standard process? Use the *acquire to dispose* scenario board as a starting point. Document any key differences for change management.
    5. What are the key pain points or bottlenecks in your current process?
3. Detailed discussion on key scenarios (45 minutes)  

    1. Are there any policies that need to be reviewed or adjusted as part of this project? If so, document and flag for change management.
    2. What are the most critical scenarios you encounter in your *acquire to dispose* process?
    3. How many total assets do you have today?
    4. How often do you dispose or retire assets?
    5. What systems or tools do you currently use for asset management?
    6. How do you ensure compliance with regulatory requirements in your *acquire to dispose* process?
    7. What improvements or changes would you like to see in your current process?

4. Interactive Q&A session (30 minutes)  

    1. What data must be migrated to the new asset management system?
    2. How do you currently manage and store asset data?
    3. Are there any data quality issues that must be addressed before migration?
    4. What are the key challenges you anticipate during the data migration process?
    5. How do you plan to validate and verify the accuracy of migrated data?
5. Wrap-Up and next steps (10 minutes)  

    1. What systems must the new asset management system integrate with?
    2. How do you currently handle data exchange between different systems?
    3. Are there any specific integration requirements or protocols that need to be followed?
    4. What are the key challenges you anticipate during the integration process?
    5. How do you plan to test and validate the integrations to ensure seamless data flow?

### Scenario board  

The following image is a sample scenario board template for the *acquire to dispose* process.  

:::image type="content" source="media/acquire-to-dispose-scenario-board.svg" alt-text="A scenario board with scenarios and tasks for each of the business process areas for this end-to-end scenario. The top row depicts a basic flowchart of the business process areas for the *acquire to dispose* process. Below each process step there are one or more blue boxes that depict scenarios and key attributes of the business process area for discussion in the workshop. The bottom of the graphic includes horizontal or supporting processes that support the entire *acquire to dispose* process. " lightbox="media/acquire-to-dispose-scenario-board.svg":::

The flowchart outlines the business process areas from acquisition to disposal. The top row shows the business process areas for the *acquire to dispose* process as a basic flowchart. Below each process area, each of the blue boxes call out scenarios and key attributes of that business process area that the workshop can then discuss. At the bottom of the graphic there are horizontal lines for the supporting processes that support the entire *acquire to dispose* process.  

## Storyline design review workshop

The *acquire to dispose* storyline design review workshop is a crucial step in refining the design of the asset management process. This workshop focuses on reviewing the storyline or "happy path" defined in the acquire to dispose scenario board discovery workshop, conducting a fit-to-standard review, reviewing the configured the solution, and reviewing high-level designs and slides for parts that cannot be demonstrated.

This workshop takes place after the initial acquire to dispose scenario board workshop and is based on the initial discovery phase. During this session, we delve deeper into the chosen storyline or "happy path", ensuring that it aligns with business requirements and standards. We also identify any gaps or areas that need further refinement.

By the end of this workshop, the aim is to achieve 80-90% accuracy and acceptance for the selected storyline, ensuring that we are well-prepared for the next phases of the project.

### Key activities for the storyline design review

- Review the storyline: Revisit the storyline or "happy path" selected during the initial discovery phase, ensuring it meets business needs and aligns with the strategic goals.

- Fit-to-standard review: Conduct a thorough review to ensure that the proposed solution fits within the standard processes and guidelines.

- Demonstrate the solution: Demonstrate the built-in capabilities and address any issues or challenges that arise. Make sure that the focus is on the primary storyline selected in the initial workshop.

- Review other components and design proposals: For parts of the process that cannot be demonstrated live, review slides or other resources to help illustrate the workflow and key points of the proposed design.

### Assumptions for the storyline design review

- The agreed business scope from the first workshop is completed

- Dynamics 365 has been configured for the key storyline selected

- The key stakeholders are available and actively contribute to the workshop. The following stakeholders are recommended:

  - Asset managers - responsible for managing the lifecycle of assets from acquisition to disposal

  - IT department - responsible for implementing and maintaining technology solutions to support the acquire to dispose process

  - Finance department - responsible for tracking asset costs and depreciation

  - Operations department - responsible for using assets to support business operations

  - Maintenance department - responsible for ensuring assets are operational and performing maintenance on the assets

  - Procurement department - responsible for purchasing assets and managing vendor relationships

  - Legal and compliance department - responsible for ensuring regulatory compliance related to asset management and disposal

  - Executive leadership - responsible for overseeing the acquisition and disposal of high-value assets and ensuring alignment with strategic goals.

  - Human resources department – responsible for hiring and training users who will be operating the assets

### Objectives for the storyline design review

- Demonstrate Dynamics 365 capabilities: Showcase how Dynamics 365 can address the identified pain points and improve the acquire to dispose process.

- Gather feedback and insights: Collect feedback from stakeholders to tailor the Dynamics 365 implementation to their specific needs.

- Define next steps: Outline the next steps and action items for the Dynamics 365 implementation.

- Document gaps, risks, issues, and decisions: Make sure all critical points are documented for future reference and action.

### High-level agenda and key questions for the storyline design review

- Introduction and objectives (5 minutes)

- Demonstration of Dynamics 365 solution for the storyline scenario (30 minutes)

- Detailed discussion on key scenarios (45 minutes)

    1. Does the proposed solution fit within the standard processes and guidelines of your organization?
    2. Are there any gaps or areas that need further refinement to align with the standard solution?
    3. How does the solution address the identified pain points and bottlenecks in your current process?
- Interactive Q&A session (30 minutes)

- Wrap-up and next steps (10 minutes)

## Detailed design workshops

For each of the *acquire to dispose* business process areas that the implementation project must include, we recommend that you have a dedicated design workshop where you dig into needs, concerns, and specific requirements. Each design workshop has almost the same agenda, but there are probably different stakeholders, and there might be different compliance and regulatory concerns.

