---
title: Application Insights telemetry with Microsoft Dataverse
description: Discover how to use Kusto queries in the Azure portal to analyze and manipulate telemetry data from Application Insights in solutions with Dataverse.
author: viange
ms.author: viange
ms.topic: concept-article
ms.date: 11/19/2024
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date: 11/19/2024
  - O25-Service
# CustomerIntent: As an admin, I want to track how Dynamics 365 Customer Service is used.
---

# Application Insights telemetry with Microsoft Dataverse

***Applies to: Dynamics 365 Customer Service***

This article discusses how you can capture telemetry data from your Microsoft Dataverse environment for use in [Application Insights](/azure/azure-monitor/app/app-insights-overview). Telemetry events for Dataverse provide performance data on various operations, such as API incoming calls, plug-in execution, and SDK calls. These events help monitor and analyze performance and failures, offering insights for troubleshooting and optimization. Key metrics include execution time, request counts, and success rates. Telemetry data supports both real-time and historical analytics, aiding in proactive system health monitoring and performance improvement.  

## Prerequisites

- Azure subscription  
- Application Insights environment

  You must have the relevant permissions with one of the following roles: *Contributor*, *Writer*, or *Admin*  
- Dataverse environment  

  If you have an environment with Dynamics 365 Customer Service, that environment includes Dataverse, Power Platform, and an Azure subscription.  

## Kusto query samples and explanations

Kusto is a query language that enables you to perform complex data analysis and manipulation on app insights data. You can use the app insights query editor in the Azure portal to run Kusto queries and view the results in various formats, such as tables, charts, and maps. The subsections in this article show sample Kusto Query Language (KQL) queries with an explanation of parameters and results.  

You can use Kusto queries to answer various questions about your agent's performance and usage, such as the following list:

- What are the most popular topics that users ask about?
- How satisfied are users with the agent's responses?
- How often do users escalate to a human agent?
- What are the common errors or issues that the agent encounters?

Learn more at [Kusto Query Language (KQL) overview](/azure/data-explorer/kusto/query/).

## Top plugins with high execution time query

The following query is designed to identify plugins with high execution times. It allows you to pinpoint potential performance bottlenecks. It filters out-of-the-box plugins and focuses on custom plugins that are taking longer to execute.  

```kusto
dependencies
| where type == 'Plugin'
| where name !startswith "Microsoft" // filtering the OOB plugins
| extend executionTimeInMS = todouble(duration)
| extend cd = parse_json(customDimensions)
| extend depth = toint(cd.depth)
| where success == 'True'
| summarize percentiles(executionTimeInMS, 10, 50, 90, 95, 98), NumOfRequests = count(), MaxDepth = max(depth), AvgExecutionTime= toint(avg(executionTimeInMS)) by name
| join kind = inner ( dependencies
| summarize NumOfTotalRequests = count() by name ) on name
| project-away name1
| extend PassRate = todouble(NumOfRequests) * 100 / NumOfTotalRequests
| extend PT95vsPT50Ratio = iif(percentile_executionTimeInMS_50 != 0, percentile_executionTimeInMS_95 / percentile_executionTimeInMS_50, toreal(0))
//| where percentile_executionTimeInMS_90 > 500
| where AvgExecutionTime > 500
| project-rename Namespace=name, ExecutionTimeinMS_90=percentile_executionTimeInMS_95, ExecutionCount = NumOfTotalRequests, Depth=MaxDepth
| project Namespace, ExecutionCount, AvgExecutionTime, percentile_executionTimeInMS_50, ExecutionTimeinMS_90, Depth
| order by ExecutionTimeinMS_90 desc
```

This query helps you identify plugins that might cause performance issues due to high execution times so that you can focus on optimizing them. It returns the following data:

|Field |Description|
|--|-|
|Namespace|The name of the plugin. |
|Execution Count|The total number of times the plugin has run.|
|Average Execution Time|The average time taken by the plugin to run. |
|Median Execution Time|The 50th percentile (median) execution time. |
|90th Percentile Execution Time|The 90th percentile execution time, showing the upper range of execution times. |
|Depth|The maximum depth of execution for the plugin. |

The following subsections provide a detailed explanation of what each part of the query does.

### Filter for dependencies on plugins

This part of the query filters the `dependencies` data to include only custom plugins, excluding Microsoft built-in plugins.

