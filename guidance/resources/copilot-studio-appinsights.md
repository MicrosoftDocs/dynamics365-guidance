---
title: Application insights telemetry with Microsoft Copilot Studio
description: Discover how to use Kusto queries in the Azure portal to analyze and manipulate telemetry data from Application Insights for performance and usage of your bot.
author: rramju
ms.author: ramara
ms.topic: conceptual
ms.date: 05/03/2024
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:04/23/2024
  - O25-Service
# CustomerIntent: As an admin, I want to track how our copilot is used.
---

<!-- If application insights in the title refers to the feature, then it should be capitalized. -->


# Application insights telemetry with Microsoft Copilot Studio

***Applies to: Dynamics 365 Customer Service***

This article discusses how you can capture telemetry data from your Microsoft Copilot Studio bot for use in [Application Insights](/azure/azure-monitor/app/app-insights-overview).

In addition to the native analytics features within Microsoft Copilot Studio, you can send telemetry data to Application Insights. Telemetry offers insights into your bot by tracking the following data:

- Logged messages and events sent to and from your bot.
- Topics to be triggered during user conversations.
- Custom telemetry events that can be sent from your topics.

## Prerequisites

To use Application Insights, you must have a Copilot Studio instance that's connected to an Azure app service. You also must have access to the app service's app insights resource in the Azure portal. You can find the app insights resource name and key in the agent's settings page under **Analytics**. Learn more about how to connect Copilot Studio to Application Insights at [Connect your Microsoft Copilot Studio bot to Application Insights](/microsoft-copilot-studio/advanced-bot-framework-composer-capture-telemetry?tabs=webApp#connect-your-microsoft-copilot-studio-bot-to-application-insights).

## Kusto query samples and explanations

Kusto is a query language that enables you to perform complex data analysis and manipulation on app insights data. You can use the app insights query editor in the Azure portal to run Kusto queries and view the results in various formats, such as tables, charts, and maps. The subsections in this section show a sample KQL query with an explanation of parameters and results.  

You can use Kusto queries to answer various questions about your agent's performance and usage, such as:

- What are the most popular topics that users ask about?
- How satisfied are users with the agent's responses?
- How often do users escalate to a human agent?
- What are the common errors or issues that the agent encounters?

Learn more about how to use Kusto queries at [Kusto Query Language (KQL) overview](/azure/data-explorer/kusto/query/).

### Analyzing sessions and messages counts per day over the last 30 days to track engagement and workload trends

```kusto
requests
| where timestamp > ago(30d)
| summarize sessions = dcount(session\_Id), messages = count() by bin(timestamp, 1d)
| render timechart
```

Explanation:

- **Filtering by Timestamp**: Selects only the requests that occurred in the last 30 days using where clause to filter the requests table by the timestamp column.
- **Summarization**: Groups the filtered requests by the timestamp column, binning them into one-day intervals (bin (timestamp, 1d)). Then, the query calculates the number of distinct sessions (sessions = dcount(session\_Id)) and the total number of messages (messages = count ()).
- **Rendering Timechart**: Renders the summarized data as a timechart, where the x-axis represents time, and the y-axis represents the count of sessions and messages. Two lines represent sessions and messages, respectively.

## Query for Distinct User Communication Over Time

```kusto
// Define query parameters

let queryStartDate = ago(14d);  // Start date for the query (14 days ago)
let queryEndDate = now();        // End date for the query (current time)
let groupByInterval = 1d;        // Interval for grouping data (1 day)
// Retrieve custom events data
customEvents
| where timestamp > queryStartDate  // Filter events after the start date
| where timestamp < queryEndDate    // Filter events before the end date
| summarize uc = dcount(user\_Id) by bin(timestamp, groupByInterval)  // Count distinct user IDs per time interval
| render timechart  // Visualize the summarized data as a time chart
```

Explanation:

- Query parameters:

  - **queryStartDate**: Specifies the starting date for the data retrieval, which is 14 days ago from the current time.
  - **queryEndDate**: Represents the current time, serving as the end date for data retrieval.
  - **groupByInterval**: Sets the interval for grouping data, in this case, one day.

- Data retrieval:

  - **customEvents**: Specifies the data source for the query, presumably containing events related to user-bot communication.

