---
title: Optimize your implementation with a fit-to-standard and fit-gap analysis
description: Learn how to review your current processes and identify what to change, keep, or add to make the most of your Dynamics 365 implementation.
ms.date: 01/30/2026
ms.update-cycle: 1095-days
ms.topic: how-to
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

# Optimize your implementation by using fit-to-standard and fit-gap analysis

During an implementation project with Dynamics 365 apps, you might be tempted to recreate the same business processes that the organization uses in their legacy systems. But this approach can lead to problems, including costly and unnecessary customizations that require more design, coding, testing, training, and documentation. This article explains how to use the fit-to-standard and fit-gap analysis methods to optimize your solution.

## Fit-to-standard analysis

Fit-to-standard analysis is a method to compare your current processes with the standard processes available in Dynamics 365. It helps you identify how well the system's configuration and functionality meet your business needs. It also helps you adopt the best practices and recommendations of Dynamics 365 wherever possible, and adapt them only where necessary.

Start fit-to-standard analysis for every project. The following list calls out the main steps:

- Download the business process catalog

  This catalog lists standard business processes that Dynamics 365 supports. Identify which business processes apply to this project and which processes you must configure for use in Dynamics 365. To define the scope of your solution, create this catalog in the early stages of the project.  

  [!INCLUDE [daf-catalog-get](../includes/daf-catalog-get.md)]  

  By using the business process catalog as work items in Azure DevOps Services, you can manage the entire project using agile methodologies or any other methodologies that you prefer. Learn more at [Use the business process catalog as a template in Azure DevOps Services](../business-processes/about-import-catalog-devops.md).

  Alternatively, import the catalog to Mavim so you can visualize the business processes that you want to include in this implementation project across the Success by Design phases. Learn more at [Import the business process catalog in Mavim](../business-processes/about-import-catalog-mavim.md) and related articles. The following image illustrates the use of the catalog in Mavim.

  :::image type="content" source="../business-processes/media/about-catalog-mavim-business-process-catalog.svg" alt-text="Diagram of the business process catalog in Mavim with the end-to-end scenarios on the left side and Source-to-pay on the right side." lightbox="../business-processes/media/about-catalog-mavim-business-process-catalog.svg":::

- Use the business process catalog to guide your fit-to-standard analysis

  Work iteratively through the processes. Start with the high-level core processes, and then move to the more detailed subprocesses and variants. Evaluate how well they fit the business needs and expectations. Learn more at [Standardize business processes during a Dynamics 365 implementation](../business-processes/standardize-business-processes.md).

  Organize these evaluations in workshops by the level 2 business process areas in the business process catalog. For some business process areas, you might need more than one workshop. For example, the organization has two lines of business and therefore two separate sales organizations, so you set up two workshops to define the *Order to cash* business processes. Learn more at [Workshops for Dynamics 365 implementation projects](../business-processes/about-workshops.md).  

- Configure the solution to match the processes in the catalog

  You don't have to configure everything perfectly at first, but you should have a good, high-level understanding of how the processes can be implemented in Dynamics 365. This understanding helps you create the solution blueprint and set the right culture of "adopt wherever possible, adapt only where justified".  

This approach offers several benefits, including the following list:

- Reduces customizations by delivering your business needs through configuration rather than creating detailed requirements that might be based on your legacy system.
- Reduces the risk of missing requirements by evaluating the fit with the new system based on the richer and broader context of business processes that are more familiar and meaningful to your business users.
- Adopts modern, standard, and market-tested processes embedded in Dynamics 365 that Microsoft and other customers validated and approved.
- Creates higher-quality solutions that are more agile, usable, and functional, and that allow you to add more value-add custom extensions where needed.
- Enables faster delivery of the new solution, since you don't need to wait for custom development.
- Supports your solution more easily with internal and external teams, including Microsoft Support.

The benefits of staying within the standard product wherever possible are clear. Implementations that follow this approach, sometimes called "vanilla implementations", adopt the Dynamics 365 apps with the standard configuration to the extent that works for the organization.