```kusto
dependencies
| where type == 'Plugin'
| where name !startswith 'Microsoft'
```

### Extract and convert execution time

These lines convert the execution duration to a double and extract custom dimensions and depth for each plugin execution, considering only successful executions.  

```kusto
| extend executionTimeInMS = todouble(duration)
| extend cd = parse_json(customDimensions)
| extend depth = toint(cd.depth)
| where success == 'True'
```

### Summarize execution metrics

This step calculates various metrics for each plugin:

- Percentiles (10th, 50th, 90th, 95th, 98th) of execution times.
- Number of requests.
- Maximum depth of execution.
- Average execution time.

```kusto
| summarize percentiles(executionTimeInMS, 10, 50, 90, 95, 98), NumOfRequests = count(), MaxDepth = max(depth), AvgExecutionTime= toint(avg(executionTimeInMS)) by name
```

### Join with total request counts

This join combines the summarized metrics with the total number of requests for each plugin, discarding the redundant column.

```kusto
| join kind = inner ( dependencies
| summarize NumOfTotalRequests = count() by name ) on name
| project-away name1
```

### Calculate the pass rate and PT95vsPT50 ratio

These lines calculate the pass rate (a percentage of the successful runs), and the ratio of the 95th percentile to the 50th percentile execution time.

```kusto
| extend PassRate = todouble(NumOfRequests) * 100 / NumOfTotalRequests
| extend PT95vsPT50Ratio = iif(percentile_executionTimeInMS_50 != 0, percentile_executionTimeInMS_95 / percentile_executionTimeInMS_50, toreal(0))
```

### Filter and rename fields

This final step filters out plugins with average execution times below 500 ms, renames fields for clarity, and orders the results by the 90th percentile execution time in descending order.

```kusto
| where AvgExecutionTime > 500
| project-rename Namespace=name, ExecutionTimeinMS_90=percentile_executionTimeInMS_95, ExecutionCount = NumOfTotalRequests, Depth=MaxDepth
| project Namespace, ExecutionCount, AvgExecutionTime, percentile_executionTimeInMS_50, ExecutionTimeinMS_90, Depth
| order by ExecutionTimeinMS_90 desc
```

## Form load times query

This query is designed to analyze and display the load times of forms, specifically focusing on the **EditForm** in your Customer Service solution. It helps you understand how quickly your forms are loading and identifies any potential performance issues by breaking down the load times into cold and warm loads.

```kusto
pageViews
| extend cd = parse_json(customDimensions)
| where cd.pageName == "EditForm"
| extend LoadTypeSimple = iif(toint(cd.loadType) == 0, 0, 1)
| extend entityName = tostring(cd.entityName)
| project LoadTypeSimple, duration, entityName
| summarize ColdCount=countif(LoadTypeSimple==0),
        WarmCount=countif(LoadTypeSimple==1),
        TotalCount=count(),
        AvgColdLoad=round(avgif(duration, LoadTypeSimple==0)),
        AvgWarmLoad=round(avgif(duration, LoadTypeSimple==1)),
        MaxColdLoad=maxif(duration, LoadTypeSimple==0),
        MaxWarmLoad=maxif(duration, LoadTypeSimple==1),
        P50FormLoad=percentile(duration, 50),
        P90FormLoad=percentile(duration, 90) by entityName
    |order by TotalCount desc
```

This query helps you monitor and optimize form load performance, ensuring a smoother user experience. It returns the following data:

|Field |Description|
|--|-|
|Cold and Warm Load Counts|The number of times forms are loaded cold (first load) versus warm (subsequent loads).|
|Load Time Averages and Maximums|Average and maximum load times for both cold and warm loads, helping you identify any performance outliers.|
|Percentile Load Times|The 50th and 90th percentile load times give you an idea of the typical and worst-case load times.|
|Entity-Specific Analysis|The results are grouped by entityName, allowing you to pinpoint which entities might be experiencing slower load times.|

The following subsections provide a detailed explanation of what each part of the query does.

### Extract custom dimensions

This line extracts the customDimensions field from the pageViews data and parses it into a JSON object for easier access to its properties.

```kusto
| extend cd = parse_json(customDimensions)
```

### Filter for EditForm

This filter ensures that the query only considers page views related to the **EditForm**.

```kusto
| where cd.pageName == "EditForm"
```

### Simplify the load type

This line simplifies the `loadType` field, categorizing it into two types|cold loads (0) and warm loads (1).

