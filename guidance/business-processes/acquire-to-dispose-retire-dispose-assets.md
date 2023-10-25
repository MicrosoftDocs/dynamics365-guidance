---
title: Retire and dispose of assets
description: Learn how you can use Microsoft Dynamics 365 products to support your organization's business processes to retire and dispose of assets.
ms.date: 09/08/2023
ms.topic: conceptual
author: edupont04
ms.author: hputhran

---

# Retire and dispose of assets

***This applies to: Dynamics 365 Business Central, Dynamics 365 Finance, Dynamics 365 Supply Chain Management***

This article describes how you can use Dynamics 365 products to support your organization's business processes to *retire and dispose of assets*.

## Introduction to retire and dispose of assets

In the rapidly evolving business environment of today, for any organization, the process of retiring and disposing of assets holds a pivotal role in the lifecycle management of resources within that organization. The *retire and dispose of assets* business process involves retiring and disposing of fixed assets that are no longer needed. It also covers when assets must be replaced by assessing the lifecycle stage, usability, and alignment of assets with the organizational goals.

As assets mature, outgrow their usefulness, or no longer fit the evolving demands of the business, or as technology evolves, the strategic choice to *retire and dispose of assets* is crucial. Making informed decisions about their retirement and disposal ensures that the organization maintains operational efficiency, optimizes resource allocation, and adheres to legal and environmental responsibilities.  

When a fixed asset is no longer needed, it can either be scrapped or sold. If the asset still has value, it's likely to be set to be sold. When a fixed asset is sold with profit, the profit is recognized in the year of the sale, and then it's posted to the profit and loss part of the chart of accounts.

## Retire and dispose of assets stakeholders

To navigate the intricacies of asset management successfully, many people in an organization must contribute to the decision making when it comes to the retirement and disposal of assets in your Dynamics 365 project. Stakeholders include the roles listed in the following list:

- **Asset Management department** - responsible for assessing asset's condition and recommending next steps regarding retirement and disposal of the assets

- **Finance department** - responsible for overseeing the financial implications, taxes, and potential profits or losses

- **Executive leadership** - responsible for deciding which assets are no longer needed to be in alignment with strategic goals

- **Operations department** - responsible for providing insights into asset performance and helps determine if retirement aligns with business objectives and operational needs

- **Legal and compliance department** - responsible for ensuring adherence to regulatory requirements during asset disposal

- **Sustainability team** – responsible for ensuring asset disposal practices are in line with sustainability goals

## *Retire and dispose of assets* process flow

The following diagram shows the high-level business process flow for *retire and dispose of assets*.

:::image type="content" source="media/aquire-to-dispose-retire-dispose-assets.svg" alt-text="Flow diagram with steps for the business process area that is further explained in the next paragraphs." lightbox="media/aquire-to-dispose-retire-dispose-assets.svg":::

Each solid gray rectangle on the diagram represents an end-to-end business process. The solid blue rectangle represents the *retire and dispose of assets* business process area. The diagram shows the subprocesses for this business process area. The arrows on the diagram show the flow of the business process in an organization. If a subprocess can lead to more than one other subprocess, the parallel subprocesses are shown as branches.

The *retire and dispose of assets* business process area flow diagram covers the following steps.

1. Start

2. *Acquire to dispose*

3. *Retire and dispose of assets*

    1. *Define accounting policies for fixed asset retirement or disposal*

    2. Scrap assets?  
        1. Yes

            1. *Remove an asset from service by scrapping it*

            2. *Record to report*

        2. No

    3. Sell assets?

        1. Yes

            i. *Remove an asset from service through sale*

            ii. *Order to cash*

        2. No

    4. Replace assets?

        1. Yes

            i. *Remove an asset from service through trade-in*  
            ii. *Inventory to deliver*

4. End

The following end-to-end downstream processes have connections to End: [Inventory to deliver](inventory-to-deliver-overview.md), [Record to report](record-to-report-overview.md), and [Order to cash](order-to-cash-overview.md).  

## Retire and dispose of assets benefits

The retirement and disposal of assets business process brings several benefits to an organization contributing to its cost optimization, risk mitigation and enhanced employee productivity. Disposal of assets in an ecologically conscious manner contributes to an organization's sustainability efforts.

The following sections outline the key benefits for an organization through asset retirement and disposal.

### Improved cost savings

Older assets tend to require more frequent maintenance and repairs, which can incur significant expenses. By retiring or disposing these assets in a timely manner, the organizations can eliminate or reduce these ongoing costs.

