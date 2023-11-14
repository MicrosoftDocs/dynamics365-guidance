---
title: Process-centric implementation lifecycle
description: The Success by design framework outlines the phases of the implementation lifecycle at high level and provides an outlook on how the business processes are recurrently used across those phases, emphasizing the importance of the process-centric implementation lifecycle.
ms.date: 03/10/2023
ms.topic: conceptual
author: edupont04
ms.author: veneva
ms.reviewer: edupont
---

# Process-centric implementation lifecycle

The value of taking a process-focused solution doesn't end with a better definition of requirements. Adapting all the activities in the subsequent phases to be more process-based helps deliver better outcomes, regardless of underlying methodology.

At go-live, a business application such as Dynamics 365 sees system users performing tasks and activities as part of a business process. The users aren't executing on gaps, fits, or isolated requirements. Keep this point in mind when you think of the full project lifecycle. The ultimate test of the project success is when the system is in operation and the design, build, and testing actions are intermediate steps towards that goal. It's recommended to drive these phases with the end-to-end business process as the framework upon which all the related activities are planned, performed, and measured.

The Success by design framework outlines the phases of the implementation lifecycle at high level and provides an outlook on how the business processes are recurrently used across those phases, emphasizing the importance of the process-centric implementation lifecycle.

## Initiate

A business application implementation is essentially the delivery of a new capability for end-to-end business transactions using the application. Processes are the foundation for the **definition of the solution scope**. Processes embody many of the properties that make for a good scope definition.

- Users understand business processes as they're expressed in the languages they know best.

- Processes are richer in context than a requirements list.

- Processes show the connections between different business units, roles, functions, task-level steps, and systems.

- They're naturally hierarchical and can be expressed in different levels of detail, depending on their intended purpose.

- Processes are the connectors that show the data and people feedback loop.

Process architecture design steps:

1. Process catalog and hierarchy

2. Process modeling and mapping

3. Process management and governance

Processes are collected and organized in a process catalog. The business processes in the catalog are arranged in hierarchical relations and can then be numbered, labeled, and uniquely referenced. This format defines the process taxonomy. As part of the process modeling, process diagrams and flows are created. This step is often referred to as Process mapping. Process hierarchy can be also used to put in order the data structures. You'll probably want to manage the content in Azure DevOps or similar tools where you can assign various tasks such as configure, build, design, or test and to different project roles.

Business processes are usually interwoven with other business processes. These interconnected processes can span systems, and the connection can be a single endpoint or an entire subprocess performed in the external system. If the latter, it should be considered for your solution scope. Where the process is in the external system is directly relevant to the end-to-end process, include the full process in the process mapping. Not only does it help in understanding the process, but also with making better decisions on customizations and selecting ISVs (Independent Software Vendor), which are also stated in your solution scope.

Using process catalog as part of the definition of the scope also helps when working with implementation partners. The process architecture expresses the ultimate outcomes for the project and having it reflected in the statement of work can help with a more comprehensive definition of the project that results in fewer change orders.

Keep in mind that business processes are always subject to change. As you move forward, you're enriching the business process flows, and possibly adjusting the solution scope. A business process flowchart offers precisely that type of  the flexibility.

## Implement

When creating the solution blueprint, the vision of the overall solution architecture gives solidity and certainty to the project scope. It's the transition from scope as business processes to scope as. As it's expressed in business language, it helps to ensure that business users can be usefully engaged in the review and approval of the scope and proposed solution. There are often other views of the solution architecture in terms of data flow, systems landscape, and integrations.

As part of the **design phase** in a Waterfall methodology, or during design work in sprints in an Agile methodology, breaking down the end-to-end business processes into meaningful subprocesses provides manageable, bite sized units of work. It also allows better communication of the project tasks with business users.

The specific user stories, or configurations, and build work at a task level can be related to the subprocesses so that they have the correct business context. This way, it's easier for business users to better understand the design. The business reviews and approvals of designs are meaningful.

If the business processes are collected in a structured and hierarchical process catalog, this catalog can be used for the following tasks:

- Help more easily and logically determine the sequence of work starting with the more foundational process designs before tackling the lower-level designs.

- Help highlight the interrelationships and dependencies between the different business value streams, departments, roles, and functions. It helps with designing a more cohesive and integrated overall solution.

- Help better manage the distribution of the actions and activities by using the sequence and interrelationship of the designs in scope.

- A process flow can directly be mapped to the system design from configuration through data setup and functional run through.

- Help deliver working processes in Dynamics 365 software, by implementing processes, including end-to-end process as early as possible, and by taking a process-centric view.

- Help provide a better understanding of the solution by looking at the current capability of the emerging system to execute end-to-end processes.

- View the system in the context of a process, reducing unnecessary customizations.

- Better engage the business subject matter experts (SMEs) and business stakeholders by using the business language of processes.

- More rapid delivery of working software that better reflects and makes better use of the Dynamics 365 SaaS cloud world.

Deliver processes in Dynamics 365 as early as possible, taking a process-centric view. The benefits are practical and real, and often the only actual barrier to taking a process-centric view of design tends to be the legacy of previous, more technical, and custom development-centric approaches, better suited to the pre-cloud and SaaS world.

Having the high-level process, you can start breaking down the end-to-end business processes into meaningful subprocesses, as shown in the Figure below.

