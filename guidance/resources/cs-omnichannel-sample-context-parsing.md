---
title: Sample context parsing with JavaScript
description: Learn about the sample implementation to access context variables from JavaScript web resources in a Dynamics 365 Customer Service implementation.
author: edupont04
ms.author: viange
ms.topic: concept-article
ms.date: 03/13/2024
ms.custom: O25-Service
---

# Sample context parsing with JavaScript in a Dynamics 365 Customer Service implementation

***Applies to: Dynamics 365 Customer Service***

Context variables are data that provide information about the conversation before it starts, such as the channel, the customer profile, and the custom settings.

You can use context variables to create routing rules that assign conversations to different queues based on these data. You can also use context variables in tools that help agents work more efficiently, such as macros and scripts.

Additionally, you might want to access context variables from custom JavaScript code in web resources.  

## Sample code

The [Microsoft.Apm.getFocusedSession()](/dynamics365/app-profile-manager/reference/microsoft-apm/getfocusedsession) function is a useful method for accessing the session object of the session that is in focus. It's part of the [app profile manager JavaScript API Reference](/dynamics365/app-profile-manager/reference/microsoft-apm) that includes methods and properties to manage tabs and sessions in the Dynamics 365 Customer Service workspace.

The following sample one retrieves the context variable customerName in the onLoad event:

```javascript
    function parseContextVariables(executionContext) {
      var formContext = executionContext.getFormContext();
      Microsoft.Apm.getFocusedSession().getContext().then((context) => {
              var customerName = context.parameters.customerName;
              alert(customerName);
      }
    );
    }
```

Another useful method is [Microsoft.Omnichannel.getConversationId()](/dynamics365/customer-service/developer/reference/methods/getconversationid). This function can be called to fetch the unique GUID of the current ongoing conversation in a session. It Returns a promise resolved with currently ongoing conversation ID. The identifier can be used to fetch the conversation record programmatically.

```javascript
    Microsoft.Omnichannel.getConversationId();
```

## Related information

- [App profile manager JavaScript API](/dynamics365/app-profile-manager/reference/microsoft-apm)
