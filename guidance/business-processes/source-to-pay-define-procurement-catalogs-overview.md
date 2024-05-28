---
title: Overview of the define procurement catalogs business process area
description: Read about how Dynamics 365 supports procurement catalogs as part of the procure to pay business process.
ms.date: 07/17/2023
ms.topic: conceptual
author: edupont04
ms.author: raprofit
---

# Overview of the define procurement catalogs business process area

***Applies to: Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center***

This article describes the *define procurement catalogs* business process area. It explains the benefits of using Dynamics 365 to support the business process area.

The business process area *defining procurement catalogs* gives organizations the ability to configure internal catalogs and external catalogs for use in the *source to pay* process. Items and services can be organized and added to catalogs to be used during purchase requisition and purchase order creation. Alternatively, categories outlined within the catalogs can be used at the purchase requisition and purchase order levels where an item or service number doesn't exist. Business users can then indicate details about the purchase without needing the item in master data when appropriate.

The initial procurement catalog structure is usually defined at the start of an implementation project. However, the catalog hierarchy gives you the flexibility to add new categories or modify categories when appropriate to meet your business needs. For example, when you have new product launches, new product lines, or when changes occur and products are phased in or out.

Once the catalogs and categories have been configured for use, restrictions can be put into place ensuring the correct employees have appropriate access to sets of items. This access is controlled by purchasing policies in Dynamics 365 Supply Chain Management.

Organizations can also use procurement catalogs to aggregate transaction data for reporting. Such reports help procurement managers easily identify trends or anomalies in purchase spend at the catalog or category levels. They can then start a deeper investigation.

## Stakeholders

Many people in an organization need to contribute to the design and definition of procurement catalogs. The list includes but isn't limited to the following roles:

- **Procurement stakeholders** - examples: Buyer, Purchasing agent, Purchasing manager, Director of Procurement. The procurement stakeholders are responsible for the overall design of the catalogs and typically work with the suppliers to gather the data required.

- **Operations stakeholders** - examples: Director of Operations, COO, VP of Operations, Operations Manager, Operations analyst. The operations stakeholders are responsible for reporting and analyzing data related to procurement and production. Their input can make sure that the structure of the catalogs, categories, and hierarchies, and so on, meet the operational reporting requirements.

- **IT department stakeholders** – examples: System administrator, Business Analyst, Business Systems Analyst. The IT department stakeholders are responsible for maintaining any integrations and setting up imports of data from suppliers. It's critical to work with these stakeholders to ensure proper handling of data.

- **Finance stakeholders** – examples: Controller, Chief Financial Officer (CFO), Accountant, or Accounting manager. The finance stakeholders are responsible for the financial reporting and mapping of the categories to proper tax categories and ledger accounts for example. It's important to include these stakeholders to ensure proper financial data can be gathered from the resulting transactions.

- **Audit** – examples: Internal auditor, External auditor. The audit stakeholders are responsible for performing audits. Audits may cover security, data handling, financial record keeping, and more. It's important to keep this group of stakeholders involved to ensure that any non-functional audit requirements are met in the design of the solution.

## Define procurement catalogs process flow

:::image type="content" source="media/source-to-pay-define-procurement-catalogs-flow.svg" alt-text="Flow diagram for the business process area, define procurement catalogs, which is explained in the paragraph after the image." lightbox="media/source-to-pay-define-procurement-catalogs-flow.svg":::

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

The following steps are illustrated in the *define procurement catalog* business process flow diagram.

1. Start

    Parallel branches to the *Design to retire* and *Source to pay* end-to-end processes.

2. *Design to retire* subprocesses

    A parallel branch connects *Define product lines* and *Organize products* to 4. *Define procurement catalogs*

3. *Source to pay*

    A parallel branch connects *Create vendors* to 4. *Define procurement catalogs*

