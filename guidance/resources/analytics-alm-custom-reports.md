---
title: ALM for analytics on data model customizations
description: Migrate custom reports with minimal manual involvement by using application lifecycle management (ALM) for digital contact centers.
ms.date: 03/15/2024
ms.topic: conceptual
author: edupont04
ms.author: ashrafomar
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-seo-date:08/29/2023
  - ai-gen-desc
  - O25-Service
# CustomerIntent: As a user I want to learn something.
---

# Application lifecycle management for analytics on data model customizations

***Applies to: Dynamics 365 Customer Service***

This article provides in-depth information about application lifecycle management (ALM) for custom reports that are based on customizations of the data model of Omnichannel for Dynamics 365 Customer Service.

## Overview of ALM

ALM is an important step when you want to move the changes that are required for custom reports across environments, but you also want minimal manual involvement. Properly configured ALM can help reduce manual errors and save time.

For report customization, consider ALM for the deployment of Power BI reports. You can achieve this deployment in different ways:

- You can move Power BI reports across environments by using Power BI deployment pipelines. Alternatively, you can manually deploy Power BI reports by pointing to correct data sources.
- Because the Customer Service admin center is a model-driven app, you can embed customized reports in it.

ALM for Dynamics 365 involves the configuration of reports in the Customer Service admin center.

The following diagram illustrates the steps. Blue boxes that contain white text represent tasks that you do in Dynamics 365. Yellow boxes that contain black text represent tasks that you do in Power BI.

:::image type="content" source="media/analytics-dataverse-powerbi-alm-diagram.svg" alt-text="Diagram that shows the steps for application lifecycle management." lightbox="media/analytics-dataverse-powerbi-alm-diagram.svg":::

## Migrating the report configuration

Reports that are added in Dynamics 365 are stored in Dataverse entities.

The following entities/tables are used to store the customized report information:

- `msdyn_dataanalyticsworkspaces` has the workspace information that's configured during the initial setup for historical/real-time analytics.
- `msdyn_dataanalyticsreport` stores the customized reports that are added in the sitemap.

    - `msdyn_reportid`: The report ID in the Power BI workspace.
    - `msdyn_dataanalyticsreportid`: The primary key in Dynamics 365.
    - `msdyn_displayname`: The display name that appears on the customized report in the Customer Service workspace model-driven app.
    - `msdyn_name`: The name of the report in the Power BI workspace.
    - `msdyn_workspaceid`: The workspace ID of the Power BI workspace that was configured in the previous step.
    - `msdyn_datainsightsandanalyticsfeatureid`: *f2266eb4-226f-4cf1-b422-89c5f48b40cb* is the feature ID for historical data model customization, and *09c168be-efe2-4f08-a986-3aab7095c863* is the feature ID for real-time data model customization.

