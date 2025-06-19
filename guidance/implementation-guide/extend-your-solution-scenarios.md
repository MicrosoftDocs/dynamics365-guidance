---
title: Customize and extend Dynamics 365 apps
description: Learn how to use app configurations, low-code/no-code customizations, and PaaS solutions to tailor Dynamics 365 apps to your organization's needs.
author: abunduc-ms
ms.author: abunduc
ms.date: 01/24/2024
ms.topic: concept-article
ms.custom:
  - evergreen
  - ai-seo-date: 01/24/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Customize and extend Dynamics 365 apps

Dynamics 365 offers many features out of the box. But sometimes you need to go beyond the standard capabilities to meet your organization's goals.

You can customize and extend Dynamics 365 apps in different ways, from simple setup and configuration changes to advanced platform as a service (PaaS) solutions. In this article, we'll show you the levels of customization and extension you can use and when they make sense.

## App configurations

Some organizations want to stick to the standard features as much as possible. That doesn't mean they can't tweak some settings. App configuration changes are easy to make and don't require professional developers. They let you personalize the app to suit your needs, such as changing the theme to match your brand.

You might need to do some due diligence before changing some settings, even if they're part of the core service. For example, you might need to consider security, integration, or embedded intelligence settings. You might also need to check out new features that come with service updates.

App settings are the safest and least disruptive way to customize your app. You should always try them first before looking for other options.

## Low-code/no-code customizations

One thing that sets Dynamics 365 apps apart from other software as a service (SaaS) products is the powerful customization capabilities they offer through "what you see is what you get" (WYSIWYG) designers and expression-based languages. These tools reduce the implementation effort and help you get more involved in designing and configuring your app.

With low-code/no-code customizations, you can take advantage of the best practices and patterns that the platform provides. You don't have to worry about the low-level details or the potential pitfalls of complex code. The platform handles and optimizes the logic for you. You only need to focus on testing the functional components. Of course, you still need to pay attention to the effect on performance, usage, and service boundaries.

Typically, customizations let you modify the user interface and change things like field settings, the security model, business processes, and visualization components. These changes help you improve data quality and reduce repetitive tasks. They also help you adjust how information is organized and displayed to users.

With customizations, you can tailor your app to fit your industry or business processes better. You can add specific functionality for specific roles or personas. You can also streamline the user experience so everyone can focus on what matters most to their work.

Low-code and no-code customizations are the best way to extend your app when changing the app settings doesn't meet your requirements.

## Extend using pro dev

Over the years, low-code/no-code customizations have improved a lot, reducing the need for professional developers to make app changes. But for cases or scenarios that you can't achieve with configurations or customizations, you can use the custom code execution capabilities of Dynamics 365 apps.

Dynamics 365 apps support extension programming models that let you use your existing skills and expertise for advanced scenarios. Depending on the app and functionality you want to extend, these models generally support .NET-based languages, software development kits (SDKs), and open-source libraries for JavaScript and HTML5.

The key thing to remember when using code-based extensions is to understand the extensibility framework of Dynamics 365 and only use the documented extension patterns. Don't use unsupported techniques that might break the service level agreements or have a negative impact on the service.

It's important that your developer teams have the latest SDKs available. They should also know about community-based tools and samples that can boost their productivity, even if Microsoft doesn't support them directly.

## Extending into PaaS

In some scenarios, you might want to use PaaS components to extend your app and add powerful capabilities that address complex requirements. Dynamics 365 apps are designed to let you extend them by using the underlying Azure capabilities. This is called the no-cliffs extension approach. You can start with SaaS, and then for the most challenging scenarios, extend into PaaS. This way, you don't have to worry about being limited by the platform.

This no-cliffs extension gives you the best of both worlds. The SaaS app gives you the ready-made features and the options and methods to extend them. The PaaS extensions enrich your solution architecture by providing scalable and robust mechanisms that handle heavy processing outside of your app.

For example, you can use IoT Intelligence add-in for Finance and Operations apps. This add-in integrates Internet of Things (IoT) signals with data in Finance and Operations apps to produce actionable insights in Power BI dashboards and automation alerts, as shown in the following diagram:

:::image type="content" source="media/extend_solution_IOT.png" alt-text="Diagram showing how IoT Intelligence add-in integrates IoT signals from Azure IoT Hub with data from Dynamics 365 Finance and Operations apps to produce insights in Power BI dashboards and reports." lightbox="media/extend_solution_IOT.png":::

Another example is Connected Field Service for IoT Central, which provides a direct integration between Dynamics 365 Field Service and Microsoft Azure IoT Central to monitor and manage IoT devices, as shown in the following diagram:

:::image type="content" source="media/extend_solution_IOT_FieldService.png" alt-text="Diagram showing how Connected Field Service for IoT Central integrates Dynamics 365 Field Service with Azure IoT Central to monitor and manage IoT devices, trigger alerts and actions, and create work orders and service requests." lightbox="media/extend_solution_IOT_FieldService.png":::

In both examples, you can use PaaS to further extend your app. You can do the same for your specific requirements that can use PaaS features as part of your extension architecture. This approach can be valuable because it reduces the maintenance costs and complexity of your solution compared to a fully custom-built extension.

One example of this approach is when you use Azure Logic Apps. Logic Apps provides a serverless engine to build automated workflows to integrate apps and data between cloud services and on-premises systems. With Logic Apps, you can trigger workflows based on events or timers and use connectors to integrate applications and facilitate business-to-business communication. Logic Apps is integrated seamlessly with Azure Functions, as shown in the following diagram:

:::image type="content" source="media/extend_solution_AzureLogicApps.png" alt-text="Diagram showing how Azure Logic Apps and Azure Functions can be used to integrate Dynamics 365 apps with other cloud and on-premises systems, trigger workflows based on events or timers, and execute custom code in serverless functions." lightbox="media/extend_solution_AzureLogicApps.png":::

Azure Functions is an event-driven serverless compute platform that can also solve complex orchestration problems. With it, you can move some of the heavy computing processes away from Dynamics 365 apps.

With Azure Functions, you can code your own workflow definition and simplify complex, stateful coordination requirements programmatically in event-driven applications. You can also take advantage of many native connectors.

There are many examples of how you can use PaaS to extend the capabilities of your app. Using a platform helps you eliminate the costs and complexity of configuring and managing the infrastructure. It also lets your development teams focus on building the apps and services that add value.

[Learn more extension options with Azure and Power Platform](integrate-other-solutions.md).

## Next steps

- Learn more about the specific considerations and best practices for [extending finance and operations apps](extend-your-solution-guidance-product-fo.md) and for [extending customer engagement apps](extend-your-solution-guidance-product-ce.md)
- Read the [case study](extend-your-solution-case-study.md) of how a company extended its Dynamics 365 app to improve its customer service
- Use the Success by Design [checklist](extend-your-solution-checklist.md) to plan and implement your extensions effectively
