---
title: Overview of the Business Process Catalog Hierarchy
description: Dive into the structured hierarchy of the Business Process Catalog, including examples and best practices for naming and organizing processes.
author: edupont04
ms.author: edupont
ms.reviewer: edupont
ms.date: 12/09/2025
ms.topic: concept-article
---

# Overview of the business process catalog levels

The business process catalog has six different levels to provide a clear and systematic way to document, manage, and communicate business processes for the organization. Each level has a specific purpose and naming convention to ensure consistency and clarity. In this article, we outline the naming conventions and requirements for each level so that you can apply the business process catalog to your implementation project with Dynamics 365 apps.

## Level one: End-to-end process

An end-to-end process represents the complete flow of activities from the initial trigger to the final outcome. It encompasses all the intermediate steps and subprocesses that are necessary to achieve the business objective.

**Naming Convention**: The name should follow the format "\[This\] to \[That\]", where \[This\] is the starting point or trigger of the process, and \[That\] is the end point or outcome.

**Examples**

- Order to cash
- Source to pay
- Hire to retire

**What an end-to-end process is:**

- **Comprehensive**: Covers the entire lifecycle of a business operation.
- **Cross-Functional**: Involves multiple departments or functions.
- **Outcome-Oriented**: Focuses on delivering a specific business outcome.

**What an end-to-end process is not:**

- A single department's workflow.
- A narrowly defined task or activity.
- A process without a clear start and end point.

## Level two: Business process areas

A business process area is a key component or phase within an end-to-end process. It represents a significant grouping of related activities that contribute to the overall objective. It provides a logical way to group business processes, and it makes the business process catalog easier to navigate.

Business process areas are often loosely associated with certain personas or roles within the organization. While this connection is not a strict rule, it serves as a helpful guiding principle when mapping activities to specific responsibilities across teams. This approach enables clearer accountability and makes the process catalog more intuitive to navigate.

When naming L2 business process areas, consistency should always be the top priority to ensure clarity and ease of use throughout the process catalog. While aligning with industry standards is beneficial, it is secondary to maintaining a clear and understandable naming convention for business users. Above all, the name of each L2 should make it immediately apparent to the business user what activities or responsibilities the process area encompasses.

> [!NOTE]
> If an external service provider or partner wants to propose a new L2 business process area, this request requires special approval and further discussion with the business process excellence team. Such additions should not be made unilaterally to ensure consistency and maintain the integrity of the overall process catalog.

**Naming Convention**: The name must use a verb-noun pair, and it is acceptable to use two verb-noun pairs if necessary.

**Examples**

- Create and manage sales (within Order to cash)
- Process vendor invoices (within Source to pay)
- Plan and recruit your workforce (within Hire to retire)

**L2 verb list:**

Use the following list as a guide to select from a verb to use when naming an L2 business process area. While additional verbs can be used, the following list is the preferred and prioritized verbs.

- Conduct
- Develop
- Define
- Analyze
- Manage
- Process
- Issue
- Procure
- Govern
- Plan
- Introduce
- Create
- Record
- Invoice
- Monitor
- Onboard
- Maintain
- Acquire
- Retire
- Run
- Identify
- Qualify
- Pursue
- Estimate
- Close
- Comply
- Establish
- Schedule
- Perform
- Review

## Level three: Business processes

A business process is a specific set of activities or tasks that accomplish a particular business function within a business process area. They should be descriptive enough to be clear about the function being performed but should not be a specific activity, task, or step within the process. Additionally, they should not be system-specific processes; the process should be applicable to most businesses regardless of the system used.

We welcome software development companies and partners to add level three business processes as long as they follow the guidelines documented here. We ask that they evaluate carefully if the new row should be added as a scenario, system process, or test case first. This ensures that the organizational structure remains consistent and avoids duplication or misclassification of activities. Careful assessment helps maintain clarity and alignment with the intended business architecture. To suggest a new business process, visit <https://aka.ms/businessprocesscatalogrequests>.

**Naming Convention**: The name should use a verb-noun pair and be descriptive enough to clearly convey the function being performed.

**Examples**

- Sell products to customers (within Create and manage sales)
- Record invoice details (within Process vendor invoices)
- Plan and budget headcount (within Plan and recruit your workforce)

**What a business process is**:

- A distinct function within a business process area.
- Descriptive of the overall function without being a specific step.
- Not system-dependent and should apply broadly across different businesses.

**What a business process is not**:

- A specific activity, task, or step in a business process.
- A system-specific process (e.g., "Update Dynamics 365 Records").

## Level four: Scenario

A scenario or pattern is a unique way of executing a specific business process, often tailored to different scenarios, industries, or requirements. Scenarios are always product specific. The naming convention for scenario allows for variations based on product, deployment mode (if applicable), industry, and partner-provided solutions. When a product offers multiple ways of achieving a business process with different features or substantially different configuration, you can create separate patterns for the features which would be noted after the product name.

This is also the most common level where externally provided solutions are integrated into the standard catalog, as scenarios often require tailored functionality that ISVs provide. By adding ISV solutions at this stage, organizations can extend product capabilities to meet specific industry or business requirements while maintaining alignment with standard patterns.

It is important to note that for a partner-provided solution to be incorporated into the standard catalog, it must be available in Microsoft Marketplace. This ensures that only verified and accessible solutions are integrated, maintaining consistency and reliability across scenarios.

**Naming convention**: The name should use a verb-noun pair, with optional extensions to indicate specific deployment modes, industries, and partner-provided solutions.

**Format**:

Verb noun pair \[using product (deployment mode)\] \[for an industry\] \[with an externally-provided solution\]

> [!NOTE]
> The deployment mode is only required for Project Operations. A pattern should always indicate which product(s) are used. A scenario can optionally include an industry and/or a partner-provided solution. Partner-provided solutions can only be used when the solution is available in AppSource or the Azure Marketplace.

**Examples**

- Examples of patterns for Sell products to customers

  - Create a sales order to sell products using Dynamics 365 Sales
  - Create a sales order to sell products using Dynamics 365 Supply Chain Management
  - Create a sales order to sell products using Dynamics 365 Business Central
  - Create a sales order to sell products using Dynamics 365 Commerce Call Center
  - Create a cash and carry sale using Dynamics 365 Commerce
  - Create an online order as a business using Dynamics 365 Commerce Business to Business (B2B) portal
  - Create an online order as a consumer using Dynamics 365 Commerce

- Examples of patterns for Create a project contract

  - Create a project contract using Dynamics 365 Project Operations (lite deployment)
  - Create a project contract using Dynamics 365 Project Operations (stocked product and not stocked)
  - Create a project contract using Dynamics 365 Project Operations (lite deployment) for financial services with SA Go
  - Create a project contract using Dynamics 365 Project Operations (lite deployment) for professional services
  - Create a project contract using Dynamics 365 Business Central

- Examples of patterns for Plan and budget headcount

  - Plan and budget headcount using Dynamics 365 Human Resources position forecasting
  - Plan and budget headcount using Dynamics 365 Human Resources with basic jobs and open positions
  - Plan and budget headcount using Dynamics 365 Finance Budgeting module
  - Plan and budget headcount using Dynamics 365 Finance Business Performance Planning add-in

## Level five: System process

A system process is a portion of a business process that uses a specific **form, page, or UI element** in Dynamics 365. Each scenario should have at least one scenario. There is no limit to the number of system processes that can be part of a given scenario. Each system process should be documented clearly to facilitate repeatability and ease of understanding. Ensure that all relevant forms and UI elements are referenced, and provide step-by-step instructions for users interacting with the process. This enhances consistency across training materials, user guides, and testing documentation.

**Naming Convention:**  
Use a verb-noun phrase that reflects the **user action** on the form. Examples

- *Enter fixed asset details*
- *Review vendor transactions*

**Guidance**:

- Should be **traceable to a UI element**
- Supports **training, documentation, and testing**

**Examples**

- Submit purchase requisition
- Approve purchase order
- Receive goods against purchase order
- Match invoice to purchase order
- Process supplier payment

These system processes reflect typical actions in the Source to Pay cycle and can be traced directly to forms or UI elements within Dynamics 365, supporting clear documentation, training, and testing.

## Level six: Test cases

A test case is a detailed set of conditions and steps used to determine whether a software application or system functions correctly. It is an essential part of the software testing process, designed to ensure that the software meets its requirements and performs as expected. Test cases are used to identify defects, ensure quality, and verify that the software behaves as intended under various conditions. They should be used whenever there is a need to verify the functionality, performance, or security of a software application, especially before releasing it to production.

### Test case structure

When writing a test case, it's important to include specific information to ensure clarity and effectiveness. A well-documented test case should include the following elements:

- inputs or prerequisites, which outline any initial conditions or data required before executing the test
- detailed steps, which provide a step-by-step guide on how to perform the test
- outputs or expected results, which describe the anticipated outcome of the test

Test cases should always be related to a business process to ensure they are relevant and meaningful. Additionally, it is recommended to have at least one test case for each user story to verify that the functionality meets the user's needs and requirements. This approach helps ensure comprehensive coverage and validation of the software application.

### Types of test cases

There are several types of test cases, each serving a specific purpose:

- **Functional Test Cases**: These are used to verify that the software functions according to the specified requirements. They focus on the user interface, APIs, databases, security, and other functional aspects of the application.
- **Performance Test Cases**: These test cases are designed to assess the performance of the software under various conditions, such as load, stress, and scalability. They help ensure that the application can handle expected user traffic and perform efficiently.
- **Usability Test Cases**: These are used to evaluate the user experience and ease of use of the software. They focus on the design, navigation, and overall user interaction with the application.
- **Security Test Cases**: These test cases aim to identify vulnerabilities and ensure that the software is secure from threats and attacks. They include tests for authentication, authorization, data encryption, and other security measures.
- **Integration Test Cases**: These are used to verify that different modules or components of the software work together as expected. They help identify issues that may arise when integrating various parts of the application.
- **Regression Test Cases**: These test cases are used to ensure that recent code changes have not adversely affected existing functionality. They are typically run after any modification to the software to verify that the changes have not introduced new defects.
- **User Acceptance Test Cases**: These are designed to validate that the software meets the needs and expectations of the end users. They are typically performed by the users themselves to ensure that the application is ready for production.

Each type of test case plays a crucial role in ensuring the overall quality and reliability of the software application. By using a combination of these test cases, you can thoroughly test the software and identify any issues before they reach the end users.

### Examples

The following list are examples of different types of test cases related to the business process of creating a sales order. This list is not a comprehensive list, nor are the steps precise for executing each test. The list is meant to be a high-level representation of the types of tests that might exists for a similar business process.

1. **Functional Test Case**:
    - **Title**: Verify Sales Order Creation
    - **Description**: Ensure that a sales order can be created successfully.
    - **Steps**:
      1. Navigate to the Sales Order module.
      2. Click on "Create New Sales Order".
      3. Enter customer details, product information, and quantity.
      4. Save the sales order.
    - **Expected Result**: The sales order is created and saved successfully.

1. **Performance Test Case**:
    - **Title**: Assess Sales Order Creation Under Load
    - **Description**: Evaluate the system's performance when creating multiple sales orders simultaneously.
    - **Steps**:
      1. Simulate the creation of 1000 sales orders concurrently.
      2. Monitor the system's response time and resource usage.
    - **Expected Result**: The system handles the load efficiently without significant delays or crashes.

1. **Usability Test Case**:
    - **Title**: Evaluate User Experience in Sales Order Creation
    - **Description**: Assess the ease of use and navigation during the sales order creation process.
    - **Steps**:
      1. Ask a user to create a sales order without prior training.
      2. Observe the user's interaction with the interface.
      3. Collect feedback on the design, navigation, and overall experience.
    - **Expected Result**: The user can create a sales order easily and provides positive feedback on the interface.

1. **Security Test Case**:
    - **Title**: Verify Access Control for Sales Order Creation
    - **Description**: Ensure that only authorized users can create sales orders.
    - **Steps**:
      1. Attempt to create a sales order with an unauthorized user account.
      2. Attempt to create a sales order with an authorized user account.
    - **Expected Result**: The unauthorized user is denied access, while the authorized user can create a sales order.

1. **Integration Test Case**:
    - **Title**: Validate Integration Between Sales Order and Inventory Modules
    - **Description**: Ensure that the sales order creation updates the inventory correctly.
    - **Steps**:
      1. Create a sales order for a specific product.
      2. Check the inventory levels before and after the sales order creation.
    - **Expected Result**: The inventory levels are updated accurately based on the sales order.

1. **Regression Test Case**:
    - **Title**: Verify Sales Order Creation After System Update
    - **Description**: Ensure that the sales order creation functionality works correctly after a system update.
    - **Steps**:
      1. Perform a system update.
      2. Create a sales order following the standard process.
    - **Expected Result**: The sales order is created successfully without any issues introduced by the update.

1. **User Acceptance Test Case**:
    - **Title**: Confirm Sales Order Creation Meets User Requirements
    - **Description**: Validate that the sales order creation process meets the end user's needs and expectations.
    - **Steps**:
      1. Provide the end user with the sales order creation feature.
      2. Ask the user to create a sales order and provide feedback.
    - **Expected Result**: The user successfully creates a sales order and confirms that the process meets their requirements.

# About workshops

## Scenario board discovery workshop

The storyboarding process is a crucial step in the implementation of a new technology solution. It involves creating and agreeing a visual representation of the key business processes in the new system, followed by showing the business process within the Dynamics 365 system. This helps to ensure that all stakeholders have a clear understanding of the proposed solution and can provide feedback early in the development process. It also helps the functional consultants to verify their understanding of the business process requirements by directly assessing the solution design in the system vs customer expectations early in the lifecycle. We recommend that you use the storyboarding process in the initial discovery process for each end-to-end process that is in scope for the project.

The Microsoft Business Process Catalog aims to provide one default template storyboard for each out of the box end-to-end process. Some end-to-end processes may have more than one storyboard example to select from, but it is recommended to select only one that most closely matches the primary process of the organization. For example, the plan to produce processes include one story board for discrete manufacturing and one for process manufacturing. If the organization only manufactures in one technique or the other, select the one for the mode of manufacturing. However, if the organization uses mixed mode, try to select the one for the process that represents the majority. If the organization is an exact split of the two modes, then you can consider running two storyboarding workshops.

### Construction of a storyboard

The default storyboards included in the Microsoft Business Process catalog were constructed with the following key principles in mind. You can use the same framework to extend or modify the existing default storyboards, or to create new storyboards for new processes.

1. **Identify key scenarios**: Start by identifying the <u>key</u> end-to-end business scenarios that need to be addressed by the new technology solution. These scenarios should be based on user stories and business requirements. You should identify the end-to—end scenarios in scope and from that collection of scenarios, identify the small set of end-to-end scenarios that would represent say 80% of the business or represent the core business process. This process will also help you to identify the common steps/elements across the scenarios and prioritize within this small set.

1. **Create** **frames**: For each selected scenario, create frames that represent the different steps or stages in the user journey. The default storyboards provided with the Microsoft Business Process Catalog provide a simple flow diagram as a starting point. Each frame should include a visual representation of the expected functionality (feature+function+user interaction) and a brief description of the actions being performed.

1. **Add details**: Include details such as user interactions, system responses, and any other relevant information. This helps to provide a comprehensive view of the user experience that can easily generate a user story (or equivalent).

### Drafting the storyboard

The default storyboard template workshops that are provided with the Microsoft Business Process Catalog are intended to be a starting point for the discussion. It is expected that you will need to update and customize the storyboard for each organization. Use the following steps to prepare for the storyboarding workshop.

1. **Initial draft:** Select and leverage the best storyboard for the organization. Make any known updates to the storyboard for the industry or customer specific that are known before the start of the workshop. Present the draft of the storyboard based on the identified key scenarios and frames. This draft should be a rough representation of the business process represented by process inputs and outcomes, user journey and interactions. It is critical that it is based on following the standard processes from the BPC and Dynamics 365 to meet the underlying business requirements and NOT modelled based on the implementation in the **current** legacy system.

