---
title: Implement a solution based on business processes
description: Learn why a process-focused approach is crucial for a successful Dynamics 365 implementation and how to use business process mapping to optimize your solution.
author: edupont04
ms.author: raprofit
ms.date: 02/03/2026
ms.update-cycle: 1095-days
ms.topic: concept-article
ms.custom:
  - evergreen
  - ai-seo-date: 01/08/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification:
  - AI-contribution
ai-usage: ai-assisted
---

# Implement a solution based on business processes

To deliver products and services in fast-changing markets and technologies, you need efficient and scalable business processes. A business solution can help you improve your processes by automating, optimizing, and standardizing them. By making business processes drive the implementation project, you can create a more adaptable and effective solution.

This article describes the following main points:

- Why a process-focused approach is essential for implementing a solution with one or more Dynamics 365 apps  
- How to use business process mapping and management to achieve your goals and meet your requirements  
- How to benefit from using business processes as the main framework for your project implementation cycle  
- How to ensure consistency, communication, and performance in your project phases and processes  

## Start with your business processes

Make business processes the core drivers of the implementation project. They reflect the organization's needs and goals, and they guide your improvements. Start by using Microsoft's business process catalog as a starting point to define your business processes. The catalog can help you quickly identify your business processes. The catalog can also help make sure that you speak a common language with Microsoft, your partner, and the users in your organization. Learn more at [Introduction to the business process catalog for Dynamics 365 apps and services](../business-processes/about.md).  

> [!TIP]
> You can use the catalog to manage your implementation project. Learn more at [Use the business process catalog as a template in Azure DevOps Services](../business-processes/about-import-catalog-devops.md).

When you use the business process catalog, start by identifying which processes are relevant for your organization, regardless of whether they're currently in scope for the implementation project. Don't delete processes that aren't in scope for your project, unless the process isn't applicable to the business as a whole.  

For example, if you're a retailer who doesn't manufacture anything, you can delete the *Plan to produce* end-to-end process. However, don't delete the related processes if you're a manufacturer and you don't plan to maintain the fixed asset features for your manufacturing equipment during the project. Instead, you can mark the processes as out of scope, or add a field to indicate the system that is used to manage those processes in your organization. If there's no system for managing a particular process because you manage that process manually, you can mark the process as *manual*, for example.  

If your organization has other processes that aren't included in the catalog, add them. If the process is a standard process used by many organizations, submit the process to Microsoft so that the catalog can be updated in the next release. You can submit new catalog requests in the [Dynamics 365 Patterns and Practices open source GitHub repository](https://aka.ms/businessprocesscatalogrequests) by clicking **New issue** and selecting **Business process catalog change request**.

You can create a profile in the Dynamics 365 Implementation Portal to identify which end-to-end processes and business process areas are planned for the implementation project. Create this profile early in the presales and discovery phase. As the project progresses, you can get more detailed and define the scope for the concrete business processes (level three in the business process catalog) and the concrete scenarios (level four in the catalog). Learn more at [Project profiling](../implementation-portal/project-profiling.md).

## Use the business language

Every organization has its own language to describe its daily operations. This language is based on business processes and industry terminology. During an implementation project, this language is the best and most familiar way for the organization to communicate their needs, tools, and technologies. The language isn't just words; it includes the processes you use to conduct your transactions and activities. Using and refining these processes in your language is important to keep your business requirements clear and accurate. It also helps you avoid confusion and misunderstanding with the technical tasks and terms involved in the implementation.

This language is often called *a taxonomy*. A process taxonomy organizes your processes in a hierarchy, from the broad top-level ones to the detailed lower-level ones. When your project starts, it quickly pays off to put your business process view at the center. When you discuss your project and business processes with external parties, this approach helps them learn your language and understand your organization.

When you use the business process catalog, you can update the language of the catalog for your business, organization, and industry. When we created the business process catalog, we designed the names to be as generic as possible so that it can apply to as many industries and organizations as possible. For example, if your organization is in the healthcare industry, you might want to rename business processes that refer to *customers* as *patients*.  

## Start with a vision for your future business processes

To focus on the activities you need to reach your goal, you must have a vision for how the technology transforms your business. You must also understand how your business works today and how you want it to work in the future.

Successful implementations start with a clear understanding of your *business model*. The business model is also called a *target operating model* (TOM). It includes how you create value through your products and services, and how you relate to your customers and suppliers. Multiple business processes support and align with your business model. Learn more about how to define your business model and connect it to your business processes at [Drive app value](drive-app-value.md). Your business processes provide the foundation for your solution roadmap and digital transformation.

Your processes also define the functional scope of your solution. You must define your business processes before you can work on your requirements and other aspects of your solution.

When you define your business model, evaluate the state of your processes. You might want to use new technology to optimize your existing processes through automation. Or maybe you need new processes to move to e-commerce or outsource some operations. Or perhaps you want to adopt lean manufacturing.

A common mistake is to think that the new system you implement defines your processes. It's the other way around: Technology is an enabler. It might change the user experience and drive certain behaviors. But the system should serve and fit your operations, and your stakeholders define your business model.  

The business process catalog provides a structured and standardized flow for many business processes that serves as a starting point and a useful guideline. In some cases, your business might choose to adopt the standard processes or execution methods directly from the catalog. However, there might also be gaps that require adjustments or tweaks to better fit your unique operational needs. It's essential to keep in mind that changing your processes might necessitate change management to ensure smooth transitions and user adoption. Learn more about how to implement change management in your project at [Change management](change-management.md). Also, if you modify the software to bridge gaps, you might have to invest in software development to customize the system accordingly. Learn more about performing gap analysis at [Optimize your implementation with a fit-to-standard and fit-gap analysis](process-focused-solution-fit-to-standard-fit-gap-analysis.md).

You might also want to consolidate and standardize your processes across different parts of your business. Knowing the state of your processes helps you plan how to achieve your goals. The effort to implement an existing process with new technology is different from the effort to define or agree on new processes.

Your business processes might not be the same across your organization. For example, one division ships inventory directly to customers, while others use a warehouse. Or perhaps you have a shared product catalog and ordering process for employee purchasing. In any case, your business model analysis, process re-engineering, and standardization strategies should be part of your project definition. This definition links your processes to your business strategy and helps you set process-based project goals.

## Next steps

- Find [opportunities for optimization in your business processes](process-focused-solution-opportunity-optimization.md).
- Understand the phases of the [process-focused implementation lifecycle](process-focused-solution-implementation-lifecycle.md).
- Review the [considerations for building business processes](process-focused-solution-considerations-building-business-processes.md).
- Learn how to perform a [fit-to-standard and a fit-gap analysis](process-focused-solution-fit-to-standard-fit-gap-analysis.md).
- [Define your requirements](process-focused-solution-define-requirements.md).
- Prepare for your implementation by following the steps in the [checklist](process-focused-solution-checklist.md).  
- Read a [case study](process-focused-solution-case-study-journey.md) about a company that implemented Dynamics 365 using a process-focused approach.
