---
title: Process outbound goods with external service providers
description: Integrate Dynamics 365 Supply Chain Management or Commerce with external service providers for efficient outbound goods processing. Learn to streamline cubing, packing, and shipping workflows with Azure services.
#customer intent: As a distribution company owner, I want to centralize integration between Dynamics 365 and multiple external service providers, so that I can scale operations across different business lines while maintaining data consistency.
author: edupont04
ms.author: edupont
ms.topic: reference-architecture
ms.date: 10/03/2025
---  
# Process outbound goods with Dynamics 365 and external service providers

***Applies to***: ***Dynamics 365 Supply Chain Management, Dynamics 365 Commerce, Azure Logic Apps, Azure Functions, Azure Synapse Link, Azure SQL Database, Microsoft Entra ID***

To build outbound business processes, this solution combines Dynamics 365 Supply Chain Management, Dynamics 365 Commerce, Azure Logic Apps, Azure Functions, Azure Synapse Link, Azure SQL Database, and Microsoft Entra ID. It connects to external applications to properly calculate rating, provide shipment and tracking information, run semi-automated packing processes, and ensure charges are applied correctly on sales orders.

This architecture applies to the distribution and commerce industries that often connect on-premises services with online services. For example, Dynamics 365 online for business management and on-premises solutions for cubing, packing, or shipping.

## Solution overview

In this architecture, sales orders are created in an external online shop solution. The data then goes through the platform for electronic data interchange (EDI) to Dynamics 365 Supply Chain Management. In the original implementation project, we used an EDI service that you can find in Azure App Source and which connects to Dynamics 365 Supply Chain Management and Dynamics 365 Commerce.

To ensure consistency in communication with different platforms, this architecture uses Azure Integration Services and streamlines the following process in communications with the different services online and on-premises:

- The EDI platform ensures that sales orders are received and placed in Dynamics 365 with the correct mode of deliveries that are crucial for the process streamline.
- Dynamics 365 calculates LTL or Parcel during the release to warehouse workflow. Based on delivery terms, Dynamics 365 defines what type of rules to apply and notifies external cubing software to provide correct Carton requirements.
- The Cubing software ensures that the right containers are used in Dynamics 365 and that necessary changes are applied on shipments before processing waves.
- Dynamics 365 notifies the Packing software when work is released, labels can be printed, and packing can progress.
- The Packing software runs the semi-automated packing in the provided boxes with the necessary labels. It also sends a notification when the shipping container can close.
- Dynamics 365 runs the closing of containers and informs the Shipping software that shipments are complete.
- The Shipping software ensures proper rating is applied for the assigned shipment and all tracking details are provided, once ensured, Dynamics 365 Supply Chain Management is triggered with notification to print Packing slip.
- Dynamics 365 Supply Chain Management system informs EDI platform that Packing slip was posted.

This reference architecture can be used for Distribution-Commerce industries when outside Shipment ratings, cubing and automated packing operations are executed. The reference architecture can be defined once the customer identifies they want to stay with external solutions usually during start of implementation.

## Stakeholders

Key stakeholders required for this solution:

- Supply Chain Manager

- Logistics Manager

- Sales manager

- Warehouse manager

- Warehouse worker

- Freight/Transport Coordinator

## Integration architecture

The following diagram illustrates the architecture for the solution.

:::image type="content" source="media/supply-chain-process-outbound-goods-connect-external-services-components.svg" alt-text="Screenshot of the architecture diagram showing the integration of Dynamics 365 Supply Chain Management with external service providers for outbound goods processing." lightbox="media/supply-chain-process-outbound-goods-connect-external-services-components.svg":::

:::image type="content" source="media/supply-chain-process-outbound-goods-connect-external-services-data-flow.svg" alt-text="Screenshot of the architecture diagram illustrating the flow of data between Dynamics 365 and external cubing, packing, and shipping software." lightbox="media/supply-chain-process-outbound-goods-connect-external-services-data-flow.svg":::

