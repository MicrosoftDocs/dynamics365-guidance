---
title: Overview of the Business Process Catalog Levels
description: Dive into the structured hierarchy of the business process catalog, including examples and best practices for naming and organizing processes.
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

### Naming convention

The naming pattern for end-to-end processes is *This to That*, where *This* is the starting point or trigger of the process, and *That* is the end point or outcome.

### Examples

The following list provides a few examples of this level of the business process catalog.

- Order to cash
- Source to pay
- Hire to retire

### What an end-to-end process is

The following table outlines key properties of an end-to-end process.

|Property|Description  |
|---------|---------|
|Comprehensive  |An end-to-end process covers the entire lifecycle of a business operation.|
|Cross-functional |An end-to-end process involves multiple departments or functions.|
|Outcome-oriented |An end-to-end process focuses on delivering a specific business outcome.|

## What an end-to-end process isn't

The following list outlines what an end-to-end process isn't.

- A single department's workflow.
- A narrowly defined task or activity.
- A process without a clear start and end point.

## Level two: Business process areas

A business process area is a key component or phase within an end-to-end process. It represents a significant grouping of related activities that contribute to the overall objective. It provides a logical way to group business processes, and it makes the business process catalog easier to navigate.

Business process areas are often loosely associated with certain personas or roles within the organization. While this connection isn't a strict rule, it serves as a helpful guiding principle when mapping activities to specific responsibilities across teams. This approach enables clearer accountability and makes the process catalog more intuitive to navigate.

When naming business process areas, always prioritize consistency to ensure clarity and ease of use throughout the process catalog. While aligning with industry standards is beneficial, it's secondary to maintaining a clear and understandable naming convention for business users. Above all, the name of each business process area should make it immediately apparent to the business user what activities or responsibilities the process area encompasses.

> [!NOTE]
> If an external service provider or partner wants to propose a new business process area, this request requires special approval and further discussion with the business process excellence team. Don't make such additions unilaterally to ensure consistency and maintain the integrity of the overall process catalog.

### Naming convention for business process areas

The name must use a verb-noun pair. You can use two verb-noun pairs if necessary.

### Examples of business process areas

The following list provides a few examples of this level of the business process catalog.

- Create and manage sales (within *Order to cash*)
- Process vendor invoices (within *Source to pay*)
- Plan and recruit your workforce (within *Hire to retire*)

### Verb list for Level 2

Use the following list as a guide to select a verb when naming a Level 2 business process area. While you can also use other verbs, the following list shows the preferred and prioritized verbs.

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

A business process is a specific set of activities or tasks that accomplish a particular business function within a business process area. Make sure the description is clear about the function being performed but doesn't describe a specific activity, task, or step within the process. Also, avoid system-specific processes. The process should apply to most businesses regardless of the system they use.

