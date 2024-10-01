---
title: TechTalk Author business processes
description: Summary of TechTalk video that talks about how you author content based on the business process catalog for Dynamics 365 implementations.
ms.date: 09/19/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Author business processes with the business process catalog

This article guides you through the process of creating, submitting, and refining the business process articles that are crucial for organizations implementing Dynamics 365 solutions.  

We based this article on [a TechTalk](https://youtu.be/96LNvI0ZrZ8?si=1XPMxMQNTi4O3tE9) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media\DTV030EXT-slide.svg" alt-text="Thumbnail of the presentation slide." link="https://youtu.be/q96LNvI0ZrZ8?si=1XPMxMQNTi4O3tE9":::

## Understanding business processes

[!INCLUDE [daf-business-process-def](~/../shared-content/shared/guidance-includes/daf-business-process-def.md)] While business processes can be technology-agnostic, our business process content maps the business process to Dynamics 365 apps. The business processes are vital in ensuring smooth operations and achieving business goals.

The business process catalog lists more than 800 business processes.

### Who benefits from business process articles?

Business process articles are primarily designed for new consultants or business analysts getting acquainted with Dynamics 365. They're equally valuable for seasoned professionals looking to expand their knowledge into new areas of the system or seeking best practices for implementation.

The following table outlines the target audiences and the purpose of the business process content.

|Targets|Description  |
|---------|---------|
|Target audience | New consultants and business analysts learning about business applications, and existing consultants and business analysts looking for best practices.|
|Target level| Level 300 content with a set of specific tasks in a sequence for achieving the objective. The content includes a definition of when each step is done in the implementation and whether more than one round is required. |
|Purpose |Provides considerations and best practices for implementing. Provides technical information for implementing. Links to product documentation to achieve the tasks. |

These articles, written at a level 300, provide detailed, sequential tasks that guide the user through achieving a business objective. They also offer best practices and considerations for implementing the features supporting the process.

### Business processes versus steps or patterns

It's important to distinguish between a business process and the steps or patterns that make up the process. For example, creating a sales order is a business process, while adding lines to a sales order is a step within that process. Understanding this distinction helps in accurately authoring articles that provide clear guidance.

Let's take some examples of business processes:

- Create a sales order  
- Hire employees  
- Create a purchase order  
- Create a customer  
- Create a vendor  

Business processes involve broader tasks like creating a sales order, hiring employees, or creating a purchase order, customer, or vendor. In contrast, steps or patterns break down these tasks into specific actions. For example, adding lines to a sales order (a step) or creating a sales order with miscellaneous charges (a pattern that combines a decision and a step). Other examples include creating a purchase order line (step) or using product categories to create purchase order lines (pattern). These steps and patterns often represent industry-specific practices.  

The following table maps types of business processes to steps or patterns.

|Business process| Step or pattern  |
|---------|---------|
|Add lines to a sales order| Step  |
|Create a sales order with miscellaneous charges | Pattern or a decision + step  |
|Create a purchase order line | Step  |
|Create purchase order lines by using product categories | Pattern  |
|Create a patient account | Industry-specific pattern|  

## Steps for authoring business process articles

The process of authoring a business process article begins with downloading the business process catalog. After selecting the process you wish to document, check the GitHub issues list to ensure no one else is working on the same article. If not, you can create a new issue request to start the authoring process.

Once approved, you receive a flow diagram, if available, as a starting point. Reviewed, update, and rebrand this diagram according to the guidelines we provide. Then you can download the template, fill in the required sections, and submit the article for review.

### Create the process flow diagram

One of the key elements of a business process article is the process flow diagram. This diagram visually represents the sequence of steps needed to complete the process. It starts with a *Start* box and includes all necessary steps, ending with an *End* box. If there are decision points, represent them with a diamond-shaped decision box that branches out to different paths.

The following image illustrates an example:

:::image type="content" source="media/DTV029EXT-process-flow.svg" alt-text="A process flow diagram explained in text after the image." lightbox="media/DTV029EXT-process-flow.svg":::

The process flow for setting customer credit limits starts with creating a customer, followed by requesting financial statements and other relevant data. It involves gathering credit ratings and payment terms, reviewing these terms, and submitting proposed changes. The flow includes decision points, such as approval of credit limits, and ends with saving the credit details to the customer record. This process involves both manual and automated steps, engaging roles like accounts receivable clerks and managers.

Consistency is crucial in creating these diagrams. Use out-of-the-box security roles for the swim lanes, and ensure all connectors are uniform. After finalizing the diagram, save it as an SVG file and insert it into your Word document, followed by a detailed description of each step.

### Implementation guidance is the heart of the article

The implementation section is perhaps the most critical part of your article. It provides a high-level description of the solution and the specific steps needed to implement it within Dynamics 365. Each step should be clearly linked to product documentation, offering users easy access to detailed instructions.

The steps are organized in a table that includes process stages, process modifiers, and app navigation. Each of these elements plays a vital role in guiding the user through the configuration and operational stages of the business process.

### Accessibility and graphics descriptions

Accessibility is a fundamental aspect of content creation. Follow each image in your article by a thorough description, so that all users, including those using screen readers, can fully understand the content. This description should detail every object and arrow in the graphic, providing a clear and comprehensive understanding of the process flow.

### Final submission

Once your article is complete, the final step is to submit it through the designated customer voice survey. This process includes uploading the Word document, any source graphics, and completing a few other details to finalize the submission.

Learn more at [Business process contributions](/dynamics365/get-started/contribute#business-process-contributions).  

## Conclusion

The process of authoring business processes for the Dynamics 365 business process catalog is a meticulous but rewarding endeavor. By following the guidelines outlined in this session, you can contribute valuable content that aids countless organizations in optimizing their Dynamics 365 implementations. As we move forward, the collective efforts of the community help build a comprehensive resource that benefits everyone involved in the Dynamics ecosystem.

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)  

- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)

- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)

- [Dynamics 365 guidance documentation and other resources](../index.yml)

- [Download Dynamics 365 Business Process Catalog](https://www.microsoft.com/en-us/download/details.aspx?id|105738)

- [Import the business process catalog into Azure DevOps](../business-processes/about-import-catalog-devops.md)

- [Contribute to Microsoft's documentation](/dynamics365/get-started/contribute)

- [Understand concepts in the Dynamics 365 business process guide](../business-processes/about-steps-navigation.md)  
