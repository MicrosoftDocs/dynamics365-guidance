---
title:  Case to resolution end-to-end overview
description: Learn about the end-to-end business process, from case to resolution. This article provides a high-level flow diagram and describes the relationship with other processes in Dynamics 365 solutions.
ms.date: 04/05/2023
ms.topic: conceptual

author: edupont04
ms.author: marcoje

---

# Case to resolution end-to-end overview

***Applies to: Dynamics 365 Commerce, Dynamics 365 Customer Insights, Dynamics 365 Customer Service, Dynamics 365 Customer Service Insights, Dynamics 365 Customer Voice, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Human Resources, Dynamics 365 Project Operations, Dynamics 365 Remote Assist, Dynamics 365 Sales, Dynamics 365 Supply Chain Management***

This article describes the *case to resolution* end-to-end business process flow and its relationship to other business processes that can be used within Dynamics 365.

## Case to resolution process relationship

The following diagram shows the relationship of other processes and products/features for the *case to resolution* process.

:::image type="content" source="media/case-to-resolution-process.png" lightbox="media/case-to-resolution-process.png" alt-text="Business process relationships with upstream and downstream processes that are explained in the next paragraphs.":::

The first column of this diagram shows potential upstream processes for the *case to resolution* process including the following:

- **Acquire to dispose**  

  When cases involve operations with fixed assets or customers assets, the *acquire to dispose* process is upstream to include the process of creating the assets and log asset installations, uninstallations or replacements at owned sites or customer locations.

- **Hire to retire**  

  In the *hire to retire* process, you use cases to manage employee requests, manager requests, and other back office operations, such as leave, absence, or benefits processes.

- **Inventory to deliver**  

  In any organization that handles tangible products, the *inventory to deliver* process may include cases that are either internal or external in nature. For example, vendor quality, customer issues, or production related cases.

- **Order to cash**  

  The *case to resolution* process can be upstream when you need to create cases related to accounts, sales orders, leads, and so on.

- **Plan to produce**  

  You can use case management with production orders to help manage your production process.

- **Procure to pay**  

  The *case to resolution* process can be upstream when you need to create cases related to suppliers, purchase orders, purchase requisitions, requests for quotations, and so on.

- **Product and service lifecycle management**  

  Case investigations may lead to product quality reviews to diagnose product or service issues that need to be addressed in product or service development process.

- **Project to profit**  

  When you use projects to manage internal or external projects, cases can be a critical part of the process to manage requests and issues.

- **Record to report**  

  Case management can be a critical tools in coordinating resolutions and refund for example, with many other business processes.

- **Service to cash**  

  The *case to resolution* process is often tightly integrated with the *service to cash* process as a tool to help resolve issues with customer assets, products, warranties, and so on.

The second column in the graphic shows the business process areas that are part of the *case to resolution* process.

- Define customer service operations

- Establish a knowledge base

- Engage with customers

- Create a case

- Manage cases

- Work on a case

- Resolve a case

- Analyze case performance

- Process product returns and exchanges

- Process product recalls

The third and last column in the diagram displays the downstream business process including the following the same list that is shown in column one for the upstream processes. This is because there is a lot of flexibility in the process flow your organization can use to manage requests and issues. In some cases, the case may be a prerequisite for completing another process, in others, the case might happen after another process is already complete.

## Featured capabilities

There are product specific capabilities offered that interact with the *case to resolution* to process including, but not limited to, the following:

- **Omnichannel for Customer Service**  

  Allows customers to contact support through multiple channels, streamlining the case resolution process and providing a consistent experience.

- **Nuance Gatekeeper**  

  Provides biometric customer authentication by understanding customer voice tone, manners and wording during voice and messaging conversations.

- **Knowledge Base management**  

  A robust knowledge base authoring, curation and publishing tool which can also be configured to crawl external knowledge bases created in content services like SharePoint.

- **Smart Assist Bot**  

  An Azure Bot integrated to Customer Service Workspace to assist agents during customer conversations

- **Unified routing**  

  Efficiently directs conversations and cases to the right agent or team using a variety of criteria including rules, skills matching and agent capacity, reducing wait times and improving resolution times.

- **Microsoft Teams for collaboration**  

  Enables support agents to collaborate in real-time with subject matter experts (SME), share information, and solve cases faster

- **AI Suggestions**  

  Allows Customer Service Workspace to suggest articles and cases based on latest messages in a conversation.

- **Dynamics 365 Customer Insights**  

  Builds a unified customer profile with data from multiple sources and provides a consolidate 360-degree view of customer so agents can have a comprehensive view of who they are servicing when dealing with a customer request.

