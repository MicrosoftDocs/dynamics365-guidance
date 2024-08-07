---
title: Create and process service work overview
description: Learn how you can use Dynamics 365 products to support your organization's business processes for creating and processing work related to services.
ms.date: 02/21/2024
ms.topic: conceptual
author: edupont04
ms.author: dehardy
---

# Create and process service work overview

***Applies to: Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Supply Chain Management***

This article describes how you can use Dynamics 365 products to support your organization's business processes for creating and processing service work.

It describes the *Create and process service work* process area within the *Service to cash* end-to-end process. This area encompasses the primary business processes related to preparing for and performing the service work within your service operations.

Processes within this area can vary widely by organization based on industries, business models, and unique requirements, but often they follow a similar high-level lifecycle that includes receiving service requests, scheduling service resources, conducting the service activities, and closing the service request before handing it off to other downstream process areas such as invoicing and payment collection.

Given the variety, and often the complexity, of this process area, it's critical that you dedicate the appropriate number of resources and time in the initial stages of your implementation project to thoroughly document the processes, steps, and patterns needed to meet your organization's unique requirements.

## Stakeholders 

Many people across the organization should contribute to the decision-making process and design of the *Create and process service work* area. The following list provides examples of such stakeholders:

- **Operations** – Examples: COO 

- **Field service** – Examples: service managers, field supervisors, dispatchers, frontline workers

- **Customer service** – Examples: call center manager

- **Finance** – Examples: CFO, controller

## Create and process service work process flow 

The following diagram illustrates the high-level process flow for *Creating and processing service work*.

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/service-to-cash-create-process-service-work-flow.svg" alt-text="Flow diagram for the business process area, which is explained in the paragraphs after the image." lightbox="media/service-to-cash-create-process-service-work-flow.svg":::

### Create and process service work

The flow diagram for the create and process service work business process area covers the following steps.

1. Start

2. *Service to cash*

    1. *Manage customer owned assets*

       A parallel branch from this subprocess is *Hire to retire* with the subprocess *Manage service resources* that leads to *Create and process service work*.

3. *Create and process service work*

    1. *Create service requests*

    2. *Schedule service work*

    3. *Perform service work*

    4. *Review and close service requests*

4. *Invoice customers*

5. *Record customer payments*

6. *Monitor customer credit and collections*

7. *Order to cash*

8. End

### Create and process service work benefits

Many key benefits can be used to monitor and measure the success of implementing technology to support the creation and processing of work orders. The following sections outline the key benefits that an organization might monitor and measure related to the *Create and process service work* process area.

####  Improved customer satisfaction

Improving customer satisfaction is the most important benefit to strive for. Using Dynamics 365 Field Service and Dynamics 365 Supply Chain Management, you can focus on improving customer satisfaction and retention by delivering high-quality services on time and within budget.

####  Increased operational efficiency

Increasing operational efficiency and productivity by reducing manual tasks, errors, and rework is one of the most important objectives for many customers when implementing new processes and systems within their organization.

#### Enhanced visibility

Enhance visibility and control over the service delivery lifecycle by tracking and managing work orders from initiation to completion.

#### Optimized resource use

Optimize resource use and allocation by matching the right skills and availability to the demand.

#### Accelerated cash flow

Accelerate cash flow and revenue recognition by invoicing customers accurately and promptly.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *Create and process service work* business processes, use the following resources and steps to learn more. (Links are added, when the articles are ready.)

1. [Manage service assets](service-to-cash-manage-service-assets.md)  

2. *Manage service resources*

3. *Create and process service work* (The article that you're currently reading)

4. [Invoice customers overview](order-to-cash-invoice-sales-orders-overview.md)

5. *Record customer payments*

6. [Monitor customer credit and collections](order-to-cash-monitor-customer-credit-collections-overview.md)

## Related information

You can use the following resources to learn more about the *Create and process service work* process in Dynamics 365.

- [Dynamics 365 Field Service Product information](https://www.microsoft.com/dynamics-365/products/field-service)
- [Dynamics 365 Field Service Documentation](/dynamics365/field-service/finance-operations-integration)
- [Dynamics 365 Field Service Learning Paths](/training/browse/?expanded=dynamics-365&products=dynamics-field-service&resource_type=learning%20path)
- [Dynamics 365 Field Service Community Forum](https://community.dynamics.com/365/fieldservice/f/dynamics-365-for-field-service-forum)
- [Dynamics 365 Field Service Blog Posts](https://cloudblogs.microsoft.com/dynamics365/it/product/dynamics-365-field-service/?sort-by=newest-oldest&date=any&s=)
- [Dynamics 365 Field Service Functional Consultant Certification](/credentials/certifications/exams/mb-240/)
- Find definitions of terminology that is used in content for *Create and process service work* process area in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article. For example, this glossary includes the following terms:

    - [Work order](glossary.md#work-order)
    - [Service customer](glossary.md#service-customer)
    - [Service location](glossary.md#service-location)
    - [Service resource](glossary.md#service-resource)
    - [Scheduling parameters](glossary.md#scheduling-parameters)
    - [Assets](glossary.md#asset)

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Dean Hardy](https://www.linkedin.com/in/deanhardy/) | Dynamics 365 FastTrack Solution Architect


