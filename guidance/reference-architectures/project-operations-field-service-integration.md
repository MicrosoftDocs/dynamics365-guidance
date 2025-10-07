---
title: Project Operations and Field Service Integration
description: Find a recommended architecture for integrating Dynamics 365 Project Operations with Field Service to streamline project planning, work order management, and field operations using Power Automate and Azure Functions.
author: v-wendysmith
ms.topic: reference-architecture
ms.date: 08/19/2025
ms.author: edupont
---

# Dynamics 365 Project Operations to Field Service integration architecture

***Applies to: Dynamics 365 Field Service, Dynamics 365 Project Operations, Power Automate Dataverse, Azure Functions, Azure Key Vault***

This solution addresses the challenges of managing large and complex projects in industries like telecommunications, construction, and manufacturing. By integrating Dynamics 365 Field Service and Dynamics 365 Project Operations, it enhances visibility, performance, and user experience.

## Introduction

This reference architecture combines Dynamics 365 Field Service and Dynamics 365 Project Operations to create a seamless integration for project and work order management. It's particularly valuable where extensive projects and field operations are essential. The solution ensures smooth data flow from project planning to execution, enhancing visibility, performance, and user experience.

This architecture should be defined during the planning and design phase of the overall implementation. Doing so ensures that integration and automation processes are aligned with business objectives from the start, leading to smoother transitions and minimized disruptions.

Key stakeholders include project managers, field service managers, IT architects, and business analysts. Project and field service managers provide operational insights; IT architects design the integration and infrastructure; while business analysts ensure alignment with business goals. Collaboration among these stakeholders is essential for a robust and effective implementation.

## Architecture

The following diagram illustrates the architecture for the solution.

:::image type="content" source="./media/project-operations-field-service-architecture.png" alt-text="Screenshot of Project Operations and Field Service integration architecture." lightbox="./media/project-operations-field-service-architecture.png":::

## Dataflow

- In step 1, project coordinators handle the entire project planning process, including creating programs, projects, and project tasks. They also assign unnamed resources based on task types.

- In step 2, after project coordinators assigned resources, Power Automate collects the relevant information and triggers an Azure Function with the necessary data.

- In steps 3, 4, and 5, the Azure Function processes the data, creates work orders, and links the project and project tasks using the Dataverse API. Multiple work orders can be created for a single project task to accommodate various resource scenarios.

- In step 6, dispatchers use the schedule board to assign work order-related resource requirements to named resources and create a *Booking* record.

- In steps 7, 8, and 9, a Dataverse plugin triggers the Azure Function to send booking and related information to a third-party mobility application by using a third-party API. Technicians access this booking information on the external field service mobility device and act accordingly. The booking life cycle includes these stages: *Acknowledgment*, *Travel*, *Onsite*, *In Progress*, and *Complete or Incomplete*.

- In step 10, when the booking stage changes, the third-party application sends an update to the Azure Function.

- In step 11, the Azure Function updates the related booking, work order, project, and project task records, reflecting various calculations such as actual dates and times, actual efforts. It recalculates the variance of actual vs estimated, percentage of overall project completion, and the number of tasks completed.

### Additional information

In the diagram, yellow triangles show exception handling with a retry mechanism. If a failure occurs, the integration layer retries API calls every 30 seconds. The system logs persistent errors in Application Insights and emails the support team. The system handles exceptions differently based on the root cause. This article doesn't cover those details. Reference data, such as resources, skills, availability, efforts, and leaves, is maintained in Dynamics 365 Field Service.

The architecture supports different scenarios, including the following list:


- Single day - single resource
- Single day - multiple resources
- Multiple days - single resource
- Multiple days - multiple resources

This flexibility lets you manage projects from a few hours to 10 years, as limited by the Project Operations app.

## Components

The following components are used in the reference architecture.

