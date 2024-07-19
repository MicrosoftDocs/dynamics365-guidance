---
title: Optimize your implementation with a fit-to-standard and fit-gap analysis
description: Learn how to review your current processes and identify what to change, keep, or add to make the most of your Dynamics 365 implementation.
ms.date: 04/30/2024
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

# Optimize your implementation with a fit-to-standard and fit-gap analysis

When you implement Dynamics 365, you might be tempted to recreate the same processes that you use in your legacy systems. But this approach can lead to problems, such as:

- Costly and unnecessary customizations that require more design, coding, testing, training, and documentation.
- Lost opportunities for innovation and improvement as you stick to the old ways of working.
- Inefficient and siloed processes that don't align with the standard and recommended practices of Dynamics 365 based on thousands of customer organizations.
- Reduced usability and functionality of Dynamics 365 as you force it to fit processes designed for different software.
- Less access to the documentation, training, sample code, and sample data available for Dynamics 365.
- Less ability to apply market and industry knowledge, insights, and experience from Dynamics 365 to your business areas.
- Less ability to use the tools and apps in the marketplace that work with Dynamics 365.
- Less capacity and resources to create customizations that add significant business value as you spend them on customizations that don't.
- More barriers for citizen developers to create fast, low-cost applications using Power Platform as you create a more complex and customized data model or process model.

To avoid these pitfalls, you need to review your current processes and decide what to change, what to keep, and what to add to your Dynamics 365 implementation. This article explains how to use the fit-to-standard and fit-gap analysis methods to optimize your solution.

## Fit-to-standard analysis

Fit-to-standard analysis is a method to compare your current processes with the standard processes available in Dynamics 365. It helps you identify how well the system's configuration and functionality meet your business needs. It also helps you adopt the best practices and recommendations of Dynamics 365 wherever possible, and adapt them only where necessary.

We recommend that you start with fit-to-standard analysis for every project. Here are the steps to follow:

1. **Download the business process catalog**

    This is a list of standard business processes that are supported by Dynamics 365. Identify which business processes are applicable to your business, and which processes you want to configure and use in Dynamics 365. You should create this catalog in the early stages of the project to define the scope of your solution. [!INCLUDE [daf-catalog-get](../includes/daf-catalog-get.md)]  

2. **Use the business process catalog to guide your fit-to-standard analysis**

    Work iteratively through the processes, starting with the high-level core processes and then moving to the more detailed subprocesses and variants. Evaluate how well they fit your business needs and expectations within the system. We recommend that you do these in workshops organized by the level 2 business process areas (Epic work item types) in the business process catalog. Keep in mind that you may need more than one workshop for your organization for some business process areas. For example, if your organization has two lines of business you and therefore two separate sales organizations, you may need to conduct the *Order to cash* workshop twice.  

3. **Configure the system to match the processes in the catalog**

    You don't need to configure everything perfectly at first, but you should have a good, high-level understanding of how the processes can be implemented in Dynamics 365. This helps you create the solution blueprint and set the right culture of "adopt wherever possible, adapt only where justified."

By using this approach, you can benefit from:

- Reducing customizations by delivering your business needs through configuration rather than creating detailed requirements that might be based on your legacy system.
- Reducing the risk of missing requirements by evaluating the fit with the new system based on the richer and broader context of business processes that are more familiar and meaningful to your business users.
- Adopting modern, standard, and market-tested processes embedded in Dynamics 365 that Microsoft and other customers have validated and approved.
- Creating higher-quality solutions that are more agile, usable, and functional, and that allow you to add more value-add custom extensions where needed.
- Enabling faster delivery of the new solution, since you don't need to wait for custom development.
- Supporting your solution more easily with internal and external teams, including Microsoft Dynamics Support.

The benefits of staying within the standard product wherever possible are clear. Implementations that follow this approach, often called vanilla implementations, adopt the Dynamics 365 system with its standard configuration.

:::image type="content" source="media/process-focused-image3.png" alt-text="Diagram of an example of an end-to-end process for purchasing." lightbox="media/process-focused-image3.png":::

## Fit-gap analysis

Fit-gap analysis is a method to identify the gaps between your business needs and the standard processes in Dynamics 365. It helps you decide how to fill those gaps with customizations or extensions. You should do a fit-gap analysis after you complete the fit-to-standard analysis and configuration.

:::image type="content" source="media/process-focused-image4.png" alt-text="Diagram of an example of a gap in an end-to-end process for receiving a purchase order." lightbox="media/process-focused-image4.png":::

In some cases, you might have specialized or innovative processes that aren't part of the standard solution, but that add business value and give you a competitive edge in the market. In these cases, you might want to customize or extend your solution to meet your needs.

However, before you decide to customize or extend your solution, you should consider the following factors:

- The complexity, cost, and time of developing and maintaining customizations or extensions
- The impact of customizations or extensions on the usability, functionality, and performance of Dynamics 365 and other related technologies
- The potential redundancy of customizations or extensions as Dynamics 365 releases new features that might cover your needs
- The different methods available to create customizations or extensions, such as Power Platform or other technologies and solutions

When you evaluate a potential customization or extension, use the process maps to show the impact, not only on the process being directly changed, but also on the connected processes. This way, you can make informed decisions and trade-offs based on the business value and feasibility of your options.

## Non-Microsoft solutions

Another way to fill the gaps in your solution is to buy a solution from a partner or non-Microsoft vendor, also known as an independent software vendor (ISV). This option might be more suitable when you have a significant gap and developing functionality in-house is too complex or costly. You might also lack the resources, budget, or expertise to create and maintain such a solution.

ISV solutions tend to focus on more specialized or industry-specific processes that add value to your business. They also have expertise and experience in the vertical industry processes they cover. You can find many ISV solutions in the marketplace that work with Dynamics 365.

:::image type="content" source="media/process-focused-image5.png" alt-text="Diagram of an example of an ISV solution that adds taxes to an end-to-end purchase order process." lightbox="media/process-focused-image5.png":::

Dynamics 365 is designed to meet standard business processes, but it also has the flexibility to customize and integrate external applications. You can use a combination of standard, customized, and partner solutions to build an optimal solution for your needs. Using the business process catalog and maps can help you communicate and collaborate with your project team, implementation partner, citizen developers, professional developers, and ISV vendors.

## Next steps

- [Define your requirements](process-focused-solution-define-requirements.md)
- Follow the [checklist](process-focused-solution-checklist.md) to prepare for your implementation
- Read a [case study](process-focused-solution-case-study-journey.md) about a company that implemented Dynamics 365 using a process-focused approach
