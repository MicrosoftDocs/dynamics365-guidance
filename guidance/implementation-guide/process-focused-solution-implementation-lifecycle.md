---
title: Base the implementation lifecycle on processes
description: Learn how to use the Success by design framework to make your implementation lifecycle process-centric by focusing on business processes.
ms.date: 01/07/2025
ms.topic: conceptual
author: edupont04
ms.author: raprofit
ms.reviewer: edupont
ms.custom:
  - ai-seo-date: 01/16/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
ai-usage: ai-assisted
---

# Base the implementation lifecycle on your business processes

A process-focused solution helps you define, design, build, test, and support your Dynamics 365 implementation with your end-to-end business processes as the framework. Processes are the way you deliver value to your customers and achieve your business goals. By using a process-focused approach, you can create a solution that reflects and improves your business operations, regardless of the underlying methodology.

The [Success by design](success-by-design.md) framework outlines the phases of the implementation lifecycle and shows how to use your business processes throughout the phases to ensure a successful outcome.

## Initiate

A business application implementation is essentially the delivery of a new capability for end-to-end business transactions using the application. The first step in your implementation is to define the *scope* of your solution. The scope is the set of capabilities and outcomes that you want to achieve with Dynamics 365.

Your business processes describe the activities, roles, functions, data, and systems that are involved in your operations. They show the connections and dependencies between different parts of your organization. They also show the level of detail and complexity of your operations. Use your business processes to define and communicate your scope in a clear and common language.

- Users understand business processes because they're expressed in the languages they know best.
- Processes are richer in context than a requirements list.
- Processes show the connections between different business units, roles, functions, task-level steps, and systems.
- They're naturally hierarchical and can be expressed in different levels of detail, depending on their intended purpose.
- Processes are the connectors that show the data and people feedback loop.

Use process mapping to create visual representations of your processes. Start by mapping your current or *as-is* processes. Map your future or *to-be* processes as well, the processes you want to use after you implement Dynamics 365. They might include changes, improvements, or innovations that you want to achieve with the new solution. Use the Dynamics 365 capabilities and features to guide your to-be process mapping.

Collect and organize your processes in a process catalog. The process catalog is a structured and hierarchical list of your processes. Number, label, and reference your processes in the catalog. Group your processes by business value streams, departments, roles, or functions. This helps you define the process taxonomy or structure.

> [!TIP]
> The business process catalog includes a structure and hundreds of business processes by default. When you use the Azure DevOps template for the catalog, Demo Deliverable work items are included by default which are tools that can be leveraged to learn about new features and see demonstrations of standard functionality.

The process catalog helps you:

- Express your project goals and vision in the natural language of your business.
- Provide a skeleton and structure for your project scope and plan.
- Identify and highlight areas for process improvement, innovation, risks, and constraints.
- Map your processes to the equivalent design and configuration in Dynamics 365.
- Create a workable definition of the project that doesn't rely on individual written requirements.

Use the process catalog to work with your implementation partners and stakeholders. Use the processes to review and approve the scope and the proposed solution and to define the statement of work and the project deliverables. We recommend that you use the business process catalog to define the scope of work. [!INCLUDE [daf-catalog-get](../includes/daf-catalog-get.md)]  

Keep in mind that your processes are always subject to change. As you move forward, you might need to update, refine, or modify your processes based on new information, feedback, or requirements. Your process catalog should be flexible and adaptable to accommodate these changes.

## Implement

After you define your scope, start to design, build, and test your solution. Use your processes to guide these activities and ensure that your solution aligns with your business goals and outcomes.

### Design phase

During the **design** phase, use your processes to create the solution blueprint. The solution blueprint is the vision and architecture of your solution. It shows how Dynamics 365 supports your processes. It also shows how your processes interact with other systems, data, and integrations. The business process catalog helps you manage following tasks:

- Determine the sequence and priority of your design work based on the importance and interrelationship of your processes. When you use the Azure DevOps template for the business process catalog, use the **Priority**, **Risk**, **Effort**, **Business Value**, and **Time Criticality** fields to help with this process.  
- Manage the distribution and assignment of the design tasks and activities to different project roles and teams. When you use the Azure DevOps template for the business process catalog, we recommend that you use the **Assigned to** field for the person who is responsible for taking action on the work item, and that you add other fields for the **Business stakeholder** and **Subject Matter Expert (SME)**. Depending on your organizations structure, you might need multiple fields for the stakeholders and SMEs.
- Communicate and collaborate with your business users and stakeholders using the process language and context. We recommend that you rename business processes where appropriate for your organization, and that you train your users on the standard language that is chosen. When possible, using the Microsoft standard language, can make downstream communications easier, but make sure you document carefully why changes are being made. We advise that you don't change the process sequence ID in the catalog. When these unique identifiers are preserved, it's easier for you to take updates to the catalog from Microsoft later.  
- Review and approve the design decisions and deliverables using the process outcomes and scenarios.

