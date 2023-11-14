---
title: Data management overview
description: Learn how data governance, architecture, modeling, storage, migration, integration, and quality can help you make informed decisions. This article discusses how admins need to think about their data holistically, not just for implementation but as a long-term asset. You can improve your customer engagement, and gather real-time information about your products in the field. We examine the various ways that data management plays a role in the creation of an effective Dynamics 365 solution.
author: vaniaf
ms.author: vaniaf
ms.date: 03/30/2023
ms.topic: conceptual

---

# Data management in Dynamics 365 implementation projects

Data surrounds us every day, like a blanket. Whether you're posting on your social media, scheduling a doctor's appointment, or shopping online, the information collected is one of the most valuable assets of any business. With the right data, organizations can make informed decisions, improve customer engagement, and gather real-time information about products in the field.

This article aims to break down the various functions within data management that collectively ensure information is accessible, accurate, and relevant for the end users. We focus on the most common discussion points surrounding the lifecycle of data within a project.

Take the time to consider what is important to each person interacting with the data. For example, business users focus on their data quality, ability to search, data relevance and performance. In contrast, architects and administrators focus on security, licensing, storage costs, archival, and scalability.

In this article, we discuss the many ways data plays a part in defining a solution. Data plays a vital role in the success of every deployment. You'll learn about different data aspects such as data governance, architecture, modeling, data migration and integration, storage and data quality.

Make sure to always ask these questions:

- How is the data used?

- What use cases require the data?

- Where is the data coming from?

- Where is the data stored?

- Is there a cost (internal/external) to access the data?

- Do users need their data on a mobile phone?

- Do customers need access to their data?

We use the Success by Design framework to highlight critical questions like these that must be asked throughout the project lifecycle to ensure the desired results for everyone.

## Data governance

Let us start the discussion with data governance before we start unpacking different principles of data management.

*Data management* is about operational issues of data. *Data governance* is about taking a high-level strategic view of policies and procedures that define enterprise data availability, usability, quality, and security.

With artificial intelligence (AI) and machine learning (ML) taking center stage in most digital transformation projects, and the fact that the success of these initiatives is highly dependent on data quality, it's prudent that executives start considering data governance seriously.

You may have heard of instances where different departments in the same company don't agree on the definitions of business terms and the values reported. For example, a sales report generated last month may experience two departments reporting different values, maybe because they use two different systems. This scenario happens when there's no internal agreement on common business terms and values. With advanced data governance in place, the walls of data silos effectively crumble. Data is now shared in a trustworthy way with a consistent understanding of business concepts and definitions.

Sharing data within the company is crucial for two economic reasons—growth and distribution. Data is a non-rival resource. It isn't a material resource that if one person uses it, others can't use it. If data is shared with everyone in your company, people can start becoming self-sufficient and build on top of it increasing the overall value as it becomes available to all.

Data governance is a broad subject. here, we want to focus on key aspects that can help drive a successful implementation.

Consider the following key pillars when analyzing data governance within your implementation:

- [Data stewardship](#data-stewardship)  
- [Data quality](#data-quality)  
- [Master data](#master-data)  
- [Proper use cases](#proper-use-cases)  

### Data stewardship

A *data steward* is a role that's responsible for the management and oversight of an organization's data assets. Their goal is to provide that data to end users in a usable, safe, and trusted way. The data steward uses established data governance processes to ensure the fitness of data elements, both the content and metadata. Their specialist role incorporates processes, policies, guidelines, and responsibilities for administering an organization's entire data in compliance with policy and/or regulatory obligations.

### Data quality

The quality of the data can't be considered as a second or third process. Data quality is at the front of data governance policies. It should be thought of as high quality and fit for whatever the intended use is. It's often dedicated teams that drive data accuracy and completeness across the organization, and they may use various tools to scrub the content for its accuracy. Although these tools aid the process more, it's still typically a human responsibility.

The users that are most familiar with their data should typically be the gatekeepers for cleansing, including standardization and adherence to the policies outlined by the data steward.

### Master data

Most enterprises keep a primary set of data used across the organization to supplement systems and reporting. The data elements are typically stored within a master data management (MDM) solution. Examples include customers, accounts, products, and other areas according to business needs. There are often rules of engagement that internal teams must follow when they request access to the master data. Such rules are documented in the data governance plan and managed by the data steward.

### Proper use cases

A data governance plan can't be set up without understanding the proper use cases. Every line of business (LOB) has a level of ownership of their data along with the use cases that drive the solution design. The same holds true for data governance. The use cases aid in naming the primary data elements the organization is taking proactive control of.

For example, one retailer wants to better target its customers through email campaigns, which in the past failed to deliver expected results due to incorrect contact information being captured. While defining this use case, the company also set up the right data governance principles that ensure what data quality is required for email campaigns. They were challenged to define "good" data to satisfy the use case. This simple use case uncovered other issues. The company found that online customers that buy as guests could enter any value in the email field with no validation. This discovery led to data stewards and LOB process owners setting up new validation processes.

Without data governance in place, organizations struggle to control corporate assets needed to ensure data quality. During the requirements gathering stage of your implementation, start paying particular attention to the availability of data required for your solution. Having an early discussion and identification goes a long way in defining your use cases.

For an example of a proper use case, see [A Show-Don't-Tell Approach to Data Governance](https://www.bcg.com/publications/2020/show-tell-approach-data-governance).  

## Next Steps

- Look at [data architecture](data-management-architecture.md) section and review the different types of enterprise data.

- Understand configuration data and how to perform a healthy data migration. Learn more at [configuration and migrated data](data-management-configuration-data-migration.md) section.

- Review Data Management product specific guidelines. Learn more at [guidelines for customer engagement apps](data-management-product-specific-ce.md) and at [guidelines for finance and operations apps](data-management-product-specific-fo.md).

- Access the checklist at [Data Management Success by Design checklist](data-management-check-list.md).