### Reduced depreciation impact

As assets age, their value decreases due to depreciation. Retiring and disposing of assets at the appropriate time helps mitigate the impact of depreciation on financial statements.

### Accurate financial reporting

When an asset is disposed, the disposal value together with any related gain or loss is posted. So, asset disposal can alter financial statements and impact the accuracy of financial metrics like depreciation, balance sheets, and profit calculations. Therefore, properly retiring and disposing of assets ensures accurate financial reporting.

### Better compliance and safety

Properly retiring assets ensures compliance with legal and regulatory requirements. Retiring or disposing assets that no longer comply with regulations, organizations can avoid potential legal and regulatory issues. Retiring the older assets that pose safety hazards due to wear and tear, helps create a safer work environment for employees, reducing the risk of accidents and injuries.

### Alignment with business goals

Retiring and disposing assets that no longer align with the organization's current business goals and strategies, organizations can reallocate resources, both financial and human, to more productive areas. This ensures that resources are invested where they can have the most impact.

### Improved risk management

Older assets are more prone to breakdowns and failures, which can disrupt operations and lead to unexpected costs. Retiring such assets helps mitigate operational risks, downtimes, and potential safety hazards, contributing to a safer work environment and ensures smoother business continuity.

### Enhanced employee productivity

Retiring outdated or nonfunctioning assets allows organizations to replace them with newer, more technologically advanced models can boost workforce efficiency and can provide a competitive advantage in the market. Up-to-date and well-maintained assets contribute to employee productivity.

> [!NOTE]
> The **retire and dispose of assets** business process area flow is described at a high level. There may be variations in the process flow depending on your operating model and business process requirements.

## Next steps

If you would like to implement Dynamics 365 solutions to assist with your *retire and dispose of assets* business processes, you can use the following resources and steps to learn more.  

1. [Plan and budget assets](acquire-to-dispose-plan-budget-assets-overview.md)  

2. [Acquire assets](acquire-to-dispose-acquire-assets-overview.md)  

3. [Manage internal assets](acquire-to-dispose-manage-internal-assets.md)  

4. [Manage and report on asset financials](aquire-to-dispose-manage-report-asset-financials.md)  

5. [Maintain and repair internal assets](acquire-to-dispose-maintain-repair-internal-asset.md)  

6. *Retire and dispose of assets*. (The article you're currently reading.)

## Related resources

You can use the following resources to learn more about the *retire and dispose of assets* process in Dynamics 365.

- [Dispose of a fixed asset using a free text invoice (Finance)](/dynamics365/finance/fixed-assets/tasks/dispose-fixed-asset-free-text-invoice)

- [Dispose of a fixed asset as scrap (Finance)](/dynamics365/finance/fixed-assets/dispose-of-a-fixed-asset-as-scrap)

- [Dispose and lend fixed assets (training)](/training/modules/manage-fixed-assets-dyn365-finance/13-dispose-lend)

- [Fixed asset disposal posting accounts (Finance)](/dynamics365/finance/fixed-assets/fixed-asset-disposal-posting-accounts)

- [Dispose of or Retire Fixed Assets (Business Central)](/dynamics365/business-central/fa-how-dispose-retire)  

- [Manage Budgets for Fixed Assets (Business Central)](/dynamics365/business-central/fa-how-manage-budgets)  

- [All TechTalks](https://community.dynamics.com/blogs/?blogid=e624b369-bfb9-4c57-8f1b-b3656ac91f5a)  

- Find definitions of terminology used in content for *retire and dispose of assets* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article, including the following terms:

  - [Asset](glossary.md#asset)  
  - [Asset disposal](glossary.md#asset-disposal)  
  - [Asset replacement](glossary.md#asset-replacement)  
  - [Asset scrapping](glossary.md#asset-scrapping)  
  - [Asset selling](glossary.md#asset-selling)  
  - [Write-off](glossary.md#write-off)  
  - [Appraisers](glossary.md#appraisers)  
  - [Asset decommissioning](glossary.md#asset-decommissioning)  

<!-- ## Tags

*Stakeholders:* Accounts payable, Accounts receivable, Administrative, Audit, Legal and Compliance, Finance, Merchandising, Operations, Appraisers, Purchasing.

*Products:* Dynamics 365 Business Central, Dynamics 365 Finance, Dynamics 365 Supply Chain Management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Sneha Daggubati](https://www.linkedin.com/in/sneha-daggubati-04665848/)  \| Senior Cloud Solution Architect

