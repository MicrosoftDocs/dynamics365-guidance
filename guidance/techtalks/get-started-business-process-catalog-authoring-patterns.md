---
title: Author business process patterns and use cases
description: Summary of TechTalk video that talks about how you author business process-related patterns based on the business process catalog for Dynamics 365 implementations.
ms.date: 09/20/2024
ms.topic: concept-article
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Author business process patterns and use cases

In today's rapidly evolving business landscape, it's more important than ever to streamline processes and have clear guidance. The Dynamics 365 business process catalog is an invaluable tool by offering detailed patterns and use cases that help businesses optimize their operations. In this fifth installment of the business process catalog series, we dive into the crucial subject of authoring business process patterns and use cases.

We based this article on [a TechTalk](https://youtu.be/a8-2pUBjuCU?si=uwefzMVMpg7MKPmQ) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media\bpc-patterns-author-slide.svg" alt-text="Thumbnail of the presentation slide." link="https://youtu.be/a8-2pUBjuCU?si=uwefzMVMpg7MKPmQ":::

## What are business process patterns?

Business process patterns are specific use cases or user stories that define how a particular business process is executed. These patterns aren't just templates. They're designed to meet specific objectives by guiding users through a set of tasks that lead to a desired outcome.

The following table outlines the target audiences and the purpose of the business process content.

|Targets|Description  |
|---------|---------|
|Target audience | New consultants and business analysts learning about business applications, and existing consultants and business analysts looking for best practices. Plus business deciding which way to implement a feature.|
|Target level| Level 400 content with a specific way of setting up Dynamics 365 to achieve the objective and a scenario for when to use this pattern. |
|Purpose |Provides considerations and best practices for implementing. Provides technical information for implementing. Links to product documentation to achieve the tasks. |

So far, we identified over 2,000 business process patterns in the catalog. We expect the number to grow as more industry-specific and solution-specific patterns are contributed. For example, the retail, manufacturing, and healthcare industries might have distinct patterns for the same process, reflecting the unique requirements of each sector.

## The authoring process

Authoring a new business process pattern is a structured yet straightforward process. The first step is to ensure that the pattern you want to author doesn't already exist in the catalog. Search through the existing patterns in the business process catalog and, if necessary, submit a request to add a new pattern. Once the pattern is added, you can proceed with authoring the document using the provided templates.

### Use the template

The following image illustrates the Word template for a pattern.

:::image type="content" source="media/dynamics365-template-pattern.png" alt-text="Screenshot of a Word document with text in red, other text highlighted in yellow, and text without formatting." lightbox="media/dynamics365-template-pattern.png":::

When you create a document based on the template, comply with the following rules:

- Name the file according to the business process with no spaces but with dashes between words. Use nouns and verbs, all lower cases.  
- Save in the appropriate end-to-end folder.

> [!IMPORTANT]
> [!INCLUDE [daf-bus-process-word-templates](~/../shared-content/shared/guidance-includes/daf-bus-process-word-templates.md)]

### Assign a name

When you assign a name to a pattern, start with an active verb such as *set up*, *manage*, *create,* or *migrate*. Not only does it help categorizing the pattern, but also it makes it easier for users to identify its purpose quickly. For example, there's a pattern with the name *Convert a sales quotation to a sales order in Supply Chain Management*.

The following table is based on a snapshot of the patterns under the order to cash end-to-end scenario:

| ID | Pattern |
|--|--|
| 65.20.030.250 | Convert a sales quotation to a sales order in Supply Chain Management |
| 65.20.030.275 | Create or import orders from e-commerce |
| 65.20.030.300 | Create orders from sales agreements |
| 65.20.030.325 | Create sales order in a call center |
| 65.20.030.350 | Create sales order lines for configurable products |
| 65.20.030.375 | Create sales orders manually |
| 65.20.030.400 | Create sales orders with broker |
| 65.20.030.425 | Create sales orders with commissions |
| 65.20.030.450 | Create sales orders with royalties |
| 65.20.030.475 | Earn loyalty points on orders |
| 65.20.030.500 | Import sales orders through Electronic Data Interchange (EDI) |

## Structuring a business process pattern

The structure of a business process pattern article includes several key sections:

- **Context and problem**: This section describes the specific use case or scenario that the pattern addresses. It sets the stage for why the pattern is necessary and what problem it solves.

- **When to use this pattern**: This is a critical section that outlines the scenarios in which the pattern is applicable. It helps users understand the specific situations where this pattern is most beneficial.

- **Solution**: This section provides the detailed steps or procedures needed to implement the pattern. While the steps should generally be generic, specific values or configurations that are essential for the pattern should be highlighted.

- **Issues and considerations**: This section addresses any potential challenges or considerations that might arise when implementing the pattern. It might include security requirements, performance considerations, or cost implications.

- **Examples**: Including real-world examples can be incredibly valuable in helping users understand how to apply the pattern in practice. These examples should be relevant and avoid any duplication by showing slight variations in process steps where necessary.

## Contributing and submitting patterns

Once your pattern is fully authored, the next step is to submit it for review and publishing. This involves using the business process catalog's submission process, where your pattern is reviewed, possibly revised, and eventually published for the broader community to use. It's important to ensure that all required fields are filled out accurately and that any examples or other resources are correctly linked.

Moreover, for those contributing patterns that involve ISV (independent software vendor) solutions, it's important to include a link to the AppSource app along with the necessary disclaimers. Differentiating your solution within the context of the pattern is crucial, as multiple contributors  might submit similar patterns with different solutions.

### Why it matters

Business process patterns are essential tools for new consultants, business analysts, and even seasoned professionals looking to expand their expertise. They provide best practices, streamline the implementation of Dynamics 365, and offer clear, actionable guidance. By contributing to this catalog, you're helping to build a robust resource that can benefit a wide range of users across different industries.

If you want to get involved, the process is simple, and the effect is significant. Whether you're submitting an industry-specific pattern or a solution-specific one, your contribution helps enhance the collective knowledge within the Dynamics 365 community.

As we continue to expand the business process catalog, we encourage everyone to participate. We recognize you for your contributions with a badge. Your contribution also plays a vital role in shaping the future of business process management in Dynamics 365.

For more details on how to contribute or to download the latest version of the catalog, visit the business process catalog at [aka.ms/BusinessProcessCatalog](https://aka.ms/BusinessProcessCatalog).

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)

- [TechTalk on the dynamics community website](https://community.dynamics.com/videos/)

- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)

- [Dynamics 365 guidance documentation and other resources](../index.yml)

- [Download the Dynamics 365 business process catalog](https://www.microsoft.com/en-us/download/details.aspx?id=105738)

- [import the business process catalog into Azure DevOps](../business-processes/about-import-catalog-devops.md)

- [contribute to microsoft's documentation](/dynamics365/get-started/contribute)

- [understand concepts in the Dynamics 365 business process guide](../business-processes/about-steps-navigation.md)
