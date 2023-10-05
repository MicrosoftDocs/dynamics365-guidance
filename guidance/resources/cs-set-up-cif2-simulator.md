---
title: Simulator for Channel Integration Framework v. 2.0
description: Learn how to simulate a digital contact center with Customer Service and Channel Integration Framework with voice channel. Get the sample solution here.
author: edupont04
ms.author: edupont
ms.topic: how-to #Required; don't change.
ms.collection: 
ms.date: 06/13/2023
ms.custom: bap-template #Required; don't change.
---

# Simulator for Channel Integration Framework v. 2.0 and Dynamics 365 Customer Service

***Applies to: Dynamics 365 Customer Service***

This article outlines the required steps to configure and simulate a digital contact center with the Customer Service workspace and Channel Integration Framework v2.0 with voice channel. The sample simulator is a resource to help optimize the Dynamics 365 implementation and Channel Integration Framework version 2.0 experiences. Use the Channel Integration Framework simulator solution to test and learn the work processes before you go live in production.

> [!NOTE]
> The simulator is just a collection of samples that we built using the Channel Integration Framework. There is no direct integration with a third-party phone provider in this sample solution.

## Prerequisites

- [System requirements](/dynamics365/customer-service/channel-integration-framework/v2/system-requirements-channel-integration-framework-v2)  
- [Get the samples and tools](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/Channel%20Integration%20Framework%20v2.0/CIF%202.0%20Simulator/)

## Configuration steps

1. Download the package at [Channel Integration Framework Simulator](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/Channel%20Integration%20Framework%20v2.0/CIF%202.0%20Simulator/Solutions)  

    Extract the files, and then open the *Solution Channel Integration Framework simulator Solution* in Power Apps. Learn more about how to import solutions at [Import solutions](/power-apps/maker/data-platform/import-update-export-solutions).  

2. Choose a default account and contact

    The simulator has the following defaults:

    |Type | Name | ID |
    |--|--|--|
    |Account | A Datum Corporation | a16b3f4b-1be7-e611-8101-e0071b6af231 |
    |Contact | Abraham McCormick | 25a17064-1ae7-e611-80f4-e0071b661f01 |

    If you want or have to choose another default account for your environment, select it, choose **Email a link**, and then choose the relevant name and ID. Use the same steps to choose a default contact. Then, change the HTML page to reflect the chosen default account and contact. Learn more at [View, compose and respond to email](/power-apps/user/view-compose-email?context=%2Fdynamics365%2Fcontext%2Fcustomer-service-context) in the Customer Service docs.  
3. Open the imported solution, and then, from the list of objects, choose the object of type *HTML Web Resource*  

    Learn more at [Import solutions](/power-apps/maker/data-platform/import-update-export-solutions)  
4. Edit the code changing the `onChangeCustomerEntityName()` function with the relevant values for **Customer Name** and **Customer Record Id (GUID)**.
    <!--![](images/5.png)
    Edit the default value for the Customer Name textbox, with the chosen Account name:
    images/6.png)
    Edit the default value for the Customer Record Id (GUID) textbox, with the chosen Account id:
    images/7.png)-->

Next, we configure templates for the different work spaces.

### Add notification templates

1. In the **Customer Service admin center**, in the **Agent** experience, open the list of workspaces, and then choose the **Manage** action for the **Notification templates** workspace.  

    Learn more at [Manage notification settings and templates](/dynamics365/app-profile-manager/notification-templates?tabs=customerserviceadmincenter).  

2. Verify that a notification template with the name **DCCP Voice Notification Template** already exists. Otherwise, create a new one with the following values:

    | Field | Value |
    |--|--|
    | Name | DCCP Voice Notification |
    | Unique Name | extn_voice_notification |
    | Title | {customerName} |
    | Icon | /webresources/msdyn_chat_icon |

3. Also add a notification field for the sample phone number with the value `extn_phonenumber`  

### Add application tab templates

1. Go back to the list of workspaces, and then choose the **Manage** action for the **Application tabs templates** workspace.  

    Learn more at [Manage application tab templates](/dynamics365/app-profile-manager/application-tab-templates?tabs=customerserviceadmincenter).  

