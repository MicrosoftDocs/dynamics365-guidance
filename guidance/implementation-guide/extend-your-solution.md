---
title: Extend Dynamics 365 apps without compromising performance
description: Learn how to customize Dynamics 365 apps to fit your business needs and avoid common pitfalls of extending cloud solutions.
author: abunduc-ms
ms.author: edupont
ms.date: 07/08/2025
ms.update-cycle: 1095-days
ms.topic: overview
ms.custom:
  - evergreen
  - ai-seo-date: 01/24/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Extend Dynamics 365 apps without compromising performance or security

Dynamics 365 apps offer rich capabilities out of the box, but sometimes you must customize them to fit your specific business processes and requirements. However, extending a cloud solution can have implications for its usability, accessibility, performance, security, compliance, scalability, maintainability, supportability, and future-proofing. You want to strike the right balance between adding value and avoiding complexity, cost, and risk.

In this article, you learn how to:

- [Define your extension strategy](#define-your-extension-strategy) and determine the need, scope, and impact of extending your apps.
- [Consider the key characteristics](#consider-the-key-characteristics) of a cloud solution and how extensions can affect them.
- [Follow the product-specific guidance](#product-specific-guidance) for extending finance and operations apps or customer engagement apps.

## Define your extension strategy

Many organizations migrate to cloud solutions to enjoy the advantages of software as a service (SaaS), such as:

- Out-of-the-box security
- Native integrations with other cloud solutions
- Cost savings
- Improved agility

The evergreen cloud approach allows solutions to evolve with the latest modern features. It's often easier to use off-the-shelf solutions and extend them when needed rather than develop custom solutions from scratch.

### What does it mean to extend?

Extending means customizing a solution to meet your specific business needs. Extensions can vary from minor changes to the user interface of a feature to more complex scenarios like adding heavy calculations after certain events. The depth of the extensions affects how much the off-the-shelf product changes to meet your requirements.

We can categorize extensions into the following types:

- Extending by modifying off-the-shelf functionalities
- Extending by introducing new functionalities on top of a native one
- Creating custom solutions on the platform

### Determine the need

Before you decide to extend a solution, you should be aware of the impact and cost of doing so. You want to add features that empower users and bring business value and efficiency, but not at the expense of key characteristics of the solution. For example, extending an invoicing system could pose risks to operations or disrupt the business because of increased complexity. Such risks are best avoided.

You should also consider whether you depend on another provider to maintain and evolve your extensions. An unresponsive partner can block you from adopting new functionalities.

A common scenario is [extending to integrate with other solutions](integrate-other-solutions.md).

### Don't replicate your legacy solution

When you gather solution requirements, you might be tempted to reproduce every piece of functionality from your legacy solution or even try to mimic the user experience. You might think it reduces the user resistance and drives adoption. But it can also lead to a highly customized solution that fails to apply the strengths of the new platform in favor of familiarity.

The legacy solution was probably in use for many years, and it often doesn't use the latest capabilities. For example, Dynamics 365 apps natively use artificial intelligence and machine learning to provide insights that help users make informed decisions.

Avoid major deviations from native features or repurposing existing features. These approaches can limit the value of an evergreen platform by compromising flexibility and the ability to evolve with changing business needs. They also increase technical debt and maintenance costs.

### Understand the power of the platform

Another challenge arises when you don't fully know the power of the new solution and opt to extend before understanding the effects of that decision. The platform might already have many ways to provide the same functionality as the legacy solution. You might need some customization of the off-the-shelf solution, but you should find the right balance. You should evaluate, explore, and in some cases pilot each scenario. And it's important to involve key business users in these decisions.

### Use partner solutions

You might save development cost and time, as well as testing and maintenance resources, by using solutions from established software development companies in the app marketplace instead of extending a solution. A software development company typically supports and maintains their solution at scale for multiple organizations. Their experience can be an advantage for organizations that require more functionality that's already provided by software development companies.

When you consider a solution from a software development company, make sure you understand the support model and how it aligns with continuous updates and protection clauses.

## Consider the key characteristics

Every extension should focus on bringing efficiency or value to your organization. You should also consider how extensions can affect the key characteristics of a cloud solution, such as:

- Usability and accessibility
- Security, privacy, and compliance
- Performance
- Scalability
- Impact on application lifecycle management
- Maintainability, supportability, and future-proofing
- Hassle-free updates

### Usability and accessibility

User experience is a key characteristic of a business solution. Providers invest heavily in the user experience to make sure that users' interactions with the solution are pleasant. They also strive to make sure the solution operates seamlessly between devices, such as laptops, tablets, and phones, and business applications like Outlook and Teams.

The purpose of extending off-the-shelf solutions should be to add value to the business. One way to add value is to improve the user experience by considering and adapting to users' requirements and expectations. Extending shouldn't negatively affect the user experience or the solution's responsiveness, performance, or behavior across different devices and platforms.

For instance, an extension that adds a calculated field to display unsettled invoices on a customer master list page in Dynamics 365 Finance might reduce performance if it requires significant database lookups and calculations for each record in the form.

### Security, privacy, and compliance

Security and compliance are important aspects of a solution. Extensions should honor your organization's security and compliance requirements. Access to data, whether controlled by security roles or some other feature, shouldn't be bypassed when customizing or extending the native functionality. Breaking the security model can cause a large negative impact, and security breaches aren't to be taken lightly. Similarly, compliance functionality implemented natively must be inherited in any customizations or extensions. Failing to do so might have consequences for organizations that don't comply with regulations.

Regulation of privacy and data use exists in many different forms across markets. While the terminology often overlaps, privacy and security aren't identical. *Security* is about preventing unauthorized access to any type of data. *Privacy* is about ensuring, by design, proper acquisition, use, storage, and deletion of data defined as private under local, regional, and global regulations.

While security is built into Dynamics 365 apps and highlighted as best practices, developers sometimes overlook privacy requirements when they extend native apps. For example, Dynamics 365 apps can store personal data. In the standard functionality, proper measures are taken to protect it. If extensions access, store, or display this information, the standard mechanisms for protection, de-identification, and masking might not catch improper handling of the data unless the developer specifically adds it to the extension.

### Performance

Cloud solutions provide a high degree of scalability and performance. You shouldn't compromise a solution's performance when you extend it.

The user interface or the business logic is often extended to create, retrieve, update, or delete more data. The changes might affect the user experience, depending on the amount of extended functionality that's added.

Service protection limits also help maintain consistent availability and performance. You should take these limits into account when you extend the solution. This way, you reduce the risk of random or unexpected surges in request volumes that threaten the solution's availability and performance.

Business stakeholders should identify, agree on, and sign off on performance goals and monitor them as part of the testing strategy to identify any deviations. These goals are especially important when the solution is extended, as extensions can highly affect them.

Depending on the environment strategy, your solution might be globally distributed. In these cases, factors like latency, firewalls, network traffic, organization proxies, and routing by Internet Service Providers (ISPs) play important roles in a good user experience. When you extend Dynamics 365 apps, especially through integrations with external systems, minimizing the number of external calls, round trips, and volumes is crucial to make sure the solution meets performance goals.

### Scalability

The scalability of a business solution is a key consideration to determine how you extend it. While the cloud platform includes scalable servers and micro services, other aspects of the platform must be considered to determine the impact of your business solution architecture.

When you extend a feature, you must understand how the functionality applies to different business units, countries, or regions. You must also understand the level of adjustments that each of them requires. If each business unit, country, or region requires its own level of customization, the solution at the extension level isn't scalable by itself and needs further adjustments.

How the business solution scales is hugely influenced by the number of parallel connections, requests, and concurrent users, among other factors. For example, the values of these parameters might change when new business units, countries, or regions are added. It's better to assess the impact of the chosen architecture as use of the solution grows from an agreed-on baseline; for example, when the scope is small or when the solution is first released.

It's important to understand how use grows over time and the impact of the design on parameters like these:

- How much storage do the extensions require, and how does storage grow over time?
- How many more application programming interface (API) calls do the features require?
- What are the limits on workflows, code execution, or API calls?

Let's look at an example of scalability and performance considerations: an extension that automates mass emailing of externally facing documents. It has open-ended criteria for execution. If not properly architected, it could hit the platform's service protection limits both in and outside the app. It might also severely affect performance in the solution.

Always conduct thorough testing, including [performance testing](performing-solution.md), in realistic current peak scenarios, and in realistic future peak scenarios.

### Impact on application lifecycle management

When you extend Dynamics 365 apps, all code and customization must be packaged and shipped from their various environments. Extensions must be included in your organization's application lifecycle management (ALM). Whether created in the user interface or with pro developer tools, extensions and other customizations must be developed, tested, approved, and released into production in accordance with ALM best practices. They should also be added to a repository where they can be backed up, merged, and properly handled.

All extended functionalities are added on top of ALM practices, which increases complexity. As an example, extended features require different configurations or they apply only to specific business units, countries, or regions. In these cases, you must have separation at the ALM process level, such as shipping the extensions in different packages or solutions.

Aspects of the packages that you should consider depend on the number of extended functionalities that were added to the native solution. For example, you might must consider the order in which these functionalities are introduced, how they're split, and how the size affects ALM operations.

Here's another example: In solutions with Dynamics 365 Commerce, an extension to the retail functionality that spans the point of sale front end, the Commerce Scale Unit, and the base Dynamics 365 Finance app can include multiple technologies and require lifecycle management and deployment of multiple separate packages.

### Maintainability, supportability, and future-proofing

In a cloud world where updates are continuous and new features are released frequently, it's important to think about the impact and costs of maintaining extended functionalities.

When you extend Dynamics 365 apps, more maintenance requirements are added to the business solution, so it's important to understand and be aware of deprecations and roadmaps. This awareness helps to avoid building something that Microsoft later offers natively in Dynamics 365. You also avoid having to replace parts of the extended solution when Microsoft deprecates capabilities.

[Keep track of release plans on Microsoft Learn](/dynamics365/release-plans/index).

#### Supportability

Extending a business solution can complicate support requirements. Normally, the first line of support is at the organization itself or a vendor. Support resources must have expertise on the business solution and extensions that are built on top of off-the-shelf capabilities. It requires a specialization of resources to support the extended business solution.

The solution provider is typically the last line of support. It's important to use proper techniques for the extended solution. If you don't comply with these rules, you risk that the warranty or support terms of your contract are void.

Because some apps make it easy to customize them to meet user needs, these customizations can affect the time that's required to maintain them. For example, when a new user is onboarded, the following list shows some aspects that might require more maintenance time:

- The time it takes to onboard
- Determining whether existing security roles and apps can be applied
- Determining if more requirements must be added

As the solution is extended, the importance of having a good testing strategy grows because it's necessary to validate how the solution behaves with each update.

### Hassle-free updates

In a cloud solution, organizations must embrace the change and innovation that comes with frequent new features and capabilities. These capabilities, in turn, add value to the business. When it's necessary to extend functionality, it should always be done in a way that makes it easy and safe for other developers to extend them down the line.

It's good practice to take the following perspectives into account:

- Have sound developer craftsmanship. This principle applies to basically any language or technology. It dictates that when APIs and extension points are created, they're well thought through, robust, and well defined, and that the extension is made in a way that allows other extensions to use the same extension point or API side-by-side.

- Be a "good citizen" in the new solution. By your example, you encourage other developers who might expand your code later to follow the same principles. This example includes writing code that others can easily read, creating APIs and extension points that others can extend without surprises, unexpected results, or side effects, and designing structures and frameworks that allow others to incorporate your effort in a clean and concise way.

- Establish a process that anticipates the future and works to minimize potential negative effects that extending the solution can bring. While it's common for organizations to build custom extensions, deviations from native functionalities can have an impact on the organization's ability to take advantage of future capabilities.

### Document the extension

One of the most common causes of friction around scope or "feature creep" is poor alignment around requirements. Whether the implementation methodology is agile, waterfall, or hybrid, stakeholders must agree on the desired outcome of an extension. They must also determine how the extension addresses the underlying requirement.

[Success by Design](success-by-design.md) recommends documenting the requirement and its resolution in a [functional design document](/training/modules/design-plan-implementation-finance-operations/12-design-doc) (FDD). The form of this type of documentation can vary depending on methodology. But it should be possible for the stakeholders to use the FDD to test that the requirement is valid, whether the proposed solution will fulfill the requirement, and whether the delivered extension was implemented as designed.

### Extensions to other solutions

Extensions on top of solutions from software development companies other than Microsoft generally require the same considerations as when you extend the standard functionality of Microsoft base apps. But if the partner solution itself is an extension of Microsoft code, there might be added complexity now that there are two potential sources of updates&mdash;from Microsoft and from the software development company&mdash;that might break something. While this is more a formality when the partner solution originates from App Source, we recommend that you discuss extensions with the software development company and verify that they intend to follow the update cadence of Dynamics 365.

We recommend that you plan your update processes well in advance, and that you coordinate these activities with each software development company. It requires effort to make sure you can obtain an updated version from your providers with enough time to regression test your full solution.

## Product-specific guidance

This article describes concepts that are product-agnostic and apply to most online deployments. Some concepts are specific to finance and operations apps like Dynamics 365 Finance, Supply Chain Management, and Commerce. [Learn how to extend finance and operations apps](extend-your-solution-guidance-product-fo.md).

Implementations with customer engagement apps bring more capabilities of the Power Platform. [Learn how to extend customer engagement apps](extend-your-solution-guidance-product-ce.md).

You can extend Dynamics 365 Business Central with AppSource apps. [Learn how to extend Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-extensibility-overview).

## Conclusion

Cloud-based solutions offer ready-to-use applications that can be easily delivered, reducing the time that's required for an organization to start taking advantage of them. Solutions that deploy to online environments are scalable and offer native integrations with other online offerings. These solutions benefit from continuous updates that add innovation and new capabilities multiple times per year. Cloud deployment reduces costs and effort and eliminates the downtime that's associated with upgrades in a traditional on-premises model. Organizations can start using the solution as-is.

Still, in some scenarios, more requirements are needed to add value to the business or to empower users and drive adoption of the new solution. Modern cloud solutions provide rich capabilities to further extend them. These capabilities can range from simple customizations using a low-code/no-code approach to an extension that uses custom code created by professional developers.

It's important to consider that the level and depth of these extensions can affect key characteristics like performance, or increase the cost of supporting and maintaining the solution. They shouldn't hinder the ability to take advantage of innovative functionalities that are delivered as part of a continuous update strategy. Normally, when you're deciding to extend a solution, you must make a trade-off between new functionalities and the effect of adding them. For example, adding too much information to a form can increase the time that's required to load it. In this article, we discussed how these key characteristics can be affected and the consequences of overextending the solution.

With [Success by Design](success-by-design.md), the [Solution Blueprint Review workshop](success-by-design.md#success-by-design-reviews) often covers such topics to establish a clear understanding of the impact that extensions have on the solution and how to identify risks and issues that come with these decisions. One of the most important factors to consider when you're deciding to extend a solution is how it might affect performance. During the solution performance implementation workshop, the FastTrack solution architect works with you and your implementation partner to review how the extensions can affect the overall performance of the solution. Together, you identify typical risks and issues related to overextending forms, synchronous events that affect the user experience, and impact on capacity such as service protection limits, resources, and allocation limits.

## Related content

- Check out the [scenarios for extending Dynamics 365](extend-your-solution-scenarios.md) to see how other organizations extended their Dynamics 365 apps to meet their business needs
- Learn more about the specific considerations and best practices for [extending finance and operations apps](extend-your-solution-guidance-product-fo.md), for [extending customer engagement apps](extend-your-solution-guidance-product-ce.md), and for [extending Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-extensibility-overview?toc=/dynamics365/guidance/toc.yml)
- Read the [case study](extend-your-solution-case-study.md) of how a company extended Dynamics 365 to improve its customer service
- Use the Success by Design [checklist](extend-your-solution-checklist.md) to plan and implement your extensions effectively
