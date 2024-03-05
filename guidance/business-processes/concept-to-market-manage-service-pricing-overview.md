---
title: Manage service pricing overview
description: Learn about the manage service pricing business process, including learning about the various stakeholders and business process flow.
author: rachel-profitt
ms.author: raprofit
ms.topic: conceptual
ms.date: 02/28/2024
---

# Manage service pricing overview

***Applies to: Dynamics 365 Business Central, Dynamics 365 Commerce, Dynamics 365 Customer Insights, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management***

This article describes how service-based organizations can use Dynamics 365 to manage the prices and discounts that are offered to customers for the services you sell, and how organizations that purchase services from a service provider can manage the pricing and contracts with those service providers.

Managing service pricing is a crucial aspect of organizational success, playing a pivotal role in ensuring profitability and maintaining a competitive edge. In the realm of Dynamics 365, the interconnected suite of products, including Dynamics 365 Sales, Field Service, Project Operations, and Supply Chain Management, provides a comprehensive framework for optimizing service pricing strategies. These tools synergistically contribute to the holistic management of service pricing, addressing various facets of the business processes involved.

The process of managing service pricing encompasses a series of essential business processes. Firstly, organizations need to meticulously determine service prices and eligibility for discounts, tailoring their offerings to market demands and competitive landscapes. Simultaneously, the creation and maintenance of service fees become paramount, requiring a fine-tuned approach to align pricing structures with value propositions.

Service pricing agreements further solidify the foundation, fostering transparent and mutually beneficial relationships between service providers and clients. In addition, the dynamic market demands necessitate the agile creation and maintenance of service promotional pricing and discounts, ensuring adaptability to changing landscapes.

Regular reviews of service pricing and discount agreements become a cornerstone in the lifecycle of the services you offer and purchase, allowing organizations to refine their strategies and stay ahead in the ever-evolving business landscape. This holistic approach to service pricing within Dynamics 365 not only streamlines processes but also empowers organizations to navigate the complexities of the market with agility and foresight.

In a service-based organization, where you'll be using any of the downstream processes in the Dynamics 365 implementation such as procure to pay, prospect to quote, order to cash, plan to produce, project to profit, case to resolution, service to cash, and/or record to report, it's essential to ensure that the business processes related to managing the pricing of those services are considered early in the project.

The data and output of these business processes affect many other downstream processes and ensuring these are defined early in the project ensures project success. If Dynamics 365 won't be used to master the service data, integrations to the system of record should be considered early.

## Stakeholders

Many people across the organization should contribute to the decision-making process and design of the *manage service pricing* business process area. The following list provides examples of such stakeholders:

- **Pricing strategy stakeholders** include pricing strategists, or market analysts. These roles are responsible for defining and implementing the overall pricing strategy aligned with organizational goals and can help provide insights into market trends and competitor pricing, aiding in the formulation of competitive pricing strategies.

- **Sales and service stakeholders** include contract managers, sales managers, and customer relationship managers. These stakeholders provide contribute insights into customer preferences, helping tailor promotional pricing to boost sales. Additionally, they help to provide feedback based on customer interactions, contributing to the continuous improvement of pricing strategies.

- **Marketing stakeholders** include product managers and marketing specialists. Product managers help collaborate on determining the value proposition of services and how fees reflect the perceived value. While marketing specialists contribute by collaborating on creating promotional pricing and discount strategies to enhance market presence.

- **Finance team stakeholders** include financial analysts, CFOs, and budget analysts. Financial analysts typically help analyze service pricing and discount structures to assess their impact on profit margins and overall financial health. While financial leadership such as the CFO, VP of Finance, or Controller provides strategic financial guidance, ensuring alignment between service pricing strategies and organizational financial goals. And the budget analysts typically collaborate with other stakeholders to establish budgets aligned with the proposed service pricing strategies.

- **Legal and audit stakeholders** include general counsels, internal auditors, or external auditors. These roles help provide legal expertise and insights into regulatory requirements to help ensure service agreements align with regulatory requirements and industry standards.

