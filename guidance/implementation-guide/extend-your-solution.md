---
title: Extend your solution
description: Learn how to extend Dynamics 365 applications to accommodate your organization’s specific processes and requirements and understand the impact of these extensions.
author: abunduc-ms
ms.author: abunduc
ms.date: 08/02/2023
ms.topic: overview
ms.custom: bap-template
---

# Extend your solution

Business solutions offer capabilities that help to drive business value. Still, in some situations, you need to extend a solution, adjusting its off-the-shelf functionality to accommodate your organization's or industry's specific business processes. Dynamics 365 applications offer rich capabilities out of the box&mdash;including powerful options to customize and extend them when needed.

Extending an app's default capabilties shouldn't compromise the fundamental advantages of an evergreen cloud solution, such as usability, accessibility, performance, security, and continuous updates. These advantages are key to success and adoption.

In this article, we discuss how you can extend functionality to accommodate your organization’s specific processes and requirements. We also help you to [understand the impact](#considerations) of extending your solutions and [what to consider](extend-your-solution-scenarios.md) when you [define your extension strategy](#define-your-extension-strategy).

Learn more about how to [extend Dynamics 365 finance and operations apps](extend-your-solution-guidance-product-fo.md) and [extend Dynamics 365 customer engagement apps](extend-your-solution-guidance-product-ce.md).

## Define your extension strategy

There's a trend towards software as a service (SaaS) cloud solutions. Organizations migrate to the cloud to enjoy the many advantages, including:

- Out-of-the-box security  
- Native integrations with other cloud solutions  
- Cost savings  
- Improved agility  

The evergreen cloud approach allows solutions to evolve with the latest modern features. It's also often easier to use off-the-shelf solutions and extend them to meet business needs rather than develop custom solutions from scratch, with all the associated hassles and costs.

### What does "extending" mean?

Even though Dynamics 365 apps cover a wide variety of business processes and industries, often some degree of specialization or customization is needed. We refer to this customization as extending the solution. Extending can vary from minor changes to the user interface of a particular feature to more complex scenarios like adding heavy calculations after certain events. The depth of the extensions has important implications for how much the off-the-shelf product needs to change to meet specific business requirements.

We can categorize extensions into the following distinct types:

- Extending by modifying off-the-shelf functionalities  
- Extending by introducing new functionalities on top of a native one  
- Creating custom solutions on the platform  

### Determine the need

Organizations must be aware of the impact of extending a solution. You want to strike the right balance between the features that empower users and bring business value and efficiency, and the value they offer compared to their costs.

A key driver in the decision to extend is understanding the potential risks to key characteristics of the solution. Think about its robustness, reliability, performance, usability, security, and ability to accept updates. For example, extending an invoicing system could pose risks to operations or disrupt the business because of increased complexity. Such risks are best avoided.

When an organization decides to extend a solution, it may depend on a third party to maintain and evolve it. An unresponsive third party can block the organization from adopting new functionalities.

A common scenario is [extending to integrate with other solutions](integrate-other-solutions.md).

### Don't replicate your legacy solution

When you gather solution requirements, you may be tempted to reproduce every piece of functionality from your legacy solution or even try to mimic the user experience. You may view this as a way to reduce user resistance and drive adoption. But it can also lead to a highly customized solution that fails to apply the strengths of the new platform in favor of familiarity.

Legacy solutions may have taken years to develop and evolve and usually don't use the latest functionality available. As an example, Dynamics 365 apps natively use artificial intelligence and machine learning to provide insights that help users to make informed decisions.

Avoid major deviations from native features or repurposing existing features. These approaches can limit the value of an evergreen platform by compromising flexibility and the ability to evolve with changing business needs. They also increase technical debt and maintenance costs.

### Understand the power of the platform

Another challenge arises when an organization doesn't fully know the power of the new solution and opts to extend before understanding the impact of that decision. The platform may already have many ways to provide the same functionality as the legacy solution. Reasonable customization of the off-the-shelf solution might be required, but the point is to find the right balance. You should evaluate, explore, and in some cases pilot each scenario. And it's important to involve key business users in these decisions.

### Use ISV solutions

You may save development cost and time, as well as testing and maintenance resources, by using independent software vendor (ISV) solutions from the app marketplace instead of extending a solution. ISVs typically support and maintain their solutions at scale for multiple organizations. Their experience can be an advantage for organizations that require more functionality that's already provided by ISVs.

When you consider whether to use ISV solutions, you should be aware of the ISV support model and its alignment with continuous updates and protection clauses.

## Considerations

Every piece of an extension should focus on bringing efficiency or value to your organization. Take inherent costs of building, testing, maintaining, and supporting the extended solution into consideration along with the impacts extensions can have on a solution.

### Usability and accessibility

User experience is a key characteristic of a business solution. Providers invest heavily in the user experience to make sure that users' interactions with the solution are pleasant. They also strive to make sure the solution operates seamlessly between devices, such as laptops, tablets, and phones, and business applications like Outlook and Teams.

Recall that the purpose of extending off-the-shelf solutions should be to add value to the business. One way to add value is to improve the user experience, by considering and adapting to users' requirements and expectations.

While improving the user experience may not be the primary driver, extending shouldn't negatively impact the user experience or the solution's responsiveness and performance and how it behaves across different devices and platforms.

For instance, an extension adds a calculated field that displays unsettled invoices on a customer master list page in Dynamics 365 Finance. This field might reduce performance if it must be calculated through a significant set of database lookups and calculations for each record in the form.

### Security, privacy, and compliance

Security and compliance are important aspects of a solution. It's crucial that extensions honor your organization's security and compliance requirements. Access to data, whether controlled by security roles or some other feature, shouldn't be bypassed when customizing or extending the native functionality. Breaking the security model can cause a large negative impact, and security breaches aren't to be taken lightly. Similarly, compliance functionality that's implemented natively needs to be inherited in any customizations or extensions. Failing to do so may have consequences for organizations that don't comply with regulations.

Regulation of privacy and data use exists in many different forms across markets. While the terminology often overlaps, privacy and security aren't identical. *Security* is about preventing unauthorized access to any type of data. *Privacy* is about ensuring, by design, proper acquisition, use, storage, and deletion, that data defined as private under local, regional, and global regulations is handled appropriately.

While security is built into Dynamics 365 apps and highlighted as best practices, developers sometimes overlook privacy requirements when they extend native apps. For example, Dynamics 365 apps can store personal data. In the standard functionality, proper measures are taken to protect it. If extensions are built to access, store, or display this information, the standard mechanisms for protection, deidentification, and masking might not catch improper handling of the data unless the developer specifically adds it to the extension.

### Performance

Cloud solutions provide a high degree of scalability and performance. It's important not to compromise a solution's performance when you extend it.

The user interface or the business logic is often extended to create, retrieve, update, or delete more data. The changes may have an impact on the user experience, depending on the amount of extended functionality that's added.

Service protection limits also help to maintain consistent availability and performance. Take these limits into consideration when you extend the solution. When you do, you reduce the risk of random or unexpected surges in request volumes that threaten the solution's availability and performance.

Business stakeholders should identify, agree on, and sign off on performance goals and monitor them as part of the testing strategy to identify any deviations. These goals are especially important when the solution is extended, as extensions can highly affect them.

Depending on the environment strategy, an organization might have globally distributed solutions. In these cases, factors like latency, firewalls, network traffic, organization proxies, and routing by Internet Service Providers (ISPs) play important roles in a good user experience. When you extend Dynamics 365 apps, especially through integrations with external systems, minimizing the number of external calls, round trips, and volumes is crucial to make sure the solution meets performance goals.

### Scalability

The scalability of a business solution is a key consideration to determine how you extend it. While the cloud platform includes scalable servers and micro services, other aspects of the platform need to be considered to determine the impact of your business solution architecture.

When you extend a feature, you must understand how the functionality applies to different business units, countries, or regions, and what level of adjustments is needed for each of them. If each business unit, country, or region requires its own level of customization, the solution at the extension level isn't scalable by itself and needs further adjustments.

How the business solution scales is hugely influenced by the number of parallel connections, requests, and concurrent users, among other factors. For example, the values of these parameters might change when new business units, countries, or regions are added. It's better to assess the impact of the chosen architecture as use of the solution grows from an agreed-on baseline; for example, when the scope is small or when the solution is first released.<!-- EDITOR'S NOTE: Here's another instance where I'm trying to clarify a sentence that I couldn't parse. As before, if I got it wrong, please rewrite to make the meaning clear. -->

It's important to understand how use grows over time and the impact of the design on parameters like these:

- How much storage do the extensions require, and how does storage grow over time?
- How many more application programming interface (API) calls do the features require?
- What are the limits on workflows, code execution, or API calls?

Let's look at an example of scalability and performance considerations: an extension that automates mass emailing of externally facing documents. It has open-ended criteria for execution. If not properly architected, it could hit the platform's service protection limits both in and outside the app. It might also severely affect performance in the solution.

Always conduct thorough testing, including [performance testing](performing-solution.md), in realistic current peak and realistic future peak scenarios.

### Impact on application lifecycle management

When you extend Dynamics 365 apps, all code and customization must be packaged and shipped from their various environments. Extensions must be included in your organization's application lifecycle management (ALM). Whether created in the user interface or with pro dev tools, extensions and other customizations must be developed, tested, approved, and released into production in accordance with ALM best practices. They should also be added to a repository where they can be backed up, merged, and properly handled.

All extended functionalities are added on top of ALM practices, which increases complexity. As an example, extended features require different configurations or they apply only to specific business units, countries, or regions. In these cases, you must have separation at the ALM process, such as shipping the extensions in different packages or solutions.

Aspects of the packages that you should consider depend on the number of extended functionalities that were added to the native solution. For example, you might need to consider the order in which these functionalities are introduced, how they're split, and how the size affects ALM operations.

Here's another example: In Dynamics 365 Commerce apps, an extension to the retail functionality that spans the point of sale front-end, the Commerce Scale Unit, and the base Dynamics 365 Finance app, can include multiple technologies and require lifecycle management and deployment of multiple separate packages.

### Maintainability, supportability, and future-proofing

In a cloud world where updates are continuous and new features are released frequently, it's important to think about the impact and costs of maintaining extended functionalities.

When you extend Dynamics 365 apps, more maintenance requirements are added to the business solution, so it's important to understand and be aware of deprecations and roadmaps. This awareness helps to avoid building something that Microsoft later offers natively in Dynamics 365. You also avoid having to replace parts of the extended solution when Microsoft deprecates capabilities.

[Keep track of release plans on Microsoft Learn](/dynamics365/release-plans/index).

#### Supportability

Extending a business solution can complicate support requirements. Normally, the first line of support is at the organization itself or a vendor. Support resources must have expertise on the business solution and extensions built on top of off-the-shelf capabilities. It requires a specialization of resources to support the extended business solution.

The solution provider is typically the last line of support. It's important to use proper techniques for the extended solution. If you don't comply with these rules, you risk that the warranty or support terms of your contract are void.

Because some apps provide the ability to customize them to meet user needs, these customizations can affect the time that's required to maintain them. For example, when a new user is onboarded, the following list shows some aspects that might require more maintenance time:

- The time it takes to onboard  
- Determining whether existing security roles and apps can be applied  
- Determining if more requirements must be added  

As the solution is extended, the importance of having a good testing strategy grows because it's necessary to validate how the solution behaves with each update.

### Hassle-free updates

In a cloud solution, organizations must embrace the change and innovation that comes with frequent new features and capabilities. These capabilities, in turn, add value to the business. When it's necessary to extend functionality, it should always be done in a way that makes it easy and safe for other developers to extend them down the line.

It's good practice to take the following perspectives into account:

- Have sound developer craftsmanship. This principle applies to basically any language or technology. It dictates that when APIs and extension points are created, they're well thought through, robust, and well defined, and that the extension is made in a way that allows other extensions to use the same extension point or API side-by-side.

- Be a "good citizen" in the new solution. By your example, you encourage other developers who may expand your code later to follow the same principles. This example includes writing code that others can easily read, creating APIs and extension points that others can extend without surprises, unexpected results, or side effects, and designing structures and frameworks that enable others to incorporate your effort in a clean and concise way.

- Establish a process that anticipates the future and works to minimize potential negative effects that extending the solution can bring. While it's common for organizations to build custom extensions, deviations from native functionalities can have an impact on the organization's ability to take advantage of future capabilities.

### Document the extension

One of the most common causes of friction around scope or "feature creep" is poor alignment around requirements. Whether the implementation methodology is agile, waterfall, or hybrid, stakeholders must agree on the desired outcome of an extension. They must also determine how the extension addresses the underlying requirement.

[Success by Design](success-by-design.md) recommends documenting the requirement and its resolution in a [functional design document](/training/modules/design-plan-implementation-finance-operations/12-design-doc) (FDD). The form of this type of documentation can vary depending on methodology. But it should be possible for the stakeholders to use the FDD to test that the requirement is valid, whether the proposed solution will fulfill the requirement, and whether the delivered extension was implemented as designed.

### Extensions to ISV solutions

Extensions on top of ISV solutions generally require the same considerations as when you extend the standard functionality of Microsoft base apps. But if the ISV solution itself is an extension of Microsoft code, there may be added complexity now that there are two potential sources of updates&mdash;from Microsoft and from the ISV&mdash;that may break something. While this is more a formality when the ISV solution originates from app source, we recommend that you discuss extensions with the ISV and verify that they intend to follow the update cadence of Dynamics 365.

We recommend that you plan your update processes well in advance, and that you coordinate these activities with each ISV. It requires effort to make sure you can obtain an updated version from your ISVs with enough time to regression test your full solution.

## Product-specific guidance

Throughout this article, we have discussed concepts that are product-agnostic and apply to most online deployments. A series of concepts are specific to finance and operations apps like Dynamics 365 Finance, Supply Chain Management, and Commerce. [Learn how to extend finance and operations apps](extend-your-solution-guidance-product-fo.md).

Implementations with customer engagement apps bring more capabilities of the Power Platform. [Learn how to extend customer engagement apps](extend-your-solution-guidance-product-ce.md).

## Conclusion

Cloud-based solutions offer ready-to-use applications that can be easily delivered, reducing the time that's required for an organization to start taking advantage of them. Solutions that deploy to online environments are scalable and offer native integrations with other online offerings. These solutions benefit from continuous updates that add innovation and new capabilities multiple times per year. Cloud deployment reduces costs and effort and eliminates the downtime associated with upgrades in a traditional on-premises model. Organizations can start using the solution as-is.

Still, in some scenarios, more requirements are needed to add value to the business or to empower users and drive adoption of the new solution. Modern cloud solutions provide rich capabilities to further extend them. These capabilities can range from simple customizations using a low-code/no-code approach or an extension that uses custom code created by professional developers.

It's important to consider that the level and depth of these extensions can affect key characteristics like performance, or increase the cost of supporting and maintaining the solution. They shouldn't hinder the ability to take advantage of innovative functionalities that are delivered as part of a continuous update strategy. Normally, when deciding to extend a solution, a trade-off is necessary between new functionalities and the affect of adding them. For example, adding too much information to a form can increase the time that's required to load it. In this article, we discussed how these key characteristics can be affected and the consequences of overextending the solution.

With [Success by Design](success-by-design.md), the [Solution Blueprint Review workshop](success-by-design.md#success-by-design-reviews) often covers such topics to establish a clear understanding of the impact that extensions have on the solution and how to identify risks and issues that come with these decisions. One of the most important factors to consider when deciding to extend a solution is how performance is affected. During the solution performance implementation workshop, the FastTrack solution architect works with you and your implementation partner to review how the extensions can affect the overall performance of the solution. Together, you identify typical risks and issues related to overextending forms, synchronous events that affect the user experience, and impact on capacity such as service protection limits, resources, and allocation limits.

## Next steps

- Find product-specific guidance at [Extending finance and operations apps](extend-your-solution-guidance-product-fo.md) and [Extend customer engagement apps](extend-your-solution-guidance-product-ce.md)
- Find examples at [Scenarios for extending Dynamics 365](extend-your-solution-scenarios.md)
- View the case study at [Extension case study](extend-your-solution-case-study.md)
- Find the checklist at [Extension checklist](extend-your-solution-checklist.md)