- **[Project planning and WBS](/dynamics365/project-operations/project-management/create-wbs)** handles the entire project planning process: creating programs, projects, tasks, and assigning unnamed resources. Without them, we wouldn't have a structured starting point for our
- **[Project planning and WBS](/dynamics365/project-operations/project-management/create-wbs)** handles the entire project planning process: creating programs, projects, tasks, and assigning unnamed resources. Without them, we wouldn't have a structured starting point for our projects.

- **[Power Automate](/power-automate/get-started-logic-flow?tabs=classic-designer)** collects relevant information and triggers an Azure Function with the necessary data, which helps automate workflows and keeps everything in sync. Some data validations occur before the payload is sent to Azure functions. For example, null values, reference data
- **[Power Automate](/power-automate/get-started-logic-flow?tabs=classic-designer)** collects relevant information and triggers an Azure Function with the necessary data, which helps automate workflows and keeps everything in sync. Some data validations occur before the payload is sent to Azure Functions. For example, the system checks for null values, reference data mismatches, and formatting issues, and prevents the payload from being sent if any of these are found.

- **[Azure Function](/azure/azure-functions/functions-get-started?pivots=programming-language-csharp)** processes the data, creates work orders, and links the project and tasks using the Dataverse API. It's the brain of the operation and handles crucial data processing.

- **[Dataverse API](/power-apps/developer/data-platform/webapi/perform-operations-web-api)** links project tasks and manages work orders. It's essential for keeping all data seamlessly integrated across the systems.

- **[Schedule board](/dynamics365/field-service/work-with-schedule-board)** - Dispatchers use the schedule board to assign resource requirements for work orders to specific resources, creating a *Booking* record.
This process allocates resources efficiently based on availability, skill set, travel time, and other factors.  

- **Mobility application from an external service provider**  - Dispatchers send booking information to this app through an Azure Function, so field technicians
get real-time updates on their devices. This way, everyone knows what to do, when to do it, and where to go. Dynamics 365 Field Service
mobility isn't used because of various in-house client challenges.  

- **Azure Function (Update)** - When the booking stage changes, this function updates related records like booking, work orders, projects, and tasks. It updates actual dates, efforts, and project completion metrics by using the Dataverse Web API.

- **Exception handling with retry mechanism** - If something goes wrong, the retry mechanism makes repeated API calls and logs persistent errors in Application Insights. This approach ensures reliability and strong performance.

## Scenario details

The customer faced several problems, including inefficiencies and performance issues in managing large and complex projects. They lacked visibility and management of all inflight work. Operations performance reporting didn't provide useful insights, and there was no mapping of project workflows or user views. The customer also didn't have a system that showed the work breakdown structure (WBS) view of all projects, tasks, and subtasks.

The customer uses unique project management processes and a wide variety of project management styles. Microsoft Project Operations is robust and flexible. It simplifies complex scenarios by using related product capabilities like Power Apps and Power Automate.

The solution addresses the customer's pain points and provides an improved user and process experience. It supports different personas and user journeys, from project planning to closure. Project Operations handles all planning activities, such as selecting dates, work types, effort calculations, and resource selection. Field Service manages resource booking, last-minute work order adjustments, agreements, and preventative maintenance. The solution connects planning in Project Operations with execution in Field Service to create a seamless user experience.

The solution addresses the customer's core concerns and achieves the desired business outcomes. It now provides an end-to-end view of projects, tasks, and bookings for more than 50 business segments, covering simple and complex scenarios. The number of project managers increased to 300. After go-live, project volumes and operational efficiency improved significantly. The solution also provides transparency into project performance to help mitigate project risk. It improves customer satisfaction and business agility. The customer now considers it the go-to platform for all new project management needs. Most screens use familiar Microsoft UI elements, like ribbons and sitemaps, which makes user adoption easy.

## Potential use cases

This solution was created for a telecommunications organization. It can also be applied to any organization who wants to integrate Dynamics 365 Project Operations with Field service to give seamless user experience.

