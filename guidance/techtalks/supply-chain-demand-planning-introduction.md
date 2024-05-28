---
title: Demand planning for Supply Chain Management
description: Learn about the importance of demand planning for Dynamics 365 Supply Chain Management and the flexibility it brings to supply chain operations.
ms.topic: conceptual
author: dereklh77
ms.author: v-heuerderek
ms.date: 02/27/2024
ai-usage: ai-assisted
---

# TechTalk: Demand planning for Dynamics 365 Supply Chain Management

In the dynamic world of supply chain management (SCM), it's crucial to stay ahead in forecasting and demand planning. The introduction of advanced demand planning capabilities in Dynamics 365 Supply Chain Management is set to revolutionize this domain. These recently announced capabilities, which are currently in public preview, bring a new level of precision and flexibility to supply chain operations.

We based this article on [a TechTalk](https://www.youtube.com/embed/3fTK02OKS\_o?si=P3Wpbp-ZDfhk2iyV) that you can find online in the Dynamics 365 channel on YouTube.

:::image type="content" source="media\demand-planning-dynamics-365-scm-1.svg" alt-text="PowerPoint thumbnail for the 'Demand Planning for S C M (public preview)' presentation by Beatriz Nebot Gracia and Erol Celebic." link="https://www.youtube.com/embed/3fTK02OKS\_o?si=P3Wpbp-ZDfhk2iyV":::

## Seamless data integration

:::image type="content" source="media\demand-planning-dynamics-365-scm-2.svg" alt-text="Graphic that shows the planning phase of the classic supply chain pipeline structure, with a focus on suppliers, manufacturer, distribution center, and customer." lightbox="media\demand-planning-dynamics-365-scm-2.svg":::

## Data import and transformation

The journey toward enhanced demand planning begins with the seamless integration of data. Historical data can be imported from a range of sources, such as Azure Data Lake Storage and comma-separated values (CSV) files. This inclusive approach extends even to businesses that don't currently use finance and operations (FNO) systems. Therefore, it widens the scope of who can benefit from these tools.

After the data is collated, it goes through a transformation phase. Here, the raw data is methodically structured into daily, weekly, or monthly segments. This reorganization is pivotal for simplifying complex datasets into more manageable forms for analysis.

### Establishing data relationships

A notable feature is the ability to create relationships between various data tables. This feature ensures a unified and comprehensive dataset that is ready for the subsequent stages of forecasting and analysis.

## Advanced forecasting capabilities

:::image type="content" source="media\demand-planning-dynamics-365-scm-3.svg" alt-text="Graphic that shows the forecasting workflow, detailing Arima, E T S, Prophet, Best fit, and Custom Azure ML." lightbox="media\demand-planning-dynamics-365-scm-3.svg":::

## Using various forecasting models

The heart of the Demand Planning app lies in its forecasting capabilities. The app employs advanced models, such as Arima, ETS, and Profit. Therefore, businesses have a range of choices and can find the model that best suits their data. The "best fit" option is a standout feature. It analyzes the effectiveness of each model on the data and suggests the most optimized solution.

## Integration with custom algorithms

For businesses that have pre-existing forecasting models, the app provides the flexibility to integrate custom algorithms. This feature ensures that previous investments in machine learning and data analysis continue to add value.

## Collaborative review and adjustment

A critical component of demand planning is the ability to review and adjust forecasts. The app facilitates this process by enabling effective team collaboration. It allows for adjustments at both granular and aggregate levels, and offers the management of different forecast versions.

## Exporting and using data

The final step in the demand planning process is exporting the data. This feature is crucial because it enables the refined forecasts to be exported back into Dynamics 365 Supply Chain Management or other formats. Therefore, it ensures practical application in supply chain execution.

## Looking ahead: the roadmap

The roadmap for the Demand Planning app is filled with promising developments. Examples include cell commenting for collaborative adjustments, role-level access for user-specific experiences, and special features for new product introductions. There are also plans to introduce copilot experiences for enriched user interactions.

Various resources are available to help users maximize the potential of this app. They include instructional videos, tutorials, and comprehensive documentation on the Dynamics 365 for Supply Chain Management Learn page. Community engagement through customer sign-up forms and Yammer groups is encouraged for feedback and shared learning. An upcoming workshop in Copenhagen offers an in-depth exploration of the app's capabilities and future direction.

## Conclusion

The new demand planning capabilities in Dynamics 365 Supply Chain Management represent a significant advancement in supply chain forecasting and management. Thanks to its comprehensive process, which ranges from data integration to practical application, together with upcoming enhancements, this tool is poised to become a cornerstone in modern supply chain operations.

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [Predict future demand for products and services with demand forecasting to drive business decisions](../business-processes/forecast-to-plan-demand-forecasting-overview.md)
- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