To migrate the reports that are added to the sitemap, you must move the data from the entities/tables. You can use the [Configuration Migration tool](/power-platform/alm/configure-and-deploy-tools) for this purpose. This article provides a [sample schema file](#sample-schema-file). Learn more at [Move configuration data across environments and organizations with the Configuration Migration tool](/power-platform/admin/manage-configuration-data).

After the migration, you must update the report references. In other words, you must update the Power BI workspace where the report is hosted and the report ID from the workspace. This article provides a [sample PowerShell script](#sample-powershell-script) for reference, but you can achieve the same result by using any language.

## Sample scripts

This section includes the following sample scripts:

- [Sample schema file](#sample-schema-file)
- [Sample PowerShell script](#sample-powershell-script)
- [Sample Azure DevOps YAML Pipeline](#sample-azure-devops-yaml-pipeline)

### Sample schema file

The following XML schema file consists of custom reports that are created and deployed to the Power BI workspace. You can use it to export data from the Configuration Migration tool. Learn more at [Move configuration data across environments and organizations with the Configuration Migration tool](/power-platform/admin/manage-configuration-data) and [Create a schema to export configuration data](/power-platform/admin/create-schema-export-configuration-data).

```xml
<entities>
  <entity name="msdyn_dataanalyticsreport" displayname="Data Analytics Report" etc="10427" primaryidfield="msdyn_dataanalyticsreportid" primarynamefield="msdyn_name" disableplugins="false">
    <fields>
      <field displayname="Report Id" name="msdyn_reportid" type="string" customfield="true" />
      <field displayname="Data Analytics Report" name="msdyn_dataanalyticsreportid" type="guid" primaryKey="true" />
      <field displayname="Display name" name="msdyn_displayname" type="string" customfield="true" />
      <field displayname="Name" name="msdyn_name" type="string" customfield="true" />
      <field displayname="Report Display Order" name="msdyn_displayorder" type="number" customfield="true" />
      <field displayname="Report Provision Status" name="msdyn_provisionstatus" type="bool" customfield="true" />
      <field displayname="Report Page" name="msdyn_reportpage" type="string" customfield="true" />
      <field displayname="Report Group" name="msdyn_reportgroup" type="string" customfield="true" />
      <field displayname="Report Entity Name" name="msdyn_reportentityname" type="string" customfield="true" />
      <field displayname="Report Template Id" name="msdyn_reporttemplateid" type="string" customfield="true" />
      <field displayname="Dataset Id" name="msdyn_datasetid" type="string" customfield="true" />
      <field displayname="Is Enabled" name="msdyn_isenabled" type="bool" customfield="true" />
      <field displayname="Workspace Id" name="msdyn_workspaceid" type="string" customfield="true" />
      <field displayname="datainsightsandanalyticsfeatureId" name="msdyn_datainsightsandanalyticsfeatureid" type="entityreference" lookupType="msdyn_datainsightsandanalyticsfeature" customfield="true" />
      <field displayname="Analytics Checksum" name="msdyn_analyticschecksum" type="number" customfield="true" />
    </fields>
    <filter>&lt;filter type = 'and'&gt;
          &lt;condition attribute = 'msdyn_datainsightsandanalyticsfeatureid' operator = 'eq' value = '<<Feature ID of the model customization>> '/&gt;
          &lt;condition attribute = 'msdyn_displayname' operator = 'eq' value = '<<custom report name>>'/&gt; 
        &lt;/filter&gt;</filter>
  </entity>
</entities>
```

Use *f2266eb4-226f-4cf1-b422-89c5f48b40cb* as the feature ID for historical data and *xxxx* as the feature ID for real-time data.

### Sample PowerShell script

The following script uses the client ID secret authentication mechanism. However, you can use any type of authentication by modifying the script.

This script connects to Power BI through the Power BI Rest APIs. It connects to Dataverse through the Dataverse Web APIs.

```powershell
#Get Power BI access token
function Get-PBIAccessToken {
    [CmdletBinding()]
    param(
        [Parameter(Mandatory=$true)]
        $TenantId,
        [Parameter(Mandatory=$true)]
        $PBIAppId,
        [Parameter(Mandatory=$true)]
        $PBIClientSecret
    )

    $authority = "https://login.microsoftonline.com/$TenantId/oauth2/token"
    $resource = "https://analysis.windows.net/powerbi/api"
    $body = @{
        "grant_type" = "client_credentials"
        "client_id" = $PBIAppId
        "client_secret" = $PBIClientSecret
        "resource" = $resource
    }
    Write-Host "Retreiving PBI Access Token"
    $tokenResponse = Invoke-RestMethod -Method Post -Uri $authority -Body $body
    
    return $tokenResponse.access_token
}
#Get Dataverse access token
function Get-DVAccessToken{
    [CmdletBinding()]
    param(
        [Parameter(Mandatory=$true)]
        $tenantId,
        [Parameter(Mandatory=$true)]
        $clientId,
        [Parameter(Mandatory=$true)]
        $clientSecret,
        [Parameter(Mandatory=$true)]
        $dataVerseURL
    )
    $oAuthTokenEndpoint = "https://login.microsoftonline.com/$tenantId/oauth2/v2.0/token"

    # OAuth Body Access Token Request
    $authBody = @{
        client_id = $clientId;
        client_secret = $ClientSecret;    
        scope = "$($dataVerseURL)/.default"    
        grant_type = 'client_credentials'
    }

    # Parameters for OAuth Access Token Request
    $authParams = @{
        URI = $oAuthTokenEndpoint
        Method = 'POST'
        ContentType = 'application/x-www-form-urlencoded'
        Body = $authBody
    }
    Write-Host "Retreiving CRM Access Token"
    # Get Access Token
    $authResponseObject = Invoke-RestMethod @authParams -ErrorAction Stop
    return $authResponseObject
}
function Get-DVWorkspaceId {
    [CmdletBinding()]
    param(
        [Parameter(Mandatory=$true)]
        $dvAuthResponseObject,
        [Parameter(Mandatory=$true)]
        $dataVerseURL
    )

    $getDataRequestUri = 'msdyn_dataanalyticsworkspaces?$top=5&$select=msdyn_workspaceid,msdyn_name&$filter=(msdyn_name ne ''Customer Service Managed Workspace'' and _msdyn_datainsightsandanalyticsfeatureid_value eq ''f2266eb4-226f-4cf1-b422-89c5f48b40cb'')'
    # Set up web API call parameters, including a header for the access token
    $getApiCallParams = @{
        URI = "$($dataVerseURL)/api/data/v9.1/$($getDataRequestUri)"
        Headers = @{
            "Authorization" = "$($dvAuthResponseObject.token_type) $($dvAuthResponseObject.access_token)"
            "Accept" = "application/json"
            "OData-MaxVersion" = "4.0"
            "OData-Version" = "4.0"
        }
        Method = 'GET'
    }
    Write-Host "Retreiving Dataverse DCCP Workspace Id"
    # Call API to Get Response
    $getApiResponseObject = Invoke-RestMethod @getApiCallParams -ErrorAction Stop

    return $getApiResponseObject.value[0].msdyn_workspaceid
}
function Get-DVDCCPReports {
    [CmdletBinding()]
    param(
        [Parameter(Mandatory=$true)]
        $dvAuthResponseObject,
        [Parameter(Mandatory=$true)]
        $workspaceId,
        [Parameter(Mandatory=$true)]
        $dataVerseURL
    )
    Write-Host "Retreiving DV DCCP Reports"
    $getDataRequestUri = 'msdyn_dataanalyticsreports?$select=msdyn_dataanalyticsreportid,msdyn_name,msdyn_workspaceid&$filter=(msdyn_workspaceid ne '''+$workspaceId+''' and _msdyn_datainsightsandanalyticsfeatureid_value eq ''f2266eb4-226f-4cf1-b422-89c5f48b40cb'')'
      # Set up web API call parameters, including a header for the access token
      $getApiCallParams = @{
          URI = "$($dataVerseURL)/api/data/v9.1/$($getDataRequestUri)"
          Headers = @{
              "Authorization" = "$($dvAuthResponseObject.token_type) $($dvAuthResponseObject.access_token)"
              "Accept" = "application/json"
              "OData-MaxVersion" = "4.0"
              "OData-Version" = "4.0"
          }
          Method = 'GET'
      }
      $getApiResponseObject = Invoke-RestMethod @getApiCallParams -ErrorAction Stop
      # Output
      $dvReports = $getApiResponseObject.value
    return $dvReports    
}

function Get-PBIReports {
    [CmdletBinding()]
    param(
        [Parameter(Mandatory=$true)]
        $accessToken,
        [Parameter(Mandatory=$true)]
        $workspaceId
    )
    Write-Host "Retreiving PBI Workspace Reports"
    $headers = @{
        "Authorization" = "Bearer $accessToken"
          'Content-Type' = 'application/json'
      }
    $uri = "https://api.powerbi.com/v1.0/myorg/groups/$workspaceId/reports"
    $response = Invoke-RestMethod -Uri $uri -Headers $headers -Method Get
    $pbiReports = $response.value
    return $pbiReports
    
}

function Update-DVReportReferences
{
      [CmdletBinding()]
    param(
        [Parameter(Mandatory=$true)]
        $pbiAccessToken,
        [Parameter(Mandatory=$true)]
        $dvAuthResponseObject,
        [Parameter(Mandatory=$true)]
        $workspaceId,
        [Parameter(Mandatory=$true)]
        $dataVerseURL
    )
    
    $pbiReports = Get-PBIReports -accessToken $pbiAccessToken -workspaceId $workspaceId
    Write-Host $pbiReports.Count
    $dvReports = Get-DVDCCPReports -dvAuthResponseObject $dvAuthResponseObject -workspaceId $workspaceId -dataVerseURL $dataVerseURL
    Write-Host $dvReports.Count
    Write-Host "Updating DCCP report references"
    $pbiReports
    foreach ($item in $dvReports)
      {
          $item.msdyn_name          
          $report = $pbiReports.value | Where-Object {$_.name -eq $item.msdyn_name}
          if($report -ne $null)
          {
              
              Write-Host "Updating report reference for $($item.msdyn_name) with PBI $($report.id)"
              $dvReportId = $item.msdyn_dataanalyticsreportid
              $patchRequestUri = "msdyn_dataanalyticsreports($($dvReportId))"+'?$select=msdyn_workspaceid,msdyn_dataanalyticsreportid'
              $updateBody  = @{
                  'msdyn_workspaceid' = ''+$workspaceId+''
                  'msdyn_reportid' = ''+$report.id+''
              } | ConvertTo-Json
              # Set up web API call parameters, including a header for the access token
              $patchApiCallParams = @{
                  URI = "$($dataVerseURL)/api/data/v9.1/$($patchRequestUri)"
                  Headers = @{
                      "Authorization" = "$($dvAuthResponseObject.token_type) $($dvAuthResponseObject.access_token)"
                      "Accept" = "application/json"
                      "OData-MaxVersion" = "4.0"
                      "OData-Version" = "4.0"
                      "Content-Type" = "application/json; charset=utf-8"
                      "Prefer" = "return=representation"  # in order to return data
                      "If-Match" = "*" 
                  }
                  Method = 'PATCH'
                  Body = $updateBody
              }
              
              $patchApiResponseObject = Invoke-RestMethod @patchApiCallParams -ErrorAction Stop   
          }
          else
          {
              Write-Host "Corresponding PBI report not found in PBI workspace with name $($item.msdyn_name)"
          }
      }
      return $pbiReports
}

###Sample usage########
#$PBIAppId = '<<Client ID which has access to Power BI workspace>>' 
#$TenantId = '<<Tenant Id of the DV/PBI organization>>'    
#$PBIClientSecret = "<<Secret of application user PBI>>" 
#$AppId = '<<Dataverse App id>>' 
#$ClientSecret = '<<DV client Secret>>' 
#$PowerPlatformEnvironmentUrl = "<<DV URL>>" 
#$PBIAccessToken = Get-PBIAccessToken -TenantId $TenantId -PBIAppId $PBIAppId -PBIClientSecret $PBIClientSecret
#$CRMAccessToken = Get-DVAccessToken -tenantId $TenantId -dataVerseURL $PowerPlatformEnvironmentUrl -clientId $AppId -clientSecret $ClientSecret
#$workspaceId = Get-DVWorkspaceId -dvAuthResponseObject $CRMAccessToken -dataVerseURL $PowerPlatformEnvironmentUrl
#Update-DVReportReferences -pbiAccessToken $PBIAccessToken -dvAuthResponseObject $CRMAccessToken -workspaceId $workspaceId -dataVerseURL $PowerPlatformEnvironmentUrl 
```

### Sample Azure DevOps YAML Pipeline

```yml
# Starter pipeline
# Start with a minimal pipeline that you can customize to build and deploy your code.
# Add steps that build, run tests, deploy, and more:
# https://aka.ms/yaml
trigger:
- main
pool:
  vmImage: windows-latest
steps:
- task: CopyFiles@2
  inputs:
    Contents: '**'
    TargetFolder: '$(Build.ArtifactStagingDirectory)'
    CleanTargetFolder: true
    ignoreMakeDirErrors: true
  displayName: 'Copy files from Repo'
- task: PowerPlatformToolInstaller@2
  inputs:
    DefaultVersion: true
- task: PowerPlatformExportData@2
  inputs:
    authenticationType: 'PowerPlatformSPN'
    PowerPlatformSPN: 'Optimize25CRM'
    Environment: '$(BuildTools.EnvironmentUrl)'
    SchemaFile: '$(Build.ArtifactStagingDirectory)\source\Optimize25Schema\schema_sample.xml'
    DataFile: 'data.zip'
  displayName: 'Export reports sitemap data from Source'
- task: PowerPlatformImportData@2
  inputs:
    authenticationType: 'PowerPlatformSPN'
    PowerPlatformSPN: 'Optimize25POC'
    Environment: '$(BuildTools.EnvironmentUrl)'
    DataFile: 'data.zip'
  displayName: 'Import reports sitemap data to Target' 
- task: PowerShell@2  
  inputs:
    targetType: 'inline'
    script: |
      $ScriptContent = Get-Content "$(Build.ArtifactStagingDirectory)\source\automation\PipelineScript.ps1" -Raw
      Invoke-Expression $ScriptContent      
      # Write your PowerShell commands here.
      Write-Host "Assigning connection variables"   
      $PBIAppId = '$(PBIClientId)' 
      $PBIClientSecret = '$(PBIClientSecret)'
      $TenantId = '$(TenantId)'    
      $AppId = '$(CRMClientId)' 
      $ClientSecret = '$(CRMClientSecret)'  
      $PowerPlatformEnvironmentUrl = '$(GetConnectionVar.PowerPlatformEnvironmentUrl)' 
      $PBIAccessToken = Get-PBIAccessToken -TenantId $TenantId -PBIAppId $PBIAppId -PBIClientSecret $PBIClientSecret
      $CRMAccessToken = Get-DVAccessToken -tenantId $TenantId -dataVerseURL $PowerPlatformEnvironmentUrl -clientId $AppId -clientSecret $ClientSecret
      $featureId = 'f2266eb4-226f-4cf1-b422-89c5f48b40cb'      
      $workspaceId = Get-DVWorkspaceId -dvAuthResponseObject $CRMAccessToken -dataVerseURL $PowerPlatformEnvironmentUrl -featureId $featureId
      Write-Host $workspaceId
      Update-DVReportReferences -pbiAccessToken $PBIAccessToken -dvAuthResponseObject $CRMAccessToken -workspaceId $workspaceId -dataVerseURL $PowerPlatformEnvironmentUrl  -featureId $featureId
```

## Related information

The following resources can help you learn more about the built-in analytics capabilities of Omnichannel for Dynamics 365 Customer Service.

- [Overview of real-time analytics dashboard](/dynamics365/customer-service/intro-realtime-analytics-dashboard)
- [Historical analytics for unified routing in Omnichannel for Customer Service](/dynamics365/customer-service/oc-historical-analytics-unified-routing)
- [Model customization of historical and real-time analytics reports in Customer Service](/dynamics365/customer-service/model-customize-reports?tabs=historicaldatamodel%2Chistoricaldatamodelcustomization)
- [Microsoft Power Platform Build Tools for Azure DevOps](/power-platform/alm/devops-build-tools)
- [Move configuration data across organizations](/power-platform/admin/manage-configuration-data)
- [Microsoft Power Platform CLI data command group](/power-platform/developer/cli/reference/data)
- [Overview of Power BI deployment pipelines](/power-bi/create-reports/deployment-pipelines-overview)
- [Power BI REST APIs for embedded analytics and automation](/rest/api/power-bi/)

## Next step

- [Configure analytics and insights dashboards in Dynamics 365 Customer Service](/dynamics365/customer-service/configure-customer-service-analytics-insights-csh) 

<!--## Tags

*Industries:* Services (70-89)

*Stakeholders* Customer services, IT, Operations, Project Management, Service operations

*Products:* Dynamics 365 Customer Service, Dynamics 365 Customer Service Insights-->
