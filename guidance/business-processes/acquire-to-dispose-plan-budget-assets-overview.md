---
title: Plan and budget assets overview
description: Learn how you can use Microsoft Dynamics 365 products to support your organization's business processes for planning and budgeting assets.
ms.date: 09/08/2023
ms.topic: conceptual
author: edupont04
ms.author: hputhran
---

# Plan and budget assets overview

***Applies to: Dynamics 365 Finance, Dynamics 365 Supply Chain Management***

This article describes how you can use Dynamics 365 products to support your organization's business processes for planning and budgeting assets.

## Introduction to plan and budget assets

Companies generally use capital assets, whether tangible or intangible, to run business operations. The planning and budgeting of assets are crucial factors in determining the financial stability of a company. By forecasting the costs that are associated with acquiring, maintaining, and replacing assets, and by estimating the expenses and cash flow requirements, an organization helps ensure that it has enough funds for the maintenance budget.

Often, businesses use historical data to plan and budget new asset purchases. If the business is new, the planning of asset requirements might require deeper understanding of aspects such as the following list:

- The business model
- The long-term and short-term growth model
- Requirements from different business units
- The overall market strategy

A structured approach to the planning and budgeting of assets is an indicator of a mature organization that aims to reduce uncertainty and risks through effective asset management and maintenance. As a result, the stakeholders gain the confidence to invest in the vision and goals of the company.

## Plan and budget assets stakeholders

Many people in an organization must contribute to the decision-making process and design of the *plan and budget assets* process in your Dynamics 365 project. Stakeholders include the roles in the following list:

- **Asset managers** – Responsible for managing the lifecycle of assets.
- **IT department** – Responsible for maintaining and testing technology solutions.
- **Finance department** – Responsible for tracking asset costs.
- **Operations department** – Responsible for maintaining the maintenance schedule of the assets to support business operations, and for providing inputs if an asset requires any reactive maintenance.
- **Human resources department** – Responsible for hiring and training users who maintain and repair the assets.
- **Procurement department** – Responsible for purchasing spare parts and managing vendor relationships.
- **Legal and compliance department** – Responsible for ensuring regulatory compliance that is related to asset management.
- **Executive leadership** – Responsible for overseeing the acquisition and disposal of high-value assets, and for ensuring alignment with strategic goals.

## Plan and budget assets process flow

The following diagram shows the high-level business process flow for planning and budgeting assets.

