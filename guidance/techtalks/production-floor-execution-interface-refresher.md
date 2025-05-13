---
title: Production floor execution interface refresher in Dynamics 365 Supply Chain Management
description: Summary of TechTalk video that provides a comprehensive overview of the production floor execution interface in Dynamics 365 Supply Chain Management
ms.date: 05/01/2025
ms.topic: conceptual
author: vibhutinair23
ms.author: vibhutinair
ai-usage: ai-assisted
---

# TechTalk: Production floor execution interface refresher in Dynamics 365 Supply Chain Management

We based this article on [a TechTalk](https://youtu.be/66Y-OVC9ClU?si=OzfKlUA_O37hIS7r) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/techtalk-DTV087EXT-slide.png" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/66Y-OVC9ClU?si=OzfKlUA_O37hIS7r":::

## Managing production workflows in Dynamics 365 Supply Chain Management

The Production Floor Execution interface in Dynamics 365 Supply Chain Management provides a streamlined, role-based workspace for workers to manage their production responsibilities directly from the shop floor. This interface offers a comprehensive toolset for accessing job overviews, tracking time and attendance, managing materials, and reporting progress on assigned tasks, all within an intuitive and responsive environment.

## Overview of core capabilities

The interface is designed to simplify the experience of frontline manufacturing employees by centralizing daily operations into a single, easy-to-use screen. Workers can view their assigned production jobs, track progress, report completions, and access time-related activities such as clocking in and out, taking breaks, and registering indirect activities. The layout is optimized for clarity, minimizing training time and ensuring consistent tasks execution across different roles and facilities.

:::image type="content" source="media/job-list-assigned-to-worker.svg" alt-text="Screenshot showing a list of all jobs assigned to a worker" lightbox="media/job-list-assigned-to-worker.svg":::

The Production Floor Execution interface is configured through the Dynamics 365 client, providing flexibility to adapt the interface based on roles, shifts, or sites. This setup supports tailored workflows that match specific business needs, ensuring that each user sees only the most relevant data and actions for their tasks.

Time and attendance activities are a key part of the interface experience. Workers can clock in and out, register breaks, and log time spent on non-production activities. They can also review their recorded time for the day, helping create transparency between employees and supervisors while enabling more accurate labor costing.

## Registering material consumption

A significant enhancement to the interface is the ability to register material consumption. This feature enables workers to directly record the materials used during production as they execute their jobs. Whether materials are consumed automatically or manually, this feature ensures that inventory levels are accurately reflected in real time and aligned with actual shop floor activity.

This update also minimizes the need for downstream reconciliation or manual corrections, giving production managers and inventory planners greater confidence in the data coming from the floor. The flexible configuration supports material registration workflows to adapt to different manufacturing scenarios, from discrete to process production.

## Tracked components and visibility

The Tracked Components feature enhances traceability across the production lifecycle by allowing workers to register and view batch and serial number information associated with specific components. This is especially valuable in industries with strict quality or compliance standards, as it ensures that every part used in an assembly can be tracked and validated throughout the supply chain.

:::image type="content" source="media/license-plate-validation.svg" alt-text="Screenshot showing the license plate validation option" lightbox="media/license-plate-validation.svg":::

Through the interface, workers can effortlessly identify which tracked components are required, which are consumed, and which remain outstanding—making it easier to manage deviations or substitutions when needed. The interface provides this data contextually alongside the production job, minimizing the number of steps and clicks required to complete a task.

## Enhanced monitoring and future capabilities

In addition to task-specific enhancements, the interface now supports visualization of machine health metrics. This allows workers to view performance data directly related to the machines or resources they operate. By surfacing these insights within the same interface used for production tasks, organizations can empower frontline workers to respond to issues quickly, minimizing downtime and improving throughput.

:::image type="content" source="media/decouple-time-assembly.svg" alt-text="Screenshot showing the skip time adjustments option" lightbox="media/decouple-time-assembly.svg":::

Looking ahead, additional features are planned to further expand the interface's capabilities. These upcoming enhancements include more comprehensive time and attendance integrations, user interface improvements for quicker navigation, and extended support for complex material handling and registration scenarios.

## Conclusion

The Production Floor Execution interface in Dynamics 365 Supply Chain Management continues to evolve into a central command hub for shop floor workers. With capabilities that support real-time job tracking, accurate material consumption, batch and serial traceability, and integrated time and attendance, it enables a higher degree of operational visibility and control. With ongoing enhancements making the interface more intelligent and adaptive, it's set to play a crucial role in boosting productivity and ensuring data integrity in modern manufacturing environments.

## Related resources

You can use the following resources to learn more about Dynamics 365:

- [Configure the production floor execution interface](/dynamics365/supply-chain/production-control/production-floor-execution-configure)

- [Customize the production floor execution interface](/dynamics365/supply-chain/supply-chain-dev/production-floor-execution-customize)

- [Adjust material consumption and make material reservations (preview)](/dynamics365/supply-chain/production-control/production-floor-execution-use#adjust-material-consumption-and-make-material-reservations-preview)

- [Register batch/serial numbers for finished products and their components](/dynamics365/supply-chain/production-control/production-floor-execution-use#tracked-components)

- [Register and track batch/serial numbers for finished products and their components](/dynamics365/supply-chain/production-control/tracked-components)

- [Design the production floor execution interface](/dynamics365/supply-chain/production-control/production-floor-execution-tabs)