4. *Define procurement catalogs*

    1. *Create procurement catalogs*

    2. *Assign products to catalogs*

        Parallel process with 3. *Assign vendors to catalogs* and 4. *Assign employee access to catalogs*

    3. *Assign vendors to catalogs*

        Parallel process with 2. *Assign products to catalogs* and 4. *Assign employee access to catalog*

    4. *Assign employee access to catalogs*

        Parallel process with 2. *Assign products to catalogs* and 3. *Assign vendors to catalogs*

    5. *Configure access to external catalogs*

5. End

## Define procurement catalogs benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the *define procurement catalogs* process. The following sections outline the key benefits that an organization might monitor and measure for within the *define procurement catalogs* process.  

### Ease of managing catalog access rights

Purchasing policies within Dynamics 365 Supply Chain Management can be used to restrict access to certain procurement catalogs or categories. This access can be granted or restricted at the legal entity, operating unit, or even by category for each requester. This helps ensure employees only have access to the catalogs or categories applicable for their position or role.

### Reduction in item management

Procurement catalogs allow for centralized management of items and their associated attributes. Related procurement categories can also be used without an item or product associated. This way, the business users can use the procurement category at the purchase requisition line where details are manually populated for the request. Combine the procurement catalogs with the PunchOut e-procurement process in Dynamics 365 Supply Chain Management. That process is used for access to external vendor catalogs. It also removes the dependency to have all possible items set up in Dynamics 365 before requesting for purchase overall reducing the number of items to manage within your master data.

### Improving spend analysis

When you can organize and group similar items in categories within the procurement catalog, it gives you the ability to analyze trends or other details at the catalog or category level. Dynamics 365 Supply Chain Management has built-in Power BI reporting capabilities so that you can review spend at the procurement category or procurement hierarchy level for year-to-date or year-over-year analysis.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *define procurement catalogs* business processes, use the following resources and steps to learn more. (Links are added, when the articles are ready.)

1. [Manage vendor relationships](source-to-pay-manage-vendor-relationships-overview.md)

2. *Develop sourcing strategies*

3. *Define procurement catalogs* (The article you're currently reading.)

4. *Define policies and procedures for procurement*

5. [Procure materials and services](source-to-pay-procure-materials-services-overview.md)

6. *Process vendor invoices*

7. *Issue and settle vendor payments*

8. *Manage vendor debits and chargebacks*

9. *Create and process promissory notes*

10. *Process vendor rebates and incentives*

11. *Analyze vendor performance*

## Related resources

You can use the following resources to learn more about the *define procurement catalogs* process in Dynamics 365.

- [Procurement catalog overview](/dynamics365/supply-chain/procurement/procurement-catalogs)

- [External catalog for PunchOut e-procurement](/dynamics365/supply-chain/procurement/set-up-external-catalog-for-punchout)

- [Use external catalogs for PunchOut e-procurement](/dynamics365/supply-chain/procurement/use-external-catalogs-for-punchout)

- [Purchasing policies](/dynamics365/supply-chain/procurement/purchase-policies)

- [Set up a procurement category hierarchy](/dynamics365/supply-chain/procurement/tasks/set-up-procurement-category-hierarchy)

- [Create a procurement catalog](/dynamics365/supply-chain/procurement/tasks/create-procurement-catalog)

- [Approve vendors for specific procurement categories](/dynamics365/supply-chain/procurement/tasks/approve-vendors-specific-procurement-categories)

- [Classify a product using category hierarchies](/dynamics365/supply-chain/pim/tasks/classify-product-category-hierarchies)

<!-- ## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Accounts payable, Administrative, Audit, Finance, IT, Operations, Purchasing

*Products:* Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Contributors:

- [Rachel Profitt](https://linkedin.com/in/rachelprofitt) \| Senior Program Manager, FastTrack for Dynamics 365

- [Lindsay Friddle](https://www.linkedin.com/in/lindsay-friddle-a616265/) \| Senior Program Manager, ACE for Dynamics 365