1. **Review and feedback**: Share the initial draft with stakeholders and gather feedback. This feedback is crucial for identifying any gaps or issues in the proposed solution.

1. **Refinement**: Refine the storyboard based on the feedback received. This may involve adding more details, adjusting the user interactions, or making other changes to improve the overall user experience.

### Inputs and outputs of the storyboarding process

Use the following guiding principles to help define the inputs and outputs that should be captured during the storyboarding process. The default storyboards include a draft of the inputs, which may need to be modified or updated during the storyboarding workshop or in preparation for the workshop.

- Inputs:
  - Key scenarios and user journeys
  - Visual representations of the process flow
  - Stakeholder feedback

- Outputs:
  - A detailed storyboard that visually represents the user journey and interactions
  - A clear understanding of the proposed solution and its impact on users
  - Key user stories and business requirements

By following this process, you can ensure that the new technology solution is well-designed and meets the needs of its users. The storyboard serves as a valuable tool for communication and collaboration, helping to align all stakeholders on the vision for the project. It also helps prioritize working on the key, critical end-to-end business scenarios before looking at more peripheral or complex or very infrequent scenarios.

### Sample storyboard

The following image illustrates a sample storyboard template for the *acquire to dispose* process.

:::image type="content" source="media/acquire-to-dispose-scenario-board.svg" alt-text="The image is a flowchart titled Acquire to Dispose Storyboard that outlines a business process from acquisition to disposal. The top row depicts a basic flowchart of the business process areas for the acquire to dispose process. Below each process step there are one or more blue boxes that depict scenarios and key attributes of the business process area for discussion in the workshop. The bottom of the graphic includes horizontal or supporting processes that support the entire acquire to dispose process." lightbox="media/acquire-to-dispose-scenario-board.svg":::

1. 10.05 Define asset strategy and policies

    1. Scenarios

        1. Build
        1. Buy
        1. Lease
        1. Develop

    1. Compliance

        1. ASC 842
        1. IFRS 16

    1. Policies

        1. Capitalization threshold
        1. Depreciation methods
        1. Maintenance guidelines
        1. Disposal
        1. Lease classification
        1. Renewal and termination
        1. Internal controls

1. 10.10 Plan and budget assets

    1. Scenarios

        1. Planned/Budgeted
        1. Unplanned/Not budgeted

    1. Budget approach

        1. Top-down
        1. Bottom-up
        1. Zero-based

    1. Budget detail

        1. Lump sum
        1. Summarize by type
        1. Detailed by asset

1. 10.20 Acquire assets

    1. Sourcing scenarios

        1. Request for quotation (RFQ)
        1. Purchase requisition
        1. Purchase order
        1. P-Card
        1. Projects
        1. Construction in Progress (CIP)

    1. Asset type scenarios

        1. Tangible, high-value
        1. Tangible, low-value
        1. Intellectual Property
        1. Trademarks
        1. Land

1. 10.30 Manage internal assets

    1. Scenarios

        1. Maintain asset details
        1. Insure
        1. Transfer

1. 10.40 Manage and report on asset financials

    1. Fixed asset scenarios

        1. Depreciate assets
        1. Revalue assets
        1. Write-up/down assets
        1. Correct asset values

    1. Asset lease scenarios

        1. Accrue lease payments
        1. Make lease payments
        1. Amortize lease liability
        1. Record lease expenses

    1. Capital asset project scenarios

        1. CIP
        1. Internal/Time
        1. Eliminate/Capitalize projects

1. 10.50 Maintain and repair assets

    1. Why

        1. Scheduled maintenance
        1. Unplanned maintenance

    1. Who

        1. Handled internally with local resources
        1. Handled internally with remote resources
        1. Handled internally with travelling resources
        1. Managed through third-party vendor

    1. Where

        1. Integrated
            1. In Dynamics 365

1. 10.60 Retire and dispose of assets

    1. Scenarios

        1. Sell
        1. Replace
        1. Dispose

1. 10.70 Analyze assets

    1. Inventory value
    1. Depreciation
    1. Condition
    1. Lease liabilities
    1. Maintenance cost

1. Case Management

1. Data and Integration

The following image illustrates the *acquire to dispose* storyboard with highlighted areas.

:::image type="content" source="media/about-business-process-catalog-levels-storyboard.png" alt-text="Screenshot of a slide that shows the 9 steps for running a storyboard workshop for the Acquire to dispose end-to-end scenario.":::

## Customer end-to-end design workshop

This is when we are done with all the scenario board workshops for all end-to-ends with a larger group of stakeholders to cover how we want the end-to-ends to map and fit together…

## Storyline design review workshop

The storyline design review workshop is a collaborative session designed to bring together key stakeholders from across the organization (including the implementation partners) to review, validate, and refine the end-to-end business process storylines developed during the scenario board discovery workshops. This workshop serves as a bridge between high-level process mapping and detailed design, ensuring alignment of the business objectives with the solution architecture before moving into deeper design phases.

**Step-by-Step Walkthrough:** Facilitate a sequential walkthrough of each major process storyline, highlighting how Dynamics 365 can support and enable these flows. Use visual aids or process diagrams to illustrate the main process steps, making any necessary adjustments to ensure accuracy and completeness. If new elements or exceptions are identified, visually distinguish them—such as with color coding or symbols—to clarify where deviations or enhancements occur.

**Discussion:** Encourage participants to share feedback on how their current practices relate to the **proposed storylines**, and actively identify opportunities for improvement or areas of concern. For each main process, work with stakeholders to pinpoint the "primary path"—the most critical or representative sequence of activities—and visually highlight it as consensus is reached. This helps focus subsequent design efforts on the most impactful scenarios. It is critical to remind the participants that the objective is to derive the **closest and best** solution within Dynamics 365, and not to recreate the legacy processes in Dynamics 365. Typically, this is managed by a moderator that keeps this important principle in mind to ensure the discussions are productive and focused.

**Deep Dive:** Explore specific blocks or steps where Dynamics 365 provides advanced functionality to streamline operations, such as automation, integration, or reporting features. Discuss any unique requirements or exceptions that may affect the overall process and document these findings for possible consideration in future workshops.

**Horizontal and Supporting Processes:** Review how supporting functions—such as case management, approvals, and risk or issue tracking—integrate with the main process storyline. Assess and document the requirements for managing these elements at each stage, ensuring the solution design addresses critical business needs.

**Data and Integration:** Examine how data is captured, stored, and migrated throughout the process steps. Discuss volumes, historical data handling, and any special considerations for data integration as part of the transition to Dynamics 365.

**Conclusion:** Update all visual materials and document key decisions, risks, actions, and issues identified during the workshop. Ensure agreement among stakeholders on the primary end-to-end scenario(s) to be carried forward into the detailed design phase. Record all outcomes and follow-up items in Azure DevOps or the project RAID log, maintaining a clear audit trail for future reference.

The storyline design review workshop is a collaborative session designed to bring together key stakeholders from across the organizations (customer, partner and any key ISVs) to review, validate, and refine the end-to-end business process storylines developed during the scenario board discovery workshops. This workshop serves as a bridge between high-level process mapping and detailed design, ensuring alignment of the business objectives with the solution architecture before moving into deeper design phases. **This is also the primary opportunity to demonstrate Dynamics 365 capabilities directly to stakeholders, showcasing how standard solution features can support the proposed processes wherever possible.**

**Step-by-Step Walkthrough:** Facilitate a sequential walkthrough of each major process storyline, highlighting how Dynamics 365 can support and enable these flows. Use visual aids or process diagrams to illustrate the main process steps, making any necessary adjustments to ensure accuracy and completeness. **Where applicable, demonstrate these steps live in Dynamics 365, focusing on the standard solution functionality to provide stakeholders with a clear understanding of out-of-the-box capabilities.** If new elements or exceptions are identified, visually distinguish them—such as with color coding or symbols—to clarify where deviations or enhancements occur.

**Discussion:** Encourage participants to share feedback on how their current practices relate to the proposed storylines, and actively identify opportunities for improvement or areas of concern. For each main process, work with stakeholders to pinpoint the "primary path"—the most critical or representative sequence of activities—and visually highlight it as consensus is reached. **The workshop should follow a fit-to-standard approach, focusing on leveraging Dynamics 365 standard features wherever feasible. Any gaps or requirements that indicate the standard solution is not a fit should be documented in detail.** This helps focus subsequent design efforts on the most impactful scenarios.

**Deep Dive:** Explore specific blocks or steps where Dynamics 365 provides advanced functionality to streamline operations, such as automation, integration, or reporting features. **Demonstrate these capabilities in the system whenever possible to provide clarity on what is available as standard.** Discuss any unique requirements or exceptions that may affect the overall process, and document these findings for consideration in future workshops, especially where the standard solution does not meet business needs.

**Horizontal and Supporting Processes:** Review how supporting functions—such as case management, approvals, and risk or issue tracking—integrate with the main process storyline. **Demonstrate standard Dynamics 365 capabilities for these supporting processes and document any gaps or requirements for enhancements.** Assess and document the requirements for managing these elements at each stage, ensuring the solution design addresses critical business needs.

**Data and Integration:** Examine how data is captured, stored, and migrated throughout the process steps. **Showcase how Dynamics 365 manages data as part of the standard solution, and document any requirements or gaps where additional integration or customization is needed.** Discuss volumes, historical data handling, and any special considerations for data integration as part of the transition to Dynamics 365.

**Conclusion:** Update all visual materials and document key decisions, risks, actions, and issues identified during the workshop. **Ensure that the workshop outputs include a detailed record of any gaps and requirements that prevent full adoption of the standard Dynamics 365 solution, as well as the rationale for any needed enhancements or customizations.** Ensure agreement among stakeholders on the primary end-to-end scenario(s) to be carried forward into the detailed design phase. Record all outcomes and follow-up items in Azure DevOps or the project RAID log, maintaining a clear audit trail for future reference.

## Detailed design workshops

A design workshop is a collaborative session where stakeholders, including business users, IT professionals, and consultants, come together to discuss and refine the functional requirements of a new technology solution. The primary purpose of the workshop is to take the information from the storyboarding process and vet out more details for the functional requirements. This helps ensure that the solution meets the needs of the business and is aligned with the overall project goals.

The Microsoft Business Process Catalog aims to provide at least one design workshop for each level 2 business process area. Some business process areas may include multiple design workshops. For example, the acquire to dispose end to end process includes a level two business process area for acquiring assets. This area includes three default workshops. One for fixed assets, one for asset leases, and one for capital projects. For each business process area that is in scope for a given project, it is recommended that at least one design workshop is conducted. In many cases, multiple workshops may be required. The separation of the design workshops is often dictated by the software structure and design of the Dynamics 365 applications but may be separated by industries or business models as well, for example.

It is recommended that during the sales cycle, enough detail is gathered to determine the level two business processes areas that are in scope and select the design workshops that would be relevant to the project.

### Workshop objectives

Each workshop should have a predefined set of objectives to help drive the outcome of the workshop. Below is a list of general workshop objectives for all design workshops. To clarify and refine the functional requirements of the new technology solution.

- To ensure that all stakeholders have a shared understanding of the proposed solution.
- To identify any gaps or issues in the proposed solution and address them.
- To configure a working solution that can be demonstrated after the workshop.
- To prepare for the next step, typically referred to as a conference room pilot or demonstration.

In addition to these objectives, the Microsoft Business Process Catalog default design workshops aim to provide a list of more specific objectives for the workshop. You may need to enhance or extend these objectives for a specific organization, industry, or ISV solution that is included in your project scope.

### Workshop delivery

Each workshop includes an agenda and a list of default key questions to ask during the workshop. The list of questions is not an exhaustive list of all questions, but rather a starting point to help drive the discussion and to make key decisions that are required to configure the Dynamics 365 solution. The key questions are designed to be specific to the end-to-end process, but the following list of questions are general questions that can be used to help form the basis of a design workshop for a custom business process or solution.

- What are the key business processes that need to be supported by the new technology solution?
- What are the specific functional requirements for each business process?
- Are there any existing systems or processes that need to be integrated with the new solution?
- What are the potential risks or challenges associated with the implementation?
- What are the success criteria for the new technology solution?

#### Inputs

When you start a design workshop, be sure to have the following key inputs available. The Workshop assumptions that are defined on each workshop help further define any additional inputs or required information for the workshop.

- Information from the storyboarding process, including key scenarios and user journeys.
- Visual representations of the process flow.
- Stakeholder feedback and business requirements.

#### Outputs

When the workshop is completed, you should have the following documented:

- A detailed and refined set of functional requirements.
- A configured working solution that can be demonstrated.
- A clear understanding of the proposed solution and its impact on users.
- Identified gaps or issues that need to be addressed before the next phase.

# Deliverables in the business process catalog

This article describes how to use Azure DevOps Boards for specific Teams with the Microsoft Business Process catalog. Additionally, it describes the custom work item types included in the default template which can be used to help effectively manage a Dynamics 365 project using Azure DevOps. The Azure DevOps template is designed to follow the Success by Design framework with a process-focused approach.

## Introduction

The Deliverables tree in Azure DevOps is a structured hierarchy designed to organize implementation work across multiple teams using interconnected Boards. This approach transforms traditional flat lists of deliverables into a dynamic tree that mirrors the logical flow of a Dynamics 365 project. Each branch of the tree represents areas of an organization and typical separation of work for a Dynamics 365 project. For example, Finance, Human Resources, Information Technology, Operations, and Sales. Each functional area is then further broken down to sub areas to make the catalog and data easier to navigate. These are represented by Area paths in the Azure DevOps template.

Within each branch there are various work item types which represent a category of work—such as configuration, migration, or testing. By mapping these deliverables to team-specific Boards, organizations gain clear visibility into ownership, dependencies, and progress across functional areas. This structure not only supports scaled agile planning but also ensures consistency in naming conventions, field groups, and governance across environments. Ultimately, the Deliverables tree enables collaborative execution, traceability from requirements to outcomes, and streamlined reporting for complex ERP implementations while still supporting smaller simple CRM projects.

Deliverables represent the concrete work and tasks that consultants must execute as part of a Dynamics 365 project, serving as actionable items that drive project progress. The catalog offers thousands of predefined deliverables that can be filtered based on the scope of the business process, and teams are encouraged to create custom work items throughout the project to address unique or evolving requirements.

The following sections outline each of the work items types included in the template with recommendations for how each should be used.

## Requirement

Requirements define the functional and non-functional needs that Dynamics 365 must fulfill. They serve as the foundation for solution design and traceability throughout the implementation lifecycle. In a Dynamics 365 project, requirements help align business objectives with system capabilities and ensure that gaps are identified early.

Requirements are not included by default in the Business Process Catalog because they represent a higher-level definition of business needs rather than a specific deliverable. We recommend using the Requirement work item type as a triage mechanism to capture and organize the initial business need, then link it to other deliverable types such as configurations, workflows, reports, or integrations that will fulfill that requirement. To maintain clarity and traceability, requirements should always be associated with the lowest-level business process possible. This ensures that each requirement is contextually tied to a specific process step, making it easier to identify dependencies and validate coverage during design and testing. This approach supports Success by Design principles for structured planning and governance.

### Examples

- System must support multi-currency invoicing for global operations.
- Enable automated tax calculation for multiple jurisdictions.
- System must allow sales reps to create quotes directly from opportunities.
- Enable case routing based on customer priority and SLA.
- Technicians must be able to capture customer signatures on mobile devices.
- System must process 1,000 sales orders per minute during peak load without errors.
- Case routing must occur within 2 seconds of case creation for high-priority customers.
- Mobile app must sync work orders within 30 seconds after connectivity is restored.
- System must maintain 99.9% uptime during business hours.
- All customer data must be encrypted at rest and in transit using AES-256.
- Application must support accessibility standards (WCAG 2.1) for visually impaired users.
- Response time for dashboards must not exceed 3 seconds for datasets under 10,000 records.

### Success by Design guidelines

- Use the Requirement work item type as a triage mechanism to capture business needs and link them to deliverables such as configurations, workflows, reports, or integrations.

