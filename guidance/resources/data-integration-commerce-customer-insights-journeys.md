---
title: Data integration between Commerce and Customer Insights - Journeys.
description: Learn how to implement near‑real‑time, synchronous data integration from Dynamics 365 Commerce into Dynamics 365 Customer Insights – Journeys using the Commerce Event Framework, Azure Integration Services, and GitHub‑provided samples to support transactional and loyalty‑driven marketing scenarios.
author: OfficerSpears
contributors: liamkerrigan, meenulaul, petkra, tchilaud
ms.author: raphel
ms.reviewer: edupont
ms.topic: concept-article
ms.date: 07/22/2025
---

# Data integration from Dynamics 365 Commerce to Customer Insights - Journeys in near real-time

In today's dynamic retail landscape, delivering exceptional customer experiences is critical. Customers engage with brands across multiple channels—physical stores, online platforms, and mobile apps—and expect seamless, personalized interactions at every touchpoint. To meet these expectations, retailers need systems that communicate efficiently and in near real-time.

This article describes near real-time marketing processes that require synchronous data integration from Dynamics 365 Commerce to Dynamics 365 Customer Insights – Journeys. It focuses on the following main themes:

- **Automated transactional emails**, such as order confirmations, feedback requests, and review prompts.
- **Enhanced loyalty scenarios**, including post-purchase invitations to join loyalty programs.

To illustrate these processes, this article shows how to implement a *Commerce Event Framework* that creates events, stores them in an event store, follows a *Command Query Responsibility Segregation* (CQRS) pattern, and integrates the events with Customer Insights – Journeys through Azure Integration Services. The article uses a sample from the implementation assets GitHub repo at [CommerceEventSample](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Commerce/CommerceEventSample). This sample contains all the custom assets that form the foundation of the solution and makes it easier for you to replicate and adapt this approach in your own environment.

While this approach demonstrates direct near real-time integrations, asynchronous options might better suit certain business cases. For example, the Commerce Data Exchange (CDX) flow between Commerce Scale Unit (CSU) and other finance and operations apps supports downstream integrations with Dataverse. This integration uses dual-write capabilities or custom connectors. Business and technical teams should evaluate each option based on factors such as data latency tolerance, system dependencies, and operational scale.

## Business opportunities

Why integrate Dynamics 365 Commerce with Customer Insights – Journeys? Let's examine the business opportunities that this approach brings you.

### Nurture the complete customer journey

To truly nurture your customers, it's essential to connect with them at every stage of their journey. You welcome first-time visitors, and you want to keep loyal customers engaged, so you want to craft each interaction to make them feel valued. This approach goes beyond individual touchpoints—it builds a relationship that evolves from the moment they discover your brand to every subsequent purchase and interaction.

With the integration of Dynamics 365 Commerce, Customer Insights - Journeys, and Customer Insights - Data, you can guide your customers seamlessly through every step. Imagine offering a warm greeting and discount to a first-time visitor, following up on abandoned carts, or sending personalized recommendations based on browsing behavior. This powerful combination enables you to deliver engaging experiences across purchase, retention, and loyalty stages—turning casual shoppers into brand advocates.

### Elevate customer engagement across all touchpoints

Modern retailers understand that personalized customer engagement is key to building loyalty and driving sales. By integrating Dynamics 365 Commerce with Customer Insights – Journeys, retailers can deliver timely, relevant communications that enhance the customer experience across all channels.

Moreover, Customer Insights - Journeys builds rich hyper-personalization of communications based on [profiles](/dynamics365/customer-insights/journeys/real-time-marketing-ci-profile) in Customer Insights - Data. By applying what we know about the customer's preferences, behaviors, and historical interactions, retailers can create communications that feel uniquely tailored to each individual. This capability lights up the seamless interaction between Commerce, Customer Insights - Journeys, and Customer Insights - Data, and helps make sure that every touchpoint reflects a comprehensive understanding of the customer.

### Real business impacts of personalization

