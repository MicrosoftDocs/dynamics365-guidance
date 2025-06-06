---
title: Overview of the Acquire to dispose business process areas
description: Get an overview for each of the business process areas in the Acquire to dispose end-to-end business process in Dynamics 365 solutions.
ms.date: 05/21/2025
ms.topic: concept-article
author: edupont04
ms.author: archanap

---

# Overview of the Acquire to dispose business process areas

***Applies to: Dynamics 365 Business Central, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Guides, Dynamics 365 Remote Assist***

The *acquire to dispose* process is broken down into many business process areas. The following sections further describe the business process areas.

## Define asset strategy

This business process area was added in the February 2025 version of the business process catalog. We're still working on the definition.

## Plan and budget assets

This business process area is deprecated in the current version of the business process catalog. The processes are now included in the *Acquire assets* business process area.
<!-- involves creating and managing budgets for acquiring and maintaining fixed assets, including identifying asset needs, estimating costs, and tracking budget performance. Budget plans can be generated from general ledgers, fixed assets, or project forecasts in Dynamics 365 Finance.

Planning and budgeting of assets also takes into consideration leasing of the assets, such as equipment or property, by evaluating leasing options, determining the lease threshold, and negotiating leasing terms.  

Learn more at [Plan and budget assets overview](acquire-to-dispose-plan-budget-assets-overview.md). -->

## Acquire assets

This business process area involves acquiring fixed assets, such as equipment or property, by purchasing or leasing them, and securing rights for intangible assets such as trademarks, patents, and licenses. The area includes identifying asset needs, evaluating asset options, sourcing the assets, creating purchase or lease orders, and receiving and recording asset deliveries.

You register newly acquired fixed assets, such as equipment or property, as asset records with asset tags and asset details. You can register the asset either through an invoice journal in the *Accounts payable* module or a fixed assets journal in the *Fixed assets* module in Dynamics 365 Finance, or through a purchase order in Dynamics 365 Supply Chain Management. You can also manage and acquire fixed assets in Dynamics 365 Business Central.

The asset acquisition process also encompasses leasing assets from a lessor, negotiating lease terms, making lease payments, and complying with lease agreements. Asset leasing module in Dynamics 365 Finance enables the lessee to create legal contracts between the lessor and lessee. It provides the flexibility to create lease extension and expansion as well as create impairment transactions that use the right-of-use asset for non-recoverable costs.  

Learn more at [Acquire assets overview](acquire-to-dispose-acquire-assets-overview.md).

## Manage active assets

This business process area is renamed in the current version of the business process catalog. In earlier versions, it's name was *manage internal assets*.

This business process area involves managing the day-to-day operations of fixed assets, including tracking asset usage, insuring the assets, and optimizing asset performance. Management of internal assets also refers to managing leased assets by tracking lease payments and complying with lease agreements.  

Learn more at [Manage active assets](acquire-to-dispose-manage-internal-assets.md).  

## Perform asset maintenance

This business process area involves maintaining and repairing internal assets by creating work orders in Dynamics 365 Field Service. If the work order is tagged to a mixed-reality guide with Dynamics 365 Guides, the worker can check if the guide is available through Dynamics 365 Supply Chain management mobile app and open it in the Dynamics 365 Guides HoloLens app. It's also possible to provide remote maintenance and conduct remote inspection with Dynamics 365 Remote Assist.  

Learn more at [Perform asset maintenance](acquire-to-dispose-maintain-repair-internal-asset.md).  

## Dispose of assets

This business process area involves retiring and disposing of fixed assets that are no longer needed or need to be replaced. In Dynamics 365 Finance, disposal of a fixed asset can be done through fixed asset invoices or a fixed asset disposal journal. In Dynamics 365 Supply Chain Management, you can register the replacement or sale of an asset. The disposal of assets also triggers calculation of asset depreciation, write-offs, and losses, which is then accounted for in financial reporting.  

Learn more at [Dispose of assets](acquire-to-dispose-retire-dispose-assets.md)  

## Analyze assets

This business process area involves calculating and recording asset depreciation, amortization, and adjustments by looking at the earnings, maintenance costs, and useful life value of the asset. This ensures accurate financial reporting of the asset's return of investment and compliance with accounting standards. The area gives an indication of whether the asset is performing at an optimal level. It also enables the asset managers to analyze the maintenance costs for the internal and leased assets to optimize maintenance strategies.  

Learn more at [Manage and report on asset financials](aquire-to-dispose-manage-report-asset-financials.md).  

## Next steps

If you want to implement Dynamics 365 solutions to assist with the *acquire to dispose* business processes, use the following resources and steps to learn more.

1. Define the goals and objectives of implementing an *acquire to dispose* technology solution. Learn more at [Implementation strategy](../implementation-guide/implementation-strategy.md).

2. Define the business process scope of your project. Learn more at [Process-focused solution](../implementation-guide/process-focused-solution.md)

3. Get a demo of Dynamics 365 solutions for the *acquire to dispose* process. For more information, see [Request a demo](https://dynamics.microsoft.com/)

4. Sign up for a trial of Dynamics 365. For more information, see [Start a Free Trial for Microsoft Dynamics 365](https://www.microsoft.com/dynamics-365/free-trial)

5. Learn about the business process catalog at [About the business process catalog for Dynamics 365 apps and services](about.md)  

## Related information

You can use the following resources to learn more about the *acquire to dispose* process in Dynamics 365.

- [TechTalk series: Asset Management in Dynamics 365 Supply Chain Management](https://community.dynamics.com/blogs/post/?postid=cd219602-2708-4b4a-9d62-3af9b4e63e10)

- [Asset management overview](/dynamics365/supply-chain/asset-management/)

- [Asset leasing home page](/dynamics365/finance/asset-leasing/asset-leasing-homepage)

- [Fixed assets home page](/dynamics365/finance/fixed-assets/fixed-assets)

- [Get started with Asset Management for Dynamics 365 Supply Chain Management](/training/modules/get-started-asset-management/)

- [Microsoft Certified: Dynamics 365 Fundamentals (ERP)](/certifications/d365-fundamentals-finance-and-operations-apps-erp/)

- [Microsoft Certified: Dynamics 365 Finance Functional Consultant Associate](/certifications/d365-functional-consultant-financials/)

<!--## Tags
*Stakeholders:* Accounts payable, Accounts receivable, Administrative, Audit, Customer services, Finance, Human Resources, Merchandising, Operations, Production, Project Management, Purchasing, Retail Store Operations, Service Operations, Treasury

*Products:* Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Guides, Dynamics 365 Remote Assist
