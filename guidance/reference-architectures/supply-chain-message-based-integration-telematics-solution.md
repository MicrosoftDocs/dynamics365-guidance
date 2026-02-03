---
title: Message Based Integration of Dynamics 365 and Telematics
description: Connect Dynamics 365 Supply Chain Management with telematics solutions using Azure Service Bus and Storage Account for seamless warehouse-to-delivery integration.
#customer intent: As an implementor, I want to learn how I can connect Supply Chain Management with a telematics solution.
author: edupont04
ms.author: edupont
ms.reviewer: edupont
ms.date: 02/03/2026
ms.topic: reference-architecture
---
# Message-based integration of Dynamics 365 Supply Chain Management with a telematics solution

***Applies to:*** ***Dynamics 365 Supply Chain Management, Azure Service Bus, Azure Storage Account***

This solution combines Dynamics 365 Supply Chain Management, Azure Service Bus, and Azure Storage Account to integrate with a telematics solution from the company AIS alfaplan GmbH. By using this integration, you can provide warehouse shipments to the telematics solution so it can use a fully digitalized and transparent delivery process from loading to unloading.

To implement a fully digitalized and transparent delivery process from loading to unloading, you need an integration between Dynamics 365 Supply Chain Management and a telematics solution. In this scenario, the telematics solution is from AIS alfaplan GmbH, but the same integration is also possible with other solution providers. This solution doesn't just provide data to the telematics solution. It also gets data into Dynamics 365 Supply Chain Management for triggering downstream processing and providing transparency.

This solution uses message-based integration to loosely couple the two systems and keep a low dependency between them. The solution isn't industry-specific. You can use it for last mile delivery and also for supply routes between warehouses.

## Architecture

This section shows the solution architecture.

:::image type="content" source="media/supply-chain-message-based-integration-telematics-solution.svg" alt-text="The architecture for message-based integration between Dynamics 365 Supply Chain Management and AIS telematics solution." lightbox="media/supply-chain-message-based-integration-telematics-solution.svg":::

## Dataflow

The following dataflow shows how and when data gets transferred from Dynamics 365 Supply Chain Management to the telematics solution. It also shows the transfer of data back from the telematics solution to Dynamics 365 Supply Chain Management. A prerequisite for this dataflow is the installation of the external Dynamics 365 solution *gevis ERP Enterprise*, which includes the Azure Service Bus connector. You must also install the solution from AIS alfaplan GmbH.

1. A sales order (last mile) or transfer order (supply delivery) gets created and released to warehouse in Dynamics 365 Supply Chain Management. After the work is completed and the goods are ready for shipment at the bay door location, the warehouse shipment is exported through the [data import/export framework](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-para).

1. When the export finishes, a message is created in an Azure Service Bus Queue. This message sends a signal to the telematics solution that there's a new shipment to deliver. The message includes the target AIS and also the URL to the exported data from the data export, which is an XML file of the structure of a composite data entity.

1. The ASB Connector processes the message sent by Dynamics 365 Supply Chain Management. It downloads the XML file of the structure of a composite data entity and runs a configurable XSLT transformation on it. The goal of the XSLT transformation is to get a file format that's compatible with the AIS structure. Afterwards, the ASB Connector uploads the file to a storage account and puts a message in a configurable Azure Service Bus Queue to send the message to AIS.

1. AIS works on the Azure Service Bus Queue for this concrete integration, by receiving the messages and downloading the file from the storage account.

1. During the processing in AIS, the application sends status updates via messages to an Azure Service Bus Queue. These messages might be about the loading of packages/items or telematic messages that a delivery vehicle is moving on the delivery route.

1. The ASB Connector processes the message sent by AIS. It downloads the message file and converts it to a call to Dynamics 365 Supply Chain Management.

1. The ASB Connector sends the status update information via a custom service call.

1. Dynamics 365 Supply Chain Management processes the received status update information, such as by triggering ship confirm processes for loading end status updates.

## Components

The following components are used in the reference architecture.

- [Azure Storage Account](/azure/storage/common/storage-account-overview) is used to save the payload of the messages between the integrated systems.

- [Azure Service Bus](/azure/service-bus-messaging/) is used as the messaging system to implement a message-based integration.

- [Azure Virtual Machines](/azure/virtual-machines/overview) are used to host the ASB Connector and the AIS application.

## Scenario details

The organizations that implement this solution use Dynamics 365 Supply Chain Management for their entire supply chain. Use the integration to gain transparency and track internal and external deliveries. Drivers use handheld devices for the AIS processing, such as for loading at the warehouse and delivery to the customer.

### Potential use cases

Tracking of external deliveries via last mile routes starting from a warehouse to one or multiple customers:

- Create sales orders in Dynamics 365 Supply Chain Management and assign those sales orders to specific last mile routes.

- Handle the loading and delivery of the orders via AIS.

- Trigger ship confirmation via loading end on the AIS mobile devices, which also triggers packing slip printing and posting.

- Track the progress of the delivery in Dynamics 365 Supply Chain Management.

Tracking of internal deliveries via supply routes from one warehouse to another:

- Create transfer orders in Dynamics 365 Supply Chain Management and assign those transfer orders to specific supply routes.

- Handle the loading and delivery of the orders via AIS.

- Trigger ship confirmation via loading end on the AIS mobile devices, which also triggers transfer order ship confirmation.

- Track the progress of the delivery in Dynamics 365 Supply Chain Management.

### Transparency optimization

This solution provides higher transparency of where the sales orders are on the delivery route. In high turnaround business where the customers are waiting for their deliveries, it's a high benefit to be able to answer questions like "Will my delivery arrive in the next 10 minutes?". Before the solution is implemented, the organizations wouldn't know about delivery once the orders leave the warehouse.

## Related resources

- [Dynamics 365 Supply Chain Management documentation](/dynamics365/supply-chain/)  

- [Dynamics 365 documentation](/dynamics365/)  

- [gevis ERP Enterprise in Microsoft Marketplace](https://marketplace.microsoft.com/de-de/product/dynamics-365-for-finance-and-operations/gws.cd5df30c-e422-44de-91f5-3a27bfdade2e?tab=overview)  

- [AIS alfaplan](https://ais-alfaplan.de/de)  

## Contributor

This article is maintained by Microsoft. It was originally written by the following contributor.

Principal author:

- [Paul Heisterkamp](https://www.linkedin.com/in/paul-heisterkamp) | Microsoft Dynamics 365 Solution Architect
