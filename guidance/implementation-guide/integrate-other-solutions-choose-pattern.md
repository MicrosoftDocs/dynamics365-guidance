---
title: Choose the right pattern for your Dynamics 365 apps integration strategy
description: Learn how to pick the best integration pattern for your Dynamics 365 apps to ensure a seamless system implementation.
author: abunduc-ms
ms.author: abunduc
ms.date: 01/26/2024
ms.topic: conceptual
ms.custom:
  - ai-seo-date: 01/26/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Choose the right pattern for your Dynamics 365 apps integration strategy

Selecting the ideal pattern is crucial for a smooth integration between systems. When you're deciding on an integration pattern, think about its functionality, how it's structured&mdash;including platform, language, and the user interface (UI)&mdash;and the kind of connectivity it handles. Also, consider the actions you want your integration to manage, such as:

- **Data types and formats**: What kind of data are you sending&mdash;transactional, text, HTML?
- **Data availability**: When do you need the data ready? Is real-time essential, or is end-of-day collection sufficient?
- **Service protection and throttling**: Some patterns come with built-in service protection that limits records because too many can slow things down. This cap might come from the provider, or you might set it yourself to keep your system running smoothly.
- **Transformation of data**: Do you need to turn transactional data into analytical data or change .txt files into HTML?
- **Triggers**: What initiates the data transfer from source to target?
- **Trigger actions**: Are there specific actions that should automatically occur once the data arrives?
- **Process error handling**: How will you monitor interfaces and manage the patterns in use?
- **Flow direction**: Is data moving in both directions or just one?
- **User interface**: The UI shapes how data looks when it arrives at the target system and how users interact with it.
- **Scalability**: Can the interface pattern handle your current and future transaction loads? What if it exceeds expectations?

## Commons patterns for integration

Let's explore some common patterns for individual integrations and weigh their pros and cons. This table gives you a snapshot. [Get product-specific guidance](integrate-other-solutions.md).

| Pattern | Mechanism | Trigger | Considerations | Use when |
|---------|-----------|---------|----------------|----------|
| Real time or synchronous | Data swaps hands synchronously, sparking actions via services. | User action or system event. | Pros: Quick back-and-forth. Up-to-the-minute values and information.<br>Cons: Only small payloads. Can lead to systems being too dependent on each other. Sensitive to delays. | You can't do without real-time information. |
| Asynchronous | Data moves on its own, either on a set schedule or bit by bit using messaging patterns. | Scheduled or user-initiated. Can wait for downtime or quiet periods. | Pros: Systems aren't too reliant on each other, making for a sturdy solution. Balances loads over time. Can be almost real-time.<br>Cons: There's a wait for responses and updates across systems. | Most recommended integration patterns and technologies are asynchronous but can feel like real-time. |
| Push | One system sends (pushes) data to another, from sender to receiver. | Sender's user or system event. | Pros: If your expertise is on the pushing side, that's where you'll focus your custom work.<br>Cons: The pushing system might not see when the receiving system is ready or busy. | The receiving end has a ready-to-go API, and your team's skills are with the sending system. |
| Pull | The receiving system asks for data from the sender, a small but important twist on pushing. | Receiver's request based on schedule. | Pros: If your expertise is on the pulling side, that's where you'll focus your efforts.<br>Cons: The sender might not have the APIs it needs to pull from. | You can't add triggers or events in the sender system but it has a ready-to-go API and your team's skills are with the receiver system. |
| One-way sync | Data from one system syncs up with another after certain events trigger it. | Data state, system, or user event. | Pros: Sets a clear record keeper. Simple conflict solving.<br>Cons: The receiver might not be able to lock down data as read-only, which can be confusing for users. | One system owns the data and others use it.<br>Think about cases where the sender's table is just part of a similar table in the receiver's domain. |
| Bidirectional sync | Data from two or more systems stay in sync with each other. | Data state, system, or user event. | Pros: Keeps data in sync across apps. Lets new divisions keep their systems. Users can make changes in their preferred system.<br>Cons: Tricky conflict resolution. Data gets copied for each system. Some data might need manual updates later. | There's no clear record keeper.<br>Data from top-notch systems should be ready to go in Dataverse for Power Apps and other tools and services. |
| Aggregation | Specialized system data rolls up to another system for processing or reporting. | Any. | Pros: Detailed data stays where it's most used. Limits traffic by boiling down big data sets.<br>Cons: Users might want to dig into the details, which means more integration work or using two systems. | You need to crunch numbers or process things like inventory by warehouse, daily revenue by customer, or financial data for posting. |
| Embedding | information from one system is seamlessly integrated into another's UI. | User event. | Pros: Easy since the data stays put in its home system.<br>Cons: Tough to use this data for crunching numbers or processing. | You're mixing information from in-house apps (like Bing, Power BI, and Exchange), non-Microsoft components, canvas apps, or other information embedded in an app's UI.<br>It's what you often see in customer engagement apps. |
| Batching | Groups messages or records to cut down on noise and overhead. | Any. | Pros: Works well with messaging services and other asynchronous patterns. Fewer individual messages mean less traffic.<br>Cons: Data isn't as fresh. The receiver's load might spike if business logic kicks in when messages arrive. | Sending individual records isn't a must-have. |

