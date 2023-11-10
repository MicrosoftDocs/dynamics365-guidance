---
title:  Forecast demand for multiple companies
description: Read about Forecast demand for multiple companies in Dynamics 365 Supply Chain Management.
ms.date: 03/14/2023
ms.topic: conceptual
author: rachel-profitt
ms.author: raprofit
ms.reviewer: edupont
---

# Forecast demand for multiple companies

***Applies to: Dynamics 365 Supply Chain Management***

This article describes design considerations and patterns to configure demand forecasting when your organization has multiple legal entities.

## Context and problem

Many organizations are composed of multiple legal entities that engage in intercompany buying and selling activities. When the demand forecasting process runs, the demand expected for buying entities should be included as part of the demand forecasted by the selling entities. The figure below shows an example where there are three legal entities, where Company A sells to Company B and Company C. In this scenario, Company A's demand forecast should include expected sales to Company B, Company C, and any external customers of Company A.

:::image type="content" source="media/intercompany-planning-group-relationship.png" alt-text="Intercompany planning group relationship":::

## Solution: Implement intercompany planning groups

Configuring **Intercompany planning groups** allows an organization to define the sequence of companies to run demand forecasting for. The sequence should begin with the companies furthest downstream in the supply chain and end with the furthest upstream companies. Using the example in the figure above, the sequence would have Company B and Company C ranked first, and have Company A run after both Company B and Company C.

### Multiple intercompany trade patterns

If your organization has multiple companies where some items are traded with a subset of companies and other items are traded with a different subset of companies, you may need to configure multiple **Intercompany planning groups**. In this example, you will need to create **Item allocation keys** for the different groups of items and assign the **Item allocation keys** to the appropriate **Intercompany planning group**.

### Procedure: Configure and use Intercompany planning groups

Use the following steps to configure your intercompany planning groups.

1. Create **Item allocation keys**. For more information, see [Create item allocation keys](/dynamics365/supply-chain/master-planning/demand-forecasting-setup#item-allocation-keys).

2. Assign **Item allocation keys** to released products.

3. Create an **Intercompany planning group**. For more information, see [Configure intercompany planning groups](/dynamics365/supply-chain/master-planning/demand-forecasting-setup#intercompany-planning-groups).

4. Add legal entities to the **Intercompany planning group** in the required sequence.

5. Assign **Item allocation keys** to the **Intercompany planning group** as required.

## Issues and considerations

Use the following design considerations when you are preparing to configure **Intercompamy planning groups** in Dynamics 365 Supply Chain Management.

### Multiple intercompany supply chains

When your organization has more than one group of companies that trade with each other, you may need to create multiple **Intercompany planning groups**. For example, you have six companies. Companies A, B, and C trade with each other, but not with D, E, F. While companies D, E, and F trade with each other. In this case, you might create two **Intercompany planning groups** for each group of companies.

## When to use this pattern

Use this pattern to:

- More than one legal entity is configured
- Requirements to plan demand across legal entities

## Additional resources

Use the following resources to learn more about Demand forecasting in Dynamics 365 Supply Chain Management.

- [Demand Forecasting with Azure Machine Learning Series](https://community.dynamics.com/blogs/post/?postid=be5e2cbb-373f-4167-9e57-8ccb97f97b84)

- [Demand forecasting overview](/dynamics365/supply-chain/master-planning/introduction-demand-forecasting)

<!--## Tags
*Stakeholder*: Cost accountant; Manufacturing SME

*Products*: Dynamics 365 Supply Chain Management

*Configuration stage*: Iterative