Imagine a customer purchasing a new pair of shoes through a mobile app. Within minutes, they receive a personalized email thanking them for their purchase, along with recommendations for accessories that complement their new shoes. This immediate, tailored communication not only delights the customer but also increases the likelihood of more sales.

### Automated transactional communications

Timely, consistent communication is essential for customer satisfaction. Automated transactional emails—such as order confirmations, shipping notifications, and delivery updates—keep customers informed at every stage of their purchase journey. This automation reduces manual effort and ensures messaging is consistent and accurate, whether the purchase was made online or in-store.

### Enhanced loyalty and retention

Post-purchase, customers can receive personalized invitations to join loyalty programs, access exclusive offers, or participate in feedback surveys. When customers experience that the retailer acknowledges their purchases and values their opinions, retailers strengthen customer relationships and encourage repeat business.

### Seamless customer experiences across channels

Let's explore a comprehensive customer journey that illustrates the value of this integration:

1. Discovery across channels  

    Sarah, a tech-savvy shopper, begins her journey on a mobile app during her morning commute, browsing new arrivals and adding items to her wish list. Later, she continues her exploration on her laptop during lunch, comparing products and reading reviews on the retailer's website.

2. In-store personalized experience  

    After work, Sarah visits a store to see the products in person. The store associates engage in clienteling—a practice that uses customer insights to deliver a more personalized experience. The sales associate greets Sarah, offers tailored assistance, and makes recommendations based on her browsing history, creating a cohesive experience that bridges her online and in-store interactions.

3. Seamless purchase and immediate confirmation  

    Sarah decides to purchase a dress she tried on in the store. The transaction is processed through Dynamics 365 Commerce, instantly updating her purchase history across all platforms. She immediately receives a digital receipt via email and a confirmation in her mobile app.

4. Timely post-purchase engagement  

    As she leaves the store, Sarah gets a push notification thanking her for her purchase and suggesting accessories that complement her new dress. This timely, personalized message encourages her to consider other items, enhancing her overall shopping experience.

5. Feedback and loyalty invitations  

    The next day, Sarah receives an email inviting her to share feedback about her in-store experience. Sarah appreciates that her opinion matters, so she completes the survey, providing valuable insights to the retailer. The retailer recognizes her engagement and sends a personalized text message inviting her to join its loyalty program. With a simple tap on her mobile app, Sarah enrolls and gains access to exclusive benefits.

6. Consistent engagement and rewards  

    Over the following weeks, Sarah receives tailored promotions and content across all channels—email newsletters, mobile app notifications, and personalized offers when she visits the website. Her loyalty points and rewards are updated in real time, whether she shops online or in store.

7. Supporting customer service with a 360-degree view  

    If Sarah ever contacts the retailer's call center, the service agents can see her complete journey—including her latest purchases, shipment updates, and marketing interactions—right within [Dynamics 365 Customer Service](/dynamics365/customer-service/implement/overview). This visibility lets the service team provide informed, personalized support, ensuring Sarah's experience is smooth and consistent.

8. Building long-term loyalty  

    Sarah feels valued and understood by the brand. The seamless integration across channels makes her shopping experience convenient and enjoyable, leading to increased brand loyalty and advocacy.

## Solution overview

This section digs deeper into each of the tools in the sample.

### A robust technical architecture

The solution uses a robust technical architecture to ensure seamless data flow and integration between systems. The following diagram shows how each component interacts within the solution:

:::image type="content" source="media/customer-insights-commerce-architecture3.png" alt-text="Architecture diagram that's explained after the illustration." lightbox="media/customer-insights-commerce-architecture3.png":::

- [Dynamics 365 Commerce](/dynamics365/commerce/welcome)  

  The primary source of truth for customer transactions, encompassing both online and in-store orders. It generates events for customer interactions, ensuring that sales data is accurately captured and available for downstream processing. This component is the foundational layer where transactions originate, providing a consistent view of customer activities to drive personalized engagement.
​​​​​​​
- Commerce Event Framework  

  The Commerce Event Framework is responsible for generating and storing events, utilizing the CQRS pattern to optimize performance by separating read and write operations. This framework, as shown in the diagram, ensures the efficient and scalable processing of events, handling high transaction volumes without performance degradation.