- Always associate requirements with the lowest-level business process possible to ensure contextual relevance and traceability.

- Include clear acceptance criteria and prioritize requirements based on business value and risk.

- Maintain relationships between requirements and related work items in Azure DevOps for end-to-end visibility.

- Validate requirements during Fit/Gap workshops and ensure alignment with Success by Design phases (Envision, Design, Build).

- Document dependencies and assumptions to support governance and change management.

### Recommended fields 

- **Description:** Detailed explanation of the business need.

- **Acceptance Criteria:** Conditions that must be met for the requirement to be accepted.

- **Scope:** Indicates if the requirement is in scope or out of scope for the project.

- **Fit Gap Status:** Identifies if the requirement is met by standard functionality or requires customization.

- **Gap Solution Approach:** Approach for addressing gaps, if applicable.

- **Baseline Complexity:** Initial assessment of complexity.

- **Estimated Complexity:** Projected complexity for the specific requirement.

- **Duration:** Estimated time to complete the requirement.

- **Priority:** Importance to the business.

- **Story Points:** Effort estimate for the requirement.

- **Original Estimate:** Initial effort estimate.

- **Remaining Work:** Updated effort as work progresses.

- **Completed Work:** Time actually spent.

- **Business Process Owner:** Accountable business owner.

- **Workstream Lead:** Delivery lead for related work products.

- **Subject Matter Expert:** Individual who provides expertise for the requirement.

- **Requirement Mapping:** Details on how the requirement will be fulfilled by other deliverables.

- **Success by Design Phase:** Phase relevant to the requirement.

- **Catalog Status:** Status for catalog governance.

- **Article Status:** Status of related documentation.

- **Business Process Flow Status:** Status of process flow diagram.

- **Application Family:** Application family tags (e.g., F&O, CE).

- **Products:** Relevant products associated with the requirement.

### Procedure: Create a requirement type work item in Azure DevOps

Use the following steps to create a requirement in the Azure DevOps project using the default template for the Microsoft Business Process Catalog.

1. Go to your Azure DevOps project and open the Deliverables backlog. You can optionally, select the backlog for a specific Team like Accounts payable or Sales, for example.

2. Select **New Work Item** and choose **Requirement**.

3. Enter a clear and detailed **Description** of the requirement.

4. Specify the **Scope** and **Priority**.

5. Add **Acceptance Criteria** to define what success looks like.

6. Fill in additional fields such as **Fit Gap Status**, **Gap Solution Approach**, and **Complexity** as needed.

7. Assign the work item to the appropriate **Business Process Owner** or **Workstream Lead**.

8. Link the requirement to related deliverables (e.g., business process, process area, configuration, workflow, report, integration).

9. Save the work item.

## Workflow

Workflows represent automated or manual process flows that can span Dynamics 365 finance & operations such as Finance and Supply Chain Management, customer engagement apps such as Sales and Customer Service, Power Automate flows, or Agent flows that connect processes across systems. These workflows streamline business operations by defining triggers, conditions, and actions that ensure consistency and compliance. In the Business Process Catalog, we include out-of-the-box (OOB) workflows for all finance and operations workflows, and we plan to add standard Business Process Flows for customer engagement apps in a future release. Power Automate flows can also be documented as deliverables when they are part of the solution design.

For each workflow, business process flow, Power Automate flow, or Agent flow, we recommend creating a single work item that is directly related to the business process the flow supports. This ensures clear alignment between the process and its automation, making it easier to manage dependencies and traceability. If there are multiple configurations of the same workflow in Dynamics 365 Finance & Operations—for example, two distinct approval workflows for purchase orders—you should duplicate the work item and name each according to its specific configuration. This approach allows you to document the requirements and configuration details for each variation and helps manage associated testing, migration, and governance activities effectively.

Agent flows, which automate tasks using Copilot, should also be documented as individual work items. For example, an Agent flow that automatically responds to customer inquiries about order status in Dynamics 365 Customer Service should have its own work item linked to the order management business process. This ensures visibility into AI-driven automation and supports testing and compliance requirements.

### Examples

- Purchase Order Approval Workflow

- Leads Business Process Flow

- Automated case escalation using Power Automate

### Success by Design guidelines

- Leverage out-of-the-box workflows and business process flows whenever possible to minimize customization and reduce upgrade risk.

- Maintain naming standards by using the workflow name from F&O or CE for work item titles.

- For Power Automate and Agent flows:

  - Document triggers, connectors, and governance policies.

  - Include AI-driven automation details such as intent, scope, and fallback actions.

  - Validate compliance with data privacy and security standards.

- Link each flow to the lowest-level business process for traceability.

- Capture dependencies and testing requirements for all automation types, including Agent flows.

- Ensure workflows and flows align with performance, compliance, and accessibility requirements before deployment.

### Recommended fields

The following fields are recommended for the Workflow work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog.

- **Description:** Details of the workflow to be configured or automated.

- **Workflow Type:** Type of workflow (e.g., approval, automation, alert).

- **Approval Levels:** Number of approval levels required.

- **Approval Types:** Types of approval needed (e.g., compliance, technical).

- **Configuration Keys:** Relevant configuration keys for the workflow.

- **Menu Path:** Navigation path to access the workflow in the application.

- **Business Process Owner:** Person accountable for the workflow.

- **Workstream Lead:** Person leading the workflow implementation.

- **Success by Design Phase:** Phase relevant to the workflow.

### Procedure: Create a workflow type work item in Azure DevOps

Use the following steps to create a workflow in the Azure DevOps project using the default template for the Microsoft Business Process Catalog.

1. Go to your Azure DevOps project and open the Deliverables backlog. You can optionally, select the backlog for a specific Team like Accounts payable or Sales, for example.

2. Select **New Work Item** and choose **Workflow**.

<!-- -->

3. Enter a clear **Description** of the workflow.

4. Specify **Workflow Type**, **Approval Levels**, and **Approval Types**.

5. Add relevant **Configuration Keys** and **Menu Path**.

6. Assign the workflow to the appropriate **Business Process Owner** or **Workstream Lead**.

7. Link the work item to related deliverables (e.g., business process, process area, configuration, workflow, report, integration).

8. Save the work item.

## Report

Reports and inquiries provide visibility into business data to support decision-making, compliance, and operational efficiency. They can take multiple forms, including:

- **Operational reports:** Day-to-day transactional insights (e.g., open orders, pending invoices).

- **Analytical reports:** Trend analysis and performance dashboards (e.g., sales pipeline, inventory aging).

- **Regulatory reports:** Compliance-driven outputs (e.g., tax filings, audit trails).

- **Ad-hoc inquiries:** On-demand queries for specific data points.

Currently, no reports are included out-of-the-box in the Business Process Catalog. However, we plan to expand the catalog in future releases to include standard reports and dashboards aligned with common business processes. This will help accelerate implementations by providing pre-defined reporting templates and governance guidelines.

For standard out-of-the-box (OOB) reports, we recommend creating a single work item to indicate that the report is in scope and meets the business requirements. This provides a central artifact to link related deliverables such as testing, security, documentation, user training and any required configuration activities. For custom reports or any report customization, create a dedicated work item to document both the functional and technical design of the report. This ensures traceability, supports governance, and provides a clear reference for testing, migration, and future enhancements.

### Examples

- Monthly financial summary report for CFO dashboard.

- Inventory aging report for warehouse management.

- Pipeline report showing opportunities by stage and probability.

- Case resolution time report segmented by agent and queue.

- Technician productivity report with completed work orders per day.

### Success by Design guidelines

- Define KPIs and data sources upfront.

- Ensure security roles for report access.

- Validate reports against regulatory requirements and business needs.

### Recommended fields

The following fields are recommended for the Report work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog.

- **Description:** Details of the report, dashboard, or analytic.

- **Report Type:** Type of report (e.g., analytical, audit, financial).

- **Report Audience:** Intended audience for the report.

- **Report Technology:** Technology used to generate the report (e.g., Power BI).

- **Execution Frequency:** How often the report should be run.

- **Business Process Owner:** Person accountable for the report.

- **Workstream Lead:** Person leading the report development.

- **Success by Design Phase:** Phase relevant to the report.

### Procedure: Create report type work items in Azure DevOps

Use the following steps to create a Report type work item in the Azure DevOps project using the default template for the Microsoft Business Process Catalog.

1. Go to your Azure DevOps project and open the Deliverables backlog. You can optionally, select the backlog for a specific Team like Accounts payable or Sales, for example.

2. Select **New Work Item** and choose **Report**.

3. Enter a clear **Description** of the report.

4. Specify **Report Type**, **Audience**, **Technology**, and **Execution Frequency**.

5. Assign the report to the appropriate **Business Process Owner** or **Workstream Lead**.

6. Link the requirement to related deliverables (e.g., business process, process area, configuration, workflow, report, integration).

7. Save the work item.

## Integration

Integrations connect Dynamics 365 applications with external systems or services to enable seamless data exchange and process automation. They are critical for maintaining data consistency across enterprise applications and supporting end-to-end business processes. Integrations can include real-time APIs, batch interfaces, middleware-based connections, or low-code solutions such as Power Automate.

Currently, the Business Process Catalog includes **Dual Write maps as standard integrations**, but no other integrations are provided out-of-the-box.

We recommend creating **one work item for each interface** to align with the Success by Design approach. This ensures traceability and provides a single artifact for linking related deliverables such as testing, security, and migration activities. Each integration work item should capture the technical and functional details required for the **Solution Blueprint review**, including interface model, technology, and performance considerations. This practice supports governance, accelerates design reviews, and simplifies change management.

### Examples

- Integrate Dynamics 365 SCM with SAP for inventory sync.

- Connect CRM with marketing automation platform.

- Integrate Dynamics 365 Sales with LinkedIn Sales Navigator for lead enrichment.

- Connect Customer Service with Power Virtual Agents for chatbot escalation.

- Integrate IoT sensors with Field Service to trigger work orders automatically.

### Success by Design guidelines

- Document endpoints, authentication, and data mapping.

- Include retry and error-handling strategies.

- Validate performance under peak loads and ensure security compliance.

### Recommended fields

The following fields are recommended for the **Integration** work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- **Description:** Details of the integration between systems.

- **Source System:** System where data originates.

- **Source Data Entity:** Data entity from the source system.

- **Target System:** System where data will be sent.

- **Target Data Entity:** Data entity in the target system.

- **Interface Technology:** Technology used for integration (e.g., Power Automate, Azure Logic Apps).

- **Interface Mode:** Mode of integration (e.g., real-time, batch).

- **Interface Model:** Model used for the interface (e.g., API, file-based).

- **Middleware:** Middleware technology used for integration.

- **Initial Data Sync Mechanism:** Approach for initial data load (e.g., batch, real-time).

- **Peak Hour Volume:** Expected transaction volume during peak hours.

- **Average Daily Volume:** Expected average daily transaction volume.

- **Average Hourly Transactions:** Expected hourly transaction count.

- **Validation Method:** Method for validating data or processes (e.g., checksum, audit trail).

- **Business Process Owner:** Person accountable for the integration.

- **Workstream Lead:** Person leading the integration.

- **Success by Design Phase:** Phase relevant to the integration.

- **Catalog Status:** Status for catalog governance.

- **Process Sequence ID:** Unique sequence ID for process alignment.

### Procedure: Create an Integration in Azure DevOps

Use the following steps to create an integration work item in the Azure DevOps project using the default template for the Microsoft Business Process Catalog:

1. Go to your Azure DevOps project and open the **Deliverables backlog**.

2. Select **New Work Item** and choose **Integration**.

3. Enter a clear **Description** of the integration.

4. Specify **Source System**, **Source Data Entity**, **Target System**, and **Target Data Entity**.

5. Add details for **Interface Technology**, **Interface Mode**, **Interface Model**, and **Middleware**.

6. Include performance-related fields such as **Peak Hour Volume**, **Average Daily Volume**, and **Average Hourly Transactions**.

7. Assign the integration to the appropriate **Business Process Owner** or **Workstream Lead**.

8. Link the work item to related deliverables (e.g., business process, configuration, migration, testing).

9. Save the work item.

## Configuration

Configurations represent system setups required to enable processes without custom development. They include parameters, number sequences, feature management keys, and other settings that tailor Dynamics 365 applications to meet business requirements.

The Business Process Catalog **includes hundreds of out-of-the-box configurations**, covering Finance and Operations and Customer Engagement apps. These configurations are updated regularly with each release to reflect new features. If customers or partners identify missing configurations, they can report them via GitHub issues at https://aka.ms/businessprocesscatalogrequests.

We recommend the following usage of the configuration work item type in the Azure DevOps template.

- For **standard OOB configurations**, the catalog already provides one work item for each setup, parameter, or number sequence in Dynamics 365 finance and operations apps and customer engagement apps.

- For **customizations that require configuration**, create a dedicated work item to document the functional and technical details.

- If a configuration is implemented differently across legal entities, business units, or geographies, **duplicate the work item** and name each copy to reflect its context (e.g., include legal entity, department, or region in the title).

This approach ensures traceability, supports governance, and provides a clear reference for testing, migration, and cutover activities.

### Examples

- Set up manufacturing accounting policies in Cost Management.

- Configure tax codes for multiple jurisdictions.

- Configure lead scoring model based on engagement and demographics.

- Set up SLA policies for premium customers.

- Configure resource scheduling optimization for technician availability.

### Success by Design guidelines

- Follow catalog mapping to menu paths and modules.

- Use configuration templates for consistency.

- Avoid direct edits; follow governance for changes.

### Recommended fields

The following fields are recommended for the **Configuration** work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- **Description: Details of the configuration or setup.**

- **Configuration Type: Type of configuration (e.g., Parameter, Setup data).**

- **Menu Path: Navigation path to access the configuration in the application.**

- **Menu Item Name: Name of the menu item for configuration.**

- **Cutover Method: Method for populating configuration data during deployment.**

- **Data Package: Name of the data package for configuration.**

- **Execution Sequence: Order of operations for configuration within the data package.**

- **Configuration Keys: Relevant configuration keys for the configuration.**

- **Feature Management Keys: Keys controlling feature availability.**

- **Country Region Codes: Applicable localization or compliance codes.**

- **Business Process Owner: Person accountable for the configuration.**

- **Workstream Lead: Person leading the configuration activity.**

- **Success by Design Phase: Phase relevant to the configuration.**

- **Catalog Status: Status for catalog governance.**

- **Process Sequence ID: Unique sequence ID for process alignment.**

### Procedure: Create Configuration type work items in Azure DevOps

Use the following steps to create a configuration work item in the Azure DevOps project using the default template for the Microsoft Business Process Catalog:

1. Go to your Azure DevOps project and open the **Deliverables backlog**.

2. Select **New Work Item** and choose **Configuration**.

3. Enter a clear **Description** of the configuration activity.

4. Specify **Configuration Type**, **Menu Path**, and **Menu Item Name**.

5. Add details for **Cutover Method**, **Data Package**, and **Execution Sequence**.

6. Include any **Configuration Keys**, **Feature Management Keys**, and **Country Region Codes**.

7. Assign the configuration to the appropriate **Business Process Owner** or **Workstream Lead**.

8. Link the work item to related deliverables (e.g., business process, workflow, report, integration).

9. Save the work item.

## Enhancement

Enhancements represent customizations that extend or modify standard Dynamics 365 functionality to meet unique business requirements. These can include code changes, custom plugins, extensions, or low-code solutions such as Power Apps. Enhancements are project-specific and vary by customer, making them critical for documenting technical and functional design details.

The Business Process Catalog **does not include any enhancements out-of-the-box**, as these are custom deliverables tailored to each implementation. Future catalog updates will continue to focus on standard processes, while enhancements remain customer-specific.

Enhancements should be documented as individual work items to ensure traceability and governance throughout the project lifecycle. Each enhancement work item should capture both the functional design, which explains the business need and expected behavior, and the technical design, which details the implementation approach and technology stack. Linking enhancements to related business processes, requirements, workflows, configurations, and testing activities provides end-to-end visibility and supports quality assurance. Because enhancements are custom and specific to each customer, naming conventions should clearly reflect the process or feature being extended, making it easier to manage dependencies and review during solution design and testing phases.

