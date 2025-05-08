---
title: Learn from a cloud implementation case study
description: Learn how a company with retail locations across Australia used a hybrid model of on-premises and cloud solutions to improve its connectivity and customer service.
author: taksatoms
ms.author: edupont
ms.date: 01/11/2024
ms.topic: concept-article
ms.custom:
  - ai-seo-date: 01/11/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
ai-usage: ai-assisted
---

# Learn from a cloud implementation case study

Microsoft helps customers find solutions that match their specific needs. This case study shows how a company with different retail locations, from busy cities to rural areas, used a hybrid model of on-premises and cloud solutions to provide reliable and flexible connectivity.

## Case study - Rev up for speedier service

A family-owned business in South Australia is one of the largest retailers in the region. It has businesses in fuel, convenience, quick-serve restaurants, and real estate. One of its key businesses is a chain of retail stores that serves busy guests across Australia.

The company cares about customer service and wanted to change the way its store systems were designed and connected. As the retail chain grew, it faced some common problems: old technologies, changing customer behavior, and slow suppliers. The company needed a new and better infrastructure solution for now and the future.

The company has a lot of traffic in its retail business and its stores are in different places. It needed a hybrid solution with reliable, flexible connectivity. Scalability and speed are important for the retail business, and the company needed an infrastructure design that was good for both.

"We serve millions of customers each month," says the company's store systems specialist. "To achieve speed of service, we know that we need to have something on-premises to retain our workloads in the store. And, at the same time, we need to have that cloud connectivity to the back office."

A cloud engineer at the company says, "We have stores in rural areas where they don't have high internet speed connections. We wanted to have something that is both in-store and in the cloud that would synchronize when it comes to failovers and redundancy, so that we can have the best of both worlds."

The company decided to use a hybrid model that combines Microsoft Azure, Azure Stack Edge, and Dynamics 365 Commerce.

The new design helps the stores stay connected every day. "What we are planning to do is a direct connection to Dynamics 365, and the failover needs to happen in Azure Stack Edge," one engineer says. "We expect to have a minimum of 99 percent of uptime."

The company also wanted to make sure the infrastructure was easy to manage, so they used what they already had in their retail business.

"We have already heavily invested in Microsoft products. We use Dynamics 365, Microsoft 365, Power BI, and multiple other products," explains an engineer. "We wanted to have a single pane of glass where we could administer and monitor all of the systems."

The hybrid model using Azure Stack Edge and Dynamics 365 Modern Point of Sale keeps the store operations running even if the network goes down.

The new infrastructure design gives the company the connectivity, consistency, and efficiency it needs. The company hopes it helps them avoid store downtime, keep track of stock levels, simplify their infrastructure processes, and save money on maintenance and computing.

The new infrastructure design also improves the customer experience at the store level. "We offer a comprehensive omnichannel experience to guests walking into our stores," says the store systems specialist. "We enable our guests to pay at the pump without having to come into the store by using the \[retail chain\] app. We also enable our guests to click and collect their food, coffee, or supermarket needs. To enable that, we need real-time connectivity to our head office systems&mdash;that is key for us. With Azure Stack Edge and an in-store database, we are hoping to get that real-time connectivity."

The system works well together. As a cloud engineer explains, "We deployed three virtual machines. One is used to monitor the in-store cameras, and the other is used to store a Dynamics 365 database backup. If the store loses its internet connection to Dynamics 365, it would be able to operate normally while that virtual machine continues with the operations. Then, once the connection is restored, it will be able to synchronize back to Dynamics 365."

The company is still working on its new infrastructure. It's also testing a solution to recognize car number plates from real-time CCTV feeds to help prevent losses, for example, when a number plate belongs to a known offender in a database.

It also plans to use the in-store cameras to do machine learning and AI on Azure Stack Edge virtual machines to predict stock levels and alert the staff, all locally, without the cloud.