- Data filtering:

  - **where timestamp > queryStartDate**: Filters events to include only events that occur after the start date.
  - **where timestamp < queryEndDate**: Further filters events to include only events that occur before the end date.

- Data summarization:

  - **summarize uc = dcount(user\_Id) by bin(timestamp, groupByInterval)**: Groups the filtered events by timestamp bins (based on the specified interval) and calculates the count of distinct user IDs within each bin. The result is stored in the `uc` column.

- Visualization:

  - **render timechart**: Renders the summarized data as a time chart, allowing visualization of user-bot communication trends over time.

  This query helps analyze and visualize the number of distinct users communicating with the bot over the past 14 days, providing insights into user engagement and interaction patterns.

## Query that excludes canvas test conversations from telemetry

This query retrieves telemetry data while excluding canvas test conversations, providing cleaner data for analysis without including test data.

```kusto
// Retrieve custom events data and exclude canvas test conversations

customEvents
| extend isDesignMode = customDimensions['DesignMode']
| where isDesignMode == "False"  // Exclude canvas test conversations
```

Explanation:

- Data retrieval:

  - **customEvents**: Specifies the data source for the query, presumably containing telemetry events.

- Exclude canvas test conversations:

  - **extend isDesignMode = customDimensions['designMode']**: Extends the dataset to include a new column isDesignMode, which extracts the value of the 'designMode' field from the customDimensions.
  - **where isDesignMode == "False"**: Filters the events to exclude canvas test conversations by checking if the value of isDesignMode is "False".

- Formatting content:

  - **format content**: Formats the query output to display the content of the telemetry events.

## Structuring custom events and custom dimension data

This query transforms the customEvents data by performing several operations:

- Ordering the events by timestamp in ascending order and within each timestamp by session ID.
- Calculating the time difference between consecutive events within the same session.
- Extracting various custom dimensions such as Kind, TopicName, Text, and errorCodeText.
- Splitting TopicName and TopicId into arrays of words and determining the number of words.
- Determining topics based on the number of words.
- Converting certain dimensions to string format.
- Assigning event groups and generating event group labels based on event names and topics.
- Computing a cumulative sum for row identification within each event group.

The final result is projected with selected fields and stored in rawData.

```kusto
let rawData = customEvents
| order by timestamp asc , session_Id
| extend TimeDifference = iif(row_number() > 1 and session_Id == prev(session_Id), (timestamp - prev(timestamp))/1ms, (timestamp-timestamp)/1ms)//1ms
| extend Kind=customDimensions["Kind"]
| extend TopicName=customDimensions["TopicName"]
| extend Text = customDimensions["text"]
|extend errorCodeIndex = indexof(customDimensions["text"], "Error code:")
|extend conversationIdIndex = indexof(customDimensions["text"], "Conversation ID:")
| extend errorCodeText = substring(customDimensions["text"], errorCodeIndex + strlen("Error code:"), conversationIdIndex - (errorCodeIndex + strlen("Error code:")))
| extend Words = split(customDimensions["TopicName"], ".") // Split the string into an array of words
| extend TopicIdWords = split(customDimensions["TopicId"], ".")
| extend NumWords = array__length(Words) // Get the number of words in the array
| extend Topics = case (array_length(Words) == 1, TopicIdWords[2],Words[2])
| extend channelId = tostring(customDimensions['channelId'])
| extend fromId = customDimensions['fromId']
| extend fromName = customDimensions['fromName']
| extend recipientId = customDimensions['recipientId']
| extend typetext = tostring(customDimensions['type'])
| extend EventGroupcounter = iif(name == "TopicStart", 1, iif(name == "TopicEnd", 0, 0))
| extend EventGroup = case(name == "TopicStart", strcat("TopicStart_", Topics),case(name == "TopicEnd", strcat("TopicEnd_", Topics),"Other"))
| extend RowId =   row_cumsum(EventGroupcounter)
| project timestamp, name, tostring (Topics),Kind,Text, errorCodeText, session_Id, customDimensions,  EventGroup,TimeDifference;
rawData
```

Explanation:

