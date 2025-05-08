---
title: TechTalk Unified developer experience for Dynamics 365
description: Summary of TechTalk video that talks about the Dynamics 365 finance and operations apps moving towards a unified developer experience with the customer engagement apps.
ms.date: 10/04/2024
ms.topic: concept-article
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Unified developer experience for Dynamics 365 finance and operations apps and customer engagement apps

In today's rapidly evolving technological landscape, businesses are constantly seeking ways to improve productivity, reduce complexity, and streamline development processes. Microsoft introduced a Unified Development Experience (UDE) for Dynamics 365 finance and operations apps. This new developer experience aims at bridging the gap between different platforms and enhancing development agility. This article explores the benefits and key aspects of this unified approach to development, focusing on how it empowers developers and organizations to work more efficiently across diverse environments.

We based this article on [a TechTalk](https://youtu.be/OuEZ1rXkpYYr) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/UnifiedDevelopmentExperience-slide.png" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/OuEZ1rXkpYY":::

> [!TIP]
> This TechTalk targets X++ developers that have worked with Dynamics 365 Finance, Supply Chain Management, and related apps. It doesn't apply to Dynamics 365 Business Central developers.

## The need for a unified developer experience

The introduction of a unified developer experience for finance and operations apps addresses several longstanding challenges in the development ecosystem. Historically, developers working on finance and operations apps applications faced difficulties when integrating with other platforms, particularly Power Platform. These platforms, while powerful in their own right, operated in silos, making it cumbersome to use the strengths of both.

Power Platform, with its low-code and pro-code capabilities, allowed users to create apps and workflows with ease. On the other hand, the finance and operations apps, written in the X++ language, was designed to handle complex tasks such as finance, logistics, and resource management. However, there was no straightforward way to combine the simplicity of Power Platform tools with the robustness of finance and operations apps, resulting in missed opportunities for synergy. This is where the Unified Development Experience comes into play.

## Solving development challenges

One of the key goals of UDE is to simplify the development process by bringing together the best features of both the finance and operations apps environment and the Power Platform. Earlier, developers faced numerous barriers, such as disjointed management tools, complex setup processes, and inefficiencies in debugging and testing across these platforms. The development story for finance and operations apps was often confined to a localized environment. Here, developers must rely on a single-box setup running locally, which limits their ability to collaborate and scale effectively.

The following image is based on a slide from the presentation in the TechTalk and had the title *Reducing Developer Friction*. It shows a visual breakdown of tools and applications available for developers in customer engagement apps and finance and operations apps, excluding Dynamics 365 Business Central.  

:::image type="content" source="media/UnifiedDevelopmentExperience1.png" alt-text="Screenshot of a slide with a diagram with rows as described in the text after the image." lightbox="media/UnifiedDevelopmentExperience1.png":::

The slide is divided into four rows. The top row has the caption **Pro Developers** and shows icons for *Visual Studio*, *Power Platform CLI*, and *ALM Developer tools*. The second row has the caption  **Dynamics 365** and shows icons for the Sales, Customer Insights (then branded as Marketing), Customer Service, Supply Chain Management, and Finance apps. The third row has the caption **Power Platform** with icons for Power Apps, Power Automate, Copilot Studio (then represented by Power Virtual Agents), Power Pages, and Power BI. This third row has a subrow that is dedicated to Dataverse, which supports data management and integration across these platforms. The overall message from this part of the presentation is about unifying tools to simplify the developer experience across Dynamics 365 finance and operations apps and the customer engagement apps.

Moreover, the lack of integration between the Power Platform and finance and operations apps meant that data and functionality couldn't be easily shared between the two. The introduction of UDE bridges this gap, allowing for a more seamless integration, which reduces friction and enhancing collaboration across different platforms.

## Increased developer productivity

One of the most significant improvements brought by UDE is the increase in developer productivity. By simplifying the setup process, Microsoft makes it easier for developers to get started with finance and operations apps development. In the past, setting up a development environment could take hours and was prone to errors, but with UDE, this process is reduced to just a few select. Developers can now focus on solving functional problems for their clients, rather than spending time setting up and maintaining their development environments.

The following image is a screenshot of another slide from the presentation.

:::image type="content" source="media/UnifiedDevelopmentExperience2.png" alt-text="Screenshot of a slide with six blocks with text that is repeated in the text after the image." lightbox="media/UnifiedDevelopmentExperience2.png":::

This image is divided into six blocks in two rows, each highlighting a specific benefit of a unified development experience. The top row contains three blocks with the following text:

1. *Faster innovation using common tools for unified Dynamics solution development*.  
2. *Better business outcomes with turnkey integrations and common capabilities to activate data*.
3. *Workloads are managed more easily with a single simplified administration experience*.

The bottom row also contains three blocks with the following text:

1. *Increased developer productivity and faster dev environment setup*.  
2. *Faster troubleshooting of production issues*.  
3. *Secure / more compliant environments* and *Reduction of TCO*, meaning the total cost of ownership.  

UDE also enables developers to switch between different versions of finance and operations apps environments seamlessly, further enhancing their ability to work efficiently across multiple projects. This flexibility, coupled with the ease of deployment and debugging in the cloud, significantly reduces the time it takes to build, test, and deploy solutions.

## A seamless experience across platforms

One of the core features of the Unified Development Experience is its ability to connect local development environments with cloud-based finance and operations apps environments. This means that while development happens locally on a developer's laptop or workstation, the code runs, it tested, and debugged in the cloud.

With UDE, Visual Studio remains the central tool for finance and operations apps development, now enhanced with the ability to work seamlessly with the Power Platform. The development experience is now more integrated, allowing for easier debugging, testing, and deployment across different environments. Developers can run code in the cloud while managing it locally, ensuring that all processes are synchronized and efficient.

## SQL access and debugging capabilities

A key feature requested by the developer community was better SQL access within the finance and operations apps environment. With UDE, Microsoft introduces the ability to access SQL databases directly from Visual Studio, allowing developers to query data, perform debugging, and troubleshoot issues more efficiently. This feature simplifies the process of connecting to cloud-hosted databases, reducing the time required for data retrieval and analysis.

In addition to enhanced SQL access, UDE provides robust debugging tools, such as the Trace Parser, which allows developers to capture and analyze performance data. This enables detailed performance diagnostics, helping developers to quickly identify and resolve issues.

## Copilot extensions

As AI continues to transform how businesses operate, Microsoft Copilot is an integral part of the Unified Development Experience. Copilot in finance and operations apps is designed to enhance user interactions by using AI-driven capabilities to automate tasks and improve decision-making. UDE allows developers to extend the functionality of the Copilot through the Copilot Studio, making it easier to integrate AI into day-to-day operations.

To provision a new Unified Developer environment, you must first validate the role and license in the Microsoft 365 admin center. Then, you must visit the Capacity report in the Power Platform admin center. Learn more at [Install and configure development tools](/power-platform/developer/unified-experience/finance-operations-install-config-tools).

With Copilot's ability to navigate forms, invoke X++ logic, and process natural language inputs, developers can create more intuitive and efficient user experiences. The integration of AI and automation within the finance and operations apps environment is a critical step toward making business processes more intelligent and responsive.

We recommend you review the following resources:

- [Tutorial: Provision a new environment with an ERP-based template](/power-platform/admin/unified-experience/tutorial-deploy-new-environment-with-erp-template)  
- [New-AdminPowerAppEnvironment](/powershell/module/microsoft.powerapps.administration.powershell/new-adminpowerappenvironment)  

## Streamlined administration and deployment

For administrators, UDE brings a range of benefits by streamlining environment management. In the past, it was a time-consuming process to manage finance and operations apps environments. You needed significant oversight to ensure that updates were applied and environments were running smoothly. With UDE, Microsoft simplifies this process by managing environment updates directly. Not only does it reduce the administrative burden. It also makes sure that environments are always up to date with the latest features and security patches.

Additionally, UDE simplifies the deployment of changes. Deploying code changes, which previously took hours, can now be accomplished in minutes, dramatically speeding up the development lifecycle. This reduction in deployment time, combined with the ability to roll back changes, enhances the overall agility of development teams.

## Conclusion

The Unified Development Experience for finance and operations apps represents a major step forward in simplifying and streamlining the development process across Microsoft's platforms. By bringing together the strengths of finance and operations apps and the Power Platform, UDE enables developers to work more efficiently, reduces friction between environments, and enhances productivity.

Learn more at [Unified developer experience for finance and operations apps](/power-platform/developer/unified-experience/finance-operations-dev-overview).

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)

- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)

- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)

- [Azure Synapse Link documentation](/powerapps/maker/data-platform/export-to-data-lake)

- [Viva Engage : Dynamics 365 and Power Platform Preview Programs : Private Preview: Online Development](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=126835908608)

- [Unified admin experience for finance and operations apps](/power-platform/admin/unified-experience/finance-operations-apps-overview)

- [Unified developer experience for finance and operations apps](/power-platform/developer/unified-experience/finance-operations-dev-overview)
