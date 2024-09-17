---
title: TechTalk for copilot capabilities in Dynamics 365 Finance and Supply Chain Management
description: Summary of TechTalk video that talks about new summary features and other uses of Copilot in Dynamics 365 Finance and Supply Chain Management. 
ms.date: 09/06/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk for copilot capabilities in Dynamics 365 Finance and Supply Chain Management

The landscape of business applications is rapidly evolving with generative AI. Microsoft Copilot plays a pivotal role in enhancing the experience for and the productivity of business users. In a Dynamics 365 TechTalk, we unveiled the latest capabilities of Copilot in Dynamics 365 Finance and Supply Chain Management. The presenters showcased how these new features can streamline operations, improve decision-making, and optimize workflow across various business functions.

We based this article on [a TechTalk](https://youtu.be/QQN7tZYr1jc?si=Yz8UPhqgDIXjaDFh) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/copilot-capabilities-dynamics-365-finance-supply-chain-management.svg" alt-text="Thumbnail of the Copilot Capabilities in Dynamics 365 Finance and Supply Chain Management presentation slide." link="https://youtu.be/QQN7tZYr1jc?si=Yz8UPhqgDIXjaDFh":::

## Enhanced decision-making in Supply Chain Management

One of the key highlights of the TechTalk was the introduction of new summarization features in Supply Chain Management, aimed at enhancing decision-making processes. A standout feature now available is the "Confirmed Purchase Orders Workspace." This workspace consolidates all purchase order changes in a single view, categorized into low and high-impact changes, allowing users to swiftly identify and address critical procurement issues. This workspace ensures that decision-makers have a clear, concise summary of order statuses and the ability to communicate with vendors directly from the application.

We also updated warehouse mobile app to include real-time insights into open work tasks. It now offers a comprehensive overview of key performance indicators (KPIs), such as peak work lines and warehouse worker availability. This feature enables warehouse managers to better allocate resources and streamline operations by understanding the workload and its distribution across different zones.

## Context-aware summarization features

The new context-aware summarization capabilities in Dynamics 365 are designed to provide users with relevant information based on their role and the specific context for their work. For example, when a user hovers over a product number in a sales order form, they now see a generated product summary that includes basic information about the product. The summary can include the product's availability across warehouses, and relevant sales data. This feature is particularly useful for sales representatives who need quick access to product information without navigating through multiple screens.

Similarly, the **Release product details** page now includes a Copilot-generated summary at the top with an overview of the product's configuration, inventory levels, purchase information, and sales data. This gives users a holistic view of the product without having to dig into detailed records.

Another innovative feature is the vendor summary, which offers a snapshot of key vendor information, including active contracts, open purchase orders, and potential risks. This feature is particularly valuable for procurement teams, allowing them to make informed decisions quickly by providing essential vendor insights upfront.

## Summarization in Finance with collections and workflow history

In Dynamics 365 Finance, the Copilot capabilities extend to summarizing critical financial information. The **Collections coordinator summary** that became generally available in June 2024 provides a comprehensive overview of a customer's aging amounts, payment history, and credit status. This feature can also generate AI-driven emails for collections, saving time for collections agents by automating routine communications. Learn more at [Collections coordinator summary](/dynamics365/finance/accounts-receivable/collectionscoordinatorsummary).

The **Workflow history summary** is another notable addition, simplifying the often cumbersome task of navigating workflow history. With the most relevant information, such as submission dates and comments, easily available, users quickly understand the status and actions taken in a workflow, without having to scroll through extensive logs. Learn more at [View workflow history](/dynamics365/fin-ops-core/fin-ops/organization-administration/tasks/view-workflow-history?context=%2Fdynamics365%2Fcontext%2Ffinance).  

## Extensibility and security considerations

While these summarization features are powerful, it's important to note that they aren't currently extendable. The summaries are designed by Microsoft and provide a curated view of information based on the user's role and access rights. However, Microsoft acknowledges the desire for more customization and filtering options.

Security remains a top priority for Microsoft, and all AI features, including Copilot, adhere to the company's Responsible AI framework. This ensures that data privacy and security are maintained, and that the AI systems are reliable, inclusive, and fair.

:::image type="content" source="media/microsoft-responsible-ai-principles.svg" alt-text="Screenshot of the six principles for responsible AI that Microsoft applies." lightbox="media/microsoft-responsible-ai-principles.svg":::

Learn more at [Microsoft's responsible AI principles](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).

## General availability and user adoption

The new Copilot capabilities in Finance and Supply Chain Management release directly to general availability and become enabled by default in updates in the second half of 2024. These features use existing transactional data within the system, making their implementation low-risk while offering significant value in terms of efficiency and productivity.

For users and administrators, these features can be managed through feature management settings, allowing them to enable or disable specific summarization capabilities based on their business needs. As these features become more widely adopted, Microsoft anticipates receiving valuable feedback that drives ongoing improvements and refinements.

## Conclusion

The introduction of Copilot capabilities in Finance and Supply Chain Management marks a significant step forward in the integration of AI within business applications. These features not only enhance user experience by providing relevant, context-aware information but also empower businesses to operate more efficiently and make better-informed decisions. As these tools continue to evolve, they're poised to become indispensable assets in the digital transformation journey of enterprises.

Learn more about these capabilities in the official Microsoft documentation and reports on [Microsoft Learn](/dynamics365/fin-ops-core/fin-ops/copilot/copilot-for-finance-operations).

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [What are the Dynamics 365 TechTalk videos?](/dynamics365/guidance/roles/techtalk-videos)

- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)

- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
