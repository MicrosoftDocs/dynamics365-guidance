---
title:  The Fit-to-standard and Fit-gap analysis 
description: Learn how revising current processes can help organizations determine what to change, what to keep, and which new opportunities lie ahead in their Dynamics 365 implementation.  
ms.date: 03/16/2023
ms.topic: conceptual
author: edupont04
ms.author: veneva
ms.reviewer: edupont
---

# The Fit-to-standard and Fit-gap analysis

In many projects, inertia drives the old ways of working. There are several dangers in assuming that what works now also works in Dynamics 365. Recreating processes based on legacy systems can lead to the following issues:

- Unnecessary and excessive customizations and costs related to design, coding, testing, training, documentation, etc.

- Stagnation in the business as the natural opportunity for innovation and improvements is lost

- Creating unique, siloed, inefficient processes when Dynamics 365 could provide more standard and recommended ways of working based on the learnings of thousands of customer organizations

- Damaging the natural usability engineered into Dynamics 365 by forcing processes designed for legacy software into Dynamics

- Creating processes in Dynamics 365 that weren't designed to be used in that way. This approach would reduce the ability to use other related functions because the processes are no longer a natural flow or fit for the purpose

- Reducing the ability to immediately use the documentation, training, sample code, and sample data available for the Dynamics system

- Reducing the ability to apply market and industry knowledge, insights, and experience in Dynamics 365 for the areas of interest for the business

- Reducing the ability to directly apply tools and apps in the marketplace

- Reduced capacity and resources available to apply customizations that can provide significant business value as the available budget and resources get used on customizations that don't add the same value

- Creating barriers for end-user developers (citizen developers) to create rapid, low-cost application using the Power Platform by creating a more complex, customized data model/process model

When it comes to understanding exactly what is going to be implemented in your future solution, do a deep analysis of the current processes and what needs improvement. To determine which areas of your current solution to keep, and which others could be built or purchased from external vendors, we suggest undergoing the analysis in the [Adapting to the standards of the new system](#adapting-to-the-standards-of-the-new-system) section. It helps to have a standard solution, with minimal customizations, minimizing costs and maximizing value to the business.

## Adapting to the standards of the new system

It's recommended to start with a fit-to-standard approach for every project. As part of the definition of the scope, there should be a business process catalog created in the early stages of the project. Then, use it as the set of processes that can be configured and enacted in Dynamics 365. Initially, not all the configuration is completed perfectly. However, starting with the core business processes and iterating until there's a good, high-level understanding of how the processes could be implemented within the system, helps create the solution blueprint. Putting the fit-to-standard approach at the front of the analysis helps to set the right culture of "adopt wherever possible, adapt only where justified."

In most projects, this analysis isn't starting with a blank piece of paper; the implementation partner has conducted some part of this analysis as part of providing estimates on cost and time and a solution overview. It's recommended that the customer project team gets deeply involved in this process to confirm that the key business processes were correctly interpreted and to start gaining knowledge of the standard processes embedded within Dynamics 365.

The continuation of the fit-to-standard leads to the definition of requirements, fits, and gaps, but it's seen from the perspective of using the processes enabled within the system first rather than trying to recreate the legacy system in Dynamics 365.

The advantages of starting with this approach using the process catalog are:

- It promotes the reduction of customizations by supporting the delivery of the underlying business needs through configuration rather than going directly into fit gap analysis with detailed requirements that might derive from the existing or legacy system.

- It helps reduce the risk of missed requirements as the evaluation of the fit with the new system is based on the richer and broader context of business processes. As these business processes are the natural language of business users, their evaluation is more comprehensive, meaningful, and effective compared to working with a list of requirements.

- The process catalog can direct the fit-to-standard assessment by working iteratively through the processes, starting with the higher-level core processes, and then working with the more detailed sub processes and variants. It also helps the business users more clearly see how well their underlying business requirements are being met within the system.

- The project is more likely to adopt modern recommended standard processes embedded in the system.

- It creates higher-quality solutions. Microsoft has signed off on the processes, which  are more likely to be market-tested by others. Custom developments and variants, especially complex ones based on the legacy system, will need to be specifically validated by the customer.

- The standard solution allows for more agility in adopting related technologies and by keeping to standards where possible, makes it easier to add the real value-add custom extensions.

- It enables faster delivery of the new solution; there's no need to wait longer for a custom solution to be developed.

- Standard processes are more easily supported by internal and external support teams, including Microsoft Dynamics Support.

The benefits of staying within the standard product wherever possible are clear. The implementations following this approach, often called vanilla implementations, adopt the Dynamics 365 system with its standard configuration.

:::image type="content" source="media/process-focused-image3.png" alt-text="End-to-end process for purchasing.":::

Some businesses may have specialized business processes or an innovative idea to improve their competitiveness in the market. In such cases, a process-centric description of the system allows these improvements to be adopted with more transparency.

## Gap analysis

As discussed in the previous section, adopting a process-centric solution within Dynamics 365 has clear benefits. However, there may be specialized functions that aren't part of the standard solution. That is identified with the fit gap analysis. After having the configurations set, you can look for gaps in the processes and make a decision whether to customize.

:::image type="content" source="media/process-focused-image4.png" alt-text="Gap in end-to-end process for receiving purchase order.":::

Extending a solution can vary in terms of time, cost, and complexity. There are many things to consider when extending. But it offers the benefit of a solution tailored to business needs. Learn more at [Extend your solution](extend-your-solution.md). Here we look at the implications of taking a process-centric approach.

- Some extensions can bring innovation into business processes. They can add business value and provide good, long-term benefits.

- It's important to consider potential customizations considering the rapid pace of innovation in Dynamics 365 SaaS applications. New features are released regularly and keeping an eye on the Dynamics release plans avoids creating extensions that are quickly redundant.

- When evaluating a potential custom extension, using the process maps can help determine the impact, not just on the process being directly changed but also the impact on connected processes.

- When looking at potential solutions for requirements that can't be met directly in the standard system, consider the different methods available:

  - For simpler designs, consider citizen developer-led applications using the Power Platform, which can generate large value rapidly and at a low cost.

  - For more complex or global solutions, some combination of citizen and professional development through the Power Platform or other technologies may be a more effective and productive route. Using the process catalog can help provide an excellent backdrop to communicate and collaborate between the project team, the citizen developer, and the professional developer.

## Third-party solutions

An alternative to extending is buying an existing solution from a third-party vendor, also known as an independent software vendor (ISV). This option is more common when there's a significant gap and developing a functionality in-house can be complex and costly. Sometimes you don't have enough resources, budget, or expertise to develop and maintain such a significant solution.

ISV solutions tend to focus on more specialized process areas, normally covering some end-to-end industry-specific process. In addition, ISVs provide specific functionality to cover gaps. Successful ISVs have expertise and experience in the vertical industry processes they cover and can therefore add value to your business processes.

:::image type="content" source="media/process-focused-image5.png" alt-text="ISV adds taxes to end-to-end scenario.":::

Dynamics 365 has been designed to meet standard business processes. It enables projects to adopt the standard application more easily and minimize the number of perceived gaps. It also has the flexibility to customize and integrate external applications. Rather than choosing one or the other, buying some third-party solution along with a standard implementation can build an optimal solution.

Representing the fits and gaps in a business process map in terms of the processes drives a better understanding within the implementation team and the organization. You also need this analysis to enlist the requirements for the design of the future solution.

## Next steps

- [Define your requirements](process-focused-solution-define-requirements.md)  
