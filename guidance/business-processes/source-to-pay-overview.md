---
title: Source to pay end-to-end overview
description: Learn about the end-to-end business process, source to pay. Get a flow diagram that describes the relationship with other processes in Dynamics 365 solutions.
author: AdiVijayashankar
ms.author: advijaya
ms.topic: conceptual
ms.date: 12/03/2024
---

# Source to pay end-to-end overview

***Applies to: Dynamics 365 Commerce, Dynamics 365 Customer Voice, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center***

This article describes the *Source to pay* end-to-end business process flow and its relationship to other business processes that can be used within Dynamics 365.

> [!NOTE]
> We're in process of updating the article based on the November 2024 version of the business process catalog.

## Source to pay process relationship

The following diagram shows the relationship of other processes for the *Source to pay* process.

:::image type="content" source="media/source-to-pay-process.svg" alt-text="Business process relationships with upstream and downstream processes that are explained in the next paragraphs." lightbox="media/source-to-pay-process.svg":::

The upstream process for the *Source to pay* processes are:

- **Concept to market**  

  This end-to-end process, which covers the process of creating services, is required to determine which services should be procured in the procure to pay process by the organization.

- **Design to retire**  

  This end-to-end process, which covers the process of creating new tangible products, is required to determine which products should be procured in the *Source to pay* process by the organization.

- **Forecast to plan**  

  Organizations need to create a supply plan in Dynamics 365 supply chain management to procure materials and services to meet the internal and external customer needs.

- **Order to cash**  

  Demand from sales orders are used by the supply plan to procure the requested materials or services. This could also include related components of an ordered finished good being produced. Additionally, in a direct delivery sales model, the sales order can trigger the creation of a purchase order with the supplier.

- **Project to profit**  

  Materials and services included to support an ongoing project will require a procurement process to be initiated by the *Source to pay* process.

- **Acquire to dispose**  

  Many assets require procurement of materials and/or services to create an asset that is usable in the organization.

- **Plan to produce:**  

  Organizations need to procure materials for use in production before the production process begins. Procurement of materials and services are required during the subcontracting or contract manufacturing processes when an outside vendor is used in the production process.

- **Service to cash**  

  Organizations need to procure materials or services to support internal and external activities such as maintenance, installation, or warranty services.

The *Source to pay* end-to-end process is broken down into the following component business process areas:

- *Develop procurement and sourcing strategies*

- *Define procurement catalogs*

- *Manage vendor relationships*

- *Procure materials and services*

- *Process vendor invoices*

- *Issue and settle vendor payments*

- *Process vendor rebates and incentives*

Learn more at [Source to pay business process areas](source-to-pay-areas.md).

The following list displays the downstream business processes:

- **Forecast to plan**  

  Material forecasts are used during the *forecast to plan* business process to ensure needed materials are purchased to support supply and demand needs. Once the plan is reviewed, the materials are purchased based on the inventory quantities requested.

- **Order to cash**  

  Materials and services are planned and purchased to fulfill orders that arrive within the *order to cash* business process. It would include orders where materials are shipped directly from the vendor to the end customer.

- **Project to profit**  

  Purchased materials and services to support ongoing projects will be used within the *project to profit* business process.

- **Acquire to dispose**  

  Purchased assets are tracked within the acquire to dispose business process.

- **Plan to produce**  

  Materials purchased are used during the *plan to produce* business process when producing finished goods. It may also include materials and services purchased during the subcontracting or contract manufacturing processes when an outside vendor is used in the production process.

- **Service to cash**  

  To support the *service to cash* business process, purchased materials or services support internal and external activities such as maintenance, installation, or warranty services.

- **Inventory to deliver**  

  Once materials are purchased, the materials are managed in the *inventory to deliver* business process that include the receiving and material movements processes.

- **Record to report**  

  After the materials and services are purchased, the *record to report* business process will be used to record any invoices, vendor debits and chargeback, and vendor payments.

### Featured capabilities

There are product-specific capabilities that interact with the *Source to pay* processing including, but not limited to:

- **Vendor collaboration**  

  This optional module in Dynamics 365 provides a portal to interact with vendors on purchase orders, RFQ (request for quotes), consignment inventory, invoices, and other main data. The option is available if EDI (Electronic data interchange) isn't used for procurement.

