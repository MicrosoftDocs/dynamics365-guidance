---
title: Manage and report on asset financials
description: Learn how you can use Microsoft Dynamics 365 products to support your organization's business processes to manage and report on asset financials.
ms.date: 09/08/2023
ms.topic: conceptual
author: edupont04
ms.author: hputhran

---

# Manage and report on asset financials

***This applies to: Dynamics 365 Finance,*** ***Dynamics 365 Supply Chain Management***

This article describes how you can use Dynamics 365 products to support your organization's business processes to *manage and report on asset financials*.

## Introduction to manage and report on asset financials

Organization may have certain assets that are large items in the balance sheet. Based on the location and area where the assets are installed or deployed, there may be extra tax component associated with the asset. These assets may have insurance associated with them as well. In some cases, assets may be leased out to a lessee. Hence, it becomes important for companies to optimally manage and report asset information.

Fixed assets are reported on the balance sheet. Activities related to investments are captured in a company's cash flow statement. The acquisition or disposal of an asset is also recorded in the cash flow statement.

When you use a general ledger together with fixed assets, you can view the current value of all fixed assets. The way in which fixed assets are handled must correspond to both international accounting standards and the accounting legislation in each country/region.

Companies start off by evaluating the need for assets and budget/plan it up in advance. The process then involves either acquiring an asset or leasing an asset depending on multiple parameters. In case the asset is acquired, it goes through a high-level process that could be a mix of more asset related information adjustment, depreciation, disposal. Companies can define rules to record acquisition method, depreciation and disposal, write-ups and write-downs.

The management of assets and its finance is an ongoing operational process for an organization. It becomes more important when audits are executed to review financial information.

In Dynamics 365, you find multiple reports to assess fixed asset information. One such example is the [Fixed assets roll forward report (Finance)](/dynamics365/finance/fixed-assets/fixed-asset-roll-forward-report). 

## Stakeholders

Stakeholders include the roles listed in the following list:

- **Asset managers** - responsible for managing the lifecycle of assets

- **IT department** - responsible for maintaining and testing technology solutions

- **Finance department** - responsible for tracking asset costs

- **Operations department** - responsible for maintaining the maintenance schedule of the assets to support business operations and providing inputs if an asset requires any reactive maintenance

- **Legal and compliance department** - responsible for ensuring regulatory compliance related to asset management

- **Executive leadership** - responsible for overseeing the acquisition and disposal of high-value assets and ensuring alignment with strategic goals.

## Manage and report on asset financials process flow

The following diagram shows the high-level business process flow for *manage and report on asset financials*.

:::image type="content" source="media/aquire-to-dispose-manage-report-asset-financials.svg" alt-text="Flow diagram with steps for the business process area that is further explained in the next paragraphs." lightbox="media/aquire-to-dispose-manage-report-asset-financials.svg":::

Each solid gray rectangle on the diagram represents an end-to-end business process. The solid blue rectangle represents the *manage and report on asset financials* business process area. The diagram shows the subprocesses for this business process area. The arrows on the diagram show the flow of the business process in an organization. If a subprocess can lead to more than one other subprocess, the parallel subprocesses are shown as branches.

The *manage and report on asset financials* business process area flow diagram cover the following steps.

1. Start

2. *Acquire to dispose*

3. *Manage and report on asset financials*

    1. *Define asset accounting books*

    2. *Define depreciation and amortization policies*

    3. *Define depreciation and amortization schedules*

        1. (First branch)

            1. *Define and adjust lease*

                1. Subbranch to *Record to report*  

            2. *Record lease expenses*

                1. Subbranch to *Record to report*  

            3. *Accrue lease payments*

                1. Subbranch to *Record to report*  

            4. *Make asset lease payments*

                1. Subbranch to *Record to report* 

            5. *Make variable payments and perform index revaluation*

                1. Subbranch to *Record to report*  

            6. *Depreciate asset leases*

                1. Subbranch to *Record to report*  

            7. *Amortize lease liability and record interest expense*

                1. Subbranch to *Record to report*  

            8. *Impair a lease agreement*

                1. Subbranch to *Record to report*  

            9. End

        2. (Second branch)

            1. *Revalue and adjust assets*

                1. Subbranch to *Record to report*  

            2. *Generate depreciation and amortization entries*

                1. Subbranch to *Record to report*  

            3. *Correct and adjust depreciation and amortization*

                1. Subbranch to *Record to report*  

            4. *Review and approve depreciation and amortization entries*

                1. Subbranch to *Record to report*  

            5. End

## Manage and report on asset financials benefits

The following sections outline the key benefits that an organization might measure to *manage and report on asset financials*. 

### Effective financial management

Having inaccurate fixed asset information can lead to incorrect financial reporting. During audits, the auditing entity may flag off certain assets that don't have correct financial information. Hence, maintaining accurate financial information is important. It helps in building investor and shareholder confidence in an organization and also helps to maintain credibility with vendors.

### Improved reporting

When organizations manage and conduct regular reviews of their assets, applying proper controls and processes, the overall asset journey can be laid out properly via financial reports by the accounting team. Such reporting helps in identifying any gaps, issues with information of assets, its financial impacts to the general ledger and a company's performance using these assets.

> [!NOTE]
> The *manage and report on asset financials* business process area flow is described at a high level. There may be variations in the process flow depending on your operating model and business process requirements.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *manage and report on asset financials* business processes, use the following resources and steps to learn more.

1. [Plan and budget assets](acquire-to-dispose-plan-budget-assets-overview.md)  

2. [Acquire assets](acquire-to-dispose-acquire-assets-overview.md)  

3. [Manage internal assets](acquire-to-dispose-manage-internal-assets.md)  

4. *Manage and report on asset financials*. (The article you're currently reading.)

5. [Maintain and repair internal assets](acquire-to-dispose-maintain-repair-internal-asset.md)  

6. [Retire and dispose of assets](acquire-to-dispose-retire-dispose-assets.md)  


## Related resources

You can use the following resources to learn more about the *manage and report on asset financials* process in Dynamics 365.

- [Fixed assets home page (Finance)](/dynamics365/finance/fixed-assets/fixed-assets)  
- [Configure and manage fixed assets and Asset leasing in Dynamics 365 Finance (training)](/training/paths/configure-manage-fixed-assets-dyn365-finance/)  
- Find definitions of terminology used in content for *manage and report on asset financials* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article, including the following terms:

  - [Asset](glossary.md#asset)  
  - [Asset books](glossary.md#asset-books)  
  - [Amortization](glossary.md#amortization)  
  - [Cashflow statement](glossary.md#cashflow-statement)  
  - [Index revaluation](glossary.md#index-revaluation)  

<!-- ## Tags

*Stakeholders:* Accounts payable, Accounts receivable, Administrative, Audit, Customer services, Finance, Human resources, Merchandising, Operations, Production, Project management, Purchasing, Retail store operations, Service operations, Treasury

*Products:* Dynamics 365 Finance, Dynamics 365 Supply Chain Management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Harshad Puthran](https://www.linkedin.com/in/harshman777/) \| FastTrack Solution Architect
