---
title: Integrate your Dynamics 365 apps with other solutions
description: Find guidance on how to integrate your Dynamics 365 apps with other solutions, including cross-app integration through Dataverse. Find a platform, design, and patterns.
author: abunduc-ms
ms.author: abunduc
ms.date: 05/25/2023
ms.topic: conceptual
---

# Integrate your Dynamics 365 apps with other solutions

Dynamics 365 apps provide a rich and mature feature set across a wide variety of industries. However, you might want to extend processes or incorporate data assets from other sources. In this article, we examine how to integrate Dynamics 365 apps with other solutions, or with each other. In the related articles, we guide you through selecting a platform, design, and pattern, and discuss the challenges you might face during integration. We also provide product-specific guidance for integration with and between the Dynamics 365 apps.  

We discuss the importance of keeping business goals at the forefront while aligning integration projects with your organization's overall solution strategy.

In line with the design pillars, we look at how the choice of integration platform should fit into the architectural landscape.

We also look at how to choose an integration design that offers users the capabilities they desire in the short and long term.

We discuss integration patterns available with Dynamics 365 apps and consider important characteristics and factors.

And finally, before diving into the product specifics, we walk through some of the common challenges people face when integrating systems.

## Objectives

- Learn how to define your business goals around cross-system processes.

- Read about how to choose a platform, design, and pattern.

- Identify challenges you might face during integration.

- Receive product-specific guidance based on use in integration.

## Define business goals

Match each requirement of cross-system processes against the overall goals of the project and the business. It helps you make sure that your integration work aligns with the overall direction of the business. Begin your integration work by defining goals that map to the business perspective.

Learn what to consider when evaluating and matching your integration strategy with your business goals at [Define business goals for your integration strategy](integrate-other-solutions-business-goals.md).  

## Choose a platform

Data storage needs have increased exponentially in recent years, and it continues to intensify in this direction. The amount of data that's generated and transferred today is practically unimaginable. In addition to the new data that's being captured or generated, historical data from legacy systems might need to be preserved. The platform you choose must incorporate all of these realities and must be able to reliably handle the storage and transfer of vast amounts of data.

[Choose a platform](integrate-other-solutions-choose-platform.md) dives into the criteria of choosing the integration platform.

## Choose a design

Many factors influence the choice of patterns for your integration. Integration scenarios can be grouped roughly into three types:  

- Look and feel  
- Data  
- Process integration  

The three types do overlap, but there are also some distinct characteristics and expected behaviors. Learn more at [Choosing a design](integrate-other-solutions-choose-design.md).  

## Choose a pattern

Choosing the right pattern is a critical part of successfully implementing integration between systems. When you choose an integration pattern, consider factors such as the following list:  

- What is its main functionality?  
- How is it built?  
- What is the platform, language, user interface, and the connectivity type?  

We recommend that you also consider what type of actions you need the integration to perform. Learn more at [Choosing a pattern](integrate-other-solutions-choose-pattern.md).  

## Challenges in integration

The diverse applications used in organizations make up the IT backbone of those companies. Organizations use applications that might be a combination of on-premises, cloud, and third parties. These applications need to communicate with each other for different business needs. Integration challenges during a project implementation can cause delays or cost increases. A key focus of any IT department is to ensure that these integrations enable business productivity and not become a blocker to business growth.

Explore [Challenges in integration](integrate-other-solutions-challenges.md) for the areas that need to be considered for the integration strategy to be successful.

## Product-specific guidance

Learn about the aspects that are specific to the individual Dynamics 365 apps at[Product-specific guidance](integrate-other-solutions-guidance-product.md).  

## Conclusion

Implementing Dynamics 365 apps is often a building block into an organization's larger solution landscape. In that case, the organization can benefit from automation to gain streamlined and effective cross-system processes and avoid manual errors.

Integration is also key in closing the digital feedback loop. Integration can make all the organization's data available, not just for reporting and visibility but also to make it accessible to users in the organization. With Azure, Power Platform, and Dataverse, you're well on your cross-system journey. Reporting, analytics, and AI-assisted forecasts and predictive analysis make the right information available for the right people at the right time.  

With Microsoft cloud technology and Power Platform, low-code/no-code options, and the citizen developer concept, that journey can start without requiring massive investments upfront.

In this article, we highlighted the work that should be done when integrating systems and processes, toward a successful solution. We introduced integration patterns and discussed common challenges that could unnecessarily prolong the start of the journey if not addressed properly.

Finally, we referenced some of the technologies that people are using across the globe to successfully integrate their Dynamics 365 apps into the solution landscape.

## Quick links

- Access the case study > [Public sector infrastructure organization learns how to choose the right solution for integration](integrate-other-solutions-case-study.md)

- Access the checklist > [Integrate with other solutions Success by Design checklist](integrate-other-solutions-checklist.md)

- Access the chapter in the book > [Integrate with other solutions](https://aka.ms/d365-chapter-integrate-with-other-solutions)

- Access the implementation guide > [Implementation guide](https://aka.ms/D365ImplementationGuide)

- [REST vs CRUD: Explaining REST & CRUD Operations](/dynamics365/supply-chain/sales-marketing/prospect-to-cash)

- [Messaging Integration Patterns](/dynamics365/fin-ops-core/dev-itpro/analytics/embed-power-bi-workspaces)

- [Open Data Protocol (OData)](/dynamics365/fin-ops-core/dev-itpro/data-entities/odata)

- [Consume external web services](/dynamics365/finance/general-ledger/electronic-messaging)

- [Custom service development](/dynamics365/fin-ops-core/dev-itpro/office-integration/office-integration)

- [Data management package REST API](https://www.enterpriseintegrationpatterns.com/patterns/messaging/index.html)

- [Recurring integrations](https://azure.microsoft.com/product-categories/integration/)

- [Electronic messaging](/dynamics365/fin-ops-core/dev-itpro/data-entities/custom-services)

- [Office integration overview](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-management-api)

- [Business events overview](https://azure.microsoft.com/services/logic-apps/)

- [Embed canvas apps from Power Apps](/dynamics365/fin-ops-core/fin-ops/get-started/embed-power-apps)

- [Analytical Workspaces (using Power BI Embedded)](/powerapps/developer/data-platform/virtual-entities/get-started-ve?toc=/dynamics365/commerce/toc.json)

## Next steps

- [Define business goals](integrate-other-solutions-business-goals.md)  
- [Choose a platform](integrate-other-solutions-choose-platform.md)  
- [Choose a design](integrate-other-solutions-choose-design.md)  
- [Choose a pattern](integrate-other-solutions-choose-pattern.md)  
- [Challenges](integrate-other-solutions-challenges.md)  
- [Product-specific guidance for integration scenarios](integrate-other-solutions-guidance-product.md)  
- [Checklist](integrate-other-solutions-checklist.md)  
- [Case study](integrate-other-solutions-case-study.md)  