Use your processes to create the system design and configuration as well. Map them to the Dynamics 365 functions, features, and settings. Use them to identify any gaps or customizations that you might need to address.

### Build phase

During the **build** phase, use your processes to configure and develop your solution. The business process catalog helps you manage following tasks:

- Plan and manage the configuration and development tasks and activities based on the process sequence and dependencies.
- Understand the context and implications of any build tasks and ensure that they fit within the process flow and outcome.
- Avoid unnecessary or disjointed customizations that might not serve the process well or might create conflicts or errors.
- Deliver working processes in Dynamics 365 software as early as possible and test them incrementally and iteratively.

> [!TIP]
> The Azure DevOps template of the business process catalog includes thousands of standard configurations with menu paths, data entity information, details about the configuration, and links to Microsoft Learn articles to help you configure your solution. Leverage these work items to help you manage the configuration tasks that must be completed for your implementation. We recommend that you capture decisions or screenshots on these work items as configurations are completed to help keep track of the details of why and how you have configured your solution.

Use your processes to collaborate and communicate with your developers, configurators, and testers as well. Use the process language and context to explain the requirements and expectations for each build task. Use the process outcomes and scenarios to review and evaluate the build deliverables.

### Test phase

During the **test** phase, use your processes to test and validate your solution. The business process catalog helps you manage following tasks:

- Ensure full testing coverage and detect any missing or inadequate functions or processes.
- Follow the process-focused path created earlier in the project and reuse the process scenarios and data.
- Focus on evaluating the business process outcomes and measure the impact of your changes.
- Test the end-to-end processes, which is how the system is used in production.

Use your processes to collaborate and communicate with your testers, business users, and stakeholders as well. Use the process language and context to explain the test cases and criteria. Use the process outcomes and scenarios to review and approve the test results and feedback.

> [!TIP]
> When you use the Azure DevOps template for the business process catalog, sample test cases are included. We recommend that each level four pattern, or User story type work item in the Azure DevOps template, has at least one test case. Consider using automated regression tests for your most critical business processes.

## Prepare

After you test and validate your solution, prepare for the go-live. Use your processes to guide your preparation activities, such as training, cutover, and support.

### Training

For **training**, use your processes to create and deliver your training materials and sessions. The business process catalog helps you manage following tasks:

- Collate and organize your training materials based on the process structure and hierarchy.
- Guide your training sessions and activities based on the process flow and scenarios.
- Train your users on how to perform their roles and tasks within the processes using Dynamics 365.
- Increase the adoption and satisfaction of your users by using the process language and context.

Create role-based training by using your processes as well. Map your roles to your processes and security settings. Use these mappings to generate role-specific training materials and sessions.

### Cutover

For **cutover**, use your processes to create and execute your cutover plan. The cutover plan is the set of steps and activities that you need to perform to transition from your legacy system to Dynamics 365. The business process catalog helps you manage following tasks:

- Identify and sequence the cutover tasks and activities based on the process dependencies and priorities.
- Estimate the duration and resources for each cutover task and activity based on the process complexity and scope.
- Assign and communicate the cutover roles and responsibilities based on the process ownership and involvement.
- Monitor and manage the cutover progress and status based on the process outcomes and milestones.

## Operate

After you go live, use your processes to **support and maintain** your solution. The business process catalog helps you manage following tasks:

- Reproduce and investigate any reported functional issues by following the standard process flow and steps.
- Communicate and collaborate with your users and stakeholders using the process language and context when discussing the issues and solutions.
- Reduce the time and effort to understand and resolve the issues by using the process outcomes and scenarios.
- Increase the confidence and satisfaction of your users by using the process feedback and improvement.

## Next steps

- Review the [considerations for building business processes](process-focused-solution-considerations-building-business-processes.md)
- Learn how to perform a [fit-to-standard and a fit-gap analysis](process-focused-solution-fit-to-standard-fit-gap-analysis.md)
- [Define your requirements](process-focused-solution-define-requirements.md)
- Prepare for your implementation by follow the [checklist](process-focused-solution-checklist.md)  
- Read a [case study](process-focused-solution-case-study-journey.md) about a company that implemented Dynamics 365 using a process-focused approach

### Related information

- [Test your Dynamics 365 solution before deployment](testing-strategy.md)
- [Prepare for go-live](prepare-to-go-live.md)
- [Standardize business processes during an implementation](../business-processes/standardize-business-processes.md)  
