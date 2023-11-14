---
title: Procure to pay end-to-end overview
description: Learn about the end-to-end business process, from procure to pay. This article provides a high-level flow diagram and describes the relationship with other processes in Dynamics 365 solutions.
ms.date: 07/17/2023
ms.topic: conceptual
author: edupont04
ms.author: raprofit
---

# Procure to pay end-to-end overview

***Applies to: Dynamics 365 Commerce, Dynamics 365 Customer Voice, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center***

This article describes the *procure to pay* end-to-end business process flow and its relationship to other business processes that can be used within Dynamics 365.

## Procure to pay process relationship

The following diagram shows the relationship of other processes for the *procure to pay* process.

:::image type="content" source="media/procure-to-pay-process.png" alt-text="forecast to plan process relationship diagram." lightbox="media/procure-to-pay-process.png":::

The upstream process for the *procure to pay* processes are:

- **Forecast to plan**  

  Supply and demand forecasts will be included during the *plan supply* subprocess before procuring materials and services to meet your internal and external customer needs.

- **Order to cash**  

  The *Demand from sales orders* subprocess will be used during the *plan supply* subprocess to procure the requested materials or services. Tt could also include related components of an ordered finished good being produced.

- **Product and service lifecycle management**  

  This end-to-end process is a mandatory prerequisite before you can procure materials and services for your organization. It must be completed before you step into the *procure to pay* process.

- **Project to profit**  

  Materials and services included to support an ongoing project will be included in the *plan supply* subprocess.

- **Prospect to quote**  

  Materials and services requested during the quotation process will be used during the supply planning process to procure the requested products or services.

The second column in the diagram displays the following business processes areas:

- *Manage vendor relationships*

- *Develop sourcing strategies*

- *Define procurement catalogs*

- *Define policies and procedures for procurement*

- *Plan supply*

- *Procure materials and services*

- *Process vendor invoices*

- *Issue and settle vendor payments*

- *Manage vendor debits and chargebacks*

- *Create and process promissory notes*

- *Process vendor rebates and incentives*

- *Analyze vendor performance*

Learn more at [Procure to pay business process areas](procure-to-pay-areas.md).

The third column in the diagram displays the downstream business process including the following list:

- **Acquire to dispose**  

  Purchased assets will be tracked within the *acquire to dispose* business process.

- **Case to resolution**  

  The *case to resolution* process may be used to track and report issues with materials, services, or vendors for corrective actions while implementing continuous improvements.

- **Forecast to plan**  

  Material forecasts will be used during the *forecast to plan* business process to ensure needed materials are purchased to support supply and demand needs. Once the plan is reviewed, the materials will be purchased based on the inventory quantities requested.

- **Inventory to deliver**  

  Once materials are purchased, the materials will be managed in the *inventory to deliver* business process that will include the receiving and material movements processes.

- **Order to cash**

  Materials and services will be planned and purchased to fulfill orders that have arrived within the *order to cash* business process. It would include orders where materials are shipped directly from the vendor to the end customer.

- **Plan to produce**  

  Materials purchased will be used during the *plan to produce* business process when producing finished goods. It may also include materials and services purchased during the subcontracting or contract manufacturing processes when an outside vendor is used in the production process.

- **Project to profit**  

  Purchased materials and services to support ongoing projects will be used within the *project to profit* business process.

- **Record to report**

  After the materials and services are purchased, the *record to report* business process will be used to record any invoices, vendor debits and chargeback, and vendor payments.

- **Service to cash**  

  To support the *service to cash* business process, materials or services may need to be purchased to support internal and external activities such as maintenance, installation, or warranty services.

### Featured capabilities

There are product-specific capabilities that interact with the *procure to pay* processing including, but not limited to:

- **Vendor collaboration**  

  This optional module in Dynamics 365 provides a portal to interact with vendors on purchase orders, RFQ (request for quotes), consignment inventory, invoices, and other master data. The option is available if EDI (Electronic data interchange) isn't used for procurement.

- **Vendor onboarding**  

  Vendors can request to onboard through a customer-hosted site that allows anonymous access. The vendor fills in request information that is then imported as a prospective vendor request in Dynamics 365 Supply Chain Management for review. Out-of-the-box workflows allow the customer to control the vendors that are approved for onboarding and created within the vendor master. Once the vendor is created in Dynamics 365, the vendor can be set up to use the vendor collaboration portal as mentioned above.

- **Microsoft Supply Chain Center**  

  You can synchronize your data from first party applications or third-party applications to the Dataverse to use advanced analytics capabilities for monitoring your supply chain.

- **Purchasing policies**  

  Purchasing policies allow your organization to have a set of rules around the requisition and purchasing processes while using the built-in workflow capabilities.

- **Quality management**  

  This capability in Dynamics 365 Supply Chain Management provides a framework to capture nonconforming materials through product test. Users can set the timing for when to generate a quality order for testing before materials are released for consumption. With the gathered data surrounding the item sampling or tests completed, results can assist with corrective action, should it be needed.

- **Dynamics 365 Finance Invoice Capture**  

  This solution can automatically create vendor invoices using OCR to translate the received vendor invoice into an electronic document for processing. It's helpful in improving accuracy and processing times while reducing manual intervention.

