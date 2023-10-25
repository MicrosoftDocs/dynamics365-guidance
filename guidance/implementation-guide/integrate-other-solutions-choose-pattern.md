---
title: Choose a pattern for integration
description: Find guidance on how to choose the right integration pattern for your Dynamics 365 apps integration strategy.
author: abunduc-ms
ms.author: abunduc
ms.date: 05/23/2023
ms.topic: conceptual

---
# Choose a pattern for integration

Choosing the right pattern is a critical part of successfully implementing integration between systems. When choosing an integration pattern, consider factors such as its main functionality. Also consider how it's built, including platform, language, user interface, and the connectivity type it handles. We recommend that you also consider what type of actions you need the integration to perform, such as the following list:

- **Data types and formats**  

  What types of data are you sending? Transactional, text, HTML?

- **Data availability**  

  When do you want the data to be ready, from source to target? Is it needed in real time? Or must you just collect all the data at the end of the day and send it in a scheduled batch to its target?

- **Service protection and throttling**  

  When you use certain integration patterns, service protection might be built in so that there's a maximum number of records allowed because the performance decreases with quantity. Sometimes the provider places this limitation on yo. In other cases, if you're offering integration points to other systems, you want to impose a limitation or throttling to make sure that the general performance of your system isn't influenced by traffic from external requests.

- **Transformation of data**  

  Do you want to convert or aggregate transactional data into analytical data? Are you changing .txt to HTML?

- **Triggers**  

  What action triggers sending data from the source to the target?

- **Trigger actions**  

  Do you want specific actions to be automated after the data arrives at the target?

- **Process error handling**  

  What type of monitoring do you put in place to detect any issues with the interfaces? What type of alerts do you want to handle the patterns that you'll use?

- **Flow direction**  

  Is the flow bidirectional or unidirectional?

- **UI**  

  The UI determines how the data is going to be displayed once it arrives at the target system. The UI determines the user experience; how the user interacts with and handles the information.

- **Scalability**  

  How does the interface pattern handle the expected transaction volumes in the present, short term, and long term? What would happen if you exceeded those expectations?

## Pattern directions

Let's take a closer look at some common patterns for individual integrations and the pros and cons for each. This table is generalized; learn more at [Product-specific guidance](integrate-other-solutions.md).

