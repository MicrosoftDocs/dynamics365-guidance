---
title: Streamlining Inventory Visibility in Field Service
description: Find examples on how to extend the Field Service Copilot chat to integrate with the Inventory Visibility app in Supply Chain Management.
ms.topic: concept-article
ms.date: 07/30/2025
author: sabrinadibartolomeo
ms.author: sabrinadi
ms.reviewer: 
contributors: sourajitsamanta
---

# Streamline inventory visibility in Field Service

This article provides a step-by-step guide to extend Microsoft Copilot chat within a model-driven app to optimize Field Service. By integrating external data sources and customizing the Copilot agent using Copilot Studio, Field Service Managers gain real-time access to inventory data, enabling more efficient and informed decision-making.

The goal of this article is to highlight the potential of using agents in the context of Dynamics 365 Field Service. When choosing the appropriate technology, it is essential to consider factors such as the number of users, costs, security, and required performance.

The article explores two possible contexts:

1.	Solution A – where Dynamics 365 Field Service is not directly linked to a Dynamics 365 Supply Chain Management environment. For this scenario, the article explains how to extend the Copilot Chat in the Field Service app. 
2.	Solution B – where Dynamics 365 Field Service is directly linked to a Dynamics 365 Supply Chain Management environment through the Power Platform Integration. For this scenario, the article explains how to extend the Copilot Chat of a custom model-driven app.

Solution A describes how to create an Azure Function and is based on this article: [Cross-environment collaboration with Copilot in Dynamics 365](/dynamics365/guidance/resources/ai-powered-cross-environment-collaboration). Therefore, the intended audience is professional developers. Scenario B, however, is targeted at advanced makers.

> [!NOTE]
> The feature of extending Microsoft Copilot within a model-driven app is in preview.

## Prerequisites

- Install the [Inventory Visibility Add-in](/dynamics365/supply-chain/inventory/inventory-visibility-setup).

## Example scenario

A Field Service manager is preparing a work order for an upcoming customer site visit. Before dispatching a technician, it's crucial to verify the availability of all required parts.
In traditional Field Service workflows, when a Field Service manager creates a work order and adds required products, there is no immediate insight into whether those products are available in inventory, particularly when the work order products are is in the **Estimated** status and inventory is managed outside of Field Service. This can lead to service delays due to unavailable parts or Partial work order completion.

Rather than logging into the Supply Chain Management system or contacting warehouse personnel, the manager simply opens the Copilot chat embedded within the work order form and selects the **Provide WO Products Inventory Info** prompt. Within moments, Copilot provides a formatted table displaying product availability across various sites and locations, key insights and recommendations allowing the manager to make quick, informed decisions with confidence.

## Solution A – Field Service environment not linked to the Finance environment

By extending the Copilot chat of the Field Service app Field Service managers can check inventory availability directly from the Copilot chat not leaving the Work Order form. 
A newly introduced prompt guides the manager by suggesting the exact phrase to enter in the Copilot chat, making it easy to trigger the desired functionality and retrieve inventory details efficiently.

:::image type="content" border="true" source="media/field-service-streamline-inventory-visibility-1.svg" alt-text="Streamlining Inventory Visibility in Field Service Solution A" lightbox="media/field-service-streamline-inventory-visibility-1.svg":::

### Solution architecture

:::image type="content" border="true" source="media/field-service-streamline-inventory-visibility-3.svg" alt-text="Streamlining Inventory Visibility in Field Service Solution architecture":::

The image illustrates a technical flowchart outlining the integration between Dynamics 365 Field Service and the finance and operations apps through the Inventory Visibility APIs.

The process begins within the Field Service Copilot Chat, where a user interaction triggers an agent flow. This flow retrieves Work Order Products based on a provided Work Order ID.

Next, an HTTP request is sent to an Azure Function, carrying the relevant Product IDs. The Azure Function then initiates a POST call to the Inventory Visibility public APIs hosted in the environment with Finance or Supply Chain Management environment, submitting the Product IDs for inventory checks. The API response is processed and summarized into a prompt, which is then displayed in the Copilot Chat interface for the manager’s review.

