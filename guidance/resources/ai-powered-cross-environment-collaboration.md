---
title: Cross-environment collaboration with Copilot in Dynamics 365
description: Learn how Copilot can act as a bridge between teams working with Dynamics 365 apps in different environments to drive better collaboration and results.
author: sobiswas
ms.author: sobiswas
ms.topic: solution-overview
ms.date: 04/07/2025
ms.custom:
  - ai-gen-docs-bap
  - ai-seo-date:4/07/2025
  - O25-Service
# CustomerIntent: As a customer service representative, I want to get opportunity details about the customer from a different Dynamics 365 app.
---

# Cross-environment collaboration with Copilot in Dynamics 365

***Applies to:** Dynamics 365 Customer Service Workspace and Dynamics 365 Sales*

In today's interconnected business landscape, seamless collaboration across departments and systems is essential for delivering exceptional customer experiences and driving growth. However, when different business units use different Dynamics 365 apps, achieving this level of collaboration can be challenging. This article explores how Microsoft Copilot can help by acting as a bridge between teams, enhancing communication and workflow so that valuable customer insights can be shared and used effectively.

## Scenario

Contoso, a global leader in its industry, operates with two key business units: Service Management and Sales. The Service Management team uses Dynamics 365 Customer Service to deliver top-notch customer support. The Sales team drives revenue growth through strategic client engagement with Dynamics 365 Sales. Insights from the Sales team are crucial for the Service Management team to provide personalized support and identify cross-sell and up-sell opportunities. However, the two teams work in separate environments, making it difficult to share insights and collaborate effectively. Here's how Copilot transformed collaboration at Contoso.

Emma is a service representative on the Service Management team. When a new case appears, Emma uses Copilot to access a comprehensive view of the customer's profile in Dynamics 365 Customer Service, including their purchase history, preferences, and prior interactions. Copilot also provides opportunity insights related to the customer from Dynamics 365 Sales. With this information readily available, Emma not only resolves the issue efficiently but also identifies potential cross-sell and up-sell opportunities that are relevant to the customer. Copilot seamlessly shares Emma's insights with the Sales team in Dynamics 365 Sales. The Sales team can then follow up with tailored offers or engagement strategies to build stronger relationships and drive more revenue.

The seamless sharing of information through Copilot creates a synergy between the two teams that not only enhances the customer experience but also aligns the efforts of both teams toward Contoso's overarching business goals. The result? A collaborative ecosystem that turns customer interactions into growth opportunities.

## Solution architecture

As illustrated in the following architecture diagram, Copilot in Customer Service uses a custom connector to invoke a function app, which retrieves opportunity details from the data in Dynamics 365 Sales. It then invokes an out-of-the-box plugin, `msdyn_SalesOpportunitySummary`, to summarize opportunity-related information based on the specified customer name. The opportunity summary is returned as a response to the prompt in the Copilot pane in Customer Service workspace.

:::image type="content" source="media/CrossInstanceCopilot/ai-solution-architecture.png" alt-text="Diagram illustrating the solution architecture of the Copilot bridge. Customer Service workspace calls a custom connector that invokes a function app. The function app retrieves opportunity details from another Dynamics 365 instance by calling the out-of-the-box 'msdyn_SalesOpportunitySummary' action." lightbox="media/CrossInstanceCopilot/ai-solution-architecture.png":::

## Implementation steps

In the following sections, we take you through the five steps to implement this sample solution:

1. Create a function app in Azure Functions.
1. Create a custom connector.
1. Verify and publish the custom connector.
1. Configure the custom plugin.
1. Test the plugin.

### Create the function app

The following steps create a sample function app that retrieves opportunity details from a Dynamics 365 Sales solution.

1. Create an Azure Functions project in Visual Studio with an HTTP trigger of version 4.0 and a .NET 8.0 isolated function worker.