[Download a PowerPoint file with this architecture](https://github.com/microsoft/dynamics365patternspractices/blob/main/architectures/dynamics-365-finance-operations-process-outbound-goods-external-service-providers-reference-architecture.pptx).

## Data flow between systems

| # | Name | Source | Target | Information | Description |
|--|--|--|--|--|--|
| 1 | Sales Orders | EDI & Online Shop | Dynamics 365 Supply Chain Management | Sales orders | EDI platform ensures timely received and place Sales orders in Dynamics 365 Supply Chain Management system with correct mode of deliveries that are crucial for the process streamline |
| 2 | Items | Dynamics 365 Supply Chain Management | Cubing software | Release products | Release product information is maintained centralized in Dynamics 365 Supply Chain Management and feeds the information of the Cubing software |
| 3 | Container dimension | Dynamics 365 Supply Chain Management | Cubing software | Container dimension | Centralized approach for maintain container dimensions was picked inside Dynamics 365 Supply Chain Management |
| 4 | Released sales orders | Dynamics 365 Supply Chain Management | Cubing software | Sales order | Released orders from Dynamics 365 are sent to Cubing software for processing |
| 5 | Containers | Cubing software | Dynamics 365 Supply Chain Management | Containers | Containers are automatically created and can be sent to Packing software to be cut. Workers can pick directly into the container |
| 6 | Containers | Dynamics 365 Supply Chain Management | Packing software | Containers | Dynamics 365 Supply Chain Management informs what boxes per order are ready for creation |
| 7 | Label information | Dynamics 365 Supply Chain Management | Packing Software | Label information | Dynamics 365 Supply Chain Management informs what labels can be printed for what orders |
| 8 | Confirmation information | Packing Software | Dynamics 365 Supply Chain Management | Confirmation information | Received information if the Packing was executed correctly or with error messages |
| 9 | Shipment information | Dynamics 365 Supply Chain Management | Shipment software | Shipment information | Upon confirmation of shipment in Dynamics 365 Supply Chain Management initiate parcel ratings through Shipment software |
| 10 | Shipment rating | Shipment software | Dynamics 365 Supply Chain Management | Shipment rating | Once the Parcel rating is successfully completed, initiate and generate the Dynamics 365 Supply Chain Management Packing slip printing and automatically include shipping charges associated with the mode of the delivery in the Dynamics 365 Supply Chain Management Sales order. |
| 11 | Internal collaboration | Outlook / Teams / Sharepoint | Dynamics 365 Supply Chain Management | Emails, Notes, Chat, Calls, Instructions | Internal collaboration of Warehouse/Sales |

## Solution components

The following components are used in reference architecture.

- Dynamics 365 Supply Chain Management manages your Products, Sales Orders, Warehouse, Delivery Terms, Work, Waves, Container closing, Packing slips.

- Azure integration services provide modern RESTful API with backend orchestration and customizable business logic (API Management, Logic apps, Function apps, Application Insights, and other supporting services) to centralize all the inbound and outbound traffic exchange with Dynamics 365 Supply Chain Management.

- Cubing Software manages calculations of container\box sizes that are required for sending goods to the customer.

- Packing Software manages the box-on-demand machine for semi-automatic cutting of the box and printing the labels.

- Shipment Software manages the rating process based on the Dynamics 365 Supply Chain Management shipping information.

- Microsoft Entra ID manages internal user identities.

- Sharepoint Online manages documentation and collaboration.

- Microsoft Outlook and Teams help business communicate.

- Power BI reports data.

## Implementation scenarios

This reference architecture can apply in a scenario where a company wants to keep a legacy application for cubing and packing with specialized rating engines already created in their previous ecosystem.

Using Azure Integration Services in a centralized manner can ensure the clear visibility and alignment of all data flows. It can serve as a communication gateway towards Dynamics 365 Supply Chain Management system to avoid throttling issues and provide central point of view through Azure Application Insight.

For example, a distribution\commerce company has huge volumes of B2B\B2C sales orders that should be organized and prioritized according to transportation mechanism. They use a single instance Dynamics 365 Supply Chain Management approach but have multiple external solutions. The company can easily scale up with the above approach to utilize different external solutions for cubing, rating, or packing station with the exact same data sets feeding principles. Through the different business line growth, this solution supports different B2B or B2C scenarios to have its own external rating, cubing, shipping solution for execution of their daily activities.

### Potential use cases

This solution was created for a distribution organization wanting to provide better management of costs in outbound process through series of specialized external solutions and to remain scalable in future with future business lines investments. It can also be applied to industries like distribution and commerce industries. It can be used by any organization who wants to utilize external planning solutions but maintain the agility of Dynamics 365 Supply Chain Management system with Azure flexibility.

You can use this solution to:

- Centralize your integration strategy

- Provide significant cost savings in the outbound process as shipping carriers evaluate outgoing parcels for each parcel

- Streamline and minimize the cost of transport by calculating container\box sized for each shipment

## Considerations

These considerations help implement a solution that includes Dynamics 365. Learn more at [Dynamics 365 guidance documentation](../index.yml).

### Cost optimization

Cost optimization is about looking at ways to reduce unnecessary expenses and improve operational efficiencies. For more information, see [Overview of the cost optimization pillar](/azure/architecture/framework/cost/overview).

The cost is equivalent to a standard Dynamics 365 implementation project including Azure Integration Services plus the cost of the external API calls to the external applications. These platforms normally offer costs per usage, and it depends on the quantity of data transactions you have with them.

You can find EDI platform software companies on Azure AppSource. This reference architecture is EDI partner agnostic.
<!-- 
## Tags

*Industries:* Wholesale Trade (50-51), Retail Trade (52-59)

*Stakeholders:* Finance, Operations, Sales, Transportation, Warehouse

*Products:* ***Applies to:*** ***Dynamics 365 Supply Chain Management,
Dynamics 365 Commerce, Azure Logic Apps, Azure Functions, Azure Synapse,
Azure SQL Database, Azure Active Directory*** -->

## Contributors

This article is maintained by Microsoft. It was originally written by the following contributors.

Principal author:

- [Andrej Kožić](https://www.linkedin.com/in/andrej-kozic-ifv/) | Dynamics 365 Solution Architect

Other contributors:

- [Branimir Lochert](https://www.linkedin.com/in/branimir-lochert-738a7976/) | Cloud Integration Architect

- [Ryan Tucker](https://www.linkedin.com/in/ryan-tucker-5b1254101/) | Dynamics 365 Senior Consultant