- **Vendor onboarding**  

  Vendors can request to onboard through a customer-hosted site that allows anonymous access. The vendor fills in request information that is then imported as a prospective vendor request in Dynamics 365 Supply Chain Management for review. Out-of-the-box workflows allow the customer to control the vendors that are approved for onboarding and created within the vendor master. Once the vendor is created in Dynamics 365, the vendor can be set up to use the vendor collaboration portal as mentioned above.

- **Microsoft Supply Chain Center**  

  You can synchronize your data from first party applications or third-party applications to the Dataverse to use advanced analytics capabilities for monitoring your supply chain.

- **Purchasing policies**  

  Purchasing policies allow your organization to have a set of rules around the requisition and purchasing processes while using the built-in workflow capabilities.

- **Quality management**  

  Dynamics 365 Supply Chain Management provides a framework to capture nonconforming materials through product testing. Users can set the timing for when to generate a quality order for testing before materials are released for consumption. With the gathered data surrounding the item sampling or tests completed, results can assist with corrective action, should it be needed.

- **Dynamics 365 Finance Invoice Capture**  

  This solution can automatically create vendor invoices using OCR to translate the received vendor invoice into an electronic document for processing. It's helpful in improving accuracy and processing times while reducing manual intervention.

- **Advanced warehouse management (mobile device)**  

  During the materials receipt process in the Inventory to deliver end-to-end scenario, you can use warehouse management processes to automate and simplify the inventory processes on the warehouse floor with mobile devices.

## Source to pay business process flow

The following diagram shows the high-level flow of the *Source to pay* business process. [!INCLUDE [daf-business-process-e2e-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-e2e-flow-def.md)]

:::image type="content" source="media\source-to-pay-flow.svg" alt-text="Diagram of the source to pay business process area map, showing the connections between various business processes." lightbox="media\source-to-pay-flow.svg":::

The following steps are illustrated in the *Source to pay* end-to-end business process flow diagram.

1. Start

2. *Source to pay* end-to-end process

    1. Parallel subprocesses include the following:

        1. *Define procurement catalogs*

        2. *Define procurement and sourcing strategy*

        3. *Manage vendor relationships*

    2. Procure materials and services

       Parallel branches from this subprocess are *acquire to dispose*, *plan to produce*, *order to cash*, *forecast to plan*, *service to cash*, and *project to profit*

3. *Receive item/service required?*

    1. If yes, then connect to *inventory to deliver*

    2. If no, then connect to *process vendor invoice*

4. *Process vendor invoices*

    Parallel branch from this subprocess is *record to report*.

5. *Issues and settle vendor payments*

    Parallel branch from this subprocess is *record to report*.

6. *Process vendor rebates and incentives*

    Parallel branch from this subprocess is *record to report*.

7. End

Parallel branches from Start include the following list:

- *Concept to market* connects to *Define procurement catalogs*

- *Design to retire* connects to *Define procurement catalogs*

- *Forecast to plan* connects to *Procure materials and services*

- *Order to cash* connects to *Procure materials and services*

- *Project to profit* connects to *Procure materials and services*

- *Acquire to dispose* connects to *Procure materials and services*

- *Plan to product* connects to *Procure materials and services*

- *Service to cash* connects to *Procure materials and services*

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *Source to pay* business processes, use the following resources and steps to learn more.

1. Define the goals and objectives of implementing a *Source to pay* technology solution. Learn more at [Implementation strategy](../implementation-guide/implementation-strategy.md).

2. Define the business process scope of your project. Learn more at [Process-focused solution](../implementation-guide/process-focused-solution.md).

3. Request a demo or get a free trial of Dynamics 365 solutions for the *Source to pay* process. Learn more at [Request a demo](https://dynamics.microsoft.com/dynamics-365-free-trial/).

4. [Source to pay business process areas](source-to-pay-areas.md)

## Related information

You can use the following resources to learn more about the *Source to pay* process in Dynamics 365.

- [Procurement and sourcing overview](/dynamics365/supply-chain/procurement/procurement-sourcing-overview) 

- [Procurement and sourcing home page](/dynamics365/supply-chain/procurement/procurement-sourcing) 

<!--## Tags

*Stakeholders:* Functional consultant, Buyer, Director of Procurement, Purchasing agent, Purchasing manager, Accounts payable clerk, Accounts payable manager, System administrator, Business Analyst, Director of IT, Business Systems Analyst, Controller, CFO, Accountant, or Accounting manager, Internal auditors, External auditors

*Products:* Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center -->
