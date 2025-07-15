---
title: TechTalk - Sales and inception with Dynamics 365 Project Operations 
description: Get a summary of a TechTalk video about sales and project inception business processes in Dynamics 365 Project Operations.
ms.date: 07/15/2025
ms.topic: concept-article
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk Sales and inception with Dynamics 365 Project Operations

In today's business landscape, efficient project management is crucial for ensuring seamless operations, especially in sales and project inception. Dynamics 365 Project Operations helps organizations manage every phase of project inception, from generating leads to winning contracts. At the same time, it supports project-based sales capabilities.

We based this article on [a TechTalk](https://youtu.be/wZ3z2noYXDQ) that you can find online in the Dynamics 365 channel on YouTube. It focuses on how Dynamics 365 Project Operations handles three key elements that drive successful project management: the sales process, pricing, and costing.

:::image type="content" source="media/project-operations-sales-inception-slide.png" alt-text="Thumbnail of the title slide for the 'Dynamics 365 Project Operations - Sales and Inception' presentation." link="https://youtu.be/wZ3z2noYXDQ":::

## Overview of sales and inception in Dynamics 365 Project Operations

Dynamics 365 Project Operations helps businesses streamline their project sales lifecycle to ensure smoother transitions between sales and operations. It provides an integrated solution that supports the entire sales and inception process. The system is designed to manage everything from lead generation to opportunity tracking and contract creation. These capabilities make it a go-to solution for organizations that work on project-based services.  

Dynamics 365 Project Operations supports multiple deployment options to meet your requirements. There are essentially three [types of deployments](/dynamics365/project-operations/environment/determine-deployment-type):

- [Project Operations Core](/dynamics365/project-operations/environment/determine-deployment-type#lite)  
- [Project Operations Integrated with ERP](/dynamics365/project-operations/environment/determine-deployment-type#integrated)  
- [Project Operations for manufacturing](/dynamics365/project-operations/environment/determine-deployment-type#pma)  

The following diagram shows the architecture of solutions that involve Dynamics 365 Project Operations.

:::image type="content" source="media/project-operations-sales-inception-architecture.svg" alt-text="Diagram that shows the architecture of Dynamics 365 Project Operations." lightbox="media/project-operations-sales-inception-architecture.svg":::

The diagram breaks the scope into two main areas: *project execution* and *project financials*. The *project execution* area covers sales, doing the work that the project is scoped for, management of assigned resources, and time and attendance. These processes are often supported by customer engagement apps that run on Dataverse, which facilitates asynchronous data persistence. The *project financials* area covers revenue recognition, invoicing, and expense management. These processes are supported by Dynamics 365 finance and operations apps that use dual-write capabilities for synchronization with Dataverse.

The business processes require four security roles:

- Account manager
- CSR manager
- Customer service representative
- Project manager

The following diagram outlines the business processes and configurations.

:::image type="content" source="media/project-operations-sales-inception-process-catalog.svg" alt-text="Diagram that shows the business processes and configurations in the project execution area." lightbox="media/project-operations-sales-inception-process-catalog.svg":::

The diagram divides deliverables or tasks into business processes and configurations. Under *Business processes*, it includes steps from project contract setup to actuals and project tracking. Under *Configurations*, it includes everything from currency setup to pricing dimensions.

Also, under *Data management*, the diagram lists key data entities that are related to project operations, such as project tasks and dependencies. Finally, under *Integrations*, it lists project schedule APIs and other data-related APIs to emphasize the interconnected nature of modern project management systems.

### Sales process from lead to opportunity

The *Lead to opportunity* sales process in Dynamics 365 is a configurable workflow that starts with lead creation. A lead can come from various sources, including call lists, marketing campaigns, and external systems. After leads are captured, they are qualified to create opportunities. Opportunities are then further developed into project quotations.

The *Lead to opportunity* process integrates directly with Dynamics 365 Sales. Because all sales capabilities are built into Dynamics 365 Project Operations, businesses can manage project-based leads without needing separate licensing for Dynamics 365 Sales. This integration simplifies tracking of project-based opportunities, so that businesses can move seamlessly from a qualified lead to a project contract.

If you want to explore the lead to opportunity process in more detail, Microsoft provides extensive documentation, including an [Implementation Guide](../implementation-guide/overview.md) that outlines best practices and strategies for optimizing your deployments.

### Opportunity-only sales process

Not all organizations start with leads. Some might begin directly with opportunities. For these organizations, Dynamics 365 Project Operations offers an *Opportunity* sales process. To begin this process, opportunities are identified, stakeholder information is gathered, and sales estimates are captured. The opportunities are then developed into quotations, just as they are in the *Lead to opportunity* process.

The workflow for both the *Lead to opportunity* and *Opportunity* sales processes is highly customizable. Therefore, businesses can tailor their process stages and mandatory business rules to meet their specific requirements.

## Project-based sales

By using Dynamics 365 Project Operations, organizations can support sales capabilities from prospecting all the way to contract fulfillment. In one app, users can capture a lead, develop it into an opportunity, and win a contract. Dynamics 365 creates a streamlined process that eliminates the need for other systems or manual interventions. The *Lead to opportunity* and *Opportunity* sales processes can be customized with business process flows that ensure that no steps are missed.

The following diagram shows the end-to-end process flow.

:::image type="content" source="media/project-operations-sales-inception-process-flow.svg" alt-text="Diagram that shows a workflow that starts from sales and opportunity management, proceeds through contract management, project planning and resource management, vendor and PO management, project delivery management, billing and invoicing, revenue recognition and project accounting, and ends with BI and reporting." lightbox="media/project-operations-sales-inception-process-flow.svg":::

In this workflow, the orange boxes represent work (steps or deliverables) that people on the customer relationship management (CRM) side of the organization typically manage by using the Dynamics 365 Project Operations app, for example. The gray and blue boxes represent work that people from the Finance or Accounts Payable/Accounts Receivable departments typically manage. Although they can use the Dynamics 365 Finance or Dynamics 365 Supply Chain Management apps to manage this work, they can also use the Dynamics 365 Business Central app.

### Project quotations

After an opportunity is qualified, the next step is to develop project quotations. Dynamics 365 Project Operations supports both manual and automated quotations. For example, users can create detailed cost estimates, including resource pricing, expenses, and more. These quotations can be developed based on project estimates, and can pull data such as tasks, resources, and expenses directly from the project.

The quotation process is highly flexible and allows for detailed customization. For example, billing methods can vary between time-and-materials and fixed-price quotations, depending on the nature of the project. After a quotation is finalized, it can be sent to the customer for approval. Finally, after it's approved, it can be converted into a project contract.

## Pricing and costing

One of the key strengths of Dynamics 365 Project Operations is its robust pricing and costing capabilities. Businesses can use the app to define complex pricing structures that are based on several factors, including organizational units, resource categories, and project attributes. For pricing and costing, the system uses a concept that is known as *pricing dimensions*. Pricing dimensions can help businesses create a more granular pricing structure.

### Pricing dimensions

In Dynamics 365 Project Operations, pricing dimensions are attributes that define both the cost and sales price for a project. Organizations can set the pricing dimensions to match various factors, such as resource categories or organizational units, to ensure accurate pricing. Additionally, pricing in Dynamics 365 Project Operations can be based on either amounts or markup percentages. Therefore, users have the flexibility to use the pricing basis that suits their business model.

For companies that require advanced pricing models, Dynamics 365 offers the capability to create custom pricing dimensions. These dimensions can include attributes such as work locations and overtime rates. Therefore, businesses can tailor their pricing structure to specific project needs. Learn more in the [pricing dimensions documentation](/dynamics365/project-operations).

### Price list management

In Dynamics 365 Project Operations, businesses can set up *cost rate* and *build rate* price lists. These price lists can be applied across multiple projects to ensure consistent pricing. Additionally, businesses can set up *transfer pricing*, which automatically adjusts prices based on exchange rates. In this way, it simplifies the management of cross-border or multicurrency projects.

After a price list is assigned to an account or project, Dynamics 365 Project Operations automatically calculates the correct prices based on the pricing dimensions and associated rates.

## Conclusion

Dynamics 365 Project Operations offers a comprehensive and integrated solution for managing the entire project sales lifecycle, from lead to opportunity to project-based sales. Its advanced pricing and costing features, in combination with customizable business process flows, make it a powerful tool for businesses that are looking for ways to streamline their project operations. Regardless of whether your organization starts with leads or dives directly into opportunity management, Dynamics 365 gives it the flexibility and depth that it needs to manage projects efficiently.

By using the resources that are available from Microsoft, such as the [Implementation Guide](../implementation-guide/overview.md) and extensive documentation about [pricing dimensions](/dynamics365/project-operations/pricing-costing/pricing-dimensions-overview), businesses can optimize their use of Dynamics 365 Project Operations to drive better project outcomes.

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [Determine your deployment type](/dynamics365/project-operations/environment/determine-deployment-type)
- [Pricing dimensions overview](/dynamics365/project-operations/pricing-costing/pricing-dimensions-overview)
- [Project Operations documentation](/dynamics365/project-operations/)
- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
