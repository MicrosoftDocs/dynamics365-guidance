---
title: Manage your data in Dynamics 365 implementation projects
description: Learn how data governance, architecture, modeling, storage, migration, integration, and quality can help you make informed decisions.
author: vaniaf
ms.author: veneva
ms.date: 01/08/2024
ms.topic: conceptual
ms.custom:
- ai-seo-date: 01/08/2024
- ai-gen-docs-bap
- ai-gen-title
- ai-gen-desc
content_well_notification:
- AI-contribution
ai-usage: ai-assisted
---

# Manage your data in Dynamics 365 implementation projects

Data is everywhere, and it is one of the most valuable assets of any business. With the right data, you can make informed decisions, improve customer engagement, and gather real-time information about your products in the field.

This article aims to help you understand the various aspects of data management that ensure your data is accessible, accurate, and relevant for users. We focus on the most common topics related to the lifecycle of data within a project.

Think about what's important to each person interacting with the data. For example, business users care about data quality, searchability, relevance, and performance. Architects and administrators care about security, licensing, storage costs, archival, and scalability.

In this article, we discuss the many ways data plays a part in defining a solution. Data is vital for the success of every deployment. You'll learn about data governance, architecture, modeling, migration and integration, storage, and quality.

Ask yourself these questions:

- How is the data used?
- What use cases require the data?
- Where is the data coming from?
- Where is the data stored?
- Is there a cost (internal or external) to access the data?
- Do users need their data on a mobile device?
- Do customers need access to their data?

We use the Success by Design framework to highlight critical questions like these that you must ask throughout the project lifecycle to ensure the desired results for everyone.

## Data governance

Before we dive into the principles of data management, let's start with data governance.

*Data management* is about the operational issues of data. *Data governance* is about taking a high-level strategic view of the policies and procedures that define the availability, usability, quality, and security of your data.

With artificial intelligence (AI) and machine learning (ML) becoming more prominent in most digital transformation projects, and the fact that their success depends on data quality, it's wise to take data governance seriously.

You may have encountered situations where different departments in the same company don't agree on the definitions of business terms and the values reported. For example, a sales report generated last month may show different values for two departments, maybe because they use two different systems. This happens when there's no internal agreement on common business terms and values. With effective data governance in place, the barriers of data silos are removed. Data is shared in a trustworthy way with a consistent understanding of business concepts and definitions.

Sharing data within the company is important for two economic reasons: growth and distribution. Data is a non-rival resource. That means that if one person uses it, others can still use it. If data is shared with everyone in your company, people can become more self-reliant and build on it, increasing the overall value as it becomes available to all.

Data governance is a broad subject. Here, we want to focus on key aspects that can help drive a successful implementation.

Consider the following key pillars when analyzing data governance in your implementation:

- [Data stewardship](#data-stewardship)
- [Data quality](#data-quality)
- [Primary data](#primary-data)
- [Proper use cases](#proper-use-cases)

### Data stewardship

A *data steward* is a role that's responsible for the management and oversight of your data assets. Their goal is to provide data to users in a usable, safe, and trusted way. The data steward uses established data governance processes to ensure the fitness of data elements, both the content and metadata. Their specialist role incorporates processes, policies, guidelines, and responsibilities for administering your data in compliance with policy and regulatory obligations.

### Data quality

Data quality is at the forefront of data governance policies. It should be thought of as high quality and fit for the intended use. It's often dedicated teams that drive data accuracy and completeness across the organization. They may use various tools to scrub the content for accuracy. Although these tools help the process, it's still typically a human responsibility.

The users who are most familiar with their data should be the gatekeepers for cleansing, including standardization and adherence to the policies outlined by the data steward.

### Primary data

Most enterprises keep a primary set of data used across the organization to supplement systems and reporting. The data elements are typically stored within a master data management (MDM) solution. Examples include customers, accounts, products, and other areas according to business needs. Internal teams must often follow rules of engagement when they request access to the primary data. Such rules are documented in the data governance plan and managed by the data steward.

### Proper use cases

A data governance plan can't be set up without understanding the proper use cases. Every line of business (LOB) has a level of ownership of their data along with the use cases that drive the solution design. The same holds true for data governance. The use cases help you name the primary data elements that you are taking proactive control of.

For example, one retailer wants to better target its customers through email campaigns. In the past, these campaigns failed to deliver expected results because inaccurate contact information was captured. While defining this use case, the company also set up the right data governance principles that ensure what data quality is required for email campaigns. They were challenged to define "good" data to satisfy the use case. This simple use case uncovered other issues. The company found that online customers who buy as guests could enter any value in the email field with no validation. This discovery led data stewards and LOB process owners to set up new validation processes.

Without data governance in place, organizations struggle to control corporate assets needed to ensure data quality. During the requirements gathering stage of your implementation, start paying close attention to the availability of data required for your solution. Having an early discussion and identification goes a long way in defining your use cases.

For an example of a proper use case, see [A Show-Don't-Tell Approach to Data Governance](https://www.bcg.com/publications/2020/show-tell-approach-data-governance).

## Next steps

- [Review data architecture](data-management-architecture.md) and the different types of enterprise data
- [Understand configuration data and how to perform a healthy data migration](data-management-configuration-data-migration.md)
- Review product-specific guidelines for data management: [guidelines for customer engagement apps](data-management-product-specific-ce.md) and [guidelines for finance and operations apps](data-management-product-specific-fo.md)
- [Review the Data Management Success by Design checklist](data-management-check-list.md)
- [Read a case study in data management](data-management-case-study.md)