This solution is for a telecommunications organization, but any organization that wants to integrate Dynamics 365 Project Operations with Field Service can use it to create a seamless user experience.

Other use cases:

- Construction companies often manage multiple projects and resources with different timelines. This architecture streamlines project planning, resource allocation, and project progress updates. It's ideal for managing long-term projects.

- Telecom companies that manage infrastructure like towers, antennas, and networks use this solution to schedule maintenance, dispatch technicians, and get real-time updates to ensure network reliability.

## Considerations

These considerations help implement a solution that includes Dynamics 365. Learn more at [Dynamics 365 guidance documentation](index.yml).

- Minimize the transformation rules and processing on Power Automate and move complex transformation logic to Azure functions.

- Develop robust exception handling to address issues during automation.

- Keep resource skills and availability information up to date to ensure proper assignments.

- Make sure you follow industry regulations and standards for data security.

## Cost optimization

Cost optimization means reducing unnecessary expenses and improving operational efficiency. Learn more in [Overview of the cost optimization pillar](/azure/well-architected/cost-optimization/).

The following table lists the components you need to implement the solution with Dynamics 365 Project Operations and Field Service with estimated values for sizes and time.

| Service category | Service type | Custom name | Region | Description |
|----------|----------|----------|----------|----------|
| Compute  | Azure Functions|          | Australia Southeast| Premium tier, Pay as you go, EP1: 1 Cores, 3.5-GB RAM, 250 GB Storage, 1 Prewarmed instance, 1 Additional scaled out units|
| Security | Key Vault |   | Australia Southeast | Vault: 100 operations, 0 advanced operations, 1 renewal, 0 protected keys, 0 advanced protected keys; Managed Hardware Security Module (HSM) Pools: 0 Standard B1 HSM Pools x 730 hours |
| Dev Ops | Azure Monitor |   | Australia Southeast | Log analytics: Log Data Ingestion: 0 GB Daily Auxiliary logs, 5 GB Daily Basic logs, 0 GB Daily Analytics Logs ingested, 1 month of Interactive Retention, 0 months of Retention, 0-GB data restored for 0 days, 0 queries per day with 0-GB data scanned per query, 0 GB of Log Data Exported per day, Platform Log Data Processed per day: 0 GB with Destination to Storage or Event Hub and 0 GB with Destination to Marketplace Partners, 0 Search job Queries per day with 0-GB data scanned per query; 0 System Center Operations Manager (SCOM) MI Endpoints; Managed Prometheus: Using default collection estimation method (with a cluster of {0} Linux nodes, {1} Windows nodes, {2} containers, and {3} pods), 0 Average daily Dashboards users, 7 Dashboards, 50000 Data samples queried per dashboard, 25 promql alerting rules, 25 promql recording rules; Application Insights: 0 GB Daily Analytics logs ingested, 3 months Data retention, 0 Standard Web Tests, 5 Minutes Execution frequency, Executing for 730 hours; 1 resource monitored X 1 metric time-series monitored per resource, 5 Minutes Log Signal frequency with 2 log signals monitored and 1 time series per signal, 0 Additional events (in thousands), 1 Additional email (in 100 thousands), 0 Additional push notifications (in 100 thousands), 0 Additional web hooks (in millions) |
| Support |   |   | **Support** |   |
|   |   |   | **Licensing Program** | **Microsoft Customer Agreement (MCA)** |
|   |   |   | **Billing Account** |   |
|   |   |   | **Billing Profile** |   |

You can optimize the configuration based on your requirements. For example, use a consumption-based Azure function if no transaction takes more than five minutes. In other scenarios, scale up Azure functions with more cores if you need to process a large number of transactions or need more memory. You can also optimize Azure Monitor to reduce daily log data ingestion. The overall cost depends on these factors.

## Implement overall solution

The following table shows the available configurations and the recommended sequence for setting them up from top to bottom. Use the links on **Process step** for more information about each component.

