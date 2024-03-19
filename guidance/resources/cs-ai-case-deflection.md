---
title: Route or deflect cases using AI Builder
description: Find resources to help you configure your Dynamics 365 Customer Service solution to route or deflect cases using AI Builder.
ms.date: 03/14/2024
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

To demonstrate this approach, we'll use two of the prebuilt AI Builder models. Learn more about them in the following articles.

- [Language detection](/ai-builder/flow-language-detection)
- [Category extraction](/ai-builder/prebuilt-category-classification-pwr-automate)

> [!NOTE]
> Prebuilt models are a great way to start with AI Builder. However, to fit your organization's requirements, you may want to consider the creation of a custom model, to define custom categories and train the model with the history of real customer interactions.

Our flow will be integrated with the following logic:

- Detect the language used by the customer in the original email
- Identify the category of the request
- Store the extracted information in the new case

When looking at what these models declare as output, we notice that we'll receive a *string* value for both Language/Classification, along with a Confidence score, which is a *float*. We therefore need to define some new columns in the case table, to store these values after we invoke the AI model:

:::image type="content" source="media/AICaseDeflection/columns.png" alt-text="Screenshot of a list of A I models, showing the display name, name, and data type fields." lightbox="media/AICaseDeflection/columns.png":::

It's also a good idea to add these new columns to the case form, so we'll be able to see their values during our test later.

Now that the data model is ready, we can start editing the flow in Power Automate. We want to position our new steps just after the check on the email sender, and right before of the case creation:

:::image type="content" source="media/AICaseDeflection/powerautomate2.png" alt-text="Diagram of the Power Automate flow, with the cursor highlighting the Insert a new step option." lightbox="media/AICaseDeflection/powerautomate2.png":::

The first step we're adding is the language detection. To do that, we filter the available operations by selecting AI Builder:

:::image type="content" source="media/AICaseDeflection/powerautomate3.png" alt-text="Screenshot of the Choose an operation screen showing various filter operations." lightbox="media/AICaseDeflection/powerautomate3.png":::
Then we search for the desired action:

:::image type="content" source="media/AICaseDeflection/powerautomate4.png" alt-text="Screenshot of the term language being entered in the search field and showing results in the Action tab." lightbox="media/AICaseDeflection/powerautomate4.png":::

The step is added to our flow, and we just need to set the email description as the input parameter:

:::image type="content" source="media/AICaseDeflection/powerautomate5.png" alt-text="Screenshot of the Detect the language being used in text pane, showing the Description entry in the Text field." lightbox="media/AICaseDeflection/powerautomate5.png":::

We'll now define variables to store the outputs of the language detection:

:::image type="content" source="media/AICaseDeflection/powerautomate6.png" alt-text="Diagram showing the flow from between initialize language value variable and initialize language score variable operations." lightbox="media/AICaseDeflection/powerautomate6.png":::

Since the result of the language detection is potentially an array, we process all results with a "for each" step, to find the result with best confidence score:

:::image type="content" source="media/AICaseDeflection/powerautomate7.png" alt-text="Screenshot of the Check all detected languages pane, with the results entry being a selected output." lightbox="media/AICaseDeflection/powerautomate7.png":::

:::image type="content" source="media/AICaseDeflection/powerautomate8.png" alt-text="Screenshot of the Check for better Language Score pane, showing customizable fields to create conditions for the pane." lightbox="media/AICaseDeflection/powerautomate8.png":::

:::image type="content" source="media/AICaseDeflection/powerautomate9.png" alt-text="Screenshot of the If yes pane, showing the underlying Set Language Value and Set Language Score variables." lightbox="media/AICaseDeflection/powerautomate9.png":::

This is a demonstration of how we can process multiple results from any model. You could decide, for example,  to store all results in a related table for further use.

Another approach would be to always get the first element from the results by using the *first(...)* expression, directly in variable initialization or even during case creation. 

> [!NOTE]
> Please always check the definition of the model you choose, to understand how the output is structured and what's the best way to read result values.

Once we have the language detection set, we can repeat the same with the category classification. Note that in this case we also have to provide a language code as input, so we can reuse the output from the previous model:

