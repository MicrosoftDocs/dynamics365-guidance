---
title: Overview of the Control production quality business process area
description: Get an overview of the business process area for controlling production quality in the plan to produce end-to-end business process in Dynamics 365 solutions.
ms.date: 12/06/2023
ms.topic: concept-article
author: edupont04
ms.author: annekrupke
---

# Overview of the Control production quality business process area within the Plan to produce end-to-end scenario

***Applies to: Dynamics 365 Finance, Dynamics 365 Human Resources, Dynamics 365 Supply Chain Management***

This article describes the *Control production quality* business process area within the *Plan to produce* end-to-end process. This process area is highly related to the *Manage inventory quality* process area in the *Inventory to deliver* end-to-end process. Controlling production quality covers the processes from inspecting manufactured goods to implementing corrective and preventive actions to improve product quality.

For regulated industries, this business process area should be considered critical. It should be addressed initially and continuously referenced throughout the implementation to ensure compliance. In other organizations, this process area may be implemented alongside the *Run production operations* process area. Also, some companies run production quality processes externally to their systems and onboard to Dynamics 365 at a later date. If an organization has requirements to implement the *control production quality* process area, it's important to identify that as early as possible because it can increase implementation scope. It's also important to recognize that these processes are often executed in "best of breed" specialized systems that are unique by industry. In that case, integrations to such systems may be required as part of the Dynamics 365 implementation.

## Stakeholders 

Many people across the organization should contribute to the decision-making process and design of the *Control production quality* area. The list includes but isn't limited to the following roles:

- **Engineering**: Responsible for product changes based on quality data analysis.

- **Finance**: Responsible for tracking cost of quality.

- **Human resources**: Responsible for managing certifications and skills on production employees, responsible for executing employee corrective and preventive actions (CAPA).

- **IT**: Responsible for ensuring systems support quality audit requirements.

- **Operations or Quality**: Responsible for managing quality inspections and management processes.

- **Production**: Responsible for implementing quality assurance processes within production and for implementing quality improvements.

- **Warehouse**: Responsible for inventory movements related to quality processes.

## Control production quality process flow 

The following diagram illustrates the *control production quality* business process area. [!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/plan-to-produce-control-production-quality-flow.svg" alt-text="Flow diagram for the business process area that is explained in the paragraphs after the image." lightbox="media/plan-to-produce-control-production-quality-flow.svg":::

1. Start

    1. A parallel branch from 1. Start includes the *Plan to produce* end-to-end process.

        1. *Run production operations* business process area

            1. *Control production quality* business process area

2. *Inventory to deliver* end-to-end process.

    1. A parallel branch from 2. *Inventory to deliver* includes the *Scrap defective inventory* business process.

        1. End (this connection isn't shown).

3. *Build a quality plan for a product* business process

4. *Control production quality* business process area

    1. A parallel branch from 4. *Control production quality* includes the *Inspect manufactured goods* business process.

5. *Quarantine manufactured goods* business process

6. *Inspect manufactured goods* business process

    1. A parallel branch from 6. *Inspect manufactured goods* includes the *Record cost of quality* business process.

7. *Record quality test results* business process

8. *Analyze production quality data* business process

    1. A parallel branch from 8. *Analyze production quality data* includes the *Scrap defective inventory* business process.

    2. A parallel branch from 8. *Analyze production quality data* includes the *Report quality nonconformance*.

        1. *Execute corrective and preventive actions* business process

9. *Rework defective inventory* business process

    1. A parallel branch from 9. *Rework defective inventory* includes the *Run production operations* business process area.

        1. End (this connection isn't shown).

10. End

## Control production quality benefits

Many key benefits can be used to monitor and measure the success of implementing technology to support the *Control production quality* process area. The following sections outline the key benefits that an organization might monitor and measure for *Control production quality*. 

### Automate quality processes

In Dynamics 365, businesses can use [quality associations](/dynamics365/supply-chain/inventory/quality-associations) to automatically trigger inspections when business events occur. They can also define [quality tests](/dynamics365/supply-chain/inventory/quality-tests), [test instruments](/dynamics365/supply-chain/inventory/quality-test-instruments), and pass/fail criteria for their [quality management test variables](/dynamics365/supply-chain/inventory/quality-test-variables), so they can run required inspections consistently and correctly. Failed inventory can be automatically quarantined and triaged for more attention to ensure that defective product is well controlled. Learn more at [Quarantine orders](/dynamics365/supply-chain/inventory/quarantine-orders). Dynamics 365 also supports quality audits by providing these details in a structured and searchable format.  

### Increase product traceability

Businesses can use tools such as [batch attributes](/dynamics365/supply-chain/production-control/batch-attributes) in Dynamics 365 to track information from quality inspections against product lots or batches throughout the production and sales process. The Operations and Quality departments can [trace items and raw materials](/dynamics365/supply-chain/inventory/trace-items-raw-materials-inventory-production-sales). This way, they can inquire about where a product came from or what it was used for, and they can find inspection results if an item is recalled, for example. [Batch dispositions](/dynamics365/supply-chain/inventory/batch-disposition-codes) can be used to view on-hand inventory that is in quarantine, off spec, or active for use in production.

### Track issues and enforce corrective and preventive actions

Dynamics 365 includes [case management](/dynamics365/fin-ops-core/fin-ops/organization-administration/cases?context=%2Fdynamics365%2Fcontext%2Fsupply-chain), [nonconformance tracking and reporting](/dynamics365/supply-chain/inventory/tasks/create-process-non-conformance), and corrective and preventive actions. With these capabilities, organizations can make sure that quality issues are identified and addressed in a timely manner.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *Control production quality* business processes, use the following resources and steps to learn more:

1. [Manage inventory quality](inventory-to-deliver-areas.md#manage-inventory-quality)  

2. [Plan to produce](plan-to-produce-overview.md)  

3. [Define production strategies](plan-to-produce-define-production-strategies.md)

4. [Plan production operations](plan-to-produce-plan-production-operations-overview.md)  

5. [Run production operations](plan-to-produce-execute-production-operations-overview.md)  

6. [Outsource production operations](plan-to-produce-outsource-production-operations-overview.md)  

7. *Control production quality* (the article that you're currently reading)      

8. [Track production costs](plan-to-produce-track-production-costs-overview.md)  

Return to the overview of business process areas at [Plan to produce business process areas](plan-to-produce-areas.md).  

## Related information

You can use the following resources to learn more about the *Control production quality* process in Dynamics 365.

- [Quality and nonconformance management overview](/dynamics365/supply-chain/inventory/quality-management-processes)  

- [Inspect the quality of goods](/dynamics365/supply-chain/inventory/tasks/inspect-quality-goods)  

- [Configure and work with quality control and quality management in Dynamics 365 Supply Chain Management (training)](/training/modules/configure-work-quality-control-dyn365-supply-chain-mgmt/)  

<!--## Tags

*Industries:* Manufacturing (20-39), Wholesale Trade (50-51), Retail Trade (52-59)

*Stakeholders:* Engineering, Finance, Human Resources, IT, Operations, Quality, Production, Warehouse

*Products:* Dynamics 365 Finance, Dynamics 365 Human Resources, Dynamics 365 Supply Chain Management-->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Anne Krupke](https://www.linkedin.com/in/annekrupke/) | FastTrack Solution Architect

Other contributors:

- [Jesper Livbjerg](https://www.linkedin.com/in/jesper-livbjerg/) | FastTrack Solution Architect
