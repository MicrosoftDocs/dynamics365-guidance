---
title: Acquire assets overview
description: Learn how you can use Dynamics 365 products to support the organization's business processes to acquire assets.
ms.date: 08/31/2023
ms.topic: conceptual
author: edupont04
ms.author: sdaggubati

---

# Acquire assets overview

***This applies to: Dynamics 365 Business Central, Dynamics 365 Finance, Dynamics 365 Supply Chain Management*** 

This article describes how you can use Dynamics 365 products to support your organization's business processes to acquire assets.

## Introduction to acquire assets

In the rapidly evolving business environment of today, organizations must effectively manage their assets to optimize operations, improve decision-making, and to thrive and remain competitive all while balancing their financial resources.

The acquire assets functionality plays a vital role in facilitating the acquisition, monitoring, and utilization of assets throughout their lifecycle.

Asset data is often maintained in worksheets and is typically configured after the general ledger setup is completed in Dynamics 365. A lot of organizations start late with data migration of data that is related to fixed asset or asset management. They often realize that there are gaps when the balance or transaction type of data is brought into the business solution. We recommend that you start the fixed asset migration early in the project to pressure-test the data and the processes that the business team follows.

With [asset leasing](/dynamics365/finance/asset-leasing/asset-leasing-homepage) in Dynamics 365 Finance, organizations can access and use assets without the need for large upfront investments. Instead of purchasing assets outright, organizations can lease them from leasing companies for a predetermined period. With the asset leasing module in Dynamics 365 Finance, the lessee to create legal contracts between the lessor and lessee.

Here are some common methods to acquire assets in Dynamics 365 Finance and Supply Chain Management:

1. **Procurement and sourcing**: With [procurement and sourcing](/dynamics365/supply-chain/procurement/procurement-sourcing) in Dynamics 365 Supply Chain Management, organizations can source assets from suppliers. This supports a supplier bidding process for supplier selection, negotiation, and purchase agreement creation. Users can use these features to acquire assets from approved suppliers through:

    1. Purchase orders

    2. Purchase requisition

2. **Fixed assets**: With the [fixed assets](/dynamics365/finance/fixed-assets/fixed-assets) module, organizations can manage their fixed assets throughout their lifecycle, which includes acquiring assets through one of the following means:

    1. Asset creation

    2. Asset acquisition journal

    3. Asset transfer

You can also acquire and manage fixed assets in Dynamics 365 Business Central. Learn more at [Acquire Fixed Assets](/dynamics365/business-central/fa-how-acquire).   

## Acquire assets stakeholders

To navigate the intricacies of asset management successfully, many people in an organization must contribute to the decision making when it comes to the acquisition of assets in your Dynamics 365 project. Stakeholders include the roles listed in the following list:

- **Finance department** - responsible for overseeing the budget aspects of asset acquisition and managing financial aspects of the lease.

- **Procurement department** - responsible for negotiating contracts, bidding process, and ensuring that assets are acquired within budgetary constraints while adhering to quality standards.

- **Executive leadership** - responsible for determining types of assets needed and ensuring alignment with strategic goals.

- **Operations department** - responsible for utilizing and maintaining the acquired or leased assets effectively and providing inputs on operational requirements, performance expectations, and maintenance needs of the assets.

- **IT department** - responsible for maintaining and testing technology solutions.

- **Legal and compliance department** - responsible for ensuring regulatory compliance and contractual terms related to asset acquisition and lease agreements.

- **Lessor** (the leasing party) – responsible for leasing assets to the lessee and maintaining the assets.

- **Lessee** (the current organization, business, or party) – responsible for utilizing the assets, making lease payments as per contract.

## Acquire assets process flow

The following diagram shows the high-level business process flow for acquiring assets. There are several entry points for the subprocesses described in the diagram including one from the [procure to pay](procure-to-pay-overview.md) end-to-end process, and one from the [project to profit](project-to-profit-overview.md) end-to-end process. Multiple exit points have been defined from the subprocesses described in the diagram, which include one to the plan to produce end-to-end process, the inventory to deliver end-to-end process and to the record to report end-to-end business process.

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

The first step in acquiring asset business process flow is to identify the need to either source or replace a particular asset by an organization within the given budget constraints. The next key process is to then determine preferred vendors to procure the asset from or to identify potential lessors. The organization that leases the asset should proceed with creating leases. They should define contract terms, followed by accepting the asset and commissioning the assets and recording liabilities. The organization that sources the assets should proceed with procurement to complete the acquisition. Then they can install the assets, define preventive maintenance plans, and commission the asset.

:::image type="content" source="media/acquire-to-dispose-acquire-assets.svg" alt-text="Flow diagram for the business process area, which is explained in the paragraphs after the image." lightbox="media/acquire-to-dispose-acquire-assets.svg":::

The acquire assets business process area flow diagram covers the following steps.

1. Start

2. *Acquire to dispose*

