---
title: TechTalk Advanced export control for Dynamics 365 Supply Chain Management 
description: Find a TechTalk that described the advanced export control capabilities for Dynamics 365 Supply Chain Management.
ms.date: 11/04/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Advanced export control for Dynamics 365 Supply Chain Management

In the fast-evolving landscape of global trade, managing exports is a critical function for companies that deal with regulated products. With advanced export management in Dynamics 365 Supply Chain Management, organizations can now gain deeper control over export compliance, ensuring they adhere to regulations, avoid penalties, and streamline their processes. This article provides an overview of this capability, how it works, and the key functionalities that make it a game-changer for businesses operating in international markets.

We based this article on [a TechTalk](https://youtu.be/OxbyeqDqq9Y) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/scm-advance-export-control-slide.png" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/OxbyeqDqq9Y":::

## Overview of advanced export management

Advanced export management in Dynamics 365 Supply Chain Management was introduced in the 10.0.36 release. It offers a robust framework to manage export control rules and compliance. It builds on the foundation laid by the dual-use goods functionality but introduces significant flexibility and customization options, allowing businesses to tailor their export control management to their specific needs.

The advanced feature set is designed to handle more complex and custom scenarios. It enables businesses to define specific jurisdictions, codes, categories, and restrictions that govern how products are classified and managed during export. This functionality allows companies to apply different rules across legal entities and even control the export of regulated products across varying geopolitical regions.

## Key capabilities and setup

One of the standout features of the advanced export management solution is the ability to define jurisdictions—sets of codes, categories, and restrictions specific to export control regulations. These jurisdictions might include rules such as the U.S. International Traffic in Arms Regulations (ITAR), the U.S. Export Control Administration Regulations (EAR), and the European Union's dual-use goods regulations. Codes and categories, referred to as Export Control Classification Numbers (ECCNs), are assigned to each product. Dynamics 365 provides flexibility in mapping these codes to categories like missile technology or national security.

When an organization sets up export control in Dynamics 365, they can define the restrictions under which export activities are permitted. For example, a company might block the sale of certain products to specific countries or regions unless an appropriate license is obtained. These licenses can then be associated with specific transactions, ensuring that companies comply with both internal and external regulations before completing a sale or shipment.

The advanced export management solution is fully integrated with Dataverse, making it possible to apply the functionality across other apps, not just Dynamics 365 Supply Chain Management. This integration ensures that companies with a diverse software ecosystem can still use this functionality across sales, shipping, and other relevant operations.

## Jurisdictions, codes, and categories

The framework for managing exports starts with defining jurisdictions, which serve as the regulatory bodies or sets of rules that apply to a given set of products or transactions. These jurisdictions govern which codes and categories products fall under. In practice, this means a company can define a set of restrictions for a jurisdiction like Norway, which might include codes for missile technology or dual-use goods.

Restrictions are then put in place to prevent the sale or export of specific items unless certain criteria are met, such as the possession of a valid license or meeting specific exemptions. For instance, if a product falls under military classification in Norway, a user might see a prompt that blocks the sale unless an exemption is granted.

Licenses are critical to the advanced export management capability. They represent special permissions that allow companies to export products that would otherwise be restricted. For instance, a license might allow a company to export a limited number of items classified as missile technology to a specific country or region, provided certain criteria are met.

## PowerFX and custom rules

PowerFX, a feature available in Dataverse, allows businesses to create custom rules and workflows for their export control processes. It enables companies to implement complex rules, similar to Excel formulas, that govern whether a transaction can proceed. For example, a company might create a rule that blocks the sale of electronics to Italy unless the sales order was created before a specific date. This level of customization gives businesses unprecedented flexibility to adapt their export control processes to the dynamic global environment.

By using PowerFX, companies can respond quickly to changes in corporate policies or geopolitical events that can affect their ability to ship specific products. This ensures that export compliance remains agile and adaptable, even as regulations or internal business rules evolve.

## Integration with external systems

A key advantage of the advanced export management capability is how it integrates seamlessly with external systems through Dataverse. This means companies can use the export control functionality with external systems, making it easier to manage compliance across the entire enterprise. Whether it's a non-Microsoft business solution or a specialized logistics platform, companies can tie in export control checks and ensure that all transactions are compliant with applicable regulations.

For example, through a simple OData call, external systems can trigger the same export control validation checks used within Dynamics 365, ensuring consistent application of rules across the board. This is useful for companies with complex supply chains or multiple software environments.

## Conclusion

The advanced export management functionality in Dynamics 365 Supply Chain Management is a significant step forward for companies managing complex, regulated supply chains. It offers robust features for setting up jurisdictions, managing codes and categories, and implementing flexible restrictions and exceptions. The integration with PowerFX and Dataverse makes it a powerful tool for both internal use and external system integration.

Learn more in the [Dynamics 365 Supply Chain Management documentation](/dynamics365/supply-chain/), which provides a comprehensive guide on how to set up and use the advanced export control feature. Additionally, feedback from early users is encouraged to help shape future releases and enhance the functionality further.

With advanced export management, businesses can ensure they remain compliant, avoid costly penalties, and streamline their export processes, even in the face of evolving global regulations.

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [Advanced export control overview](/dynamics365/supply-chain/pim/export-control-overview)
- [Keep track of your trade policies with advanced export control - Microsoft Dynamics 365 Blog](https://cloudblogs.microsoft.com/dynamics365/it/2023/09/01/keep-track-of-your-trade-policies-with-advanced-export-control/?)
- [Dynamics 365 and Power Platform Preview Programs: Product Information Management : All Conversations (yammer.com)](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=158974935040&view=all)
- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