:::image type="content" source="media/process-focused-image1.png" alt-text="Illustrates different business flows that span Dynamics 365 apps across finance and operations and sales.":::

A process-centric view provides an excellent basis for converting designs into software. It can help directly address the question of how to execute the business process within Dynamics 365. The **configuration and development tasks** have the background of the business process context, and don't need to be treated as an isolated delivery.

This isolation is still frequently seen in projects where the development and configuration work becomes highly technical and is divorced from the business process, and may not serve the project well. Instead, when a data- and process-centric view is taken, the configuration and development tasks can be planned and managed for delivering a process embedded in Dynamics 365 software.

A process-first view allows the team to collaborate more productively. The process designs, which now reflect the functions and configuration and flow within the Dynamics system, help the various teams communicate the context and better understand the delivery of any development. Compared to working from a task in DevOps, or a design document without the proper anchoring in a business process, the process background provides a better context and implications for a build task. For example, taking a process-centric view can help with the mapping of the access necessary for performing process tasks. That helps build a picture of the related security roles.

A process-focused view of the emerging solution also helps avoid the dangers of a narrow "fit gap" list or Task list that can lead to disjointed point solutions. Instead, with a process-first background, there's a high probability that the tasks and activities crystallize into a coherent and well-functioning solution.

The project can also use the process-focused solution to conduct reviews of the solution with the wider business to confirm that the project is delivering on expectations. These reviews are harder to do well without the supporting process definition. That's because without the processes in focus, the project can't speak the language of the business. Many organizations are expecting some degree of business process transformation as part of the implementation of Dynamics 365.

The reviews of the solution, when the new processes are first explained in business process terms, helps ground the subsequent discussion of the current state in a clear, well understood business language. This significantly improves the quality and usefulness of the business review by minimizing the technical implementation jargon and instead concentrating on the "business of business."

Showing incremental progress of the build and development using business process language improves the confidence of the wider business in the project. This can be key to the project's success.

A project that has taken a process-centric view reaps the benefits during **testing**. Other than the necessarily narrow focus of unit testing and some non-functional tests, almost all other test types should be rooted in some form of process definition. When there's an existing set of process definitions and the associated designs, and a system with the designs implemented, there are many advantages to the testing methods.

- It helps ensure full testing coverage and enables earlier detection of any missing or inadequately defined functions or processes.

- The testing can more easily follow the process-focused path already created earlier in the project.

- Testing has a natural focus on evaluating business process outcomes, which tends to be a closer match to the intention of the design and eventual production use.

- It enables incremental testing of processes and subprocesses, which in turn helps engineer quality into the solution.

- Testing end-to-end processes, which is how the system is used in production, is enabled.

Overall, testing in a business application like Dynamics 365 is a natural match to a process-focused view of the solution. Having a process-centric approach throughout the lifecycle allows testing to become the natural and obvious progression of project delivery.

Learn more at [Testing strategy](testing-strategy.md).

## Prepare

**Training** to use business systems like Dynamics 365 applications is fundamentally learning how to conduct day-to-day business processes using the system. Most of the functional roles in the system interact with multiple functions and processes. Rarely do roles exist in a vacuum of their own process, but instead interact with other processes. Having business process flows defined and available in the process catalog, including flows across system roles, helps to both collate process-based training materials and guide the training.

During the design process, if the roles are mapped against the processes as part of the security design, they can be directly used for testing and for generating role-based training.

Even where some of the system roles may be specifically restricted to a specialized function in the system, there's often a need to understand the upstream and downstream processes to perform a function well, and to understand the implications of any delays or changes in the flow.

If whole project approach is process-focused, including the configure/build activities, then the process of generating materials for training (such as task guides for finance and operations apps and guided tasks for customer engagement apps) goes smoothly, as there's a direct correlation between the system processes and the training processes.

The process-based training not only helps prior to go live, it also can be used with new hires and when users change roles. It allows those new to the business to absorb the business process simultaneously while understanding how that process is performed within the system and increase adoption in the organization.

Roles can be easily defined in a business process and use the correct security roles for testing and training.

:::image type="content" source="media/process-focused-image2.png" alt-text="Illustrates the create order end-to-end process across sales manager, sales clerk, warehouse worker, and accounts receivables clerk.":::

A successful cutover execution often comes backed up by a detailed and well-defined **cutover plan**. The details of every step and the sequence of every activity lead to a better comprehension for the implementation team to perform the tasks that will take them to be ready for the go live.

Having a process-centric view will allow you to fluently surface the tasks sequence, duration times, roles to achieve a successful cutover execution.

Learn more at [Prepare for go-live](prepare-to-go-live.md).

## Operate

The process catalog created in the project provides more than the framework for implementation. It can also help with **supporting the solution**. The support team often have to reproduce reported functional issues so that they can investigate the root causes. A robust process-based definition of the flow allows support to recreate the steps defined by the agreed standard process flow. The visual depiction and description of the process allows the support team to speak a common language with the business user when discussing the issues.

This ability to place yourself in the business process helps reduce the number of back-and-forth cycles of communication and the overall time taken to understand the issue in business terms. It increases the confidence of the user that their reporting of the issue has been understood. This reduces anxiety and improves user sentiment of the system.

## Next steps

- [Considerations for building business processes](process-focused-solution-considerations-building-business-processes.md)  