:::image type="content" source="media/process-focused-image3.png" alt-text="Diagram of an example of an end-to-end process for purchasing." lightbox="media/process-focused-image3.png":::

## Fit-gap analysis

Fit-gap analysis is a method to identify the gaps between your business needs and the standard processes in Dynamics 365. It helps you decide how to fill those gaps with customizations or extensions. Perform a fit-gap analysis after you complete the fit-to-standard analysis and configuration.

:::image type="content" source="media/process-focused-image4.png" alt-text="Diagram of an example of a gap in an end-to-end process for receiving a purchase order." lightbox="media/process-focused-image4.png":::

In some cases, you might have specialized or innovative processes that aren't part of the standard solution, but that add business value and give you a competitive edge in the market. In these cases, you might want to customize or extend your solution to meet your needs.

However, before you decide to customize or extend your solution, consider the following factors:

- The complexity, cost, and time of developing and maintaining customizations or extensions
- The impact of customizations or extensions on the usability, functionality, and performance of Dynamics 365 and other related technologies
- The potential redundancy of customizations or extensions as Dynamics 365 releases new features that might cover your needs
- The different methods available to create customizations or extensions, such as Power Platform or other technologies and solutions

When you evaluate a potential customization or extension, use the process maps to show the impact, not only on the process you're directly changing, but also on the connected processes. This way, you can make informed decisions and trade-offs based on the business value and feasibility of your options.

## Non-Microsoft solutions

Another way to fill the gaps in your solution is to buy a solution from a partner or non-Microsoft vendor. This option might be more suitable when you have a significant gap and developing functionality in-house is too complex or costly. You might also lack the resources, budget, or expertise to create and maintain such a solution.

Partner solutions tend to focus on more specialized or industry-specific processes that add value to your business. They also have expertise and experience in the vertical industry processes they cover. You can find many solutions in the marketplace that work with Dynamics 365.

:::image type="content" source="media/process-focused-image5.png" alt-text="Diagram of an example of a partner solution that adds taxes to an end-to-end purchase order process." lightbox="media/process-focused-image5.png":::

Dynamics 365 is designed to meet standard business processes, but it also has the flexibility to customize and integrate external applications. You can use a combination of standard, customized, and partner solutions to build an optimal solution for your needs. Using the business process catalog and maps can help you communicate and collaborate with your project team, implementation partner, citizen developers, professional developers, and software development company vendors.

## Common pitfalls

The following list outlines common pitfalls.

- You lose opportunities for innovation and improvement when you stick to the old ways of working.
- You create inefficient and siloed processes that don't align with the standard and recommended practices of Dynamics 365 based on thousands of customer organizations.
- You reduce the usability and functionality of Dynamics 365 by forcing it to fit processes designed for different software.
- You have less access to the documentation, training, sample code, and sample data available for Dynamics 365.
- You have less ability to apply market and industry knowledge, insights, and experience from Dynamics 365 to your business areas.
- You have less ability to use the tools and apps in the marketplace that work with Dynamics 365.
- You spend capacity and resources on customizations that don't add significant business value.
- You create more barriers for citizen developers to create fast, low-cost applications using Power Platform by creating a more complex and customized data model or process model.

To avoid these pitfalls, review the current processes and decide what to change, what to keep, and what to add to the new Dynamics 365 implementation. Find inspiration in this article, but also check the guidance in the following articles:

- [Process maturity models](../business-processes/process-maturity-introduction.md)  
- [Standardize business processes](../business-processes/standardize-business-processes.md)  

## Next steps

- [Define your requirements](process-focused-solution-define-requirements.md).
- [Base the implementation lifecycle on business processes](process-focused-solution-implementation-lifecycle.md).  
- Follow the [checklist](process-focused-solution-checklist.md) to prepare for your implementation.
- Read a [case study](process-focused-solution-case-study-journey.md) about a company that implemented Dynamics 365 using a process-focused approach.
- Use the business process catalog to drive [workshops](../business-processes/about-workshops.md) for continuous acceptance testing.  