1. Install the `Microsoft.Azure.WebJobs.Extensions.OpenApi.Core` NuGet package in the project. In the following C# code sample, we call the function app `DealSummary`.

    ```csharp
    [Function("DealSummary")]
    [OpenApiOperation(operationId: "DealSummary")]
    [OpenApiSecurity("function_key", SecuritySchemeType.ApiKey, Name = "code", In = OpenApiSecurityLocationType.Query)]
    [OpenApiParameter(name: "customerName", In = ParameterLocation.Query, Required = false, Type = typeof(string), Description = "customerName")]
    [OpenApiResponseWithBody(statusCode: HttpStatusCode.OK, contentType: "text/plain", bodyType: typeof(Response), Description = "Deal Summary for a customer")]
    ```

1. Fetch the opportunity record ID from the Sales environment by running a query based on the parameter that's provided to the function app. In this example, we retrieved the top opportunity record for a specific customer.

1. Invoke the out-of-the-box `msdyn_SalesOpportunitySummary` action by providing the opportunity ID and obtain the summarized response, as shown in the following C# code snippet.

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

1. Publish the function app to Azure Functions and retrieve the Swagger file from the hosted function app.

### Create a custom connector

The following steps create a custom connector that invokes the function app.

1. In the Power Apps maker portal, [https://make.powerapps.com](https://make.powerapps.com), create a custom connector from blank.

1. Enter a name, such as *Summarize Deal*, and then continue.

1. Enter a meaningful description, such as *Summarize the deal details for a specific customer in a paragraph*. Copilot uses it to identify the plugin.

1. Select the **Security** page, and then choose the appropriate authentication type.

1. Create an action. Enter a meaningful summary and description, and then switch to the Swagger editor.

1. Copy the Swagger file content from the function app and paste it in the Swagger editor.

    After you toggle the **Swagger editor** field, the action and request are created.

1. Validate the response from the function app.

1. Select the **AI Plugin (preview)** page. Enter a meaningful name, such as *Summarize the deal details*, and description, such as *Summarize the deal details for a specific customer in a paragraph*.

1. Select **Plugin Actions**, and then select the **Enable as copilot plugin operation** field.

1. Validate the request details.

1. Select the **Update connector** action to complete the creation of the connector.

    Your connector appears in the custom connectors list.

### Verify and publish the custom connector

1. In [Copilot Studio](https://copilotstudio.microsoft.com), select your Dynamics 365 Customer Service environment.

1. In the left navigation bar, select **Agents**, and then select **Copilot in Dynamics 365 Customer Service**.

1. Use Copilot in Dynamics 365 Customer Service to create a *Connector* action.

1. In the Dataverse environment, select the custom connector you created and configure its actions and parameters.

1. Verify the custom connector details, edit if necessary, and publish the changes.

### Configure the Copilot plugin

1. In the Customer Service admin center, go to **Agent experience** > **Productivity**. Select **Manage Plugins for Generative AI (preview)**.

    The Copilot plugin is listed here. In our example, its name is *Summarize Deal*.

1. To turn on the plugin, follow the four steps in the wizard.

1. Specify either **Admin** or **Agent** as the authentication mechanism.

1. Select **All agents who have Copilot** as the access type. Alternatively, select specific security roles.

1. Select **Save**. Make sure that the custom plugin is turned on.

### Test the plugin

To test the plugin, ask a question in the Copilot pane, such as *Get me details about the deal for the customer*, followed by the customer's name. If a summary of the opportunity that's related to the specified customer appears in the chat window, your configuration is correct.

## Conclusion

This article described a method for implementing cross-instance collaboration with Copilot in Dynamics 365. Using the capabilities of Microsoft Copilot, organizations can bridge the gap between different Dynamics 365 apps, allowing teams to share valuable insights and collaborate effectively. The solution architecture and implementation steps outlined in this article provide a comprehensive guide for setting up this cross-instance collaboration.

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

- Sourav Das Biswas | FastTrack Solution Architect
- Sourajit Samanta | FastTrack Solution Architect