- **Advanced warehouse management (mobile device)**  

  During the *materials receipt* process in the *Inventory to deliver* end-to-end scenario, you can use warehouse management processes to automate and simplify the inventory processes on the warehouse floor with mobile devices.  

## Procure to pay business process flow

The following diagram shows the high-level flow of the *procure to pay* business process. Each solid rectangle on the diagram represents an end-to-end business process area. The sub-processes shown in the diagram are shown for the procure to pay* business process. The arrows on the diagram show the flow of the business process in an organization. If a sub-process can lead to more than one other sub-process, the parallel sub-processes are shown as branches.

:::image type="content" source="media/procure-to-pay-flow.png" alt-text="Flow diagram for the end-to-end business process, procure to pay, which is explained in the paragraph after the image." lightbox="media/procure-to-pay-flow.png":::

The following steps are illustrated in the *procure to pay* end-to-end business process flow diagram.

1. Start

2. *Procure to pay* end-to-end process

    Parallel subprocesses include the following processes:

    1. *Manage vendor relationships*

    2. *Develop sourcing strategies*

    3. *Define procurement catalogs*

    4. *Define policies and procedures for procurement*

        Parallel subprocesses:

          1. *Manage vendor relationships*  
          2. *Develop sourcing strategies*  
          3. *Define procurement policies*  

        The *Define policies and procedures for procurement* subprocess also connects to the subprocess *Plan supply*

    5. *Plan supply*

        Parallel branches from this subprocess:  

          1. *Procure materials and services*
          2. *Analyze vendor performance* and *Forecast to plan*.

        Learn more about *Plan supply* as part of the *forecast to plan* end-to-end business process at [Plan supply and replenishment overview](forecast-to-plan-supply-replenishment-overview.md).  

    6. *Procure materials and services*  

        Parallel branches from this subprocess:

        1.*Acquire to dispose*
        2. *Plan to produce*  with a downstream process to *Inventory to deliver*  
        3. *Inventory to deliver*  with a downstream process to *Order to cash*  
        4. *Order to cash*  
        5. *Forecast to plan*  
        6. *Service to cash*  
        7. *Project to profit*.  

        > [!NOTE]
        > The direct delivery process (the purchase order is created from the sales order and goods are delivered to customer straight from vendor) is not outlined in this diagram.

    7. *Process vendor invoices*

        Parallel branches from this subprocess are *Analyze vendor performance* and *Record to report*. This subprocess also connects to the following parallel subprocesses:

        1. *Create promissory notes*  
        2. *Process vendor rebates and incentives*  
        3. *Manage vendor debits and chargebacks*  

    8. *Analyze vendor performance* connects to the following subprocesses:

        1. *Plan supply*  
        2. *Process vendor invoices*  
        3. *Manage vendor debits and chargebacks*  

    9. *Create and process promissory notes*

    10. *Process vendor rebates and incentives*

    11. *Manage vendor debits and chargebacks*

        Parallel branches to this subprocess include the following list:

        1. *Analyze vendor performance*  
        2. *Record to report*  
        3. *Case to resolution*  

    12. *Issue and settle vendor payments*

        Parallel subprocesses:  

        1. *Create and process promissory notes*  
        2. *Process vendor rebates and incentives*  
        3. *Manage vendor debits and chargebacks*, which connects to the subprocess *Issue and settle vendor payments*

    Parallel branches from Start include the following list:

3. *Product and service lifecycle management* connects to *Define procurement catalogs*

4. *Prospect to quote* connects to *Plan supply*

5. *Order to cash* connects to *Plan supply*

6. *Forecast to plan* connects to *Plan supply*

7. *Project to profit* connects to *Plan supply*  

8. End  

The following end-to-end downstream processes have connections to End:  

- *Acquire to dispose*  
- *Plan to produce*  
- *Inventory to deliver*  
- *Order to cash*  
- *Forecast to plan*  
- *Service to cash*  
- *Project to profit*  
- *Record to report*  
- *Case to resolution*  

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *procure to pay* business processes, use the following resources and steps to learn more.

- Define the goals and objectives of implementing a *procure to pay* technology solution. Learn more at [Implementation strategy](../implementation-guide/implementation-strategy.md).  

- Define the business process scope of your project. Learn more at [Process-focused solution](../implementation-guide/process-focused-solution.md).  

- Request a demo or get a free trial of Dynamics 365 solutions for the *procure to pay* process. Learn more at [Request a demo](https://dynamics.microsoft.com/dynamics-365-free-trial/).

- [Procure to pay business process areas](procure-to-pay-areas.md)  
- [Plan supply and replenishment overview](forecast-to-plan-supply-replenishment-overview.md)  

## Related resources

Use the following resources to learn more about the *procure to pay* process in Dynamics 365.

- [Procurement and sourcing overview](/dynamics365/supply-chain/procurement/procurement-sourcing-overview)  

- [Procurement and sourcing home page](/dynamics365/supply-chain/procurement/procurement-sourcing)  

<!--## Tags

*Stakeholders:* Functional consultant, Buyer, Director of Procurement, Purchasing agent, Purchasing manager, Accounts payable clerk, Accounts payable manager, System administrator, Business Analyst, Director of IT, Business Systems Analyst, Controller, CFO, Accountant, or Accounting manager, Internal auditors, External auditors

*Products:* Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management, Microsoft Supply Chain Center-->
