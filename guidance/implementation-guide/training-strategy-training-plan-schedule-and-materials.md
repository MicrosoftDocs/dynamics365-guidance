---
title: Define a schedule for training plans in implementation projects
description: Find guidance about how to define a schedule for the training plan in your Dynamics 365 implementation project.
ms.date: 06/26/2023
ms.update-cycle: 1095-days
ms.topic: concept-article
author: TimoGossen
ms.author: timogoss
ms.custom:
  - evergreen
---

# Define a schedule for the training plan in your Dynamics 365 implementation project

Successful integration of a training strategy into the main project effort requires coordination with project management resources. Your organization's training strategy doesn't exist independently of other ongoing efforts in the project. It's important that key milestones, resource requirements, dates, and tasks are acknowledged and accounted for as part of your training plan, and that they are incorporated into your overall project plan as tasks or dependencies.

Regardless of the size of your organization and the complexity of the application that is being deployed, you must consider the following training-related factors. We have included examples of common questions that project teams encounter as a part of their training initiatives. If these questions are applicable to your project, you must address them as part of your training strategy and project plan. This list isn't a comprehensive list of the questions that your organization must answer, but it should help you get started.

- **Project team resources**:

    - What is the availability of the trainers and super users?
    - Who are the super users, and if they haven't been defined, when is that decision made?
    - Does this process involve any external resources who require onboarding or administrative setup before they can begin their work?

- **Trainees**:

    - Who must take part in training activities, and when do these activities occur?
    - Are there any resource dependencies (for example, resource A is required before resource B)?
    - How will training, and attendees, be staggered so that there is no gap in coverage for day-to-day business functions?

- **Dates or key milestones**:

    - When should training begin for distinct groups of users?
    - What dependencies do these trainings have?
    - Are any project-related activities dependent on training?
    - Does training rely on the creation of materials or development work whose schedules could shift?
    - What milestones should training include, and do these milestones have any impacts?

- **Training plan**:

    - When is the training plan completed?
    - Who reviews it, and what is the plan for updating it if necessary?

- **Training execution and feedback**:

    - When and where does training take place?
    - Does training have an impact on other project efforts?
    - If there are subsequent trainings, how is feedback evaluated, and what is the cycle for processing this feedback?

As the preceding list shows, many questions that are related to a training strategy have an impact on, or rely on, activities that occur separately from traditional training activities. In the following table, we examine one question from this list to underscore the importance of asking and getting answers for these questions as part of your project planning.

| Question | Answer |
|---|---|
| Are any project-related activities dependent on training? | <p>We often recommend conducting training before user acceptance testing (UAT). The major benefits of this order are as follows:</p><ul><li>During UAT, users already know how to navigate the system and accomplish tasks. Therefore, fewer items that are logged as bugs should have to be listed as training issues.</li><li>UAT serves as a measure for validating the effectiveness of training. If many training-related issues are identified during UAT, you might have to update your training materials. You might even conduct future training on the subjects that users are struggling with.</li></ul> |

This example shows why it's crucial for your training plan and overall training strategy to reflect and be connected to your organization's project plan. It also shows why updates to one plan must be reflected in the other plan. Otherwise, you risk creating conflicts that can lead to project delays.

## Training materials

Your organization can create multiple consumable types of content for Dynamics 365 applications. Depending on your project, you can create different types for use in different trainings. Here are a few common examples of the types of training materials that an organization might create:

- **Documents**: Your organization can create written documents that guide users through the application and educate them about business processes. These documents can also serve as reference materials. This type of material is the least interactive, but it's the easiest to create and update.
- **Videos**: Trainers can create videos that explain key training areas in detail and walk through the application to provide guidance about how users can navigate the system and complete their job tasks. For many users, videos are more helpful than documents, because they show features of the application instead of just telling about them.

    Instead of recording one long video that walks the user through an end-to-end flow, trainers can record videos in small chunks that represent discrete processes in an application. This approach has benefits from a maintenance perspective. When changes are made to your application, trainers don't have to re-record the whole video, including training for concepts that haven't changed. Instead, they can focus on updating specific videos for new features and functionality.

