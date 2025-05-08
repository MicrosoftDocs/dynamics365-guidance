---
title: Overcome integration challenges in Dynamics 365 projects
description: Learn how to plan ahead for common integration challenges between on-premises and cloud apps in Dynamics 365 projects.
author: abunduc-ms
ms.author: abunduc
ms.date: 01/26/2024
ms.topic: concept-article
ms.custom:
   - ai-seo-date: 01/26/2024
   - ai-gen-docs-bap
   - ai-gen-title
   - ai-gen-desc
content_well_notification: AI-contribution
---

# Overcome integration challenges in Dynamics 365 projects

Many organizations use a mix of on-premises, cloud, and partner apps to run their business. These apps need to talk to each other for different purposes. But integrating them can be difficult and costly. If you don't plan well for integration challenges, you might face delays, errors, or performance issues in your Dynamics 365 projects.

To avoid these problems, you need to consider three main areas of integration challenges: business, technology, and project governance. In this article, we'll explain what these challenges are and how you can address them.

## Business challenges

Integration affects not only the apps you're connecting but also their users and other downstream apps. You need to involve all the relevant stakeholders from the start of your project. You also need to align their expectations and requirements for integration scenarios.

Here are some common business challenges you might encounter:

- **Lack of application owners and stakeholders**. Sometimes, people who own or use other apps that depend on integration don't get involved until it's too late. This can lead to missed deadlines, scope changes, and poor quality. You need to identify and include all the affected apps in your integration design.

- **Misalignment between business owners**. Different business groups might have different needs and views on how to integrate their apps. If they don't agree on a common approach, you might end up with mismatched requirements, budget overruns, and accountability gaps. You need to bring the key owners together and walk them through the scenarios. You also need to explain the pros and cons of different types of integration, such as process, data, and UI integration. And you need to highlight the risks and benefits of each option.

- **Ambiguous and unrealistic expectations**. Sometimes, integration requirements are vague or too demanding. For example, some stakeholders might want to sync large amounts of data in real time or use Dynamics 365 as a reporting tool. These decisions can hurt the scalability and performance of your solution. You need to help them define their requirements clearly and understand the tradeoffs involved in your architecture choices.

- **Lack of business continuity planning**. Integration can also affect how your apps work if there's an outage or a disaster. For example, if your on-premises app goes down, how will it affect the data or process flow in Dynamics 365? You need to define the procedures and actions that your business group will take in such situations.

- **IT-driven requirements and design**. Sometimes, integration is seen as a technical task that doesn't involve the business teams. But successful integration depends on a well-defined cross-system business process. If you don't get enough input from the business teams, you might waste time and resources on trial and error. You need to learn more about their processes and goals before you design your solution. [Learn how to create a process-focused solution](process-focused-solution.md).

## Technology challenges

Many organizations have legacy apps with traditional on-premises architecture. Moving to cloud apps requires following new patterns and best practices for integration. You also need to think about the future needs of your solution, such as performance, extensibility, and maintenance.

Here are some common technology challenges you might face:

- **Inappropriate technology choice**. Some enterprises have an existing architecture that doesn't fit well with cloud patterns. Or they might choose a generic approach that doesn't suit their specific needs. This can result in inefficient or unscalable integration solutions that harm the user experience and adoption. You need to evaluate your current and future needs carefully and choose the right technology for each scenario. You also need to consider factors such as:

  - Synchronous versus asynchronous integration
  - Single record or batch
  - Frequency and direction of integration
  - Message reliability and speed
  - Data volume
  - Time expectations
  - Error management and retries

- **Data security risks**. Integrating on-premises apps with Dynamics 365 can raise security concerns for IT and customers. You need to protect your data from unauthorized access or exposure. You also need to comply with any regulatory requirements that apply to your industry or region. Be sure to address access control, data protection, compliance, and transparency.

- **Storage costs and platform limits**. Dynamics 365 and Power Platform have limits on how much data you can store and how often you can access it. These limits help protect the service quality and performance from disruptions. You need to follow these limits in your integration solution. Otherwise, you might face service throttling, errors, or increased storage costs.

- **Network latency**. Network delays can affect your integration performance, especially if you're transferring large amounts of data. You need to design your data payloads to use the network resources efficiently and avoid performance issues.

- **Anti-patterns**. Some architects don't follow the best practices for Dynamics 365 apps when they integrate them with on-premises apps. This can result in poor performance or errors. You need to avoid these common anti-patterns:

  - Repeated connections between on-premises and cloud apps that slow down the integration. You should send data in batches instead.

  - Latency between your on-premises apps and the Dynamics 365 datacenter that affects the user experience. You should use a cloud service such as Power Automate, Azure Functions, or Azure SQL to reduce the latency impact.

  - Too much data synchronized with Dynamics 365 for reporting purposes that overloads the database. You should use a dedicated datastore for reporting purposes instead.

- **Proprietary technology**. Some customers might use partner technology that doesn't provide enough details or support for easy integration. Sometimes, these issues are discovered late in the project, causing delays and risks. You need to identify and plan for these dependencies early in the project and find alternative solutions if needed.

- **Readiness**. Technology changes fast, and architects need to keep up with the latest trends and patterns. Sometimes, they might choose a familiar approach that isn't the best fit for their current or future needs. You need to assess whether you have enough resources with the right skills and expertise for your chosen technology.

## Project governance challenges

The first stage of your project should include a clear project governance model. Integration can range from simple to complex, depending on your needs and scenarios. If you don't have a good project governance plan, you might encounter gaps and issues in your project execution.

Here are some common project governance challenges you might face:

- **Impact of integration on users, processes, and reporting**. Integration can change how your users work with their apps, how your processes flow across systems, and how your data is reported and analyzed. You need to plan for change management activities, such as communication and training, to help your users adapt to the new integration solution.

- **Performance testing**. Making your solution perform well should be one of your main design goals. This applies to both the integration layer and the app layer. You need to plan for performance testing to identify any bottlenecks or issues before you deploy your solution to users.

- **Development and test environments**. You need to have separate environments for all your apps where you can develop and test your integration solution thoroughly. You also need to have a plan for stub-based testing during the unit testing phase if needed.

By addressing these challenges early in your project, you can avoid many problems and ensure a smooth integration between your on-premises and cloud apps in Dynamics 365.

## Next steps

- Learn about the aspects that are specific to each Dynamics 365 app and how to [integrate them with other solutions](integrate-other-solutions-guidance-product.md)
- Use this Solution by Design [checklist](integrate-other-solutions-checklist.md) to make sure you've covered all the steps and considerations for your integration project
- Read how a public sector infrastructure organization learned how to [choose the right solution for their integration project](integrate-other-solutions-case-study.md)