2. If they don't already exist, add three templates.

    a. Add a template for search based on the following table.

      | Field | Value |
      |--|--|
      | Name | DCCP Global Search |
      | Unique Name | extn_global_search |
      | Page Type | Search |

    b. Add a template for cases based on the following table.

      | Field | Value |
      |--|--|
      | Name | DCCP Case Form|
      | Unique Name | extn_case_tab |
      | Page Type | Entity Record|
      | Parameter field **data** |`{"customerid":"{customerRecordId}", "customeridtype":"{customerEntityName}", "customeridname":"{customerName}", "caseorigincode":"{extn_media_type}", "description":"Phone: {extn_phonenumber} / Email: {extn_email_address} / InteractionId: {extn_interactionid}", "title":"{extn_subject}"}` |
      | Parameter field **entityName** |incident  |

    c. Add a template for customers based on the following table.

      | Field | Value |
      |--|--|
      | Name | DCCP Customer Form|
      | Unique Name | extn_customer_tab|
      | Page Type | Entity Record|
      | Parameter field **entityID** |{customerRecordId}|
      | Parameter field **entityName** |{customerEntityName}  |

### Add session templates

1. Go back to the list of workspaces, and then choose the **Manage** action for the **Session templates** workspace.  

    Learn more at [Manage session tab templates](/dynamics365/app-profile-manager/session-templates).  

2. If they don't already exist, add two templates.

    a. Add a template for default sessions based on the following table.

      | Field | Value |
      |--|--|
      | Name | DCCP Default Session|
      | Unique Name | extn_default_session|
      | Page Type |Generic|
      | Title |Channel Integration Framework 2.0 Simulator Home|
      | Communication panel mode|Docked|
      | Anchor Tab |Global Search|

    b. Add a template for identified sessions based on the following table.

      | Field | Value |
      |--|--|
      | Name | DDCCP Voice Identified Session|
      | Unique Name | extn_voice_identified_session|
      | Page Type |Generic|
      | Title |Voice-{customerName}|
      | Communication panel mode|Docked|
      | Anchor Tab |DCCP Case Form|

      Also add an extra tab based on the `customerName` data entity.

### Add voice channel providers

1. Go back to the list of workspaces, and then choose the **Manage** action for the **Third party voice channel provider** workspace.  

    Learn more at [Manage session tab templates](/dynamics365/app-profile-manager/session-templates).  

2. Add a template for channel providers based on the following table.

      | Field | Value |
      |--|--|
      | Name | CIF2_Simulator|
      | Unique Name | extn_cif2simulator|
      | Label|CIF2 Simulator|
      | Channel URL |`https://EnvironmentURL/WebResources/extn_/sample/vnb_cif_support_html`|
      | Enable Out Bound|Yes|
      | Channel Order|1|
      | API Version |2|
      | Enable Analytics|Yes|

### Add agent experience profiles

1. Go back to the list of workspaces, and then choose the **Manage** action for the **Agent experience profiles** workspace.  

    Learn more at [Agent experience profiles](/dynamics365/app-profile-manager/overview).  

2. Add a template for agent experiences based on the following table.

      | Field | Value |
      |--|--|
      | Name | CIF2_Simulator|
      | Unique Name | extn_cif2simulator|
      | Label|CIF2 Simulator|