Synchronous integration patterns and near-real-time patterns often get mixed up and wrongly swapped.

Consider a synchronous pattern where you look up current stock values from one system to another in real-time, waiting for an answer before moving on. It hinges on speed and availability. Now, imagine a near-real-time pattern that updates stock information every few minutes, letting you carry on even during an outage.

When you're picking a pattern, zoom out for a wider view of the integration landscape.

## Messaging patterns, middleware, and service bus

*Messages* are bits of information that move between systems, carrying instructions like events or delete requests, or payloads like records. Connections between endpoints are called *channels* and the message paths are called *routing*. The messaging platform is often referred to as the *middleware*, and it often offers services like message routing and orchestration, transformation, and monitoring, logging, and notification. A service bus refers to asynchronous messaging on a platform with service-based channels and endpoint connectors. It's a common way to handle complex integrations across distributed systems.

Messaging patterns shine because they manage the flow of information, spot outages, and hold onto messages until everything's back up and running. The following diagram shows the typical components of a messaging platform:

:::image type="content" source="media/integrate-other-solutions-messaging-platform-components.png" alt-text="Diagram illustrating the components of a messaging platform, including service-based channels, endpoint connectors, and the flow of messages between systems." lightbox="media/integrate-other-solutions-messaging-platform-components.png":::

When you're setting up messaging patterns, think about these factors:

- **Frequency and volume**: Have a clear picture of how often and how much data will pass through, how it's distributed over time, and what might be required in the longer term.
- **Idempotency and out-of-order messages**: Idempotency ensures that if a message is sent more than once, such as a retry after a failure, the receiving system processes it only once. Use things like message IDs to check whether a message is a duplicate or out of order. Services like Azure Service Bus do this without extra coding.
- **Service-level agreement (SLA) or end-to-end cycle latency**: Determine the minimum freshness your data needs. For example, orders taken on an e-commerce site should reach the warehouse in less than five minutes.
- **Triggers and actions end-to-end process**: Map out the whole business process across systems, including triggers and actions. This helps you spot any gaps and figure out how to handle errors.
  - What leads up to integration?
  - What sets it off?
  - Does integration prompt action in the receiver system?
  - What comes after integration?
  - How do you spot, log, notify, and fix errors?
- **Batching**: Grouping messages means less "chatter" but usually bigger messages. Can your needs handle batching? How many rows or records per message? Are there any limits on volume?
- **Topology and architecture**: Think about your setup now and down the line. For instance:
  - Do you have any cloud or local components?
  - Where is the data, and will latency between geographic regions support your requirements?
  - Do any local privacy policies and regulations apply?
  - Are there limits on service protection?
  - Does the data that's exchanged need to be transformed, reformatted, or remapped as part of the integration?

