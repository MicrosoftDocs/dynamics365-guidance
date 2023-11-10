---
title:  Delivery approach for the training plan
description: Find guidance about how to define how you run training based on your training plan for your Dynamics 365 implementation project.
ms.date: 06/26/2023
ms.topic: conceptual
author: TimoGossen
ms.author: timogoss
---

# Delivery approach for the training plan

As a subset of your training plan, your organization should create a training delivery document that contains specifics about the actual execution of training. Many of the topics in the training delivery document are covered in the overarching training plan. However, it's important to have a specific plan for training delivery, to ensure that your organization is prepared to carry out training.

Let's dig into the topics that your training delivery document should cover.

## Who is involved, and how?

In other articles, we define the [audience for training](training-strategy-training-plan-scope-and-audience.md) and explain the details of incorporating [resource scheduling](training-strategy-training-plan-schedule-and-materials.md) into your project plan. To help you create your training delivery document, we go a step further in organizing these resources into training sessions. This step is important if your organization schedules multiple training sessions at the same time. In addition to allocating your trainers and trainees, you must assign them to the correct training, based on the content that will be covered.

## What methods of training should the organization conduct?

Like training materials, different types of training suit different situations and users. Therefore, it's important to consider which training or combination of trainings best fits your organization. Consider the advantages and disadvantages of different methods. The following table shows common types of training, and the anticipated advantages and disadvantages of each type.

| Type | When it's most effective | Advantages | Disadvantages |
|---|---|---|---|
| Live training (in-person or virtual) | <ul><li>The content is critical for business functions, and you want strict control over delivery.</li><li>The content contains nonfunctional requirements, or business processes that require specific devices.</li></ul> | <ul><li>There is better interaction between the trainer and participants, and also among participants.</li><li>Feedback is immediate.</li><li>Collaboration in business processes is easier (for example, when front-office and back-office employees must work together to complete an order).</li></ul> | <ul><li>Scheduling challenges can occur.</li><li>Because Dynamics 365 is a web-based product, in-person variants of this type of training require a physical room that has computers.</li><li>In-person variants of this type of training are limited to the number of people per room per session.</li></ul> |
| Interactive web-based training | <ul><li>Content is moderately difficult.</li><li>Business processes are best learned through repetition and ongoing training, because user access to the application is necessary.</li></ul> | <ul><li>Web-based content can be built once and consumed by an unlimited number of users.</li><li>People can do the training on their own. There are no scheduling requirements, and no physical location is needed.</li></ul> | <ul><li>Trainings are less effective than in-person trainings, because there is less interaction, and the user faces more distractions.</li><li>Trainings aren't usually done in real time. Therefore, any questions or challenges that users face during a training session might not be answered quickly.</li><li>When web-based training is built by using digital adoption tools, it can be costly and can  also require technical maintenance.</li></ul> |
| Self-paced training | <ul><li>Content can easily be explained in a user manual or video series.</li><li>Content is best consumed as written reference material that can be used as needed.</li></ul> | <ul><li>Written and video content can be updated quickly as future releases and updates of your Dynamics 365 application occur.</li><li>Training content is easiest to create.</li></ul> | <ul><li>This type of training is the least interactive. Therefore, users who rely on interaction with either a trainer or a web-based application might struggle to learn when they must read or watch content.</li></ul> |

## When should training occur?

As a part of your training delivery plan, you should decide when different types of training occur. In other articles, we discuss how super users and trainers should be trained in necessary areas of your application earlier than system users. You should build this type of consideration into your training delivery plan. Plan to conduct training for your system users late enough in the project, after development and before user acceptance testing (UAT). In this way, your users don't forget concepts and tasks that they have been taught during training. However, be sure to leave enough time after training occurs to accommodate any delays in your project or training schedule.

We believe that it's never too early to start training super users and trainers. Because the main goal of training for users is to help them become familiar with your application early in your project, you should start to conduct training (whether formal or informal) with them during development. Then continue it as an ongoing process. These early training sessions should familiarize super users and project team members with basic application functions, and they should serve as a backbone for future train-the-trainer sessions.

The following image is a high-level sample schedule that shows training sessions for each important group that must be trained, alongside key relevant project milestones.

:::image type="content" source="media/training-plan-schedule.png" alt-text="Sample training plan schedule.":::

Trainers and project team members should be aware of how the size of the organization affects training. Larger organizations that have more users are likely to require multiple personas and more business use cases. Especially if these larger organizations are international companies or companies that have numerous locations, they might require different training sessions and venues, and training sessions might have to occur at different times during the project. In these cases, it's important not only to make sure that training materials are available in multiple languages, but also to employ multiple trainers or multilingual trainers.