| Pattern | Mechanism | Trigger | Considerations | Use when |
|-------------------------|-------------------------|-------------------------|-------------------------|-------------------------|
| Real time or synchronous | Data is exchanged synchronously, invoking actions via services. | User action or system event. | Pros: Fast request and response round trip. Real-time values and information.</br>Cons: Small payloads. Action-reaction can cause tight coupling of systems. Risk of ripple effect from transient errors. Sensitive to latency. | Generally, not a best practice to use because of the risk of processes getting stuck and solutions that are fragile.</br>Use when real-time information is critical. |
| Asynchronous | Data is exchanged unattended on a periodic schedule or as a trickle feed using messaging patterns. | Scheduled and user initiated. Can wait for off hours or idle time. | Pros: Loose coupling of systems makes the solution robust. Load balancing over time and resources. Can be very close to real time. Timely error handling.</br>Cons: Delay in response and visibility to changes across systems. | Most recommended integration patterns and technologies supported are asynchronous, although they can be near real time. |
| Push | One system puts (pushes) data into another. Information flows from the originator to the receiver. | Originating system user or system event. | Pros: If technical expertise lies within the pushing system, the custom effort lies here. Good for reactive scenarios.</br>Cons: Pushing system might not have visibility into availability and load and idle times in the receiving system. | For reactive scenarios.</br>Receiving system provides a turnkey API and organization's developer skill set is with the originating system. |
| Pull | Receiving system requests data from the originator, a subtle but significant difference from the Push pattern. | Receiving system request based on schedule. | Pros: If technical expertise lies within the pulling system, the custom effort lies here. Good for proactive scenarios. Clear visibility into availability and load and idle times in the receiving system.</br>Cons: Originating system might not have the APIs needed to pull from. | For proactive scenarios.</br>Maybe we can't add triggers or events in the originating system. Originating system provides a turnkey API and organization's developer skill set is with the receiving system. |
| One-way sync | Data from one system is synchronized to another by one or more trigger events. | Data state, system, or user event. | Pros: Establishes a clear system of record. Simple conflict resolution.</br>Cons: Sometimes the receiving system or non-system of record doesn't have built-in capability to make the data read only, which can confuse users. | One system is owner or system of record and other systems consume that data.</br>Consider scenarios in which the originating table is a subset of a similar table in the target. |
| Bidirectional sync | Data from two or more systems are synchronized. | Data state, system, or user event. | Pros: Data is kept in sync across applications. Acquired divisions on multiple platforms can continue to use their existing systems. Users can use their system to make changes.</br>Cons: Complex conflict resolution. Redundant data is replicated for each system. Synchronized data might be a subset of data in systems. The rest must be automatically given values or manually updated later. | Scenarios in which there isn't a clear system of record.</br>Data from best-of-breed systems should be available in Dataverse for Power Apps and other tools and services. |
| Aggregation | Data from a specialized system is integrated to another system on an aggregated level for processing or reporting. | Any. | Pros: Detailed data is kept in the system where it's used. Aggregation can derive a small dataset from a large one, thus limiting traffic across platforms.</br>Cons: Users often expect to be able to drill down to the detailed level. While drill-down doesn't require embedding, it does require more integration complexity or users operating in two systems. | Aggregates are needed to calculate or process on-hand inventory by warehouse, revenue by invoice header, revenue by customer by day, or operational data for posting in a finance system, among other things. |
| Embedding | Information from one system is seamlessly integrated into the UI of another system. | User event. | Pros: Simple because the data remains in the originating system.</br>Cons: Difficult to use the data for calculations for processing. | A mix of information from first-party applications (for example, Bing, Power BI, and Exchange), third-party components, canvas apps, or other information embedded in the UI of an application.</br>This is common practice in customer engagement apps. |
| Batching | Batching is the practice of gathering and transporting a set of messages or records in a batch to limit chatter and overhead. | Any. | Pros: Great for use with messaging services and other asynchronous integration patterns. Fewer individual packages and less message traffic.</br>Cons: Data freshness is lower. Load in the receiving system can be affected if business logic is executed on message arrival. | Whenever it isn't necessary to transmit individual records. |

Synchronous integration patterns and near real-time patterns are often mischaracterized and mistakenly used interchangeably.

An example of a synchronous integration pattern is a process in which a user performs a web service-based lookup of current on-hand values from one system to another. In this example, the user waits for a response before continuing the process, thus making the process both latency and availability dependent. Also known as *coupling*, generally avoid these use cases.

A near real-time pattern for the same design scenario is a system with fresh on-hand inventory information every one to three minutes. Here, users can continue the process even if there's a transient outage in the providing system or the supporting architecture. This pattern combined with using a messaging-based integration architecture results in a robust solution.

> [!NOTE]
> When choosing a specific pattern, it's important to take a broader look at the integration context.

## Messaging patterns, middleware, and service bus

A service bus refers to asynchronous messaging on a well-equipped messaging platform that includes a service-based channel and endpoint connectors. It's a common, modern way of managing complex integration architecture across distributed systems. The messaging platform is often referred to as the *middleware*, and it often offers services such as the following list:

- Message routing and message orchestration  
- Transformation, and even in some cases, load balancing message error handling  
- Monitoring, logging, and notification services  

Messages are pieces of information or datasets that can be transferred between systems. Each message can contain instructions such as an event fired or a delete request, or it can contain a payload like a record or dataset. Some messaging platforms allow for prioritizing messages based on type, origin, destination, or payload.

Modern messaging platforms are based on service endpoints, REST, and JSON, but the platforms can offer many other features. Connections between endpoints are called channels and the message paths are called routing.

The benefit of messaging patterns is that the messaging platform handles the flow of information between systems. It detects transient outages in individual systems or service endpoints, and handles the queueing of messages to the affected systems until they're back online. Below we can see the typical components of a messaging platform.

:::image type="content" source="media/integrate-other-solutions-messaging-platform-components.png" alt-text="Components of a messaging platform" lightbox="media/integrate-other-solutions-messaging-platform-components.png":::

The asynchronous nature of the messaging patterns allows for a robust, decoupled integration architecture with less manual intervention and lower maintenance costs.

When implementing a messaging pattern, consider the following items:

- **Frequency and volume**  

  It's critical to have a clear picture of the frequency and transactional volume of data that will go through the interface. Also include how that load is distributed over time, and what the requirements are in the longer term.

