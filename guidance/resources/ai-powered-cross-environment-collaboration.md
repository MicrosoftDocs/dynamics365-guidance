---
title: Cross-environment collaboration with Copilot in Dynamics 365
description: Sample implementation that helps you enhance team collaboration and customer experience with contextual insights for agents across multiple environments with customer engagement apps.
author: sobiswas
ms.author: sobiswas
ms.topic: solution-overview
ms.date: 04/07/2025
ms.custom:
  - ai-gen-docs-bap
  - ai-seo-date:4/07/2025
  - O25-Service
# CustomerIntent: As an agent, I want to get opportunity details about the customer from a different Dynamics 365 app.
---

# Cross-environment collaboration with Copilot in Dynamics 365

***Applies to:** Dynamics 365 Customer Service Workspace and Dynamics 365 Sales*

This article walks you through a solution that can help you enhance team collaboration and customer experience with contextual insights for agents in Dynamics 365 implementations with more than one customer engagement app.

In today's interconnected business landscape, seamless collaboration across departments and systems is essential for delivering exceptional customer experiences and driving growth. However, when different business units use different Dynamics 365 apps, achieving this level of collaboration can be challenging. This scenario illustrates how Microsoft Copilot can come into play, acting as a bridge that enhances communication and workflow between teams. As a result, valuable customer insights are shared and used effectively.

In this article, we explore how Copilot can act as a bridge between teams working in different environments with Dynamics 365 apps to drive better collaboration and results.

## Scenario

Contoso, a global leader in its industry, operates with two key business units: Service Management and Sales. The Service Management team focuses on delivering top-notch customer support, while the Sales team is dedicated to driving revenue growth through strategic client engagement. To cater to their unique needs, the Service Management team used Dynamics 365 Customer Service, and the Sales team uses Dynamics 365 Sales.

Here's how Copilot transforms collaboration at Contoso:

Imagine a service agent, Emma, from the Service Management team. When a new case appears, Emma uses Copilot to access a comprehensive view of the customer's profile—including their purchase history, preferences, and prior interactions. Emma also receives opportunity insights related to the customer from Dynamics 365 Sales. With this information readily available, Emma not only resolves the issue efficiently but also identifies potential cross-sell and up-sell opportunities relevant to the customer.

Instead of these insights being confined to Dynamics 365 Customer Service, Copilot ensures that they're seamlessly shared with the Sales team in Dynamics 365 Sales. The Sales team can then follow up with tailored offers or engagement strategies based on Emma's insights to build stronger relationships and drive more revenue.

This synergy between the Service Management and Sales teams, powered by Copilot, not only enhances the customer experience but also aligns the efforts of both teams toward Contoso's overarching business goals. The result? A collaborative ecosystem that turns customer interactions into growth opportunities.

## Solution Architecture

### Approach

Copilot in Customer Service consumes data from Contoso's Sales team's use of Dynamics 365 Sales. Copilot uses a custom connector to invoke an Azure Function, which retrieves data from the Sales data. An out-of-the-box opportunity summary plugin, `msdyn_SalesOpportunitySummary`, is invoked to summarize opportunity-related information based on the specified customer name. The opportunity summary is then returned as a response to the prompt in the Customer Service Workspace (CSW) Copilot pane.

:::image type="content" source="media/CrossInstanceCopilot/ai-solution-architecture.png" alt-text="Diagram illustrating the solution architecture. The Customer Service Workspace app calls a custom connector, which invokes an Azure Function. The function retrieves opportunity details from another Dynamics 365 instance by calling the out-of-the-box 'msdyn_SalesOpportunitySummary' action." lightbox="media/CrossInstanceCopilot/ai-solution-architecture.png":::

## Implementation steps

In this section, we take you through the five steps to implement this sample.

1. Create an Azure Function
2. Create a custom connector
3. Verify and publish the custom connector
4. Configure the custom plugin
5. Test the plugin

### Create the Azure Function

Follow the steps here to create a sample Azure function that retrieves opportunity details from a Dynamics 365 Sales solution.

1. Create a new Azure Functions project in Visual Studio with an HTTP trigger, version 4.0, and a .NET 8.0 isolated function worker.

1. Install the `Microsoft.Azure.WebJobs.Extensions.OpenApi.Core` NuGet package in the project.

    ```csharp
    [Function("DealSummary")]
    [OpenApiOperation(operationId: "DealSummary")]
    [OpenApiSecurity("function_key", SecuritySchemeType.ApiKey, Name = "code", In = OpenApiSecurityLocationType.Query)]
    [OpenApiParameter(name: "customerName", In = ParameterLocation.Query, Required = false, Type = typeof(string), Description = "customerName")]
    [OpenApiResponseWithBody(statusCode: HttpStatusCode.OK, contentType: "text/plain", bodyType: typeof(Response), Description = "Deal Summary for a customer")]
    ```

