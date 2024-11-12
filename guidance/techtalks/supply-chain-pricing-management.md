---
title: TechTalk Pricing management in Dynamics 365 Supply Chain Management 
description: Summary of TechTalk video that talks about the unified pricing management module in Dynamics 365 Supply Chain Management.
ms.date: 11/07/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Pricing management in Dynamics 365 Supply Chain Management

Pricing strategies are central to the success of any business, particularly in an era where omnichannel retailing is the new normal. Dynamics 365 Supply Chain Management includes a feature-rich pricing management system designed to handle complex pricing needs, empowering businesses to implement flexible and dynamic pricing models. In this article, we explore how the unified pricing management works in Dynamics 365. The TechTalk and the article cover components such as the pricing structures, discount management, charge application, and rebates.

We based this article on [a TechTalk](https://youtu.be/Pc9nBoHN5m0) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/scm-pricing-slide.svg" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/Pc9nBoHN5m0":::

The following image outlines the main challenges and business value of pricing management in a corporate setting.

:::image type="content" source="media/scm-pricing-challenges-roadmap.svg" alt-text="The image is from a slide that shows the main challenges and business value of pricing management in a corporate setting." lightbox="media/scm-pricing-challenges-roadmap.svg":::

The following list outlines the primary challenges:  

- Pricing silos that lack transparency across channels.  
- Pricing relevancy that emphasizes the need to consider all pricing factors for environments.  
- Pricing complexity that deals with the difficulties in transitioning between B2B and B2C pricing logics.  
- Real-time execution, which is required for an omnichannel customer experience.  

## The shift toward omnichannel pricing

Traditional B2B organizations are increasingly transitioning to omnichannel sales models. This shift allows businesses to sell directly to end customers, granting greater control over pricing and margins. The omnichannel transformation brings a need for significant adjustments to pricing models and rules. Dynamics 365 Supply Chain Management addresses these challenges by offering an omnichannel pricing engine, a central module that allows businesses to manage pricing rules and automate pricing execution across various sales channels.

By converting data from customer orders, product details, and market conditions into pricing attributes, the platform supports a flexible, attribute-based pricing model. This model is designed to manage complex pricing structures and discount rules while maintaining high performance, ensuring that businesses can respond rapidly to market changes.

## Pricing components and structures

In Dynamics 365 Supply Chain Management, pricing is determined by a series of components, including price, margin, discounts, charges, and rebates. Each legal entity can have more than one pricing structure, with the price determination logic set to prioritize multiple sources. For example, Dynamics 365 first looks for pricing agreements. Then the software looks for base prices that are determined by the cost of goods sold, or other predefined values in the system.

The price engine responds to omnichannel needs by quickly calculating prices based on a wide array of attributes. These attributes can include customer segments, product categories, delivery modes, and geographical location. This structure allows for sophisticated pricing strategies that can adapt to diverse business requirements.

## Handling discounts

Managing discounts in an organization often requires flexibility, especially when trying to balance long-term contractual discounts with short-term promotional campaigns. Dynamics 365 enhances existing discount management capabilities by introducing several new [discount types](/dynamics365/supply-chain/unified-pricing-management/upm-discounts), including:

- **Simple discounts** – These discounts can be applied as either a percentage or a flat amount, typically based on specific customer or product attributes.

- **Quantity discounts** – These discounts are based on purchasing thresholds.

- **Free item discounts** – Automatically adding more products to an order at no cost.

- **Mix-and-match discounts** – Discounts applied when purchasing a combination of products.

- **Threshold discounts** – Discounts triggered when customers spend a specific amount.

In addition to standard discounts, Dynamics 365 includes features such as coupon codes and promotional funds so that businesses can tightly control discount usage and costs.

## Charges and fees

Another crucial aspect of pricing management is the application of various charges and fees. Dynamics 365 offers enhanced functionality for applying charges based on product, customer, and order attributes. Charges can be applied both at the order header level and the order line level, which provides a flexibility in how businesses handle other fees. For example, the system can automatically apply expedited delivery charges or any fees that are associated with certain payment methods, such as credit card processing fees, based on predefined pricing rules.

:::image type="content" source="media/scm-pricing-product-attributes.svg" alt-text="The image displays a simple graphical representation showing the product attributes used by the Contoso Entertainment System to determine pricing. It has a large blue triangle with text blocks that describe the three main attributes." lightbox="media/scm-pricing-product-attributes.svg":::

## Rebates management

[Rebate management](/dynamics365/supply-chain/rebate-management/rebate-management-overview) is another essential part of the pricing ecosystem in Dynamics 365. Rebates can be applied based on quantity, value, or a lump sum, and businesses can manage rebates over specific periods. By using pricing attributes, rebate management overcomes many of the limitations found in earlier versions of Dynamics 365. Rebates are calculated and displayed directly within the sales order, allowing businesses to track and account for rebates in real time.

## Integration and extensibility

A key advantage of the pricing management system in Dynamics 365 Supply Chain Management is its integration with external applications through the Commerce Scale Unit. This integration enables external systems to interact with the pricing engine via APIs, allowing for real-time price calculation and retrieval. This capability is useful for businesses that operate across multiple platforms, such as physical stores, eCommerce sites, and mobile apps.

:::image type="content" source="media/scm-pricing-customer-attributes.svg" alt-text="The image illustrates the customer attributes used by Contoso Entertainment System for pricing determination represented by a blue triangle with sections for each attribute type." lightbox="media/scm-pricing-customer-attributes.svg":::

Moreover, the pricing management system supports customization through extension points, enabling businesses to add custom attributes to their pricing models. This flexibility ensures that the pricing engine can adapt to unique business requirements, making it a robust solution for diverse industries.

## Conclusion

The unified pricing management module in Dynamics 365 Supply Chain Management offers a comprehensive solution for handling complex pricing needs in a modern, omnichannel business environment. With its advanced capabilities for managing prices, discounts, charges, and rebates, businesses can easily implement flexible and dynamic pricing strategies that are tailored to their specific needs. By integrating with external applications and offering extensive customization options, Dynamics 365 helps companies remain competitive in an increasingly complex marketplace.

Learn more in the [Dynamics 365 Supply Chain Management documentation](/dynamics365/supply-chain/unified-pricing-management/upm-pricing-management-overview).

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [Unified pricing management module overview](/dynamics365/supply-chain/unified-pricing-management/upm-pricing-management-overview)  
- [Price attributes overview](/dynamics365/supply-chain/unified-pricing-management/upm-price-attributes-overview)  
- [Rebate management overview](/dynamics365/supply-chain/rebate-management/rebate-management-overview)  
- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
