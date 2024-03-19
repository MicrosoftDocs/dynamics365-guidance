---
title: Set up agent capacity for custom entities
description: Learn how to configure capacity-based routing for custom entities in Customer Service using no-code and low-code approaches.
titleSuffix: DCCP
ms.date: 03/14/2024
ms.topic: conceptual
author: edupont04
ms.author: thomasjosep
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:11/28/2023
# CustomerIntent: As an administrtor, I want to use capacity-based routing for agents in Customer Service.
---

# Set up agent capacity for custom entities

***Applies to: Dynamics 365 Customer Service***

This article provides two approaches to perform route and release capacity on record routing with Dynamics 365 Customer Service.

In Dynamics 365 Customer Service, you must make some configuration changes to use *capacity-based routing* for any entity other than the case (incident) entity. We outline two options: a no-code option and a low-code option.  

Find more resources for your implementation at [Dynamics 365 Guidance](index.yml). Microsoft provides a sample library to aid you in your implementation and setup at [Dynamics 365 Customer Service implementation optimization resources](cs-index.yml). There's a wealth of details available born out of real customer deployments designed to significantly reduce your time to value.

## Agent capacity recap

Let's review the unified routing and how capacity is set up and released for the native **Case** entity. We're in the Customer Service admin center where capacity is managed at the user level and at the workstream level. The **Workstream for Cases** is set up with **Unit based** capacity. The cost of each incoming case is set at a numerical value. The following illustration shows a configuration of a workstream for record routing for the **Case** table. In this example, we set the capacity to unit-based and the value of each case to *25* as indicated with the number 1 in the following illustration. In the illustration, the number 2 calls out that the configuration shows up in the **Work distribution** card.

:::image type="content" source="media/agent-capacity1.svg" alt-text="A screenshot of the Workstream with work distribution settings that are set to a unit-based capacity of 25." lightbox="media/agent-capacity1.svg":::

In the Customer Service admin center, we now move to **User management**, and then to **Enhanced user management**. In the following example, we opened the relevant user record and navigated to the **Omnichannel** tab. Here, we set the capacity to *100* as called out by the number 1 in the following illustration.

:::image type="content" source="media/agent-capacity2.svg" alt-text="A screenshot of an example of the Omnichannel tab of a user record where the capacity is set to 100." lightbox="media/agent-capacity2.svg":::

In this example, if we have a case workstream and a chat workstream, and the unit-based capacity for the chat workstream is *30*, then the agents can have any combination of cases and chats as long as the total never exceeds 100.  

With this setup, records start routing to our agents. The case record comes in and gets routed to our agent. The mechanism that handles the routing is the Queue Item entity. This record has a relationship to our routed record (Object) and to the agent that it was routed to (*Worked by*). Once our agent completes the case, the *Worked by* agent relationship value is removed, and the record is deactivated, which clears the 25 capacity points from our agent.

## No-code solution to release capacity non-case records

The advantage of the no-code solution is that it doesn't require you to be a developer and know C#. The example flows here might take about an hour or so to put together and test. Let's walk through the workstream setup for the entity along with the capacity. First, we create a custom activity entity, and then we complete the setup. Our example uses unit-based capacity, and the value of our custom entity is *25*  as indicated with the number 1 in the following illustration. In the illustration, the number 2 calls out that the configuration shows up in the **Work distribution** card.  

:::image type="content" source="media/agent-capacity3.svg" alt-text="A screenshot of the Workstream, work distribution settings that are set with unit based capacity of 25." lightbox="media/agent-capacity3.svg":::

## Route non-case records using Power Automate

Next, we automate the creation of our associated Queue Item record. In Power Automate, we insert a *Perform an unbound action* step with the **Action Name** field set to *msdyn_ApplyRoutingRuleEntityRecord*. The following illustration shows the steps of the first example Power Automate flow, which creates the Queue Item. The first example is the trigger when a record is added. The second example is the unbound action with action name of *msdyn_ApplyRoutingRuleEntityRecord* with the target being the example custom entity.  

:::image type="content" source="media/agent-capacity4.svg" alt-text="Diagram that shows the steps of the first example Power Automate flow, which creates the Queue Item. " lightbox="media/agent-capacity4.svg":::

## Close live work items using Power Automate

Next, we have to account for removing the agent from the **Worked by** lookup on the **Queue Item** record. As a result, the capacity of our custom entity (25 points) is cleared from our agent. We can use Power Automate also for this configuration.

Your business requirements may differ from the following example. Your flow is likely to be different, but the goals of your flow are the same.

In short, when our record is updated and if the **Status** field is set to *Completed*, list the related queue item, put a *-1* in the **Worked by** field, and change the **Status** and **Status Reason** fields to *Inactive*.

:::image type="content" source="media/agent-capacity5.svg" alt-text="Diagram that shows the steps of the second example Power Automate flow that removes the capacity from the user record." lightbox="media/agent-capacity5.svg":::

## Low-code solution to release capacity non-case entity

An advantage of the low-code solution is that it's a synchronous job. Your business processes might require a solution that is a bit closer to real-time than you get with the no-code solution. The setup for the workstream and capacity is the same as the previous example.

## Route non-case records using a plug-in

The first step is also similar to the previous example. We have to route the non-case record, which also creates the Queue Item record that we see natively when a case is routed. The steps and sample code to perform this action are available at [Route non-case records using a plug-in](/dynamics365/customer-service/trigger-routing-non-case-records). The plugin triggers the same `msdyn_ApplyRoutingRuleEntityRecord` as our Power Automate solution does.

## Close live work items or deactivate queue items

There's more good news here as well. There's sample code available at [Close live work items or deactivate queue items](/dynamics365/customer-service/deactivate-queue-items) to achieve the second series of actions to close our Queue Item records accordingly.

## Defining your business process

A key thing to keep in mind is the business process that drives these updates within your organization. It's critical that time is spent defining and documenting each step in the lifecycle of your non-case record. Both of our solution examples listed here assume the following basic process.

1. The non-case record is created and active.  

    This invokes the first step in our automation to create the Queue Item record.

1. It's then assigned to an agent.

1. The agent performs whatever interaction or updates your business process dictates.

1. The agent deactivates the non-case record when they complete the business process.  

    This invokes our automation that removes the agent from the **Worked by** lookup and deactivates the Queue Item record, which releases the capacity that was consumed by this item.

Step #3 in this list is where your business process specifics can add complexity to the flow or the plug-in. Let's expand the above process a bit:

1. The non-case record is created and active.

1. This invokes the first step in our automation to create the Queue Item record.

1. It's then assigned to an agent.

1. The agent makes a phone call to the customer to collect two pieces of information. After the agent speaks to the customer, they update picklist A and picklist B with the information collected from the customer and save the record.

1. This could invoke this record to be routed to the Queue A.

1. Another agent picks up the record from Queue A.

1. This invokes another Queue Item record to be created.

1. This agent performs some extra actions to complete the process and the record.

1. This invokes the Queue Item record to be closed releasing the capacity.

Your business process dictates the triggers for assignment and closure and should be accounted for in either the flow or the plug-in code to accommodate your requirements.

## Related resources

- [Unified Routing](/dynamics365/customer-service/administer/overview-unified-routing)
- [Release capacity for agents](/dynamics365/customer-service/administer/capacity-profiles?tabs=customerserviceadmincenter#release-capacity-for-agents)
- [Dynamics 365 Guidance](/dynamics365/guidance/#implementation-optimization-resources)