- **Idempotency and out-of-order messages**  

  Mechanisms are available to ensure that the messages are idempotent, for example, using a message ID to check whether the message is a duplicate or an out-of-order message. Services such as Azure Service Bus support this capability and allow you to implement it without the need for more code.

- **Service-level agreement (SLA) or end-to-end cycle latency**  

  Consider whether there are minimum requirements for how fresh the data in the receiving system must be. For example, orders taken on an e-commerce site should reach the warehouse in less than five minutes.

- **Triggers and actions end-to-end process**  

  It's also important to look at the cross-system business process in the bigger picture:

  - What happens before the integration steps?
  - Is there a potential risk of introducing semantic errors earlier in the process?
  - What event triggers the integration?
  - Does the integration trigger action in the receiving system?
  - What business process steps happen after the integration steps are done?
  - If an error is identified, logged, and notified, how is the problem corrected? How often might errors occur, how long might it take to correct them, and who is responsible for making the corrections?

- **Batching**  

  Batching messages or datasets enables less frequent communication, or "chatter". But it also typically makes messages and payloads bigger.  

  - Do the requirements support a batched approach in which datasets are consolidated into each message, or does the integration require individual records or rows?
  - If a batched approach is suitable, how many rows and records are in each message?
  - Are there service protection volume limits to consider?

- **Topology and architecture**  

  Topology and architecture are important considerations for the short and long term. Both as your organization grows internationally, or as you migrate systems to the cloud and have to address new challenges and considerations.  

  - Are there integration components that span the cloud and on-premises boundary? Does the messaging service handle that?
  - Where in the world is the data located, and does the inherent latency between geographic regions support the requirements?
  - Does any data exist in countries or regions of the world that have local privacy policies and regulations?
  - Are there service protection limitations in technology? Protocol or platform dependencies in any of the integrated systems?
  - Does the data exchanged require transformation, reformatting, or remapping as part of the integration?

