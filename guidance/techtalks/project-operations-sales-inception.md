---
title: TechTalk Sales and inception with Dynamics 365 Project Operations 
description: Summary of a TechTalk video that talks about sales and inception business processes in Dynamics 365 Project Operations.
ms.date: 11/05/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Sales and inception with Dynamics 365 Project Operations

In today's business landscape, efficient project management is crucial for ensuring seamless operations, particularly in sales and project inception. With Dynamics 365 Project Operations, organizations can manage everything from lead generation to winning contracts, while supporting project-based sales capabilities.  

We based this article on [a TechTalk](https://youtu.be/wZ3z2noYXDQ) that you can find online in the Dynamics 365 channel on YouTube. It focuses on how Dynamics 365 Project Operations handles the sales process, pricing, and costing—key elements that drive successful project management.

:::image type="content" source="media/project-operations-sales-inception-slide.png" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/wZ3z2noYXDQ":::

## Overview

Dynamics 365 Project Operations provides an integrated solution that supports the entire sales and inception process. The system is designed to manage everything from lead generation to opportunity tracking and contract creation, making it a goto solution for organizations working on project-based services. The platform allows businesses to streamline their project sales lifecycle, ensuring smoother transitions between sales and operations.

Project Operations supports multiple deployment options to match your requirements. The following image depicts the architecture of solutions with Dynamics 365 Project Operations.

:::image type="content" source="media/project-operations-sales-inception-architecture.svg" alt-text="Image of a slide with the architecture of Dynamics 365 Project Operations as explained after the image." lightbox="media/project-operations-sales-inception-architecture.svg":::

There are essentially three [types of deployments](/dynamics365/project-operations/environment/determine-deployment-type):

- [Lite deployment–deal to proforma invoicing](/dynamics365/project-operations/environment/determine-deployment-type#lite)  
- [Project Operations for resource/non-stocked scenarios](/dynamics365/project-operations/environment/determine-deployment-type#integrated)  
- [Project Operations for stocked/production order scenarios](/dynamics365/project-operations/environment/determine-deployment-type#pma)  

The diagram breaks the scope into two main areas: *project execution* and *project financials*. The *project execution* area covers scenarios for sales, doing the work that the project is scoped for, managing assigned resources, and time and attendance. These processes are often supported by customer engagement apps that run on Dataverse, which facilitates asynchronous data persistence. The *project financials* area revenue recognition, invoicing, and expense management. This section uses finance and operations apps that use dual-write capabilities to synchronize with Dataverse.  

### Sales process from lead to opportunity

The *lead to opportunity* sales process in Dynamics 365 is a configurable workflow that starts with lead creation. A lead can come from various sources, including call lists, marketing campaigns, or external systems. Once captured, leads are qualified to create opportunities, which are further developed into project quotations.

The *lead to opportunity* process integrates directly with Dynamics 365 Sales. Businesses can manage project-based leads without needing separate licensing for Dynamics 365 Sales, as all sales capabilities are built into Project Operations. This integration simplifies tracking project-based opportunities, allowing businesses to move seamlessly from a qualified lead to a project contract.

For those looking to explore the lead to opportunity process in more detail, Microsoft provides extensive documentation, including an Implementation Guide that outlines best practices and strategies to optimize your deployments.

### Opportunity sales process

Not all organizations start with a lead; some might begin directly with opportunities. In these cases, Dynamics 365 Project Operations offers an opportunity-first sales process. In this workflow, the sales process begins with identifying opportunities, gathering stakeholder information, and capturing sales estimates. These opportunities are then developed into quotations, just like in the lead to opportunity process.

Both lead to opportunity and opportunity-only workflows are highly customizable, allowing businesses to tailor their process stages and mandatory business rules to match their specific requirements.

## Project-based sales

Dynamics 365 Project Operations enables organizations to support sales capabilities from prospecting all the way to contract fulfillment. With Project Operations, users can capture a lead, develop it into an opportunity, and win a contract—all in the same app. Dynamics 365 creates a streamlined process that eliminates the need for other systems or manual interventions. The lead-to-opportunity and opportunity sales processes can be customized with business process flows that ensure no steps are missed.

The following image illustrates the end-to-end process flow.

:::image type="content" source="media/project-operations-sales-inception-process-flow.png" alt-text="The image shows a workflow that starts from sales and opportunity management through to billing and revenue recognition. The flow is segmented into stages from left to right, starting with Sales/Opportunity Management, Contract Management, Project Planning and Resource Management, Vendor/PO Management, Project Delivery Management, Billing and Invoicing, and BI and Reporting." lightbox="media/project-operations-sales-inception-process-flow.png":::

The orange boxes represent steps or deliverables that are typically managed by people on the customer relationship management (CRM) side of the organization, for example by using the Project Operations app. The grey and blue boxes represent work that is typically managed by people from the Finance or Accounts Payable/Accounts Receivable departments. In Dynamics 365, this work can be managed in the Finance or the Supply Chain Management apps, but it can also be managed in the Business Central app.

### Project quotations

Once an opportunity is qualified, the next step is to develop project quotations. Project Operations supports both manual and automated quotations. For example, users can create detailed cost estimates, including resource pricing, expenses, and more. These quotations can be developed based on project estimates, pulling data directly from the project, such as tasks, resources, and expenses.

The quotation process is highly flexible, allowing for detailed customization. For example, billing methods can vary between time-and-materials or fixed-price quotes, depending on the nature of the project. Once the quotation is finalized, it can be sent to the customer and, upon approval, converted into a project contract.

## Pricing and costing

One of the key strengths of Project Operations is its robust pricing and costing capabilities. The platform allows businesses to define complex pricing structures based on several factors, including organizational units, resource categories, and project attributes. The system uses a concept known as *pricing dimensions*. This capability can help businesses create a more granular pricing structure.

### Pricing dimensions

Pricing dimensions in Project Operations are attributes that define both the cost and sales price for a project. Organizations can set these pricing dimensions to match various factors, such as resource categories or organizational units, to ensure accurate pricing. Additionally, pricing in Project Operations can be based on either amount-based pricing or markup percentages, giving users flexibility depending on their business model.

For companies that require advanced pricing models, Dynamics 365 offers the ability to create custom pricing dimensions. These dimensions can include attributes like work location or overtime rates, allowing businesses to tailor their pricing structure to meet specific project needs. Learn more in the [pricing dimensions documentation](/dynamics365/project-operations).

### Price list management

Dynamics 365 Project Operations allows businesses to set up *cost rate* and *build rate* price lists. These price lists can then be applied across multiple projects, ensuring consistent pricing. Additionally, businesses can set up *transfer pricing*, which automatically adjusts based on exchange rates, simplifying the management of cross-border or multi-currency projects.

Once a price list is assigned to an account or project, Project Operations will automatically calculate the correct prices based on the pricing dimensions and associated rates.

## Conclusion

Dynamics 365 Project Operations offers a comprehensive and integrated solution for managing the entire project sales lifecycle, from lead to opportunity and project-based sales. Its advanced pricing and costing features, combined with customizable business process flows, make it a powerful tool for businesses looking to streamline their project operations. Whether your organization starts with a lead or dives directly into opportunity management, Dynamics 365 provides the flexibility and depth needed to manage projects efficiently.

:::image type="content" source="media/project-operations-sales-inception-process-catalog.png" alt-text="Screenshot of a slide with grey boxes for business processes and configurations in the project execution area that are loosely defined after the image." lightbox="media/project-operations-sales-inception-process-catalog.png":::

The business processes require four security roles:

- Account manager
- CSR manager
- Customer service representative
- Project manager

The diagram divides deliverables or tasks into business processes or configurations. Under business processes, it includes steps from project contracts to actuals and project tracking. Configurations cover everything from currency setup to pricing dimensions. Under data management, we list key data entities that relate to project operations, such as project tasks and dependencies. Lastly, a card for integrations lists project schedule APIs and other data-related APIs, emphasizing the interconnected nature of modern project management systems.  

By using the resources available from Microsoft, such as the [Implementation Guide](../implementation-guide/overview.md) and extensive documentation on [pricing dimensions](/dynamics365/project-operations/pricing-costing/pricing-dimensions-overview), businesses can optimize their use of Dynamics 365 Project Operations to drive better project outcomes.

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [Determine your deployment type](/dynamics365/project-operations/environment/determine-deployment-type)  
- [Pricing dimensions overview](/dynamics365/project-operations/pricing-costing/pricing-dimensions-overview)  
- [Project Operations documentation](/dynamics365/project-operations/)  
- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
