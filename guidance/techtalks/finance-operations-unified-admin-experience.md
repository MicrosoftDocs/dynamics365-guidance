---
title: Modernizing the admin experience for finance and operations apps
description: Find a TechTalk video that talks about the gradual modernization of the admin experiences for Dynamics 365 finance and operations apps through the connection to the Power Platform admin center.
ms.date: 09/11/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Modernizing the admin experience for finance and operations apps in the Power Platform admin center

The landscape of enterprise software management is evolving rapidly, and with that, the need for a more streamlined and efficient administrative experience has never been greater. Microsoft Power Platform provides a suite of capabilities for Dynamics 365 applications in the Power Platform admin center. Over time, more and more management capabilities will be migrated from Microsoft Dynamics Lifecycle Services to the Power Platform admin center. This article explores the key features and benefits of this unified experience, providing insights into how it simplifies IT administration and enhances operational efficiency.

We based this article on [a TechTalk](https://youtu.be/24RS5YgXnEc?si=Ou_CGQpB2V3a9w3x) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/techtalk-DTV054EXT-unified-admin-slide.png" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/24RS5YgXnEc?si=Ou_CGQpB2V3a9w3x":::

Learn more about the consolidation of administrative experiences at [Microsoft Power Platform integration with finance and operations apps](/dynamics365/fin-ops-core/dev-itpro/power-platform/overview).

## The shift to managing environments in the Power Platform admin center

For many years, Dynamics Lifecycle Services was where you managed environments in solutions with Dynamics 365 finance and operations apps. However, we're moving more management capabilities from Lifecycle Services to the Power Platform admin center, which results in a more integrated and cohesive administrative experience.

In Lifecycle Services, you manage environments such as sandbox, production, and developer instances as separate entities, each requiring individual attention. The Power Platform admin center changes this by introducing a container-based environment model. This way,  a single environment can house multiple applications, including Dynamics 365 apps, Power Apps, and custom integrations, all sharing the same data and underlying infrastructure. This shift towards a unified environment not only simplifies management but also enhances the scalability and flexibility of your IT infrastructure.

## Key features of the new admin experience

- **Centralized Management Interface:** One of the most significant advantages of the unified admin experience is the centralized management interface. Administrators now have a single portal to manage all aspects of their environments, from backups and restores to user permissions and application management. This eliminates the need to switch between different tools and interfaces, reducing the learning curve and making the overall management process more intuitive.

- **Enhanced Environment Management:** The Power Platform admin center allows for more granular control over environments. Administrators can now see all environments across a tenant in a single view and perform actions like backups, restores, and history tracking directly from the environment list. This level of control is a marked improvement over the more compartmentalized approach in Lifecycle Services.

- **AI-Powered Recommendations:** The new advisor feature within the Power Platform admin center uses AI to provide administrators with actionable insights. By analyzing telemetry data, it offers recommendations to optimize performance, enhance security, and manage resources more efficiently. This proactive approach to environment management helps prevent issues before they arise and ensures that your systems are running at peak efficiency.

- **Comprehensive Licensing and Billing Insights:** Managing licenses across multiple environments can be a complex task. The Power Platform admin center simplifies this by providing detailed insights into license utilization, including the ability to see which environments are consuming the most resources and whether your current licensing setup is sufficient. This transparency allows for more informed decision-making and helps avoid unexpected costs.

- **Automation and Scripting Support:** Automation is at the heart of the unified admin experience. With built-in support for PowerShell and other scripting tools, administrators can automate routine tasks such as environment provisioning, copying, and even transitioning data between environments. This not only saves time but also reduces the risk of human error, leading to more reliable operations.

## Licensing and role management

One of the key areas of focus in the unified admin experience is licensing and role management. In the Power Platform admin center, only designated administrators can deploy and manage environments. This is controlled through Microsoft Entra ID roles, with the two primary roles being *Dynamics 365 Administrator* and *Power Platform Administrator*.

These roles allow for fine-grained control over who can create and manage environments, ensuring that only authorized personnel can make changes that affect the organization's IT infrastructure. Additionally, the ability to delegate administration to partners through delegated administration privileges adds another layer of flexibility, particularly for organizations that work closely with third-party vendors.

## Environment provisioning and management

Creating and managing environments has been greatly simplified in the Power Platform admin center. Whether you need to set up a new sandbox, a developer environment, or a production instance, the process is streamlined and can be automated through PowerShell scripts.

One of the most notable improvements is the ability to perform full environment copies. In Lifecycle Services, you could only copy the database. But in the Power Platform admin center, you can copy both data and code. This includes all customizations, ISV solutions, and even configurations, providing an exact replica of the source environment. This feature is invaluable for troubleshooting and testing scenarios, where having an identical environment can significantly reduce the time and effort required to resolve issues.

Additionally, the new transactionless copy feature addresses storage concerns by allowing administrators to copy only the necessary configuration and reference data, without the transaction data that often bloats storage usage. This can lead to significant reductions in storage costs, particularly in environments where multiple copies are required for testing and development purposes.

## Conclusion

The unified admin experience for Dynamics 365 Finance and Operations marks a new era in enterprise software management. By consolidating management tools, enhancing automation capabilities, and providing deep insights into environment usage and licensing, Microsoft has created a platform that not only simplifies the lives of IT administrators but also empowers organizations to operate more efficiently and effectively.

For more detailed guidance on how to use the Power Platform admin center and to access the full suite of features discussed, visit the [Microsoft Documentation](/dynamics365/fin-ops-core/dev-itpro/deployment/cloud-deployment-overview).

The future of enterprise IT management is here, and it's unified, streamlined, and incredibly powerful.

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)

- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)

- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
