---
title: Better interpretation of alphanumeric values with generative AI
description: Enhance alphanumeric code recognition in Dynamics 365 Contact Center with AI-powered prompts for better speech interpretation and user confirmation.
author: viange
ms.author: viange
ms.topic: conceptual
ms.collection: null
ms.date: 04/01/2025
ms.custom:
  - bap-template
  - O25-Service
  - ai-gen-docs-bap
  - ai-gen-description
  - ai-seo-date:04/01/2025

#customer intent: As a Dynamics 365 Contact Center admin, I want to improve alphanumeric code recognition using generative AI so that I can enhance speech interpretation accuracy.

---

# Better interpretation of alphanumeric values with generative AI

***Applies to: Dynamics 365 Customer Service***

Dynamics 365 Contact Center includes voice channels for Omnichannel agents that you configure in Copilot Studio. This article introduces a new AI-powered technique to enhance speech interpretation by converting spoken sentences into specific data, such as alphanumeric codes.

Examples of alphanumeric sequences are car plates, Social Security Numbers, and customer codes. Copilot Studio offers predefined entities for such data, such as **Age**, **Dates**, and **Phone numbers**. However, you can extend them by adding lists of elements with synonyms and validation regexes for more complex cases. Learn more at [Use entities and slot filling in agents](/microsoft-copilot-studio/advanced-entities-slot-filling).

> [!NOTE]
> A voice interaction differs from a texted one, especially for alphanumeric data that can be spoken in various ways.

User variability adds further challenges, as unique expressions make exhaustive management difficult. Even with instructions on pronouncing data, only some users follow them precisely.

Overall, speech interpretation is a complex task and in real conversation it relies typically on human knowledge of the context and the language.

This knowledge is now available with the use of generative artificial intelligence (generative AI), and it's just a matter of guiding it with appropriate instructions.

## Alphanumeric code recognition scenario

A more challenging scenario involves asking the customer to spell out information and validating the recognition result. This complexity arises because the pronunciation of individual letters can cause misunderstandings, or the speaker might include casual initial comments, common in spontaneous responses.

For example, the caller might say: *Eh, yes, it's Y H twenty-five J C T*. Often, a human agent easily ignores the prefix and focuses on the spelling of the car plate. However, they might still require clarifications and repetitions since phonemes that are difficult for recognizers to hear are also challenging for humans when spoken back.

Often, rather than spelling out letters, customers are asked to use a word alphabet. Word alphabets are easier to understand, especially over the telephone where phrases like *B as in Bravo T as in Tango* reduce errors compared to shorter utterances such as *B T*.

While the NATO spelling alphabet is typically used in English-speaking countries or regions, other regions have different practices. In France, person names are commonly used, while people in Italy often prefer names of towns.

Using the word-spelling alphabet can address confusing issues, but another aspect is reconstructing the correct Car Plates number from the spoken sequence.

The variability from users in spelling UK license plates during telephone conversations can lead to diverse methods, even varying modes within a single session. The following table outlines some of the more common ways in which users spell out a name or ID:

| Type of verbal spelling              | Example                          |
|--------------------------------------|----------------------------------|
| Single letter                        | A, B                             |
| Standard word alphabet in the country/region | A as in Alpha, B for Bravo    |
| Non-standard alphabet                | Anthony, Amsterdam               |
| Other variants                       | Double A                         |

For example, a user can spell out the UK license plate ***AB22CYT*** in different combinations and preamble:

> *here it's a as in alpha b as bravo twenty two charlie y t for toronto*

Due to recognition errors, the transcript in Copilot Studio might not recognize B as D, resulting in:

> *here it's a as in alpha ***d*** as bravo twenty two charlie y t for toronto*

In this example, the letter *b* is not recognized, and the transcript lists it as the letter *d* instead.

## Address the challenges with generative AI prompts

Generative AI can resolve such a mix of different spelling modalities, ambiguities, and errors producing the correct result. The key is to design an appropriate prompt describing the context and the processing steps to correct and to interpret the user sentence transcription as a car plate. We want a structured response so we can provide instruction to return the alphanumeric code of the car plate in a specific field. Let's name the new field **PlateCode**.

Then, another need is to prepare a confirmation message that the user can easily recognize. As mentioned before, even a single letter like D can likely be acoustically confused as a B, as well by a human. For that reason and for the sake of usability, it's more appropriate to read back the car plate using the same actual words the user said. For the single letters, use an alphabet that's standard in the relevant country or region.

All the listed items can be addressed with more instructions for AI, requesting to return the confirmation message in another field we name **PlatePhrase**. We use this field content as a message to ask the user to confirm the recognized license plate.

## Prompt design and testing

The figure in this section shows the test results for the license plate using a prompt designed to perform instructions in three steps to correct and interpret the license plate and return the required fields. When you add a new prompt node from the **Add an Action** menu in Copilot Studio, the window opens so that you can define the instruction prompt. You can use variables, and you can test the behavior by providing examples of values for the variables.

The following image provides these examples:

- The Left pane (Prompt) with instructions concatenated to user input variable.
- The Middle pane (Prompt response) with AI response, zoomed in at the bottom of the figure.
- The Right pane (Input) to assign a sample value to the user input variable.

:::image type="content" source="media/cs-mcs-alphanum/AI-Prompt.png" alt-text="Screenshot of AI Prompt." lightbox="media/cs-mcs-alphanum/AI-Prompt.png":::

The prompt begins with a brief sentence to provide context for AI. Then, we outline three steps of instructions.

The first step is to correct errors in isolated letters when they conflict with the subsequent word (for example, D as in Bravo), and return an intermediate result in the field **NewSentence**. This field isn't used by the Bot but serves as an intermediate step for proceeding to the next instructions.