3. *Acquire assets*

    1. *Source assets*

        The following sequences show alternate starting points for this step.

        1. *Procure to Pay* to *Source Assets*

            1. *Procure to Pay*

            2. *Determine preferred and approved vendors*

            3. *Create or process purchase requisition or purchase order*

        2. *Project to profit* to *Source assets*

            1. Project to profit

            2. Project elimination

    2. *Receive assets*

    3. *Register assets* (place assets into service)

    4. *Install assets*

    5. *Define asset maintenance data*

    6. *Define preventive maintenance plan*

    7. *Convert inventory to fixed asset*

        1. Parallel branch from this subprocess is *Inventory to deliver*. The following sequence shows alternate starting points for this step.

            1. *Create asset leases*

            2. *Classify asset leases*

            3. *Determine lease payment schedules*

    8. *Commission asset*

        1. Parallel branch from this subprocess is *Plan to produce*

    9. *Commence on the use of assets and record liabilities*

    10. *Accumulate acquisition costs*

        1. Parallel branch from this subprocess is *Record to report*

4. End

The following end-to-end downstream processes have connections to End: [Inventory to deliver](inventory-to-deliver-overview.md), [Record to report](record-to-report-overview.md), and [Plan to produce](plan-to-produce-overview.md).  

## Acquire assets benefits

The acquire assets business process brings several benefits to an organization contributing to its operational efficiency, financial flexibility, risk mitigation, and overall performance.

The following sections outline the key benefits for an organization through asset acquisition and asset leasing:

### Improved operational efficiency

Acquiring assets that align with operational needs and requirements can significantly enhance efficiency and productivity. Streamlined operations lead to improved output, reduced costs, and increased customer satisfaction. Integration of asset management with other modules of Dynamics 365 brings more benefits. This integration ensures that relevant processes, such as finance, procurement, and inventory management, are seamlessly interconnected. As a result, organizations can automate workflows, eliminate manual data entry, and minimize the risk of errors.

### Improved decision-making

Asset acquisition with well-defined monitoring, tracking, and maintenance provides organizations with access to accurate and real-time data about their asset portfolio. This data enables informed decision-making regarding maintenance, replacements, or upgrades. Timely insights into asset performance, costs, and utilization and synchronized information flow across different departments enhance efficiency, accuracy. The insights help organizations make strategic choices that maximize asset value and contribute to long-term sustainability.

### Improved financial health

Asset acquisition with careful planning can result in significant cost savings and optimized return on investment (ROI) or preservation of capital with leased assets.

### Access to high-end assets

Acquiring or leasing assets strategically by investing in the latest technology, innovative equipment, or industry-specific assets, organizations can differentiate themselves from competitors. This allows businesses to maintain a competitive edge and deliver high-quality products or services to their customers.

> [!NOTE]
> The *acquire assets* business process area flow diagram is described at a high level, and there may be variations in the process flow depending on your operating model and business process requirements.

## Next steps

If you would like to implement Dynamics 365 solutions to assist with your acquire assets business processes, you can use the following resources and steps to learn more. Links are added when articles become available.

1. [Plan and budget assets](acquire-to-dispose-plan-budget-assets-overview.md)  
2. Acquire assets. (The article you're currently reading.)
3. Manage internal assets
4. Manage and report on asset financials
5. [Maintain and repair internal assets](acquire-to-dispose-maintain-repair-internal-asset.md)  
6. Retire and dispose of assets

## Related resources

You can use the following resources to learn more about the *acquire assets* process in Dynamics 365.

- [Asset management overview (Supply Chain Management)](/dynamics365/supply-chain/asset-management/)
- [Create a fixed asset (Finance)](/dynamics365/finance/fixed-assets/tasks/create-fixed-asset)
- [Acquire assets through procurement (Finance) ](/dynamics365/finance/fixed-assets/acquire-assets-procurement)  
- [Acquire fixed assets (Business Central)](/dynamics365/business-central/fa-how-acquire)  
- [Manage fixed assets (Business Central)](/dynamics365/business-central/fa-manage)
- [TechTalk: Asset Management in Dynamics 365 Supply Chain management](https://community.dynamics.com/blogs/post/?postid=d39c8d76-73f1-483a-b386-cbe613704361)

- Find definitions of terminology used in content for *acquire assets* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article, including the following terms:

  - [Asset](glossary.md#asset)  
  - [Asset acquisition strategy](glossary.md#asset-acquisition-strategy)  
  - [Lessor](glossary.md#lessor)  
  - [Lessee](glossary.md#lessee)  
  - [Lease payment schedule](glossary.md#lease-payment-schedule)  
  - [Depreciation](glossary.md#depreciation)  

<!-- ## Tags

*Stakeholders:* Accounts payable, Administrative, Audit, Finance, Human resources, Operations, Purchasing.

*Products:* Dynamics 365 Finance, Dynamics 365 Supply Chain Management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- Sneha Daggubati \| Senior Cloud Solution Architect