```kusto
| extend LoadTypeSimple = iif(toint(cd.loadType) == 0, 0, 1)
```

### Extract the name of the entity

Here, the query extracts the entityName from the custom dimensions, converting it to a string for further processing.

```kusto
| extend entityName = tostring(cd.entityName)
```

### Select relevant fields

This step projects only the relevant fields (LoadTypeSimple, duration, and entityName) for further analysis.

```kusto
| project LoadTypeSimple, duration, entityName
```

### Summarize data

This summarization step calculates various metrics by `entityName`.

```kusto
| summarize ColdCount=countif(LoadTypeSimple==0),
       WarmCount=countif(LoadTypeSimple==1),
       TotalCount=count(),
       AvgColdLoad=round(avgif(duration, LoadTypeSimple==0)),
       AvgWarmLoad=round(avgif(duration, LoadTypeSimple==1)),
       MaxColdLoad=maxif(duration, LoadTypeSimple==0),
       MaxWarmLoad=maxif(duration, LoadTypeSimple==1),
       P50FormLoad=percentile(duration, 50),
       P90FormLoad=percentile(duration, 90) by entityName
```

|Field |Description|
|--|-|
|ColdCount and WarmCount|The count of cold and warm loads.|
|TotalCount|The total count of form loads.|
|AvgColdLoad and AvgWarmLoad|The average load times for cold and warm loads, rounded to the nearest integer.|
|MaxColdLoad and MaxWarmLoad|The maximum load times for cold and warm loads.|
|P50FormLoad and P90FormLoad|The 50th and 90th percentile load times, providing insights into the median and upper range of load time.|

### Order by total count

Finally, the query orders the results by `TotalCount` in descending order so that you can see the entities with the most form loads at the top.

```kusto
| order by TotalCount desc
```

## Network performance by locations query

This query is designed to analyze and display network performance metrics such as latency and throughput, segmented by user and country/region. It helps you understand how your application is performing across different locations and identify any potential performance issues. This query is valuable for monitoring and optimizing network performance across different geographical regions, ensuring that users receive consistent and reliable access to your application.

```kusto
pageViews
| where timestamp >= ago(180d)
| take 10
| extend dimensions = parse_json(customDimensions)
| project
    USERID = user_Id,
    COUNTRY = client_CountryOrRegion,
    APPMODULE = dimensions.appModule, 
    PAGENAME = dimensions.pageName, 
    ENTITYNAME = dimensions.entityName, 
    LATENCY = dimensions.warmLatency, 
    THROUGHPUT = dimensions.warmThroughput
| summarize
    min(todouble(THROUGHPUT)),
    max(todouble(THROUGHPUT)),
    avg(todouble(THROUGHPUT))
by
    USERID, 
    COUNTRY
```

The query returns the following data:

|Field |Description|
|--|-|
|User and Location-Based Analysis|The query breaks down performance metrics by user ID and country/region, allowing you to see how network performance varies across different users and locations.|
|Throughput Metrics|The query provides insights into the minimum, maximum, and average throughput experienced by users, helping you identify regions or users that might face network performance issues.|
|Custom Dimensions|By projecting fields like `APPMODULE`, `PAGENAME`, and `ENTITYNAME`, you can further analyze which specific parts of your application contribute to performance issues in different locations.|

The following subsections provide a detailed explanation of what each part of the query does.

### Filter data by time range and limit results

This initial part of the query filters the data to include only records from the last 180 days. The `take 10` command limits the results to the first 10 records. You can adjust these parameters based on the volume of data and specific analysis needs.

```kusto
pageViews
| where timestamp >= ago(180d)
| take 10
```

### Extract and parse custom dimensions

This line parses the `customDimensions` field into a JSON object, allowing for easier access to its properties.

```kusto
| extend dimensions = parse_json(customDimensions)
```

### Project the relevant fields

This step selects and renames relevant fields from the data:

|Field |Description|
|--|-|
|USERID | The user's ID. |
|COUNTRY|The country or region of the client.|
|APPMODULE | The specific application module being used. |
|PAGENAME | The name of the page being accessed. |
|ENTITYNAME | The name of the entity being interacted with. |
|LATENCY | The latency of the network connection (specific to warm connections). |
|THROUGHPUT | The throughput of the network connection (specific to warm connections). |

