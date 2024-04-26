---
title: Choose the right processes for your solution
description: Learn how to define and improve your business processes for a successful solution.
author: edupont04
ms.author: veneva
ms.reviewer: edupont
ms.date: 01/11/2024
ms.topic: conceptual
ms.custom:
  - ai-seo-date: 01/11/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
ai-usage: ai-assisted
---

# Choose the right processes for your solution

Process architecture is a shared view of all the business processes that your organization uses to deliver a product or service. It shows how your organization operates, in a logical order.

Process architecture is the first and most important pillar of good solution design. It confirms your end-to-end business understanding, provides a structure for your scope, and serves as the basis for testing and training. It also forms a map for requirements gathering. The processes are organized at different levels to reflect specific areas, functions, locations, and teams. Process architecture is also called a target operating model, a process library, or a catalog.

Any transformation starts with defining your processes, which is also a good time to revisit and improve them. Defining your processes helps you:

- Create consistency by consolidating and unifying processes across locations, teams, and systems.

- Reduce complexity by standardizing and simplifying previously complicated and cumbersome procedures.

- Eliminate guesswork and ambiguity by streamlining operations and improving communications.

- Promote productivity by eliminating inefficiencies and establishing one workflow for all users.

- Guarantee quality by maximizing attention to detail and ensuring work is done in a predefined, optimized way each time.

- Boost morale by helping team members take pride in mastering the process, refining their skills, and avoiding mistakes and missed deadlines.

- Encourage continuous improvement by giving team members who follow the processes a chance to give feedback on how to improve them.

- Increase user acceptance by providing a higher-quality experience at each launch.

## Dependent activities in the Processes pillar

While we won't go into the details of the business process management lifecycle and capability maturity, following the Success by Design framework can help you identify important elements of your solution design.

Process architecture includes several dependent activities:

- **Scope management**: Defining the scope of the solution is the first step of the design. Ideally, you have a baseline process taxonomy with at least three levels of the process architecture. Start by mapping requirements to it and marking which processes are in scope. You can add or remove processes from your initial process library. Learn more in the section [Key deliverables related to processes](#key-deliverables-related-to-processes).

- **Linear and cross-functional process flows**: These flows show the input, output, and activities at process and subprocess levels to help you figure out how to change a process to meet requirements. You can add details such as assumptions, metrics, timelines, and costs.

- **Business analysis**: At first, business users often don't know or understand the application, and the tech partner doesn't understand the business. In those cases, a business analysis helps bring them together. A business analyst gathers requirements and links them to processes. Conversely, a good process structure drives the requirements gathering by asking all the necessary questions.

- **Requirements management**: Every functional and nonfunctional requirement needs to be linked to at least one process. If a relevant process doesn't exist, you must slot it into the right section of the process architecture.

- **Solution design**: After you have a better end-to-end business understanding, it's time to translate it into your system processes. With the Dynamics 365 solution design, a Microsoft partner works with the process leads to develop the solution. It's often helpful to create process flows that show how the processes can be run in the system.

  As part of the process, data goes in as input exchanged between people and applications, and data goes out as output in the form of documents, analysis, and reports.

  :::image type="content" source="media/solution-architecture-design-bubbles.png" alt-text="Diagram showing four interlocking circles to illustrate the idea that solution design (the center circle) encompasses people, data, processes." lightbox="media/solution-architecture-design-bubbles.png":::

- **Test management**: After the solution is designed and developed, the process architecture establishes a baseline for testing. When you test every process, you ensure that every requirement is addressed and the solution is appropriate. Learn more at [Testing strategy](testing-strategy.md).

- **Training**: Process architecture also defines and drives your training content. You can use your process flows and guides as a first draft for your training materials. Learn more at [Process-focused solution](process-focused-solution.md) and [Success by Design overview](success-by-design.md).

## Key deliverables related to processes

**Process architecture map**: A visual presentation of your business processes.

  :::image type="content" source="media/processarchitecturemap.png" alt-text="Diagram of a process architecture map in the form of a simplified Kanban board." lightbox="media/processarchitecturemap.png":::

**Process catalog or inventory and taxonomy**: A sequenced list of the processes, uploaded to Microsoft Dynamics Lifecycle Services (LCS) and synchronized with Azure DevOps Services.

  :::image type="content" source="media/spreadsheet.png" alt-text="A table with no content provided as an example of a process catalog or inventory and taxonomy." lightbox="media/spreadsheet.png":::

**Linear and cross-functional process flows**: These flows show the input, output, and activities at process and subprocess levels to help you figure out how to change a process to meet requirements. You can add details such as assumptions, metrics, timelines, and costs.

- Linear flow**

  :::image type="content" source="media/linearflow.png" alt-text="Flowchart showing a linear flow." lightbox="media/linearflow.png":::

- Process flow**

  :::image type="content" source="media/processflows.png" alt-text="Simplified diagram of a process flow." lightbox="media/processflows.png":::

**Requirements traceability matrix**: Links requirements throughout the validation process, and is a key deliverable for requirements management.

  :::image type="content" source="media/rtm.png" alt-text="Two overlapping tables with no content, and an arrow pointing from the bottom table to the top table, illustrating a simplified requirements traceability matrix." lightbox="media/rtm.png":::

**Fit gap assessment**: At this point, you mark which requirements and respective processes the system will address, and which ones require customization.

  :::image type="content" source="media/spreadsheet.png" alt-text="A table with no content provided as an example of a fit gap assessment." lightbox="media/spreadsheet.png":::

## Next steps

- [Determine the people involved in and affected by your solution](solution-architecture-design-pillars-people.md)
- [Know and manage your data for your solution](solution-architecture-design-pillars-data.md)
- [Develop a solution strategy using Dynamics 365 apps and other technologies](solution-architecture-design-pillars-technology.md)
- [Apply project management, change management, and governance and control methodologies for your solution](solution-architecture-design-pillars-methodology.md)
- [Create a functional and technical design document for your solution](../patterns/create-functional-technical-design-document.md)
