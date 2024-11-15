---
title: TechTalk - Pricing management in Dynamics 365 Supply Chain Management 
description: Get a summary of a TechTalk video about the Unified pricing management module in Dynamics 365 Supply Chain Management.
ms.date: 11/14/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Pricing management in Dynamics 365 Supply Chain Management

Pricing strategies are central to the success of any business, especially now that omnichannel retailing is the "new normal." Dynamics 365 Supply Chain Management includes a feature-rich pricing management system that is designed to handle complex pricing needs. Therefore, businesses can implement flexible and dynamic pricing models. This article explores how unified pricing management works in Dynamics 365. The article and the TechTalk that it summarizes cover components such as pricing structures, discount management, charge application, and rebates.

We based this article on [a TechTalk](https://youtu.be/Pc9nBoHN5m0) that you can find online in the Dynamics 365 channel on YouTube.

:::image type="content" source="media/scm-pricing-slide.svg" alt-text="Thumbnail of the title slide for the 'Pricing Management Overview: Dynamics 365 Supply Chain Management' presentation." link="https://youtu.be/Pc9nBoHN5m0":::

The following diagram outlines the business value of pricing management in a corporate setting.

:::image type="content" source="media/scm-pricing-challenges-roadmap.svg" alt-text="Diagram that shows the main challenges and business value of pricing management in a corporate setting." lightbox="media/scm-pricing-challenges-roadmap.svg":::

## The shift toward omnichannel pricing

Traditional B2B organizations are increasingly transitioning to omnichannel sales models. As a result of this move, businesses can sell directly to end customers and gain more control over pricing and margins. The omnichannel transformation requires significant adjustments to pricing models and rules. Dynamics 365 Supply Chain Management addresses these challenges by offering an omnichannel pricing engine. This pricing engine is a central module that businesses can use to manage pricing rules and automate pricing execution across various sales channels.

By converting data from customer orders, product details, and market conditions into pricing attributes, the platform supports a flexible, attribute-based pricing model. This pricing model is designed to manage complex pricing structures and discount rules, but also maintain high performance. In this way, it ensures that businesses can respond rapidly to market changes.

## Pricing components and structures

In Dynamics 365 Supply Chain Management, pricing is determined by a series of components, including prices, margins, discounts, charges, and rebates. These components make up the pricing structure. Each legal entity can have more than one pricing structure, and the price determination logic can be set to prioritize multiple sources. For example, Dynamics 365 first looks for pricing agreements. It then looks for base prices that are determined by the cost of goods sold (COGS) or other predefined values in the system.

The pricing engine responds to omnichannel needs by quickly calculating prices based on a wide range of attributes. Those attributes can include customer segments, product categories, delivery modes, and geographical locations. This structure allows for sophisticated pricing strategies that can adapt to diverse business requirements.

## Discount management

The management of discounts in an organization often requires flexibility, especially when long-term contractual discounts must be balanced with short-term promotional campaigns. Dynamics 365 enhances existing discount management capabilities by introducing several new [discount types](/dynamics365/supply-chain/unified-pricing-management/upm-discounts), including:

- **Simple discounts** – These discounts can be applied as either a percentage or a flat amount, typically based on specific customer or product attributes.
- **Quantity discounts** – These discounts are based on purchasing thresholds.
- **Free item discounts** – More products can automatically be added to an order at no cost.
- **Mix-and-match discounts** – These discounts are applied when customers purchase a combination of products.
- **Threshold discounts** – These discounts are applied when customers spend a specific amount.

In addition to standard discounts, Dynamics 365 includes features such as coupon codes and promotional funds. Therefore, businesses can tightly control discount use and costs.

## Charges and fees

Another crucial aspect of pricing management is the application of various charges and fees. Dynamics 365 offers enhanced functionality for applying charges based on product, customer, and order attributes. Charges can be applied at both the order header level and the order line level. Therefore, businesses have flexibility in the way that they handle other fees. For example, the system can automatically apply expedited delivery charges or fees that are associated with specific payment methods, such as credit card processing fees, based on predefined pricing rules.

:::image type="content" source="media/scm-pricing-product-attributes.svg" alt-text="Diagram that shows the three product attributes that an example company, Contoso Entertainment System, uses to determine pricing: product, product category, and brand." lightbox="media/scm-pricing-product-attributes.svg":::

## Rebate management

[Rebate management](/dynamics365/supply-chain/rebate-management/rebate-management-overview) is another essential part of the pricing ecosystem in Dynamics 365. Rebates can be applied based on the quantity, the value, or a lump sum. Additionally, businesses can manage rebates over specific periods. By using pricing attributes, rebate management overcomes many of the limitations in earlier versions of Dynamics 365. Rebates are calculated and shown directly on the sales order. Therefore, businesses can track and account for rebates in real time.

## Integration and extensibility

A key advantage of the pricing management system in Dynamics 365 Supply Chain Management is its integration with external applications through the Commerce Scale Unit. As a result of this integration, external systems can interact with the pricing engine via APIs. Therefore, real-time price calculation and retrieval can be done. This capability is useful for businesses that operate across multiple platforms, such as physical stores, e-commerce sites, and mobile apps.

Additionally, the pricing management system supports customization through extension points. Therefore, businesses can add custom attributes to their pricing models. This flexibility ensures that the pricing engine can adapt to unique business requirements and makes it a robust solution for diverse industries.

:::image type="content" source="media/scm-pricing-customer-attributes.svg" alt-text="Diagram that shows the four customer attributes that Contoso Entertainment System uses to determine pricing: order customer, customer group, region, and segment." lightbox="media/scm-pricing-customer-attributes.svg":::

## Conclusion

The **Unified pricing management** module in Dynamics 365 Supply Chain Management offers a comprehensive solution for handling complex pricing needs in a modern, omnichannel business environment. By using its advanced capabilities for managing prices, discounts, charges, and rebates, businesses can easily implement flexible and dynamic pricing strategies that are tailored to their specific needs. By integrating with external applications and offering extensive customization options, Dynamics 365 helps companies remain competitive in an increasingly complex marketplace.

Learn more in the [Dynamics 365 Supply Chain Management documentation](/dynamics365/supply-chain/unified-pricing-management/upm-pricing-management-overview).

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [Unified pricing management module overview](/dynamics365/supply-chain/unified-pricing-management/upm-pricing-management-overview)
- [Price attributes overview](/dynamics365/supply-chain/unified-pricing-management/upm-price-attributes-overview)
- [Rebate management overview](/dynamics365/supply-chain/rebate-management/rebate-management-overview)
- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
