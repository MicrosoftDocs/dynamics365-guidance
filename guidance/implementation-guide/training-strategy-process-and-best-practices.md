---
title: Training process and best practices
description: Find best practices for the training strategy in Dynamics 365 implementation projects.
ms.date: 06/20/2023
ms.topic: conceptual
author: TimoGossen
ms.author: timogoss
---

# Training process and best practices

Training is an ongoing process. As we mention in the article [Training strategy](training-strategy.md), your organization's training journey begins long before the execution of user training. Furthermore, it ends long after users complete their first tasks in your production application. In this article, we list some of the best practices that we have learned.

## Training as an ongoing process

Training is an ongoing and constantly evolving process that reflects both changes in your organization and application, and changes to the Dynamics 365 ecosystem. While you're developing a training strategy, it's important to consider the implications of both types of change.

> [!NOTE]
> It's important to provide support to new users during and after onboarding, because these users might receive fewer training resources than users who were present during the application's initial rollout.

### Internal change

For the purpose of this section, *internal change* refers to change that, at a transactional level, is unique to the organization that experiences it. Each type of internal change might require that training materials are updated, and that training is then conducted for the same or different groups of users.

#### Personnel change

User turnover is inevitable, either when employees leave an organization and new ones take their place, or when employees change job roles within the company. All new users are expected to learn their job roles quickly, and to learn how to navigate the application and complete their work in it. Training helps achieve this goal.

It's unlikely that an organization will conduct multiple lengthy in-person training sessions for a single user's onboarding. Instead, organizations rely more on self-paced or web-based training as a means of education. It's important to provide support to new users during and after onboarding, not only because they are initially behind more experienced users who have been using the application for a longer period, but also because they might receive fewer training resources than users who were present during the application's initial rollout.

Your organization's training materials for users who join after go-live are similar to the training materials that were used before go-live. However, make sure that newer users are supported and receive the assistance that they require to be trained on the application.

#### Application change

Many Dynamics 365 projects have adopted a phased rollout approach, where features of each application are released to production over time. (By contrast, in the "big bang" approach, a single deployment to production before go-live has all the included functionality.) Although the rest of this section covers the development and distribution of training for the first release of application functionality, future phases of the project must include updates to training materials and new training sessions.

Your organization might want to treat each phase of a rollout as a distinct project from a training perspective. In this case, each future phase contains a distinct, more condensed training plan and training delivery schedule to ensure that proper user training is conducted at every stage. These future phases focus heavily on updating training materials based on new business processes, and on training both new and experienced users on the application.

> [!NOTE]
> Phase 2 training might include both users who are already familiar with the application (because they used it after the phase 1 go-live) and employees who have never used or been trained on your system. Any new and updated training materials should reflect the difference in experience and skill level of these user groups. It should be neither so simple that it's irrelevant to experienced users nor so complex that it's confusing to new users.

When you design your training materials, consider a building block approach. Phase 1 training materials and training can be the foundation on which all users can learn to use the application. Future phases can then build on that foundation. Training materials for subsequent phases can be updates of earlier material and newly created material.

### External change

In other articles, we discuss Dynamics 365 as software as a service (SaaS) that provides continual updates to organizations, from both a technical standpoint and a business standpoint. It's important that your organization prepares for these updates as part of its training strategy, and that these updates are acknowledged in the training plan and execution.

> [!NOTE]
> Our customers can activate updates to software at their own pace.

As updates to a Dynamics 365 application are announced and rolled out, your organization should set aside an instance that is used to conduct regression testing of business processes against your custom application. Trainers should be involved in these activities, and they should assess the potential impact of these updates on business processes.

Some updates, especially improvements that are made on the software's back end, cause little to no change in the way that your users do their work in your application. Therefore, they should not require a significant update to training materials or more training. However, other updates that are more focused on user experience or new features in the platform might drastically affect some system users. This type of change requires both updates to training materials and additional user training. The following table contains examples of how software updates might or might not require changes to your training offerings.