```kusto
| project
    USERID = user_Id,
    COUNTRY = client_CountryOrRegion,
    APPMODULE = dimensions.appModule,
    PAGENAME = dimensions.pageName,
    ENTITYNAME = dimensions.entityName,
    LATENCY = dimensions.warmLatency,
    THROUGHPUT = dimensions.warmThroughput
```

### Summarize the network performance metrics

This summarization step calculates key metrics by `USERID` and `COUNTRY`:

|Field |Description|
|--|-|
|min(todouble(THROUGHPUT)) | The minimum throughput value for the user's sessions. |
|max(todouble(THROUGHPUT)) | The maximum throughput value for the user's sessions.|
|avg(todouble(THROUGHPUT)) | The average throughput value for the user's sessions. |

```kusto
| summarize
    min(todouble(THROUGHPUT)),
    max(todouble(THROUGHPUT)),
    avg(todouble(THROUGHPUT))
by
    USERID,
    COUNTRY
```

## Most failed plugins query

This query is designed to identify the plugins in your application that have the highest number of failures. It helps you pinpoint the plugins that are causing the most issues, allowing you to focus on troubleshooting and improving them.

```kusto
dependencies
| where type == "Plugin"
| extend cd = parse_json(customDimensions)
| project timestamp, success, correlationId = cd.correlationId, typeName = cd.pluginType
| summarize NumberofRequest = count(), Passed = dcountif(timestamp, success == "True"), Failed = dcountif(timestamp, success == "False") by tostring(typeName)
| order by Failed desc
| limit 10
```

This query is valuable for improving the reliability and performance of your application. It identifies and addresses the plugins that are most prone to failure. It returns the following data:

|Data |Description|
|--|-|
|Plugin Types with the Most Failures | The query identifies the top 10 plugins with the highest number of failed executions. |
|Number of Requests, Passes, and Failures| For each of the top 10 plugins, the query shows the total number of executions, the number of successful executions, and the number of failed executions.|
|Focus on Troubleshooting | The query highlights the plugins with the most failures so that you can prioritize which plugins need immediate attention for troubleshooting and optimization. |

The following subsections provide a detailed explanation of what each part of the query does.

### Filter for plugin dependencies

This line filters the dependencies data to include only entries related to plugins. The `type == "Plugin"` condition ensures that only plugin-related data is analyzed.

```kusto
dependencies
| where type == "Plugin"
```

### Extract and parse custom dimensions

This command parses the customDimensions field into a JSON object, making it easier to access its properties for further analysis.

```kusto
| extend cd = parse_json(customDimensions)
```

### Project the relevant fields

In this step, the query selects and renames relevant fields.

```kusto
| project timestamp, success, correlationId = cd.correlationId, typeName = cd.pluginType
```

|Field |Description|
|--|-|
|timestamp | The time when the plugin execution occurred. |
|success| Indicates whether the plugin execution was successful or not.|
|correlationId | A unique identifier to correlate plugin executions. |
|typeName | The type or name of the plugin, extracted from the custom dimensions. |

### Summarize plugin execution data

This summarization step calculates key metrics for each plugin type.

```kusto
| summarize NumberofRequest = count(), Passed = dcountif(timestamp, success == "True"), Failed = dcountif(timestamp, success == "False") by tostring(typeName)
```

|Field |Description|
|--|-|
|NumberofRequest|The total number of requests (executions) for the plugin.|
|Passed|The number of successful executions.|
|Failed|The number of failed executions.|

The results are grouped by `typeName`, which represents the plugin's type or name.  

### Order and limit the results

Finally, the query orders the results by the number of failed executions in descending order and limits the output to the top 10 plugins with the most failures. This way, your analysis can focus on the most problematic plugins.

```kusto
| order by Failed desc
| limit 10
```

## Plugins with depth greater than two

This query is designed to identify plugins that are executed with a depth greater than two, which could indicate potential performance issues or complex plugin chains. The depth of a plugin execution refers to how many layers deep the plugin is in the execution chain. The query focuses on plugins with higher depths to help you understand and optimize complex plugin executions.

```kusto
dependencies
| where type == 'Plugin'
| extend cd = parse_json(customDimensions)
| extend depth = toint(cd.depth)
| where name !startswith "Microsoft" // filtering the OOB plugins
| where depth > 2
| summarize count(), (P95)=percentiles(duration,95), (P95s)=percentile(toint(duration),95) by depth, name, bin(timestamp, 7d)
| order by depth
| where isnotempty(P95)
| project name, depth, timestamp, count_, P95
| summarize MaxDepth = max(depth) by name
| order by MaxDepth desc
```

