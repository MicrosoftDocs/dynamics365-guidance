---
title: Telemetry insights data consent
description: Learn about the process of approving data sharing in the Dynamics 365 implementation portal, including overviews of approval statuses for data consent requests.
author: dereklh77
ms.author: v-heuerderek
ms.topic: article
ms.date: 04/04/2024
---

# Data consent for telemetry insights in the Implementation Portal

In this article, we introduce you to the process of approving data sharing in the Dynamics 365 Implementation Portal. Based on Microsoft's [Privacy policy](https://privacy.microsoft.com/privacystatement), we require two contacts from our customer's organization to approve access to their organization's tenant. This way, our partners can access information such as the names of their customers and telemetry insights. This is done while being compliant with data protection regulations and building trust with customers.

Once you've set up a telemetry request in the **Set up telemetry** guide, you'll see all requests on the **Data Consent** page. This newly populated view displays the consent status for the environment from the reviewers.

## Approval status

The following table describes the status options of data sharing request.

| Data Consent Status | What it indicates |
|---------------------|-------------------|
| **Not Applicable** | Data consent policy doesn't apply to this request because the request is created for the same tenant as the user. |
| **Pending** | The request for consent is pending with either one or both reviewers. |
| **Not Allowed** | The request was rejected by the reviewers and canceled. You must submit a new request. |
| **Allowed** | The request has been approved by both reviewers. |

## Admin tasks related to data consent requests

All the following options are available for admins.

### Cancel data consent requests

If an admin wants to cancel the data consent, they can do so from the **Data Consent** view as described in the following steps.

1. Open the **Data consent** area in the **Telemetry insights** section of the Dynamics 365 Implementation Portal.

2. Choose the **Cancel** option. This cancels both the consent requests and makes the reviewer fields to be editable again.

### Edit or change data consent reviewers

You can change the data consent reviewer emails in the **Data consent** view with the following steps.

1. Open the **Data consent** view from the **Telemetry insights** area

2. Choose the **Edit** option on the reviewer names that you want to change, and then specify the new email address.

3. Choose the checkbox to confirm that the user belongs to the target tenant, and then choose the **Update** option.

This sends an email to the newly added user for approval. The admin can update the reviewer emails as required.

### Approving and rejecting data sharing consent

Reviewers receive an email to approve the request once:

- The user provides the target tenant data to consent reviewers

- The admin updates the email IDs of the reviewers in data consent area

Users are provided with a direct link for accessing the data consent page and they can approve or reject the request.

## What features are unavailable if data consent is pending or rejected?

As of March 2024,

- The customer name won't be resolved based on the provided Tenant ID.

- Telemetry insights won't appear since that contains telemetry data from the customer environment.
