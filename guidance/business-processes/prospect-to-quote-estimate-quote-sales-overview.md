---
title: Overview of the estimate and quote sales business process area
description: Learn how you can use Dynamics 365 products to support the organization's business processes for estimating and quoting sales.
ms.date: 11/01/2023
ms.topic: concept-article
author: edupont04
ms.author: kowildfe
---

# Help sales teams maintain profitability with the estimate and quote sales process area

***Applies to: Dynamics 365 Sales, Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Fraud Protection***

This article describes the key steps and considerations for using Dynamics 365 to accurately estimate and quote sales. Effective quoting helps sales teams win more deals and maintain profitability.

Quoting is a pivotal process where a prospect shows interest and engagement. A timely, competitive quote enables sales teams to progress opportunities and turn them into revenue. Dynamics 365 provides end-to-end tools for efficient, data-driven quoting at scale.

Through integration with Dynamics 365 Sales, finance and operations apps provide real-time visibility into inventory availability, costs, and margins during quoting. This visibility empowers sales teams to confidently create profitable quotes.

## Key stakeholders

The following key stakeholders are involved in estimating and quoting sales:

- **Sales reps**: Create and manage quotes in Dynamics 365 Sales.
- **Sales managers**: Oversee the overall quoting process and quote attainment.
- **Account managers**: Work directly with customers and prospects on quote details.
- **Finance**: Validate pricing and margins on quotes (connected to the upstream *Record to Report* process).
- **Operations**: Fulfill quotes and validate inventory/costs (connected to the downstream *Inventory to Deliver* process).

## Estimate and quote sales flow

The following diagram illustrates the key steps in the *estimate and quote sales* business process area.

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/prospect-to-quote-estimate-quote-sales-flow.svg" alt-text="Flow diagram for the estimate and quote sales business process area, which is explained in the paragraph after the image." lightbox="media/prospect-to-quote-estimate-quote-sales-flow.svg":::

The following steps are illustrated in the business process flow diagram.

1. Start
1. *Prospect to quote* end-to-end process
1. *Estimate and quote sales* business process area

    1. *Create sales quotes*

        Sales reps start the process by creating a sales quotation in Dynamics 365 Sales. This process involves the following key activities:

        - Adding products, services, and discounts.
        - Creating or selecting a price list.
        - Entering customer and payment details (integrated with the *Service to Cash* process).

    1. *Manage sales quotes*

        Sales reps and managers evaluate and revise quotes as needed. This process involves the following activities:

        - Closing quotes that are lost or canceled.
        - Creating sales orders from approved quotes (hands off to the *Order to Cash* process).
        - Revising quotes based on customer feedback.

1. End

There is an upstream branch to *create sales quotes* from *record revenue events*. There is an upstream branch to *manage sales quotes* from *retrieve pricing and availability* and *convert quote to order*.

There are also downstream branches to *create and manage sales*, *process inbound goods*, and *create work orders*.

## Benefits

Several benefits can be achieved by using Dynamics 365 to optimize the quoting process:

- Increased deal sizes

    Through upselling and cross-selling additional products and services

- Higher win rates

    By providing fast, competitive quotes that are tailored to prospects

- Faster sales cycle

    By accelerating time-to-close through efficient quoting

- Profitability

    Through real-time visibility into margins by quote and product line

Overall, streamlining the quoting process helps sales teams close more deals faster and maximize revenue.

## Next steps

If you want to implement Dynamics 365 solutions to help with your *estimate and quote sales* business processes, you can use the following resources and steps to learn more.

1. [Define sales strategies](prospect-to-quote-define-sales-strategy-overview.md)

2. [Run marketing campaigns](prospect-to-quote-run-marketing-campaigns-overview.md)

3. [Identify and qualify leads](prospect-to-quote-identify-qualify-leads.md)

4. [Pursue opportunities](prospect-to-quote-pursue-opportunities-overview.md)

5. *Estimate and quote sales* (the article that you're currently reading)

6. [Manage customer relationships](prospect-to-quote-manage-customer-relationships.md)

## Related information

- [Manage quote, order, and invoice](/dynamics365/sales/sales-transactions)
- [Create or edit quotes](/dynamics365/sales/create-edit-quote-sales)
- [Define product pricing with price lists and price list items](/dynamics365/sales/create-price-lists-price-list-items-define-pricing-products) 
- [Product overview Dynamics 365 Sales](https://dynamics.microsoft.com/sales)
- Find definitions of terminology that is used in content for *estimate and quote sales* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article. For example, this glossary includes the following terms:

    - [Quote](glossary.md#quote)
    - [Margins](glossary.md#margins)
    - [Product and price lists](glossary.md#product-and-price-lists)
    - [Discounts](glossary.md#discounts)
    - [Upsell](glossary.md#upsell)
    - [Sales planning and strategy](glossary.md#sales-planning-and-strategy)
    - [Sales process and stages](glossary.md#sales-process-and-stages)

<!-- 
## Tags

*Products:* Dynamics 365 Sales

*Industries:* Agriculture, Manufacturing, Retail, Professional Services, Public Sector

*Roles:* Sales Manager, Sales Rep, Finance Manager, Operations Manage -->

## Contributors

This article was authored by:

- [Kody Wildfeuer]( https://www.linkedin.com/in/kody-wildfeuer/) \| FastTrack Solution Architect