- **Dynamics 365 Customer Service Insights**  

  Provides actionable insights and analytics to help teams identify trends, optimize processes, and improve the overall customer experience.

- **Dynamics 365 Customer Voice**  

  Provides an end-to-end survey management tool that can be used in multiple scenarios including post-case customer satisfaction surveys.

- **Power Virtual Agents and Azure Bots**  

  Automates routine tasks, allows for self-service options, and frees up support agents to focus on more complex cases.

- **Connected Customer Service for IoT Center and Hub**  

  Allows support teams to proactively identify and resolve issues with connected devices, reducing downtime and improving customer satisfaction.

- **Returns, RMA's and Exchanges**  

  Sales Returns in Dynamics 365 Finance and Operations provides capabilities to process return orders for physical return or credit-only processes, as well as Return Material Authorizations (RMA) and Replacement order creation, in advance or upon return, for product exchanges.

## Case to resolution business process flow

The following diagram shows the high-level flow of the *case to resolution* business process. Each solid rectangle on the diagram represents an end-to-end business process area. The sub-processes shown in the diagram are shown for the *case to resolution* business process. The arrows on the diagram show the flow of the business process in an organization. If a sub-process can lead to more than one other sub-process, the parallel sub-processes are shown as branches.

:::image type="content" source="media/case-to-resolution-flow.png"  lightbox="media/case-to-resolution-flow.png" alt-text="inventory to deliver end-to-end process flow diagram":::

The following steps are illustrated in the *case to resolution* end-to-end business process flow diagram.

1. Start

2. Case to resolution

3. Define customer service operations

4. Establish a knowledge base

5. Engage with customers

6. Create a case

7. Manage a case

8. Work on a case

    1. Process product return and exchanges

    2. Process product recalls

    3. Inventory to deliver

9. Resolve a case

10. Analyze case performance

11. End

Start has parallel branches to each of the following end-to-end processes (shown on the left side of the diagram)

1. Acquire to dispose

2. Hire to retire

3. Product and service lifecycle management

4. Procure to pay

5. Plan to produce

6. Order to cash

7. Prospect to quote

8. Service to cash

9. Record to report

10. Project to profit

Each of these boxes has a branch that connects to 6. Create a case.  

Procure to pay, Plan to produce, and Order to cash each have a parallel branch connecting to Inventory to deliver, which also connects to 6. Create a case.

Create a case has parallel branches to each of the end-to-end processes a-j (shown on the right side of the diagram)

Each of the end-to-end processes a-j have parallel branches connecting 7. Manage a case (shown on the right side of the diagram).

## Next steps

If you would like to implement Dynamics 365 solutions to assist with your *case to resolution* business processes, you can use the following resources and steps to learn more.

- Define the goals and objectives of implementing an *case to resolution* technology solution. Learn more at [Implementation strategy](../implementation-guide/implementation-strategy.md).

- Define the business process scope of your project. Learn more at [Process-focused solution](../implementation-guide/process-focused-solution.md).

- Request a demo or get a free trial of Microsoft Business Applications solutions for the *case to resolution* process. Learn more at [Request a demo](https://dynamics.microsoft.com/dynamics-365-free-trial/).

- Get an introduction of the **case to resolution** business process. Learn more at [*Case to resolution* introduction](case-to-resolution-introduction.md).

- Get an overview of the **case to resolution** business process areas. Learn more at [*Case to resolution* business process areas](case-to-resolution-areas.md)

## Related resources

You can use the following resources to learn more about the *case to resolution* process in Dynamics 365.

- [Dynamics 365 Customer Service documentation](/dynamics365/customer-service/landing-page)

- [Case management in Dynamics 365 Finance and Operations Management documentation](/dynamics365/fin-ops-core/fin-ops/organization-administration/cases)

- [Dynamics 365 Customer Service on Microsoft Learn](/training/dynamics365/customer-service)

<!--## Tags
*Stakeholders:* Functional consultant, Business analyst, Accounts payable lead, Accounts receivable lead, Finance lead, Sales lead, Purchasing lead, Production lead, Supply chain lead, Customer Service lead, Retail Store Operations lead, Human resources leads, Managers, Employees

*Products:* Dynamics 365 Commerce, Dynamics 365 Customer Insights, Dynamics 365 Customer Service, Dynamics 365 Customer Service Insights, Dynamics 365 Customer Voice, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Human Resources, Dynamics 365 Project Operations, Dynamics 365 Remote Assist, Dynamics 365 Sales, Dynamics 365 Supply Chain Management