[!INCLUDE [daf-business-process-flow-def](../includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/acquire-to-dispose-plan-budget-assets.svg" alt-text="Flow diagram with steps for the process of maintaining assets that is explained further in the next paragraphs." lightbox="media/acquire-to-dispose-plan-budget-assets.svg":::

The flow diagram for the *plan and budget assets* business process area covers the following steps.

1. Start
1. *Acquire to dispose*
1. *Plan and budget assets*

    1. *Classify assets*
    1. *Define sourcing strategy for assets*

        1. *Define budget for capital assets*

            1. Branch to the *Forecast to plan* end-to-end business process
            1. Subbranch to the *Project to plan* end-to-end business process
            1. Subbranch to the *Record to report* end-to-end business process
            1. *Create a project for capital assets*

                1. Branch to the *Project to plan* end-to-end business process
                1. Subbranch to the *Record to report* end-to-end business process
                1. *Request budget for capital assets*

                    1. *Review and approve requests for capital assets*
                    1. *Define resources for capital assets*
                    1. *Determine the capitalization for assets*
                    1. *Define asset depreciation policies*
                    1. *Create maintenance budget*

                        1. Branch to the *Record to report* end-to-end business process
                        1. *Track maintenance cost*
                        1. *Analyze maintenance costs*

            1. *Reallocate budget for existing capital assets*

                1. *Analyze maintenance costs*

        1. *Budget for leased assets*

            1. Branch to the *Forecast to plan* end-to-end business process
            1. Subbranch to the *Project to plan* end-to-end business process
            1. Subbranch to the *Record to report* end-to-end business process
            1. *Define leasing policies*

                1. Branch to the *Project to plan* end-to-end business process
                1. Subbranch to the *Record to report* end-to-end business process
                1. *Establish and define lease contracts*

                    1. Branch to the *Record to report* end-to-end business process
                    1. *Analyze maintenance costs*

1. End

## Plan and budget assets benefits

The following sections outline the key benefits that an organization might measure for *plan and budget assets*.

### Refined asset planning process

A well-planned process for purchasing, deploying, maintaining, and disposing of assets year over year helps organizations build a strong asset planning and budgeting strategy. Subsequent budgets can have better data, so that the organizations can plan for future requirements of assets and their maintenance.

### Optimized resource allocation

Planning and budgeting require evaluation of both the needs of the business and the condition and performance of the existing assets. As a result, organizations get a holistic picture of the cost-effective strategy for either replacing assets or reallocating them where they can be more efficient.

### Risk management

Effective asset planning and budgeting enables organizations to assess potential risks, such as redundant assets, equipment failures, end-of-life software, and any noncompliant practices. This information can help them create a proactive maintenance and replacement plan that can reduce the operational risks and, in turn, optimize asset lifecycle.

### Improved asset lease management

With Dynamics 365, organizations can more effectively manage leased assets as a lessee. Capabilities such as the following are built in:

- Lease accounting
- Lease management
- Lease portfolio analysis

These capabilities and others can help organizations reduce the risk of lease errors, improve lease compliance, and achieve cost savings. Learn more at [Asset leasing home page](/dynamics365/finance/asset-leasing/asset-leasing-homepage).

> [!NOTE]
> The flow diagram that this article provides for the *plan and budget assets* business process area is described at a high level. There might be variations in the process flow, depending on your operating model and business process requirements.

## Next steps

If you want to implement Dynamics 365 solutions to help with your *plan and budget assets* business processes, use the following resources and steps to learn more. Links are added as articles become available.

1. *Plan and budget assets* (the article that you're currently reading)
2. [Acquire assets](acquire-to-dispose-acquire-assets-overview.md)
3. [Manage internal assets](acquire-to-dispose-manage-internal-assets.md)
4. [Manage and report on asset financials](aquire-to-dispose-manage-report-asset-financials.md)
5. [Maintain and repair internal assets](acquire-to-dispose-maintain-repair-internal-asset.md)
6. [Retire and dispose of assets](acquire-to-dispose-retire-dispose-assets.md)

## Related resources

You can use the following resources to learn more about the *plan and budget assets* process in Dynamics 365.

- [Fixed assets home page (Finance)](/dynamics365/finance/fixed-assets/fixed-assets)
- [Asset leasing home page (Finance)](/dynamics365/finance/asset-leasing/asset-leasing-homepage)
- [Configure and manage fixed assets and asset leasing in Dynamics 365 Finance (training)](/training/paths/configure-manage-fixed-assets-dyn365-finance/)
- Find definitions of terminology that is used in content for *plan and budget assets* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article, including the following terms:

    - [Asset classification](glossary.md#asset-classification)
    - [Capital assets](glossary.md#capital-assets)
    - [Leased assets](glossary.md#leased-assets)
    - [Depreciation](glossary.md#depreciation)
    - [Capital asset budget](glossary.md#capital-asset-budget)
    - [Maintenance budget](glossary.md#maintenance-budget)

<!-- ## Tags

*Stakeholders:* Accounts payable, Accounts receivable, Administrative, Audit, Customer services, Finance, Human resources, Merchandising, Operations, Production, Project management, Purchasing, Retail store operations, Service operations, Treasury

*Products:* Dynamics 365 Finance, Dynamics 365 Supply Chain Management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Harshad Puthran](https://www.linkedin.com/in/harshman777/) \| FastTrack Solution Architect