| Field | Description | Sample values |
|:-|:-|:-|
| type | Type of activity | Message, ConversationUpdate, event, invoke |
| channelId | Channel Identifier | emulator, directline, msteams, webchat |
| from Name | Username from Client | John Doe, Steve Smith |
| recipientid | Recipient Identifier |  |
| recipientName | Recipient name | John Doe, Steve Smith |
| Text | Text in Message | Store hours |
| designmode | Conversation happened within the test canvas | True/false |
| timestamp | Time the Conversation occurred | 2023-12-12T01:15:53.0372788Z |
| name | Bot Event | Topic Start, BotMessageReceived, Bot MessageSend, Action, TopEnd, Custom Telemetry |
| Topics | Triggered Topic | ConversationStart, Greeting |
| Kind | Actions that happened within the topic trigger. It shows value wherever it's applicable | Question, SetVariable, SearchandSummarizeContent |
| Session\_id | Unique ID for Bot session |  |
| Event group | Groups the Actions within Topic | TopicStart\_Greetings, Other, TopicEnd\_Greetings. It can be customized. |
| TimeDifference | Time taken to run each action. Represented in milliseconds. ||

## Identify top errors in the bot

This query pipeline effectively filters and analyzes error occurrences within the **customEvents** data, providing insights into the distribution of error types. The column chart visualization aids in quickly understanding the relative frequencies of different error codes, allowing for targeted investigation and resolution of issues.

```kusto
let rawData = customEvents
| order by timestamp asc , session_Id
| extend TopicName=customDimensions["TopicName"]
| extend Text = customDimensions["text"]
| extend errorCodeIndex = indexof(customDimensions["text"], "Error code:")
| extend conversationIdIndex = indexof(customDimensions["text"], "Conversation ID:")
| extend errorCodeText = substring(customDimensions["text"], errorCodeIndex + strlen("Error code:"), conversationIdIndex - (errorCodeIndex + strlen("Error code:")))
| extend Words = split(customDimensions["TopicName"], ".") // Split the string into an array of words
| extend TopicIdWords = split(customDimensions["TopicId"], ".") 
| extend NumWords = array\_length(Words) // Get the number of words in the array
| extend TN = case (array\_length(Words) == 1, TopicIdWords[2], Words[2])
| project timestamp, name, tostring(TN), Text, errorCodeText, session_Id, customDimensions;
rawData
| where Text contains "Error Code:" and name == "BotMessageSend"
| summarize errortype = count() by errorCodeText
| render columnchart
```

Explanation:

- The query starts by organizing the **customEvents** data, sorting it by timestamp in ascending order and then by session ID.
- It extracts necessary fields like **TopicName**, **Text**, and **errorCodeText** from the **customDimensions** property.
- The **errorCodeText** is obtained by finding the substring between "Error code:" and "Conversation ID:" within the **Text**.
- After preparing the data, it filters the **rawData** to include only rows where the **Text** contains "Error Code:" and the name is "BotMessageSend".
- It then summarizes the count of occurrences for each unique **errorCodeText**.
- Finally, the summarized data is visualized as a column chart.

## Telemetry on Generative Answers

This query is designed to retrieve and structure event data related to generative answers. It extracts various properties from the customDimensions field and presents them in a structured format for analysis or further processing. By focusing on events with the name *GenerativeAnswers*, the query provides insights into interactions and outcomes of generative answer processes.

```kusto
customEvents
| where name == "GenerativeAnswers"
// | where cloud\_RoleInstance == "MS Learn Chatbot" // Bot Name
| extend cd = todynamic(customDimensions)
| extend conversationId = tostring(cd.conversationId)
| extend topic = tostring(cd.TopicName)
| extend message = tostring(cd.Message)
| extend result = tostring(cd.Result)
| extend SerializedData = tostring(cd.SerializedData)
| extend Summary = tostring(cd.Summary)
| extend feedback = tostring(todynamic(replace_string(SerializedData,"$","")).value)
| project cloud_RoleInstance, name, timestamp, conversationId, topic, message, result, feedback, Summary
| order by timestamp desc
```

Explanation:

- This query starts by selecting events with the name "GenerativeAnswers" from the **customEvents** table.
- It extends the data by converting **customDimensions** to dynamic objects (cd) to access its properties.
- Other properties such as **conversationId**, **topic**, **message**, **result**, **SerializedData**, and Summary are extracted from the dynamic object.
- The feedback field is derived by replacing "$" characters in **SerializedData** and converting the resulting dynamic object to a string.
- Finally, it projects selected fields and orders the data by timestamp in descending order.

