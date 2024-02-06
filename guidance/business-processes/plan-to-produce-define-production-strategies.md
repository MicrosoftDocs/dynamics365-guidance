---
title: Overview of the Define production strategies business process area
description: Learn how you can use Dynamics 365 products to support your organization's business processes for defining production strategies.
ms.date: 01/23/2024
ms.topic: conceptual
author: edupont04
ms.author: annekrupke
---

# Overview of the Define production strategies process area within the Plan to produce process

***Applies to: Dynamics 365 Business Central, Dynamics 365 Human Resources, Dynamics 365 Supply Chain Management***

This article describes the *Define production strategies* business process area within the *Plan to produce* end-to-end process. This process area includes the processes that establish how the organization intends to run, measure, and account for production. By taking the time to map and analyze production processes, the organization can make better decisions based on real data.

This process area should be implemented whenever any other production processes are implemented. For implementations that include Dynamics 365 Finance and Supply Chain Management, production and other supply chain processes are often part of a second phase. Alternatively, all processes are implemented at once.

## Stakeholders 

Many people across the organization should contribute to the decision-making process and design of the *Define production strategies* area. The following list provides examples of such stakeholders:

- **Engineering**: Responsible for designing products and identifying the steps and materials that are required to complete production
- **Human Resources**: Responsible for the workforce/human element of production
- **Operations**: Responsible for managing production
- **Production**: Responsible for running production
- **Warehouse**: Responsible for inventory/material flow in production

## Define production strategies process flow 

The following diagram illustrates the *Define production strategies* business process area. [!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/plan-to-produce-define-prod-strategies.svg" alt-text="Flow diagram for the business process area that is explained in the paragraphs after the image." lightbox="media/plan-to-produce-define-prod-strategies.svg":::

1. Start

    1. A parallel branch from Start includes the *Hire to retire* end-to-end process.

        1. *Plan and recruit your workforce* business process area

            1. *Identify production resources* business process

    1. A parallel branch from Start includes the *Acquire to dispose* end-to-end process.

        1. *Acquire assets* business process area

            1. *Identify production resources* business process

    1. A parallel branch from Start includes the *Product and service lifecycle management* end-to-end process.

        1. *Introduce new products and services* business process area

            1. *Define production process for a product* business process

        1. *Control product engineering changes* business process area

            1. *Define production process for a product* business process

1. *Plan to produce* end-to-end process

    1. A parallel branch from 2. *Plan to produce* includes the *Outsource production operations* business process area.

        1. End (unshown connection)

1. *Define production strategies* business process area
1. *Identify production process* business process

    1. A parallel branch from 4. *Identify production process* includes the *Analyze and improve production processes* business process.

        1. End (connection not shown)

1. *Identify production resources* business process
1. *Define steps to complete production* business process

    1. A parallel branch from 6. *Define steps to complete production* includes the *Define outsourcing requirements* business process.

        1. *Outsource production operations* business process area

1. *Define production process for a product* business process
1. End

> [!NOTE]
> The process of defining materials that production consumes to make a subassembly or finished product is cataloged in the [Design to retire](design-to-retire-overview.md) end-to-end process.

## Define production strategies benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the *Define production strategies* business process area. The following sections outline the key benefits that an organization might monitor and measure for *Define production strategies*. 

### Maximize production flexibility through mixed-mode manufacturing

In Dynamics 365 Supply Chain Management, organizations can model multiple modes of production within the same production site. In this way, they can produce different products through lean, process, or discrete manufacturing, depending on the mode that is the best fit.

### Standardize processes

Organizations can use *routes* to define the standard operating procedures for the production process. They can even attach specific step instructions or pictures to a step, so that operators on the shop floor can easily access them. This approach helps ensure product quality and consistency.

### Visualize and control the cost of production

Functionality for mapping the production process in Dynamics 365 helps businesses understand and accurately capture the cost of production. Therefore, they can make better decisions about purchasing, scheduling, maintenance, and process improvement. Dynamics 365 also includes functionality for defining the cost standards for the production process, and for recording the actual cost of specific production work for variance analysis.

### Maximize production and resource efficiency

Organizations that model their production resources and capacity in Dynamics 365 can create efficient production schedules and, at the same time, respect capacity constraints. They can also use resource certifications and capabilities to ensure that the right resources are selected for the job, regardless of whether those resources are operators or machines. Outsourcing policies can be automated by identifying a vendor as a production resource. Businesses can also report on production operations data to recognize and alleviate bottlenecks in the production process.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *Define production strategies* business processes, you can use the following resources and steps to learn more.

1. [Plan to produce](plan-to-produce-overview.md)
2. *Define production strategies* (the article that you're currently reading)
3. [Plan production operations](plan-to-produce-plan-production-operations-overview.md)
4. [Run production operations overview](plan-to-produce-execute-production-operations-overview.md)
5. [Outsource production operations](plan-to-produce-outsource-production-operations-overview.md)
6. [Control production quality](plan-to-produce-control-production-quality-overview.md)
7. [Track production costs](plan-to-produce-track-production-costs-overview.md)

Return to the overview of business process areas at [Plan to produce business process areas](plan-to-produce-areas.md).

## Related resources

You can use the following resources to learn more about the *Define production strategies* process in Dynamics 365.

- [Mixed mode planning - Combine discrete, process, and lean sourcing - Supply Chain Management](/dynamics365/supply-chain/production-control/mixed-mode-plan)
- [Production setup requirements - Supply Chain Management](/dynamics365/supply-chain/production-control/production-set-up-requirements)
- [Modeling a lean organization - Supply Chain Management](/dynamics365/supply-chain/production-control/lean-manufacturing-modeling-lean-organization)
- [Manufacturing - Business Central](/dynamics365/business-central/production-manage-manufacturing)

<!-- ## Tags

*Industries:* Manufacturing (20-39), Wholesale Trade (50-51), Retail Trade (52-59)

*Stakeholders:* Engineering, Human Resources, Operations, Production, Warehouse

*Products:* Dynamics 365 Business Central, Dynamics 365 Human Resources, Dynamics 365 Supply Chain Management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Anne Krupke](https://www.linkedin.com/in/annekrupke/) | FastTrack Solution Architect

Other contributors:

- [Jesper Livbjerg](https://www.linkedin.com/in/jesper-livbjerg/) | FastTrack Solution Architect

- [Andrew Lencsak](https://www.linkedin.com/in/dynamicsunplugged/) | Director, Solution Delivery
