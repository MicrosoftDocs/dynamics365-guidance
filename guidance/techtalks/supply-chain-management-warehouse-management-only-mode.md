---
title: TechTalk Warehouse management only mode with Dynamics 365 Supply Chain Management 
description: Summary of TechTalk video that talks about adding warehouse management capabilities from Dynamics 365 Supply Chain Management to any business solution.
ms.date: 10/15/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Warehouse management only mode with Dynamics 365 Supply Chain Management

Microsoft's Dynamics 365 Supply Chain Management continues to evolve with new features designed to optimize warehouse operations. One of the most intriguing recent developments is the introduction of *Warehouse management only mode*. This feature, currently available as a preview, aims to enhance the functionality of Dynamics 365 by focusing exclusively on warehouse management tasks, providing users with a scalable and flexible system.

In this TechTalk, we delved into the *Warehouse management only mode* and explored how it integrates with existing business solutions for enterprise resource planing (ERP) and order management systems. The TechTalk also covered how *Warehouse management only mode* can streamline inbound and outbound processes, and why it can be an essential tool for businesses.

We based this article on [a TechTalk](https://youtu.be/uOURvwXwY-E) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/DTV013-slide.png" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/uOURvwXwY-E":::

## What is Warehouse management only mode?

*Warehouse management only mode* is a cloud-based system implemented into the Dynamics 365 Supply Chain Management solution. We designed it for businesses that need a warehouse management system (WMS) to integrate with their existing ERP or order management systems. *Warehouse management only mode* can be used on its own. You can also deploy *Warehouse management only mode* as an enhancement on top of the core Dynamics 365 warehouse management capabilities.

The following image is an infographic that showcases the warehouse management capabilities of a business app, such as Dynamics 365 Supply Chain Management.  

:::image type="content" source="media/DTV013-warehouse-management-capabilities.png" alt-text="Screenshot of slide with boxes that call out rule engine, integrated processes, scanning, material handling, carrier integration, embedded analytics, continuous updates." lightbox="media/DTV013-warehouse-management-capabilities.png":::

The visualization calls out various integrated features, including the following list:

- A rule engine for flexible workflows  
- Scanning for paperless task management  
- Material handling and carrier integration  
- Built-in analytics for insights  
- Continuous software updates  

The diagram calls out specific industries, manufacturing, automotive, eCommerce, retail, healthcare, food, and high tech. It also has visual representations for inventory management, inbound processes, quality management, warehouse operations, outbound logistics, and labor management.

With this mode, businesses can handle various operational requirements without implementing the full Dynamics 365 suite. It allows for a quick setup process and seamless integration. That makes it an ideal option for those businesses who need a standalone WMS but want to retain the possibility of scaling their use of Dynamics 365 in the future.

## Integration and configuration

One of the primary advantages of *Warehouse management only mode* is its ability to integrate with various external ERP and order management systems. The system uses a dedicated warehouse workload, meaning that it can function independently of the full ERP, and can integrate via various means including OData, API processes, or Dataverse virtual entities.

The following image outlines the integration between various systems and processes within a warehouse setting.  

:::image type="content" source="media/DTV013-flow.png" alt-text="The image shows a flowchart detailing the dataflow for Warehouse Management Only Mode in any ERP system. A tile with the warehouse capabilities from Dynamics 365 is in the middle and connects with arrows to and from Dynamics 365 ERP, other ERP, and other integrations." lightbox="media/DTV013-flow.png":::

The warehouse capabilities from Dynamics 365 Supply Chain Management serve as the nexus for multiple flows:  

- Inbound and outbound delivery requests (including purchases, sales, returns, and transfers)  
- Production  
- Integrations with other systems, such as other ERP providers or intelligent order management systems.  

It also highlights the connection to other integrations such as carriers and material handling equipment. Additionally, the chart emphasizes the role of mobile updates for delivery status and stock levels, along with warehouse planning and optimization processes.

When a business uses this mode, they have the flexibility to use Microsoft's ecosystem of solutions to enable extended warehouse and distribution capabilities. It's not least useful for industries that rely heavily on mature non-Microsoft solutions for handling equipment solutions, carrier hubs, and other logistics services.

The architecture of this mode is designed with inbound and outbound processes in mind. For instance, the system can process inbound shipment orders and convert them into actual warehouse orders. These orders can then be handled with the same tools and workflows familiar to existing Dynamics 365 users. This integration extends to inventory management, handling orders via the Warehouse App, and integrating with carriers for shipping and receiving.

## Scenarios for use

*Warehouse management only mode* is suited for various business scenarios. Some typical use cases include:

- **ERP Integration**  

  Businesses running external ERP systems can use the WMS solely for warehouse operations. The system integrates seamlessly, allowing for efficient management of inbound and outbound shipments.

- **Migration**  

  For companies planning to migrate to the full Dynamics 365 Supply Chain Management suite, *Warehouse management only mode* provides a smooth transition. Businesses can start by using it with their current ERP and later migrate fully to Dynamics 365.

- **Multiple Legal Entities**  

  In cases where businesses operate multiple legal entities, the *Warehouse management only mode* allows them to run warehouse operations independently within each entity.

## Key features

Several core features make *Warehouse management only mode* a powerful tool for businesses. One of the most significant is the ability to process large amounts of data quickly. For example, businesses can handle vast amounts of inbound and outbound shipment data using either virtual entities or APIs. This flexibility ensures that the system can scale with a company's needs.

The following image is a high level integration architecture diagram showcasing the flow and processing of data within a complex ERP system for warehouse management.

:::image type="content" source="media/DTV013-architecture.png" alt-text="Two main tiles, where the bottom one shows warehouse management operating in a standalone mode with components like Warehouse Execution, Shipment Orders, and Message Processing directly interacting. The top tiles shows a managed data lake that acts as a central hub. This hub connects to various components including shipment order events and message entities. To the left, data flows in from external integrations, such as Dynamics 365 Business Central, Oracle, SAP, and FedEx, connecting via direct APIs to the system." lightbox="media/DTV013-architecture.png":::

Additionally, the system offers sophisticated validation processes for order messages, ensuring that inbound and outbound shipments are handled accurately and efficiently. Users can also configure their mobile devices to manage warehouse tasks, such as receiving, shipping, and inventory management, directly from the *Warehouse app*.

Moreover, the system allows users to set up business events to automate certain processes, such as notifying external systems when data is ready for consumption. This reduces the need for constant monitoring and manual updates, improving efficiency.

## Inbound and outbound processes

The inbound process begins when a purchase order is created in an external system. Once the purchase order is processed, the warehouse management system generates an inbound shipment order. This order is then registered in the warehouse using the Warehouse App. The system allows for real-time registration and tracking of incoming shipments, creating a seamless flow of goods from suppliers into the warehouse.

The outbound process, on the other hand, involves creating outbound shipment orders based on sales or transfer orders from the external system. Once processed, these orders are released to the warehouse, and the system reserves the inventory required for shipment. The Warehouse App helps users manage the picking and packing process, with the shipment finalized and sent out once the order is ready.

Both inbound and outbound flows are designed to minimize manual intervention and ensure accuracy. The use of business events further automates the communication between the warehouse and external systems, reducing delays and errors in processing.

## Advanced capabilities

*Warehouse management only mode* also introduces a new **shipment receiving journal**, which contains detailed information about the items received in the warehouse. This journal is useful for tracking inventory and ensuring that all incoming goods are accounted for.

Another standout feature is the system's ability to handle large data sets in phases, with validation processes running at each step to ensure accuracy. This feature is beneficial for businesses that handle high volumes of inventory or have complex supply chains.

## Conclusion

The *Warehouse management only mode* in Dynamics 365 Supply Chain Management is a game changer for businesses looking for an advanced warehouse management system that integrates seamlessly with their existing ERP or order management solutions. By focusing solely on warehouse operations, this mode allows businesses to streamline their inbound and outbound processes, improve data accuracy, and reduce manual intervention.

For companies looking to optimize their warehouse operations without fully migrating to Dynamics 365, this feature offers a flexible, scalable solution. Learn more in the [Dynamics 365 documentation](/dynamics365/supply-chain/warehousing/warehouse-management-overview), or explore more resources available on the Microsoft Tech Community.

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
- [Use Warehouse management only mode to optimize your business - Blog](https://cloudblogs.microsoft.com/dynamics365/it/2023/09/15/leverage-warehouse-management-only-mode-to-optimize-your-business/)
- [Warehouse management only mode documentation](/dynamics365/supply-chain/warehousing/wms-only-mode-overview)
- [Supply Chain Management Software Pricing](https://dynamics.microsoft.com/supply-chain-management/pricing/)
