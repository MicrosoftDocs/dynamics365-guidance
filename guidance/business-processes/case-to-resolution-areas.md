---
title: Overview of case to resolution business process areas
description: Get an overview for each of the business process areas in the case to resolution end-to-end business process flow in Dynamics 365 solutions. Learn about their role in case performances.
ms.date: 11/25/2024
ms.topic: concept-article

author: edupont04
ms.author: marcoje

---

# Overview of the case to resolution business process areas

***Applies to: Dynamics 365 Commerce, Dynamics 365 Customer Insights, Dynamics 365 Customer Service, Dynamics 365 Customer Service Insights, Dynamics 365 Customer Voice, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Human Resources, Dynamics 365 Project Operations, Dynamics 365 Remote Assist, Dynamics 365 Sales, Dynamics 365 Supply Chain Management***

The *case to resolution* process is broken down into many business process areas. The following sections further describe the business process areas.

## Define customer service operations

This business process area involves defining the customer service operations policies and procedures that guide the handling of cases. It includes creating customer service standards such as agent teams, queues, agent scripts, and conversation/email templates. It also covers establishing case routing and distribution rules, and defining service level agreements (SLAs) to ensure timely and effective resolution of customer issues. In Dynamics 365 Customer Service deployments, you configure these definitions in the Customer Service admin center.

## Establish a knowledge base

This business process area involves creating a knowledge base of information to support case resolution. This includes creating articles, how-to guides, and other resources to help agents resolve cases quickly and accurately. The knowledge base can also be used to provide self-service support to customers, reducing the need for live agent support. Dynamics 365 Customer Service provides a robust tool for authoring knowledge base content, curating, and publishing. You can also configure the tool to crawl external knowledge bases created in content services, such as SharePoint.

## Engage with customers

This business process area involves establishing a conversation between a customer or employee and a virtual or human agent through chat, email, phone and social media channels, in order to allow customer or employee to identify/authenticate themselves, get answers to their questions, and request transactions to be run on their behalf and/or solutions to be provided by Customer Service operations. Conversations can be initiated by customers (inbound conversations) or by agents (outbound conversation) according to the need to be addressed. Omnichannel for Customer Service allows customers to conveniently connect to Customer Service operations through their voice, chat, or social media channel of choice. Dynamics 365 Customer Service can monitor Customer Service operations mailbox and distribute emails to agents in the form of email activities or cases, as required. Many organizations have invested heavily invested in legacy Call Center solutions or Contact Center as a Service (CCaaS) solutions from vendors. In contrast, Dynamics 365 provides Channel Integration Framework so that an organization can connect their vendors' solutions with Dynamics 365.

## Create a case

This business process area involves logging cases in the system when the available content and transactions aren't enough to fulfill customer or employee needs. Cases must include relevant information such as customer information, case description, and priority level. It may also involve automated case creation, such as through email or web form submissions. The patterns related to this business process area cover both the creation of cases in Dynamics 365 Customer Service and the use of Case management in the finance and operations apps.

## Manage cases

This business process area involves routing cases to the appropriate teams or individuals for resolution, tracking case progress, and providing updates to customers or stakeholders as needed. In Dynamics 365 Customer Service, Unified Routing can distribute cases to queues or agents based on a combination of rules, skills matching and agent capacity to determine the agent that will provide the right resolution in the least amount of time.

## Work on a case

This business process area involves accepting a case (or picking a case in a queue), working on the case, including researching, and analyzing the issue, communicating with customers or stakeholders, and collaborating with other teams or individuals as needed to resolve the case. Dynamics 365 integration with Microsoft Teams allows agents to reach out directly to subject matter experts (SMEs) and obtain guidance to solve complex issues. If subject matter expert is unknown, agent can initiate a Swarm request and define which skills are required to get the case solved, and Dynamics 365 assigns the experts to be engaged on the case.

## Resolve cases

This business process area involves resolving the case and closing it in the system, including documenting the resolution and ensuring that the customer or stakeholder is satisfied with the outcome. Dynamics 365 Customer Service provides agents with an enhanced email editor and email templates, making it easier to send a formal closure email to customer or employee.

## Analyze case performance

This business process area involves analyzing case data to identify trends, track performance metrics, and identify areas for improvement in the case to resolution process. Dynamics 365 Customer Service provides case insights through Power BI dashboards that include case trend analysis by multiple criteria, while Dynamics 365 Customer Voice can manage customer satisfaction surveys to customers upon case resolution.

## Process product return and exchanges

This business process area involves managing returns and exchanges of products, including logging the return or exchange request, coordinating shipment, and updating inventory and financial records as needed. This process doesn't include the handling of the inventory or the financials that are covered in the [Inventory to deliver process](inventory-to-deliver-overview.md) and the [Record to report process](record-to-report-overview.md), respectively. But it includes the process to initiate the return or exchange.

## Process product recalls

This business process area involves managing product recalls, including logging the recall request, coordinating with vendors or suppliers, and notifying customers and stakeholders as needed. This process doesn't include the handling of the inventory or the financials that are covered in the [Inventory to deliver process](inventory-to-deliver-overview.md) and the [Record to report process](record-to-report-overview.md), respectively. But it includes the process to initiate the return or exchange.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *case to resolution* business processes, learn more at the following resources and steps.

1. [Case to resolution introduction](case-to-resolution-introduction.md)
2. [Case to resolution end-to-end overview](case-to-resolution-overview.md)
3. Learn about the business process catalog at [About the business process catalog for Dynamics 365 apps and services](about.md)  

## Related information

You can use the following resources to learn more about the *case to resolution* process in Dynamics 365.

- [Dynamics 365 Customer Service documentation](/dynamics365/customer-service/landing-page)

- [Case management in Dynamics 365 Finance and Operations Management documentation](/dynamics365/fin-ops-core/fin-ops/organization-administration/cases)

- [Dynamics 365 Customer Service on Microsoft Learn](/training/dynamics365/customer-service)

<!--## Tags
*Stakeholders:* Functional consultant, Business analyst, Accounts payable lead, Accounts receivable lead, Finance lead, Sales lead, Purchasing lead, Production lead, Supply chain lead, Customer Service lead, Retail Store Operations lead, Human resources leads, Managers, Employees

*Products:* Dynamics 365 Commerce, Dynamics 365 Customer Insights, Dynamics 365 Customer Service, Dynamics 365 Customer Service Insights, Dynamics 365 Customer Voice, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Human Resources, Dynamics 365 Project Operations, Dynamics 365 Remote Assist, Dynamics 365 Sales, Dynamics 365 Supply Chain Management
