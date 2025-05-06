---
title: TechTalk - Advanced export control for Dynamics 365 Supply Chain Management 
description: Get a summary of a TechTalk video about the advanced export control capabilities for Dynamics 365 Supply Chain Management.
ms.date: 11/04/2024
ms.topic: concept-article
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Advanced export control for Dynamics 365 Supply Chain Management

In the rapidly evolving landscape of global trade, management of exports is a critical function for companies that deal with regulated products. Through advanced export management in Dynamics 365 Supply Chain Management, organizations can now gain deeper control over export compliance. In this way, they can ensure that they adhere to regulations, avoid penalties, and streamline their processes. This article provides an overview of this capability, how it works, and the key functionalities that make it a game-changer for businesses that operate in international markets.

We based this article on [a TechTalk](https://youtu.be/OxbyeqDqq9Y) that you can find online in the Dynamics 365 channel on YouTube.

:::image type="content" source="media/scm-advance-export-control-slide.png" alt-text="Thumbnail of the title slide for the 'Advanced Export Control for Dynamics 365 Supply Chain Management' presentation." link="https://youtu.be/OxbyeqDqq9Y":::

## Overview of advanced export management

Advanced export management in Dynamics 365 Supply Chain Management was introduced in the 10.0.36 release. It offers a robust framework for managing export control rules and compliance. It builds on the foundation that was laid by dual-use goods functionality by introducing significant flexibility and customization options. Therefore, businesses can tailor the management of export control to their specific needs.

The advanced feature set is designed to handle more complex and custom scenarios. Businesses can define specific jurisdictions, codes, categories, and restrictions that govern how products are classified and managed during export. Companies can apply different rules across legal entities, and can even control the export of regulated products across geopolitical regions.

## Key capabilities and setup

One of the standout features of the advanced export management solution is the ability to define jurisdictions. Jurisdictions are sets of codes, categories, and restrictions that are specific to export control regulations. Examples might include rules such as the U.S. International Traffic in Arms Regulations (ITAR), the U.S. Export Control Administration Regulations (EAR), and the European Union's dual-use goods regulations. Codes that are referred to as Export Control Classification Numbers (ECCNs) are assigned to each product. Dynamics 365 provides flexibility in the way that these codes are mapped to categories such as *Missile technology* or *National security*.

When organizations set up export control in Dynamics 365, they can define the restrictions under which export activities are permitted. For example, companies might block the sale of some products to specific countries or regions unless appropriate licenses are obtained. These licenses can then be associated with specific transactions to ensure that companies comply with both internal and external regulations before they complete a sale or shipment.

Because the advanced export management solution is fully integrated with Dataverse, the functionality can be applied across other apps besides Dynamics 365 Supply Chain Management. This integration ensures that companies that have a diverse software ecosystem can still use the functionality across sales, shipping, and other relevant operations.

## Jurisdictions, codes, and categories

The first step in the framework for managing exports is to define jurisdictions. Jurisdictions represent the regulatory bodies or sets of rules that apply to a given set of products or transactions. They govern which codes and categories products fall under. For example, if a company defines a jurisdiction such as Norway, the codes might include codes for missile technology or dual-use goods.

Restrictions are then put in place to prevent the sale or export of specific items unless precise criteria are met. Those criteria might include possession of a valid license or the granting of specific exemptions. For example, if a product falls under the military classification in Norway, a user might be notified that sales of that product are blocked unless an exemption is granted.

Licenses are critical to the advanced export management capability. They represent special permissions that allow companies to export products that are otherwise restricted. For example, a license might allow a company to export a limited number of items that are classified as missile technology to a specific country or region, provided that precise criteria are met.

## Power Fx and custom rules

Power Fx is a feature that is available in Dataverse. Businesses can use it to create custom rules and workflows for their export control processes. By using Power Fx, companies can implement complex rules that resemble Excel formulas, and that govern whether a transaction can proceed. For example, a company might create a rule that blocks the sale of electronics to Italy unless the sales order was created before a specific date. This level of customization gives businesses unprecedented flexibility to adapt their export control processes to the dynamic global environment.

Power Fx helps companies respond quickly to changes in corporate policies or geopolitical events that might affect their ability to ship specific products. Therefore, export compliance remains agile and adaptable, even as regulations or internal business rules evolve.

## Integration with external systems

A key advantage of the advanced export management capability is that it integrates seamlessly with external systems through Dataverse. The ability to use export control functionality with external systems makes it easier for companies to manage compliance across the entire enterprise. Regardless of whether the external systems are non-Microsoft business solutions or specialized logistics platform, companies can add export control checks and ensure that all transactions comply with applicable regulations.

For example, through a simple Open Data Protocol (OData) call, external systems can trigger the same export control validation checks that are used in Dynamics 365. This capability ensures that rules are consistently applied across the board. Therefore, it's useful for companies that have complex supply chains or multiple software environments.

## Conclusion

The advanced export management functionality in Dynamics 365 Supply Chain Management is a significant step forward for companies that manage complex, regulated supply chains. It offers robust features for setting up jurisdictions, managing codes and categories, and implementing flexible restrictions and exceptions. The integration with Power Fx and Dataverse makes it a powerful tool for both internal use and external system integration.

By using advanced export management, businesses can ensure that they remain compliant, avoid costly penalties, and streamline their export processes, even in the face of evolving global regulations.

Learn more in the [Dynamics 365 Supply Chain Management documentation](/dynamics365/supply-chain/), which provides a comprehensive guide for setting up and using the advanced export control feature. Additionally, we encourage early users to submit feedback to help shape future releases and enhance the functionality.

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [Advanced export control overview](/dynamics365/supply-chain/pim/export-control-overview)
- [Keep track of your trade policies with advanced export control - Microsoft Dynamics 365 Blog](https://cloudblogs.microsoft.com/dynamics365/it/2023/09/01/keep-track-of-your-trade-policies-with-advanced-export-control/?)
- [Dynamics 365 and Power Platform Preview Programs: Product Information Management : All Conversations (yammer.com)](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=158974935040&view=all)
- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
