---
title: Sample telemetry dashboard for Field Service mobile app offline profile usage
description: Discover how to use Kusto queries with the sample dashboard for the Dynamics 365 Field Service mobile app's offline profiles.
ms.date: 12/11/2024
ms.topic: conceptual
author: edupont04
ms.author: jaduples
---

# Sample telemetry dashboard for Field Service mobile app offline profile usage

***Applies to: Dynamics 365 Field Service***

This article describes a sample that Microsoft makes available for download in the [Dynamics-365-FastTrack-Implementation-Assets](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Field%20Service/Analytics/) GitHub repo. The sample, *Field Service Mobile Offline Analytics Telemetry Dashboard*, demonstrates the information that you can get for [offline profiles in the Dynamics 365 mobile app](/dynamics365/field-service/mobile/set-up-offline-profile). You can import the dashboard into your own Azure Application Insights resources. The dashboard focuses on the usage on mobile offline synchronization. Use the sample dashboard to understand usage, diagnose performance issues, and synchronization issues.  

> [!IMPORTANT]
> This article requires the Offline telemetry as well as Dataverse telemetry to be exported to your Azure Application Insights resources. Azure Application Insights is a consumption-based service, and we recommend that you manage the cost carefully.

Learn more about the telemetry events that the sample relies on at [Telemetry events for mobile app synchronization and actions](/power-platform/admin/telemetry-events-mobile).  

## Import the sample dashboard

To use the sample dashboard, you must be signed into Azure Data Explorer with an account that also gives you access to a Dynamics 365 Field Service environment. Learn more at [Visualize data with Azure Data Explorer dashboards](/azure/data-explorer/azure-data-explorer-dashboards).

1. In Azure Data Explorer, create a new dashboard by importing the file *dashboard-Field Service Mobile Offline.json* that you can download from [Dynamics-365-FastTrack-Implementation-Assets](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Field%20Service/Analytics/dashboard-Field%20Service%20Mobile%20Offline.json).

2. Give the new dashboard a relevant name, and then choose the **Data sources** action.

3. In the **Data source** pane, choose the pencil icon to edit the connection. In the **Edit data source** pane, replace the placeholder at the end of the link in the **Cluster URI** field with your Azure Application Insights subscription ID, and fill in the remaining fields.

4. Once the connection to the correct Azure subscription works, choose the **Connect** action.

5. From the list of databases, choose your Application Insights name, and then save your changes.

6. Your dashboard should have data now. Feel free to edit the queries to suit your needs.

## Sync summary dashboard

The following image illustrates the dashboard with fictive data.

:::image type="content" source="media/fs-mobile-offline-dashboard-sync-summary.png" alt-text="tekst" lightbox="media/fs-mobile-offline-dashboard-sync-summary.png":::

The dashboard shows a summary of recent offline synchronizations. The dashboard has the following charts:

- Distribution of sync types

- Daily users doing offline sync

- Usage by App versions

- Data sync duration (P95) by Sync Mode

- Daily sync success rate

### Distribution of sync types

