---
title: Customize and extend Dynamics 365 online
description: Learn how you can customize and extend Dynamics 365 as part of your implementation project.  
author: taksatoms
ms.author: tsato
ms.date: 05/16/2023
ms.topic: conceptual
---

# Customize and extend Dynamics 365 online

An online application with rich features also provides powerful capabilities to customize and extend the app to meet specific business requirements. Customizations to the online application can be at several levels. Many involve little code (embracing the low-code/no-code philosophy) and offer the flexibility to tap into the underlying PaaS layer. You can take advantage of professional software development techniques that include custom code.

The article [Extend your solution](extend-your-solution.md) covers the details of customization and app extensions, considerations, and scenarios. In this article, we focus on the principles to keep in mind when making decisions about customizing the application or extending platform capabilities. While these principles broadly apply, in some cases a tradeoff is necessary. For example, the approach might depend on specific situations, in-house skills, timelines, budget, user expectations, processes, or other factors.

## Know the platform

When you switch to a cloud platform such as Dynamics 365, know that it isn't a one-time software purchase. It's an ongoing partnership between the customer and service provider. There's an operating contract that governs the service-level agreement (SLA), security, ongoing updates, and more. Understand how the service runs, and how updates and changes impact your solution (and therefore business). Employ the supported way of extending and customizing the application in harmony with the service contract. With this knowledge and compliance, you can ensure continued support and avoid unexpected issues.

Even when using supported extension techniques, you need to adhere to best practices. For example, the platform might allow you to run synchronous code for up to two minutes when creating a record. But running to the time limit would block a user's UI thread for two minutes when they save a record. Is that acceptable?  

Similarly, you could use custom code to limit access to records and implement a custom security requirement, but certain access mechanisms could bypass your custom code, leading to exposure. The point is to design your customizations carefully. Assess their impact, particularly when those customizations affect the end user's experience or deviate from the security control constructs provided by the platform.

In general, the platform favors the low-code/no-code techniques that rely on configuration rather than custom code, and they should be a preferred approach. However, custom coding may be required in some use cases. Dynamics 365 has a no-cliffs philosophy with limitless possibilities to extend the application using the underlying platform. The ability to address this by using the underlying PaaS is a superpower in the world of SaaS applications.

> [!NOTE]
> Custom coding and PaaS extensions bring extra maintenance responsibilities and are best left to professional development. Even when you use PaaS to extend your solution, serverless technologies are better suited to this approach.

Other factors include solution capacity planning, which should consider the impact of your customizations, and the implications of using certain PaaS technologies that use a pay-as-you-go model. We recommend that your organization establishes guidelines for customizations that take the following points into consideration:

- The platform  
- The user experience  
- Security  
- Approved patterns for integrations  

In addition, enforce best practices with automated checks wherever possible in the build pipeline. Power Platform includes an app checker and app monitor that can help identify unsupported techniques and anti-patterns that can lead to performance and scalability issues.

## Don't mimic your existing system

A common misunderstanding in an implementing project is to try to replicate the legacy system, or to replicate the features of a different cloud app. In other words, lifting and shifting the current on-premises application experiences into the cloud. This mindset limits transformation to the technical aspects of how the application is operated. Attempts to recreate on-premises apps in a SaaS service can lead to excessive customization, prevent you from realizing the true potential of the platform and limit your access to future innovation in the standard service.

To focus on business value, you should adopt a business process–oriented approach. In this approach, the implementation focuses on supporting business processes rather than providing specific technology features. It's important that business requirements aren't muddled with implementation details or dictate a specific approach but focus on a business outcome instead. The final transformed process is facilitated through using platform capabilities instead of replicating the existing solution. It puts focus on the core process and is future-proof, less costly, and easier to maintain than simply lifting and shifting your existing experiences to the cloud. You also avoid technical debt from excessive customizations. Aligning to the platform allows you to maximize its capabilities so you get an evergreen, always up-to-date solution.

## Future-proofing

