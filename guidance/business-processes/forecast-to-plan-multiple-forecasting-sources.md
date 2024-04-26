---
title: Configure demand forecasting for organizations with multiple sources
description: Read about forecast demand from multiple sources in Dynamics 365 Supply Chain Management, including overviews on the context, problem, and integration with forecasting tools.
ms.date: 04/26/2024
ms.topic: conceptual
author: rachel-profitt
ms.author: raprofit
ms.reviewer: edupont
---

# Configure demand forecasting for organizations with multiple sources for forecasting demand history

***Applies to: Dynamics 365 Supply Chain Management***

This article describes design considerations and patterns to configure demand forecasting when your organization has multiple sources for forecasting demand history.

## Context and problem

An organization can have multiple sources for the demand forecast, including multiple statistically generated forecasts, customer forecasts, sales team forecasts, and so on.  

## Solution: Record each forecast in a separate forecast model

Each forecast line in Dynamics must be assigned to a forecast model, which is a configurable value.  

## Issues and considerations

Use the following design considerations when you're preparing to configure **multiple forecasting sources** in Dynamics 365 Supply Chain Management.

### Integration with third-party forecasting tools

When some items are forecasted using a third-party solution and loaded to Dynamics 365 through integration, you should create a separate forecast model for each integration. For example, if you use Forecasting Solution A for some items and Dynamics for forecasting other items, you would have one forecast model that contains the Solution A forecast and one that contains the Dynamics statistical forecast.

### Multiple forecasts for the same item

For one item, a company might have different types of forecasts, such as the statistical forecast, customer-provided forecasts, and sales forecasts. In this case, a separate forecast model should be created for each type of forecast.

### Procedure: Configure forecast models

Create forecast models, set up integrations to load forecasts to unique forecast models for that integration, create business rules for when different forecast models should be used for other types of forecasts.

## Related resources

Use the following resources to learn more about demand forecasting in Dynamics 365 Supply Chain Management.

- [Webinar: Demand Forecasting with Azure Machine Learning Series](https://community.dynamics.com/blogs/post/?postid=be5e2cbb-373f-4167-9e57-8ccb97f97b84)  
- [Demand forecasting overview](/dynamics365/supply-chain/master-planning/introduction-demand-forecasting)  

<!--## Tags
*Stakeholders*: Cost accountant; Manufacturing SME  

*Products*: Dynamics 365 Supply Chain Management  

*Configuration stage*: Iterative  