:::image type="content" source="media/AICaseDeflection/powerautomate10.png" alt-text="Screenshot of the Classify text into categories with the standard model pane, showing the Language and Text fields." lightbox="media/AICaseDeflection/powerautomate10.png":::

We'll read the outputs of the category classification model in the same way we did before for language detection.

After that, we're ready to infer these values during case creation, by editing the "Create a record" step:

:::image type="content" source="media/AICaseDeflection/powerautomate11.png" alt-text="Screenshot of the banner reading Create a record(don't rename this step)." lightbox="media/AICaseDeflection/powerautomate11.png":::

:::image type="content" source="media/AICaseDeflection/powerautomate12.png" alt-text="Screenshot of the A I Category, A I Category Confidence, A I Language, and A I Language Confidence fields." lightbox="media/AICaseDeflection/powerautomate12.png":::

With these changes, the ARC flow always transforms a new email. Our logic will execute and the new case columns will fill with the results from AI Builder models.

## Testing the process

Now that we implemented all the changes, we're ready to perform a test. As a prerequisite, we must correctly configure server-side-sync on a mailbox associated with the queue where the routing rule triggers; otherwise, we won't receive any emails.

Let's compose a new email, simulating the feedback from a dissatisfied customer, and send it to the queue we configured:

:::image type="content" source="media/AICaseDeflection/sendemail.png" alt-text="Screenshot of an email to customer service informing them of a damaged product and requesting a new keyboard or refund." lightbox="media/AICaseDeflection/sendemail.png":::

After a few minutes, we can see that the mail is synchronized in Dynamics 365 and registered as a new activity:

:::image type="content" source="media/AICaseDeflection/emailactivity.png" alt-text="Screenshot of the feedback on product email, showing the sender and recipient of the email." lightbox="media/AICaseDeflection/emailactivity.png":::

Let's check our Power Automate flow and we'll see it was correctly triggered:

:::image type="content" source="media/AICaseDeflection/flowrun.png" alt-text="Screenshot of the 28-day run history pane, showing the Start, Duration, and Status fields." lightbox="media/AICaseDeflection/flowrun.png":::

If we open the details of this execution, we can check the results of the language detection and category extraction models:

:::image type="content" source="media/AICaseDeflection/languageoutput.png" alt-text="Screenshot of the Outputs extendable pane, showing code that reveals the status of the language detection model." lightbox="media/AICaseDeflection/languageoutput.png":::

:::image type="content" source="media/AICaseDeflection/categoryoutput.png" alt-text="Screenshot of the Outputs extendable pane, showing code that reveals the status of the category extraction model." lightbox="media/AICaseDeflection/categoryoutput.png":::

Finally, going back into Customer Service to see the generated case, we can see the values stored in the record:

:::image type="content" source="media/AICaseDeflection/case.png" alt-text="Screenshot of the A I Prediction pane, showing the A I Language, A I Language Confidence, A I Category, and A I Category confidence fields." lightbox="media/AICaseDeflection/case.png":::

With these values, we can enter the configuration of the workstream, and define new routing rules to divert the case to a specific queue, basing on the predicted category:

:::image type="content" source="media/AICaseDeflection/routingrule.png" alt-text="Screenshot of the Conditions pane, showing customizable fields to configure a workstream and define routing rules." lightbox="media/AICaseDeflection/routingrule.png":::

## Summary

This article takes you through how a low code approach can help you enhance a typical email-to-case process with the addition of AI automation, and enhance and simplify case routing.

AI Builder offers many capabilities, and opens the opportunity to achieve interesting results when used in combination with Customer Service.

We could, for example,  implement a flow recognizing customers requesting instructions to reset their credentials, and generate an automated response with a link to a KB explaining self-service procedures.

Again, we could implement a flow to detect a customer asking for the status of a shipment. The flow could extract the unique number of the shipment, call an external API to check the status, and provide an answer to the customer automatically, resolving the case without human intervention.

With the announcement of exciting [new Open AI capabilities in AI Builder](/ai-builder/prebuilt-azure-openai), it is possible to implement many more scenarios.
