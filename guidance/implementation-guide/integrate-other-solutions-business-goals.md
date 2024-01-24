---
title: Define business goals for integration projects
description: Find guidance on how to define your Dynamics 365 integration strategy so that it aligns with your business goals.
author: abunduc-ms
ms.author: abunduc
ms.date: 05/25/2023
ms.topic: conceptual

---
# Define business goals that map to the business perspective for integration projects

When you're adding an integration with another solution to a Dynamics 365 implementation project, you want to align the project with the overall direction of the business. You want to match each requirement of cross-system processes against the overall goals of the project and the business. To accomplish this, begin your integration work by defining goals that map to the business perspective.

## Reasons for integrating

You might have many reasons why you want to integrate systems in your solution. Given the array of tools available and the vast ecosystem provided by Microsoft Power Platform and Azure, integration across processes and systems is often readily available and a scalable and reliable choice. Here are some examples of when you might want to unify systems by using integration.

### Integration to legacy system

You might have a highly specialized system that you want to keep in place or phase out over time. For example a custom-built or heavily customized system that fits a specific set of requirements for the business. With this approach, you integrate Dynamics 365 apps into the legacy system to get the benefits of both and allow for business processes to span both systems.

### Multi-phased implementation

You might be implementing Dynamics 365 apps in a planned multi-phased approach, starting with a geographic location, a single division, or a single Dynamics 365 app; Finance, for example. In this scenario, some level of integration with the parts of the legacy solution that will be implemented in future phases could be necessary.

### Regulatory requirements

Regulatory, government, and industry data exchange or reporting are often standard practice or required by law in some industries and regions. It's often reported electronically, but more complex exchanges of data could require a more traditional integration approach.

### Financial consolidation

Perhaps your organization is a subsidiary of a larger operation that requires data to be consolidated and reported in a corporate parent entity. This often requires extracts of data to be transformed and loaded into the corporate consolidation system. In some cases, it's the other way around: your organization might expect integration of consolidation and other data from your subsidiaries into your new system.

### Multiple system architectures

Sometimes the Dynamics 365 apps are links in a bigger chain of specialized line-of-business systems. For example, the *Prospect to cash* process might start in one external system where the opportunity is discovered. Then, it goes through quote and order management in the Dynamics 365 Sales app. And the process ends with an integration to other systems for warranty tracking, billing, and financial reporting.

### Extract to reporting solutions

Perhaps you might have invested in building a specialized analytics solution that includes a data warehouse with many years of historical data and tailored reporting on top of it. In that scenario, you might want to extract data from Dynamics 365 apps for transformation and load it into the existing data warehouse.

Many more scenarios aren't described here. Some might even be combinations of several of the examples.

When multiple systems "talk" to each other, systems that perform distinct functions in the business, it's not only about making it work. Integration can enable business processes, reporting, and analytics that wouldn't have been possible otherwise.

## Goals and benefits

Organizations that integrate systems when building their business solution can achieve several key goals and benefits, including:

- Process automation  

  Integration enables the automation of repetitive tasks in the workflow.

- Data availability at the right time  

  Communication between different departments is key. If the sales department depends on information from accounting, integration can help the data to flow at the time that the sales department needs it. Whether the data arrives in real time or in batches, you can program it to arrive at a certain time. The right pattern of communication helps satisfy the different business units.

- Reduced human errors  

  An error in the data like a typo, an incorrect number, or a button pressed at the wrong time could significantly affect your process, or even worse, degrade the customer experience.

- Increased productivity  

  The users become more focused on the processes that add value, since they don't need other systems to retrieve the information they need.

- Process optimization  

  Integration simplifies your processes so that you spend less time executing tasks, thereby adding more value to your business.

- Increased security  

  By automating processes and data movement through integrations, organizations implement better controls for data access and reduce the need for users to directly work with sensitive data.

- Regulatory compliance  

  Automated integrations could help meet some of the controls needed to meet regulatory needs like HIPAA (Health Insurance Portability and Accountability Act) or FDA Regulations in the US.