## Manage service pricing process flow

The following diagram illustrates the *Manage service pricing* business process area.

:::image type="content" source="media\concept-to-market-manage-service-pricing-overview.svg" alt-text="Diagram of the Manage service pricing business process flow, showing the connection between various business process areas." lightbox= "media\concept-to-market-manage-service-pricing-overview.svg":::

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

1. Start

2. *Concept to market*

3. *Introduce new services*

4. *Manage service pricing*

5. *Determine service price and discount eligibility*

6. *Create and maintain services fees*

  A parallel branch connects to *Manage service lifecycle*, which is under *Concept to market*

7. *Create and maintain service pricing agreements*

  Parallel branches connect to *Manage vendor relationships*, which is under *Procure to pay* and *Manage customer relationships*, which is under *Prospect to quote*

8. *Create and maintain service promotional pricing and discounts*

9. *Review services pricing and discount agreements*

10. *Run marketing campaigns*

11. End

*Manage service lifecycle*, *Manage vendor relationships*, and *Manage customer relationships* have parallel connections to End.

## Manage service pricing benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the *manage service pricing* business processes. The following sections outline the key benefits that an organization might monitor and measure for *managing service pricing* processes.

### Enhanced pricing accuracy and efficiency

Dynamics 365 Sales, Customer Service, and Field Service facilitate precise service pricing through its product catalog that allows users to quickly and easily define pricing. When you use Dynamics 365 Supply Chain Management robust features are included, that help to ensure organizations achieve greater accuracy and efficiency in their pricing strategies. The platform's automated pricing engines ensure the correct price is used on transactions and analytics enable real-time market analysis. This not only minimizes the risk of pricing errors but also streamlines the entire pricing process.

Organizations can measure the benefit of enhanced pricing accuracy through key performance indicators (KPIs) such as reduced pricing discrepancies, improved quotation turnaround times, and increased customer satisfaction. When you use more than one Dynamics 365 product, you can quickly and easily synchronize the pricing data using Dual Write or Virtual entities depending on your organizational business requirements.

### Agile response to market changes

One of the primary benefits of utilizing Dynamics 365 for managing service pricing is the agility it provides in responding to dynamic market changes. You can easily integrate Dynamics 365 with external tools and feed the data into Azure Data Lake using Azure Synapse Link and then gleam the platform's data-driven insights and predictive analytics with Power BI and Machine Learning, which can allow organizations to adapt their pricing strategies swiftly.

KPIs such as time-to-market for adjusted pricing and the frequency of pricing updates can be used to measure the effectiveness of this benefit. By staying ahead of market trends, organizations can maintain competitiveness and capitalize on emerging opportunities.

### Transparent and compliant service agreements

Dynamics 365 helps to ensure transparent and compliant service agreements, a critical benefit for organizations navigating complex regulatory landscapes. The platform's centralized contract management system allows for the creation and maintenance of service agreements with visibility into terms, conditions, and compliance requirements. Basic service agreements can be used across applications such as Dynamics 365 Field Services and Customer Service and when needed the agreements can be synchronized to Dynamics 365 Supply Chain Management or Project Operations. With these applications you can get the added benefit of ensuring revenue recognition and subscriptions are managed accurately and swiftly.

KPIs such as contract compliance rates and audit success can be monitored to gauge the effectiveness of this benefit. Transparent and compliant service agreements foster trust with clients and mitigate legal risks, contributing to long-term success.

### Optimal promotional pricing strategies

When you use Dynamics 365 Supply Chain Management or Commerce a powerful pricing and discounting engine empowers organizations to implement optimal promotional pricing strategies, enhancing their market presence and driving sales. The platform's ability to integrate with Dynamics 365 Customer Insights Data and Journeys data enables targeted promotional pricing, aligning discounts with customer behavior and preferences. When you use other applications such as Sales, Field Service or Customer Service, the pricing and discounting can be easily mastered in Dynamics 365 Supply Chain Management and used in any of the downstream processes to ensure accurate transactions.