1. Fetch the opportunity record ID from the Sales environment by running a query based on the parameter provided to the Azure Function. In this example, we retrieved the top opportunity record for a specific customer.

1. Invoke the out-of-the-box `msdyn_SalesOpportunitySummary` action by providing the opportunity ID and obtain the summarized response. The following code snippet shows an example.

    ```csharp
    Guid opportunityId = opportunity.Id;
    var executeSalesOpportunitySummaryAction = new OrganizationRequest()
    {
        RequestName = "msdyn_SalesOpportunitySummary"
    };
    executeSalesOpportunitySummaryAction.Parameters.Add("msdyn_id", opportunityId.ToString()); // Retrieved Opportunity Record Id.
    executeSalesOpportunitySummaryAction.Parameters.Add("msdyn_activityId", opportunityId.ToString()); // Retrieved Opportunity Record Id.
    try
    {
        var summaryResponse = this.dataverseProvider.ExecuteAsync(executeSalesOpportunitySummaryAction);
        summarizedResponse = summaryResponse == null ? string.Empty : summaryResponse.Results["msdyn_summary_raw"].ToString();
    }
    catch (Exception ex)
    {

      logger.LogTrace(ex, $"OpportunitySummaryProcessor > Error generating summary for Opportunity {opportunityId}: {ex.Message}. StackTrace: {ex.StackTrace}");
    }

    ```

1. Publish the Azure Function to Azure and retrieve the Swagger file from the hosted function app.

### Create a custom connector

Use the following steps to create a customer connector.

1. Go to the maker portal at [https://make.powerapps.com](https://make.powerapps.com) and create a new custom connector. Choose the option **create from blank**.

1. Provide a name, such as *Summarize Deal*, and then continue.

1. Provide a meaningful description since Copilot uses it to identify the plugin. For example, *Summarize the deal details for a specific customer in a paragraph.*

1. Select the **Security** page. and then choose the appropriate authentication type. 

1. Create a new action. Provide a meaningful summary and description, then switch to the Swagger editor. Copy and paste the Swagger file content from Step 1 where you created the Azure function.

    Once you toggle the **Swagger editor** field, there's a new action, and the request is created.

1. Validate the response from the Azure function.

1. Select the **AI Plugin (preview)** page, and then provide a meaningful name and description. For example, you can use a name such as *Summarize the deal details*, and in you can specify a description such as *Summarize the deal details for a specific customer in a paragraph*.

1. Choose the **Plugin Actions** action, and then select the **Enable as copilot plugin operation** field.

1. Validate the request details.

1. Choose the **Update connector** action to complete the creation of the connector. Once the process completes successfully, you can see your connector listed under the custom connectors list.

### Verify and publish the custom connector

Use the following steps to verify and publish the custom connector.

1. Go to [Copilot Studio](https://copilotstudio.microsoft.com). In Copilot Studio, choose the relevant environment.

1. Choose the **Agents** menu item in the left navigation, and then choose **Copilot in Dynamics 365 Customer Service**.

1. Use Copilot in Dynamics 365 Customer Service to create a *Connector* action.

1. Select the custom connector created in Step 2 in the Dataverse environment, and configure its actions and parameters.

1. Verify the custom connector details, edit if necessary, and publish the changes.

### Configure the custom plugin

Use the following steps to configure the custom plugin.

1. In the Customer Service Admin app, navigate to **Agent experience** > **Productivity**, and then choose **Manage Plugins for Generative AI (preview)**.  

1. You can now see the custom plugin listed here. Based on our guidance, it might have the name *Summarize Deal*. Next, turn on the plugin by following the four steps in the wizard:

1. Specify if the authentication mechanism must use **Admin** or **Agent** authentication.

1. Choose the access type as *All agents who have Copilot*. Alternatively, specific the relevant security roles.

1. Choose the **Save** action to complete the configuration. Make sure the custom plugin status is turned on.

### Test the plugin

Test the plugin by creating a prompt in Copilot and asking a question, such as *Get me details about the deal for the customer*, followed by the relevant customer's name. If you did all the configurations correctly, then you can now see the summary of the opportunity related to the specified customer in the chat window.

## Conclusion

By following these steps, you can successfully implement cross-instance collaboration with Copilot in Dynamics 365, enhancing team collaboration and delivering a superior customer experience.

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

- Sourav Das Biswas | FastTrack Solution Architect
- Sourajit Samanta | FastTrack Solution Architect
