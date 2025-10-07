---
title: Navigate the business process catalog in Mavim
description: Learn how to navigate the business process catalog in Mavim to enhance your Dynamics 365 implementation strategy.
author: vibhutinair23
ms.author: vibhutinair
ms.topic: how-to
ms.date: 07/17/2025
---

# Navigate the business process catalog in Mavim

This article describes how to easily navigate up and down through the different levels of processes in the business process catalog in Mavim, an external software company. Find the Mavim solution in the [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/apps/mavimbv1671629332610.mavim_bpm?tab=Overview).

## Use the business process catalog in Mavim during the Strategize phase

The information from the business process catalog built into Mavim's Business Process Management platform allows you to take over the diagnostic phases of your project. This pre-existing operational framework provides a foundational vision for the project, requiring adjustments based on specific company needs and changes. Later articles elaborate on the logistics of scoping, defining process activity status, and storyboarding and story designing through the modification of existing flows to achieve the final design.

### Fit-to-standard analysis with business process catalog in Mavim

The business process catalog in Mavim accelerates and eases the fit-to-standard analysis when determining the projected landscape based on goals. The Mavim platform allows organizations to analyze existing processes and identify areas for improvement, which is essential for defining a strong implementation strategy. With access to a library of pre-built process templates based on Microsoft's standard configuration, organizations can use industry and application best practices to figure out the differences between a best-practice model, and how their business currently is operating. This accelerates the process mapping exercise in the strategy phase and provides a valuable benchmark for process design.

The outcome of using the business process catalog in Mavim during the Strategize phase is a well-defined, strategic approach to Dynamics 365 implementation. It ensures that all stakeholders are aligned, processes are understood and optimized, and the implementation strategy is grounded in best practices. This leads to more efficient operations, reduced risks, and a higher likelihood of successful project outcomes all built at the beginning.

### Use the business process catalog in Mavim for strategizing

Use the Mavim platform to navigate through the business process catalog. There are multiple levels of processes going from Level 1 to Level 4.

- Level 1: End-to-end scenarios
- Level 2: Process areas
- Level 3: Unique business processes

    At level 3, actual process diagrams visualize the processes. On this level, scenarios and configurations are connected to the processes.

- Level 4: Scenarios

Scenarios describe when and how processes occur, and configurations translate processes to the actual functionality in the Dynamics 365 apps that need to be configured during the implementation project.

In the Strategize phase, it's all about getting a clear understanding of the business processes and their attributes that are covered by a Dynamics 365 implementation.

Before you begin, you must have the following prerequisites:

- You must have access to the Mavim BPM tool.
- Import the business process catalog for Dynamics 365 into your Mavim environment.
  - To gain access to the free-trial environment already built, go to [Free Trial of the business process catalog in Mavim](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/mavimbv1671629332610.mavim_bpc_freetrial?tab=Overview).
  - To learn how to connect the two, learn more at [Import the Catalog in Mavim using a Power Automate Flow](/dynamics365/guidance/business-processes/about-import-catalog-mavim).

:::image type="content" source="media/about-catalog-mavim-business-process-catalog.svg" alt-text="Diagram of the Dynamics 365 Business Process Catalog, showing the various business processes." lightbox="media/about-catalog-mavim-business-process-catalog.svg":::

To navigate the business process catalog in Mavim, follow these steps:

1. **Access the business process catalog**

    Once logged into Mavim, you should see the imported business process catalog. If you don't, click **Home**, as it's listed as a distinct area or module within the tool.

1. **Understand the high-level structure**

   The catalog is organized hierarchically. You can typically find high-level end-to-end processes. These represent major business flows, such as *prospect to quote*, *order to cash*, or *source to pay*.

1. **Drill down into end-to-end processes**

    To explore the processes within a specific end-to-end flow, click the name of that process. For example, click *order to cash*.

1. **Navigate to lower-level processes**

    Within an end-to-end process, you can find more specific processes or sub-processes. Continue to click the names of these processes to delve deeper. For example, within *order to cash*, you might find *manage sales orders*. Clicking *manage sales orders* might then lead to *enter sales orders*.

1. **View detailed process diagrams**

    - At the lowest level, you can typically find a process diagram. This visual representation illustrates the steps, activities, and roles involved in a specific process.
    - Identify the process diagram icon or name and click it to open the diagram.
    - Observe the elements of the diagram. Look for activities, decision points, roles (who is doing what), and the flow of the process. For example, the *enter sales orders* process opens a detailed diagram showing the steps involved in entering a sales order.

1. **Explore connections between processes**

    - Within the process diagrams, elements (activities or subprocesses) might be clickable.
    - Clicking these elements might allow you to jump directly to related process diagrams, enabling you to see how different processes connect.

1. **Navigate back**

    To return to the previous level in the process hierarchy, click :::image type="content" source="media/back-button.svg" alt-text="Screenshot of the back button."::: **Back** within the Mavim interface.

    :::image type="content" source="media/about-catalog-mavim-navigate-back.svg" alt-text="Diagram of navigating back in the Dynamics 365 Business Process Catalog." lightbox="media/about-catalog-mavim-navigate-back.svg":::

1. **Access additional process information**

   - Alongside the process diagrams, the business process catalog often contains other valuable information. To show the tabs, click :::image type="content" source="media/focus-button.svg" alt-text="Screenshot of the focus button."::: **Focus** or to display the process diagram and description side by side click :::image type="content" source="media/move-button.svg" alt-text="Screenshot of the move button."::: **Move**.
   - For example, when viewing the "process supplier invoice," you can find:
     - **Description**: A textual explanation of the process.
     - Related **Configurations**: Settings required in Dynamics 365 to support the process.
     - Related **Scenarios/Patterns**: Different use cases or contexts in which the process might occur.