KPIs such as the impact on sales revenue, customer acquisition rates during promotions, and the ROI of promotional campaigns can be measured to assess the success of this benefit. By fine-tuning promotional pricing, organizations can maximize the impact of marketing efforts and achieve a competitive edge.

### Continuous improvement through analytics

When Dynamics 365 is combined with the robust analytics capabilities of Power BI and Azure Data Lakes with Azure Synapse Link organizations are enabled to have continuous improvement in service pricing strategies. Organizations can leverage data-driven insights to identify trends, assess the performance of pricing structures, and refine strategies accordingly.

KPIs such as the rate of pricing strategy optimization and the impact on profit margins over time can be used to measure this benefit. By fostering a culture of continuous improvement, organizations can ensure that their service pricing remains responsive to market dynamics and evolving business needs.

## Next steps

If you would like to implement Dynamics 365 solutions to assist with your *manage service pricing* business processes, you can use the following resources and steps to learn more.

- [Define service offering and strategy](concept-to-market-define-service-offerings-strategy-overview.md)

- [Introduce new services](concept-to-market-introduce-new-services.md)

- *Manage service pricing* (the article you're currently reading)

- [Define service costing](concept-to-market-define-service-costing-overview.md)

- *Manage service lifecycle*

## Related resources

You can use the following resources to learn more about the *manage service pricing* processes in Dynamics 365.

- [Service Management - Business Central](/dynamics365/business-central/service-service)

- [Define product pricing - Sales](/dynamics365/sales/create-price-lists-price-list-items-define-pricing-products)

- [Use the Dynamics 365 Commerce pricing engine with Dynamics 365 Sales](/dynamics365/fin-ops-core/fin-ops/data-entities/commerce-pricing)

- [Manage retail pricing in Dynamics 365 Commerce](/training/modules/manage-retail-pricing/)

- [Create a new trade agreement](/dynamics365/supply-chain/sales-marketing/tasks/create-new-trade-agreement)

- [Sales agreements overview](/dynamics365/supply-chain/sales-marketing/sales-agreements)

- [Price simulation - Supply Chain Management](/dynamics365/supply-chain/sales-marketing/price-simulation)

- [Pricing management overview (preview)](/dynamics365/supply-chain/pricing-management/pricing-management-overview)

- [Service management overview](/dynamics365/supply-chain/service-management/service-management-home-page)

- [Dynamics 365 Service Management](/dynamics365/field-service/overview)

- Find definitions of terminology used in content for *run production operations* in the [Glossary of terms in Dynamics 365 business processes]
    - [Discounts](glossary.md#discounts)
    - [Discount concurrency](glossary.md#discount-concurrency)
    - [Discount eligibility](glossary.md#discount-eligibility)
    - [Margins](glossary.md#margins)
    - [Price adjustments](glossary.md#price-adjustments)
    - [Pricing agreement](glossary.md#pricing-agreement)
    - [Price attributes](glossary.md#price-attributes)
    - [Price components](glossary.md#price-components)
    - [Pricing management](glossary.md#pricing-management)
    - [Promotional pricing](glossary.md#promotional-pricing)
    - [Purchase agreement](glossary.md#purchase-agreement)
    - [Sales agreement](glossary.md#sales-agreement)
    - [Service fees](glossary.md#service-fees)
    - [Service pricing optimization](glossary.md#service-pricing-optimization)
    - [Trade agreement](glossary.md#trade-agreement)

<!-- ## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Accounts receivable, Audit, Customer services, Finance, Marketing, Operations, Production, Project Management, Purchasing, Sales, Service operations, Treasury

*Products*: Dynamics 365 Business Central, Dynamics 365 Commerce, Dynamics 365 Customer Insights, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Rachel Profitt](https://www.linkedin.com/in/rachelprofitt/) \| Principal Program Manager