### Examples

- Add custom field for sustainability score in product master.

- Develop custom workflow for vendor onboarding.

- Add custom field for competitor name on opportunity form.

- Create custom ribbon button for quick case reassignment.

- Develop custom plugin to auto-calculate travel time for work orders.

### Success by Design guidelines

- Justify every enhancement with clear business value and Fit/Gap analysis to ensure alignment with project scope and measurable outcomes.

- Prioritize low-code or no-code solutions (e.g., Power Apps, Power Automate) over heavy customizations to reduce complexity and upgrade risk.

- Document both functional and technical design details, including dependencies, integration points, and architectural decisions (use ADRs for transparency and traceability).

- Plan lifecycle management for upgrades and maintenance, noting potential impacts on future releases and ISV solutions.

- Validate compliance and security implications, especially for enhancements involving sensitive data or automated decision-making.

- Apply Responsible AI principles (Fairness, Reliability & Safety, Privacy & Security, Transparency, Accountability) when building AI-driven or agentic enhancements.

- Ensure human oversight and interruptibility for autonomous or semi-autonomous agentic features; include mechanisms to pause or shut down execution if needed.

- Implement transparency and traceability for AI agents by logging prompts, decisions, and actions to support debugging, compliance, and ethical reviews.

- Perform risk assessments for emergent behaviors and multi-agent collaboration, and define clear boundaries for agent capabilities.

- Link enhancements to related requirements, workflows, configurations, and testing work items to maintain end-to-end governance and support Solution Blueprint reviews.

- Conduct performance and scalability checks for enhancements that introduce automation or AI-driven logic to ensure operational reliability.

### Recommended fields

The following fields are recommended for the **Enhancement** work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- **Description:** Details of the enhancement to be developed.

- **Development Technology:** Technology used for the enhancement (e.g., X++, Power Apps, JavaScript).

- **Functional Design:** Documentation or link describing how the enhancement meets business needs.

- **Technical Design:** Documentation or link describing how the enhancement will be implemented technically.

- **Configuration Keys:** Relevant configuration keys for the enhancement.

- **Feature Management Keys:** Keys controlling feature availability.

- **Business Process Owner:** Person accountable for the enhancement.

- **Workstream Lead:** Person leading the enhancement development.

- **Success by Design Phase:** Phase relevant to the enhancement.

- **Catalog Status:** Status for catalog governance.

- **Process Sequence ID:** Unique sequence ID for process alignment.

### Procedure: Create an Enhancement in Azure DevOps

Use the following steps to create an enhancement work item in the Azure DevOps project using the default template for the Microsoft Business Process Catalog:

1. Go to your Azure DevOps project and open the **Deliverables backlog**.

2. Select **New Work Item** and choose **Enhancement**.

3. Enter a clear **Description** of the enhancement.

4. Add details for **Development Technology**, **Functional Design**, and **Technical Design**.

5. Include any **Configuration Keys** or **Feature Management Keys**.

6. Assign the enhancement to the appropriate **Business Process Owner** or **Workstream Lead**.

7. Link the work item to related deliverables (e.g., requirements, workflows, configurations, testing).

8. Save the work item.

## Documentation

Documentation deliverables provide essential guidance and reference materials that support implementation, governance, and ongoing operations. They include user guides, strategy documents, and solution design artifacts that align with the Success by Design framework.

The Business Process Catalog **includes a small number of documentation deliverables out-of-the-box**, such as the **Solution Blueprint** and strategy documents for key Success by Design topics (e.g., Environment Strategy, ALM Strategy, Integration Strategy). These serve as foundational artifacts for governance and quality assurance. Additional documentation deliverables should be created as needed to capture project-specific details and ensure traceability.

Documentation work items should be used to catalog all critical reference materials that support the implementation and governance of Dynamics 365 projects. For standard Success by Design documents included in the catalog, use the provided work items to track completion and updates. For custom documentation, create a dedicated work item to capture the purpose, scope, and links to related content. This ensures visibility, supports audits, and provides a central artifact for linking related deliverables such as workshops, configurations, and testing activities.

### Examples

- Solution Blueprint

- Environment Strategy

- Application Lifecycle Management (ALM) Strategy

- User guide for purchase order approval process

- Technical design document for integration architecture

- User guide for creating and managing quotes in Sales Hub.

- Knowledge article for resolving common billing disputes.

- Step-by-step guide for technicians to use the mobile app offline

### Success by Design guidelines

- Ensure documentation aligns with **Success by Design phases** and supports governance checkpoints.

- Use standard templates for strategy documents and solution design artifacts to maintain consistency.

- Include links to authoritative sources such as Microsoft Learn and internal best practices.

- Keep documentation updated throughout the project lifecycle to reflect design changes and decisions.

- Store documentation in a centralized repository with version control for auditability.

- Link documentation work items to related deliverables (e.g., workshops, configurations, testing) for traceability.

### Recommended fields

The following fields are recommended for the **Migration** work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- **Description:** Details of the migration activity.

- **Source System:** System where data originates.

- **Source Data Entity:** Data entity from the source system.

- **Target System:** System where data will be migrated.

- **Target Data Entity:** Data entity in the target system.

- **Migration Strategy:** Strategy for migration (e.g., phased, big bang).

- **Migration Method:** Method used (e.g., API-based, Data Management Framework).

- **Data Migration Volume:** Estimated volume of data to migrate.

- **Data Scrubbing Technology:** Technology used for data cleansing.

- **Validation Method:** Method for validating migrated data (e.g., checksum, audit trail).

- **Interface Model:** Model used for integration during migration (e.g., API, file-based).

- **Middleware:** Middleware technology used for migration.

- **Initial Data Sync Mechanism:** Approach for initial data load (e.g., batch, real-time).

- **Business Process Owner:** Person accountable for migration.

- **Workstream Lead:** Person leading the migration.

- **Success by Design Phase:** Phase relevant to migration.

- **Catalog Status:** Status for catalog governance.

- **Process Sequence ID:** Unique sequence ID for process alignment.

### Procedure: Create a Migration in Azure DevOps

Use the following steps to create a migration work item in the Azure DevOps project using the default template for the Microsoft Business Process Catalog:

1. Go to your Azure DevOps project and open the **Deliverables backlog**.

2. Select **New Work Item** and choose **Migration**.

3. Enter a clear **Description** of the migration.

4. Specify **Source System**, **Source Data Entity**, **Target System**, and **Target Data Entity**.

5. Add details for **Migration Strategy**, **Migration Method**, **Data Migration Volume**, and **Validation Method**.

6. Assign the migration to the appropriate **Business Process Owner** or **Workstream Lead**.

7. Link the work item to related deliverables (e.g., business process, configuration, integration).

8. Save the work item.

## Personalization

Personalization work items represent adjustments to the user interface or experience within Dynamics 365 applications to improve usability and efficiency for specific roles or individuals. These changes typically involve modifying forms, views, dashboards, or workspace layouts without altering core functionality.

The Business Process Catalog does not currently include personalization work items out-of-the-box, but we are evaluating whether to include standard personalization templates in future releases. For now, personalization deliverables should be documented as custom work items when they are part of the implementation scope.

Personalization work items should be used to capture all UI adjustments that optimize user experience for specific roles or business scenarios. Each work item should document the purpose, affected areas, and any dependencies on configurations or workflows. Linking personalization work items to related requirements and testing ensures traceability and supports governance. If multiple variations are required for different legal entities, departments, or regions, create separate work items and name them accordingly.

### Examples

- Customize workspace for Accounts Payable clerk.

- Add quick links for frequently used reports in Finance dashboard.

- Migrate historical opportunities from Salesforce to Dynamics 365 Sales.

- Import legacy case data from Zendesk.

- Load historical work orders from legacy field service system.

### Success by Design guidelines

- Validate personalization requirements during design workshops and confirm alignment with business roles.

- Use standard personalization features before considering custom development to minimize complexity.

- Document all changes for governance and audit purposes.

- Link personalization work items to related requirements, workflows, and testing deliverables for traceability.

- Ensure accessibility compliance and performance impact are assessed before deployment.

- If personalization involves automation or adaptive UI changes, apply **Responsible AI principles** and ensure transparency and user control.

### Recommended fields

The following fields are recommended for the **Personalization** work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- **Description:** Details of the personalization to be applied.

- **Menu Path:** Navigation path for personalization.

- **Menu Item Name:** Name of the menu item being personalized.

- **Configuration Keys:** Relevant configuration keys for personalization.

- **Feature Management Keys:** Keys controlling personalization features.

- **Business Process Owner:** Person accountable for personalization.

- **Workstream Lead:** Person leading personalization setup.

- **Success by Design Phase:** Phase relevant to personalization.

- **Catalog Status:** Status for catalog governance.

- **Process Sequence ID:** Unique sequence ID for process alignment.

### Procedure: Create a Personalization in Azure DevOps

Use the following steps to create a personalization work item in the Azure DevOps project using the default template for the Microsoft Business Process Catalog:

1. Go to your Azure DevOps project and open the **Deliverables backlog**.

2. Select **New Work Item** and choose **Personalization**.

3. Enter a clear **Description** of the personalization.

4. Add relevant **Menu Path**, **Configuration Keys**, and **Feature Management Keys**.

5. Assign the personalization to the appropriate **Business Process Owner** or **Workstream Lead**.

6. Link the work item to related deliverables (e.g., business process, configuration, workflow).

7. Save the work item.

## Security

Security work items represent the measures required to protect data, enforce compliance, and manage access within Dynamics 365 projects. This includes **role-based security**, **data access controls**, **environment-level security**, and **compliance configurations**. Security deliverables ensure that only authorized users can perform specific actions, sensitive data is protected, and organizational policies are enforced across all environments.

Currently, the Business Process Catalog **does not include security work items out-of-the-box**, but we are evaluating how to incorporate standard security templates in a future release. For now, security deliverables should be documented as custom work items when they are part of the implementation scope.

Security work items should be used to capture all aspects of security configuration for a project. This includes defining **security roles**, **field-level permissions**, **data privacy settings**, and **environment access controls**. Each work item should document the purpose, compliance requirements, and dependencies on workflows, integrations, or configurations. Linking security work items to related deliverables such as testing and documentation ensures traceability and supports governance. If multiple variations are required for different legal entities or regions, create separate work items and name them accordingly.

As organizations adopt AI agents and agentic automation within Dynamics 365, security becomes even more critical. Agents often interact with sensitive data, invoke tools, and execute actions autonomously or semi-autonomously. This introduces new risks such as **data leakage**, **prompt injection attacks**, and **unauthorized tool usage**. To mitigate these risks, security measures must extend beyond traditional role-based access to include **agent identity management**, **real-time monitoring**, and **policy enforcement**.

Microsoft recommends implementing **agent-specific identities** (e.g., Azure AD service principals), applying **Microsoft Purview Data Security Posture Management for AI**, and enabling **Defender for AI agents** for real-time threat detection and blocking of suspicious actions. Additionally, organizations should apply **Responsible AI principles**—Fairness, Reliability & Safety, Privacy & Security, Transparency, and Accountability—when designing and deploying agentic workflows. This includes logging agent decisions, enforcing compliance policies, and ensuring human oversight for critical operations.

### Examples

- Create security role for warehouse manager.

- Implement segregation of duties for finance roles.

- Create security role for regional sales managers with access to their territory only.

- Restrict case visibility to assigned queues.

- Ensure technicians can only view work orders assigned to them.

### Success by Design guidelines

- Validate security requirements during design workshops and confirm alignment with organizational policies and compliance standards.

- Implement role-based security using least-privilege principles to minimize risk.

- Configure field-level and record-level security for sensitive data and enforce environment-level access controls.

- Document compliance requirements (e.g., GDPR, SOX) and ensure configurations meet regulatory standards.

- Link security work items to related deliverables such as workflows, integrations, and testing for traceability.

- Perform penetration testing and vulnerability assessments before go-live.

- Agentic AI considerations:

  - Apply Responsible AI principles (Fairness, Reliability & Safety, Privacy & Security, Transparency, Accountability) when designing agentic workflows or AI-driven security monitoring.

  - Implement agent-specific identities (e.g., Azure AD service principals) and enforce strict access policies for AI agents.

  - Enable real-time monitoring and anomaly detection for agent actions using Microsoft Defender for AI and Purview Data Security Posture Management.

  - Ensure human oversight and interruptibility for autonomous or semi-autonomous agents performing security-sensitive tasks.

  - Log all AI-driven decisions and actions for transparency, compliance, and auditability.

  - Define clear boundaries for agent capabilities and perform risk assessments for emergent behaviors or multi-agent collaboration.

### Recommended fields

The following fields are recommended for the **Security** work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- **Description:** Details of the security configuration or role.

- **Compliance Requirement:** Indicates if compliance requirements apply (e.g., GDPR, SOX).

- **Configuration Keys:** Relevant configuration keys for security.

- **Feature Management Keys:** Keys controlling security features.

- **Business Process Owner:** Person accountable for security setup.

- **Workstream Lead:** Person leading security configuration.

- **Success by Design Phase:** Phase relevant to security.

- **Catalog Status:** Status for catalog governance.

- **Process Sequence ID:** Unique sequence ID for process alignment.

### Procedure: Create a Security Work Item in Azure DevOps

Use the following steps to create a security work item in the Azure DevOps project using the default template for the Microsoft Business Process Catalog:

1. Go to your Azure DevOps project and open the **Deliverables backlog**.

2. Select **New Work Item** and choose **Security**.

3. Enter a clear **Description** of the security configuration or role.

4. Specify **Compliance Requirement** and add relevant **Configuration Keys** or **Feature Management Keys**.

5. Assign the security work item to the appropriate **Business Process Owner** or **Workstream Lead**.

6. Link the work item to related deliverables (e.g., business process, configuration, workflow).

7. Save the work item.

## Workshop

Workshops are interactive sessions designed for requirements gathering, solution design, process mapping, and decision-making. They foster collaboration and alignment among stakeholders and are a cornerstone of the Success by Design framework. The Business Process Catalog includes several types of workshops out-of-the-box, such as scenario board discovery workshops, storyline design review workshops, and detailed design workshops for each business process area. Additionally, generic workshops like the Solution Blueprint Review and Environment Strategy are included to support key Success by Design topics.

