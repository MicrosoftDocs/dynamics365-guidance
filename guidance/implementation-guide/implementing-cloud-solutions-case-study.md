---
title: Case study for implementing cloud solutions
description: Review a case study for cloud implementation, including customizations and operating in the cloud with Dynamics 365.  
author: taksatoms
ms.author: tsato
ms.date: 05/15/2023
ms.topic: conceptual

---

# Case study for implementing cloud solutions

Microsoft always looks to provide customers with solutions that cater to their specific needs. This case study explores how a company with varied retail locations, from busy cityscapes to rural areas, was able to implement a hybrid model that used both on-premises and cloud solutions to provide reliable and flexible connectivity.  

## Case study - Rev up for speedier service

A family-owned business based in South Australia is one of the largest retailers in the region, with ventures that span fuel, convenience, quick-serve restaurants, and real estate.

One of its key businesses is a chain of retail stores that serves busy guests across Australia.

Their focus on customer service has led the company to reimagine the way its store systems are designed and connected. As their retail chain has grown, they have faced common challenges: outdated technologies, changes in customer behavior, and the pace of change with existing suppliers. The company was ready for an overhaul and an infrastructure solution that could serve its goals now and in the future.

Given the high volume of traffic that the retail chain processes and the diversity of its retail store locations, the company was seeking a hybrid solution with reliable, flexible connectivity.

Scalability and speed are critical for their retail business, and they needed an infrastructure design that optimizes for both.

"We serve millions of guests each month," says the company's store systems specialist. "To achieve speed of service, we know that we need to have something on-premises to retain our workloads in the store. And, at the same time, we need to have that cloud connectivity to the back office."

A cloud engineer at the company adds, "We have stores in rural areas where they don't have high internet speed connections. We wanted to have something that is both in-store and in the cloud that would synchronize when it comes to failovers and redundancy, so that we can have the best of both worlds."

When it came to renewing store hardware and to keep up with the pace of innovation, the company chose to go with a hybrid model that integrates Azure, Azure Stack Edge, and Dynamics 365 Commerce.

The new design impacts the stores' day-to-day connectivity. "What we are planning to do is a direct connection to Dynamics 365, and the failover needs to happen in Azure Stack Edge," one engineer said. "We expect to have a minimum of 99 percent of uptime."

One of the team's other top considerations was how easy the infrastructure would be to manage, so they factored in what the company was already using across its retail business.

"We have already heavily invested in Microsoft products. We use Dynamics 365, Microsoft 365, Power BI, and multiple other products," explains one engineer. "We wanted to have a single pane of glass where we could administer and monitor all of the systems."

The hybrid deployment model using Azure Stack Edge and Dynamics 365 Modern Point of Sale provides store operations redundancy in case of network outage.

The new infrastructure design provides the connectivity, consistency, and efficiency that the company needs. Over time, the company expects that it will help them avoid store downtime, maintain real-time stock levels, simplify its infrastructure management processes, and reduce maintenance and compute costs.

The new infrastructure design will impact the customer experience at the store level. "We offer a comprehensive omnichannel experience to guests walking into our stores," says the store systems specialist. "We enable our guests to pay at the pump without having to come into the store by using the \[retail chain\] app. We also enable our guests to click and collect their food, coffee, or supermarket needs. To enable that, we need real-time connectivity to our head office systems—that is key for us. With Azure Stack Edge and an in-store database, we are hoping to get that real-time connectivity."

This orchestration ensures connectivity and consistency, as a cloud engineer explains. "We deployed three virtual machines. One is used to monitor the in-store cameras, and the other is used to store a Dynamics 365 database backup. If the store loses its internet connection to Dynamics 365, it would be able to operate normally while that virtual machine continues with the operations. Then, once the connection is restored, it will be able to synchronize back to Dynamics 365."

As the company continues to roll out its new infrastructure, it's piloting a solution to recognize vehicles' number plates based on real-time CCTV feeds. One benefit of this is loss prevention, in situations where a number plate is tied to a known offender in a published database.

They also plan to use the in-store cameras to do machine learning and AI on Azure Stack Edge virtual machines to predict stock levels and alert the staff, all locally, without the cloud.
