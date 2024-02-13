---
title: Customize and extend Dynamics 365 online
description: Learn how to tailor Dynamics 365 to your business needs and take advantage of the underlying platform capabilities.
author: taksatoms
ms.author: tsato
ms.date: 01/11/2024
ms.topic: conceptual
ms.custom:
  - ai-seo-date: 01/11/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
ai-usage: ai-assisted
---

# Customize and extend Dynamics 365 online

Dynamics 365 online is a rich and flexible app that you can customize and extend to meet your specific business requirements. You can customize the app at different levels, from simple configuration to custom code. You can also use the underlying platform as a service (PaaS) layer to extend the app with professional software development techniques.

The article [Extend your solution](extend-your-solution.md) covers the details, considerations, and scenarios of customization and app extensions. In this article, we focus on the principles to keep in mind when you decide how to customize or extend the app. Sometimes, you might need to make tradeoffs based on factors such as your situation, skills, budget, timeline, user expectations, or processes.

## Know the platform

When you use a cloud platform like Dynamics 365, you're not just buying software. You're entering a partnership with the service provider. The service provider has an operating contract that covers the service-level agreement (SLA), security, updates, and more. You need to understand how the service works and how updates and changes affect your solution (and your business). You also need to follow the supported ways of extending and customizing the app to avoid breaking the service contract. With this understanding and compliance, you can ensure continued support and avoid unexpected issues.

Even when you use supported extension techniques, you need to follow best practices. For example, the platform might let you run synchronous code for up to two minutes when creating a record. However, it would block the user interface (UI) for two minutes when the user saves a record. Is that acceptable?

Similarly, you could use custom code to limit access to records and implement a custom security requirement. But some access mechanisms could bypass your custom code and expose your data. The point is to design your customizations carefully and assess their impact, especially when they affect the user experience or deviate from the security controls provided by the platform.

In general, the platform favors low-code/no-code techniques that rely on configuration rather than custom code. You should use these techniques whenever possible. However, some use cases might require custom coding. Dynamics 365 has a no-cliffs philosophy that lets you extend the app using the underlying platform, which gives you limitless possibilities to extend the app in the world of software as a service (SaaS) applications.

> [!NOTE]
> Custom coding and PaaS extensions bring extra maintenance responsibilities and are best left to professional developers. Even when you use PaaS to extend your solution, serverless technologies are better suited to this approach.

Other factors include solution capacity planning, which should consider the impact of your customizations, and the implications of using certain PaaS technologies that use a pay-as-you-go model. We recommend that you establish guidelines for customizations that take the following points into account:

- The platform
- The user experience
- Security
- Approved patterns for integrations

You should also enforce best practices with automated checks in the build pipeline whenever possible. Power Platform includes an app checker and app monitor that can help you identify unsupported techniques and anti-patterns that can cause performance and scalability issues.

## Don't mimic your existing system

A common mistake in an implementation project is to try to replicate the legacy system or the features of a different cloud app; in other words, "lifting and shifting" the current on-premises application experiences to the cloud. This mindset limits the transformation to the technical aspects of how the application is operated. It also leads to excessive customization, prevents you from realizing the true potential of the platform, and limits your access to future innovation in the standard service.

To focus on business value, you should adopt a business process–oriented approach. In this approach, the implementation focuses on supporting business processes rather than providing specific technology features. The business requirements should be clear and focused on the business outcome, not on the implementation details or a specific approach. The final transformed process is facilitated by using platform capabilities instead of replicating the existing solution. This way, you focus on the core process and get a solution that's future-proof, less costly, and easier to maintain. You also avoid technical debt from excessive customizations. Aligning to the platform lets you maximize its capabilities and get an evergreen, always up-to-date solution.

## Future-proofing

One of the key principles we have established in this article and throughout this section is getting comfortable with change. SaaS enables you to adopt new features to maintain a competitive edge. These features and capabilities are built on top of an existing baseline of features and tables. Although repurposing or using a custom table might not be unsupported, deviations can severely affect your ability to take advantage of future capabilities or affect the interoperability of your solution.

In addition to the business process-oriented approach to implementation, we also recommend that you review your existing business processes and compare them to what the standard app offers. You can benefit from adopting standardized processes that are backed by research and feedback from leading customers in their industries. You can benefit from their expertise and make your business less dependent on expensive and hard-to-maintain customizations.

The Common Data Model (CDM) is an open standard schema for business data created in collaboration with SAP and Adobe. It's used across Dynamics 365 applications. Aligning to the CDM can help you future-proof your solution and make sure you can take advantage of enhancements and other business applications across the industry that honor the schema and can easily interpret your data.

Another way to future-proof is to understand your organization's roadmap, investment direction, and latest industry trends. This way, you can better align to the future direction of the platform. You should make it a practice to stay on top of upcoming Dynamics 365 capabilities in the [release notes](/dynamics365/release-plans/index). Plan to roll out these capabilities to keep innovating your business processes.

## Understand the tradeoff

Expect to make tradeoff decisions when implementing your solution, especially when it comes to the user experience (UX). In Dynamics 365, the platform provides several out-of-the-box controls and UX patterns that you can reuse in a model-driven paradigm to quickly assemble applications. These address common usage patterns and also meet accessibility standards. It's common for a business to make specific requests around app navigation, behavior of a specific control, or even colors to highlight specific controls. From a technical perspective, you can meet most of these UX needs either by using custom code to build custom controls or by using a different app paradigm. For example, you can start with a blank canvas to develop a pixel-perfect UI that you can use in combination with model-driven controls.

Several factors could guide these decisions, including user adoption, but you should also assess the cost-benefit ratio of customization. In some cases, building and maintaining custom controls can be time-consuming and require specialized skills. If you can easily address some scenarios with user training, you can save hundreds of hours of development and testing effort. In addition, specialized UX requests often come from the need to replicate an existing system or a familiar pattern, even though they defy modern UX best practices and accessibility needs.

## Independent software vendors

Independent software vendors (ISVs) are partner organizations that develop software or software solutions that are compatible with the service and deliver more capabilities.

An effective way to extend your solution is to use an ISV solution from the app marketplace for your platform. This can save you time and effort in development and testing, and provide you with a proven solution used by peers in your industry.

Several industry-focused ISVs provide solutions to fill unique product gaps and address specific business needs in industries such as fashion and hospitality. Make sure to do your homework when looking for an ISV. For example, an ISV needs to make sure their solution is available for the version you're targeting for go-live. Otherwise, deployment timelines can be affected. You also need to know the support model for an ISV, their commitment to keep it up to date, and the protection clause if the solution provider goes bankrupt or is sold. You also need to know how the ISV handles deprecation notices for phased-out software and update cycles.

## Next steps

- Understand the importance of implementing cloud solutions by reviewing the [overview](implementing-cloud-solutions.md)
- Understand how to [adopt a cloud mindset](implementing-cloud-solutions-adopt-cloud-mindset.md)
- Review [cloud implementation considerations](implementing-cloud-solutions-cloud-implementation.md) for successful implementation
- Learn how to successfully [operate in the cloud](implementing-cloud-solutions-operate-in-cloud.md)
- Review the [evergreen cloud](implementing-cloud-solutions-evergreen-cloud.md) approach and the model of continuous updates
- Understand best practices to [upgrade from on-premises to the cloud](implementing-cloud-solutions-upgrade-from-onpremises-to-cloud.md)
- Review the [checklist](implementing-cloud-solutions-checklist.md) to help with best practices in implementing cloud solutions
- Read the [case study](implementing-cloud-solutions-case-study.md) to see how adopting a cloud mindset and putting together a proper strategy can help your organization