[Learn more about messaging services on Azure](https://azure.microsoft.com/solutions/messaging-services/#overview).

When you're designing integration, it's wise to plan for the unexpected. There are many external factors beyond our control, so it's essential to build integrations that are robust from the get-go. We'll dive into how to do just that in the next section.

## Mind the errors

Planning for failures is critical. The more integration touchpoints you have, the more likely it is that something will go wrong. Weave error logging, keeping watch, and continuity plans into your design to keep disruptions to a minimum.

How you handle errors depends on the pattern. For synchronous ones, think about trying again or undoing actions based on whether errors are transient or persistent. For asynchronous integrations, set up queues for checking and redoing actions, keeping aside any failed messages to fix later.

Make sure your requests can't be duplicated because of retries. Keep them unique, or idempotent.

Some of the most common error scenarios include system downtime, sign-in issues, and hitting platform limits or service caps like API limits, throttling, process errors, and runtime exceptions.

It's critical to make error logging, monitoring, and communication part of your overall plan for handling errors. Detailed logs help implementation teams and application owners fix problems faster. Error tracking also helps application owners identify potential areas of improvement.

### Monitoring and alerting

How you monitor for errors should match your integration setup. The monitoring system needs to cover all systems that are contributing to the integration landscape and give you a clear picture of how the integration is running. Set up alerts for key patterns and processes so that your IT team can address issues quickly.

Make sure your monitoring system is sturdy, so that it doesn't become a point of failure itself. The best way to do this is by using the built-in monitoring features of the tools you're already working with.

- The Data Management Framework in Dynamics 365 finance and operations apps comes with monitoring and logging to help you investigate integration issues. Learn more about [troubleshooting data package processing](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities-data-packages#troubleshoot-data-package-processing) and [data management error descriptions](/dynamics365/fin-ops-core/dev-itpro/data-entities/dm-error-descriptions).
  
- Immediate feedback from synchronous outbound connections can alert users through the UI or be logged in the system.

- Azure Monitoring works with any Azure tool, like Logic Apps, Azure Functions, and Event Grid, to keep logs centralized and dashboards clear. You can also customize it to get signals from any app, including Dynamics 365.

- Partner apps and middleware often come with ready-to-use monitoring features. They can send monitoring information as signals to external tools like Azure Monitor.

- Dual-write integration in Microsoft apps gives you a unified view for managing errors [Learn more about error management and alert notifications](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/errors-and-alerts).

Your monitoring system should never slow down your integrations. Most systems can be set up to handle signals from your integration components asynchronously.

It must also comply with the security principles of your app design. This includes tool security, like access, encryption, and storage, and privacy of the information that's passed. Pay particular attention to privacy laws and regulations to ensure you're not storing or displaying sensitive data.

### Notifications

Dynamics 365 not only provides embedded notification features but also allows you to tap into external notification systems for greater flexibility.

#### Internal app notifications

For those times when immediate action is needed, Dynamics 365 ensures you're alerted without delay through standard informational messages. If you trigger a synchronous integration and run into an error, a prompt pop-up message informs you, with the details neatly stored in the message list. If this integration is part of a batch process, you can revisit those messages in the job history.

For finance and operations apps, the Data Management Framework diligently logs errors in tables (job history and execution details) for asynchronous integrations. Here, you can count on the standard alerting system or batch notifications to keep relevant users informed about any job failures or partial failures. When data from an integrated system is batch processed, errors might show up later, like when the data is processed or consolidated. While standard messaging and alerts within the batch framework have you covered, setting up a custom logging or monitoring system could be a smart move for keeping track of more complex scenarios.

Both the batch framework and the alert rules can trigger business events and provide information outside Dynamics 365. Learn more about [alerts as business events](/dynamics365/fin-ops-core/dev-itpro/business-events/alerts-business-events) and [batch business events](/dynamics365/fin-ops-core/dev-itpro/business-events/system-business-events).

#### External notifications

Microsoft offers a range of options for external notifications, each designed to fit the complexity and objectives of your scenario. A convenient choice is using Power Automate to set up alert notifications that respond to Dynamics 365 events. These triggers can come from business events within the batch framework or alert rules. [Learn more about business events in Power Automate](/dynamics365/fin-ops-core/dev-itpro/business-events/business-events-flow).

Power Automate has an [integrated notification system](/connectors/flowpush/) that can be connected to a mobile app or an email account. For a broader reach, [Azure Event Grid](/dynamics365/fin-ops-core/dev-itpro/business-events/home-page#create-an-azure-event-grid-endpoint) can subscribe to these business events and distribute the information to other systems, including Azure Service Bus, Logic Apps, and Azure Monitor (Application Insights). Your monitoring and notification system can then scale and evolve as necessary.

Identifying individuals who should receive error details is an important part of regular monitoring. Your approach to monitoring and notifications might change depending on the severity of the errors. In situations where an application integration is critical, some organizations might opt to send text notifications to administrators for a quicker response.

Error messages that are shown to users need to be clear, precise, and brief. They should also include information that users can act on, such as contact details or a link to an FAQ. This not only enhances the user experience but is also a smart practice in error management.

### Azure Monitor and Application Insights

You can also create external notifications by sending signals straight to Application Insights, a feature that's ready to use with Dynamics 365. [Learn how to analyze model-driven apps and Dataverse telemetry with Application Insights](/power-platform/admin/analyze-telemetry). You can send signals to Application Insights through a simple Dynamics 365 extension using the provided API and examples for .NET applications. [Learn how to use the Application Insights API for custom events and metrics](/azure/azure-monitor/app/api-custom-events-metrics).

This method offers great flexibility in generating and sharing information. However, it's important to design your signaling system carefully to avoid overwhelming the integrated system with too much telemetry data or triggering an excessive number of signals in a short time.

What you see on Azure App Insights dashboards depends on what information and signals you feed it. [Learn more about Azure Application Insights dashboards](/azure/azure-monitor/app/overview-dashboard).

To summarize, error logging and monitoring are essential because they have a direct impact on:

- Keeping your application healthy, ensuring it performs well and remains stable
- Streamlining the process of finding and fixing errors
- Reducing the ripple effect of errors on your business operations
- Keeping users happy and productive

## Next steps

- Find out what challenges you might face when integrating systems and how to overcome them with [best practices](integrate-other-solutions-challenges.md)
- Learn about the aspects that are specific to each Dynamics 365 app and how to [integrate them with other solutions](integrate-other-solutions-guidance-product.md)
- Use this Solution by Design [checklist](integrate-other-solutions-checklist.md) to make sure you've covered all the steps and considerations for your integration project
- Read how a public sector infrastructure organization learned how to [choose the right solution for their integration project](integrate-other-solutions-case-study.md)