- Reduced cost of operations  

  Integrations might help reduce repetitive manual activities, human errors, and training activities, which could lead to an overall decrease in cost of operations.

- Avoiding data silos  

  Integrations break down data silos and improve the value of the organization's data. With AI, machine learning, and IoT usage on the rise, this data might help drive better insights, data science, and predictive analytics in your company.

Learn more in the [Integration design for Dynamics 365 solutions](/training/modules/integration/) online training module.

### Integration planning

To properly incorporate business goals into the entire project lifecycle, we recommend you plan the integration architecture in the initial stages of the implementation project.

When planning integrations, it's easy to miss a critical point or underestimate volume or complexity. A step that helps prevent such issues is to create a blueprint of the design before you start any specification work and do some calculations of loads and transaction flow.

> [!NOTE]
> Success by Design highly recommends that you approach integration work the same way as an extension project, by following a defined software development lifecycle (SDLC) that incorporates business stakeholders and collects their buy-in. The SDLC should include requirements, design, development, and testing, as well as performance testing, deployment, and application lifecycle management (ALM). The work-to-define requirements should be business driven and process focused. For more information, see [Process-focused solution](process-focused-solution.md), and [Application lifecycle management](application-lifecycle-management.md).

### Conceptualizing

Creating a blueprint and thoroughly planning the implementation activities also help you formulate the testing and performance testing of the solution later in the implementation. For that reason, integration architecture is a key part of the Success by Design solution blueprint.

To create a blueprint for integration, you can use several types of diagrams, such as the following list.

- **Application integration diagram**  

  The application integration diagram is often a high-level representation of solution architecture. Many styles exist. In its basic form, it provides an overview of which systems in the solution need to be integrated. the diagram also shows what data is exchanged, and the direction of the data flow. Once the overview is established, add details about the specific interface touchpoints, frequency, and volume information. You can also add a link to ALM information, such as a functional design document (or FDD) number or link.

  :::image type="content" source="media/integrate-other-solutions-application-integration-diagram.png" alt-text="A sample of an application integration diagram" lightbox="media/integrate-other-solutions-application-integration-diagram.png":::

- **Interaction diagram**  

  The interaction diagram defines system and user trigger points, data and process flows, and the sequence of events. It can also uncover unforeseen complexity. By following the flow, even nontechnical team members can understand and validate the design before any work has started. The following diagram illustrates a simple three-system interaction diagram for a simulated process flow.

  :::image type="content" source="media/integrate-other-solutions-interaction-diagram.png" alt-text="A sample of an interaction diagram" lightbox="media/integrate-other-solutions-interaction-diagram.png":::

- **Process documentation, mapping, and volume calculations**  

  Once the high-level overviews are defined, we recommend you document the cross-systems processes in more detail, for example by defining user stories, before starting the system-to-system mapping. Mapping can be done as part of a functional or technical design document.

  :::image type="content" source="media/integrate-other-solutions-process-documentation.png" alt-text="A sample of a process documentation diagram" lightbox="media/integrate-other-solutions-process-documentation.png":::

The design document, along with the process definition, should be detailed enough to ensure that everyone agrees on the scope, process, desired outcome, test criteria, and benefits of the integration. Often such a document also contains information about the expected effort and duration. Calculating the volume of transactions that flow through the interface is important because it helps you decide what patterns to use, and ultimately the size of the different platform components and services needed for the integration.

## Next steps

- [Choose a platform](integrate-other-solutions-choose-platform.md)  
- [Choose a design](integrate-other-solutions-choose-design.md)  
- [Choose a pattern](integrate-other-solutions-choose-pattern.md)  
- [Challenges](integrate-other-solutions-challenges.md)  
- [Product-specific guidance for integration scenarios](integrate-other-solutions-guidance-product.md)  
- [Checklist](integrate-other-solutions-checklist.md)  
- [Case study](integrate-other-solutions-case-study.md)  