- **Microsoft Learn**: Microsoft has published [several labs on the Microsoft Learn Training portal](/training/) that provide a wealth of knowledge about Dynamics 365. Microsoft Learn also covers other applications that your users must get to know. Microsoft Learn allows the user to follow any number of predetermined paths that are designed for different user personas. Individuals can also create their own knowledge path that is tailored to their learning requirements. Users can learn on their own schedule, browse videos when necessary, and engage with other community members.
- **Guided help**: Dynamics 365 includes the capability to create custom help panes and guided tasks to help your users complete basic tasks in the system. Guided help is easy to set up and implement, and doesn't require another solution on top of your application. In addition, Dynamics 365 applications can install the [Guides application](/dynamics365/mixed-reality/guides/), which allows for visual or holographic displays that show step-by-step instructions for tasks that your users must perform.
- **Virtual material via a digital adoption platform**: Digital adoption platforms are built on top of Dynamics 365 and enable users to interact directly with the application during training. They are the most interactive form of training material. The virtual material is easily updated, and after it's published, it has an immediate effect for all users who must view it. It reduces the need to update physical documents or re-record parts of video material. Digital adoption platforms can come in multiple forms. One effective form is a tool that trainers can use to create multiple "scripts" that walk a user through a business process in Dynamics 365. This tool is useful if, for example, all users must learn basic navigation through an account record, but only system administrators must know how to customize a price list. In the article [Create a training plan](training-strategy-training-plan-scope-and-audience.md), we talk about reducing overlap. Digital adoption platforms are an excellent way to manage scope in the creation of training materials. Instead of having to explain the same material twice in different formats, create multiple reference guides, or create a single complicated guide, a trainer can create one set of scripts and apply them to different groups of users.

## What to consider when choosing the training materials

Be thoughtful when you choose the type or types of training materials to create for your training audience. Consider the benefits and drawbacks of each. For example, if your business users are mainly users who don't have lots of experience working with web-based cloud applications, you might want to consider using a digital adoption platform, because it offers a more hands-on approach. On the other hand, system administrators and support desk users might find documents more helpful, because they prefer to have the large volume of written information that doesn't require all the hands-on training that a digital adoption platform provides.

When you create training content, keep in mind that training is an ongoing process. Your organization can start to create training materials and training early in your project, and then refine it later. In the world of cloud applications, where software is constantly changing, it's important that your training strategy prioritizes adaptability, so that you can easily update materials in response to application changes.

You should also consider language and accessibility needs in your organization. If you have a multi-geo or multi-language deployment, any training materials that you create might have to be available in different languages. These materials must also comply with any federal, state, or local regulations about accessibility, so that all users have an equal opportunity to consume effective training materials.

## Who develops and reviews the content?

During the creation phases of your project plan and training plan, you must identify the trainers, subject matter experts (SMEs), and business process owners who help develop the training content. Trainers usually create the content, which is then reviewed by the SMEs and/or business process owners. As we discuss earlier, depending on the importance of the course, you might want to consider bringing in multiple people to review the material.

## How long does it take to develop the content?

Your organization must allocate time for content design, development, and review in the project schedule and training plan. The amount of time that is required to create training content depends on the complexity of your application and the type or types of content that must be developed. To estimate the time, we recommend identifying the scope of training areas and subsequent material that must be created based on those areas, and the format or formats that the training materials must take. You can then estimate the total time to create training materials based on experience. Alternatively, you can extrapolate the total time from the amount of time that a trainer takes to create a subset of the material.

## When is the content needed?

Your project plan should specify when content creation begins, and your training plan should specify when training materials become available to specific groups of users. These two schedules should be coordinated to ensure that content creation begins on time, and that the material is ready when it's needed. System user training can begin around the time when development is completed (that is, when the system is code-complete, and no changes to the application are anticipated).

## Where do you store the content?

We recommend that your organization employs a content storage control method, especially if multiple types of content are being created for groups of users. Training content should exist in a single centralized source instead of being passed around by email or shared links. This approach ensures proper source control and the ability to institute access control for your user groups. In addition, if more than one person will edit content, your organization might need a versioning strategy.

## Next steps

- [Create a training plan](training-strategy-training-plan-scope-and-audience.md)
- [Delivery approach for the training plan](training-strategy-training-plan-delivery-approach.md)
- [Training process and best practices](training-strategy-process-and-best-practices.md)
- [Checklist for your training strategy](training-strategy-checklist.md)
- [Case study for your training strategy](training-strategy-case-study.md)
- [Training strategy](training-strategy.md)