1. **Understand configuration deliverables**

   - Within the "Relationship" section, you can find specific setup requirements (configuration deliverables) in Dynamics 365 related to the process.
   - Note the different modules. Some configuration deliverables can be particular to certain Dynamics 365 apps.
   - Click a configuration deliverable for more detailed information about what you need to configure.
   - Deep links (if available): Some configuration deliverable items might have direct links to the relevant forms within Dynamics 365 (for example, to the "Charts tolerances" form in F&O). To jump over to the relevant form within Dynamics 365, click :::image type="content" source="media/dynamics365-button.svg" alt-text="Screenshot of the Dynamics 365 button."::: **Dynamics 365**. This allows you to quickly see the connection between the process and the actual system.

1. **Understand scenarios or patterns**

    - The "Scenarios" or "Patterns" in the "Relationship" section describes different contexts or use cases for the same core process. For example, the "process supplier invoices" process can occur in scenarios like "record supplier invoices and perform two-way invoice matching." Understanding these scenarios helps in tailoring the implementation to specific organizational needs.

    :::image type="content" source="media/about-catalog-mavim-understand-scenarios.svg" alt-text="Diagram of understanding scenarios or patterns in the Dynamics 365 Business Process Catalog." lightbox="media/about-catalog-mavim-understand-scenarios.svg":::

1. **Use dashboards for strategic overview (future steps)**

    Mavim's implementation dashboard, accessible as a template based on the business process catalog, serves as a tool for understanding and managing the Dynamics 365 implementation. It facilitates an initial assessment by comparing the out-of-the-box Dynamics capabilities against the target operating model, highlighting the extent of existing coverage and the necessary customization effort. This "fit app to future application model" analysis quantifies and qualifies the gaps, informing program design, budget allocation towards customizations, and providing a detailed breakdown of the required effort.

    By dissecting data across dimensions like risks and organizational priorities, the dashboard aids in sequencing implementation efforts and provides the program management office with comprehensive insights for effective planning and decision-making regarding the digital transformation and its budgetary impact. It also helps pinpoint necessary modules and capabilities aligned with objectives and KPIs, identify impacted value chain areas, and offers a holistic view of the transformation's complexity and associated risks, establishing a baseline for tracking progress and value realization by linking required application modules to defined value drivers.

    These dashboards also can be used to track the scope of the implementation, showing which processes are in or out of scope. This functionality is likely to be covered in a future article.

## Benefits of using the business process catalog in Mavim for strategy

During the Strategize phase, well-defined processes significantly enhance organizational efficiency and productivity. By standardizing processes, organizations ensure consistency and quality in their business operations, setting a strong foundation for the implementation.

By establishing a solid foundation for the project with best-practice processes and thoroughly examining the operating model, you can identify risks early on, ultimately reducing future project costs. Optimizing processes in the Strategize phase leads to cost reductions through better resource usage and waste minimization. Documenting these processes helps identify potential risks early, allowing for proactive mitigation and smoother implementation.

Along with identifying risks within the processes, the Strategize phase ensures that documented processes are scalable, enabling organizations to adapt to changing demands and support future growth. This phase provides valuable insights for data-driven decision-making, ensuring that the implementation strategy is both adaptable and flexible.

## Conclusion

By following these steps, you can effectively navigate the business process catalog within Mavim for Dynamics 365. This initial exploration allows stakeholders and implementation teams to gain a shared understanding of the available out-of-the-box processes, which is a critical first step in the Strategize phase of a Dynamics 365 implementation.

## Frequently asked questions

The following are some frequently asked questions.

### Can the business process catalog be customized to fit specific organizational needs?

Yes, the catalog can be customized to align with specific organizational processes and requirements, allowing for tailored implementation and optimization.

### What industries can benefit from using the business process catalog in Mavim?

The business process catalog is designed to be versatile and can benefit a wide range of industries, including manufacturing, retail, finance, healthcare, and more.

### How does the business process catalog integrate with other Microsoft tools and services?

The catalog in Mavim can integrate with various Microsoft tools and services, such as Azure DevOps, Power Automate, and Dynamics 365, to enhance process management and automation.

## Related content

- [An introduction to the Success by Design framework](/dynamics365/guidance/implementation-guide/success-by-design)
- [Import the Catalog in Mavim using a Power Automate Flow](/dynamics365/guidance/business-processes/about-import-catalog-mavim)
- [An Introduction to the Success by Design Framework](/dynamics365/guidance/business-processes/about-catalog-mavim-success-design-d365)
- [On Demand Webinar: Strategize Phase of Success by Design Business Talk with Mavim](https://www.mavim.com/webinar-strategize-phase-bpc)
- [The Microsoft business process catalog integrated in Mavim](https://www.mavim.com/business-process-catalog-in-mavim)
- [Microsoft Business Process Catalog in Mavim Business Talks Series](https://www.mavim.com/dynamics-business-talks-microsoft)
- [Strategize Phase of Success by Design Video Part 1](https://youtu.be/tRDj189hrLE?si=3HcDkJiH2usFIlWL)
- [Strategize Phase of Success by Design Video Part 2](https://youtu.be/yK0WETITcGQ?si=ayVtfb527VUShvIh)

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Mavim](https://www.mavim.com/) \| Microsoft Partner

Other contributors:

- [Lennard van Leuven](https://www.linkedin.com/in/lennardvanleuven/) \| [Mavim](https://www.linkedin.com/company/mavim/?viewAsMember=true)
- [Siena Pennington](https://www.linkedin.com/in/siena-pennington/) \| [Mavim](https://www.linkedin.com/company/mavim/?viewAsMember=true)
- [Rachel Profitt](https://www.linkedin.com/in/rachelprofitt) \| Principal Program Manager (Microsoft)
