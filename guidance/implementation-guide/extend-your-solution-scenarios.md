---
title: Scenarios for customizing and extending capabilities in Dynamics 365 implementation projects
description: Get example scenarios for when and how to extend the standard capabilities in Dynamics 365 implementation projects.
author: abunduc-ms
ms.author: abunduc
ms.date: 05/11/2023
ms.topic: conceptual

---

# Scenarios for customizing and extending capabilities in Dynamics 365 implementation projects

Dynamics 365 includes many capabilities. But an implementation project must fulfill an organization's requirements and extend the built-in capabilities.  

Customizations and extensions to the standard Dynamics 365 apps stretch from simple setup and configuration updates to customized Platform as a Service (PaaS) solutions. In this article, we explore the levels at which customization is possible and discuss their relevance.

Some organizations prefer to stay as standard as possible. That doesn't mean that they can't make simple changes with configurations or low-code/no-code customizations using modern tools. Staying standard allows for slight changes, as long as those changes don't highly impact key characteristics of a solution.

## App configurations

Configurations are the out-of-the-box controls that allow makers and admins to tailor the app to the needs of a user. These setting changes are low effort, requiring no support from professional developers. They're a powerful way to make the application your own, for example changing a theme to reflect business branding.

In some cases, due diligence might be required for configurations, even though they are tested and shipped as part of the core service. Examples include security model configuration, out-of-the-box integration setup, and enabling embedded intelligence. Also consider new capabilities delivered via the service updates that might be controlled using the app settings.

App settings are the safest and the least impactful way of tailoring the solution to your needs and should be the preferred approach before exploring another extensibility technique.

## Low-code/no-code customizations

A differentiator for Dynamics 365 apps and the latest generation SaaS products is the powerful customization capabilities made available through "what you see is what you get" (WYSIWYG) designers and descriptive expression-based languages. This paradigm helps significantly reduce the implementation effort and enables businesses to get more involved with design and configuration.

This low-code/no-code approach also guides makers to take advantage of the optimized patterns and best practices, avoiding the potential pitfalls and antipatterns that are observed in a complex code. Because the platform takes care of lower-level details and automatically optimizes the logic, testing is focused on functional components. The impact on performance, usage pattern and service boundaries, however, still needs to be taken into consideration.

Typically, customizations result in user interface modifications and changes to the field settings, security model, business processes, visualization components, and so on. Changes implemented through customizations must ensure data quality and reduce repetitive tasks. They must also adjust visualization components that determine how information is organized and displayed to the users.

With customizations, applications can be tailored to more closely fit organization requirements that are specific to an industry or unique business processes, including specific functionality focused on specific roles or personas. Personalization streamlines the user experience so all users can focus on what is most important to their work.  

Low-code and no-code customizations are the preferred extensibility approach when the requirements aren't satisfied by app configuration changes.

## Extend using pro dev

Over the years the low-code/no-code base configuration capabilities have advanced, reducing the dependency on professional developers for application changes. Edge cases or scenarios that can't be achieved using the configuration-based approach can still exist. In that case, the powerful custom code execution capabilities of Dynamics 365 apps can be applied.

Dynamics 365 apps support extension programming models that enable organizations to use existing expertise within the organization for advanced scenarios. These models, depending on the specific app and functionality extended, generally support .NET based languages, Software Development Kits, and open-source libraries around JavaScript and HTML5.

The key aspect to keep in mind when using code-based customization is to understand the extensibility framework of Dynamics 365 and only use the documented extension patterns. Use of unsupported techniques breaches the service level agreements and can have a potentially severe impact on the live service.

It's important that your developer teams have the latest software development toolkits available to them. They should also know about community based third-party tools and samples. Such tools can drive productivity even when Microsoft doesn't provide direct support for them.

## Extending into PaaS

In some scenarios, organizations use PaaS components to extend solutions and add powerful capabilities that help address complex requirements. Dynamics 365 apps have a core design philosophy that allows our SaaS applications to be extended by using the underlying Azure capabilities. This is referred to as the no-cliffs extension approach. Businesses can start with SaaS, and then for the most complex long-tail scenarios, extend into the PaaS. Doing so alleviates the fear of being limited by the platform.

This no-cliffs extension provides the best of both worlds. The SaaS application provides the off-the-shelf functionalities and the options and methods to extend them. The PaaS extensions further enrich the solution architecture by providing rich and powerful mechanisms that scale and allow heavy processing of operations outside of the business solution.

An example of how this approach is natively used is the Internet of Things (IoT) Intelligence add-in for Finance and Operations apps. This add-in integrates IoT signals with data in Finance and Operations apps to produce actionable insights, as the following illustration shows.

:::image type="content" source="media/extend_solution_IOT.png" alt-text="IOT add-in for finance and operations apps" lightbox="media/extend_solution_IOT.png":::

The same happens with Connected Field Service. Connected Field Service for IoT Central provides a direct integration between Dynamics 365 Field Service and Microsoft Azure IoT Central. It's an add-on solution that brings in Azure IoT PaaS on top of Dynamics 365 Field Service, as shown in the following illustration.

:::image type="content" source="media/extend_solution_IOT_FieldService.png" alt-text="IOT add-in for Field Service" lightbox="media/extend_solution_IOT_FieldService.png":::

In both examples, organizations can use PaaS to further extend the solution. The same can be applied to specific organization requirements that can use PaaS features as part of the extension's architecture. This approach can be valuable because it reduces the maintenance requirements for parts of the solution compared to a fully custom-built extension.

One example of this approach is when organizations use Azure Logic Apps. Logic Apps provides a serverless engine to build automated workflows to integrate apps and data between cloud services and on-premises systems. With Logic Apps, you can trigger workflows based on events or timers and apply connectors to integrate applications and facilitate business-to-business (B2B) communication. Logic Apps is integrated seamlessly with Azure Functions, as the following illustration shows.

:::image type="content" source="media/extend_solution_AzureLogicApps.png" alt-text="Integration pattern with Azure Logic apps and Azure Functions" lightbox="media/extend_solution_AzureLogicApps.png":::

Azure Functions is an event-driven serverless compute platform that can also solve complex orchestration problems. By using it, you can move some of the heavy computing processes away from Dynamics 365 apps.

With Azure Functions organizations can code their own workflow definition and simplify complex, stateful coordination requirements programmatically in event-driven applications, and taking advantage of numerous native connectors.

A multitude of examples demonstrates where PaaS can be applied to further extend the capabilities of the solution. Using a platform helps eliminate the costs and complexity of configuring and managing the required infrastructure, while empowering development teams to focus on building the apps and services that drive value.

Read more about these extension options with Azure and the Power Platform in [Integrate with other solutions](integrate-other-solutions.md).

## Next steps

- Find product-specific guidance at [Extending finance and operations apps](extend-your-solution-guidance-product-fo.md) and [Extend customer engagement apps](extend-your-solution-guidance-product-ce.md)  
- View the case study at [Extension case study](extend-your-solution-case-study.md)  
- Find the checklist at [Extension checklist](extend-your-solution-checklist.md)  
- Return to the overview at [Extend your solution](extend-your-solution.md)  
