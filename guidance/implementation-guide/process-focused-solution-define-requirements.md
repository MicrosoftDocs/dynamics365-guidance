---
title: Define your requirements for your Dynamics 365 solution
description: Learn how to use business process mapping to create clear and accurate requirements for your Dynamics 365 solution and improve your business operations.
ms.date: 07/16/2024
ms.update-cycle: 1095-days
ms.topic: concept-article
author: edupont04
ms.author: raprofit
ms.reviewer: edupont
ms.custom:
  - evergreen
  - ai-seo-date: 01/16/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
ai-usage: ai-assisted
---

# Define your requirements for your Dynamics 365 solution

Some projects start with lists of requirements that are based on isolated functional features. Without reference to mapped and documented business processes, these requirements can cause problems, such as:

- Missing process steps that are discovered too late.
- Misinterpretation of the requirement by parties who aren't experts in the related process.
- Lower business engagement in the project.
- Longer review cycles because the requirements and designs are less clear.

To avoid these problems, use business process mapping to define your requirements. Business process mapping is a method to draw the as-is processes that show how your business is running right now, and the to-be processes that show how it should work in the future. This approach emphasizes the importance of business process mapping early in the project. All requirements should be linked at the lowest level of your business process hierarchy. This allows you to report and manage the requirements at the same level. Also consider that all test cases should be linked to the lowest level of the process hierarchy, and test cases should cover one or more of the requirements for the business process. But it's more important that the test cases cover the business process, not individual requirements, to ensure that the entire process works not just an individual requirement is met.  

After you determine what to keep, change, or add to your solution, create the list of requirements and align them to the business processes for an accurate picture. Use tools that help you track and manage the requirements.

Typically, in a process-focused solution, after you agree on the processes, you can derive the detailed requirements and map the relevant designs. The business process catalog can assist with this process. For example, the business process catalog is available in a template that can be imported into Azure DevOps Services can help you define your scope, establish ownership of processes, create and track requirements, and much more. For more information, see [Import the business process catalog into Azure DevOps](../business-processes/about-import-catalog-devops.md).

The list of requirements is easier to create from the business process mapping and can be revised and refined iteratively.

## Types of requirements

In any Dynamics 365 project, gathering and documenting requirements is crucial for success. Requirements are typically categorized into two main types:

- **Functional**

  Functional requirements define what the system should do in terms of specific behaviors or functions it must perform, such as processing orders or generating reports.
- **Nonfunctional**

  Requirements that are not functional describe system attributes such as performance, security, and usability that define how the system should behave.

It's essential to gather both types comprehensively to ensure the system meets business needs effectively. To gather requirements, engage stakeholders across departments to capture diverse perspectives and prioritize needs. Use workshops, interviews, and documentation reviews to clarify requirements and validate them against business objectives. This structured approach ensures that Dynamics 365 implementation aligns with organizational goals while meeting user expectations for functionality and performance.

The business process catalog Azure DevOps template includes no default requirements. However, there is a requirement work item type and we recommend that you use this work item type to document your business requirements. Generally, we recommend that the requirements are linked as child work items to the  level 4 patterns (User story work item type). Following is a list of suggested types of requirements and an example of each.  

| Requirement Type | Description | Example |
|--|--|--|
| BI report | Requirements related to business intelligence reports that provide analytical insights. | Generate monthly sales performance dashboard with drill-down capabilities. |
| Business objective | High-level goals or outcomes the project aims to achieve. | Increase customer retention by 10% within the next fiscal year. |
| Data migration | Requirements for transferring data from legacy systems to Dynamics 365. | Migrate customer master data including contacts, accounts, and transactions. |
| Feature | Specific functionalities or features needed in the Dynamics 365 system. | Enable automated email notifications for order status updates. |
| Financial report | Requirements for financial statements or reports. | Generate quarterly profit and loss statement with comparative analysis. |
| Forms | Requirements related to user interface forms within Dynamics 365. | Design a custom lead capture form with mandatory fields for sales team. |
| Functional | Requirements that specify what the system should do, typically related to core functionalities. | Ability to create, edit, and delete customer records in Dynamics 365. |
| Interface | Requirements for integrating Dynamics 365 with other systems or applications. | Integrate Dynamics 365 with Outlook for seamless email synchronization. |
| Operational | Requirements related to day-to-day operational processes supported by Dynamics 365. | Automate inventory replenishment process based on predefined stock levels. |
| Performance | Requirements concerning system performance and response times. | Achieve average page load time of less than 2 seconds for customer portal. |
| Quality of service | Requirements related to service levels, reliability, and availability. | Ensure Dynamics 365 system uptime of 99.9% during business hours. |
| Safety | Requirements pertaining to system security and data protection. | Implement role-based access control to restrict sensitive data access. |
| Scenario | Requirements describing specific use cases or scenarios. | Support order processing scenario including creation, approval, and fulfillment. |
| Security | Requirements related to safeguarding data integrity and preventing unauthorized access. | Encrypt sensitive customer data stored in Dynamics 365 databases. |
| Report | Requirements for generating various types of reports and analytics. | Create monthly sales forecast report for executive review. |
| Workflow | Requirements for automating business processes using workflows in Dynamics 365. | Design approval workflow for purchase orders with multiple approval stages. |

