---
title: Route or deflect cases using AI Builder
description: Find resources to help you configure your Dynamics 365 Customer Service solution to route or deflect cases using AI Builder.
ms.date: 04/23/2024
ms.topic: conceptual
author: edupont04
ms.author: viange
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:3/12/2024
# CustomerIntent: As an agent, I want to set my presence on every channel type.
---

# Route or deflect cases using AI Builder

***Applies to: Dynamics 365 Customer Service***

Case management is the core of any customer service solution. Dynamics 365 Customer Service offers many features to collect customer support inquiries, track them as cases and allow agents to work on a resolution.  

In particular, when working with Omnichannel for Customer Service, it's common to receive requests from multiple sources. Some of these channels imply a direct interaction with the customer (such as chatbot, direct call) and therefore allow the collection of detailed information through scoping questions. However, other channels are asynchronous in nature, such as emails.  
  
Working with unstructured data, as emails are by nature, may imply extra effort when processing the resulting case, in order to achieve the following objectives:

- Analyze the original message
- Define the nature of the request
- Understand how the case needs to be assigned and resolved

## Email-to-case process with automatic record creation and unified routing

Let's consider a typical scenario such as in the following illustration:

:::image type="content" source="media/AICaseDeflection/processFlow.png" alt-text="Diagram of the Omnichannel for customer service, showing the route that begins from the mailbox." lightbox="media/AICaseDeflection/processFlow.png":::

Many organizations have a support mailbox (such as *support@contoso.com*) which external contacts use to forward their support requests.

