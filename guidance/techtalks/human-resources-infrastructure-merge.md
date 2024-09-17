---
title: TechTalk Human Resources infrastructure merge
description: Find a TechTalk video that talks about the infrastructure merge of the Human Resources app with the finance and operations platform.
ms.date: 09/12/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Dynamics 365 Human Resources infrastructure merge

In recent years, the integration of Dynamics 365 Human Resources into the broader ecosystem of finance and operation apps was a significant focus for many organizations. The move started in 2022 and aimed to unify the infrastructure so that businesses can streamline operations by merging their human resources systems with existing finance and operations environments. This article explores the key considerations, challenges, and potential benefits of undertaking such a merge, based on insights shared in a recent TechTalk.  

We based this article on [a TechTalk](https://youtu.be/Du5UOeb4I0I?si=vD4B4E7WDod9km-D) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/techtalk-dtv051ext-hr-slide.png" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/Du5UOeb4I0I?si=vD4B4E7WDod9km-D":::

## Understanding the impact of the merged infrastructure

The following image outlines the steps for a merge or migration process. It begins with planning the approach, followed by design, preparation, and customization. Next, the merge is conducted in a testing environment, followed by testing and verification. After analysis and fine-tuning, the final step is merging into production. This sequence provides a clear roadmap for executing a data merge or migration effectively.

:::image type="content" source="media/human-resources-infrastructure-merge-process.svg" alt-text="A process chart with six steps as outlined in the text before the image." lightbox="media/human-resources-infrastructure-merge-process.svg":::

In this context, the merge refers to the process of migrating Dynamics 365 Human Resources from a standalone infrastructure into the shared infrastructure of other finance and operation applications. For organizations with both systems in place, this presents an opportunity to combine them into a single, unified environment. This merge is entirely optional and can be initiated based on the business's needs, allowing companies to control the timeline and execution.

The process of customer migration typically involves an automated lift-and-shift of the customer database from the human resources standalone infrastructure to the finance and operations infrastructure. Post-migration, businesses can choose to merge their human resources and finance systems into one. This decision is driven by business objectives and isn't mandated by Microsoft, offering flexibility in how and when the merge is executed.

Learn more in the Human Resources documentation at [Dynamics 365 Human Resources infrastructure merge](/dynamics365/human-resources/hr-infrastructure-merge).  

### Key benefits of merging systems

Merging human resources with finance and operations systems can simplify application lifecycle management. With a single environment, businesses can manage service updates, deployments, and integrations more efficiently. One significant advantage is the elimination of the need for data integration between HR and finance systems, as all data resides within a single database. A merge not only reduces complexity but also enhances data consistency and integrity across the organization.

For companies that prioritize seamless integration and simplified operations, merging these systems aligns with long-term business objectives. However, the decision to merge should be carefully assessed, considering the specific needs and constraints of the organization.

## Considerations and challenges

While the benefits of merging systems are clear, there are several challenges and considerations that organizations must address before proceeding. Data security is a paramount concern, particularly if there are distinct groups of system administrators who need access to only certain data sets. In such cases, maintaining separate environments might be necessary to ensure that sensitive HR data remains protected.

Financial dimensions, such as charts of accounts and other financial structures, might differ between HR and finance systems. Organizations must decide whether to consolidate these dimensions or maintain separate structures. Additionally, Dataverse integration presents another challenge, as a merged system can only be linked to one Dataverse environment, necessitating the merging of any existing Dataverse setups.

System maintenance also requires careful planning. Different maintenance schedules or requirements between HR and finance systems could complicate the merge. Organizations must assess the risk, effort, and feasibility of conducting the merge, ensuring that it aligns with their operational goals and capabilities.

## Scenarios and recommendations

Several scenarios were discussed in the TechTalk to illustrate common situations organizations might face during the merge process. For example, if a company has two instances of finance and operations, one for HR and another for finance, the decision to merge these depends on the organization's objectives. If maintaining separate environments serves the business better, you might not want to merge.

In another scenario, a company with a strong security protocol might choose to keep HR and finance systems separate to prevent cross-access between data sets. Conversely, if the goal is to have a single environment for all operations, merging the systems could streamline processes and reduce long-term maintenance efforts.

The following image highlights key considerations for merges for each organization. It explains that merging is an organization-specific decision, with the option to maintain two environments or combine them into one. There's no hard deadline for completing a merge, as it isn't mandatory. No other tools are required for merging, and we recommend that you treat the process like an application migration with a complete testing cycle. There are no changes to licensing for Dynamics 365 Human Resources in this context. Check out the latest information at [Licensing](/dynamics365/human-resources/hr-infrastructure-merge#licensing).

:::image type="content" source="media/human-resources-infrastructure-merge-importance.svg" alt-text="A chart with five important things to have in mind as outlined in the text before the image." lightbox="media/human-resources-infrastructure-merge-importance.svg":::

## Conclusion

The decision to merge Dynamics 365 Human Resources with finance and operations systems should be driven by the specific needs and goals of the organization. While the merge offers numerous benefits, such as simplified management and enhanced data integration, it also requires careful consideration of data security, system maintenance, and integration challenges.

Ultimately, the choice to merge is a strategic decision that should be based on a thorough assessment of the organization's objectives and constraints. With no mandated timeline from Microsoft, businesses have the flexibility to plan and execute the merge at their own pace, ensuring that the transition aligns with their operational priorities.

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [Dynamics 365 Human Resources infrastructure merge](/dynamics365/human-resources/hr-infrastructure-merge)  
- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
- [Dynamics 365 Human Resources documentation](/dynamics365/human-resources/)
- [Microsoft Dataverse documentation](/power-apps/maker/data-platform/data-platform-intro)
- [Dynamics 365 Finance documentation](/dynamics365/finance/)