> [!NOTE]
> We recommend that you use relationships in Azure DevOps to link and relate your requirements to multiple processes when appropriate. For example, a performance requirement may related to multiple business processes in your hierarchy.

## Document requirements

Documenting business requirements is a critical process that ensures all stakeholders have a clear understanding of what needs to be achieved. This process involves capturing detailed and precise information about the business needs, objectives, and constraints. Effective documentation helps in aligning the project goals with business objectives, facilitates communication among team members, and provides a reference point throughout the project lifecycle. By systematically documenting requirements, businesses can minimize misunderstandings, manage expectations, and ensure successful project outcomes. The following table provides examples of business requirements with fields that we recommend you track in Azure DevOps or another system when documenting business requirements.

|Field  |Description|Example|
|---------|---------|---------|
|**Title**   |Start with a clear and concise title that summarizes the requirement.|Migrate Customer Master Data|
|**Assigned To** |Assign the requirement to the team member responsible for its implementation.|John Doe|
|**Description**|Provide a detailed description of the requirement.|The objective is to migrate all customer-related data, including contacts, accounts, and transactions, from the legacy system (ABC Content Hub) to Dynamics 365. The migration must ensure data integrity and functionality.|
|**Acceptance Criteria**|Define the specific conditions that must be met for the requirement to be considered complete.|All customer accounts, contact information, and transaction history must be successfully migrated and accessible in the new CRM system.|
|**Work Around**| If there are any temporary solutions before the requirement is fully implemented, describe them here.|Until the migration is complete, customer data is manually updated in both systems.|
|**Business Justification/Impact** |Explain why this requirement is necessary and its impact on business operations.| Migrating customer data to Dynamics 365 will streamline operations, improve data accuracy, and enhance customer service.|
|**Architect Comments**| Use this section for any other notes or discussions related to the architecture or other aspects of the project. |Make sure that the data migration script is thoroughly tested in a staging environment before deployment. The extract of data must be completed during off hours to ensure that the current system can still be used due to performance concerns. Additionally, the customers must be loaded into Dynamics 365 Supply Chain Management first, and then the initial sync for dual-write must be completed to copy the data to the Dataverse.|
|**Disposition Type**| Use this field to indicate if the requirement is a fit or a gap.|Gap|
|**Priority**| Assess and select appropriate options based on the criticality and potential risks.|Priority: High, Risk: Medium.|
|**Potential ISV**| Use this field to indicate a potential solution from an external software development company for filling a gap.|-|
|**Requirement Type**| Use this drop-down box to select the type of requirement as described earlier in this article.|Data migration|
|**Requirement Complexity**| Use this drop-down box to categorize how complex the requirement will be to meet if it is a gap. |Very Complex|
|**Requirement Stage**| Use this drop-down box to indicate how far along the requirement is in being filled. Suggested values for the drop-down box include the following: Architecture review, Business approved, Business review, Completed, Disposition review.|-|
|**Requirement Category**| Use this field to indicate if the requirement is functional or non-functional.|-|
|**In Scope**| Use this drop-down box to indicate if the requirement is not in scope, in the statement or work, or if a change request is required. |-|
|**Effort (Hours)**| Estimate the number of hours required to complete the requirement.|40 hours.|

Optionally, define the User/Role and Country/Region. Your organization may also use other identifiers such as Business Unit or Department for example to differentiate requirements from different sources.

You might also consider adding additional fields to indicate the level of change management that is required for a requirement, training, standard operations procedures, or documentation that needs to be updated and so on. Consider your business culture and structure when defining the template and information that should be captured on the requirements. For example, you may want to track the person who defined the requirement and the person who approved the requirement.  

## A solution that helps you improve your business operations

Designing and building a solution that has a great positive impact isn't an easy task. You must consider many aspects. Everything is so connected that even a small piece can influence the whole project.

The business process flows are the common ground where you can gather all the implementation artifacts. They keep all the solution components and phases aligned and connected. Business process flows are the main tool for communication that helps you drive changes on how your business runs and helps you minimize missing any pieces.

Business processes are involved throughout the implementation journey and remain useful for future improvements in your business. They have a lasting impact on your business, as long as you continuously revise them to align with your business goals and vision and reflect any changes in your solution.

By defining business process flows, you prepare a solid foundation for all the implementation activities. And at the end, you can enjoy the benefits of optimized and efficient processes, reduced risks, lower costs, role compliance, an integrated solution, and a successful implementation.

## Next steps

- Follow the [checklist](process-focused-solution-checklist.md) to prepare for your implementation
- Read a [case study](process-focused-solution-case-study-journey.md) about a company that implemented Dynamics 365 using a process-focused approach

### See also

- [Business processes in Dynamics 365](../business-processes/overview.md)
