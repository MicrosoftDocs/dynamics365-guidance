---
title: Case study in data management for Dynamics 365 solution
description: Read a case study about a travel company that moved from a system with fragmented customer data to a Dynamics 365 solution with a unified, secure data foundation.
author: vaniaf
ms.author: vaniaf
ms.date: 01/17/2024
ms.topic: conceptual
ms.custom:
  - ai-seo-date: 01/17/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Case study in data management

This case study shows how a global travel company improved its data management as part of migrating to Dynamics 365. Its previous system had customer data scattered across several applications and databases, which made it hard to maintain and use consistently. By moving to Dynamics 365, the company created a secure and responsible data foundation that let it easily request, update, and delete customer data as needed.

## The problem

A global travel company had thousands of staff in the United Kingdom, Dubai, and Australia/New Zealand. They used a legacy homegrown IT system that had grown over the years. The system was difficult to maintain and had many issues. Customer data was split into several disconnected applications and databases. Different departments had sometimes very different views of customers, which caused confusion and poor service for customers. Call centers were always busy, and customer calls were routed from department to department because no one person knew the whole picture.

## The solution

To increase productivity, achieve compliance, and reduce costs, the company started a project to move to Dynamics 365 Finance, Supply Chain Management, and customer engagement apps. The first phase of the project targeted the UK business and involved moving more than 150 business processes to Dynamics 365.

Because the travel company handled personal data, such as passport information and medical certificates, it had to comply with European data protection regulations. The team worked with an experienced system integrator. Together, they took a proactive approach to data governance and data security and mapped out the architectural blueprint of their design. They wanted to control all data outflows and inflows to ensure data consistency, integrity, and security. To get a single source of truth, they defined the apps that held the master data. A company-wide policy let every department know where to find the data and how to request, update, and delete a customer's record. They also built workflows to manage data retention responsibly, such as disposing of information when a customer requested it.

One of the senior managers said that the project helped the company become truly data driven, because it had taken a proactive approach to data governance with a design that put data at the center of every decision.

With the first phase of the UK deployment successful, the company is now working on going live for the Dubai and ANZ businesses.

The system integrator also recommended a way of managing configuration data for deployments. With businesses in three countries/regions, there were many common setups in the three legal entities that could be reused&mdash;but there were also differences that needed to be maintained separately. Instead of managing all this complexity manually, the system integrator had good experience using data templates and packages in Finance and Supply Chain Management. They worked with the company and came up with a configuration plan checklist that identified the specific setup requirements for each of the three businesses. This planning exercise paid off when the company discovered how smooth, quick, and error-free its subsequent deployments became.

As part of the project, the company also moved its historical databases from different applications to Azure Data Lake Storage, and connected with Power BI to provide analytical reporting to the users.

The company now has a unified view of its customers, which helps it provide better customer service and allows marketing efforts to be more targeted.
