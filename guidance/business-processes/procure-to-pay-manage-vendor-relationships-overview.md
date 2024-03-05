---
title: Manage vendor relationships overview
description: Learn how to use Dynamics 365 to support your organization's business processes for managing vendors, including improving vendor performance and reducing procurement costs.
author: Pjagotra
ms.author: pjagotra
ms.topic: conceptual
ms.date: 02/26/2024
ai-usage: ai-assisted
---

# Manage vendor relationships overview

***Applies to: Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management***

This article explains how to use the *manage vendor relationships* business process in Dynamics 365 Commerce, Finance, Project Operations, and Supply Chain Management. This process is part of the *procure to pay* end-to-end process. It helps you find, select, and evaluate vendors for your business needs.

The *manage vendor relationships* business process area is an essential part of the *procure to pay* process in Dynamics 365 Supply Chain Management. Dynamics 365 includes a comprehensive set of capabilities to help you streamline vendor management. You can use it to:

- Search for potential vendors based on product type, location, price, and other criteria.

- Approve qualified vendors and create vendor records with all the relevant information.

- Update vendor records as needed, such as changing bank accounts or payment terms.

- Monitor vendor performance using various metrics, such as delivery time, quality, and compliance.

- Collaborate with vendors through a centralized platform that shows purchase orders, invoices, and consignment stock.

The *manage vendor relationships* business process area helps you optimize your supply chain operations and achieve better business outcomes. You should implement it at the start of your Dynamics 365 Supply Chain Management implementation. It's a foundational process for any organization.

## Stakeholders

The stakeholders in the *manage vendor relationships* business process area are those who manage vendor relationships, identify and select eligible vendors, monitor vendor performance, and maintain communication with vendors. They can include the following roles:

- **Procurement roles** such as buyer, purchasing agent, purchasing manager, and vendor account manager. They're responsible for finding vendors, selecting qualified vendors, approving and creating vendor records in the system, requesting materials or services to be purchased, and managing vendor collaboration.

- **Accounts payable roles** such as accounts payable payment clerk. They're responsible for setting up the payment details for vendors, such as payment terms and method of payment.

- **Operations roles** such as director of operations, COO, VP of operations, operations manager, and operations analyst. They might be responsible for approving vendor selection and creation, and for reporting and analyzing data related to vendor performance and procurement.

- **Finance roles** such as finance controller, CFO, accountant, accounting supervisor, and accounting manager. They might be responsible for updating and approving changes to vendor records, such as mapping vendors to the correct vendor group and tax group.

## Manage vendor relationships process flow

