---
title:  Solution architecture design processes
description: Learn how you can choose the right processes for an implementation project. Using solution architecture design pillars, you can learn how to identify those needs and the elements essential to creating a blueprint of your solution.
author: edupont04
ms.author: veneva
ms.reviewer: edupont
ms.date: 02/27/2023
ms.topic: conceptual

---

# Solution architecture design pillars: Processes

Process architecture is a commonly understood, shared view of all business processes that an organization uses to deliver a product or service. It represents how an organization operates, in a structured order.  

Complete, accurate, and well-organized process architecture is the first and most important pillar for a sound solution design. It confirms end-to-end business understanding, provides a structure for understanding the scope, and serves as the basis for testing and training. It also forms a map for requirements gathering. The processes are constructed at different levels to reflect specific areas, functions, locations, and teams. Process architecture is often referred to as a target operating model, a process library, or a catalog.

Any transformation starts with defining your processes, which is also a good time to revisit and improve them. The task of defining your processes serves the following key points:

- It creates consistency by allowing for consolidation and unification of processes across locations, teams, and systems.

- It reduces complexity by standardizing and rationalizing previously complicated and cumbersome procedures.

- It eliminates guesswork and potential ambiguity by streamlining operations and improving communications.

- It promotes productivity by eliminating inefficiencies and establishing one workflow for all users.

- It guarantees quality by maximizing attention to detail and ensuring work is done in a pre-defined, optimized way each time.

- It boosts morale by helping team members take pride in mastering the process, refining their skills, and avoiding mistakes and missed deadlines.

- It encourages continuous improvement by giving team members who follow the processes a chance to give input on how to improve them.

- It increases user acceptance by providing a higher-quality experience at each launch.

## Dependent activities in the Processes pillar

While we're not going to take a deep dive into the business process management lifecycle and capability maturity, following the Success by Design framework can help you identify important elements of your solution design.

Process architecture includes multiple dependent activities:

- **Scope management**  

  Defining the scope of the solution is the first step of the design. Ideally, you have a baseline process taxonomy with at least three levels of the process architecture. Start by mapping requirements against it and marking which processes are in scope. You can add to and take away processes from your initial process library.

  Learn more in the section [Key deliverables related to processes](#key-deliverables-related-to-processes)

- **Linear and cross-functional process flows**

  These flows show the input, output, and activities at process and subprocess levels to help you figure out how a process must change to meet requirements; you can also add details such as assumptions, metrics, timelines, and costs.

- **Business analysis**  

  At first, business users often don't know or understand the application, and the tech partner doesn't understand the business. In those cases, a business analysis helps to join them together. A business analyst gathers requirements and links them to processes; conversely, a good processes structure drives the requirements gathering by asking all necessary questions.

- **Requirements management**  

  Every functional and nonfunctional requirement needs to be linked to at least one process. If an applicable process doesn't exist, you must slot it into the relevant section of the process architecture. Azure DevOps is a good tool to use for this success measure.

- **Solution design**  

  Once you have a better end-to-end business understanding, it's time to translate it into your system processes. With the Dynamics 365 solution design, a Microsoft partner works with the process leads to develop the solution. It's often helpful to create process flows that show how the processes can be run in the system.

  As part of the process, data goes in as input exchanged between people and applications, and data goes out as output in the form of documents, analysis, and reports.

  :::image type="content" source="media/solution-architecture-design-bubbles.png" alt-text="Solution design is people, data, processes":::

- **Test management**  

  Once the solution is designed and developed, the process architecture establishes a baseline for testing. When you test every process, you ensure that every requirement is addressed and the solution is appropriate. Learn more at [Testing strategy](testing-strategy.md)

- **Training**  

  Process architecture also defines and drives your training content. You can use your process flows and guides as a first draft for your training materials. Learn more at [Process-focused solution](process-focused-solution.md), and [Success by Design overview](success-by-design.md).

## Key deliverables related to processes

1. Process architecture map  

    A visual presentation of your business processes.

    :::image type="content" source="media/processarchitecturemap.png" alt-text="process architecture map":::
2. Process catalog/inventory and taxonomy

    A sequenced list of the processes, uploaded to Microsoft Dynamics Lifecycle Services (LCS) and synchronized with Azure DevOps.

    :::image type="content" source="media/spreadsheet.png" alt-text="process catalog/inventory and taxonomy":::
3. Linear and cross-functional process flows

    These flows show the input, output, and activities at process and subprocess levels to help you figure out how a process must change to meet requirements; you can also add details such as assumptions, metrics, timelines and costs.

    **Linear flow**  

    :::image type="content" source="media/linearflow.png" alt-text="linear flow" lightbox="media/linearflow.png":::

    **Process flows**  

    :::image type="content" source="media/processflows.png" alt-text="process flows" lightbox="media/processflows.png":::
4. Requirements traceability matrix (RTM)

    This links requirements throughout the validation process, and is a key deliverable for requirements management.  

    :::image type="content" source="media/rtm.png" alt-text="requirements traceability matrix":::
5. Fit gap assessment

    At this point, you mark which requirements and respective process the system will address, and which ones require customization.  

    :::image type="content" source="media/spreadsheet.png" alt-text="fit gap assessment":::

## Next steps

Think about people and how their work must impact your solution architecture. Learn more at [Solution architecture design pillars: People](solution-architecture-design-pillars-people.md)  