When this mailbox is associated to a queue in Customer Service, and the queue is configured to [convert incoming emails to activities](/dynamics365/customer-service/set-up-queues-manage-activities-cases?tabs=customerserviceadmincenter#create-a-queue), every new incoming message is created as an email activity and registered as a queue item.

:::image type="content" source="media/AICaseDeflection/emailsettings.png" alt-text="Screenshot of the Email settings screen showing the Convert Incoming Email to Activities field." lightbox="media/AICaseDeflection/emailsettings.png":::

By applying [rules to automatically create or update records](/dynamics365/customer-service/automatically-create-update-records), these activities can be transformed automatically into new cases.

:::image type="content" source="media/AICaseDeflection/arc1.png" alt-text="Screenshot of the Step 1 details pane, showing the rule name, queue to monitor, and activity type to monitor fields." lightbox="media/AICaseDeflection/arc1.png":::

:::image type="content" source="media/AICaseDeflection/arc2.png" alt-text="Screenshot of the Condition pane, showing the condition name and condition that must pass fields." lightbox="media/AICaseDeflection/arc2.png":::

:::image type="content" source="media/AICaseDeflection/arc3.png" alt-text="Screenshot of the Actions to take field, showing the Record to create and Configure in Microsoft Power Automate fields." lightbox="media/AICaseDeflection/arc3.png":::

Then, by seting up [routing of records](/dynamics365/customer-service/set-up-record-routing?tabs=customerserviceadmincenter), the newly created cases can be delivered to agents for resolution.

Since the case description was populated automatically with the email body, the actual request for the case could be hard to identify. Also, the customer could be sending the request to a wrong mailbox (such as a support request to an "info" mailbox).

For cases originating from emails, the organization may then need to have one or more agents dedicated to manually sorting through those cases, to triage and categorize them, and eventually route the request again to assign it to the proper owner.  

This could imply a significant effort in dedicated resources, and it might be a good idea to apply some automation in this scenario.

## AI capabilities in unified routing

With unified routing, you can apply machine learning model based rules during the [work classification](/dynamics365/customer-service/configure-work-classification) phase:  

:::image type="content" source="media/AICaseDeflection/workclassification.png" alt-text="Screenshot of the Create work classification ruleset screen, with the Machine learning model rule type being highlighted." lightbox="media/AICaseDeflection/workclassification.png":::

While these are some powerful options at our disposal, there are still a few scenarios that might not be covered:

- There's currently not an option to invoke another model, for example a custom model 

- The work classification rules are applied at workstream level, there isn't an option to apply machine learning at an early stage, for example before the routing actually takes place

> [!NOTE]
> Always check product documentation and roadmap to be aware of all latest available features

## Power Automate and AI Builder

When you set up the different types of automatic routing, you'll see the link **Configure in Microsoft Power Automate**. Modern routing actions are implemented as Power Automate flows. The automatically generated flow has some predefined steps, such as recognizing the email sender and create the case record. You can edit the flows to add additional steps, such as the step added in the following illustration:

:::image type="content" source="media/AICaseDeflection/powerautomate1.png" alt-text="Diagram showing the progression of the Power Automate flow." lightbox="media/AICaseDeflection/powerautomate1.png":::

> [!NOTE]
> Some of the predefined steps are restricted for editing. Changing or moving these steps in unsupported ways could prevent the routing to work properly.

An existing capability in Power Automate is  that you can [use AI Builder models](/ai-builder/use-in-flow-overview) in a flow.

AI Builder offers many prebuilt models: sentiment analysis, category classification, language detection, entity extraction, and many more. It's also possible to create and train a custom model.

## Better email-to-case process with AI Builder

By applying the capabilities of Power Automate and AI Builder, it's possible to evolve the initial scenario:

:::image type="content" source="media/AICaseDeflection/processFlowAI.png" alt-text="Diagram of the email-to-case process with A I Builder for the Omnichannel for Customer Service." lightbox="media/AICaseDeflection/processFlowAI.png":::

Adding AI Builder actions to the routing flow, we can analyze the original text of the email, extract relevant information, categorize the case during initial creation, and allow the routing engine to identify the proper destination.

## Adding AI Builder actions in routing flows

To demonstrate this approach, we'll start by preparing a custom GPT prompt in Power Platform's AI Prompt section:

:::image type="content" source="media/AICaseDeflection/AIBuilder_menu1.png" alt-text="Screen of the custom prompt editor in Power Platform." lightbox="media/AICaseDeflection/AIBuilder_menu1.png":::

:::image type="content" source="media/AICaseDeflection/AIBuilder_prompt1.png" alt-text="Screen of the custom prompt editor in Power Platform with detailed prompt." lightbox="media/AICaseDeflection/AIBuilder_prompt1.png":::

The flexibility of the GPT prompt will let us define that we want to process an input text and ask to categorize the text in one of our predefined categories. We can also specify that we want a text field contaning a reason to justify the assigned category. To complete the prompt we ask to extract additional information from the text. We can also indicate that we want the output formatted as JSON and include an example of the desired data structure.

We can test our prompt directly from the editor, by providing a sample input text to observe a preview of the output. This allows for some fine-tuning before saving the finalized prompt.

We're now ready to use the newly created prompt in our existing ARC flows, to implement the following logic:

- Process the text of the incoming email
- Identify the category of the request
- Store the extracted information in the new case

Before proceeding, we need to define some new columns in the case table, to store the values returned by the AI model:

:::image type="content" source="media/AICaseDeflection/D365_columns1.png" alt-text="Screenshot of a list of custom Dataverse columns." lightbox="media/AICaseDeflection/D365_columns1.png":::

It's also a good idea to add these new columns to the case form, so we'll be able to see their values during our test later.

Now that the data model is ready, we can start editing the flow in Power Automate. We want to position our new steps just after the check on the email sender, and right before of the case creation:

:::image type="content" source="media/AICaseDeflection/powerautomate2.png" alt-text="Diagram of the Power Automate flow, with the cursor highlighting the Insert a new step option." lightbox="media/AICaseDeflection/powerautomate2.png":::

When adding the new step, we start by selecting the AI Builder connector to filter available actions, and then select the action "Create text with GPT using a prompt":

:::image type="content" source="media/AICaseDeflection/PowerAutomate_add1.png" alt-text="Screenshot of Power Automate AI Builder connector." lightbox="media/AICaseDeflection/PowerAutomate_add1.png":::

:::image type="content" source="media/AICaseDeflection/PowerAutomate_add2.png" alt-text="Screenshot of Power Automate AI Builder actions." lightbox="media/AICaseDeflection/PowerAutomate_add2.png":::

In the configuration of the new step, we need to select our previously saved custom prompt, and pass the Description value from the incoming email as the input parameter:

:::image type="content" source="media/AICaseDeflection/PowerAutomate_add3.png" alt-text="Screenshot of Power Automate AI Builder step." lightbox="media/AICaseDeflection/PowerAutomate_add3.png":::

Since we instructed the prompt to return a JSON output, we add an additional step to process the JSON which will allow us to work with specific fields. To do so, we leverage the native "Parse JSON" action, and provide a sample of the expected JSON to generate the corresponding schema:

:::image type="content" source="media/AICaseDeflection/PowerAutomate_add4.png" alt-text="Screenshot of Power Automate Parse JSON step." lightbox="media/AICaseDeflection/PowerAutomate_add4.png":::

Finally, we can use the extracted values in the existing step that will create the new case:

:::image type="content" source="media/AICaseDeflection/PowerAutomate_add5.png" alt-text="Screenshot of Power Automate create record step." lightbox="media/AICaseDeflection/PowerAutomate_add5.png":::

With these changes, the ARC flow will perform the expected logic to transform an incoming email into a new case, but at the same time it will enrich the case with the results from the AI action.

## Testing the process

Now that we implemented all the changes, we're ready to perform a test. As a prerequisite, we must correctly configure server-side-sync on a mailbox associated with the queue where the routing rule triggers; otherwise, we won't receive any emails.

Let's compose a new email, simulating the feedback from a dissatisfied customer, and send it to the queue we configured:

:::image type="content" source="media/AICaseDeflection/sendemail.png" alt-text="Screenshot of an email to customer service informing them of a damaged product and requesting a new keyboard or refund." lightbox="media/AICaseDeflection/sendemail.png":::

After a few minutes, we can see that the mail is synchronized in Dynamics 365 and registered as a new activity:

:::image type="content" source="media/AICaseDeflection/emailactivity.png" alt-text="Screenshot of the feedback on product email, showing the sender and recipient of the email." lightbox="media/AICaseDeflection/emailactivity.png":::

Let's check our Power Automate flow and we'll see it was correctly triggered:

:::image type="content" source="media/AICaseDeflection/flowrun.png" alt-text="Screenshot of the 28-day run history pane, showing the Start, Duration, and Status fields." lightbox="media/AICaseDeflection/flowrun.png":::

If we open the details of this execution, we can check the results of the GPT prompt:

:::image type="content" source="media/AICaseDeflection/PowerAutomate_output1.png" alt-text="Screenshot of the Outputs extendable pane, showing code that reveals the status of the GPT prompt." lightbox="media/AICaseDeflection/PowerAutomate_output1.png":::

Finally, going back into Customer Service to see the generated case, we can see the values stored in the record:

:::image type="content" source="media/AICaseDeflection/D365_output1.png" alt-text="Screenshot of the case form in Dynamics 365, showing the AI fields being populated." lightbox="media/AICaseDeflection/D365_output1.png":::

With these values, we can enter the configuration of the workstream, and define new routing rules to divert the case to a specific queue, basing on the predicted category:

:::image type="content" source="media/AICaseDeflection/D365_routing1.png" alt-text="Screenshot of the Conditions pane, showing customizable fields to configure a workstream and define routing rules." lightbox="media/AICaseDeflection/D365_routing1.png":::

Even if you don't feel like implementing complete automation in your routing rules yet, and prefer to let your agents analyze incoming emails, by providing a suggested category and a simple explanation, you can greatly reduce their effort during the triage phase.

## Working with custom categories

In the previous example we provided a static list of categories in the definition of our prompt. But what if we want to define and maintain the categories in a Dataverse table? Let's say for example that we created an Email Category table, to list the caetgory values, and insert a description of the category:

:::image type="content" source="media/AICaseDeflection/EmailCategory_data1.png" alt-text="Screenshot of the Email Category table in Dataverse." lightbox="media/AICaseDeflection/EmailCategory_data1.png":::

The GPT prompt editor allows us to perform grounding on Dataverse data, so we can edit our prompt to add a reference to our Email Category table, specify that the incoming text has to be matched with the category description and that we want the corresponding category name in return:

:::image type="content" source="media/AICaseDeflection/AIBuilder_prompt2.png" alt-text="Screenshot of the GPT prompt editor with Dataverse grounding." lightbox="media/AICaseDeflection/AIBuilder_prompt2.png":::

The results of this prompt will be very similar to what we obtained previously, but this time if we need to update the list of our categories, we can simply change the records in Dataverse and no change is required to the prompt definition.

This approach also allows us to build some kind of fine-tuning and continuous improvement process. In this example, we have users check the results of the automated email categorization, and confirm or change the assigned category. For that purpose, we implement a flow with steps as in the following list:

- Add in the case two columns, one for AI Category and one for Confirmed Category
- Let predefined user roles double-check the category assigned by the AI
- Users can confirm whether the assign category is correct, or select a different one
- Periodically extract all the records where Confirmed Category is differebt from AI Category
- Analyze the list of records to understand what they have in common and why they were assigned a wrong category
- Improve the descriptions of the affected categories to improve the accuracy of the AI model

With a process such as this example, you can incrementally increase the accuracy of your flow, without the need of any change to your implemented solution. You could even try to use a GPT prompt to generate category descriptions starting from past resolved cases.

## Dataverse AI Functions

Another option you can evaluate, is the use of [Dataverse AI Functions](/power-platform/power-fx/reference/function-ai) instead of the GPT prompt:

:::image type="content" source="media/AICaseDeflection/PowerAutomate_aifunction1.png" alt-text="Screenshot of Dataverse AI Functions in Power Automate." lightbox="media/AICaseDeflection/PowerAutomate_aifunction1.png":::

These functions are exposed as any other unbound action. You can easily run them not only from your Power Automate flow, but also in low-code plugins. While offering a bit less flexibility because you can't formulate your own custom prompt, they represent a very simple way to perform some AI actions in your solution.

## Summary

This article takes you through how a low code approach can help you enhance a typical email-to-case process with the addition of AI automation, and enhance and simplify case routing.

AI Builder offers many capabilities, and opens the opportunity to achieve interesting results when used in combination with Customer Service.

We could, for example,  implement a flow recognizing customers requesting instructions to reset their credentials, and generate an automated response with a link to a KB explaining self-service procedures.

Again, we could implement a flow to detect a customer asking for the status of a shipment. The flow could extract the unique number of the shipment, call an external API to check the status, and provide an answer to the customer automatically, resolving the case without human intervention.

With the flexibility of the GPT prompts, and all the tools offered by AI Builder and Azure Open AI, you can build exciting solutions that work seamlessly in your Power Platform environment.