- [Azure Function App](/azure/azure-functions/functions-overview?pivots=programming-language-csharp)  

  The Azure Function App polls for new events from the event store, retrieves customer and order information, and transforms the data for downstream services. As depicted in the diagram, it ensures secure, reliable communication between Dynamics 365 Commerce and Azure Service Bus, performing crucial functions such as data enrichment, validation, and orchestration. This step bridges the gap between data generation and workflow orchestration.

- [Azure Cosmos DB](/azure/cosmos-db/introduction)  

  Azure Cosmos DB maintains state by tracking processed events, preventing duplication and ensuring idempotency in event processing. As seen in the architecture diagram, it plays a crucial role in state management, guaranteeing data consistency in scenarios involving retries or concurrent event processing.

- [Azure Service Bus](/azure/service-bus-messaging/service-bus-messaging-overview)  

  Azure Service Bus provides reliable queuing of messages, ensuring data integrity and delivery even if downstream systems are unavailable. Represented in the diagram as the core messaging layer, it decouples event producers from consumers, maintaining smooth data flow and reducing the risk of data loss.

- [Azure Logic Apps](/azure/logic-apps/logic-apps-overview)  

  Azure Logic Apps orchestrates workflows, transform data, and route messages to [Customer Insights – Journeys](/dynamics365/customer-insights/journeys/real-time-marketing-overview). As shown in the diagram, they handle the orchestration of events flowing through the architecture, managing errors and retries to ensure reliable execution. Their low-code interface accelerates development by simplifying complex workflow definitions.

- [Customer Insights – Data](/dynamics365/customer-insights/data/overview)  

  Plays a crucial role in enriching customer profiles by aggregating customer data from multiple sources, creating [unified customer profiles](/dynamics365/customer-insights/data/marketing-get-started), and generating insights through AI models. If Customer Insights – Data has been implemented, these insights can significantly enhance personalization, providing the necessary context for hyper-personalised communication. These enriched profiles are used by Customer Insights – Journeys to create more impactful and relevant customer interactions.

- [Customer Insights – Journeys](/dynamics365/customer-insights/journeys/real-time-marketing-overview)  

  Customer Insights manages customer communications, automations, and marketing campaigns, initiating customer journeys based on event triggers. In the architecture diagram, it's the final step where enriched and transformed data culminates in targeted customer engagement actions.

### High-level workflow

The following workflow outlines how these components integrate Dynamics 365 Commerce with Customer Insights – Journeys. This end-to-end process ensures that customer data is captured, enriched, and used effectively to drive personalized engagement.

1. Event generation

    Transactions occurring in Dynamics 365 Commerce trigger the Commerce Event Framework to generate and store relevant events.

1. Event retrieval and processing

    The Azure Function App polls for new events, validates them against Azure Cosmos DB to avoid duplication, and retrieves customer and order information as needed.

1. Message queuing

    Validated events are placed in the Azure Service Bus queue for reliable delivery.

1. Workflow orchestration

    Azure Logic Apps processes the queued messages, transforming the data and initiating the appropriate customer journey.

1. Customer engagement

    Customer Insights – Journeys executes the customer journey, sending emails, text messages, or other types of communications.

### Key takeaways

- Use Commerce Event Framework for efficient, scalable event generation.
- Use Azure Function App for secure, enriched event transformation.
- Use Azure Cosmos DB for state management and data consistency.
- Use Azure Service Bus for reliable message delivery.
- Use Azure Logic Apps for low-code workflow orchestration.

### Development considerations for implementation

To successfully implement the solution, developers must extend and customize several components:

- Dynamics 365 Commerce extensions  

  Extensions are required for the Commerce Scale Unit (CSU) event framework to capture the necessary events.
- Purpose-built Azure integration components:

  - Azure Function App  

    Responsible for polling and transforming events, including authentication and data enrichment.
  - Azure Cosmos DB  

    Manages event storage and maintains state for event processing.
  - Azure Service Bus  

    Provides reliable message queuing to ensure decoupling and fault tolerance.
  - Azure Logic App  

    Processes events and integrates them with Customer Insights – Journeys for triggering customer journeys.

