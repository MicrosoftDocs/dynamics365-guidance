---
title: Automate agent tasks with Power Automate Desktop
description: Create automated tasks using Power Automate Desktop to integrate Customer Service Workspace with desktop applications.
author: jowells
ms.author: jowells
ms.topic: conceptual
ms.date: 04/23/2024
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:3/28/2024
  - O25-Service
# CustomerIntent: Create automated tasks using Power Automate Desktop to integrate Customer Service Workspace with desktop applications
---

# Automate agent tasks with Power Automate Desktop

***Applies to: Dynamics 365 Customer Service***

It's common that customer service representatives, or agents, have to rely on other applications outside of Customer Service Workspace to conduct their day to day business. Some of these tasks could be monotonous and/or repetitive. With the help of Power Automate Desktop, a user could automate these tasks and call them straight within Customer Service Workspace.  

## What are Power Automate Desktop flows?

Desktop flows broaden the existing robotic process automation (RPA) capabilities in Power Automate and enable you to automate all repetitive desktop processes. Automating is quicker and easier than ever with the new intuitive Power Automate desktop flow designer. Here, you use the prebuilt drag-and-drop actions or recording your own desktop flows to run later.

Desktop flows are addressed to essentially everyone who is performing simple or complex rule-based tasks on their workstations. Users at home, small businesses, enterprises, or larger companies can use automation capabilities in Power Automate to create flows, interact with everyday tools like email and Excel, or work with modern and legacy applications. Learn more at [Introduction to desktop flows](/power-automate/desktop-flows/introduction).

## Use Power Automate desktop flows to automate tasks for customer service representatives

It isn't uncommon for Customer Service Representatives (CSR) to have to manage their day-to-day activities with multiple different applications. Utilizing desktop flows, a CSR can get information from Dynamics 365 Customer Service workspace and automate a task with a legacy system on their workstation. This enables the user to avoid having to do repetitive or low value tasks.

## Sample automated task using Contoso Invoicing

The following sections describe a sample Power Automate desktop flow that takes information from a Dynamics 365 case record and enters it into a .NET application, Contoso Invoicing. The automation is triggered within the Customer Service workspace through a command bar button.

### Prerequisites

Go through the first five, of eight, units of the Power Automate online workshop at [Training | Microsoft Learn](/training/modules/install-required-software-online-workshop/introduction).

### Import and modify the existing solution

This process requires a couple of steps. First, you must import the solution, get the URL of the desktop flow, and then update the web resource.

1. Download the managed solution from the [GitHub folder](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Customer%20Service/ComponentLibrary/Automation/).  
2. Browse to [https://make.powerapps.com/](https://make.powerapps.com/).  
3. In the navigation panel on the left side, choose **Solutions**.  
4. Choose the **Import solution** action.  
5. Choose the **Browse** action.  
6. Locate the *RPACaseToInvoicing_1_0_0_XX_managed.zip* file, and choose the **Open** action.  

    > [!NOTE]
    > XX is a placeholder for the current minor version of the solution.

7. Choose the **Next** action.
8. Choose the **Import** action
9. Wait for the import to complete.  
10. Once it has, on the workstation used to install the prerequisites, open the Power Automate app.  
11. In the Power Automate app, choose the **CSW Case to Contoso Invoicing** action, and then choose the icon with three vertical dots. Choose the **Properties** element.
12. Open the details and copy the value of the **Run URL** field. Save this for later.

### Update the JavaScript file

The JavaScript file used for the command bar button has references to the specific Power Automate desktop used for automation. You must update the JavaScript file to reflect that flow.

1. Download the extn_remoteDesktopCasetoContosoInvoicing.js web resource Javascript file included in the solution
2. Locate the following line:

    ```javascript
    var desktopFlowURL = "ms-powerautomate:/console/flow/run?environmentid=REPLACEWITHENVID&workflowid=REPLACEWITHWORKFLOWID&source=Other"
    ```

3. After `var desktopFlowURL =`, remove everything between the quotes and replace it with the value from the **Run URL** field from the earlier instructions. Save the file.
4. In [https://make.powerapps.com/](https://make.powerapps.com/), choose the **Solutions** action.  
5. Choose **Unmanaged** and find **Default Solution**.
6. On the left pane under **Objects**, expand **Web Resources**, and then choose **Code**.
7. Search for *extn_remoteDesktopCasetoContosoInvoicing.js*, select it, and then choose the **Edit** action.
8. Choose the **Choose file** action, and then specify the *remoteDesktopCasetoContosoInvoicing.js* file that you modified earlier.
9. Save your changes.
10. Now choose the **Publish** action.

### Run the desktop flow

Once the solution has been imported, the necessary customizations changed, and published, the Desktop Flow is ready for execution.

1. On the workstation used to install the prerequisites, open the Contoso Invoicing application.
2. Open up Dynamics 365 Customer Service workspace.
3. Choose the hamburger button, and choose **Cases**.
4. Open a case.
5. On the command bar, choose the **Add to Contoso Inv** action.
6. This opens a browser and prompt you:

    :::image type="content" source="media/padAutomation/browserPrompt.png" alt-text="Screenshot of the browser prompt to run the Desktop flow." lightbox="media/padAutomation/browserPrompt.png":::

7. Choose Open.
8. You get prompted with the following prompt:

    :::image type="content" source="media/padAutomation/externalSourceInvokeFlowPrompt.png" alt-text="Screenshot of security prompt when the Desktop flow is invoked on the workstation." lightbox="media/padAutomation/externalSourceInvokeFlowPrompt.png":::

9. Choose Continue

    > [!NOTE]
    > You can disable this prompt as outlined in the following article. However, this can pose a security threat. Learn more at [Run desktop flows via URL or desktop shortcuts](/power-automate/desktop-flows/run-desktop-flows-url-shortcuts).

10. This will now run the flow by opening up the Contoso Invoicing app and entering in the details from the case.  

> [!NOTE]
> This sample has some hard coded data in the JavaScript to keep the example simple. The data that is hard coded is the Address, Phone, and Email.  