Learn more at [Messaging services on Azure](https://azure.microsoft.com/solutions/messaging-services/#overview).

We highly recommend that when you design integration, you don't assume that everything always works as intended. In fact, when working with integration, there are many external factors that we often can't completely control. Therefore, we need to make sure that our integrations are robust by design, which we discuss in the next section.

## Mind the errors

Designing for failure is a crucial component of architecting any solution, including integration components. As part of the integration architecture, it's important to incorporate the following items:

- **Error logging**  

  Select the platform (such as a log file or database) to log the errors.

  - Error monitoring and notifications

    - Define the process and technical approach to monitor errors.
    - Select an error notification approach, which is the process to notify administrators and other stakeholders if there's an error. Business-critical errors might need a different notification approach than non-critical errors.

- **Business continuity**  

  It's important to plan for business continuity with minimal disruption to business if errors occur. Learn more at [Service the solution](service-solution.md).

With more integration touchpoints, the potential for errors grows. Therefore, error handling also needs to be planned in accordance with the integration scenario. For example, in the scenario of a synchronous integration pattern, an error might require a complete rollback of the entire process. In an asynchronous data integration scenario, in contrast, it might be acceptable to fix a data issue just by notifying the administrator.

:::image type="content" source="media/integrate-other-solutions-error-handling.png" alt-text="Error handling" lightbox="media/integrate-other-solutions-error-handling.png":::

Let's now discuss error management for two key patterns of synchronous and asynchronous integration.

As a reminder, in a synchronous integration pattern, each step is dependent on the completion of a preceding step. If an error occurs, consider a retrial or rollback. Which option to use depends on whether the error is transient or persistent. In the scenario of a transient error, the normal behavior of the application will resume after a few retries. Retrial limits should be predefined to avoid a situation in which all resources are blocked. Once the retrial limit has been crossed, the entire process needs to be rolled back, and appropriate error messages should be logged.

For an asynchronous integration, the error management strategy might differ depending on your business requirements. Consider creating a queue that can continue to validate the message being exchanged and retry until the retrial limit is reached. The message that fails from being exchanged can also be stored in another queue for later intervention.

Transient errors such as network timeouts get fixed after a few retries. However, persistent errors require intervention to be fixed.

An important consideration as you build your retrial mechanisms is to ensure that your requests are idempotent. This way, you prevent data duplication issues due to retries.

The following are some of the most common error scenarios in any integration between Dynamics 365 and other applications:

- System becomes unavailable

- Authorization and authentication errors

- Errors caused by platform limits

- Errors caused by service protection limits that are applied to secure service levels

  - API limits (limits allowed based on the user license type)
  - Throttling
  - Process errors
  - Runtime exceptions

It's critical to plan error logging, monitoring, and communication as part of an overall error-handling approach. Logging errors with the exact timestamp and message details helps the implementation team and application owners troubleshoot the errors. Error tracking also enables the application owners to identify potential areas of improvement in their process by reviewing frequent errors, if any. Below we see a persistent blocking error. The platform supports logging and notifications so that an administrator can be notified and resolve the issue.

:::image type="content" source="media/integrate-other-solutions-error-handling-notification.png" alt-text="Error handling with notification" lightbox="media/integrate-other-solutions-error-handling-notification.png":::

## Monitoring and alerting

The monitoring design highly depends on the integration design. The general principles guiding the monitoring/alerting implementation are outlined in the next subsections.  

### Completeness

The monitoring design should cover all the systems that are contributing to the integration landscape. For example, if the integration scenario includes Dynamics, Logic Apps, a middleware, and a third-party application, all the listed parties should be included in the monitoring and error handling strategy since a failure may occur at any step.

### Clarity

The monitoring system must be implemented to provide a clear understanding of the integration system's status. It might include error notification, error logging, messaging status, monitoring dashboards, and reports. The monitoring architecture should also provide easy understanding of the type of issue encountered and avoid any ambiguity regarding the resources involved.

### Alerting/Notification capabilities

Each monitoring system should be designed to have the required alerting capabilities. It doesn't mean that each type of error should be notified to the monitoring team, but the alerting capabilities must be implemented for critical patterns and business processes to enable the IT team for fast reaction.

### Robustness

The monitoring system should be designed for robustness, so it doesn't become a point of failure in itself. One of the most effective ways to do so is to use the embedded monitoring capabilities of the tools involved in the integration scenarios. For example:

- The Data Management Framework (DMF) in Dynamics 365 finance and operations apps has embedded monitoring and logging capabilities to investigate integration issues. Learn more at [Troubleshoot data package processing](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities-data-packages#troubleshoot-data-package-processing) and [Data management error descriptions](/dynamics365/fin-ops-core/dev-itpro/data-entities/dm-error-descriptions).

- Synchronous outbound connections provide immediate feedback that can be notified to the user through UI or stored in the system.

- Azure Monitoring can be used for any Azure tool involved (Logic Apps, Azure Functions, Event Grid, etc.) to centrally store logs and provide clear visibility through dashboards. Azure Monitor can also be used for custom signaling from any application, including Dynamics (customization required).

- Third party applications and middleware usually provide embedded monitoring capabilities that can be used out-of-the-box. Most third-party middleware can provide monitoring information in the form of signals external monitoring tools the collect, such as Azure Monitor.

- First party Dual-Write integration provides a consolidated view to enable error management ([Error management and alert notifications](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/errors-and-alerts)).

### Scalability

As per the previous point, the monitoring system should never become a bottleneck forcing the monitored integration scenarios to wait for the monitoring system to process. Most of the monitoring systems can be set up to receive and process asynchronously the signals from the integration components.

### Security/privacy

The monitoring system must never violate the security principles applied in the application design. This aspect includes the tool security, such as access to the tool, information encryption, storage security, and so on. It also applies to the privacy aspects of the information passed. We recommend that you pay particular attention to the privacy requirements and regulations <!--Removed GDRP> (e.g., GDPR)--> to avoid storing or showing sensible information.

## Monitoring Design

Dynamics 365 provides both embedded notification capabilities and the ability to use external notification/distribution systems.

### Internal app notifications

For synchronous scenarios, Dynamics 365 provides immediate alerting through the standard info messages from the application. If the user is triggering a synchronous integration, errors in the process are immediately notified with a pop-up message and stored in the message list. If the same synchronous integration is triggered in the context of a batch process, the same messages can be retrieved in the job history. For Finance and Operations Apps, the Data Management Framework stores the errors in tables (job history and execution details), for the asynchronous integrations. In this case, the standard alerting system or batch notifications can be used to notify selected users when a job has failed/partially failed. Another common scenario includes batch processing the information passed by an integrated system. In this scenario the errors could appear way after the data has been provided to dynamics, during its processing/consolidation/manipulation. Of course, it's possible to use standard messaging and alerting in the batch framework but also include in the custom process a custom logging/monitoring systems for complex scenarios.  

> [!NOTE]
> Both the batch framework and the alert rules can be used to trigger business events and provide information outside Dynamics 365. Learn more ([Alerts as business events](/dynamics365/fin-ops-core/dev-itpro/business-events/alerts-business-events) and [Batch business events](/dynamics365/fin-ops-core/dev-itpro/business-events/system-business-events)).

### External notifications

For external notifications, Microsoft provides multiple options depending on the complexity of the scenario and its purpose. Probably the simplest one would be using Power Automate to generate alert notifications based on Dynamics 365 triggers. The standard trigger can be a business event provided by the batch framework or the Alert rules. Learn more at [Business events in Microsoft Power Automate](/dynamics365/fin-ops-core/dev-itpro/business-events/business-events-flow).  

Power Automate includes an OOB notification system that can be attached to a flow mobile app or to an email account. Learn more at [Notifications](/connectors/flowpush/). For more general information dissemination, the same business events can be subscribed by [Azure Event Grid](/dynamics365/fin-ops-core/dev-itpro/business-events/home-page#create-an-azure-event-grid-endpoint). The system can then redistribute the information to other systems, including Azure Service Bus, Logic Apps, and Azure Monitor (Application Insights). From any of the previous applications, your monitoring and notification system can then follow the route and expand with any complexity required.

It's also important to identify owners who should receive error details through notification as part of regular monitoring. The monitoring and notification approach might differ for business-critical errors versus non-critical errors. In scenarios with a mission-critical application integration, some organizations might choose to send text notifications to the administrators to speed up the process.

Error messages displayed to end users through the UI should be clear, precise, and short. They should also include information users can act on, such as point of contact information or a link to an FAQ. It makes the user experience a more positive one and should be considered a best practice as part of error handling.

## Azure Monitor and Application Insights

Another potential path to create external notifications is to send signals directly to Application Insights. The capability already exists out-of-the-box for Dynamics 365. Learn more at [Analyze model-driven apps and Microsoft Dataverse telemetry with Application Insights](/power-platform/admin/analyze-telemetry). <!-- and a similar functionality for Finance and Operations Apps is under evaluation.--> Sending signals to Application Insights can also be achieved through a simple Dynamics 365 extension using API and examples already provided for .NET applications ([Application Insights API for custom events and metrics](/azure/azure-monitor/app/api-custom-events-metrics)).

The advantage of this approach is to provide extreme flexibility in the way the information is generated and distributed. On the other hand, it's important to design the signaling system in a way that doesn't hurt the systems involved, especially Dynamics 365. For example, it's important to avoid overwhelming the application with telemetry information to send outside or attach those signals to massive processes that could cause thousands of signals in a short period.  

### Dashboards

Microsoft doesn't mandate or provide guidance on the way the dashboards must be designed in Application Insights. Everything depends on the type of information to provide, and the signals ingested. One thing to highlight is that Azure App Insights isn't provided to standard users but used by IT teams or power users at minimum. Learn more at [Azure Application Insights Overview Dashboard](/azure/azure-monitor/app/overview-dashboard) and [Create custom dashboards in Azure Application Insights](/azure/azure-monitor/app/tutorial-app-dashboards).

To summarize, error logging and monitoring have a significant impact on the following key factors and therefore are considered essential:

- Application health including performance and stability

- Ease of troubleshooting and resolving errors

- Minimize business impacts when errors occur

- Increase user satisfaction

Learn more at [Product-specific guidance](integrate-other-solutions-guidance-product.md).

## Next steps

- [Define business goals](integrate-other-solutions-business-goals.md)  
- [Choose a platform](integrate-other-solutions-choose-platform.md)  
- [Choose a design](integrate-other-solutions-choose-design.md)  
- [Challenges](integrate-other-solutions-challenges.md)  
- [Product-specific guidance for integration scenarios](integrate-other-solutions-guidance-product.md)  
- [Checklist](integrate-other-solutions-checklist.md)  
- [Case study](integrate-other-solutions-case-study.md)  