| | Software update | Training needs |
|---|---|---|
| **Performance improvements** | Improvements that we have made to the schedule board should result in a 40 percent increase in performance. | Although this update is relevant and beneficial to your users, there is no underlying change in the way that your users do their work. Therefore, it doesn't require an update to training materials or more training. |
| **Interface updates** | Updates that we have made to the layout of the schedule board should make navigation and the creation of bookings easier for your dispatchers. | Keep an eye on release notes to use new features. Work with your implementation partner and your internal teams on your heatmap for Dynamics 365 capabilities. Have a regular review of future projects, and incorporate new features that are delivered. Join the [D365UG User Group for Dynamics 365](https://www.d365ug.com/home) to learn about member-driven education, networking, and events. Create a Yammer group or Microsoft Teams channel to continue conversations about best practices and learnings. Host engagement events such as town halls or "lunch and learns" to continue training after go-live and drive user engagement. Share success stories about how people are using your application in innovative and impactful ways. |

## Training best practices

The authors of this guide have experience with Dynamics 365 implementations of all sizes and complexities. We have created and reviewed training plans, participated in and hosted training sessions, and evaluated the outcomes of training on user adoption. From most of these projects, common themes have emerged. We share the most important recommendations here as best practices, things to keep in mind during your organization's training process. These best practices are neither comprehensive nor set in stone. They are meant to guide a project team to a more successful training outcome.

### Earlier is better

It's important to start early with a training plan. Dynamics 365 projects are often run on tight timelines that provide little to no leeway. To ensure that no unexpected resource requirements or shortages appear midway through implementation, it's crucial that a training plan, including staffing and resource availability, is completed at the start of a project. Give yourself enough time to prepare a training plan, develop content, and deliver training. Content development should be completed well before the start of training delivery.

In addition, project roles and responsibilities in cloud solution deployments are rarely separate. Often, a single IT resource wears multiple hats, one of which might involve creating a training plan, reviewing training materials, or maybe even conducting training. By making sure that these individuals are aware, at the outset, of their contributions to the training plan, you help them balance their workloads and complete specific activities earlier. In this way, you might be able to prevent delays from occurring.

### More is (usually) better

In Dynamics 365 applications, a user can often access the same record or complete the same business process in several ways. Therefore, training that initially seems repetitive is useful, because it teaches multiple ways to accomplish a task, depending on the situation and context. Although too much training can involve a small amount of wasted effort, when an organization is adopting a new application, the cost of time is far preferable to users who are insufficiently trained on a sizable portion of their job. The latter situation occurs in organizations far more often than the former situation, even for similar amounts of training.

It's also important that your training materials don't contain too much duplicate content. You can have both content that is published to a website such as Microsoft Learn (learn.microsoft.com) and content that you deliver in training sessions. Both types of content should cover the same capabilities. However, too much overlap can result in training fatigue and overall apathy about training. An organization certainly wants to avoid a situation where users skip valuable content because they consider it repetitive.

### Train with a goal in mind

It's important to conduct different training for all users by using different methods. However, it's more important not to lose sight of the goal: successful user education and meaningful adoption of your Dynamics 365 application.

It does the organization no good if every technician understands how to use their new mobile application, but none of them use it correctly because of a failed training process. Having comprehensive training materials is just one step in this process. Although the more obvious goals of high training participation and education are important, the key that can separate excellent training programs from adequate ones is, as we state earlier in this section, effective training that leads to excitement and high user adoption together with accomplishment of critical key performance indicators (KPIs).

### Consider your audience

In addition to having distinct job roles, your users come from diverse backgrounds and probably different generations. Avoid alienating your audience through references, case scenarios, pictures, or stories that might confuse or even offend some groups of people. Your training should keep users engaged, but be careful not to be divisive.

For example, a junior salesperson in their twenties and a senior salesperson in their sixties attend the same introductory training. Your application includes an embedded LinkedIn widget on your contact entity. Trainers should not assume that both users are familiar with LinkedIn and its capabilities. However, they also should not assume that only one of the users is familiar with LinkedIn, because such an assumption is even more divisive.

A good rule of thumb is to assume that all training participants arrive with the same level of background information and context of the application, plus any technological knowledge that is required to use it effectively.

### Accessibility concerns

Your organization must consider accessibility when it creates training materials. All Office 365 products have an accessibility checker that can help you spot potential issues in your content.

### Identify ongoing challenges

As we discuss earlier, feedback is an important part of any improvement cycle. In addition to identifying areas of improvement for future trainings and training materials, we recommend that the people who conduct training or collect feedback from the training identify key areas where users are struggling with new functionality. This information can be used to create more focused training materials that can be distributed to users. Alternatively, it can be used to create webinars or other sessions that are focused on these problem areas.

## Guidance for finance and operations apps

Up to this point in this section, our training guidance has applied across Dynamics 365 apps. Although our customers often combine two or more Dynamics 365 apps in their solution, there are differences between finance and operations apps and customer engagement apps. <!-- can mean differences in how each project should train its users. In this section, we highlight some of these differences and how to apply them to your training material.-->Here, we list resources that are provided for Dynamics 365 Finance, Supply Chain Management, and Commerce, and that can help with product help and training.

### Help on learn.microsoft.com

The [Dynamics 365 documentation on Microsoft Learn](/dynamics365/) is the primary source for product documentation for the previously listed apps. The site offers the following features:

- **Access to the most up-to-date content**: The site gives Microsoft a faster and more flexible way to create, deliver, and update product documentation. Therefore, you have easy access to the latest technical information.
- **Content written by experts**: Content on the site is open to contributions by community members both inside and outside Microsoft.
- **Content that is personalized based on the selected language**: If a user is set up for the German language, for example, any help content that they access will be provided in German. However, some areas aren't translated from English.

<!--- Help is now on GitHub Customers can copy and create personalized Help content and link it to their application. Customers can create a personalized and contextualized Help resource for users of their custom business processes.-->

> [!NOTE]
> You can find content on Microsoft Learn by using any search engine. For the best results, use a site search. For example, enter *site:learn.microsoft.com Dynamics 365 "search term"*.
>
> As you're choosing the appropriate tier for the environment, consider the number of concurrent users of the training environment. Don't automatically select the default tier 2 environment if the volume of expected users exceeds the recommended volume for the tier. Learn more about the different environment tiers in [Selecting the right environment for your organization](/dynamics365/fin-ops-core/fin-ops/imp-lifecycle/environment-planning?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#selecting-the-correct-tier-2-or-higher-environment).

### In-product Help

In the Dynamics 365 client, new users can enter the Help system to read articles that are pulled from the [Dynamics 365 part of Microsoft Learn](/dynamics365/). In addition, they can find task guides from the Business process modeler (BPM) in Microsoft Dynamics Lifecycle Services. Help is contextualized to the page that the user is on. For example, if a user is on a sales order page and wants to know how to create sales orders, the Help system shows the Microsoft Learn articles and task guides that are related to sales orders.

:::image type="content" source="media/training-help-pane-ops-help.png" alt-text="Help pane." lightbox="media/training-help-pane-ops-help.png":::

### Task guides

Task recorder and task guides are useful help and training features. You can use Task recorder to record a user's activity in the user interface (UI). You can capture all actions and any UI fields and controls that are used. This recording can then be used in a task guide.

A task guide is a controlled, guided, interactive experience that leads you through the steps of a task or business process. You can open (or play) a task guide from the Help pane. When you select a task guide, the Help pane shows the step-by-step instructions for the task.

:::image type="content" source="media/training-task-guide-ops.png" alt-text="Task guide steps in the Help pane." lightbox="media/training-task-guide-ops.png":::

Localized task guides are available, and you can create custom task guides. The data that you enter in the system is saved in the environment.

To begin the guided, interactive experience, select **Start Task guide** at the bottom of the Help pane. A black pointer shows you where to go first. Follow the instructions that appear in the UI, and enter data as directed.

:::image type="content" source="media/training-task-guide-step-1-ops.png" alt-text="Step in the guided, interactive experience." lightbox="media/training-task-guide-step-1-ops.png":::

> [!NOTE]
> As you're choosing the appropriate tier for the environment, consider the number of concurrent users of the training environment. Don't automatically select the default tier 2 environment if the volume of expected users exceeds the recommended volume for the tier. Learn more about the different environment tiers in [Selecting the right environment for your organization](/dynamics365/fin-ops-core/fin-ops/imp-lifecycle/environment-planning?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#selecting-the-correct-tier-2-or-higher-environment).

## Guidance for customer engagement apps

Dynamics 365 has product-specific tools to help with user training for the customer engagement apps. Custom help panes are one of the most common tools that are used.

### Custom help panes

Dynamics 365 lets you create guided help pages that provide in-product assistance to your users. This assistance can be customized to your application and user base, and can include text, links, images, and video links. Learn more in [Custom help panes and learning path](/powerapps/maker/data-platform/create-custom-help-pages#custom-help-panes-and-learning-path).

## Related resources

<!--- [Training plan template](https://community.dynamics.com/cfs-filesystemfile/__key/communityserver-components-sitefiles/TechTalk+Presentation+Files/Part-2-_2D00_Training-Plan-Template-DYN840PAL.xltx?_=637360611268049897) TODO:fix broken link-->

<!--- [Training plan charter template](https://community.dynamics.com/cfs-filesystemfile/__key/communityserver-components-sitefiles/TechTalk+Presentation+Files/Part-2-_2D00_Training-Plan-Charter-Template-DYN840PAL.dotx?_=637360611901424624) TODO:fix broken link-->

<!--- [TechTalk Series: Training Plans and Content for your Finance & Operations Project (Microsoft Dynamics blog)](https://community.dynamics.com/365/b/techtalks/posts/techtalk-series-training-plans-and-content-for-your-finance-operations-project) TODO:Fix broken link-->

- [Dynamics 365 training offerings](/dynamics365/get-started/training/)
- [In-product Help for finance and operations apps](/dynamics365/fin-ops-core/fin-ops/get-started/help-overview#in-product-help)
- [Custom help panes and learning path](/powerapps/maker/data-platform/create-custom-help-pages#custom-help-panes-and-learning-path)

## Next steps

- [Create a training plan](training-strategy-training-plan-scope-and-audience.md)
- [Define the training schedule](training-strategy-training-plan-schedule-and-materials.md)
- [Delivery approach for the training plan](training-strategy-training-plan-delivery-approach.md)
- [Checklist for your training strategy](training-strategy-checklist.md)
- [Case study for your training strategy](training-strategy-case-study.md)
- [Training strategy](training-strategy.md)
