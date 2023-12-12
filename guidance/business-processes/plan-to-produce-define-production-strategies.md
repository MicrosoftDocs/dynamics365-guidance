---
title: Define production strategies overview
description: Learn how you can use Dynamics 365 products to support your organization's business processes for defining production strategies.
ms.date: 12/06/2023
ms.topic: conceptual
author: edupont04
ms.author: annekrupke
---

# Define production strategies overview

***Applies to: Dynamics 365 Business Central, Dynamics 365 Human Resources, Dynamics 365 Supply Chain Management***

This article describes the *Define production strategies* business process area within the *Plan to produce* end-to-end process. This process area includes the processes for setting the foundations of how the organization intends to run, measure, and account for production. By taking the time to map and analyze production processes, the organization can make better decisions based on real data.

This process area should be implemented when any other production processes are implemented. For implementations with Dynamics 365 Finance and Supply Chain Management, production and other supply chain processes are often part of a second phase, or all processes are implemented at once.

## Stakeholders 

Many people across the organization should contribute to the decision-making process and design of the *Define production strategies* area. The following list provides examples of such stakeholders:

- **Engineering**: Responsible for designing product and identifying steps and materials to complete production

- **Human Resources**: Responsible for the workforce/human element of production

- **Operations**: Responsible for managing production

- **Production**: Responsible for running production

- **Warehouse**: Responsible for inventory/materials flow in production

## Define production strategies process flow 

The following diagram illustrates the *Define production strategies* business process area. [!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/plan-to-produce-define-prod-strategies.svg" alt-text="Flow diagram for the business process area that is explained in the paragraphs after the image." lightbox="media/plan-to-produce-define-prod-strategies.svg":::

1. Start

    1. A parallel branch from Start includes the *Hire to retire* end-to-end process

        1. *Plan and recruit your workforce* business process area

            1. *Identify production resources* business process

    2. A parallel branch from Start includes the *Acquire to dispose* end-to-end process

        1. *Acquire assets* business process area

            1. *Identify production resources* business process

    3. A parallel branch from Start includes the *Product and service lifecycle management* end-to-end process

        1. *Introduce new products and services* business process area

            1. *Define production process for a product* business process

        2. *Control product engineering changes* business process area

            1. *Define production process for a product* business process

2. *Plan to produce* end-to-end process

    1. A parallel branch from 2. *Plan to produce* includes the *Outsource production operations* business process area

        1. End (unshown connection)

3. *Define production strategies* business process area

4. *Identify production process* business process

    1. A parallel branch from 4. *Identify production process* includes the *Analyze and improve production processes* business process

        1. End (connection not shown)

5. *Identify production resources* business process

6. *Define steps to complete production* business process

    1. A parallel branch from 6. *Define steps to complete production* includes the *Define outsourcing requirements* business process

        1. *Outsource production operations* business process area

7. *Define production process for a product* business process

8. End

> [!NOTE]
> The process of defining materials that production consumes to make a subassembly or finished product is catalogued in the [*Design to retire* end-to-end process](design-to-retire-overview.md).


## Define production strategies benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the *Define production strategies* business process area. The following sections outline the key benefits that an organization might monitor and measure for *Define production strategies*. 

### Maximize production flexibility with mixed-mode manufacturing

With Dynamics 365 Supply Chain Management, organizations can model multiple modes of production within the same production site. This way, they can produce different products with lean, process, or discrete manufacturing, depending on the mode that is the best fit.

### Standardize processes

Organizations can use *routes* to define the standard operating procedures for the production process. They can even attach specific step instructions or pictures to a step for operators to easily access on the shop floor. It helps provide product quality and consistency.

### Visualize and control cost of production

Mapping the production process in Dynamics 365 supports businesses in understanding and capturing the accurate cost of production. They can make better decisions around purchasing, scheduling, maintenance, and process improvement. Dynamics 365 also includes functionality to define the cost standards for the production process, and to record the actual cost of specific production work for variance analysis.

### Maximize production and resource efficiency

Organizations that model their production resources and capacity in Dynamics 365 can create efficient production schedules while respecting capacity constraints. They can also use resource certifications and capabilities to ensure that the right resources are being selected for the job, whether it's an operator or a machine. Outsourcing policies can be automated by identifying a vendor as a production resource. Businesses can also report on production operations data to recognize and alleviate bottlenecks in the production process.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *Define production strategies* business processes, you can use the following resources and steps to learn more.

1. [Plan to produce](plan-to-produce-overview.md)
2. *Define production strategies* (the article that you're currently reading)  
3. [Plan production operations](plan-to-produce-plan-production-operations-overview.md)  
4. Run production operations
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
