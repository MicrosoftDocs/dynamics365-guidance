---
title: Beyond the DRA - cloud label printing for Dynamics 365 Supply Chain Management
description: Find a TechTalk video that talks about how you can print labels by connecting Dynamics 365 Supply Chain Management to an external service provider.
ms.date: 09/11/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Beyond the DRA - cloud label printing for Dynamics 365 Supply Chain Management

In the evolving landscape of enterprise resource planning (ERP) systems, efficient label printing is essential, particularly in the management of supply chains. As organizations adopt cloud technologies to streamline operations, Dynamics 365 Supply Chain Management offers new possibilities beyond traditional Document Routing Agent (DRA) printing methods. This article delves into the advancements in cloud label printing for Dynamics 365 Supply Chain Management, exploring its features, configurations, and use cases.

We based this article on [a TechTalk](https://youtu.be/DuUcwo5ufdo?si=WP-S_B1MLyoWCqLA) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/supply-chain-management-cloud-label-printing-slide.svg" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/DuUcwo5ufdo?si=WP-S_B1MLyoWCqLA":::

## Introduction to cloud label printing

The traditional DRA method was the backbone of label printing in Dynamics 365 Supply Chain Management. This method involves setting up labels as document routing layouts, primarily using Zebra Programming Language (ZPL), which are then mapped to specific work orders and printers. Once a print job is initiated, it's sent to the DRA installed on-premises, which then dispatches the job to the corresponding printer. While reliable, this approach has its limitations, particularly in terms of scalability and design flexibility.

:::image type="content" source="media/supply-chain-management-cloud-label-printing-whats-new.svg" alt-text="Diagram with three columns for label layouts, custom labels, dynamics printer selection." lightbox="media/supply-chain-management-cloud-label-printing-whats-new.svg":::

With version 10.0.34, Dynamics 365 Supply Chain Management now supports an alternative that relies on external services for label design and printing. This new capability introduces a more dynamic and scalable approach so that organizations can manage complex labeling requirements more efficiently. Learn more at [Print labels using an external service](/dynamics365/supply-chain/supply-chain-dev/label-printing-using-external-label-service).

## Key features and setup

Cloud label printing in Dynamics 365 Supply Chain Management revolves around label layouts, a new feature that provides enhanced flexibility compared to document routing layouts. These layouts allow the use of variables and templates, offering a more sophisticated design capability. To use cloud label printing, businesses must define these label layouts within the system, which can then be associated with external services like Loftware or BarTender for actual printing.

One of the critical aspects of cloud label printing is dynamic printer selection. This feature allows the definition of default label printers for warehouse workers and locations. However, the real power lies in the ability to override these defaults on the fly, providing the flexibility to adapt to different printing scenarios as needed.

The setup process for cloud label printing involves several steps, starting with the creation of an external service definition. This definition specifies how the system should communicate with the external labeling service, typically via HTTP API calls. The configuration includes setting up service operations, defining the API endpoint, and managing authentication details.

Once the external service is defined, businesses can create instances of this service and associate them with specific label printers within Dynamics 365 Supply Chain Management. These printers can be either on-premises or cloud-based, depending on the organization's infrastructure and requirements.

## Use cases and considerations

The choice between DRA and cloud label printing depends on various factors, including the complexity of labeling requirements, scalability needs, and budget considerations. For organizations with simple labeling needs and limited budgets, the DRA remains a cost-effective and straightforward solution. However, as businesses grow and their labeling demands become more complex, cloud label printing offers significant advantages.

:::image type="content" source="media/supply-chain-management-cloud-label-printing-use-cases.svg" alt-text="pros and cons for document routing agent, cloud label, or hybrid configurations." lightbox="media/supply-chain-management-cloud-label-printing-use-cases.svg":::

Cloud label printing is beneficial for organizations that require advanced label designs, such as those with complex templates or extensive use of variables. The drag-and-drop design capabilities offered by external services like BarTender or Loftware make it easier to create and manage intricate label layouts without the need for deep technical expertise in ZPL.

Moreover, cloud label printing is ideal for organizations with high-volume printing needs or those operating in regulated industries where compliance and traceability are critical. The ability to integrate cloud label printing with other cloud-based services, such as Azure, further enhances its scalability and flexibility.

However, it's important to note that cloud label printing introduces extra costs, as the external services used for printing typically require separate licensing and fees. Organizations must also consider the architectural implications of integrating these services into their existing Dynamics 365 Supply Chain Management setup, including the need for thorough testing and integration planning.

## Practical demonstrations

A recent TechTalk session demonstrated the practical application of cloud label printing using two popular external labeling services: Loftware and BarTender. These demos showcased how to configure label printing in Dynamics 365 Supply Chain Management. Tasks include setting up label layouts, defining external services, and running print jobs.

For example, one demo highlighted the use of Loftware Cloud integrated with Dynamics 365 Supply Chain Management. That demo shows how labels can be designed, managed, and printed directly from the cloud without relying on on-premises components. Another demo demonstrated integration with BarTender. This demo included both cloud-based and on-premises configurations to illustrate the flexibility of cloud label printing in meeting diverse business needs.

## Conclusion

The introduction of cloud label printing in Dynamics 365 Supply Chain Management marks a significant step forward in the evolution of enterprise label printing. The support for external label services gives organizations greater flexibility, scalability, and integration capabilities. Organizations can move beyond the limitations of traditional DRA printing and embrace more modern, cloud-based solutions.

As businesses continue to navigate the complexities of supply chain management, the ability to efficiently manage label printing is crucial. Whether through the continued use of DRA or by adopting cloud label printing, organizations now have more options to tailor their printing processes to their specific needs.

For those interested in exploring cloud label printing further, Microsoft provides comprehensive documentation and resources to guide the setup and implementation process. Using these tools can help ensure a smooth transition and maximize the benefits of this powerful new feature.

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
- [Dynamics 365 Supply Chain Management Documentation](/dynamics365/supply-chain/)
- [Print labels using an external service](/dynamics365/supply-chain/supply-chain-dev/label-printing-using-external-label-service)  
- [Print labels using the Loftware NiceLabel label service solution](/dynamics365/supply-chain/supply-chain-dev/label-printing-using-nicelabel)  
- [Print labels using the Seagull Scientific BarTender&reg; label service solution](/dynamics365/supply-chain/supply-chain-dev/label-printing-using-bartender)  
- [Loftware Cloud Label Printing](https://www.loftware.com/)
- [BarTender Label Software](https://www.seagullscientific.com/)
- [Azure Integration Services](https://azure.microsoft.com/services/integration/)