In the sample project plan, system user training takes place over the course of a single week, in a single location. In international and multilingual organizations, most of the items in the plan become more complex. To illustrate the increased complexity, the following image shows what system user training might look like in a multinational organization.

:::image type="content" source="media/training-plan-schedule-comp.png" alt-text="Sample complex training plan.":::

As the image shows, the complexity of the training schedule and planning dramatically increases when the scope of the implementation increases. Instead of taking roughly a week, this updated training schedule now takes almost a month, in three different countries/regions, and requires drastically increased coordination of resources. If other phases that have different business process areas must also be covered, the complexity of training increases even more. We hope that these samples are useful demonstrations of the value of planning when, where, and how training occurs. They should also help you understand why it's important to understand that your organization should be prepared to make more investments to successfully train its users.

## How should your organization set up and maintain a training environment?

If your organization has created a Dynamics 365 environment to train users as part of a broader [environment management strategy](environment-strategy-overview.md) that uses [Application Lifecycle Management (ALM) best practices](application-lifecycle-management.md), make sure that this training environment is deployed with code and data that are representative of production use. In addition, make sure that the code and data are of adequate quality to meet your training objectives. Both these points are important:

- If your organization's training environment doesn't have up-to-date code and application features, your users are left confused. Therefore, the overall effectiveness of your training might decrease. Your users might feel that the training was unprofessional or incomplete, especially if the quality of the training environment is insufficient to accomplish training objectives.
- If your organization's training environment doesn't have sufficient and relevant test data, your users aren't properly trained. In addition, they might fixate on the quality of the data and not on the training materials. When users are distracted, overall training effectiveness decreases. This situation can have an impact on user adoption.

Poor data quality in your training environment can affect the training's real-world relevance. A common issue that we witness in poorly conducted training sessions is that users don't find the training realistic. This impression can affect the quality not only of the data that these users enter later during the training but also the data that they enter after the system goes live.

> [!NOTE]
> If your training environment contains only accounts that are named "Test 1" and "Test 2," for example, it's unlikely that your users will enter realistic data as they progress through their training scenarios. If users don't understand the implications of entering fictitious data, there can be wide-reaching impacts on production. Fictitious data that users enter in production can influence downstream business processes, system logic, and reporting. To ensure more realistic scenarios during training, we recommend that your dataset is a subset of real data from a legacy system.

## How do you assess competency and effectiveness of training?

One of the most effective ways to improve training is to collect feedback and use it to make enhancements. Training isn't meant to be a static exercise where material is created once and delivered in the same way during every iteration. It should be a work in progress that is frequently updated. After a training session is completed, there is still work to be done. Many organizations require multiple training sessions, and all of them present opportunities to revisit, evaluate, and improve future training sessions.

You can measure the effectiveness of your training by following several recommendations. The first is to assess your users' learning at the end of, or shortly after, training. Prioritize the processes that they use most frequently in their jobs. For example, it's much more important for sales users to understand how to create and update an account record in Dynamics 365 if they must complete this process every day. Such prioritization should be emphasized during the creation of any assessment method that you choose. Earlier in this section, we discuss how the creation of solid training objectives helps you assess the effectiveness of your training. Provided that those training objectives contain the most critical topics that we are training users on, we can now use them as the basis for assessing our users.

Many larger organizations create exams to assess the knowledge of their users. Some might even create a certification program that is used after training to assess readiness at a user level, at a team level, or even at a higher level, such as the business unit, subsidiary company, or geographical region. Trainers can create metrics based on exam results and certification statistics to evaluate training quality. If some groups have scores or statistics that are lower than desired, the organization can work to improve future training or host follow-up trainings for those groups.

Day-in-the-life testing, which can be used to measure real-world scenarios and the effectiveness or speed with which your users complete tasks, also measures training effectiveness and organizational readiness. Accuracy is important for ensuring data quality. However, it's also important to know whether some business processes take your users 10 minutes or two minutes to complete. This information can be used to measure your organization's readiness for the new application. If some business metrics must be met regardless of the application that is used, make sure that those metrics are met in your Dynamics 365 application. For example, if members your call center staff are expected to process at least six calls per hour, it's important to ensure that they have been trained to complete a single end-to-end call process in your application within 10 minutes.

