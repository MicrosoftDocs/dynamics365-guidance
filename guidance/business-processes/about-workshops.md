---
title: Workshops for Dynamics 365 Implementations
description: Explore how workshops help stakeholders align on key business processes and refine Dynamics 365 solutions for optimal outcomes.
author: edupont04
ms.author: edupont
ms.date: 01/13/2026
ms.topic: concept-article
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-description
  - ai-seo-date: 01/08/2026
---

# Workshops for Dynamics 365 implementation projects

As part of an implementation project, hold workshops to help you identify the relevant business processes that the final solution must support. Microsoft provides [Word templates](https://aka.ms/businessprocessworkshops) that can help you. In this article, you find descriptions of the different types of workshops that are most helpful.

## Workshop for scenario board discovery

Establishing a scenario board or storyboard is a crucial step in the implementation of a new business solution. It involves creating and agreeing to a visual representation of the key business processes in the new system, followed by showing the business process within the Dynamics 365 system. This approach helps to ensure that all stakeholders have a clear understanding of the proposed solution and can provide feedback early in the development process. It also helps the functional consultants to verify their understanding of the business process requirements by directly assessing the solution design in the system versus customer expectations early in the lifecycle. Use the storyboarding process in the initial discovery process for each end-to-end process that is in scope for the project.

The business process catalog aims to provide one default template storyboard for each out-of-the-box end-to-end process. Some end-to-end processes have more than one storyboard example to select from, but select only one that most closely matches the primary process of the organization. For example, the plan to produce processes include one story board for discrete manufacturing and one for process manufacturing. If the organization only manufactures in one technique or the other, select the one for the mode of manufacturing. However, if the organization uses mixed mode, try to select the one for the process that represents the majority. If the organization is an exact split of the two modes, then you can consider running two storyboarding workshops.

### Construction of a storyboard

The default storyboards included in the business process catalog were constructed with the following key principles in mind. Use the same framework to extend or modify the existing default storyboards, or to create new storyboards for new processes.

1. **Identify key scenarios**  

    Start by identifying the key end-to-end business scenarios that the new technology solution needs to address. Base these scenarios on user stories and business requirements. Identify the end-to-end scenarios in scope. From that collection of scenarios, identify the small set of end-to-end scenarios that represent 80% of the business or represent the core business process. This process also helps you identify the common steps and elements across the scenarios and prioritize within this small set.

1. **Create "frames"**  

    For each selected scenario, create "frames" that represent the different steps or stages in the user journey, much like you would create "frames" for a video storyboard. The default storyboards provided with the business process catalog provide a simple flow diagram as a starting point.

    Each "frame" or tile should include a visual representation of the expected functionality (feature, function, and user interaction) and a brief description of the actions being performed.

1. **Add details**  

  Include details such as user interactions, system responses, and any other relevant information. This information helps to provide a comprehensive view of the user experience that can easily generate a user story or equivalent.

### Drafting the storyboard

The default storyboard template workshops that the business process catalog provides are intended to be a starting point for the discussion. Update and customize the storyboard for each organization. Use the following steps to prepare for the storyboarding workshop.

1. **Initial draft**  

    Select and leverage the best storyboard for the organization. Make any known updates to the storyboard for the industry or customer specific that are known before the start of the workshop. Present the draft of the storyboard based on the identified key scenarios and frames. This draft should be a rough representation of the business process represented by process inputs and outcomes, user journey and interactions.  

    > [!IMPORTANT]
    > Base the draft on the standard processes from the business process catalog and Dynamics 365 to meet the underlying business requirements. Don't model it based on the implementation in the current legacy system.

1. **Review and feedback**  

    Share the initial draft with stakeholders and gather feedback. This feedback is crucial for identifying any gaps or problems in the proposed solution.

1. **Refinement**  

    Refine the storyboard based on the feedback you receive. This step might involve adding more details, adjusting the user interactions, or making other changes to improve the overall user experience.

### Inputs and outputs of the storyboarding process

Use the following guiding principles to help define the inputs and outputs that you should capture during the storyboarding process. The default storyboards include a draft of the inputs, which you might need to modify or update during the storyboarding workshop or in preparation for the workshop.

- Input:

  - Key scenarios and user journeys
  - Visual representations of the process flow
  - Stakeholder feedback

- Output:

  - A detailed storyboard that visually represents the user journey and interactions
  - A clear understanding of the proposed solution and its impact on users
  - Key user stories and business requirements

By following this process, you can ensure that the new technology solution is well-designed and meets the needs of its users. The storyboard serves as a valuable tool for communication and collaboration, helping to align all stakeholders on the vision for the project.  It also helps prioritize working on the key, critical end-to-end business scenarios before looking at more peripheral, complex, or very infrequent scenarios.

### Sample storyboard

The following image shows a sample storyboard template for the *acquire to dispose* process.

:::image type="content" source="media/about-workshops-sample-storyboard.svg" alt-text="The image is a flowchart titled Acquire to Dispose Storyboard that outlines a business process from acquisition to disposal. The top row depicts a basic flowchart of the business process areas for the acquire to dispose process. Below each process step there are one or more blue boxes that depict scenarios and key attributes of the business process area for discussion in the workshop. The bottom of the graphic includes horizontal or supporting processes that support the entire acquire to dispose process." lightbox="media/about-workshops-sample-storyboard.svg":::

You can download the sample storyboard as part of the *Acquire to dispose Visio flow diagrams (AI Generated).vsdx* file at [https://github.com/microsoft/dynamics365patternspractices/tree/main/graphics](https://github.com/microsoft/dynamics365patternspractices/tree/main/graphics).

### Sample workshop scenario

Use the following high-level steps to leverage this graphic in an *acquire to dispose* storyboarding workshop for Dynamics 365.

1. **Prepare**  

    To prepare for the workshop, review the graphic and structure. If you know business requirements or scope, consider highlighting in scope processes or deleting or striking out any out of scope scenarios. If there are industry specific requirements, add the scenario into the appropriate boxes or create new boxes if required. Ensure that all the correct stakeholders are invited to the meeting.

1. **Introduction**  

    Present the storyboard as an overview of asset lifecycle management within an organization **using Dynamics 365**.

1. **Step-by-step walkthrough**  

    Guide participants through each step sequentially, explaining how Dynamics 365 can facilitate these processes. You can consider leveraging a high-level short process that shows the main process. Make any changes required to the top row process as required. Try to stick to this process as much as possible and minimize renaming where possible. If you add new boxes, consider using a different color or symbol to visually indicate where there are **changes**.  

1. **Discussion**  

    Encourage participants to discuss how their current practices align with the storyboard and identify opportunities for improvement. For each process step, try to identify one key "path" or option that represents the majority of the organization's process, the most critical process, or processes and scenarios that most closely align to the overall project goal. Highlight the "main path" a different color as the stakeholder agree on the most critical steps. It's often helpful to have this "main" path defined by a smaller set of stakeholders prior to the workshop as a proposal which can be modified or refined in the workshop.

1. **Deep dive**  

    Use the specific blocks under to delve deeper into areas where Dynamics 365 offers functionality that can streamline operations, such as automated asset tracking or predictive maintenance scheduling. Discuss any uniqueness that the organization might have related to each process or scenario. Document any key findings or discussion from the session.

1. **Horizontal and supporting processes**:

    1. **Case management**  

        Highlight how case management can be leveraged throughout the acquire to dispose process to handle requests, approvals, and manage problems and risks reported in the process. Document and discuss any needs for each process step to manage requests, approvals, and problems.
    1. **Data and integration**  

        Highlight how data captured at each stage within Dynamics 365 can inform decision-making in subsequent phases. Make sure to discuss where the data is currently stored and highlight how it will be captured and migrated into Dynamics 365. Be sure to discuss volumes, and how historical data is handled, especially for assets that are partially depreciated.

1. **Conclusion**:  

    Make sure the graphic is updated and key points are documented. All stakeholders should agree on the primary scenarios that you model in the next phase. Document any key risks, actions, problems, and decisions against the process in Azure DevOps or the RAID log where you are managing the project.

Document the outcome of the selection of the elements that define the key end-to-end processes or scenarios, first visually at the storyboard level and then in more detail as user stories, for example.  

In practical use, bring the Visio file to the workshop. Use the workshop to highlight the concrete elements that you need for this concrete implementation project. In the sample storyboard, that might mean that this organization primarily creates assets by *buying* them, as opposed to *developing* them. They call out the *buy* scenario with a red outline.
Here are the steps we suggest you take:

1. Identify the stakeholders from the template.
1. Schedule the meeting and use the agenda in the template as a starting point.
1. Start with the business process areas (the white boxes at the top of the diagram) to identify the high-level scope of the project.
1. Mark the primary scenarios or paths to take.

    1. Each scenario is a demo case.
    1. Each path is an end-to-end test case.
    1. Each bullet point is a user story with one or more requirements.
1. Clear any scenarios that you don't need.
1. Add any missing scenarios.
1. Use the questions in the template to drive the discussion.
1. Document requirements and other findings.
1. Complete the relevant tasks in Azure DevOps.

## Workshops for storyline design review

The storyline design review workshop is a collaborative session that brings together key stakeholders from across the organization, including the implementation partners. During the workshop, the group reviews, validates, and refines the end-to-end business process storylines developed during the scenario board discovery workshops. This workshop serves as a bridge between high-level process mapping and detailed design. It ensures alignment of the business objectives with the solution architecture before moving into deeper design phases.

- **Step-by-step walkthrough**  

  Facilitate a sequential walkthrough of each major process storyline. Highlight how Dynamics 365 can support and enable these flows. Use visual aids or process diagrams to illustrate the main process steps. Make any necessary adjustments to ensure accuracy and completeness. If you identify new elements or exceptions, visually distinguish them - such as with color coding or symbols - to clarify where deviations or enhancements occur.

- **Discussion**  

  Encourage participants to share feedback on how their current practices relate to the proposed storylines. Actively identify opportunities for improvement or areas of concern. For each main process, work with stakeholders to pinpoint the "primary path" - the most critical or representative sequence of activities. Visually highlight it as consensus is reached. This helps focus subsequent design efforts on the most impactful scenarios. Remind the participants that the objective is to derive the closest and best solution within Dynamics 365, and not to recreate the legacy processes in Dynamics 365. Typically, a moderator manages this principle to ensure the discussions are productive and focused.

- **Deep dive**  

  Explore specific blocks or steps where Dynamics 365 provides advanced functionality to streamline operations, such as automation, integration, or reporting features. Demonstrate these capabilities in the system whenever possible to provide clarity on what is available as standard. Discuss any unique requirements or exceptions that might affect the overall process. Document these findings for consideration in future workshops, especially where the standard solution doesn't meet business needs.

- **Horizontal and supporting processes**  

  Review how supporting functions - such as case management, approvals, and risk or issue tracking - integrate with the main process storyline. Demonstrate standard Dynamics 365 capabilities for these supporting processes. Document any gaps or requirements for enhancements. Assess and document the requirements for managing these elements at each stage. Ensure the solution design addresses critical business needs.

  - **Data and integration**  

    Examine how data is captured, stored, and migrated throughout the process steps. Showcase how Dynamics 365 manages data as part of the standard solution. Document any requirements or gaps where additional integration or customization is needed. Discuss volumes, historical data handling, and any special considerations for data integration as part of the transition to Dynamics 365.

- **Conclusion**  

  Update all visual materials and document key decisions, risks, actions, and issues identified during the workshop. Ensure that the workshop outputs include a detailed record of any gaps and requirements that prevent full adoption of the standard Dynamics 365 solution, as well as the rationale for any needed enhancements or customizations. Ensure agreement among stakeholders on the primary end-to-end scenario(s) to be carried forward into the detailed design phase. Record all outcomes and follow-up items in Azure DevOps or the project RAID log, maintaining a clear audit trail for future reference.

## Workshops for detailed design

A design workshop is a collaborative session where stakeholders, including business users, IT professionals, and consultants, come together to discuss and refine the functional requirements of a new technology solution. The primary purpose of the workshop is to take the information from the storyboarding process and vet out more details for the functional requirements. This process helps ensure that the solution meets the needs of the business and is aligned with the overall project goals.

The business process catalog aims to provide at least one design workshop for each level 2 business process area. Some business process areas might include multiple design workshops. For example, the acquire to dispose end-to-end process includes a level two business process area for acquiring assets. This area includes three default workshops: one for fixed assets, one for asset leases, and one for capital projects. For each business process area that's in scope for a given project, conduct at least one design workshop. In many cases, multiple workshops might be required. The separation of the design workshops is often dictated by the software structure and design of the Dynamics 365 applications but industries or business models might separate them as well.

During the sales cycle, gather enough detail to determine the level two business processes areas that are in scope and select the design workshops that are relevant to the project.

### Objectives of the detailed design workshops

Each workshop should have a predefined set of objectives to help drive the outcome of the workshop. Below is a list of general workshop objectives for all design workshops. To clarify and refine the functional requirements of the new technology solution.

- To ensure that all stakeholders have a shared understanding of the proposed solution.
- To identify any gaps or issues in the proposed solution and address them.
- To configure a working solution that can be demonstrated after the workshop.
- To prepare for the next step, typically referred to as a conference room pilot or demonstration.

In addition to these objectives, the Microsoft Business Process Catalog default design workshops aim to provide a list of more specific objectives for the workshop. You might need to enhance or extend these objectives for a specific organization, industry, or ISV solution that is included in your project scope.

### Delivery of the detailed design workshops

Each workshop includes an agenda and a list of default key questions to ask during the workshop. The list of questions isn't an exhaustive list of all questions, but rather a starting point to help drive the discussion and to make key decisions that are required to configure the Dynamics 365 solution. The key questions are designed to be specific to the end-to-end process, but the following list of questions are general questions that you can use to help form the basis of a design workshop for a custom business process or solution.

- What are the key business processes that the new technology solution needs to support?
- What are the specific functional requirements for each business process?
- Are there any existing systems or processes that need to be integrated with the new solution?
- What are the potential risks or challenges associated with the implementation?
- What are the success criteria for the new technology solution?

### Inputs and outputs of the detailed design workshops

Use the following guiding principles to help define the inputs and outputs that you should capture during the design workshop. The Word templates include a draft of the inputs, which you might need to modify or update during the workshop or in preparation for the workshop. The Workshop assumptions that are defined on each workshop help further define any additional inputs or required information for the workshop.

- Input

  - Information from the storyboarding process, including key scenarios and user journeys.
  - Visual representations of the process flow.
  - Stakeholder feedback and business requirements.

- Output

  - A detailed and refined set of functional requirements.
  - A configured working solution that you can demonstrate.
  - A clear understanding of the proposed solution and its impact on users.
  - Identified gaps or problems that you need to address before the next phase.

## Related content

- [Custom work item type for workshops in the Dynamics 365 business process catalog](about-import-catalog-devops-workshop-work-item-type.md)  
- [Overview of the business process catalog levels](about-catalog-levels.md)  
- [Other work item types in the business process catalog](about-devops-work-items-other.md)  
- [Use the business process catalog as a template in Azure DevOps Services](about-import-catalog-devops.md)  
- [Introduction to the business process catalog for Dynamics 365 apps and services](about.md)  