This chart can help you understand the distribution of data sync types that users initiate. Learn more in the blog post [Best Practices for Offline Mode in the Field Service mobile app - Part 1 ](https://www.microsoft.com/dynamics-365/blog/administrator/2023/11/06/best-practices-for-offline-mode-in-the-field-service-mobile-app-part-1/).

#### Learn and diagnose sync types

Often, most data sync types are of type `DELTA_SYNC`. There are occasions where users can make many `FIRST_SYNC` attempts, such as through reconfigurations, or a significant number of grid refreshes, such as when a user presses refresh on the grid, which might indicate usability or data issues that should be investigated. The chart is based on a Kusto query such as we show in the following snippet.

```kusto
dependencies
| where timestamp between (_startTime.._endTime)
| where name == "Offline.SyncDatabase"
| extend cd = parse_json(customDimensions)
| extend eventContext = parse_json(tostring(cd.eventContext))
| extend dataSyncMode = tostring(customDimensions.DataSyncMode)
| where isnotempty(dataSyncMode)
| summarize count() by dataSyncMode
| project-rename ['Data sync mode'] = dataSyncMode
| render piechart
```

This query summarizes the number of synchronizations per data sync mode from the `Offline.SyncDatabase` dependency record.

### Daily users doing offline sync

This chart shows the number of users executing Mobile Offline synchronizations over time.

#### Learn and diagnose daily users

This chart can be useful to validate the volume of users making use of offline capabilities, especially where there's a mix of users using both offline and online profiles. This is also useful to validate any peak time where users perform synchronizations, which can cause performance bottlenecks. The chart is based on a Kusto query such as we show in the following snippet.

```kusto
dependencies
| where timestamp between  (_startTime.._endTime)
| where name == "Offline.SyncDatabase"
| extend cd = parse_json(customDimensions)
| extend eventContext = parse_json(tostring(cd.eventContext))
| extend profileId = tostring(eventContext.ProfileId)
| summarize ['Unique Users'] = dcount(profileId) by bin(timestamp, 1d)
```

This query extracts the number that has executed an offline synchronization per day from the `Offline.SyncDatabase` dependency record

### Usage by app versions

This chart shows the number of users using specific versions of the Field Service mobile app across Android, Windows, and iOS platforms. Due to the limited space, the chart just shows a short form of each version in the format *major.min.revision.build*.

#### Learn and diagnose app versions

The version information is only made available when a user executes a sync, so it doesn't cover users that data don't have offline provides.

The Field Service mobile app gets updated incrementally to users through the relevant app stores. Each of the app stores has a different release cadence. Use the graph to identify the rollout of an expected version across users. This can also help to diagnose if a user hasn't received an update in some time because they haven't logged on or have technical issues. The chart is based on a Kusto query such as we show in the following snippet.

```kusto
dependencies
| where timestamp between  (_startTime.._endTime)
| where name == "Offline.SyncDatabase"
| extend cd = parse_json(customDimensions)
| where isnotempty(user_Id) // Filter out rows where user_Id is empty
| where cd.AppFlavor == "FieldService"
| extend appVersion = tostring(cd.AppInfo\_Version)
| extend Version = extract(@"\b\d+\.(\d+\.\d+)", 1, appVersion)
| extend DeviceInfo_OsName = tostring(cd.DeviceInfo_OsName)
| where isnotempty(Version)  // Filter our request where there's no app version
| summarize Users = dcount(user_Id),
            Android = dcountif(user_Id, DeviceInfo_OsName == "Android"),
            iOS = dcountif(user_Id, DeviceInfo_OsName == "iOS" or DeviceInfo_OsName == "iPadOS"),
            Windows = dcountif(user_Id, DeviceInfo_OsName has "Windows")
        by Version
| order by Version asc
```

This query extracts the version of the Field Service mobile app in a short format without the prefixes for major and minor versions, and shows how many users are running the version by device operating system.

### Data sync duration P95 by sync mode

This chart graphs over time the performance of synchronization (optionally filtered by specific sync modes).

#### Learn and diagnose sync duration

Sync performance is impacted by various factors including device type, network quality, application version, offline sync filter complexity, number of records and record size.

Use this graph to get an overview of the performance across all users to then diagnose further within the Sync Performance page. The chart is based on a Kusto query such as we show in the following snippet.

```kusto
dependencies
| where timestamp between  (_startTime.._endTime)
| where name == "Offline.SyncDatabase"
| extend cd = parse_json(customDimensions)
| extend eventContext = parse_json(tostring(cd.eventContext))
| extend EventName = tostring(cd.eventName)
| extend DataSyncMode = iff(isempty(['dataSyncMode']), "All", tostring(customDimensions.DataSyncMode))
| where isempty(['dataSyncMode']) or DataSyncMode in (['dataSyncMode'])
| project timestamp, name, user_Id, DataSyncMode, cd, eventContext, duration
| summarize percentiles(duration, 95) by bin(timestamp, 1d), DataSyncMode
| order by timestamp desc
| project-rename ['Timestamp'] =  timestamp, ['Data sync mode'] =  DataSyncMode, ['P95 Duration (ms)'] =  percentile_duration_95
| limit 20
```

This query retrieves the P95 duration of synchronizations

### Daily sync success rate

This chart graphs the success of synchronization for all users over time.

#### Learn and diagnose sync success rates

Synchronizations can fail for various reasons, including users canceling the sync, or issues on the device, issues with network connectivity, and so on. Use the **Sync Error** page to diagnose further. Learn more in the blog post [Best Practices for Offline Mode in the Field Service mobile app - Part 3](https://www.microsoft.com/dynamics-365/blog/it/2023/11/10/best-practices-for-offline-mode-in-the-field-service-mobile-app-part-3/). The chart is based on a Kusto query such as we show in the following snippet.

```kusto
dependencies
| where timestamp between  (_startTime.._endTime)
| where name endswith "Offline.SyncDatabase"
| extend cd = parse_json(customDimensions)
| extend eventContext = parse_json(tostring(cd.eventContext))
| extend syncMode = tostring(customDimensions.DataSyncMode)
| extend EventName = tostring(cd.eventName)
| extend ScenarioResult = tostring(cd.ScenarioResult)
| where isempty(['dataSyncMode']) or syncMode in (['dataSyncMode'])
| where isnotempty(ScenarioResult)
| summarize Success = todouble(countif(ScenarioResult == "SUCCESS")), All = countif(ScenarioResult == "SUCCESS" or ScenarioResult == "FAILURE") by bin(timestamp, 1d)
| extend SuccessRate = todouble(Success/All) * 100
| project timestamp, SuccessRate
```

This query graphs the percentage of synchronizations that have been successful over time.

### Device types

This chart shows a pie chart of the types of devices users are using.

#### Learn and diagnose based on device types

Performance of the Field Service mobile app can vary significantly across device types. Make sure your users have the latest mobile devices to have the best mobile experience possible. The chart is based on a Kusto query such as we show in the following snippet.

```kusto
dependencies
| where timestamp between  (_startTime.._endTime)
| where name == "Offline.SyncDatabase"
| extend cd = parse_json(customDimensions)
| where isnotempty(user_Id) // Filter out rows where user_Id is empty
| where cd.AppFlavor == "FieldService"
| extend appVersion = tostring(cd.AppInfo\_Version)
| extend Version = extract(@"\b\d+\.(\d+\.\d+)", 1, appVersion)
| extend DeviceInfo_OsName = tostring(cd.DeviceInfo_OsName)
| extend DeviceInfo_MakeModel = strcat(tostring(cd.DeviceInfo_make), " ", tostring(cd.DeviceInfo_model))
| summarize count() by DeviceInfo_MakeModel
```

The query shows the distribution of device types being used for offline synchronization.

## Sync errors

From the dashboard, you can access a dedicated page for synchronization errors. This page shows a summary and timeline of synchronization errors for the Field Service mobile app in offline mode.

:::image type="content" source="media/fs-mobile-offline-dashboard-sync-errors.png" alt-text="The Sync errors report with two cards for a list of synchronization errors summary and sync error timeline." lightbox="media/fs-mobile-offline-dashboard-sync-errors.png":::

### Sync errors summary

This table shows the types of errors users have been experiencing.

#### Learn and diagnose sync errors

Sync errors occur for various reasons. The problem can be temporary. Frequent occurrences of a specific error might indicate a systemic issue and should be investigated further. If any support is required its recommended raise a support ticket for assistance to diagnose further. The chart is based on a Kusto query such as we show in the following snippet.

```kusto
dependencies
| where timestamp between  (_startTime.._endTime)
| where name == "Offline.SyncDatabase"
| where success == false
| extend cd = parse_json(customDimensions)
| extend AppVersion = tostring(cd.AppInfo_Version)
| extend ErrorCode = tostring(cd.ErrorCode)
| extend ErrorMessage = tostring(cd.ErrorMessage)
| extend FailureType = tostring(cd.FailureType)
| where isempty(['userId']) or user_Id == ['userId']
| summarize UsersImpacted = dcount(user_Id), ErrorCount= count() by ErrorCode, ErrorMessage, FailureType
| order by ErrorCount
| project-rename ['Error code'] = ErrorCode,['Error message'] = ErrorMessage, ['Failure type'] = FailureType, ['Errors'] = ErrorCount,  ['Users impacted'] = UsersImpacted
| order by ['Error code']
```

Use this type of query to gain an insight into the type of offline sync errors

### Sync errors timeline

This table shows the number of sync errors occurring over time

#### Learn and diagnose sync errors over time

This graph provides further insights into any time-based patterns of when sync errors are occurring. If any support is required its recommended raise a support ticket for assistance to diagnose further. The chart is based on a Kusto query such as we show in the following snippet.

```kusto
dependencies
| where timestamp between  (_startTime.._endTime)
| where name == "Offline.SyncDatabase"
| where success == false
| where isempty(['userId']) or user_Id == ['userId']
| extend cd = parse_json(customDimensions)
| extend AppVersion = tostring(cd.AppInfo\_Version)
| extend ErrorCode = tostring(cd.ErrorCode)
| extend ErrorMessage = tostring(cd.ErrorMessage)
| extend FailureType = tostring(cd.FailureType)
| where isempty(['errorMessage']) or ErrorMessage contains ['errorMessage']
| summarize ['Users Impacted'] = dcount(user_Id), Errors = count() by bin(timestamp, 1d)
| render timechart
```

This type of query gives you the number of errors and users impacted over time.

## Sync performance

The dashboard also includes a report of performance issues for synchronizing the Field Service mobile app. This dashboard provides insights into the following areas:

- Offline filter performance

- Network connectivity

- Average duration of syncs by device type

### Offline filter performance

This table shows the time taken by the server to retrieve table records related to an *Offline Filter* query during a sync.

#### Learn and diagnose offline filters

Offline filter performance is crucial to ensuring a good sync experience for users. Multiple joins and related records can generate expensive SQL queries. Read these blog articles for guidance on how to improve offline sync performance:

- [Best Practices for Offline Mode in the Field Service mobile app - Part 2](https://www.microsoft.com/dynamics-365/blog/administrator/2023/11/08/best-practices-for-offline-mode-in-the-field-service-mobile-app-part-2/)  
- [Best Practices for Offline Mode in the Field Service mobile app - Part 3](https://www.microsoft.com/dynamics-365/blog/it-professional/2023/11/10/best-practices-for-offline-mode-in-the-field-service-mobile-app-part-3/)  

The chart is based on a Kusto query such as we show in the following snippet.

```kusto
dependencies
| where timestamp between  (_startTime.._endTime)
| where name startswith "Offline.SyncDatabase"
| extend cd = parse_json(customDimensions)
| extend eventContext = parse_json(tostring(cd.EventContext))
| extend currentSyncId = tostring(eventContext["CurrentSyncId"])
| project operation_Id, currentSyncId
| where isempty(['externalCorrelationId']) or operation_Id == ['externalCorrelationId']
| join
(
    dependencies
    | where timestamp > ago(7d)
    | where type == "SDKRetrieveMultiple"
    | extend requestId = trim_end("_([a-z0-9-]*)", operation_Id)
) on $left.operation_Id == $right.requestId
| summarize  percentiles(duration, 50,95) by target
| order by  percentile_duration\_95
| project Table = target, ['Average Duration (ms)'] = round(percentile\_duration\_50, 0), ['P95 Duration (ms)'] = round(percentile_duration_95, 0)
```

This query joins the offline requests with the backend server SDK RetrieveMultiple requests to correlate the sync with specific offline filter queries against a table.

### Network connectivity

This table shows a view of the network connectivity for mobile users by geography, showing network throughput and latency.

#### Learn and diagnose connectivity

Networking challenges can have significantly effect on the overall experience of users. Various factors influence performance. Make sure you review network sync intervals, and consider allowing sync over Wifi only (preview) to improve battery performance under challenging network conditions. Learn more at [View offline sync status - Power Apps](/power-apps/mobile/offline-sync-icon#offline-sync-setting). The chart is based on a Kusto query such as we show in the following snippet.

```kusto
pageViews
| where timestamp between  (_startTime.._endTime)
| extend hostType = tostring(customDimensions.hostType)
| where hostType == "MobileApplication"
| extend networkConnectivityState = tostring(customDimensions.networkConnectivityState)
| extend warmThroughput = toint(customDimensions.warmThroughput)
| extend warmLatency = toint(customDimensions.warmLatency)
| extend coldLatency = toint(customDimensions.coldLatency)
| extend City = client\_City
| extend stateorProvince = client\_StateOrProvince
| extend countryOrRegion = client\_CountryOrRegion
| where isempty(['userId']) or user_Id == ['userId']
| order by ['Latency ms'] desc
| limit 100
| project timestamp, networkConnectivityState, warmThroughput, warmLatency, coldLatency, City, stateorProvince, countryOrRegion
| summarize ['Throughput Kbs'] = percentile(warmThroughput, 95), ['Latency ms'] =  percentile(warmLatency, 95), ['Online Count'] = countif(networkConnectivityState == "online"), ['Offline Count'] = countif(networkConnectivityState == "offline")  by ['State'] = stateorProvince, ['Country'] = countryOrRegion
```

This query makes use of the *pageviews* table from the [model-driven app telemetry](/power-platform/admin/telemetry-events-model-driven-apps#where-is-the-page-load-data-available) to help to understand network information – filtered by hosts that are mobile apps.

### Average duration of syncs by device type

This table shows the sync duration by the type of device used by users.

#### Learn and diagnose device types

In order to ensure the best experience for users, we recommend that you make sure they use supported mobile devices, and that the devices meet the recommended benchmark and storage requirements. Learn more at [Supported mobile devices](/dynamics365/field-service/mobile/download-mobile-app#supported-mobile-devices). The chart is based on a Kusto query such as we show in the following snippet.

```kusto
dependencies
| where name == "Offline.SyncDatabase"
| extend cd = parse_json(customDimensions)
| extend ActiveDuration = toint(tostring(cd.ActiveDuration))
| extend WithBackgroundTime = duration
| extend DataSyncMode = tostring(cd.DataSyncMode)
| extend DeviceInfo_OsName = tostring(cd.DeviceInfo_OsName)
| extend DeviceInfo_Make = tostring(cd.DeviceInfo_make)
| extend DeviceInfo_Model = tostring(cd.DeviceInfo_model)
| where isnotempty(DataSyncMode)
| summarize percentile_ActiveDuration_95= round(percentile(ActiveDuration, 95)/1000, 0), percentile_WithBackgroundTime_95 = round(percentile(WithBackgroundTime, 95)/1000, 0) by client_Type, DataSyncMode, DeviceInfo_Make, DeviceInfo_Model
| order by DataSyncMode, client_Type, DeviceInfo_Make, DeviceInfo_Model
| project ['Data sync mode']  = DataSyncMode, ['Client type'] = client_Type, ['Device Make'] = DeviceInfo_Make,['Model'] = DeviceInfo_Model, ['P95 Active Duration (in seconds)'] = percentile_ActiveDuration_95, ['P95 With Background Time Duration (in seconds)'] = percentile_WithBackgroundTime_95
```

This query extracts duration and device information for `Offline.SyncDatabase` records from the dependencies table, and aggregates by device type.

## Sync payload

The package also includes a dashboard that shows the number of records stored, synchronized and the size of the data synchronization.

:::image type="content" source="media/fs-mobile-offline-dashboard-sync-payload.png" alt-text="Screenshot of a dashboard with three reports." lightbox="media/fs-mobile-offline-dashboard-sync-payload.png":::

The dashboard includes three charts that show the following information:

- Records on the device
- Records synchronized
- Payload size

### Records on the device

This table shows the % of records being synchronized by table.

#### Learn and diagnose the records

Very large tables can take a lot of time to download. Make sure only the fields required for the mobile experience are synchronized. Learn more in the blog post [Improve Mobile Offline performance with Offline Table Column Selection](https://www.microsoft.com/dynamics-365/blog/it-professional/2024/07/08/improve-mobile-offline-performance-with-offline-table-column-selection/) and the article [Optimize the offline profile](/power-apps/mobile/mobile-offline-guidelines#optimize-dowloaded-data-with-offline-table-column-selection-preview). The chart is based on a Kusto query such as we show in the following snippet.

```kusto
dependencies
| where timestamp between  (_startTime.._endTime)
| where isempty(['userId']) or user_Id == ['userId']
| where name startswith "Offline.DataSyncV3"
| extend cd = parse_json(customDimensions)
| extend eventContext = parse_json(tostring(cd.EventContext))
| extend entityName = tostring(eventContext.EntityName)
| extend recordCount = toint(eventContext.RecordCount)
| extend currentSyncId = tostring(eventContext.CurrentSyncId)
| where recordCount > 0
| where isnotempty(entityName)
| project timestamp, recordCount, entityName, currentSyncId
| summarize sum(recordCount) by entityName, currentSyncId
| summarize avg(sum\_recordCount) by entityName
```

This pie chart shows the number of records on the device by table name – sourced from the `Offline.DataSyncV3` set of records within the dependencies table.

### Records synced

This timeline shows the count of records synchronized, optionally filtered by Data sync mode and/or table.

#### Learn and diagnose the number of records that are synced

Frequently changing records can cause data to be downloaded to all engineers' devices regularly. Where possible, make sure that the offline filters restrict the data that is downloaded to only that which is required by the specific engineer in order to complete their job. Review the blog post [Best Practices for Offline Mode in the Field Service mobile app - Part 1](https://www.microsoft.com/dynamics-365/blog/it-professional/2023/11/06/best-practices-for-offline-mode-in-the-field-service-mobile-app-part-1/). The chart is based on a Kusto query such as we show in the following snippet.

```kusto
dependencies
| where timestamp between (['_startTime'] .. ['_endTime']) // Time range filtering
| where isempty(['userId']) or user_Id == ['userId'] // Single selection filtering
| where name startswith "Offline"
| extend cd = parse_json(customDimensions)
| extend eventContext = parse_json(tostring(cd.EventContext))
| extend entityName = tostring(eventContext.EntityName)
| where entityName == ['tableName'] // Single selection filtering
| extend dataSyncMode  = iff(isempty(['dataSyncMode']), "All", tostring(customDimensions.DataSyncMode))
| where isempty(['dataSyncMode']) or dataSyncMode == ['dataSyncMode']
| extend recordCount = toint(eventContext.RecordCount)
| extend currentSyncId = tostring(eventContext.CurrentSyncId)
| where recordCount > 0
| where isnotempty(entityName)
| project timestamp, recordCount, entityName,  user_Id
| order by timestamp asc
| extend syncCount = recordCount
| summarize sum(syncCount) by bin(timestamp, 1min)
```

This timeline shows the number of records being synced. You can filter the view by sync mode, user name, and table name.

### Payload size

This table shows average response size in Kb per data sync mode type.

#### Learn and diagnose the sizes

Downloading a significant amount of data for offline usage can impact download time and device storage. The offline filter should be configured to only download the records required by the engineering. Also make sure you configure only the columns required for the mobile experience to reduce the overall payload. The blog post [Improve Mobile Offline performance with Offline Table Column Selection](https://www.microsoft.com/dynamics-365/blog/it-professional/2024/07/08/improve-mobile-offline-performance-with-offline-table-column-selection/) provides details on feature to limit the number of columns. Review the blog post [Best Practices for Offline Mode in the Field Service mobile app - Part 2](https://www.microsoft.com/dynamics-365/blog/administrator/2023/11/08/best-practices-for-offline-mode-in-the-field-service-mobile-app-part-2/) for details are reducing the size of the metadata being downloaded. The chart is based on a Kusto query such as we show in the following snippet.

```kusto
dependencies
| where timestamp between  (_startTime.._endTime)
| where name startswith "Offline "
| extend cd = parse_json(customDimensions)
| extend eventContext = parse_json(tostring(cd.EventContext))
| extend entityName = tostring(eventContext.EntityName)
| extend syncMode = tostring(customDimensions.DataSyncMode)
| extend contentLength = toint(eventContext.ContentLength)
| extend responseSize = toint(eventContext.ResponseSize)
| extend shortName = trim_start("Offline.DdsClient.([A-Za-Z)*])", name)
| where isnotempty(syncMode)
| where responseSize > 0
| extend responseSizeKb = responseSize/1024
| project timestamp, contentLength, responseSize,responseSizeKb, entityName,  user_Id, syncMode, shortName
| summarize ['Average Response Size in Kb'] = round(avg(responseSizeKb)) by syncMode
| project-rename ['Data sync mode'] = syncMode
| order by ['Average Response Size in Kb']
```

This query retrieves all of the offline sync records within the dependencies table aggregate the response size by sync mode.

## Sync details

The package also includes a **Sync details** report that you can use to drill into individual users' synchronization.

### User sync details

This table shows the detailed sync records over a time (optionally filtered by a specific user and/or external correlation ID)

#### Learn and diagnose users

Use this table to diagnose individual requests for a specific user. If a user has provided the external correlation ID from their Field Service mobile app's About page, you can use that ID to filter the report. Use this information to understand the time taken to synchronize, the device used, and whether any errors occurred. The chart is based on a Kusto query such as we show in the following snippet.

```kusto
dependencies
| where name startswith "Offline"
| where isempty(['userId']) or user_Id == ['userId'] // Single selection filtering
| extend cd = parse_json(customDimensions)
| extend ActiveDuration = toint(tostring(cd.ActiveDuration))
| extend WithBackgroundTime = duration
| extend DataSyncMode = tostring(cd.DataSyncMode)
| extend ErrorMessage = tostring(cd.ErrorMessage)
| extend DeviceInfo_OsName = tostring(cd.DeviceInfo_OsName)
| extend DeviceInfo_make = tostring(cd.DeviceInfo_make)
| extend DeviceInfo_model = tostring(cd.DeviceInfo_model)
| extend appVersion = tostring(cd.AppInfo_Version)
| where isnotempty(DataSyncMode)
| summarize P95ActiveDurationInSec = round(percentile(ActiveDuration, 95)/1000, 0),P95WithBackgroundTimeInSec = round(percentile(WithBackgroundTime, 95)/1000, 0), arg_max(timestamp, ErrorMessage), Failures = countif(success == false) by UserAzureObjectID = user_Id, DataSyncMode,DeviceInfo_OsName, DeviceInfo_make, DeviceInfo_model, appVersion, operation_Id
| project ['Timestamp'] = timestamp, ['User Azure Object ID'] = UserAzureObjectID, ['External Correlation Id'] = operation_Id, ['Data Sync Mode'] = DataSyncMode, ['OS'] = DeviceInfo_OsName, ['Make'] = DeviceInfo_make, ['Model'] =  DeviceInfo_model,['App Version'] = appVersion, ['P95 Active duration (seconds)'] = P95ActiveDurationInSec , ['P95 with background time (sec)'] = P95WithBackgroundTimeInSec,Failures, ['Error message'] = ErrorMessage
| order by Timestamp desc
```

The query drills into the detailed synchronization events for users. Use this to do detailed diagnostics.
<!-- 
## Tags

*Field Service Features:* Field Service Mobile, Power App Mobile -->

## Related information

- [Dynamics 365 Field Service mobile app](/dynamics365/field-service/mobile/overview)  
- [Telemetry events for mobile app synchronization and actions](/power-platform/admin/telemetry-events-mobile)  
- [Visualize data with Azure Data Explorer dashboards](/azure/data-explorer/azure-data-explorer-dashboards)  
