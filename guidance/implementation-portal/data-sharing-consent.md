---
title: Data sharing consent
description: Learn about the various approval statuses for data sharing consent and what features become unavailable users do not consent to data sharing.
author: dereklh77
ms.author: goantu
ms.topic: how-to
ms.date: 02/29/2024
---

# Data sharing consent

In this article, we introduce you to the process of approving data sharing in a Dynamics 365 implementation project. Based on Microsoft's [Privacy policy](https://privacy.microsoft.com/privacystatement), we require two contacts from our customer's organization to approve the implementation project's access to their organization's tenant. This allows partners to access information such as customer name and telemetry insights and ensures compliance with data protection regulations, building trust with customers.

After creating a project in the Implementation protal, you will see an Admin tab on the project page. This newly populated tab displays the consent status for the project from the reviewers.

## Approval Status

The following table describes the available states of the target customer consent to data sharing.

| **Data Consent Status** | **What it indicates** |
|-------------------------|-------------------------|
| **Not Applicable** | Data consent policy doesn't apply to this project because the project is created on the same tenant of user. |
| **Pending** | The request for consent is pending with either one or both reviewers. |
| **Not Allowed** | The request was rejected by the reviewers and canceled. You must submit a new request. |
| **Allowed** | The request has been approved by both reviewers. |

## Admin tasks related to data consent requests

All the following options are available only for project admins.

### Cancel data consent requests

Due to any reason, if a project admin wants to cancel the data consent, they can do so from the Admin section &gt; Data Consent tab by following the steps given below.

1. Open the project in the Dynamics 365 Implementation Portal.

2. Choose the **Admin** section, and then choose the **Data Consent** tab.

3. Choose the **Cancel** option. This cancels both the consent requests and clears the reviewer fields to be editable again.

### Edit/Change data consent reviewers

The data consent reviewers can edit the project admin from the Admin page using the following steps.

1. Open the project record in the Dynamics 365 Implementation Portal.

2. Choose the Admin section and navigate to the Data Consent tab.

3. Choose the **Edit** option across the reviewer names to provide the new emails in the Reviewer field.

4. Choose the checkbox to confirm that the user belongs to the target tenant and choose the Update option.

This sends an email to the newly added user for approval. The project admin can update the reviewer emails as required.

### Approving and rejecting data sharing consent

Reviewers receive an email to approve the request once:

- The user provides the target tenant data to consent reviewers
- The project admin updates the email IDs of the reviewers in Admin &gt; Data Consent tab

Users are provided with a direct link for accessing the project admin page and they can select the "Data Consent" tab and approve or reject the request.

## What features are unavailable if data consent is pending or rejected?

As of March 2024,

- The customer name won't be resolved based on the provided Tenant ID.

- Telemetry insights (when it's available as public preview) won't appear since that contains Telemetry data from the customer environment.

## Feedback/Questions?

Email your feedback/queries to [ftd365ip-support@microsoft.com](mailto:ftd365ip-support@microsoft.com).