One of the key principles we have established in this article and throughout this section is getting comfortable with change. SaaS enables you to adopt new features to maintain a competitive edge. These features and capabilities are built on top of an existing baseline of features and tables. Although repurposing or using a custom table may not be unsupported, deviations can severely impact your ability to take advantage of future capabilities or can affect the interoperability of your solution.

In addition to the business process-oriented approach to implementation, we also recommend that you review your existing business processes. Compare them to what the standard application has to offer. You can benefit from adopting standardized processes backed by research and feedback from leading customers in their industries, because you benefit from all that expertise. Using standard processes also makes your business less dependent on expensive and hard-to-maintain customizations.

The Common Data Model (CDM) is an open standard schema for business data created in collaboration with SAP and Adobe, and is used across Dynamics 365 applications. Aligning to the CDM can help future-proof your solution. It can also make sure you can take advantage of enhancements and other business applications across the industry that honor the schema and can easily interpret your data.

Another way to future-proof is to understand your organization's roadmap, investment direction, and latest industry trends so you can better align to the future direction of the platform. You should make it a practice to stay on top of upcoming Dynamics 365 capabilities in the [release notes](/dynamics365/release-plans/index.yml). Plan to roll out these capabilities to keep innovating your business processes.

## Understand the tradeoff

Expect tradeoff decisions to be made when implementing your solution, particularly when it comes to the user experience (UX). In Dynamics 365, the platform provides several out-of-the-box controls and UX patterns that can be reused in a model-driven paradigm to quickly assemble applications. These address common usage patterns and also meet accessibility standards. It's common for a business to make specific requests around application navigation, behavior of a specific control, or even colors to highlight specific controls. From a technical perspective, most of these UX needs can be met either by using custom code to build custom controls or by using a different app paradigm. For example, start with a blank canvas to develop a pixel-perfect UI that you could use in combination with model-driven controls.

Several factors could guide these decisions, including user adoption, but you should also assess the cost-benefit ratio of customization. In some cases, building and maintaining custom controls can be time-consuming and require specialized skills. If you can easily address some scenarios with user training, you can save hundreds of hours of development and test effort. In addition, specialized UX requests often derive from the need to replicate an existing system or just a familiar pattern, even though the requests defy modern UX best practices and accessibility needs.

## Independent software vendors

Independent software vendors (ISVs) are third-party organizations that exclusively develop software or software solutions that are compatible with the service to deliver more capabilities.

An effective way to approach extending your solution is to use an ISV solution from the app marketplace for your platform. This can save time and effort in development and testing, and provide you with a tried and tested solution used by peers in your industry.

Several industry-focused ISVs provide solutions to fill unique product gaps and address specific business needs in industries such as fashion and hospitality. Make sure to perform due diligence when looking for an ISV. For example, an ISV needs to make sure their solution is available for the version you're targeting for go live. Otherwise, deployment timelines can be affected. It's also important that you're aware of the support model for an ISV, their commitment to keep it up to date, and the protection clause if the solution provider goes bankrupt or is sold.

You'll also want to know how the ISV handles deprecation notices for phased out software and update cycles.

The article [Extend your solution](extend-your-solution.md) provides a deeper dive into making a solution work for you.

## Next steps

- Understand the importance of implementing cloud solutions reviewing the [overview](implementing-cloud-solutions.md)
- Understand how to [adopt a cloud mindset](implementing-cloud-solutions-adopt-cloud-mindset.md)
- Review [cloud implementation consideration](implementing-cloud-solutions-cloud-implementation.md) for successful implementation 
- Learn how to successfully [operate in the cloud](implementing-cloud-solutions-operate-in-cloud.md)
- Review the [evergreen cloud](implementing-cloud-solutions-evergreen-cloud.md) approach and the model of continuous updates
- Understand best practices to [upgrade from on-premises to the cloud](implementing-cloud-solutions-upgrade-from-onpremises-to-cloud.md) 
- Review the [checklist](implementing-cloud-solutions-checklist.md) to help with best practices in implementing cloud solutions
- Read the [case study](implementing-cloud-solutions-case-study.md) to see how adopting a cloud mindset and putting together proper strategy can help your organization