For a high-level overview of the default workshops and their structure, see [About workshops](#about-workshops). Note that the catalog's workshop list is not exhaustive—partners are expected to supplement these with workshops tailored to their industry expertise and methodology. The partner's approach should align with the Success by Design framework and incorporate Microsoft's recommended workshops, but also expand to address unique project needs.

Workshop work items should be used to catalog all critical collaborative sessions throughout the project lifecycle. For standard workshops included in the catalog, use the provided work items to track planning, delivery, and outcomes. For custom or partner-specific workshops, create dedicated work items to capture objectives, agenda, key questions, and decisions. This ensures visibility, supports audits, and provides a central artifact for linking related deliverables such as requirements, configurations, and testing activities.

### Workshops for agents and agentic automation

As organizations adopt AI agents and agentic automation, it is important to approach workshops with a process-first mindset. While it is appropriate to conduct detailed workshops about a specific agent when necessary (for example, designing a Copilot for a particular business scenario), we recommend prioritizing workshops that focus on reshaping and optimizing business processes to become frontier firms. The goal should be to identify opportunities where agents and AI can drive transformation, streamline workflows, and elevate business outcomes—not simply to implement a specific agent or feature.

Workshops should encourage stakeholders to think holistically about how automation, AI, and agents can be embedded within end-to-end processes, supporting strategic objectives and organizational change. By focusing on process innovation, teams can ensure that agentic solutions are aligned with business goals, scalable across the enterprise, and governed by responsible AI principles. Partners and project teams should use workshops to challenge existing practices, explore new operating models, and design processes that leverage the full potential of AI and automation—rather than limiting the conversation to the technical details of a single agent.

### Examples

- Fit/Gap workshop for Order to Cash process.

- Design workshop for integration architecture.

- Workshop to define lead qualification criteria and scoring model.

- Session to design case escalation paths and SLA rules.

- Workshop to plan preventive maintenance schedules and resource allocation.

### Success by Design guidelines

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

### Recommended fields

The following fields are recommended for the **Workshop** work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- **Description:** Details of the workshop purpose and scope.



- **Agenda:** Expected content to be covered in the workshop.

- **Workshop Assumptions:** Pre-requisites and assumptions for the workshop.

- **Key Questions:** Questions to be addressed during the workshop.

- **Microsoft Workshop Type:** Type of workshop based on Microsoft methodology.

- **Partner Workshop Type:** Type of workshop based on partner methodology.

- **Business Process Owner:** Person accountable for the workshop.

- **Workstream Lead:** Person leading the workshop.

- **Success by Design Phase:** Phase relevant to the workshop.

- **Catalog Status:** Status for catalog governance.

- **Process Sequence ID:** Unique sequence ID for process alignment.

### Procedure: Create a Workshop in Azure DevOps

Use the following steps to create a workshop work item in the Azure DevOps project using the default template for the Microsoft Business Process Catalog:

1. Go to your Azure DevOps project and open the **Deliverables backlog**.

2. Select **New Work Item** and choose **Workshop**.

3. Enter a clear **Description** of the workshop.

4. Add **Agenda**, **Workshop Assumptions**, and **Key Questions**.

5. Specify **Microsoft Workshop Type** and **Partner Workshop Type**.

6. Assign the workshop to the appropriate **Business Process Owner** or **Workstream Lead**.

7. Link the work item to related deliverables (e.g., business process, configuration, workflow).

8. Save the work item.

## Deliverable

Deliverables are tangible outputs produced as part of a Dynamics 365 project, representing key milestones, artifacts, or work products that drive project progress and quality assurance. The Business Process Catalog includes standard/mandatory Success by Design deliverables out-of-the-box, such as the **Solution Blueprint** and **Environment Strategy**. These deliverables are foundational for governance and are required for every implementation.

**Difference between Document and Deliverable Work Item Types:**

- **Deliverable work items** are used to track major project outputs that are typically aligned with the statement of work (SOW) and contractual commitments to the customer. Examples include the Solution Blueprint, Environment Strategy, and other milestone artifacts.

- **Document work items** are used to catalog supporting materials, reference guides, strategy documents, and other documentation that may not be contractual deliverables but are essential for implementation, governance, or user enablement.

Use Deliverable work items for anything that is explicitly promised in the contract or SOW, or is required by Success by Design. Use Document work items for additional materials, guides, or reference content created throughout the project.

Partners should note that deliverables typically align with what is expressed in the contract with the customer, but additional deliverables may be created as the project evolves to address new requirements, risks, or opportunities.

Deliverable work items should be used to catalog all major outputs and milestones required by the project, especially those specified in the SOW or Success by Design framework. For standard deliverables included in the catalog, use the provided work items to track completion and updates. For custom or additional deliverables, create dedicated work items to capture the purpose, scope, and links to related documentation, testing, and configuration activities. This ensures visibility, supports audits, and provides a central artifact for linking to requirements, workshops, and other deliverables.

### Examples

- Solution blueprint document for Concept to Market.

- Configuration workbook for Finance module.

- Configuration workbook for SLA and routing rules.

- Blueprint for resource scheduling optimization.

### Success by Design guidelines

- Link deliverables to workstreams and acceptance criteria.

- Use standard naming conventions for traceability.

- Validate completeness before sign-off.

### Recommended fields

The following fields are recommended for the **Deliverable** work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- **Description:** Details of the deliverable to be produced.

- **Microsoft References:** Links to Microsoft documentation or Learn articles.

- **Partner References:** Links to partner documentation.

- **Business Process Owner:** Person accountable for the deliverable.

- **Workstream Lead:** Person leading the deliverable creation.

- **Success by Design Phase:** Phase relevant to the deliverable.

- **Catalog Status:** Status for catalog governance.

- **Process Sequence ID:** Unique sequence ID for process alignment.

### Procedure: Create a Deliverable in Azure DevOps

Use the following steps to create a deliverable work item in the Azure DevOps project using the default template for the Microsoft Business Process Catalog:

1. Go to your Azure DevOps project and open the **Deliverables backlog**.

2. Select **New Work Item** and choose **Deliverable**.

3. Enter a clear **Description** of the deliverable.

4. Add any **Microsoft References** or **Partner References**.

5. Assign the deliverable to the appropriate **Business Process Owner** or **Workstream Lead**.

6. Link the work item to related deliverables (e.g., business process, configuration, workflow).

7. Save the work item.

## Testing

Testing work items are used to triage and plan validation activities for Dynamics 365 implementations. These work items help teams organize and track the scope of testing before actual test cases, test plans, or test suites are created. Testing ensures that solution functionality, performance, security, and compliance requirements are met prior to go-live.

The Business Process Catalog **does not include any testing work items out-of-the-box**. Instead, teams should create testing work items as needed to capture requirements, plan scenarios, and link to related deliverables. These work items serve as a bridge between requirements and formal test artifacts, supporting traceability and governance.

Testing work items should be used to catalog all planned validation activities, including functional, performance, security, integration, and user acceptance testing. When a requirement or need for testing is identified throughout the project, create a testing work item to document the scope, objectives, and acceptance criteria. As the project progresses, link these work items to actual test cases, test plans, or test suites for execution and reporting. This approach ensures comprehensive coverage and supports auditability.

### Examples

- Test case for purchase order registration workflow.

- Performance test for high-volume transaction posting.

- Test case for quote creation from opportunity with discount approval.

- Scenario to validate SLA breach escalation workflow.

- Test mobile app functionality for offline work order updates.

### Success by Design guidelines

- Include unit, integration, performance, security, and user acceptance scenarios in the testing plan.

- Map tests to requirements, configurations, workflows, and enhancements for traceability.

- Automate testing where possible using RSAT, Power Platform test tools, or similar frameworks.

- Document acceptance criteria and expected results for each test.

- Link testing work items to related deliverables for auditability and governance.

- For agentic AI and automation, design tests to evaluate:

  - AI agent reliability, safety, and compliance with Responsible AI principles.

  - Transparency and traceability of agent decisions and actions.

  - Human oversight for autonomous or semi-autonomous features.

  - Performance and scalability of agentic workflows under real-world conditions.

  - Security and privacy risks associated with AI-driven automation.

  - Use testing work items to plan and document evaluations of AI models, prompts, and agentic features, ensuring ethical and responsible deployment.

### Recommended fields

The following fields are recommended for the **Testing** work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- **Description:** Details of the testing activity.

- **Work Instructions:** Steps required to perform the test.

- **Acceptance Criteria:** Conditions that must be met for successful testing.

- **Automation Status:** Status of regression test automation.

- **Business Process Owner:** Person accountable for testing.

- **Workstream Lead:** Person leading the testing activity.

- **Success by Design Phase:** Phase relevant to testing.

- **Catalog Status:** Status for catalog governance.

- **Process Sequence ID:** Unique sequence ID for process alignment.

### Procedure: Create a Testing Work Item in Azure DevOps

Use the following steps to create a testing work item in the Azure DevOps project using the default template for the Microsoft Business Process Catalog:

1. Go to your Azure DevOps project and open the **Deliverables backlog**.

2. Select **New Work Item** and choose **Testing**.

3. Enter a clear **Description** of the testing activity.

4. Add **Work Instructions** and **Acceptance Criteria**.

5. Specify **Automation Status** if applicable.

6. Assign the testing work item to the appropriate **Business Process Owner** or **Workstream Lead**.

7. Link the work item to related deliverables (e.g., business process, configuration, workflow).

8. Save the work item.

# Business process catalog work items

This article describes introduces the Microsoft Business Process catalog tree and related work items in Azure DevOps. It describes the custom work item types included in the default template which can be used to help effectively manage a Dynamics 365 project using Azure DevOps. The Azure DevOps template is designed to follow the Success by Design framework with a process-focused approach.

## Introduction

The Business Process Catalog tree represents the **"what"** of a Dynamics 365 implementation. It provides a structured hierarchy of processes that define the scope of work for a project. This tree is designed to ensure clarity and consistency across implementations by organizing processes into logical levels. At its core, the catalog helps teams understand business operations before diving into system configuration or customization, supporting a fit-to-standard approach that accelerates delivery and reduces risk.

## Levels in the catalog

The tree is organized into six levels, each offering increasing granularity:

- **Level 1 – End-to-End Processes:** Broad business capabilities such as "Order to Cash" or "Source to Pay."

- **Level 2 – Process Areas:** Logical groupings within an end-to-end process (e.g., "Manage Sales Orders").

- **Level 3 – Business Processes:** Specific functions that describe what the business does, system-agnostic and reusable across industries.

- **Level 4 – Scenarios or Patterns:** Variations of processes for different industries or solution approaches.

- **Level 5 – System Processes:** Detailed steps tied to specific forms or pages in Dynamics 365.

- **Level 6 – Test Cases:** Actions for validating functionality during testing phases.

This layered structure ensures that projects can start at a high level and drill down to detailed, actionable items as needed.

## Using the tree in Azure DevOps

In Azure DevOps, the catalog tree is implemented through custom work item types that mirror these levels. Each level corresponds to a work item type (e.g., End-to-End, Process Area, Business Process, Scenario) and is linked hierarchically to maintain traceability. This structure enables teams to manage scope, track progress, and align deliverables with business objectives. By importing the catalog into Azure DevOps, organizations gain a standardized framework for planning, fit/gap analysis, and execution. It also supports integration with testing tools like RSAT, ensuring that processes documented in the tree flow seamlessly into test cases and quality assurance activities.

One of the primary functions of this tree is to define project scope. By mapping all business processes and their variations into a structured hierarchy, the catalog provides a clear view of what is in scope for the implementation. This helps stakeholders agree on boundaries early in the project, reduces ambiguity, and ensures that any gaps or enhancements are identified and managed systematically. Scope definition at this level also supports governance and change control, as any additions or modifications can be traced back to specific processes and their related work items.

## Benefits

- **Clear Scope Definition:** Provides a single source of truth for what is included in the project, reducing misunderstandings and scope creep.

- **Traceability and Governance:** Links every process to related work items, deliverables, and test cases, enabling better oversight and compliance.

- **Accelerated Fit/Gap Analysis:** Helps teams quickly identify standard versus custom requirements, improving decision-making and reducing delays.

- **Improved Quality Assurance:** Ensures that test cases align with documented processes, supporting robust validation and minimizing defects.

- **Consistency Across Projects:** Establishes a repeatable framework that can be applied to multiple implementations, promoting best practices and efficiency.

## End-to-end process

The top-level node of the Business Process Catalog. It represents a complete business capability spanning multiple functional domains, systems, and stakeholders. Provides highest-level context for related Process Areas and clarifies business outcomes, boundaries, and dependencies.

The top-level node of the Business Process Catalog represents a **complete business capability** spanning multiple functional domains, systems, and stakeholders. It provides the highest-level context for related Process Areas and clarifies business outcomes, boundaries, and dependencies.

### Standard End-to-End Processes

The catalog includes 15 industry-standard End-to-End processes that cover the full spectrum of business operations.

1. Acquire to dispose
2. Administer to operate
3. Case to resolution
4. Concept to market
5. Design to retire
6. Forecast to plan
7. Hire to retire
8. Inventory to deliver
9. Order to cash
10. Plan to produce
11. Project to profit
12. Prospect to quote
13. Record to report
14. Service to deliver
15. Source to pay

**Recommendation:** Customers and partners should **not add new End-to-End processes**. Instead, align to these existing processes to maintain consistency and leverage standard guidance. You can rename existing processes.

## Scoping

We recommend that End-to-End processes are scoped very early—ideally during sales and pre-sales phases before an Azure DevOps project even exists. This early alignment ensures clarity on project boundaries, accelerates fit/gap analysis, and supports accurate solution design.

By default, all end-to-end process work items have the **Scope** field set to **10-Unspecified**. Teams can update this field to one of three values:

- **20-In Scope** – The process is part of the implementation.

- **30-Out of Scope** – The process exists but will not be implemented.

- **40-Not Applicable** – The business does not perform this process at all. 
  For example, a retailer might mark the entire *Plan to Produce* process as **40-Not Applicable** because they do not manufacture products.

Administer to Operate is a critical End-to-End process that should be in scope for every Dynamics 365 project. This process represents the IT and operational backbone of an organization, encompassing activities such as environment management, security administration, monitoring, and compliance. It is where the entire Success by Design framework is embedded, particularly under the Implement Solutions area. These activities ensure that the solution is deployed, governed, and maintained according to best practices. Treating Administer to Operate as a formal process guarantees that technical and operational readiness is not overlooked, reducing risk and enabling sustainable operations post go-live.

## Process Area

A **Process Area** is the second level in the Business Process Catalog hierarchy. It represents a **logical grouping of related activities** within an End-to-End process, making the catalog easier to navigate and consume. Each Process Area contributes to the overall objective of the End-to-End process and often aligns loosely with certain roles or personas in the organization, helping clarify accountability.

### Standard Process Areas

The catalog includes more than 90 predefined process areas across the 15 End-to-End processes. These areas are designed to cover common business functions and should be used as-is for consistency.

**Recommendation:** Customers and partners should **not create new Process Areas** unless approved by the Business Process Excellence team. Aligning to the standard set ensures governance and compatibility with Success by Design principles.

#### Strategy areas 

Every End-to-End process includes a "strategy" area that focuses on planning, setup, and configuration activities. While these may seem technical, they are true business processes because they have defined inputs, outputs, and governance requirements. For example, setting up financial dimensions or defining security roles involves decision-making, approvals, and alignment with organizational policies. These activities are not ad hoc—they follow structured steps, require stakeholder involvement, and impact downstream processes.

Moreover, many strategy-related processes occur only during major technology implementations or transformations, making them critical for success. Without proper governance and controls, misconfigured setups can lead to compliance risks, operational inefficiencies, and costly rework. Treating these as formal processes ensures accountability, traceability, and alignment with business objectives.

#### Analytics areas 

Similarly, each End-to-End process includes an Analytics area that represents activities performed after execution to measure performance, identify trends, and inform decisions. These processes are cyclical: insights from analytics often trigger changes in earlier processes, such as adjusting procurement strategies based on spend analysis or refining pricing models based on sales performance.

Analytics processes have clear inputs (transactional data), defined steps (aggregation, reporting, interpretation), and outputs (recommendations, dashboards, KPIs). They are essential for continuous improvement and strategic planning. By recognizing analytics as a formal process, organizations can ensure these activities are governed, documented, and linked to measurable outcomes rather than treated as informal reporting tasks.

### Scoping

Process Areas should be scoped early in the project lifecycle, ideally during discovery workshops and fit/gap analysis. This ensures clarity on which functional areas are included and helps prioritize solution design. Like End-to-End processes, the Scope field defaults to 10-Unspecified and can be updated to:

- **20-In Scope** – Included in implementation

- **30-Out of Scope** – Exists but excluded

- **40-Not Applicable** – Business does not perform this area

Within Administer to Operate, the Implement Solutions process area plays a pivotal role in project success. It includes tasks such as environment provisioning, deployment planning, and configuration management—all of which require structured governance. These are not optional technical steps; they are business-critical processes with defined inputs, outputs, and dependencies. Properly managing this area ensures alignment with organizational policies, compliance standards, and performance objectives. By documenting and scoping these areas early, teams can avoid last-minute surprises and maintain control throughout the implementation lifecycle.

## Process

A Business process is the third level in the Business Process Catalog hierarchy, the corresponding work item type is called a Process. It represents a specific function or activity that the business performs to achieve a defined outcome. Unlike End-to-End processes or Process Areas, Level 3 processes are more granular and actionable, making them essential for fit/gap analysis and solution design. These processes are system-agnostic, meaning they describe what the business does rather than how a specific application performs the task. This ensures they can be reused across industries and technologies.

**Example:**  
Within *Manage Sales Orders* (Process Area), a Business Process might be *Validate Order Pricing*, which includes steps for checking discounts, taxes, and compliance before confirming an order.

Business Processes form the foundation for **fit/gap analysis** because they define what the business needs before mapping to system capabilities. They enable traceability from high-level objectives down to detailed requirements, ensuring that every customization or enhancement is justified. By documenting these processes, teams can link them to test cases, KPIs, and compliance checks, creating a closed loop for governance and quality assurance.

Business Processes in Azure DevOps can be linked directly to **test cases and test plans**, enabling automated validation. This ensures that every scoped process is tested against its intended outcome, reducing risk and improving confidence in the solution.

### Standard business processes

The catalog includes over 600 predefined Business Processes across all End-to-End processes and Process Areas. These processes cover common operational activities and should be used as-is for consistency.

**Recommendation:** Customers and partners should not create new Business Processes unless absolutely necessary. When new processes are required, we recommend they are submitted to the Business Process Excellence team at Microsoft to evaluate and add the process to our standard catalog. You can submit requests for changes to the catalog at <https://aka.ms/businessprocesscatalogrequests>. Aligning to the standard set ensures governance, accelerates implementation, and supports Success by Design principles.

### Key fields on the processes

The following fields should be given special consideration for the process work items. The fields are arranged into three key field groups in the Azure DevOps template:

1\. Business Assignments

- **Business Process Owner** – Accountable for the process outcome.

- **Workstream Lead** – Oversees implementation activities for the process.

- **Subject Matter Expert (SME)** – Provides detailed knowledge and validation.

2\. Solution Details

- **Fit/Gap Status** – Indicates whether the process is supported out-of-the-box or requires customization.

- **Gap Solution Approach** – Documents how gaps will be addressed (e.g., configuration, extension, ISV solution).

3\. Planning Details

- **Baseline Complexity** – Standard complexity rating for the process.

- **Estimated Complexity** – Adjusted complexity based on project specifics.

- **Estimate** – Effort required to implement the process (hours or story points).

- **Estimated Project Impact** – Qualitative measure of how critical this process is to project success.

### Success by Design guidelines

- Always start with the assumption that the standard Dynamics 365 capabilities will meet business needs. Customizations should only be considered when a clear business value and compliance requirement justify deviation.

- For each Business Process, document whether it is supported out-of-the-box (Fit) or requires a solution approach (Gap). Use the Fit/Gap Status and Gap Solution Approach fields to maintain transparency and traceability.

- Push back on unnecessary extensions by validating against KPIs, regulatory requirements, and strategic objectives. Encourage configuration over code wherever possible.

- Every gap should have a documented rationale tied to measurable outcomes. Avoid "nice-to-have" customizations that increase complexity without delivering tangible benefits.

- Ensure gaps and their solutions are linked back to the Business Process and higher-level objectives. This supports governance and change control throughout the project lifecycle.

- Connect Business Processes to test cases in Azure DevOps to validate that fit/gap decisions are implemented correctly and meet business requirements.

## Scenario

A Scenario is the fourth level in the Business Process Catalog hierarchy and is always product-specific. It represents a concrete way of executing a Business Process using a specific Microsoft product or feature. If multiple products or features support the same Business Process, the catalog includes one scenario for each product-feature combination. This ensures clarity on how the solution is implemented and provides flexibility for customers and partners to choose the best fit.

Scenarios are the most common level for customers and partners to extend with industry-specific or organization-specific requirements. They allow tailoring without altering higher-level catalog nodes, maintaining governance while enabling innovation. Adding an Agent to support a Business Process—such as an AI-driven pricing assistant—would also occur at this level.

### Key fields on the scenarios

Similar to processes, the following fields should be given special consideration for the scenario work items. The fields are arranged into three key field groups in the Azure DevOps template:

1\. Business Assignments

- **Business Process Owner** – Accountable for the process outcome.

- **Workstream Lead** – Oversees implementation activities for the process.

- **Subject Matter Expert (SME)** – Provides detailed knowledge and validation.

2\. Solution Details

- **Fit/Gap Status** – Indicates whether the process is supported out-of-the-box or requires customization.

- **Gap Solution Approach** – Documents how gaps will be addressed (e.g., configuration, extension, ISV solution).

3\. Planning Details

- **Baseline Complexity** – Standard complexity rating for the process.

- **Estimated Complexity** – Adjusted complexity based on project specifics.

- **Estimate** – Effort required to implement the process (hours or story points).

- **Estimated Project Impact** – Qualitative measure of how critical this process is to project success.

### Scoping

Scenarios should be scoped during **solution architecture and design workshops**, after Business Processes have been confirmed. They are critical for defining how the system will meet specific requirements and for estimating effort accurately.

### Success by Design guidelines

- Extend at the Scenario level for industry or company-specific needs; avoid altering higher-level nodes.

- Document product and feature details clearly, including any AI agents introduced for automation or decision support.

- Validate scenarios against fit-to-standard principles—prefer configuration and standard features before custom code.

- Link scenarios to KPIs and compliance requirements to justify any extensions.

- For agent scenarios:

  - Define the agent's role, inputs, and outputs.

  - Ensure responsible AI principles are applied (transparency, fairness, security).

  - Document governance for agent lifecycle (training, monitoring, updates).

## System process

A System process is the fifth level in the Business Process Catalog hierarchy. It represents high-level steps tied to specific forms, pages, or system components in Dynamics 365 or related Microsoft technologies. These steps are not detailed click-by-click instructions but provide enough granularity to connect business requirements to technical execution. System Processes are product-specific, unlike Business Processes which are system-agnostic, and they focus on major actions rather than UI details. Currently, System Processes are available for selected End-to-End processes, and coverage will expand in future releases to ensure full alignment across the catalog.

System processes help ensure:

- **Traceability:** Linking business requirements to technical execution.

- **Testing integration:** Connecting to test cases for validation and automation.

- **Governance:** Providing transparency for compliance and audit requirements.

- **Future readiness:** Supporting agent-driven automation and RSAT integration.

### Success by Design guidelines

- Document every System Process that supports a Scenario to ensure traceability.

- Include form/page references and configuration details for clarity.

- Validate against fit-to-standard principles—avoid unnecessary customizations.

- Link System Processes to test cases for automated validation.

- For agent-driven automation, define governance for lifecycle management and monitoring.

## Test Case

A Test Case is the sixth level in the Business Process Catalog hierarchy. It represents a series of specific validation steps or actions performed within a System Process, designed to confirm that the system behaves as expected. Test Cases can be manual or automated, depending on the complexity, frequency, and criticality of the process being validated. Manual test cases are typically used for exploratory or one-time validations or configurations that do not change frequently, while automated test cases are preferred for business critical, regression, performance, and repetitive scenarios.

There are also different types of test cases, including:

- **Functional test cases** – Validate that a feature or process works as intended.

- **Integration test cases** – Ensure that multiple components or systems interact correctly.

- **Performance test cases** – Measure system responsiveness and scalability under load.

- **Security test cases** – Validate access controls, data protection, and compliance.

- **AI/Agent evaluation** – Assess accuracy, fairness, explainability, and reliability of AI-driven processes or agents.

This diversity ensures comprehensive coverage of both deterministic system behaviors and probabilistic AI outcomes, supporting robust quality assurance and compliance.

Test cases are critical in any Dynamics 365 deployment as they help ensure that:

- **Functional assurance:** Validate that configurations and customizations deliver the intended outcome.

- **AI/Agent evaluation:** For agent-driven scenarios, test cases include evaluation metrics and benchmarks to measure performance, fairness, and reliability across versions.

- **Continuous monitoring:** AI agents require ongoing evaluation because their behavior can change over time. Test cases provide a structured way to benchmark and monitor these changes.

> Currently, Test cases are available for selected end-to-end processes, and coverage will expand in future releases to ensure full alignment across the catalog.

### Key Fields on the Work Item

- **Steps** – Detailed click-by-click actions for execution (including AI-generated steps where applicable).

- **Expected Result** – Criteria for success.

- **Automation Indicator** – Indicates if the test is to be conducted manually, id automation is planned, or if it is full auotmated.

- **Evaluation Metrics** (for AI/agents) – Accuracy, latency, fairness, and compliance checks.

- **Run History** – Pass/fail statistics across cycles.

- **Status** – Draft, Active, Completed.

### Scoping

Test Cases should be created during **solution design and testing phases**, after System Processes are finalized. For AI/agents, evaluation test cases should be defined early and updated continuously as models evolve.

### Success by Design guidelines

- **Align Test Cases to Business Value:** Each test case should validate a critical business outcome or compliance requirement.

- **Leverage Automation:** Use RSAT for deterministic tests and Leapwork or similar tools for complex workflows.

- **For AI/Agents:**

  - Define evaluation criteria beyond functional correctness (e.g., fairness, explainability, performance).

  - Include both **offline evaluations** (benchmarking against historical data) and **online monitoring** (continuous performance tracking).

  - Document governance for agent lifecycle, including retraining and version comparisons.

- **Maintain Traceability:** Link test cases to System Processes, Scenarios, and Business Processes for full visibility.

- **Plan for Scalability:** Use test suites and plans in Azure DevOps to organize large volumes of test cases efficiently.

# Other Work Item Types in the business process catalog

## Tree

The Tree work item type serves as the structural backbone for organizing large groups of work items into logical hierarchies, delineating top-level nodes for backlog types such as Business Process Catalog, Deliverables, and Delivery Plan. It is intended for navigation, governance, and clarity across workstreams to enable consistent reporting. We do not recommend creating new Tree nodes beyond those provided in the standard template; instead, leverage existing hierarchy definitions to maintain consistency. Include Tree items as rows only when structural representation is required for catalog exports or visualization; omit them to keep the catalog lean. Future recommendations may suggest adding or modifying Tree nodes to support advanced reporting and AI-driven navigation. Use Tree items to avoid unnecessary proliferation, consolidating nodes for clarity and aligning with approved hierarchy definitions. Additionally, Tree structures play a critical role in supporting scaled agile planning and governance for enterprise programs.

### Included Trees

- **Business Process Catalog**: This tree defines the "why". Defines implementation by capturing core business processes for operations. Provides a structured hierarchy starting with system-agnostic levels—end-to-end processes, process areas—into detailed processes and patterns. Ensures alignment with business objectives and serves as the foundation for scoping and solution design

- **Deliverables**: This tree defines the "what". Represents tangible outputs required to tailor the solution, including configurations, workflows, integrations, and documentation. Deliverables are aligned with Success by Design principles, helping track requirements and convert them into actionable outputs for visibility and traceability throughout the project lifecycle

- **Delivery Plan**: This tree defines the "when and how". Outlines the project methodology and delivery approach. Organizes phases, workshops, timelines, milestones, and teams to plan and monitor execution. The plan integrates with visualization tools such as Gantt charts and roadmaps to track progress and dependencies

- **Objectives**: This three defines the "goals". Captures overarching goals and success criteria for the initiative. Includes executive objectives, program increments, and sprint-level targets. Aligns activities with strategic priorities by linking objectives to deliverables and processes, supporting governance and continuous progress tracking against business outcomes

## Folder

The Business Process Catalog includes predefined folders in certain trees to improve organization and navigation. For example, in the **Deliverables tree**, folders are provided for each **Area Path**, which represents functional areas. These folders help group related deliverables logically under their respective domains. 
**Sample from Finance Area:**

Finance

Accounting

Accounting

Asset financials

Inventory valuation

Organization structure

Accounts payable

Accounts payable

Expense management

Supplier management

Supplier trade allowances

This structure ensures clarity for stakeholders and simplifies reporting across functional areas.

We also recommend that partners create folders in the Delivery Plan tree to organize work items by iteration paths, phases, key milestones, or project stages. These folders provide a clear visual structure for planning and tracking progress without altering the underlying process taxonomy. When adding new folders, ensure alignment with governance standards to maintain consistency and avoid unnecessary complexity.

### Success by Design guidelines

- Use Folder items for structure and discoverability, not for documenting procedural steps or outcomes.

- Minimize proliferation; prefer a stable taxonomy (capability → module → process → scenario).

- Consolidate overlapping groupings and avoid duplicate work item names for multiple folders.

- Maintain traceability by linking Folder items to their parent Tree node and applying consistent naming conventions.

- Agentic AI considerations:

  - Design Folder names as interpretable labels that convey scope and context for AI-driven navigation and summarization. Include lightweight metadata for AI agents to infer relationships and generate dynamic recommendations.

### Recommended fields

The following fields are recommended for the **Folder** work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- **Title** – Display name of the folder.

- **Parent Tree** – Reference to the parent Tree node for traceability.

- **Folder Path** – Logical path for hierarchy navigation.

- **Purpose** – Brief description of the folder's scope.

- **Owner** – Responsible person or team for folder contents.

- **Visibility/Permissions** – Access scope for governance.

- **Review Cadence** – Frequency for review and archival.

- **Tags** – Labels for release phase or capability that can be queried

- **Catalog Status** – Active, Deprecated, or Future.

### Procedure: Create a folder work item in Azure DevOps

- Use the following steps to create a new Folder in your Azure DevOps project using the Microsoft Business Process Catalog template:

1. **Navigate to Boards**  
    Go to **Boards → Work Items** or the relevant backlog view where you want the folder to appear.

2. **Select New Work Item**  
    Click **New Work Item** and choose **Folder** from the list of available work item types.

3. **Enter Folder Details**

    - **Title:** Provide a clear, descriptive name for the folder (e.g., "Finance – Accounting").

    - **Parent Tree:** Link the folder to its parent node in the catalog hierarchy for traceability.

    - **Folder Path:** Specify the logical path (e.g., Deliverables\Finance\Accounting).

    - **Purpose:** Briefly describe the folder's scope (e.g., "Organizes deliverables for Finance area").

    - **Owner:** Assign responsibility for folder contents.

    - **Visibility/Permissions:** Set access controls if needed.

    - **Tags:** Add labels for filtering (e.g., release phase, capability).

    - **Catalog Status:** Mark as Active, Deprecated, or Future.

4. **Save the Folder**  
    Click **Save & Close** to create the folder. It will now appear in the backlog or tree view.

5. **Add Related Work Items**  
    Link relevant deliverables, documentation, or other work items under the folder for structured navigation.

6. **Verify Hierarchy**  
    Ensure the folder appears correctly in the catalog hierarchy and supports roll-up reporting.

## Functional Area

The **Functional Area** work item type represents a finer-grained categorization under a **Process Area**, grouping related features or sub-capabilities typically aligned to application modules, departments, or functional domains. It provides additional structure for **ownership**, **configuration deliverables**, and **reporting** without duplicating the process taxonomy defined in the Business Process Catalog.

Functional Areas are **not included out-of-the-box** in the catalog. They are recommended for use in the **Delivery Plan tree** to help organize work into logical groupings that reflect the functional areas of the project. This approach improves visibility for governance, planning, and estimation, especially in large implementations with multiple modules or workstreams.

### When to use functional areas

- Use Functional Area rows when you need visibility into **sub-domains** for governance, configuration planning, or reporting.

- Omit them if **Process Areas and tags provide sufficient granularity** for organizing work.

- Recommended for **Delivery Plan organization**, where they can map to **iteration paths, phases, or key milestones** for better tracking.

### Success by Design guidelines

- Use Functional Areas for **structure and discoverability**, not for documenting procedural steps or outcomes.

- Avoid unnecessary proliferation—**consolidate overlapping definitions** and maintain alignment with approved catalog hierarchy.

- Apply **consistent naming conventions** aligned to application modules or organizational domains.

- For **agentic AI considerations**, design Functional Area names as interpretable labels that convey scope and context for AI-driven navigation and summarization.

### Recommended fields

- **Title** – Display name of the functional area.

- **Parent Process Area** – Reference for traceability.

- **Purpose** – Brief description of the functional area's scope.

- **Owner** – Responsible person or team.

### Procedure: Create a Functional Area in Azure DevOps

Use the following steps to create a new Functional Area in your Azure DevOps project using the Microsoft Business Process Catalog template:

1. Go to **Boards → Work Items** or the relevant backlog view where you want the Functional Area to appear.

2. Click **New Work Item** and choose **Functional Area** from the list of available work item types.

3. **Enter Functional Area Details**

    - **Title:** Provide a clear, descriptive name for the functional area (e.g., "Accounts Payable").

    - **Parent Process Area:** Link the Functional Area to its parent Process Area for traceability.

    - **Purpose:** Briefly describe the scope (e.g., "Organizes work items for AP configuration and reporting").

    - **Owner:** Assign responsibility for this functional area.

    - **Tags:** Add labels for filtering (e.g., module, phase, capability).

    - **Catalog Status:** Mark as Active, Deprecated, or Future.

4. Click **Save & Close** to create the work item. It will now appear in the backlog or tree view.

5. Link relevant deliverables, configuration tasks, or documentation under the Functional Area for structured navigation.

6. Ensure the Functional Area appears correctly under its parent Process Area and supports roll-up reporting.

## Phase

The **Phase** work item type represents a major stage in the delivery lifecycle, providing structure for **planning**, **governance**, and **visibility** across the project timeline. Phases anchor time-bound deliverables, reviews, and decision gates, ensuring alignment with **Success by Design methodology**. They help teams visualize project stages (e.g., *Initiate*, *Prepare*, *Execute*, *Optimize*) and link related tasks, deliverables, and status reports for traceability.

Phases are **not included out-of-the-box** in the Business Process Catalog. We recommend partners create these under the **Delivery Plan tree** to align with their methodology and project approach. This improves clarity for stakeholders and supports structured reporting.

Recommendation on when to use phases

- Use Phase rows when you need to **visualize project stages** and organize work items by lifecycle.

- Map deliverables, tasks, and reviews to phases for **traceability and governance**.

- Avoid creating unnecessary custom phases—adhere to the standard phase model for consistency.

**Example:**

### Success by Design Guidelines

- Adopt the organization's standard phase model (*Initiate, Prepare, Execute, Optimize*).

- Define **clear entry and exit criteria** for each phase.

- Map deliverables (tasks, test plans, status reports) to phases for visibility.

- Use **phase gates** for decisions and risk mitigation.

### Recommended Fields

The following fields are recommended for the Phase work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- **Title** – Name of the phase (e.g., Prepare, Execute).

- **Duration** – Planned length of the phase (e.g., in days or weeks).

- **Estimate** – Effort required for activities within the phase (e.g., hours or story points).

- **Start Date** – Planned start date for the phase.

- **Target Date** – Planned completion date for the phase.

### Procedure: Create a Phase work item in Azure DevOps

Use the following steps to create a new Phase in your Azure DevOps project:

1. Go to **Boards → Work Items** or the relevant backlog view where you want the phase to appear.

2. Click **New Work Item** and choose **Phase** from the list of available work item types.

3. **Enter Phase Details**

    - **Title:** Provide the phase name (e.g., "Prepare").

    - **Phase Sequence:** Enter the numeric order (e.g., 2 for Prepare).

    - **Entry Criteria:** Define conditions required to start the phase.

    - **Exit Criteria:** Define conditions required to complete the phase.

    - **Owner:** Assign responsibility for governance.

    - **Linked Deliverables:** Add references to tasks, reports, and configuration items.

    - **Review Cadence:** Specify frequency for governance checks.

    - **Catalog Status:** Mark as Active, Deprecated, or Future.

4. Click **Save & Close** to create the work item. It will now appear in the backlog or Delivery Plan tree.

5. Associate deliverables, tasks, and reviews under the phase for structured navigation and reporting.

6. Ensure the phase appears correctly in the Delivery Plan tree and supports roll-up reporting.

## Task

The Task work item type represents a granular unit of work that advances a deliverable, configuration, or documentation item toward completion. It is action-oriented, time-bound, and traceable to parent catalog items such as Processes, Scenarios, or Workshops. Tasks are included by default in the Azure DevOps template for the Business Process Catalog. Modifications are recommended to align Task fields and workflow with catalog governance standards for consistency across implementations. Tasks ensure visibility and accountability throughout the delivery plan and should be reserved for work that impacts deliverables rather than minor notes or informal actions.

### Example

Configure price calculation parameters for sales orders in D365 Finance and validate with sample data.

### Success by Design guidelines

- Start Task titles with a verb to indicate action.

- Define a clear Definition of Done (DoD) and due date for each Task.

- Assign a single accountable owner and include dependencies or blockers.

- Link the Task to its parent item (Process, Scenario, or System Process) for traceability.

- Attach evidence upon completion (screenshots, documents, logs).

- Design Task metadata to support AI-driven prioritization and recommendations. Include clear labels and consistent taxonomy so AI agents can infer dependencies, predict delays, and suggest automation opportunities.

### Recommended fields

The following fields are recommended for the **Task** work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- Title – Clear, action-oriented name for the Task.

- Parent Link – Reference to the parent deliverable or catalog item.

- Owner – Person responsible for execution.

- Due Date – Target completion date.

- Dependencies – Work that must precede this Task.

- Definition of Done (DoD) – Criteria for completion.

- Status – Current state (New, Active, Closed).

- Tags – Labels for capability, release phase, or priority.

### Procedure: Create a Functional Area in Azure DevOps

Use the following steps to create a deliverable work item in the Azure DevOps project using the default template for the Microsoft Business Process Catalog:

1. Navigate to **Organization Settings \> Boards \> Process** in Azure DevOps.

2. Select the inherited process to customize.

3. Click **Work Item Types** and choose **New Work Item Type**.

4. Enter the name "Task" and set an icon and color for easy identification.

5. Configure fields: add required fields such as Title, Parent Link, Owner, Due Date, Dependencies, DoD, Status, and Tags.

6. Define workflow states (New, Active, Closed) with transitions.

7. Associate the Task work item type with relevant backlog levels for visualization.

8. Save and publish the process.

9. Verify in Boards by creating a sample Task linked to its parent item for traceability.

## Action Item

An Action Item represents a quick, discrete follow-up task that typically arises from meetings, workshops, or issue triage. It is short-lived, focused on ensuring completion of a specific action without requiring detailed estimation or complex planning. Action Items are included by default in the Business Process Catalog template and should be used for commitments that impact deliverables or decisions. They are ideal for capturing immediate actions that need accountability and visibility. Avoid using Action Items for major tasks or configuration work—reserve those for Task work item types.

### Example

Update the O2C workflow diagram to reflect new tax calculation service and circulate for review.

### Success by Design guidelines

- Use Action Items for quick actions that do not require detailed estimation or scheduling.

- Assign a single accountable owner and a clear due date for every Action Item.

- Capture context such as the originating meeting, decision, or issue to maintain traceability.

- Link Action Items to impacted catalog items (e.g., Processes, Scenarios, Deliverables) for governance.

- Close promptly and record outcomes or residual risks.

- **Agentic AI Considerations:** Design Action Item metadata to support AI-driven recommendations for prioritization and follow-up. Include clear labels and consistent taxonomy so AI agents can infer urgency and dependencies.

### Recommended fields

The following fields are recommended for the **Action Item** work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- **Title** – Clear, action-oriented name for the item.

- **Owner** – Person responsible for completion.

- **Due Date** – Target completion date.

- **Context** – Originating meeting, decision, or issue.

- **Impacted Items** – References to related catalog items.

- **Status** – Current state (New, Active, Closed).

- **Tags** – Labels for capability, release phase, or priority.

### Procedure: Create a Functional Area in Azure DevOps

Use the following steps to create an Action Item work item in the Azure DevOps project using the default template for the Microsoft Business Process Catalog:

- Navigate to **Organization Settings \> Boards \> Process** in Azure DevOps.

- Select the inherited process you want to customize.

- Click **Work Item Types** and choose **New Work Item Type**.

- Enter the name **Action Item** and set an icon and color for easy identification.

- Configure fields: Add required fields (Title, Owner, Due Date, Context, Impacted Items, Status, Tags).

- Define workflow states (New, Active, Closed) with simple transitions.

- Associate the Action Item work item type with relevant backlog levels for visibility.

- Save and publish the process.

- Verify in Boards by creating a sample Action Item linked to impacted catalog items for traceability.

## Bug

A Bug represents a defect detected during testing or operation, capturing observed versus expected behavior, scope, and severity. It tracks the work required to correct the defect and verify the fix. Bugs are included by default in the Business Process Catalog template and should be used for significant blockers or defects that cannot be resolved through normal workflow. Avoid logging minor questions or clarifications as Bugs; reserve this type for items that require structured resolution and governance. Future enhancements may include AI-driven triage capabilities and automated regression testing.

### Example

Incorrect VAT rounding when posting sales orders for reduced-rate items.

### Success by Design guidelines

- Provide reproducible steps and evidence (logs, screenshots); note environment and build/version.

- Assess business impact and severity; link to failing Test Case and impacted Scenarios.

- Document fix verification and regression coverage.

- Maintain clear state transitions (New → Active → Resolved → Closed) for governance.

- **Agentic AI Considerations**: Design Bug metadata to support AI-driven triage and prioritization. Include structured fields for severity, priority, and repro steps so AI agents can predict delays and recommend corrective actions.

### Recommended fields

The following fields are recommended for the **Bug** work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- **Title** – Clear, descriptive name of the defect.

- **Repro Steps** – Detailed steps to reproduce the issue.

- **System Info** – Environment details (build, version).

- **Severity/Priority** – Impact and urgency indicators.

- **Linked Test Cases** – References to associated validations.

- **Status** – Current state (New, Active, Resolved, Closed).

- **Tags** – Labels for capability, release phase, or module.

### Procedure: Create a Functional Area in Azure DevOps

Use the following steps to create a deliverable work item in the Azure DevOps project using the default template for the Microsoft Business Process Catalog:

- Navigate to **Organization Settings \> Boards \> Process** in Azure DevOps.

- Select the inherited process to customize.

- Click **Work Item Types**, then choose **New Work Item Type**.

- Enter name: **Bug**, set icon and color for easy identification.

- Configure fields: Add required fields (Title, Repro Steps, System Info, Severity, Priority, Linked Test Cases, Status, Tags).

- Define workflow states (New, Active, Resolved, Closed) with transitions.

- Associate Bug work item type with relevant backlog levels for visibility.

- Save and publish the process.

- Verify in Boards by creating a sample Bug linked to Test Cases for traceability.

## Risk

Risk represents a potential event or condition that could negatively impact project objectives such as timeline, scope, or budget. It requires proactive identification, probability and impact assessment, and mitigation planning to minimize adverse effects. Risks are included by default in the Business Process Catalog Azure DevOps template. Future inclusion of advanced AI-driven risk scoring and predictive analytics is planned to improve prioritization and automation. Use Risk items for significant uncertainties that could derail delivery or require contingency planning. Avoid using Risk for issues that have already occurred—those should be logged as Issues.

### Example

Delay in integration delivery may push UAT start and affect go-live readiness.

### Success by Design guidelines

- Use a scoring model (probability × impact) to quantify risk severity.

- Define clear triggers and early warning signs for monitoring.

- Assign an accountable owner and track mitigation and contingency actions with due dates.

- Review risks at phase gates and escalate high-severity risks promptly.

- **Agentic AI Considerations:** Design risk metadata to support AI-driven prioritization and predictive insights. Include structured fields for probability, impact, and mitigation status so AI can predict delays and recommend actions.

### Recommended fields

The following fields are recommended for the **Risk** work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- **Title** – Clear, descriptive name of the risk.

- **Probability / Impact** – Numeric or categorical scoring for severity.

- **Mitigation Plan** – Actions to reduce likelihood or impact.

- **Contingency Plan** – Fallback actions if risk materializes.

- **Owner** – Person accountable for monitoring and resolution.

- **Review Date** – Next checkpoint for reassessment.

- **Status** – Current state (Open, Mitigated, Closed).

- **Tags** – Labels for capability, release phase, or priority.

### Procedure: Create a Functional Area in Azure DevOps

Use the following steps to create a deliverable work item in the Azure DevOps project using the default template for the Microsoft Business Process Catalog:

- Navigate to **Organization Settings \> Boards \> Process** in Azure DevOps.

- Select the inherited process to customize.

- Click **Work Item Types** and choose **New Work Item Type**.

- Enter name: **Risk**, set icon and color for easy identification.

- Configure fields: Add required fields (Title, Probability, Impact, Mitigation Plan, Contingency Plan, Owner, Review Date, Status, Tags).

- Define workflow states (New, Active, Closed) with transitions.

- Associate Risk work item type with relevant backlog levels for visibility.

- Save and publish the process.

- Verify in Boards by creating a sample Risk linked to deliverables for traceability.

## Assumption

An Assumption records a condition believed to be true for planning or design and is used to surface dependencies and uncertainty early so teams can validate them during execution. It improves traceability by explicitly tying planning premises to the deliverables and schedules they affect. Assumptions are typically included by default in Business Process Catalog templates; keep the structure consistent across projects and avoid customizing the core workflow unless there is a clear governance need. When a template doesn't include Assumptions, plan to add them to enable validation and risk transparency rather than modifying other work item types to carry these details.

### Example

Customer master data will be migrated and validated before O2C testing begins.

### Success by Design guidelines

- Record the rationale and source for each assumption to make review and validation straightforward.

- Define the validation method and target date so owners know how and when confirmation will happen.

- Link each assumption to all dependent deliverables, processes, tests, or milestones to preserve traceability.

- Convert the assumption to an Issue immediately if it proves false, and update plans, owners, and dates accordingly.

- Establish a review cadence (e.g., phase gates or weekly checkpoints) to confirm status and retire stale entries.

- **Agentic AI considerations**: use structured fields (rationale, validation date, dependencies, status) so AI can flag conflicts, predict impact when deadlines slip, and nudge owners before validation is due.

### Recommended fields

The following fields are recommended for the **Assumption** work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- Title – concise statement of the assumption

- Rationale / Source – why this is believed and where it originated

- Validation method – how the team will confirm it (e.g., data load, sign‑off, test)

- Validation date – target date to complete validation

- Dependencies – linked deliverables or processes that rely on the assumption

- Status – open, validated, invalidated

- Tags – capability, phase, priority, or domain classification

### Procedure: Create a Functional Area in Azure DevOps

Use the following steps to create a deliverable work item in the Azure DevOps project using the default template for the Microsoft Business Process Catalog:

- Go to **Organization Settings** \> **Boards** \> **Process**, and select an **inherited** process to customize.

- Open **Work item types** and choose **New work item type**.

- Name it **Assumption** and select an icon/color.

- Add fields: **Title**, **Rationale/Source**, **Validation method**, **Validation date**, **Dependencies**, **Status**, **Tags**.

- Define simple states and transitions (e.g., **New → Active → Closed**) that align with governance.

- (Optional) Add rules (e.g., require **Validation date** when state = Active).

- Associate the type with the appropriate backlog or board queries for visibility.

- **Save** and **Publish** the process.

- Verify on **Boards** by creating a sample Assumption and linking it to the dependent items.

## Issue

An Issue represents a current problem that has occurred and may impact project delivery, scope, or quality. It differs from a Risk because an Issue is something that has already happened and requires immediate attention and resolution tracking. Issues are included by default in the Business Process Catalog template and should be used for significant blockers or defects that cannot be resolved through normal workflow. Avoid logging minor questions or clarifications as Issues; reserve this type for items that require structured resolution and governance. Future enhancements may include AI-driven impact analysis and automated escalation recommendations.

### Example

API documentation for tax service is incomplete, blocking integration testing.

### Success by Design guidelines

- Assign a single accountable owner and a clear due date for resolution.

- Capture the impact and scope of the Issue, including affected deliverables or processes.

- Document resolution steps and decisions for auditability.

- Link the Issue to related Risks, Change Requests, or impacted catalog items for traceability.

- **Agentic AI Considerations:** Structure metadata to support AI-driven triage and prioritization. Include fields for severity, dependencies, and deadlines so AI can predict delays and recommend escalation paths.

### Recommended fields

The following fields are recommended for the **Issue** work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- **Title** – Clear, descriptive name of the Issue.

- **Impact/Scope** – Details of affected areas and severity.

- **Resolution Steps** – Actions taken or planned to resolve the Issue.

- **Owner** – Person accountable for resolution.

- **Due Date** – Target date for closure.

- **Status** – Current state (New, Active, Resolved, Closed).

- **Tags** – Labels for capability, release phase, or priority classification.

### Procedure: Create a Functional Area in Azure DevOps

Use the following steps to create a deliverable work item in the Azure DevOps project using the default template for the Microsoft Business Process Catalog:

- Navigate to **Organization Settings \> Boards \> Process** in Azure DevOps.

- Select the inherited process to customize.

- Click **Work Item Types** and choose **New Work Item Type**.

- Enter the name **Issue** and set an icon and color for easy identification.

- Configure fields: Add required fields (Title, Impact/Scope, Resolution Steps, Owner, Due Date, Status, Tags).

- Define workflow states (New, Active, Resolved, Closed) with transitions aligned to governance.

- Associate the Issue work item type with relevant backlog levels for visibility.

- Save and publish the process.

- Verify in Boards by creating a sample Issue linked to impacted deliverables for traceability.

## Decision

A Decision work item captures an agreed choice that impacts project scope, design, or delivery. It documents the context, options evaluated, and rationale to ensure downstream traceability and governance. Decisions are included by default in the Business Process Catalog template and should be used for significant choices requiring auditability and linkage to impacted deliverables. Avoid logging minor clarifications or informal agreements; reserve this type for decisions that influence requirements, timelines, or solution architecture. Future enhancements may include AI-driven recommendations for decision impact analysis and automated follow-up actions.

### Example

Approve adoption of centralized tax calculation service across Order-to-Cash with phased rollout.

### Success by Design guidelines

- Record decision date, decision-maker(s), and options considered with rationale.

- Link impacted catalog items and define follow-up actions such as Action Items or Change Requests.

- Store supporting evidence (meeting notes, design documents) for auditability.

- **Agentic AI Considerations:** Structure metadata to support AI-driven insights for decision impact analysis and proactive recommendations. Include clear fields for context, rationale, and dependencies so AI can predict downstream effects and suggest mitigations.

### Recommended fields

The following fields are recommended for the **Decision** work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- Title – Clear descriptive name of the decision.

- Decision Date – When the decision was made.

- Approver(s) – Person(s) or role(s) who approved.

- Options/Rationale – Alternatives considered and reasons for selection.

- Impacted Items – References to related processes, deliverables, or work items.

- Status – Current state (Open, Approved, Implemented).

- Tags – Labels for capability, phase, or priority classification.

### Procedure: Create a Functional Area in Azure DevOps

Use the following steps to create a deliverable work item in the Azure DevOps project using the default template for the Microsoft Business Process Catalog:

1. Navigate to **Organization Settings \> Boards \> Process** in Azure DevOps.

2. Select the inherited process to customize.

3. Click **Work Item Types** and choose **New Work Item Type**.

4. Enter name: **Decision**, set icon and color for easy identification.

5. Configure fields: Add required fields (Title, Decision Date, Approver(s), Options/Rationale, Impacted Items, Status, Tags).

6. Define workflow states (New, Approved, Implemented) with transitions aligned to governance.

7. Associate Decision work item type with relevant backlog levels for visibility.

8. Save and publish the process.

9. Verify in Boards by creating a sample Decision linked to impacted catalog items for traceability.

## Change Request

A Change Request represents a formal proposal to modify scope, design, configuration, or schedule after the original baseline has been established. It ensures structured impact analysis and governance approval before changes are implemented. Change Requests are included by default in the Business Process Catalog template and should generally remain as-is for consistency. We do not recommend modifying this work item type beyond adding organization-specific fields if absolutely necessary, as it supports standardized governance workflows. Future enhancements may include AI-driven impact analysis and automated approval workflows to streamline governance.

### Example

Add an approval step for high-value orders above a configurable threshold.

### Success by Design guidelines

- Describe the change and its drivers, including business justification.

- Assess impact on processes, data, testing, and timeline before submission.

- Route through defined approval workflow and record decision outcomes.

- Track implementation tasks and validation tests.

- **Agentic AI Considerations:** Structure metadata to support AI-driven recommendations for impact analysis and prioritization. Include fields for dependencies, affected deliverables, and deadlines to predict downstream effects and suggest mitigations.

### Recommended fields

The following fields are recommended for the **Change Request** work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- **Title** – Concise description of requested change

- **Requestor** – Person initiating the change

- **Description** – Explanation of proposed change

- **Impact Analysis** – Effect on scope, schedule, cost, and risk

- **Approval** – Decision status and approver(s)

- **Implementation Plan** – Tasks, owners, and target dates

- **Status** – Current state (New, Approved, Implemented)

- **Tags** – Labels for capability, phase, and priority classification

### Procedure: Create a Functional Area in Azure DevOps

Use the following steps to create a deliverable work item in the Azure DevOps project using the default template for the Microsoft Business Process Catalog:

1. Navigate to **Organization Settings \> Boards \> Process** in Azure DevOps.

2. Select the inherited process to customize.

3. Click **Work Item Types** and choose **New Work Item Type**.

4. Enter name: **Change Request**, set icon and color for easy identification.

5. Configure fields: Add required fields (Title, Requestor, Description, Impact Analysis, Approval, Implementation Plan, Status, Tags).

6. Define workflow states (New → Approved → Implemented) with transitions aligned to governance.

7. Associate Change Request work item type with relevant backlog levels for visibility.

8. Save and publish the process.

9. Verify in Boards by creating a sample Change Request linked to impacted deliverables for traceability.

## Status Report

Status Report represents a structured summary of project progress, risks, issues, decisions, and outlook for a specific period or phase. It provides leadership with KPIs and actionable insights for governance and decision-making. Status Reports are included by default in the Business Process Catalog template and should be used consistently for visibility and compliance. Future enhancements may include AI-driven summarization and predictive insights for trend analysis. Recommend modifying only for additional metadata fields aligned with organizational reporting standards, not for core workflow changes.

### Example

Weekly Order to Cash implementation status: completed configuration items, open defects, risk trend, upcoming milestones.

### Success by Design guidelines

- Use a standard template with quantitative metrics (e.g., burnup charts, defect density, test pass rate).

- Highlight variances and corrective actions; align reporting cadence with governance checkpoints (phase gates, steering meetings).

- Keep reports concise with visuals and archive for traceability.

- **Agentic AI Considerations:** Include structured fields for KPIs, risks, and decisions to enable AI-driven summarization and predictive analytics. Ensure data is normalized and tagged for trend detection, anomaly alerts, and automated executive summaries.

### Recommended fields

The following fields are recommended for the **Status Report** work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- **Title** – Clear name for the Status Report (e.g., "Week 47 Status Report").

- **Reporting Period** – Start and end dates

- **Summary** – Narrative of progress and outlook

- **KPIs** – Quantitative indicators (% completion, defect counts)

- **Risks / Issues / Decisions** – Highlights by category

- **Next Steps** – Planned actions for upcoming period

- **Status** – Current state (Draft, Published, Archived)

- **Tags** – Labels for capability, phase, or priority classification

### Procedure: Create a Functional Area in Azure DevOps

Use the following steps to create a deliverable work item in the Azure DevOps project using the default template for the Microsoft Business Process Catalog:

1. Navigate to **Organization Settings \> Boards \> Process** in Azure DevOps.

2. Select the inherited process to customize.

3. Click **Work Item Types**, then choose **New Work Item Type**.

4. Enter name: **Status Report**, set icon and color for easy identification.

5. Configure fields: Add required fields (Title, Reporting Period, Summary, KPIs, Risks, Issues, Decisions, Next Steps, Status, Tags).

6. Define workflow states: Draft → Published → Archived with transitions aligned to governance.

7. Associate Status Report work item type with relevant backlog levels for visibility.

8. Save and publish the process.

9. Verify in Boards by creating a sample Status Report linked to phase deliverables for traceability.

## Test Plan

A Test Plan represents the structured approach for validating processes and scenarios during a specific milestone or release. It defines the overall testing strategy, scope, environments, schedules, and exit criteria to ensure quality and compliance. Test Plans will be included in the future in the Business Process Catalog template and can be used consistently for governance and traceability. Future enhancements may include AI-driven predictive analytics for test coverage and automated readiness checks. Modification is recommended only for adding organization-specific fields or reporting attributes, not for altering the core workflow.

### Example

Regression Test Plan for Sales scenarios covering pricing, taxation, and availability.

### Success by Design guidelines

- Describe objectives, scope, and coverage clearly.

- Specify environments, data sets, and entry/exit criteria for each plan.

- Link Test Suites and Test Cases to maintain traceability.

- Track execution status and defects throughout the lifecycle.

- **Agentic AI Considerations:** Structure metadata to enable AI-driven insights for coverage gaps, risk-based prioritization, and predictive readiness scoring. Include normalized fields for KPIs and tags to support automated dashboards and anomaly detection.

### Recommended fields

The following fields are recommended for the **Test Plan** work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- **Title** – Clear name for the Test Plan (e.g., "Regression Test Plan – Sales").

- **Objectives/Scope** – Purpose and boundaries of testing.

- **Environments/Data** – Details of environments and data sets used.

- **Acceptance Criteria** – Exit conditions for completion.

- **Linked Test Suites** – References to associated suites.

- **Schedule** – Timeline and milestones.

- **Status** – Current state (Draft, Active, Completed).

- **Tags** – Labels for capability, phase, or priority classification.

### Procedure: Create a Functional Area in Azure DevOps

Use the following steps to create a deliverable work item in the Azure DevOps project using the default template for the Microsoft Business Process Catalog:

1. Navigate to **Organization Settings \> Boards \> Process** in Azure DevOps.

2. Select the inherited process to customize.

3. Click **Work Item Types** and choose **New Work Item Type**.

4. Enter name: **Test Plan**, set icon and color for easy identification.

5. Configure fields: Add required fields (Title, Objectives/Scope, Environments/Data, Acceptance Criteria, Linked Test Suites, Schedule, Status, Tags).

6. Define workflow states: Draft → Active → Completed, with transitions aligned to governance.

7. Associate Test Plan work item type with relevant backlog levels for visibility.

8. Save and publish the process.

9. Verify in Boards by creating a sample Test Plan linked to Test Suites and Test Cases for traceability.

## Test Suite

A Test Suite represents a structured grouping of related Test Cases within a Test Plan to validate a specific feature, requirement, or user story. It enables coherent execution of multiple test cases under a common objective, improving traceability and reporting for quality assurance. Test Suites are included by default in the Business Process Catalog template and should be used consistently for organizing test coverage. Future enhancements may include AI-driven recommendations for suite composition and automated sequencing. Modification is recommended only for adding organization-specific metadata fields, not altering core workflow.

### Example

Sales Order Validation Suite containing tax, pricing, and availability Test Cases.

### Success by Design guidelines

- Organize suites by scenario, capability, or feature for clarity.

- Avoid overlapping membership; keep suite contents mutually exclusive.

- Define sequencing and dependencies for execution order.

- Link each Test Suite to its parent Test Plan for traceability.

- **Agentic AI Considerations:** Include structured metadata (scenario, priority, dependencies) to enable AI-driven optimization of suite composition, predictive coverage analysis, and automated execution planning.

### Recommended fields

The following fields are recommended for the **Test Suite** work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- **Title** – Clear name for the Test Suite (e.g., "Sales Order Validation Suite").

- **Parent Test Plan** – Reference to the overarching Test Plan.

- **Membership** – List of Test Cases included in the suite.

- **Sequence** – Execution order and dependencies.

- **Run History** – Pass/fail statistics across cycles.

- **Status** – Current state (Draft, Active, Completed).

- **Tags** – Labels for capability, phase, priority classification.

### Procedure: Create a Functional Area in Azure DevOps

Use the following steps to create a deliverable work item in the Azure DevOps project using the default template for the Microsoft Business Process Catalog:

1. Navigate to **Organization Settings \> Boards \> Process** in Azure DevOps.

2. Select the inherited process to customize.

3. Click **Work Item Types**, then choose **New Work Item Type**.

4. Enter name: **Test Suite**, set icon and color for easy identification.

5. Configure fields: Add required fields (Title, Parent Test Plan, Membership, Sequence, Run History, Status, Tags).

6. Define workflow states: Draft → Active → Completed with transitions aligned to governance.

7. Associate Test Suite work item type with relevant backlog levels for visibility.

8. Save and publish the process.

9. Verify in Boards by creating a sample Test Suite linked to its parent Test Plan and Test Cases for traceability.

## Ticket

A Ticket represents a support or service request raised by a user to address break/fix issues, configuration changes, or assistance related to catalog processes or environments. It facilitates triage, assignment, and resolution tracking under agreed SLAs. Tickets are included by default in the Business Process Catalog template and should be used consistently for operational support and governance. Future enhancements may include AI-driven routing and automated SLA monitoring. Modification is recommended only for adding organization-specific metadata fields, not altering the core workflow.

### Example

Provision access for test users to D365 Finance UAT environment; assign security roles per persona.

### Success by Design guidelines

- Use clear categories (e.g., access, environment, data, defect) to speed routing.

- Capture SLA targets and priority; link to impacted processes or deliverables for traceability.

- Record resolution notes and verification evidence for auditability.

- Maintain consistent naming conventions for easy query and reporting.

- Structure metadata to enable AI-driven triage, prioritization, and SLA compliance checks. Include normalized fields for category, priority, and impacted items so AI can predict delays and recommend escalation paths.

### Recommended fields

The following fields are recommended for the **Ticket** work item type and included by default in the Azure DevOps template for the Microsoft Business Process Catalog:

- **Title** – Clear description of the request.

- **Requester** – Person initiating the ticket.

- **Category/Priority** – Type and urgency for routing.

- **SLA** – Target response and resolution times.

- **Impacted Items** – Linked processes or deliverables.

- **Resolution** – Outcome and verification evidence.

- **Status** – Current state (New, Active, Resolved, Closed).

- **Tags** – Labels for capability, release phase, or priority classification.

### Procedure: Create a Functional Area in Azure DevOps

Use the following steps to create a deliverable work item in the Azure DevOps project using the default template for the Microsoft Business Process Catalog:

1. Navigate to **Organization Settings \> Boards \> Process** in Azure DevOps.

2. Select the inherited process to customize.

3. Click **Work Item Types**, then choose **New Work Item Type**.

4. Enter name: **Ticket**, set icon and color for easy identification.

5. Configure fields: Add required fields (Title, Requester, Category/Priority, SLA, Impacted Items, Resolution, Status, Tags).

6. Define workflow states: **New → Active → Resolved → Closed**, aligned to governance.

7. Associate Ticket work item type with relevant backlog levels for visibility.

8. Save and publish the process.

9. Verify in Boards by creating a sample Ticket linked to impacted catalog items for traceability.

## User Story

A user story is a concise and informal description of a software feature from the perspective of the end user. It is a fundamental component of agile development, designed to capture the user's needs and the value that the feature will provide. User stories are typically written in simple language to ensure that all stakeholders, including non-technical team members, can understand them. The standard format for documenting a user story is: "As a \[role/persona\], I need to \[task to be performed\] in order to \[achieve specific results\]." This format helps to clearly define the user, their goal, and the benefit they will receive, ensuring that the development team has a clear understanding of the requirements and the desired outcome.

The Microsoft Business Process Catalog does not include any default user stories. It is recommended to document user stories as part of the storyboarding process in the initial discovery. Additional user stories may be captured during the design phase as well. Each business process that is in scope should have at least one user story, but could have multiple.

**Naming convention**

As a \[name of role/persona\] I need to \[task to be performed\] in order to \[achieve specific results\]

<span class="mark">Recommend structures/fields. We would recommend to use the work item type for User story and create them as child under</span>

<span class="mark">Examples</span>

## Epic

## Features
