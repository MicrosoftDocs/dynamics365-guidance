---
title: Automate agent tasks with Power Automate
description: Create automated tasks with Power Automate to integrate Customer Service workspace with desktop applications.
author: jowells
ms.author: jowells
ms.topic: concept-article
ms.date: 04/23/2024
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:3/28/2024
  - O25-Service
# CustomerIntent: Create automated tasks with Power Automate to integrate Customer Service workspace with desktop applications
---

<!-- note from editor: I recommend changing "Power Automate Desktop" to "Power Automate" based on this entry in the style guide: https://styleguides.azurewebsites.net/Styleguide/Read?id=2696&topicid=47506. Also, workspace is not capitalized in Customer Service workspace, according to the style guide. -->



# Automate agent tasks with Power Automate

***Applies to: Dynamics 365 Customer Service***

It's common for customer service representatives, or agents, to rely on other applications outside of Customer Service workspace to conduct their day-to-day business. Some of these tasks can be monotonous or repetitive. With the help of Power Automate Desktop, a user can automate these tasks and call them directly within Customer Service workspace.  

## What are desktop flows?

Desktop flows broaden the existing robotic process automation (RPA) capabilities in Power Automate and enable you to automate all repetitive desktop processes. Automating is quicker and easier with the new intuitive Power Automate desktop flow designer. Here, you use the prebuilt drag-and-drop actions or record your own desktop flows to run later.

Desktop flows are for use by anyone who is performing simple or complex rule-based tasks on their workstations. Users at home, small businesses, enterprises, or larger companies can use automation capabilities in Power Automate to create flows, interact with everyday tools like email and Excel, or work with modern and legacy applications. Learn more at [Introduction to desktop flows](/power-automate/desktop-flows/introduction).

## Use desktop flows to automate tasks for customer service representatives

Customer service representatives (CSRs) commonly manage their daily activities with many different applications. Using desktop flows, a CSR can get information from Dynamics 365 Customer Service workspace and automate a task with a legacy system on their workstation. This enables the user to avoid having to do repetitive or low value tasks.

## Sample automated task using Contoso Invoicing

The following sections describe a sample Power Automate desktop flow that takes information from a Dynamics 365 case record and enters it into a .NET application, Contoso Invoicing. The automation is triggered within the Customer Service workspace through a command bar button.

### Prerequisites

Go through the first five, of eight, units of the Power Automate online workshop at [Training | Microsoft Learn](/training/modules/install-required-software-online-workshop/introduction).

### Import and modify the existing solution

This process requires a few steps. First, you must import the solution, get the URL of the desktop flow, and then update the web resource.

1. Download the managed solution from the [GitHub folder](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Customer%20Service/ComponentLibrary/Automation/).  
2. Browse to [https://make.powerapps.com/](https://make.powerapps.com/).  
3. In the navigation panel on the left, choose **Solutions**.  
4. Choose **Import solution**.  
5. Choose **Browse**.  
6. Locate the *RPACaseToInvoicing_1_0_0_XX_managed.zip* file, and choose **Open**.  

    > [!NOTE]
    > XX is a placeholder for the current minor version of the solution.

7. Choose **Next**.
8. Choose **Import**. Wait for the import to complete.  
9. Once complete, on the workstation used to install the prerequisites, open the Power Automate app.  
10. In the Power Automate app, choose **CSW Case to Contoso Invoicing** and then choose the icon with three vertical dots. Choose the **Properties** element.
11. Open the details and copy the value of the **Run URL** field. Save this for later.

### Update the JavaScript file

The JavaScript file used for the command bar button has references to the specific Power Automate desktop used for automation. You must update the JavaScript file to reflect that flow.

1. Download the extn_remoteDesktopCasetoContosoInvoicing.js web resource JavaScript file included in the solution.
2. Locate the following line:

    ```javascript
    var desktopFlowURL = "ms-powerautomate:/console/flow/run?environmentid=REPLACEWITHENVID&workflowid=REPLACEWITHWORKFLOWID&source=Other"
    ```

3. After `var desktopFlowURL =`, remove everything between the quotes and replace it with the value from the **Run URL** field from the earlier instructions. Save the file.
4. In [https://make.powerapps.com/](https://make.powerapps.com/), choose **Solutions**.  
5. Choose **Unmanaged** and find **Default Solution**.
6. On the left pane under **Objects**, expand **Web Resources**, and then choose **Code**.
7. Search for *extn_remoteDesktopCasetoContosoInvoicing.js*, select it, and then choose **Edit**.
8. Select **Choose file** and then specify the *remoteDesktopCasetoContosoInvoicing.js* file that you modified earlier.
9. Save your changes.
10. Choose **Publish**.

### Run the desktop flow

Once the solution has been imported and the necessary customizations changed and published, the Desktop Flow is ready to run.

1. On the workstation used to install the prerequisites, open the Contoso Invoicing application.
2. Open Dynamics 365 Customer Service workspace.
3. Choose **Menu** and then choose **Cases**.
4. Open a case.
5. On the command bar, choose the **Add to Contoso Inv** action.
6. This opens a browser and a prompt:

    :::image type="content" source="media/padAutomation/browserPrompt.png" alt-text="Screenshot of the browser prompt to run the desktop flow." lightbox="media/padAutomation/browserPrompt.png":::

7. Choose **Open**.
8. You'll get the following prompt:

    :::image type="content" source="media/padAutomation/externalSourceInvokeFlowPrompt.png" alt-text="Screenshot of security prompt when the desktop flow is invoked on the workstation." lightbox="media/padAutomation/externalSourceInvokeFlowPrompt.png":::

9. Choose **Continue**.

    > [!NOTE]
    > You can disable this prompt as outlined in the following article. However, this can pose a security threat. Learn more at [Run desktop flows via URL or desktop shortcuts](/power-automate/desktop-flows/run-desktop-flows-url-shortcuts).

10. This will now run the flow by opening the Contoso Invoicing app and entering the details from the case.  

> [!NOTE]
> This sample has some hard-coded data in JavaScript to keep the example simple. The data that is hard-coded is the Address, Phone, and Email.  