The following diagram illustrates the *manage vendor relationships* business process area. [!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media\procure-to-pay-manage-vendor-relationships-overview.svg" alt-text="Diagram showing the procure to pay business process area, connecting procure to pay to manage vendor relationships." lightbox="media\procure-to-pay-manage-vendor-relationships-overview.svg":::

The process has these steps:

- Start

- *Procure to pay* end-to-end process

- *Manage vendor relationships* business process area

  - Is it a new vendor?

    - *Yes* leads to *Identify prospective vendor*

    - *No* leads to *Manage and update vendor*

  - *Identify prospective vendor* business process: Search for and choose vendors that meet your criteria.

  - *Create vendor* business process: Approve and create a vendor record in the system for the selected vendor.

  - *Manage and update vendor* business process: Make changes to the vendor record as needed, such as changing bank accounts or payment terms.

- *Procure material and service* business process area

- *Receive material and service* business process area

- *Process vendor invoice* business process area

- *Issue and settle vendor payments* business process area

- *Evaluate vendor performance* business process: Use the data from the previous steps to assess how well the vendor meets your expectations. This helps you make better decisions for future procurement and align your interests with the vendor.

- End

### Benefits

The *manage vendor relationships* business process area can help you:

- **Reduce costs** by improving efficiency, accuracy, and transparency in your procurement activities. You can shorten processing times, negotiate better prices with vendors, and lower accounting expenses. You can also get better terms and conditions, service levels, and discounts from vendors who value your relationship.

- **Improve planning** by gaining insights into your vendors' operations, such as lead times, production capacity, and potential bottlenecks. You can use this information to plan your inventory management and production scheduling. You can also respond more effectively to unexpected situations, such as a surge in demand or a disruption in the supply chain.

- **Streamline procurement** by having a centralized view of all your purchasing activities. You can monitor them in real-time, identify bottlenecks, and make data-driven decisions.

- **Enhance vendor relationships** by communicating effectively with your vendors. You can keep them updated about your changing needs and situations. They're more likely to keep you informed about theirs. They're also more likely to be responsive to your requests, both expected and unexpected. You can use the **Vendor Collaboration** module in Dynamics 365 Supply Chain Management to share information about purchase orders, invoices, and consignment stock with external vendors.

- **Reduce risks** by working closely with your vendors. They're more likely to be transparent about their own risks and proactive in implementing risk mitigation strategies. They're also more likely to meet their contractual obligations, reducing the risk of delays or quality issues.

- **Evaluate vendor performance and compliance** by using a consistent and methodical approach to assess your vendors. You can use the vendor evaluation functionality in Dynamics 365 Supply Chain Management to manually evaluate vendors based on various criteria. You can also use Key Performance Indicators (KPIs) to develop strategies for increasing sales, reducing inefficiencies, and increasing revenue. Additionally, you can ensure adherence to procurement policies, minimize the likelihood of fraudulent or corrupt activities, and maintain a record for regulatory compliance purposes.

## Next steps

If you want to implement Dynamics 365 solutions to support your *manage vendor relationships* business processes, use these resources and steps to learn more.

- Manage vendor relationships (the article that you're reading)

- Develop a sourcing strategy

- [Define a procurement catalog](procure-to-pay-define-procurement-catalogs-overview.md)

- Define policies and procedures for procurement

- Procure materials and services

- Receive materials and services

- [Process vendor invoices](procure-to-pay-process-vendor-invoices-overview.md)  

- [Issue and settle vendor payments](design-to-retire-issue-and-settle-vendor-payments-overview.md)  

- Manage vendor debits and chargebacks

- Create and process promissory notes

- [Process vendor rebates and incentives](procure-to-pay-process-vendor-rebates-incentives-overview.md)  

- Analyze vendor performance

## Related resources

You can use the following resources to learn more about the *manage vendor relationships* process in Dynamics 365.

- [Set up vendor accounts - Supply Chain Management](/dynamics365/supply-chain/procurement/set-up-vendor-accounts)

- [Create vendors - Training](/training/modules/configure-accounts-payable-dyn365-finance/8-create-vendors)

- [Set up and maintain vendor collaboration - Supply Chain Management](/dynamics365/supply-chain/procurement/set-up-maintain-vendor-collaboration)

- [Configure and manage vendor collaboration in Dynamics 365 Supply Chain Management](/training/modules/configure-manage-vendor-collaboration-dyn365-supply-chain-mgmt/)

- [Evaluate a vendor and put a vendor on hold - Training](/training/modules/configure-perform-procure-purchase-dyn365-supply-chain-mgmt/5-put-on-hold?ns-enrollment-type=learningpath&ns-enrollment-id=learn-dynamics.configure-manage-procurement-vendors-d365-finance-ops)

- [Supply risk assessment overview - Supply Chain Management](/dynamics365/supply-chain/procurement/supply-risk-assessment-overview)

- [Power BI reports for risks analysis and performance ranking - Supply Chain Management](/dynamics365/supply-chain/procurement/supply-risk-assessment-reports)

- Find definitions of terminology used in content for *run production operations* in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article, including the following terms:
  - [Vendor](glossary.md#vendor)
  - [Vendor account number](glossary.md#vendor-account-number)
  - [Vendor bank accounts](glossary.md#vendor-bank-accounts)
  - [Vendor collaboration portal](glossary.md#vendor-collaboration-portal)

<!---## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Accounts payable, Administrative, Audit, Finance, Production, Project Management, Purchasing, Service operations, Warehouse

*Products:* Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center --->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [**Praveen Jagotra**](https://www.linkedin.com/in/praveen-jagotra/) \| Senior Solutions Architect, FastTrack for Dynamics 365

Other contributors:

- **Adi Vijayashankar** \| Senior Solutions Architect, FastTrack for Dynamics 365