Another way to measure the effectiveness of your organization's training is to analyze the results of your UAT. As we briefly discuss in the article [Define the training schedule](training-strategy-training-plan-schedule-and-materials.md), you can use UAT to gauge user competency in your application. Look at the number and types of non-system-related bugs that users logged, and measure the time that users take to complete the processes that they are testing (usually informally, because the goal of UAT is accuracy, not speed). If you find that your testers log many items that aren't system bugs but the result of knowledge gaps, you might want to update that training. This situation might also indicate that more user training in those areas is required.

Similarly, after the system goes live, you can use help desk statistics to determine the longer-term effectiveness of training. If users submit help desk tickets or request assistance about specific areas of your solution, you should review the training documents to determine whether they have to be updated. Once again, more user training might be required.

Another common approach to collecting feedback about training is to conduct pilot training sessions with a limited audience. You can invite super users to attend them, gather feedback, and use it to improve the training. A side benefit of pilot trainings is that they help super users in their process of becoming experts in your application.

| Question | Recommendation |
|---|---|
| During a training session, what if a critical bug is discovered that blocks the training from proceeding? | <p>We believe that your training environment should be treated like a production environment during training sessions. Just as bug fixes should not be made directly in production, they should almost never be made directly in a training instance while training is taking place. Depending on the severity of the bug, a work item should be created for a developer in their corresponding development or hotfix environment, and the bug should be fixed and tested before it's pushed to downstream instances (including training), per standard ALM processes.</p><p>If the bug is critical enough to block entire business scenarios and prevent trainees from accomplishing any tasks, it might be necessary to fix it directly in the training environment. However, we recommend this approach only in situations where the bug prevents any workarounds or any other sessions that can be conducted. Bug fixes that are made directly in a "live" environment can cause other, unforeseen issues to occur and can therefore lower users' confidence in the application even more. Furthermore, any bug fixes that are made in this instance must also be made in the lowest instance where development is occurring. Then regression testing must be completed, and any potential conflicts must be resolved.</p><p>For practical reasons, it's critical to have a skilled trainer who can both identify that there is a system bug and determine the appropriate workaround without causing major distractions for trainees. This point underscores how important it is for good trainers to understand how to use an organization's Dynamics 365 applications.</p> |

## Assumptions, dependencies, and risks

As we discuss in the article [Define the training schedule](training-strategy-training-plan-schedule-and-materials.md), successful training relies on many external factors that should be defined in your training plan. These factors can include *assumptions*, or statements that are assumed to be true of the project, and that are often critical to training success. Here are some examples of assumptions:

- Appropriate trainer resources are allocated to create training materials and train users.
- The tenant management and development teams create and maintain a training environment for use in the project.

Your training plan and project plan should also include *dependencies*, which can be represented in a process workflow. They effectively show that specific tasks or activities must occur before others as part of your training strategy.

:::image type="content" source="media/training-documentation.png" alt-text="Training documentation creation sample process workflow.":::

The tree in the preceding image is an example of a straightforward dependency list for creating a specific type of training document. Your plan probably contains more complex dependencies that might rely on multiple, unrelated project tasks. Define and organize these dependencies at the start of a project. You can then reduce the amount of time that your trainers or other project members must wait for required tasks to be completed by scheduling upstream project tasks specifically to minimize this downtime. This task must be done in coordination with the broader project team and project schedule.

Finally, create and maintain an active training risk log as part of the overall project risk log. This task is important for ensuring that proper attention is paid to training risks that might affect the success of training or other project activities that rely on successful user training.

> [!NOTE]
> Make sure that each training participant has a user account, and that this account gives the participant the same level of access that they will have in the production environment. Don't give training users access as system admins. Even though the team might not have defined the security model yet, if users have elevated permissions during training, they get a skewed impression of how they do their work in the new solution.

If you conduct multiple training sessions in a single training instance, it's important to take these proper actions at the conclusion of each training session:

- Properly document (with screenshots, if necessary) any bugs that are discovered during training, and send them for review or triage.
- If you restore from a Dynamics 365 backup, make sure that you have a backup for the correct date. Work with your partner or IT staff (and also Microsoft, if necessary) to ensure that this situation isn't a blocker.
- If you restore from source control as part of your [ALM process](application-lifecycle-management.md), make sure that all code and data are ready for an environment refresh.
- Refresh your environment by using your chosen method.
- Before the start of the next training, use a smoke test to validate user access and data.

## Next steps

- [Create a training plan](training-strategy-training-plan-scope-and-audience.md)
- [Define the training schedule](training-strategy-training-plan-schedule-and-materials.md)
- [Training process and best practices](training-strategy-process-and-best-practices.md)
- [Checklist for your training strategy](training-strategy-checklist.md)
- [Case study for your training strategy](training-strategy-case-study.md)
- [Training strategy](training-strategy.md)