The second step involves interpreting the partial result as a car plate and returning the car plate as an alphanumeric code in the field **PlateCode**. English license plates have two possible formats, which complicates interpretation. But for AI, it is enough to show the two formats *LLDDLLL or LDDDLLL*.

The third step entails providing a message to ask the user for confirmation of the recognized license plate, including an example to illustrate the desired format. The message is returned in the field **PlatePhrase**, so that the agent provides a confirmation message, such as *The car plate is {PlatePhrase}. Is it correct?*.

Finally, there are two brief instructions: to return only the requested fields without any other comment, and to return an empty **PlateCode** if the user utterance doesn't indicate a car plate.

In the Input pane, the literal representation of numbers was utilized instead of digits. This approach aids AI in resolving numerical ambiguities more effectively. The speech recognition result is available in MCS in two formats: **MinimallyFormattedText** and **Text**. The former one is more effective because it provides numbers in letters.

The **Prompt response** pane shows the result which is included as an inner **structuredOutput** field in the AI response.

In the **Prompt design** window, you can specify if you want the output in text or JSON format, as the following screenshot illustrates:

:::image type="content" source="media/cs-mcs-alphanum/Prompt-output.png" alt-text="Screenshot of Prompt output." lightbox="media/cs-mcs-alphanum/Prompt-output.png":::

You can also specify the model in the Prompt settings. We're using the default model, GPT-4o mini, as the following screenshot illustrates:

:::image type="content" source="media/cs-mcs-alphanum/Prompt-GPT-Model.png" alt-text="Screenshot of Prompt GPT Model." lightbox="media/cs-mcs-alphanum/Prompt-GPT-Model.png":::

For readers' convenience, this is the complete text of the prompt:

```
You are on the phone with a user saying a car plate.
1. From the user's sentence, construct a 'NewSentence' correcting isolated letters and 'as in' or 'for'. Example: P as Bravo -> Bravo.
2. Interpret the 'NewSentence' into a car number plate in the 'PlateCode' field in the format LLDDLLL or LDDDLLL format.
3. From 'PlateCode' provide a confirmation message 'PlatePhrase' using NATO telephonic alphabet. Example: "E as in Echo, F as in Foxtrot, 3, 3, G as in Golf, S as in Sierra, Q as Quebec"
If user doesn't say a car plate then 'PlateCode' is empty.
Return only the fields one per line.
```

## Copilot Studio Agent implementation

1. The user input is collected by a question node as user's entire response.  
2. If channel is voice, the user input variable value is superseded with **MinimallyFormattedText** that's a property of the `System.Activity.SpeechRecognition` object.  

   :::image type="content" source="media/cs-mcs-alphanum/MCS-question.png" alt-text="Screenshot of Copilot Studio Agent Question Node.":::

3. Next, we add a Prompt added in the canvas selecting an action new Prompt. The following screenshot illustrates the prompt.  

   :::image type="content" source="media/cs-mcs-alphanum/MCS-Prompt.png" alt-text="Screenshot of Copilot Studio Agent Prompt Action Node.":::

   Open and edit the prompt as shown in the image. In the prompt settings, set the output format of the prompt to *Json*, temperature to *0* and model to *GPT-4o*. The output of this action is stored in a ResponseRecord variable which structuredOutput inner Json has these fields:  

   ```json
   {
     ...
     "structuredOutput": {
       "NewSentence": "...",
       "PlateCode": "...",
       "PlatePhrase": "..."
     }
     ...
   }
   ```

4. Next, we parse the `structuredOutput` element into an object of type `record`. Select **From sample data** as the data type, choose **Get schema from sample Json**, and then type the following Json string.  

   ```json
   {
     "NewSentence": """",
     "PlateCode": """",
     "PlatePhrase": """"
   }
   ```

   The following image illustrates what this step looks like in Copilot Studio.  

   :::image type="content" source="media/cs-mcs-alphanum/MCS-Schema.png" alt-text="Screenshot of Copilot Studio Getting schema.":::

The response fields are now present in the record saved in step 4 by Json parse node: `AnswerRecod.PlateCode` and `AnswerRecord.PlatePhrase`.  

The flow at this point can continue with a confirmation request message using the `AnswerRecord.PlatePhrase` (marked as **1** in the following image). If there is a negative answer, the agent asks again (marked as **2** in the following image), and we jump back to the `Prompt` node (marked as **3** in the following image).  

:::image type="content" source="media/cs-mcs-alphanum/MCS-Answer-Confirmation.png" alt-text="Screenshot of Copilot Studio Canvas Answer confirmation.":::  

## Summary and key highlights

This article discusses recent advances in Dynamics 365 Contact Center, particularly in enhancing the Voice channel for Omnichannel agents in Copilot Studio.

The following capabilities for managing customer conversations were adopted:

- It introduces a new technique for recognizing alphanumeric sequences, such as car plates, Social Security Numbers, and customer codes, using AI for better speech interpretation.  
- The document highlights the challenges of user variability in voice interactions and how AI can be guided with appropriate instructions to resolve them.  
- It explains the use a New Prompt node for designing and testing AI prompts in Copilot Studio.  

## Related information

- [Use your prompt actions in Copilot Studio](/ai-builder/use-a-custom-prompt-in-mcs)
- [Use prompts to make your agent perform specific tasks](/microsoft-copilot-studio/nlu-prompt-node)
- [Dynamics 365 Customer Service implementation optimization resources](cs-index.yml)  

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal authors:

- Vince Angeloni | FastTrack Solution Architect
- Paolo Baggia | Project Management Manager
- Flavio Tonelli | Data Scientist
- Sheyla Militello | UX Designer
