---
title: Update External Web App Automatically from Customer Service Workspace
description: Embed an external web app in Customer Service workspace for seamless case updates. Follow these steps to sync Dynamics 365 with your portal.
author: rajislearning
ms.author: rajeeku
ms.topic: how-to
ms.date: 06/24/2025
ms.custom:
  - bap-template
  - O25-Service
  - ai-gen-docs-bap
  - ai-gen-description
  - ai-seo-date:06/24/2025
---

# Update external web apps automatically from Customer Service workspace

This article explains how to set up contextual updates to external systems from Customer Service workspace. It shows you how to embed an external web app in Customer Service workspace, and how to make sure the external web app gets automatic updates from Customer Service workspace.

Here's the scenario: A customer service agent uses Dynamics 365 to manage support tickets, while the company's external portal displays real-time status updates. Any change in a case in Dynamics 365 automatically syncs and shows up in the external portal. The organization used Unified Service Desk but are moving to Customer Service workspace.

To open a third-party application within a Customer Service workspace session template, it needs to initiate an entity session, which loads an entity form. Then, use an onload script to open the external application in the app's side pane.

## Get the prerequisites right

We expect you to host the external application in an IFRAME control.

1. Create a Power Apps Component control that accepts a bound input text parameter, `src`, which specifies the URL of the external application to be displayed in an IFRAME control.

Find a sample IFRAME control as a reference at [Sample-IFrame-control](/power-apps/developer/component-framework/sample-controls/iframe-control).

## Configure contextual updates to the external system

Let's walk you through how to configure the contextual updates to the external system from your Customer Service workspace.

1. Create a custom page using the Power Apps Component control

    1. Insert the code component that you created as a prerequisite.

        :::image type="content" source="media/customer-service-unified-service-desk-migration/external-app-insert-code-component.png" alt-text="Screenshot to show how to insert the code component.":::

    1. Configure the `src` parameter with the URL of your external web application

        :::image type="content" source="media/customer-service-unified-service-desk-migration/external-app-configure-source-parameter.png" alt-text="Screenshot to show how to insert a source parameter.":::

1. Write a JavaScript function to open the custom page when the entity form loads.  

    The following sample script illustrates an approach you can take.

    ```javascript
      //Create an App Side Pane using XRM.App api
      const pane = Xrm.App.sidePanes.getPane("externalPage")
                 ?? await Xrm.App.sidePanes.createPane({
                    title: "External App",// App Side Pane title
                    imageSrc: "WebResources/icon.svg",// Icon of App Side Pane
                    paneId: "externalPage",// App Pane ID
                    canClose: true
                 });
                 await pane.navigate({
                     pageType: "custom",// Open a custom page
                     name: "icici_externalpage_298a3"// Name of the custom page
           });
      pane.state = 1;// Open state of the App Side Pane  
    ```

    Learn more at [Clientapi-Create-App-side-panes](/power-apps/developer/model-driven-apps/clientapi/create-app-side-panes).

    Next, we configure the app so that the external system automatically gets updates from Customer Service.

1. Create a JavaScript function that triggers on field change inside entity form to pass the relevant data or context to the external application.  

    The following sample script illustrates an approach you can take.

     ```javascript
    var formContext = executionContext.getFormContext();
    try {
         var field1Value = formContext.getAttribute("poc_field1").getValue();
         var field2Value = formContext.getAttribute("poc_field2").getValue();    
         setTimeout(() => {
         // App Pane Id
         var paneObj = window.top.document.querySelector('[data-id="pane-container-externalPage"]');
           try {
            if (paneObj) {               
              // Get the IFRAME object and the ContentWindow 
              var paneIframeCW = paneObj.querySelector("iframe").contentWindow;  
              // Send a message to the external application's host origin using postMessage
              paneIframeCW.postMessage(
              { type: "EventFromCSW", payload: { Param1: field1Value, Param2: field2Value } },
             "Target Origin");
             }
           }
           catch (e) {
                throw new Error(e);
            }
        }, 500);
    }
    catch (e) {
        throw new Error(e);
    }
    
    ```

1. Add an Onload event handler inside the external application.  

    The following sample script illustrates an approach you can take.

    ```javascript
       window.addEventListener("message", (event) => {
      // Check the source origin
           if (event.origin !== "https://.crm.dynamics.com") {
                 alert("Event from Non Allowed Origin");
                 return;
           }
          if (event.data.type === "EventFromCSW") {
                 const param1 = event.data?.payload?.Param1;
                 const param2 = event.data?.payload?.Param2;                
                 //// Apply your custom logic based on the received data
           }
     }); 

    ```

1. Test the application  

    Open Customer Service workspace and verify that the context is sent correctly to the external app.

    :::image type="content" source="media/customer-service-unified-service-desk-migration/external-app-contextual-update-test.png" alt-text="Launch the external app in context in Customer Service workspace.":::

## Related content

- [Migrate from Unified Service Desk to Customer Service workspace](cs-usd-migration-guide.md)  
- [FAQ on transition to Customer Service workspace from Unified Service Desk](customer-service-unified-service-desk-migration-tips.md)  
