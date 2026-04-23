---
title: Opportunity Health Overview in Dynamics 365 Sales
description: "Opportunity health tracking for sales management: Discover how to automate probability and highlight urgent deals in Dynamics 365 Sales using Power Apps."
#customer intent: As a Sales user, I want to be presented with a clear indication of the health of an Opportunity, immediately upon opening the form.
author: edupont04
ms.author: edupont
ms.date: 04/22/2026
ms.topic: reference-architecture
---

# Opportunity health overview in Dynamics 365 Sales

***Applies to***: ***Dynamics 365 Sales, Power Apps, Dataverse***

This solution combines Dynamics 365 Sales, Power Apps, and Dataverse to build a custom UI overview of opportunity health. Salespeople often ask for a clear indication of the health of an opportunity. With this solution, they get that indication immediately when they open the **Opportunity** form in Dynamics 365 Sales.

## Architecture

The following diagram illustrates the architecture for the solution.

:::image type="content" source="media/sales-opportunity-health.svg" alt-text="Architecture diagram showing how Dynamics 365 Sales, Power Apps, and Dataverse work together to display opportunity health, calculate weighted estimated revenue, and highlight overdue estimated close dates." lightbox="media/sales-opportunity-health.svg":::

[Download a PowerPoint file with this architecture](https://github.com/microsoft/dynamics365patternspractices/tree/main/architectures). To download an architecture, choose the file in the explorer, and then choose the download raw file icon.

## Workflow

1. A user updates the stage of an opportunity.

1. A business rule triggers and sets a value for the **Probability** field based on the stage of the opportunity.

    1. Qualify – 25%

    1. Define – 50%

    1. Propose - 75%

    1. Close – 90%

1. A calculated field **Weighted Total Est Revenue** is determined by normalizing *Probability* and multiplying it by *Total Est Revenue*: (*Probability* / 100) \* *Total Est Revenue*.

## Components

This reference architecture uses the following components.

- [A calculated field](/power-apps/maker/data-platform/formula-columns?tabs=type-or-paste) to determine the value of **Weighted Total Est Revenue** by multiplying the normalized probability percentage by the estimated value: `(Probability / 100) * Total Est Revenue`

- [A business rule](/power-apps/maker/data-platform/data-platform-create-business-rule) to determine the probability of the opportunity based on the stage it's in.

  | Field | Value |
  | --- | --- |
  | **Business Rule** | Set Opportunity Probability |
  | **Entity** | Opportunity |
  | **Scope** | Table |
  | **Actions** | If `prefix_probabilityoverwritten = false`, set **Probability** based on the relevant **Opportunity Stage** value:<br><br>- `Qualify` > Set Probability to `25%`<br>- `Define` > Set Probability to `50%`<br>- `Propose` > Set Probability to `75%`<br>- `Close` > Set Probability to `90%` |

- [A PCF Control](/power-apps/developer/component-framework/overview) to display the [**EstimatedCloseDate**](/dynamics365/developer/reference/entities/opportunity#BKMK_EstimatedCloseDate) field in red font, if the date is in the past.

  | Field | Value |
  | --- | --- |
  | **PCF Control** | Conditional Formatting Control |
  | **Configuration** | - `Hex`<br>String input that determines the font color.<br>- Bound to Date fields. |
  | **Actions** | If the value of the date or date/time is less than the current date/time, set the font color to the value in the `Hex` property. |

- [A JavaScript web resource](/power-apps/developer/model-driven-apps/script-jscript-web-resources) to display the **EstimatedCloseDate** column (within a grid view) as red if it is in the past.

  | Field | Value |
  | --- | --- |
  | **Web Resource (JS)** | `opportunity_grid.js` |
  | **Actions** | Create a function that catches the **EstimatedCloseDate** value when the Opportunity form opens or refreshes. The function checks if the **EstimatedCloseDate** value is earlier than or equal to the current date and time. If it is, set the text font color to red. |

## Scenario details

Sales users want a clear indication of the health of an opportunity, so they can see it as soon as they open the form. They want the stage of the opportunity to determine the probability, so they don't have to enter extra data. They want the font of the **EstimatedCloseDate** to be in red, so it's a clear indication that the opportunity needs some help. This solution is as much no-code as possible, such as by using Business Rules, but when pro-code is needed by using the PCF Control, it's designed in a way that can be reusable for multiple different scenarios and not just this one.

### Potential use cases

This solution was created for a professional services (accounting, tax, auditing) organization. It can also be applied to industries like manufacturing, education, real estate, construction, retail, and more. Any organization that keeps track of opportunities can use this solution.

Use this solution to:

- Help summarize important information about the opportunity

- Give a clear indication of opportunity health when viewing an opportunity form or grid

## Considerations

These considerations help implement a solution that includes Dynamics 365. Learn more at [Dynamics 365 guidance documentation](../index.yml).

### Cost optimization

Cost optimization is about looking at ways to reduce unnecessary expenses and improve operational efficiencies. For more information, see [Overview of the cost optimization pillar](/azure/architecture/framework/cost/overview).

The only cost for this design is the effort to build it. This cost is minimal because it uses built-in capabilities in Dynamics 365 Sales.

## Related resources

Review the following related architecture guides, solutions, and other guidance content:

- [Dynamics 365 Sales documentation](/dynamics365/sales/overview)  
- [Power Apps documentation](/power-apps/)  
- [Implementing controls using TypeScript](/power-apps/developer/component-framework/implementing-controls-using-typescript?tabs=before)  
<!-- 
## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Sales

*Products:* Dynamics 365 Sales -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Blake Scarlavai](https://www.linkedin.com/in/blake-scarlavai/) | Principal Consultant
