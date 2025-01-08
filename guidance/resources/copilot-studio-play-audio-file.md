---
title: Play secure audio file from Copilot Studio
description: Learn about the sample solution so that you can play secure audio files from Copilot Studio classic.
author: edupont04
ms.author: viange
ms.topic: conceptual
ms.date: 01/08/2025
ms.custom: O25-Service
---

# Play secure audio file from Copilot Studio

***Applies to: Dynamics 365 Customer Service***

[!INCLUDE[pva-rebrand](../includes/pva-rebrand.md)]

For customer voice solutions, if the organization wants to play their custom audio clips that they play through their Interactive Voice Response (IVR), they must use secure storage.


## [Enhanced voice bot](#tab/enhancedvoicebot)

To add a custom audio clip to your enhanced voice bot, perform the following steps.
 ### Prerequisites

 - Active Azure subscription.
 - An Azure storage account. Learn more in [Create an Azure storage account](/azure/storage/common/storage-account-create).

 ### Upload audio files in Azure Blob Storage

  In the [Azure portal](https://portal.azure.com), perform the following steps:  

   1. Enable static website hosting. Learn more in [Enable static website hosting](/azure/storage/blobs/storage-blob-static-website-how-to?tabs=azure-portal). Make sure that the **Primary endpoint** is set to the URL of your website.
   1. Navigate to **Data Storage** > **Containers**.
   1. Select $web and upload your audio files. 
   1. To secure the storage folder, perform the following steps:
       -  Assign a [Storage Blob Data Reader](/azure/role-based-access-control/built-in-roles/storage#storage-blob-data-reader) role to Copilot Studio app registration or the specific user/group that needs access. Learn more in [Assign a storage blob data role](/azure/storage/blobs/storage-auth-abac-portal#step-3-assign-a-storage-blob-data-role).
       - Navigate to the container where you've uploaded the file, select the required audio file, and then select **Shared access tokens**. Specify the required permissions, start and expiry dates.
        > [!TIP]
        > The audio file won't play post the expiry date. Make sure to specify this date accordingly.
       - Select **Generate SAS token and URL**. Copy the value in BLOB SAS URL.
  
  ### Add the URL to the bot

  Navigate to Copilot Studio and perform the following steps:

   1. Select the voice bot to which you want to add the audio file as a latency message.
   1. Perform the steps in [add a latency message for long running operations](/microsoft-copilot-studio/voice-configuration#add-a-latency-message-for-long-running-operations).
   1. In the message box, specify the SSML tag, `<audio src=""/>` and paste the BLOB SAS URL you have copied from the Azure portal as the value of the src attribute. For example, `<audio src="https://<storageaccount>.blob.core.windows.net/$web/<audiofile>?<SAS token>"/>`. Learn more in [Format speech synthesis with SSML](/microsoft-copilot-studio/voice-configuration#format-speech-synthesis-with-ssml).
   1. Save and publish the bot.
   
## [Classic bot](#tab/classicbot)


 For classic bots, you can add audio files using Azure Blob Storage. By default, Azure Blob storage URLs contain values that are filtered out by security scanning code when passed between systems.

 ### Prerequisites
  - Have a custom Copilot Studio classic Bot, such as [Sample Copilot Studio classic Bot solution](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/ComponentLibrary/PVA/PlayAudioFile/sampleartifacts/PlaySecureAudioFilefromPVA_1_0_0_1.zip)
  - Create Azure Storage Account
  - Have a custom audio clip
  - Find documentation on how to [install Bot Framework Composer](/composer/install-composer?tabs=windows)

 ### Solution

 - Utilize Azure Blob storage to host audio files for playback through SSML
 - Encode the URLs such that they meet content security scan requirements for Microsoft systems.

 ### Steps to Create Storage Account and secure audio file:

 1. Sign in to your Azure account (sign-up [link](https://azure.microsoft.com/free/))

 2. Create an Azure Storage account

 3. When provisioning:
   
    1. uncheck the box for **Allow enabling public access on individual containers** to ensure only URLs with secure access tokens are allowed

     :::image type="content" source="media/PlayAudioFile/copilot-studio-play-audio-file-1.png" alt-text="Screenshot of the Create a storage account screen, with the Advanced tab and Allow enablic public access option being highlighted." lightbox="media/PlayAudioFile/copilot-studio-play-audio-file-1.png":::

   2. Leave the **Enable public access from all networks** selected

   :::image type="content" source="media/PlayAudioFile/copilot-studio-play-audio-file-2.png" alt-text="Screenshot of the Create a storage account screen with the Networking tab and Enable public access option being highlighted." lightbox="media/PlayAudioFile/copilot-studio-play-audio-file-2.png":::

 4. Once created, create a blob storage container under **Containers**

 5. Upload audio files as blobs to the container

 6. Double click on an uploaded audio file row in container view, and navigate to **Generate SAS**

 7. Set an expiration time, and then choose **Generate SAS token and URL**.

 8. Copy the Blob SAS URL

 9. Before pasting into Copilot Studio, one more step is needed which is to encode the URL. Replace all `&` characters with  `&amp;` to make it safe to pass through the Copilot Studio system.

  > [!TIP]
  > The *expiration time* will determine when the system will stop being able to play back this audio file; please be careful when choosing this datetime.

 ### Steps to use audio file from secure storage:

 1. Open your custom Copilot Studio in Bot Framework composer.

 2. Open your Bot in [Copilot Studio](https://copilotstudio.microsoft.com/).

 3. Go to Topics, New topic and finally Open in Bot Framework Composer.

   :::image type="content" source="media/PlayAudioFile/copilot-studio-play-audio-file-3.png" alt-text="Screenshot of the Power Virtual Agents screen with the Topics tab, New topic option, and Open in Bot Framework Composer option being highlighted." lightbox="media/PlayAudioFile/copilot-studio-play-audio-file-3.png":::

 4. Once Bot Framework Composer is open, add a new dialog to your Bot.

   :::image type="content" source="media/PlayAudioFile/copilot-studio-play-audio-file-4.png" alt-text="Screenshot of the Play Audio Secure File screen with the Add a dialog option being highlighted." lightbox="media/PlayAudioFile/copilot-studio-play-audio-file-4.png":::

 5. With the new dialog created, choose **BeginDialog**.

   :::image type="content" source="media/PlayAudioFile/copilot-studio-play-audio-file-5.png" alt-text="Screenshot of the PlayAudioSecureFile screen with the Play Audio and Begin Dialog options being highlighted." lightbox="media/PlayAudioFile/copilot-studio-play-audio-file-5.png":::

 6. In the edit panel, add a new event **Send a response**.

   :::image type="content" source="media/PlayAudioFile/copilot-studio-play-audio-file-6.png" alt-text="Screenshot of the Begin Dialog screen with the Send a response option being highlighted." lightbox="media/PlayAudioFile/copilot-studio-play-audio-file-6.png":::

 7. Add speech component to your bot response. Learn more at [Add speech components to your bot responses](/composer/concept-speech?tabs=v2x#add-speech-components-to-your-bot-responses).

 8. After choosing audio option, copy/past your secure URL generated above to the "URL" tag.

   :::image type="content" source="media/PlayAudioFile/copilot-studio-play-audio-file-7.png" alt-text="Screenshot of a text input field, with the text U R L being highlighted." lightbox="media/PlayAudioFile/copilot-studio-play-audio-file-7.png":::

 9. Finally save and publish your Copilot Studio classic bot.

---