This entire workflow is encapsulated within a dedicated Agent Topic tailored for the Field Service app in the Dynamics 365 Field Service instance.
 
### Configuration steps

This section outlines a possible approach for retrieving information from an external system and presenting it to the user in a readable format within the Copilot chat. 

#### **Step 1: Create a custom Zero Prompt**

The Field Service app has an interactive agent visible and customizable in Copilot Studio called *Copilot in Power Apps - Field Service*.

1.	Open the **Copilot in Power Apps - Field Service** agent. In the **Topic** tab, locate the **Field Service Zero Prompt** topic and create a copy. This enables customization of the topic, as the standard version is not editable. 

    > [!NOTE]
    > The standard Field Service Zero Prompt topic cannot be modified. Using a custom version will exclude it from future updates applied to the standard topic.

1.	Create a new Container inside the Adaptive card as described here: [Zero prompt experience (preview)](/power-apps/maker/model-driven-apps/copilot-chat-zpe-guide)
   
1.	Save and publish the topic.

#### Step 2: Create the WO Product Inventory Check topic

1.	In Copilot Studio, go to **Topics**, select **Add a topic**, and then select **From blank**. Learn more at [Create and edit topics](/microsoft-copilot-studio/authoring-create-edit-topics#create-a-topic) and [Add topics to Copilot chat in model-driven apps](/power-apps/maker/model-driven-apps/copilot-chat-mda-topics).
2.	Rename it **WO Product Inventory Check**, and then define the trigger phrase **Provide WO Products Inventory Info**.

    > [!TIP]
    > Select the More icon (...) to see the code of the agent.

    ```yml
      kind: AdaptiveDialog
      beginDialog:
        kind: OnRecognizedIntent
        id: main
        intent:
          triggerQueries:
            - Provide WO Products Inventory Info
    ```
3.	Add conditions to ensure the topic activates only in the context of a Work Order. Provide a message otherwise.

    ```yml
       actions:
       - kind: ConditionGroup
         id: conditionGroup_bzzEnJ
         conditions:
           - id: conditionItem_IS8gGk
             condition: =Global.PA__Copilot_Model_PageContext.pageContext.entityTypeName = "msdyn_workorder" && Global.PA__Copilot_Model_PageContext.pageContext.pageType = "entityrecord"
         elseActions:
           - kind: SendActivity
             id: sendActivity_zQQXIk
             activity: Product inventory check can only be performed in the context of a Work Order
    ```
4.	Create and agent flow to retrieve associated product IDs.
   
       Add the node **Add a tool - a New Agent flow**.
     	 The flow designer opens.
     	 Create a flow that:
       - accepts a Work Order ID as Input  

           The Work Order ID is available in the topic as a custom variable, `PA__Copilot_Model_PageContext.pageContext.id.guid`.
       - queries Work Order Products
       - returns as Output the list of product IDs

5.	Call the Inventory Availability API 

    Develop an HTTP-triggered Azure Function that serves as a wrapper for the Inventory Service APIs. The function accepts inputs including product IDs, site ID, and location ID. See [Inventory Visibility API query](/dynamics365/supply-chain/inventory/inventory-visibility-api#query-with-post-method)
      
    Implement the Azure Function following these high-level steps:
   
    - Authenticate with Inventory Service. See [Inventory Visibility Authentication](/dynamics365/supply-chain/inventory/inventory-visibility-api#inventory-visibility-authentication) for detailed instructions.
    - Query Inventory Service Post method `/api/environment/{environmentId}/onhand/indexquery` and pass the required parameters as part of Body
    - Parse the response JSON and extract the `availableToReserve` value for each product ID.

    > [!WARNING]
    > Always make sure the API is secured and requires a valid token for invocation from the client application.
  
6. Summarize the response

    Use the the Prompt node in Microsoft Copilot Studio to summarize the response returned by the HTTP call action. Learn more at [Add a prompt to a topic node](/ai-builder/use-a-custom-prompt-in-mcs#add-a-prompt-to-a-topic-node).

    Here's an example of such instructions:
        
    ```
        You are tasked with processing an input inventory response details to extract meaningful insights and generate a summary report.
        The report should highlight key findings, trends, and any actionable recommendations based on the data provided.
        Summarize the following supply chain inventory data by grouping by Org, Site, Loc and listing each product's ID with its Ava.ToReserve and Inv.Supply values.
        Include total AvailableToReserve and InventorySupply per product. Give the  results in a tabular format for better readability, aligning correctly with dotted lines headers and rows columns.
        Use as header Org, Site, Loc, Prod, Name, Avalable, Inv.Supply.
        Provide your data table here: _your data_
    ```

## Solution B – Field Service environment linked to Supply Chain Management environment

By extending Microsoft Copilot within a custom model-driven app, a tailored agent is created that enables the use of Generative AI orchestration. This functionality currently unavailable in the standard Field Service Copilot chat agent.

With generative orchestration, the agent can intelligently select the most appropriate tools, knowledge sources, topics, and even collaborate with other agents to respond to user queries or react to event triggers.

This solution uses the **Microsoft Dynamics 365 ERP MCP** server and the tool [**Find Inventory**](/dynamics365/fin-ops-core/dev-itpro/copilot/copilot-mcp#find-inventory).

:::image type="content" source="media/field-service-streamline-inventory-visibility-2.svg" alt-text="Screenshot that shows Inventory Visibility in Field Service solution B" lightbox="media/field-service-streamline-inventory-visibility-2.svg":::

### Configuration steps

#### Step 0: Enable extensibility of the Copilot chat agent

Each model-driven app includes an interactive agent, the Copilot chat, which can be customized using Microsoft Copilot Studio. Prior to customization, the feature must be enabled for the environment. 

1.	Open the model-driven app in Power Apps, and then on the left navigation bar select the Agents icon, search for **Interactive agent**, select the ellipses icon (…), and then select **Configure -> Configure in Copilot Studio**. Learn more at [Customize Copilot chat in model-driven apps](/power-apps/maker/model-driven-apps/customize-copilot-chat).  

    A new agent named **Copilot in Power Apps – `name`**  is created, where `name`represents the name of the model-driven app.
3.	In **Settings**, enable **Generative AI orchestration** for the agent’s responses instead of using the classic approach.
4.	**Save** and **Publish** the agent and the app.

#### **Step 1: Create a custom Zero Prompt**

1.	In the **Topic tab**, locate the **Platform Zero Prompt** topic and create a duplicate. This provides a customizable version of the zero prompt. 
2.	Add a new **Container** within the **adaptive card**, following the guidance provided in [Zero prompt experience (preview)](/power-apps/maker/model-driven-apps/copilot-chat-zpe-guide)
3.	**Save** and **Publish** the topic.
   
#### Step 2: Create the WO Product Inventory Check topic

1.	Repeat 1 through 4 as outlined in Solution A.
2.	Add a **Question** node that displays the content of the **ProductIds** variable (output from the flow).  

    Prompt: *Would you like to verify the inventory availability?*
    Include two choice options: **Yes** and **No**.
3.	Add a **Condition** node to end the current topic if **No** is selected.
4.	**Save** and **Publish** the topic.

#### Step 3: Add the Dynamics 365 ERP MCP server to the agent

1.	In the agent, on the **Tools** tab, select **Add a tool**.
2.	In the **Add tool** dialog, select the **Model Context Protocol** filter, and search for **Dynamics 365 ERP MCP**.
4.	Select **Add to agent**.
5.	**Publish** the agent.
 
## Related content

- [Customize Copilot Chat in model-driven app](/power-apps/maker/model-driven-apps/customize-copilot-chat)
- [Cross-environment collaboration with Copilot in Dynamics 365](/dynamics365/guidance/resources/ai-powered-cross-environment-collaboration)
- [Use Model Context Protocol for finance and operations apps](/dynamics365/fin-ops-core/dev-itpro/copilot/copilot-mcp)
- [Extend your Copilot Agent in Power Apps with Copilot Studio and new SDK's](https://www.youtube.com/watch?v=iwrMubn2Al8&t=2234s)

## Contributors
This article is maintained by Microsoft. It was originally written by the following contributors:

- Sabrina Di Bartolomeo | FastTrack Solution Architect
- Sourajit Samanta | FastTrack Solution Architect 