Software development companies and partners can add level three business processes if they follow the guidelines documented here. Evaluate carefully if the new row should be added as a scenario, system process, or test case first. This approach keeps the organizational structure consistent and avoids duplication or misclassification of activities. Careful assessment helps maintain clarity and alignment with the intended business architecture. You can suggest a new business process at [https://aka.ms/businessprocesscatalogrequests](https://aka.ms/businessprocesscatalogrequests).

### Naming convention for business processes

Use a verb-noun pair for the name. Make it descriptive enough to clearly convey the function being performed.

### Examples of business processes

The following list provides a few examples of this level of the business process catalog.

- Sell products to customers (within Create and manage sales)
- Record invoice details (within Process vendor invoices)
- Plan and budget headcount (within Plan and recruit your workforce)

### What a business process is

The following list outlines what a business process is.

- A distinct function within a business process area.
- Descriptive of the overall function without being a specific step.
- Not system-dependent and should apply broadly across different businesses.

### What a business process isn't

The following list outlines what a business process isn't.

- A specific activity, task, or step in a business process.
- A system-specific process, such as *Update Dynamics 365 records*.

## Level four: Scenario

A scenario or pattern is a unique way of executing a specific business process, often tailored to different scenarios, industries, or requirements. Scenarios are always product specific. The naming convention for scenario allows for variations based on product, deployment mode (if applicable), industry, and partner-provided solutions. When a product offers multiple ways of achieving a business process with different features or substantially different configuration, you can create separate patterns for the features which would be noted after the product name.

This level is also the most common level where externally provided solutions are integrated into the standard catalog, as scenarios often require tailored functionality that software development companies outside Microsoft provide. By adding partner solutions at this stage, organizations can extend product capabilities to meet specific industry or business requirements while maintaining alignment with standard patterns.

For a partner-provided solution to be incorporated into the standard catalog, it must be available in Microsoft Marketplace. This requirement ensures that only verified and accessible solutions are integrated, maintaining consistency and reliability across scenarios.

### Naming convention for scenarios

The name should use a verb-noun pair, with optional extensions to indicate specific deployment modes, industries, and partner-provided solutions.

The format is the following structure:

`Verb + noun pair + using *product (deployment mode)* for *an industry* with an externally-provided solution`

> [!NOTE]
> The deployment mode is only required for Dynamics 365 Project Operations. A pattern should always indicate which products are used. A scenario can optionally include an industry and/or a partner-provided solution. Partner-provided solutions can only be used when the solution is available in AppSource or Azure Marketplace.

### Examples of scenarios

The following list provides a few examples of this level of the business process catalog.

- Examples of patterns for *Sell products to customers*

  - Create a sales order to sell products by using Dynamics 365 Sales
  - Create a sales order to sell products by using Dynamics 365 Supply Chain Management
  - Create a sales order to sell products by using Dynamics 365 Business Central
  - Create a sales order to sell products by using Dynamics 365 Commerce Call Center
  - Create a cash and carry sale by using Dynamics 365 Commerce
  - Create an online order as a business by using Dynamics 365 Commerce Business to Business (B2B) portal
  - Create an online order as a consumer by using Dynamics 365 Commerce

- Examples of patterns for *Create a project contract*

  - Create a project contract by using Dynamics 365 Project Operations (lite deployment)
  - Create a project contract by using Dynamics 365 Project Operations (stocked product and not stocked)
  - Create a project contract by using Dynamics 365 Project Operations (lite deployment) for financial services with SA Go
  - Create a project contract by using Dynamics 365 Project Operations (lite deployment) for professional services
  - Create a project contract by using Dynamics 365 Business Central

- Examples of patterns for *Plan and budget headcount*

  - Plan and budget headcount by using Dynamics 365 Human Resources position forecasting
  - Plan and budget headcount by using Dynamics 365 Human Resources with basic jobs and open positions
  - Plan and budget headcount by using Dynamics 365 Finance Budgeting module
  - Plan and budget headcount by using Dynamics 365 Finance Business Performance Planning add-in

## Level five: System process

A system process is a portion of a business process that uses a specific form, page, or UI element in Dynamics 365. Each scenario should have at least one system process. A given scenario can include any number of system processes. Clearly document each system process to make it easy to repeat and understand. Reference all relevant forms and UI elements, and provide step-by-step instructions for users interacting with the process. This approach keeps training materials, user guides, and testing documentation consistent.

### Naming convention for system processes
  
Use a verb-noun phrase that reflects the *user action* on the form. Examples:

- *Enter fixed asset details*
- *Review vendor transactions*

### Guidance

- A system process should be traceable to a UI element
- A system process supports training, documentation, and testing  

### Examples of system processes

The following list provides a few examples of this level of the business process catalog.

- Submit purchase requisition
- Approve purchase order
- Receive goods against purchase order
- Match invoice to purchase order
- Process supplier payment

These system processes reflect typical actions in the *Source to Pay* cycle that you can trace directly to forms or UI elements within Dynamics 365. They support clear documentation, training, and testing.

## Level six: Test cases

A test case is a detailed set of conditions and steps you use to determine whether a software application or system functions correctly. It's an essential part of the software testing process, designed to ensure that the software meets its requirements and performs as expected. Use test cases to identify defects, ensure quality, and verify that the software behaves as intended under various conditions. Use them whenever you need to verify the functionality, performance, or security of a software application, especially before releasing it to production.

### Test case structure

When writing a test case, include specific information to ensure clarity and effectiveness. A well-documented test case should include the following elements:

- inputs or prerequisites, which outline any initial conditions or data required before executing the test
- detailed steps, which provide a step-by-step guide on how to perform the test
- outputs or expected results, which describe the anticipated outcome of the test

Always relate test cases to a business process to ensure they're relevant and meaningful. Additionally, have at least one test case for each user story to verify that the functionality meets the user's needs and requirements. This approach helps ensure comprehensive coverage and validation of the software application.

### Types of test cases

Several types of test cases serve specific purposes:

- **Functional Test Cases**: Use these test cases to verify that the software functions according to the specified requirements. They focus on the user interface, APIs, databases, security, and other functional aspects of the application.
- **Performance Test Cases**: Design these test cases to assess the performance of the software under various conditions, such as load, stress, and scalability. They help ensure that the application can handle expected user traffic and perform efficiently.
- **Usability Test Cases**: Use these test cases to evaluate the user experience and ease of use of the software. They focus on the design, navigation, and overall user interaction with the application.
- **Security Test Cases**: Use these test cases to identify vulnerabilities and ensure that the software is secure from threats and attacks. They include tests for authentication, authorization, data encryption, and other security measures.
- **Integration Test Cases**: Use these test cases to verify that different modules or components of the software work together as expected. They help identify issues that might arise when integrating various parts of the application.
- **Regression Test Cases**: Use these test cases to ensure that recent code changes don't adversely affect existing functionality. Run them after any modification to the software to verify that the changes didn't introduce new defects.
- **User Acceptance Test Cases**: Use these test cases to validate that the software meets the needs and expectations of the end users. Typically, the users themselves perform these tests to ensure that the application is ready for production.

Each type of test case plays a crucial role in ensuring the overall quality and reliability of the software application. By using a combination of these test cases, you can thoroughly test the software and identify any issues before they reach the end users.

### Examples of test cases

The following list provides examples of different types of test cases related to the business process of creating a sales order. This list isn't comprehensive, and the steps aren't precise for executing each test. The list offers a high-level representation of the types of tests that might exist for a similar business process.

1. **Functional Test Case**:
    - **Title**: Verify Sales Order Creation
    - **Description**: Ensure that a sales order can be created successfully.
    - **Steps**:
      1. Go to the Sales Order module.
      1. Select **Create New Sales Order**.
      1. Enter customer details, product information, and quantity.
      1. Save the sales order.
    - **Expected Result**: The sales order is created and saved successfully.

1. **Performance Test Case**:
    - **Title**: Assess Sales Order Creation Under Load
    - **Description**: Evaluate the system's performance when creating multiple sales orders simultaneously.
    - **Steps**:
      1. Simulate the creation of 1,000 sales orders concurrently.
      1. Monitor the system's response time and resource usage.
    - **Expected Result**: The system handles the load efficiently without significant delays or crashes.

1. **Usability Test Case**:
    - **Title**: Evaluate User Experience in Sales Order Creation
    - **Description**: Assess the ease of use and navigation during the sales order creation process.
    - **Steps**:
      1. Ask a user to create a sales order without prior training.
      1. Observe the user's interaction with the interface.
      1. Collect feedback on the design, navigation, and overall experience.
    - **Expected Result**: The user can create a sales order easily and provides positive feedback on the interface.

1. **Security Test Case**:
    - **Title**: Verify Access Control for Sales Order Creation
    - **Description**: Ensure that only authorized users can create sales orders.
    - **Steps**:
      1. Attempt to create a sales order with an unauthorized user account.
      1. Attempt to create a sales order with an authorized user account.
    - **Expected Result**: The unauthorized user is denied access, while the authorized user can create a sales order.

1. **Integration Test Case**:
    - **Title**: Validate Integration Between Sales Order and Inventory Modules
    - **Description**: Ensure that the sales order creation updates the inventory correctly.
    - **Steps**:
      1. Create a sales order for a specific product.
      1. Check the inventory levels before and after the sales order creation.
    - **Expected Result**: The inventory levels are updated accurately based on the sales order.

1. **Regression Test Case**:
    - **Title**: Verify Sales Order Creation After System Update
    - **Description**: Ensure that the sales order creation functionality works correctly after a system update.
    - **Steps**:
      1. Perform a system update.
      1. Create a sales order following the standard process.
    - **Expected Result**: The sales order is created successfully without any issues introduced by the update.

1. **User Acceptance Test Case**:
    - **Title**: Confirm Sales Order Creation Meets User Requirements
    - **Description**: Validate that the sales order creation process meets the end user's needs and expectations.
    - **Steps**:
      1. Provide the end user with the sales order creation feature.
      2. Ask the user to create a sales order and provide feedback.
    - **Expected Result**: The user successfully creates a sales order and confirms that the process meets their requirements.

## Related content

- [About the business process catalog for Dynamics 365 apps and services](about.md)  