| Process step | Process stage | **Process modifier** | **Application: Navigation and Entity** |
|--------------|--------------|----------------------|-----------------------------------------|
| Install Project Operations App into Dataverse | Install Project Operations App into Dataverse |   | [Deploy Project Operations Core](/dynamics365/project-operations/environment/lite-deployment) |
| Configure Project Operations | Setup project operations |   | [Define project calendars](/dynamics365/project-operations/project-management/define-project-calendars)     |
| Install Field Service App into  Dataverse | Install Field Service App into  Dataverse |   | [Install Field Service](/dynamics365/field-service/install-field-service) |
| Configure Field Services app | Configure Field Services app |   | [Configure default settings](/dynamics365/field-service/configure-default-settings) |
| Add reference data for Project Operations and Field Service                                                   | Add / Sync the reference data such as resources, skills, availability, and related information  |   | [Dynamics 365 Community reference](https://community.dynamics.com/blogs/post/?postid=ad367c2d-e956-4d65-a600-d8f5a20fab19)                           |
| Build an Azure function (Say Fun1) to make API calls to third party mobility application | Process the payload |                      | [Getting started with Azure Functions](/azure/azure-functions/functions-get-started?pivots=programming-language-csharp) |
| Build an Azure function (Say Fun1) to make API calls to third party mobility application   | Make an API call using certificate-based authentication and create ticket of work. |   | [Getting started with Azure Functions](/azure/azure-functions/functions-get-started?pivots=programming-language-csharp) |
| Build an Azure function (Say Fun1) to make API calls to third party mobility application | Implement exceptional handling with retry mechanism |   | [Getting started with Azure Functions](/azure/azure-functions/functions-get-started?pivots=programming-language-csharp) |
| Build Azure function (Say Fun2) to process the inbound requests that come from the third party mobile application |                                                                                                |                      | [Getting started with Azure Functions](/azure/azure-functions/functions-get-started?pivots=programming-language-csharp) |
| Configure Azure Key Vault to store the client certificate |   |   | [Set and retrieve a certificate from Azure Key Vault](/azure/key-vault/certificates/quick-create-portal) |
| Write a Power Automate to trigger when the project task stage is "Ready to Sync" | Call the Azure function (Say Fun1) by passing the necessary information in the form of payload |   | [Set trigger flow](/power-automate/dataverse/create-update-delete-trigger?tabs=classic-designer) |

## Related resources

Use these resources to learn how to integrate Dynamics 365 processes and provide a seamless experience for managing projects.

- Technology article contributed by Vikram Boinapally:
  [https://www.technologyrecord.com/digital/magazine/issue26/170/index.html](https://www.technologyrecord.com/digital/magazine/issue26/170/index.html)

- Webinar session given by Vikram Boinapally: [Microsoft Event](https://mktoevents.com/Microsoft+Event/372957/157-GQE-382)

- Case study:
  [https://tiatra.com/telstra-building-a-better-operations-management-platform/](https://tiatra.com/telstra-building-a-better-operations-management-platform/)

- [Microsoft certification for Dynamics 365 Field Service Functional Consultant Associate](/credentials/certifications/d365-functional-consultant-field-service/?practice-assessment-type=certification)

The following image shows the overall architecture that was implemented. The reference architecture explained in previous sections is part of this overall architecture.

:::image type="content" source="./media/project-operations-field-service-implemented.png" alt-text="Screenshot of Project Operations and Field Service integration implemented architecture." lightbox="./media/project-operations-field-service-implemented.png":::

<!---
## Tags

Industries: Construction (15-17), Manufacturing (20-39),
Telecommunications

Stakeholders: Operations, Project Management, Service operations

Products: Dynamics 365 Field Service, Dynamics 365 Project Operations
--->
## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Vikram Boinapally](https://www.linkedin.com/in/vikram-boinapally-14821318/)