> [!NOTE]
> The Microsoft FastTrack team provides samples for all aspects of the solution covered in this article. You can access them in the GitHub repository at [Commerce Event Sample - Dynamics 365 FastTrack Implementation Assets](https://github.com/Microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Commerce/CommerceEventSample)

### Overcome challenges with Commerce Event Framework

Traditional integration methodologies are often fraught with limitations such as the "fire-and-forget" approach, latency issues, and inadequate monitoring. Events are dispatched without confirmation of receipt, leading to potential data loss, while delays in data processing can result in outdated information, complicating real-time decision-making. Moreover, limited event tracking makes troubleshooting cumbersome.

The Commerce Event Framework addresses these challenges with its core features:

- Persisted event storage  

  Intentional design decision to persist events in a read-only event store and made available to poll, with a lightweight event payload. These design choices enhance performance, scalability, and reduce system load.
- Near real-time integration  

  Events are processed almost instantaneously, ensuring that customer data remains current.
- Reliability and scalability  

  Azure Service Bus facilitates dependable message delivery while the architecture scales to handle high volumes of events.
- Monitoring and auditing  

  Event tracking capabilities allow for comprehensive monitoring and streamlined troubleshooting.
- Performance optimization through CQRS  

  By separating read and write operations, the architecture enhances both performance and scalability.

The Commerce Event Framework empowers developers to handle complex scenarios with ease. The next subsections explore the key components that drive this framework and how they form a robust integration solution.

### CommerceEventsController

The CommerceEventsController handles the main requests related to commerce events. It provides two main endpoints: one for retrieving all commerce events (GetAllCommerceEvents) and another for searching specific events (Search). This enables efficient event retrieval with filtering capabilities to ensure only relevant data is accessed. By using `QueryResultSettings`, the controller provides flexibility in paginating and filtering the results, making data handling efficient, even with large datasets.

### CommerceEventEntity

The `CommerceEventEntity` is the core data model representing an individual commerce event. This entity captures detailed information about each event, such as:

- `EventTransactionId`  

  Unique identifier for the transaction.
- `EventDateTime`  

  Timestamp for when the event occurred.
- `EventType`  

  Type of event, such as checkout or cart update.
- `EventChannelId`, `EventCustomerId`, `EventStaffId`, `EventTerminalId`  

  Metadata fields capturing contextual details like channel, customer, staff involved, and terminal used.
- `EventData`  

  More event-specific data in a serialized format.

This entity forms the backbone of the Commerce Event Framework, providing a structured format to store and retrieve event details.

### CommerceEventDataService

The `CommerceEventDataService` acts as the data handler for managing commerce events within the system. It supports multiple request types, such as retrieving all events (`CommerceEventEntityDataRequest`), creating new events (`CreateCommerceEventEntityDataRequest`), and searching events based on criteria (`SearchEventEntityDataRequest`). This service is essential in bridging the gap between the application logic and the data layer.

- `GetCommerceEvents`  

  This method queries the underlying SQL view (`COMMERCEEVENTSVIEW`) to retrieve the list of events, ensuring the data is paginated and filtered as per the provided settings.
- `SearchCommerceEvents`  

  This method allows event searches based on specific criteria like event type and date range. It uses caching mechanisms to improve search performance by storing frequently accessed data.
- `CreateCommerceEvent`  

  This method inserts new events into the database using a stored procedure. It captures event details such as transaction ID, event type, timestamps, and other metadata. The use of parameterized queries ensures data integrity and security.

The `CommerceEventDataService` is a pivotal component, providing the necessary functions to manage commerce events effectively, supporting the broader goal of reliable and scalable event processing.

### CheckoutCartRequestHandler

The CheckoutCartRequestHandler demonstrates how the Commerce Event Framework can be extended to capture specific business events—in this case, the checkout process. When a customer checks out, the handler not only processes the checkout request but also creates a new CommerceEventEntity to capture the checkout event. This event includes relevant metadata, such as the customer ID, channel, transaction ID, and other details.
The event is then stored using the `CreateCommerceEventEntityDataRequest`, which persists the event data, ensuring that it can be later retrieved for auditing, analytics, or troubleshooting purposes. The use of TransactionScope ensures that the checkout and event creation are handled atomically, maintaining data consistency.

### AddCartLineRequestHandler

The `AddCartLineRequestHandler` is another example of extending the Commerce Event Framework to capture specific actions—in this case, adding items to a cart. When a customer adds a product to their cart, this handler processes the `AddCartLinesRequest` and then creates a `CommerceEventEntity` to record the action. The `AddCartLineRequestHandler` captures essential event information such as:

- `EventType`  

  Set to `AddCartLines` to signify an addition of items to the cart.
- `EventTransactionId`  

  The unique cart ID associated with the event.
- `EventData`  

  Serialized details of the items added to the cart, including product IDs.
- `EventCustomerId`, `EventStaffId`, `EventTerminalId`  

  Metadata to provide more context about the action, such as which customer, staff, or terminal was involved.

The event is persisted similarly using the `CreateCommerceEventEntityDataRequest`, ensuring all cart modification activities are logged and can be audited or used for analytics. As with the checkout process, the use of TransactionScope ensures atomic handling, maintaining data integrity.

Partners and customers can use this framework to create new custom events tailored to their business needs, such as "CustomerCreate" or other domain-specific actions, enhancing the extensibility and adaptability of the solution

### Commerce Event Messaging Files

The Commerce Event Framework also includes several messaging files that serve as data carriers, encapsulating the requests and responses required to perform various operations. These message classes help standardize the interaction between different layers of the application.

- `CommerceEventEntityDataRequest`  

  Represents a request to retrieve commerce event entities. It's the foundational request type for fetching event data from the data service.
- `CreateCommerceEventEntityDataRequest`  

  Handles requests to create new commerce event entities, ensuring that new events are captured in a structured manner.
- `CreateCommerceEventEntityDataResponse`  

  Represents the response containing the outcome of a request to create a commerce event entity, confirming the details of the inserted event.
- `GetCommerceEventLastSyncDataRequest`  

  Encapsulates the request to retrieve the last synchronization datetime for commerce events, helping keep data consistency.
- `GetCommerceEventLastSyncDataResponse`  

  Represents the response containing the last sync datetime, used to determine the latest state of data.
- `SearchEventEntityDataRequest`  

  Encapsulates the criteria needed to search for specific events, such as date ranges or event types.
- `SearchEventEntityDataResponse`  

  Represents the response containing the results of a search request, providing a collection of commerce event entities matching the criteria.
- `SetCommerceEventLastSyncDataRequest`  

  Handles requests to set or update the last sync datetime for a specific application, ensuring synchronization tracking.

These message files provide the necessary abstraction for handling requests within the Commerce Event Framework, making it easier to manage data flow while maintaining separation of concerns.

Additionally, events can be cleaned up with a script during package deployment, ensuring the system remains optimized and free of obsolete event data.

## Azure Integration Components in detail

This section explains the key Azure integration components that enable seamless data flow between Dynamics 365 Commerce and Customer Insights – Journeys. These components ensure reliability, scalability, and enriched customer experiences.

### Azure Function App

The Azure Function App polls and processes new events from Dynamics 365 Commerce. When triggered at frequent intervals (for example, every minute), the Azure Function App performs several critical tasks:

- Authentication  

  The Function App gets an access token from the authority specified for Dynamics 365 Commerce using OAuth2 client credentials. This ensures secure communication with the CSU endpoint.
- Polling events  

  The Function App sends requests to the CSU to fetch events. It retrieves the last processed event from Cosmos DB to ensure only new events are processed, preventing duplication.
- Data enrichment  

  The Function App enriches each event with customer and order details fetched from the appropriate endpoints. These details are combined with event data to provide complete context.
- State management  

  Events are stored in Azure Cosmos DB, which tracks properties such as status and retryCount to ensure each event's processing state is well managed and auditable.
- Error handling and retries  

  If event retrieval or processing fails, the Function App uses an exponential backoff strategy with a maximum retry count. Failed events are updated in Cosmos DB, and retries continue until they succeed or reach the retry limit.
- Sending to Azure Service Bus  

  After enrichment, events are sent to Azure Service Bus for reliable delivery to downstream consumers.

### Azure Cosmos DB

Azure Cosmos DB plays a key role in state management for event processing. It ensures:

- Idempotency  

  Events are tracked by unique identifiers, guaranteeing that each event is processed only once.
- Partitioning for Efficiency  

  The database uses channel IDs as partition keys to ensure that data is efficiently stored and queried, enabling effective scaling and concurrency management.
- Retry and State Tracking  

  The database keeps track of retries and the current status of each event (for example, new, processing, processed, failed), making it easier to monitor workflow progression and retry failed events if necessary.

### Azure Service Bus

Azure Service Bus ensures reliable message queuing for decoupling the event generation from further processing. Key features include:

- Message Reliability  

  Messages are added to a Service Bus topic, ensuring that multiple subscribers, such as Azure Logic Apps, can reliably receive and process them.
- Error Management  

  In cases of delivery failure, messages are moved to a dead-letter queue for analysis, ensuring no event is lost.
- Scalability  

  Service Bus handles high volumes of events efficiently, allowing the system to scale by adding more subscribers as needed.

### Azure Logic App

The Azure Logic App orchestrates the integration process, ensuring that the enriched event data reaches Customer Insights – Journeys. Specific roles include:

- Message retrieval  

  Logic Apps listen to Azure Service Bus for new messages. Upon receiving them, Logic Apps start the workflow to process customer data.
- Data transformation  

  The Logic App transforms the enriched data into a format suitable for Customer Insights – Journeys, ensuring all data conforms to the expected structure.
- Conditional logic and creation  

  Logic Apps first check if the contact already exists in Customer Insights. If not, they create new contacts and link existing customer information.
- Error handling  

  Logic Apps have built-in mechanisms for retries, ensuring that any temporary failures in downstream services are retried before escalation.
- Triggering customer journeys  

  Once the customer data is verified and enriched, Logic Apps trigger specific journeys in Customer Insights, such as personalized campaigns or loyalty program invitations.

The Logic App uses a low-code interface, making it easier to define complex workflows that connect multiple systems and ensuring the reliability of the overall data integration process.

## Customer Insights – Journeys

Customer Insights – Journeys transforms enriched customer data into meaningful, actionable experiences. It tailors engagements to fit each customer's unique journey, using outputs from Logic Apps to deliver relevant, personalized interactions.

### Key Features of Customer Insights – Journeys

Here are some powerful ways to enhance customer engagement:

- Transactional emails  

  Automatically send essential transactional information—like order confirmations, shipping updates, and digital receipts. Keeping customers informed at every stage builds trust and transparency, allowing them to feel more connected and confident in their journey with your brand.
- Feedback requests  

  Use custom triggers to gather customer feedback at the perfect moment. Whether it's a survey request after a purchase or a simple prompt for a product review, timely engagement helps brands understand their customers better and drive improvements.
- Loyalty program engagement  

  Logic Apps automatically trigger journeys that drive engagement in loyalty programs. They send personalized loyalty invitations, update customers on their loyalty points, and deliver exclusive offers. This fosters a sense of value and appreciation, encouraging long-term loyalty.
- Post-purchase engagement  

  A post-purchase experience can set the tone for future interactions. Using a custom trigger via an HTTPS POST from Logic Apps, you can initiate a journey that sends a post-purchase email including a thank-you message, order details, and product recommendations. This small yet thoughtful interaction helps maintain brand visibility and keeps customers engaged, paving the way for repeat business.
- The unified customer experience advantage  

  Customer Insights – Journeys takes the power of unified customer profiles to the next level. By personalizing each interaction based on comprehensive data, brands can create meaningful, relevant connections that elevate the customer experience.
- Target Unified Customer Profiles  

  Target your customers using unified profiles, built from multiple data sources including Customer Insights – Data and Azure Data Lake Storage. With a 360-degree view of your customer, you can reach them at the right moment with the right message.
- Real-Time Personalization  

  Imagine being able to personalize engagements in real-time. By tapping into enriched customer profiles, you can create custom triggers that launch journeys based on actions—such as purchases or browsing history. The deeper your understanding of each customer, the more personalized and timely your engagements can be.

## Get started with your first post-purchase journey

Here's how you can set up a custom trigger to initiate a post-purchase journey:

1. Create a custom trigger: In Customer Insights – Journeys, go to the **Triggers** section to create a trigger for an event, such as `post-purchase`. This is invoked via an HTTPS POST from Azure Logic Apps.
2. Integrate the trigger: Use the provided code snippet to seamlessly integrate the trigger with external systems, enabling the journey to be initiated automatically. If you're integrating via an HTTPS POST from a Logic App or another middleware service, call the Dataverse base URL along with the trigger name, as detailed in the code snippet. Alternatively, when working in Logic Apps or Power Automate, you can directly invoke the trigger through the connector by utilizing an unbound action for a streamlined integration.
3. Configure the journey: Create a new journey that begins with the custom trigger and includes actions like sending a post-purchase email.
4. Publish: Finally, publish the journey to make it live—ensuring all relevant content is ready to be sent.

For more in-depth guidance, explore the documentation:

- [Create Custom Triggers in Customer Insights – Journeys](/dynamics365/customer-insights/journeys/real-time-marketing-custom-triggers)
- [Create Trigger-Based Journeys](/dynamics365/customer-insights/journeys/real-time-marketing-trigger-based-journey)

If you're interested in learning more about using unified customer profiles for richer, more impactful customer journeys, check out our related resources:

- [Unified Customer Profiles in Dynamics 365 Customer Insights – Journeys](/dynamics365/customer-insights/data/marketing-get-started): Learn how unified profiles can take your customer experiences to the next level.  
- [Data integration with Dynamics 365 Commerce and Dynamics 365 Customer Insights - Data](data-integration-commerce-customer-insights-data.md)  

## Bring everything together

The integration of Dynamics 365 Commerce with Customer Insights – Journeys through synchronous data integration delivers substantial business value. This solution empowers real-time customer engagement, streamlines marketing automation, and enhances loyalty management while providing actionable insights that guide strategic decisions. As the retail landscape evolves, this architecture remains adaptable, with the potential to incorporate new channels and integrate emerging AI technologies for deeper personalization.

## Call to action

Ready to revolutionize your customer engagement strategy? Start today by implementing basic integration with Dynamics 365 Customer Insights using our GitHub samples: [Commerce Event Sample - Dynamics 365 FastTrack Implementation Assets](https://github.com/Microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Commerce/CommerceEventSample)

## Related content

- [Overview of data integration with Dynamics 365 Commerce and Customer Insights](data-integration-commerce-customer-insights.md)  
- [Data integration with Dynamics 365 Commerce and Dynamics 365 Customer Insights - Data](data-integration-commerce-customer-insights-data.md)  
- [Commerce Data Exchange and commerce channel communications](/dynamics365/commerce/dev-itpro/define-retail-channel-communications-cdx)  
- [Guidance for dual-write setup](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/connection-setup)  

## Contributors in alphabetic order

[Liam Kerrigan](https://www.linkedin.com/in/liamkerrigan/) \| Senior Program Manager

[Meenu Laul](https://www.linkedin.com/in/meenu-laul-6590bb17/) \| Senior Solution Architect

[Peter Krause](https://www.linkedin.com/in/ms-peterkrause/) \| Principal Solution Architect

[Raphael Vonderküste](https://www.linkedin.com/in/raphaelvdk/) \| Principal Program Manager

[Thomas Chilaud](https://www.linkedin.com/in/thomas-chilaud/) \| Principal Solution Architect