This query is valuable for understanding and optimizing the performance of plugins with deep execution chains, helping you identify and address potential bottlenecks in your application. It returns the following data:

|Field |Description|
|--|-|
|Plugins with High Execution Depth|The query identifies plugins that are executed with a depth greater than two, which can indicate complex or potentially problematic plugin chains.|
|Execution Metrics|It shows the total number of executions and the 95th percentile of execution duration, which helps identify plugins that might be causing performance issues.|
|Maximum Depth by Plugin|The query summarizes the maximum depth of execution for each plugin and highlights the most complex plugin executions in your system.|

The following subsections provide a detailed explanation of what each part of the query does.

### Filter for plugin dependencies

This line filters the dependencies data to include only entries related to plugins, ensuring that the analysis focuses on plugin executions.

```kusto
dependencies
| where type == 'Plugin'
```

### Extract and parse custom dimensions

This step parses the customDimensions field into a JSON object and extracts the depth value, converting it to an integer. The depth indicates how deeply nested the plugin execution is within the overall execution chain.

```kusto
| extend cd = parse_json(customDimensions)
| extend depth = toint(cd.depth)
```

### Filter out Microsoft plugins and a depth greater than two

These lines filter out Microsoft out-of-the-box plugins and focus on custom plugins with a depth greater than two. This ensures that the query only analyzes more complex, custom plugin executions.

```kusto
| where name !startswith "Microsoft" // filtering the OOB plugins
| where depth > 2
```

### Summarize execution data

This summarization step calculates several metrics by depth, plugin name, and weekly time bins:

```kusto
| summarize count(), (P95)=percentiles(duration,95), (P95s)=percentile(toint(duration),95) by depth, name, bin(timestamp, 7d)
```

|Parameter |Description|
|--|-|
|count()|The total number of plugin executions for each depth and name.|
|P95 and P95s|The 95th percentile of the execution duration, giving insight into the longer execution times.|

### Order and filter the results

The query orders the results by depth and filters out any records where the 95th percentile of duration (P95) is empty. This focuses the results on meaningful data.

```kusto
| order by depth
| where isnotempty(P95)
```

### Project and summarize key fields

Finally, the query projects key fields such as plugin name, depth, and 95th percentile duration, and summarizes the maximum depth of execution for each plugin. The results are ordered by the maximum depth in descending order, highlighting the most deeply nested plugins.

```kusto
| project name, depth, timestamp, count_, P95
| summarize MaxDepth = max(depth) by name
| order by MaxDepth desc
```

## Using Azure Data Explorer dashboards with Application Insights queries

In addition to using Kusto queries directly within the Azure portal, you can use Azure Data Explorer Dashboards to visualize the results of these queries and create interactive, real-time reports. It's a powerful way to monitor and analyze the telemetry data from your Dynamics 365 Customer Service environment at a glance. We created a dashboard that you can directly import into your Azure Data Explorer environment.  

The dashboard file and the instructions to link it to your ApplicationInsights subscription are in the GitHub repo at [https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/ComponentLibrary/AppInsights-Telemetry/Dataverse).  

The following image illustrates the layout of the dashboard based on sample data.

:::image type="content" source="media/cs-dataverse-appinsights/Dashboard.png" alt-text="Screenshot of the Azure Data Expleror sample Dashboard." lightbox="media/cs-dataverse-appinsights/Dashboard.png":::

With Azure Data Explorer dashboards, you can create interactive filters. You can filter by date ranges, specific regions, or even plugin names, so that you can explore data relevant to your specific needs.  

Once your dashboard is ready, you can take the following steps| 

- Share the dashboard with anyone in your organization by granting them access to view or edit the dashboard in Azure Data Explorer.  
- Alternatively, embed the dashboard into your own portal or website using the embedding features provided by Azure.  

By integrating your telemetry data into an Azure Data Explorer dashboard, you can continuously monitor your Dynamics 365 Customer Service environments and proactively address potential performance bottlenecks or issues.

## Related information

- [Analyze model-driven apps and Microsoft Dataverse telemetry with Application Insights](/power-platform/admin/analyze-telemetry)
- [Application Insights overview](/azure/azure-monitor/app/app-insights-overview)