3. In the **Channel providers** section, choose the **Edit** action, and then add the *CIF2_Simulator* channel provider that you set up in the [Add voice channel providers](#add-voice-channel-providers) section.

      Next, you assign users

4. Choose the **Edit** action to assign users

5. Add the users that work with the simulator to the list. Learn more at [Add users to agent experience profiles](/dynamics365/app-profile-manager/add-profile-default)  

## Run the simulator for inbound interactions

Run the simulator in the Customer Service workspace. You can configure the following parameters to simulate an inbound interaction:

- Media Type  

  The channel of the interaction. It uses the `{extn_media_type}` [custom slug](/dynamics365/customer-service/channel-integration-framework/v2/automation-dictionary-keys-cif#slugs)  
- Notify Template  

  Read-only. It changes according to the Media Type.  
- Session Template  

  Read-only. It changes according to the Media Type.
- Telephone  

  The calling number. It uses the `{extn_phonenumber}` custom slug
- E-mail Address  

  The e-mail address for email and chat channels. It uses the `{extn_email_address}` custom slug
- Subject  

  A simple text that uses the `{extn_subject}` custom slug.
- Interaction/Call Id (extn_interactionid)  

  The unique identifier of the interaction/call ID in the third party channel provider. In the simulator, it's a random GUID that uses the `{extn_interactionid}` custom slug.  
- Customer Data  

  You can change the default values for these fields, but choose an existing account or contact.  

- Customer Name  

  The name of the account (name) or contact (fullname). It uses the `{customerName}` slug.

- Customer Entity Name  

  The account or contact. It uses the `{customerEntityName}` slug.

- Customer Record Id (GUID)  

  The account ID or contact ID of the customer. It uses the `{customerRecordId}` slug

<!--![](images/30.png)-->

### Notification

When you have specified the media type and filled in the parameters form, choose the **Notify** action. A pop-up dialog gives you two choices:

1. Accept  

    Choosing to accept the notification creates a session and fills in a new case with data from the parameters and custom slugs.

2. Reject  

    Choosing to reject the notification creates a task and notifies you about it. You get the same message if you let the notification time out.  

### Multi-session experience

You can create multiple sessions by customer and channel. For example, create an outbound (click-to-call / click-to-act) interaction by choosing the customer under a session, and then choosing the **Phone** icon. It triggers the [Channel Integration Framework 2.0 onclicktoact event](/dynamics365/customer-service/channel-integration-framework/v2/enable-outbound-communication-clicktoact).  

### Miscellaneous Channel Integration Framework API Calls

The simulator has the following buttons to call the [Channel Integration Framework 2.0 API](/dynamics365/customer-service/channel-integration-framework/v2/reference/microsoft-ciframework-v2):  

- **Get all sessions** calls Microsoft.CIFramework.getAllSessions

- **Get current session** calls Microsoft.CIFramework.getFocusedSession

- **Change current session's title** calls Microsoft.CIFramework.setSessionTitle

- **Notify new activity in other sessions** calls Microsoft.CIFramework.notifyNewActivity

- **Notify urgency in sessions** calls Microsoft.CIFramework.notifyKpiBreach

- **Request focus on another session** calls Microsoft.CIFramework.requestFocusSession

- **Set presence status as Away** calls Microsoft.CIFramework.setPresence

- **Create case** calls Microsoft.CIFramework.createRecord

- **Close current Tab** calls Microsoft.CIFramework.closeTab

## Extend the simulator

The code for the simulator app is under the `extn_/sample/vnb_cif_support_html` web resource. It's an HTML file containing the page definition and the JavaScript.

For example, if you want to add new slugs or attributes, take the following steps:

- Include them in the form, such as after the `Interaction/Call Id` field  
- Include them in the notification by adding them to the `onChangeNotifyContext` function  
- Include them in the Session Context by adding them to the `onChangeSessionContext` function  

If you want to perform some actions in Dynamics 365 after creating a session, add them to the `_createSession` function.

### Add the {comment} slug to the form

In this example, we add the {comment} field below the **Subject** field inside the HTML `<body>` element.  

```html
    <div class="parameter">
        <div>Comment (extn_comment)</div>
        <input type="text" id="extn_comment" value="This is a comment" onChange="extnSample.CommonFunctions.onChangeNotifyContext();"/>
    </div>
```

### Add the {comment} slug to the notification input object

The changes should be made to the `onChangeNotifyContext` function.  

```javascript

      onChangeNotifyContextCustomPage: function ();
          var extnbr_notify_template = document.getElementById("extnbr_notifytemplate").value;
          var extnbr_session_template = document.getElementById("extnbr_session_template_custompage").value;
          var extnbr_customerName = document.getElementById("customerName").value;
          var extnbr_mediatype = document.getElementById("extnbr_mediatype").value;
          var extnbr_telephone = document.getElementById("extnbr_telephone").value;
          var extnbr_email_address = document.getElementById("extnbr_email_address").value;
          var extnbr_subject = document.getElementById("extnbr_subject").value;
          var extnbr_comment = document.getElementById("extnbr_comment").value;
```

### Add the {comment} slug to the session creation input object

The changes should be made to `onChangeSessionContext` function: <!--![](images/44.png)-->

### Add the {comment} slug to the notification template

Add the Comment notification field for {comment} slug as follows:

1. Open the voice notification in the Customer Service admin center  
2. In the **Notification Fields** section, add new notification field based on the following table.

  | Field | Value |
  |--|--|
  | Name | DCCP sample message |
  | Title| Comment |
  | Value | {extn_comment} |

### Use the {comment} slug in the Case form

1. Create a new JavaScript Web Resource with the following function, and include it in the Case form `Onload` event:

```javascript
function extn_CaseForm (executionObj) {

  var formContext = null;

  if (executionObj !== null && executionObj.getFormContext !== null)

    formContext = executionObj.getFormContext();

  else

    formContext = executionObj;

    Microsoft.Apm.getFocusedSession().getContext().then(

    function (session_context) {

      if (session_context.parameters["comment"] != null && session_context.parameters["comment"] != undefined && session_context.parameters["comment"] != "") {

       alert("Comment for the user: " + session_context.parameters["comment"]);
      }

   }

   );

}
```

## Learn more

- [Channel Integration Framework 2.0](/dynamics365/customer-service/channel-integration-framework/v2/overview-channel-integration-framework)  
- [Sample library for Digital Contact Center Platform](/digital-contact-center-platform/guidance/component-library)  
