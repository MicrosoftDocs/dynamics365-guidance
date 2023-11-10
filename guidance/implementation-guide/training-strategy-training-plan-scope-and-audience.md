---
title:  Create a training plan
description: Find guidance about how to develop your own training plan for your Dynamics 365 implementation project.
ms.date: 06/27/2023
ms.topic: conceptual
author: TimoGossen
ms.author: timogoss
---

# Create a training plan

Proper training is critical to user adoption. Organizations must develop a training plan at the start of the project and engage resources from the beginning.

It's important to remember that managing a training plan is an iterative process. As you progress in the project and learn more about your business requirements and training needs, you might have to update your plan.<!-- [This sample training plan charter](https://community.dynamics.com/cfs-filesystemfile/__key/communityserver-components-sitefiles/TechTalk+Presentation+Files/Part-2-_2D00_Training-Plan-Charter-Template-DYN840PAL.dotx?_=637360611901424624) gives you something to start with. TODO: FIX BROKEN LINK-->

:::image type="content" source="media/training-plan-elements.png" alt-text="Training plan elements.":::

We recommend putting together a training plan that, at a high level, consists of at least the following elements:

- Training objectives
- Scope
- Audience
- Training schedule and resource availability (project planning)
- Delivery approach
- Validation of training success/objectives
- Assumptions/dependencies
- Risks
- Training environment management
- Training materials
- Training as an ongoing process
- Training resources

Just as the project plan is key to project timelines and execution, a training plan is key to training timelines and training execution. Training of business users is one of the last tasks on a project and has dependencies on several key items. For example, you need a near-complete solution, good-quality and representative business data, and reserved time from users. If a project is running even a little late, the final preparations for training are often squeezed. A robust, well-thought-through training plan that reduces the number of items in the critical path is essential for avoiding last-minute compromises and lower-quality training outcomes.

## Scope

One crucial element for ensuring that your organization's project has a proper training strategy is the definition of an accurate scope for the training. Here are different areas that cover the breadth of scope that you must build into your training plan:

- Business processes that are completed by users. These processes are derived from your user stories and functional requirements.

    **Example**: Users must be able to create and process an invoice from end to end in Dynamics 365 finance and operations apps.

- Any nonfunctional requirements that users must be trained to meet.

    **Example**: Users should be able to provide feedback directly from the application.

- Any administrative tasks that users might have to perform in the application, but that are separate from their business-driving work.

    **Example 1**: Users must be able to configure and use the Advanced Find tool in Dynamics 365.

    **Example 2**: Users should be able to upload templates by using the Dynamics 365 data management tool.

There might be other areas of your solution that should be part of the scope of your training. Tasks or processes that users must accomplish in Dynamics 365 should probably be part of it. For example, during your implementation, training should be provided to project team members who will have to work inside the application from a development or configuration perspective.

After you have the full set of business processes, requirements, and tasks, you can use them to create a *true scope* for your training. The true scope consists of actionable training areas. There might not be a one-to-one relationship between them, because there might be overlap between processes, and other training topics might have to be added.

Next, we discuss how to avoid overlap and add more training topics.

### Avoiding overlap

You might, for example, have 10 sets of business processes that are different in terms of function but almost identical in terms of system execution. Each process takes a user 30 minutes to complete. In this case, consider setting your system training areas so that they represent the similarity in the way that users complete the business processes in your solution. Don't set them so that they represent the functional disparity between the processes. You can still reference different business functions, and can even take the time to walk through any differences in execution. However, it's important that the scope (that is, each training area) is efficiently framed and doesn't duplicate training effort.

### Other training topics

You might, for example, require that users frequently switch between their mobile and desktop devices. However, if you also require minimal delay during the transition, it might be important to cover the transition, even if it isn't necessarily covered in any business processes, or in any other requirements or tasks.

The next step in the process of setting the scope for your training is to categorize and prioritize the list of training areas that you've created. For example, some business processes in your new application might differ from the "as is" processes in your organization's current application. This fact is important for a few reasons:

- System training and business process training are two separate efforts, even though training might address both types.
- Training that is related to changed business processes should be given special attention during training sessions and in training materials.

It's common for business process training challenges to affect system training effectiveness. As part of the scope for your training, you should separate system training on the new processes and application from subjects that are related more to organizational change management.

You should also prioritize, or at least highlight, any training that is related to critical nonfunctional requirements that have an impact on legal regulations or company policies. For example, if your organization is legally required to fill in fields on your sales order form in a specific way, that section of training should be emphasized, so that users are aware of its importance.

One process that might help you determine the priority of training areas is the creation of a change impact assessment. In this assessment, you detail the changed areas, the topics and stakeholder groups that are affected, and the impact that the changed areas have. You then have a consolidated list of training topics, an estimated list of people who need training on a topic, and the beginnings of a prioritization for each.

The following table shows an example of a change impact assessment.

| Change impact | Training topic | Impact (1–5) | Action |
|---|---|---|---|
| The Purchase department's legacy system will be replaced with Dynamics 365 Supply Chain Management, and the business wants to use the standardized process in Dynamics 365. | Procure to pay business process | 3 | Trainers will hold a series of webinars where they detail differences between the legacy system that is used for purchasing and Supply Chain Management. |
| Field technicians are moving from a pen-and-paper-based work order management system to a mobile application. | Using the new mobile application to complete a work order | 4 | Because of the impact that this change has, multiple live training sessions for technicians will be held to ensure proper education. |

## Audience

Now that the objectives for your organization's training strategy have been defined, together with the scope of content that training should contain, we can define the next piece of the training puzzle: who should be trained, and what type or types of training they should receive.

### Who receives training?

It's critical to identify the different groups of people who need training. Dynamics 365 offers excellent role-based access control and application segregation as a way of providing access to users based on how they have to use your solution. Therefore, it's important that all employees who must use the product are trained in the correct way and on the correct topics.

The following sections identify the core groups of people who should be trained on your Dynamics 365 solution.

> [!NOTE]
> Each group of users can be broken into subgroups.

It's important to break down these users into personas. If personas are incomplete or incorrect, your organization might not complete proper training on the correct business processes. Worse still, it might not complete training at all for specific user groups.

### System users

System users are the people who use the system daily and drive direct business value. Your solution might have multiple types of system users that are separated by licensing, security role, or even the Dynamics 365 app itself. Each type requires different training. This group of users might cover multiple departments and job functions. Therefore, the training should be general and provide high-level knowledge of your solution with regard to key core entities that all users might have to access. However, it should also be specific enough to help these users perform their job functions.

As part of your training plan, be sure to identify each business role that must use your solution differently and requires training. This process is related to, but distinct from, the process of creating groups of users based on security role. Some personas might have identical security roles in Dynamics 365 but different job functions. These groups of users use your solution differently and require different training.

:::image type="content" source="media/training-personas.png" alt-text="Training personas.":::

For example, your organization determines that the access that salespeople and sales team leaders require in your system is similar enough to warrant identical security roles. Nevertheless, it's important that these groups of users are treated distinctly during this portion of your training strategy, and that each group receives correct training. Salespeople must be trained more on the "doing" functions of your solution, such as creating records, updating records, and sending emails. Although sales team leaders might work on similar tasks to salespeople, and they might require some or all of the same training, they also need other types of training, such as reviewing and approving records, and creating and viewing charts and dashboards.

Another benefit of being specific when you define training personas based on business role instead of security role is the value for new hires. If a new hire in a specific business role undergoes an exact set of training based on what was identified previously in this section, onboarding is easier, and less time is spent trying to match job titles to security roles and then back to business processes in your solution.

> [!NOTE]
> In many organizations, some user roles have more turnover than other personas that receive training. Therefore, your training materials should be structured in a way that helps make staff onboarding easy.

### Trainers

Trainers are a special category of users who require training. They should be knowledgeable in all areas of the system, and are responsible for developing training materials and training other users. "Train the trainer" is a common approach to onboarding this type of user to your solution. Depending on the size of your organization, you might have several trainers. It's important that, at the end of "train the trainer" sessions, your trainers are aware of and able to effectively perform their job functions (creating training materials and conducting training for other users). The training of these users has a different goal than the training of system users: trainers should be part of the training strategy process and will be advocates for the new application.

### Super users

Super users are an elite group of (usually) system users who act as champions of the application. This group is key to driving excitement and adoption of the new system. These users are often involved in early feedback cycles with the project team. As subject matter experts (SMEs), they become educated about the application early on. Then, by the time system user training begins, your super users are experts in different business processes. As part of your training delivery plan, your organization can strategically use super users to help your trainers in their job functions (by having them attend training sessions and serve as application advocates). In addition, these super users can act as a "first line" that helps answer employee questions. In this way, they help prevent your support desk from being overwhelmed and, at the same time, help keep morale high.

We have mentioned several times that meaningful user adoption is critical to the success of an application and relies heavily on a well-executed training strategy. Super users are instrumental in this process. If your organization is deploying several applications, we recommend having multiple super users who are spread across each application according to their area of expertise.

### Project stakeholders and executives

If your project stakeholders and executives must be able to access and use your solution, they must also receive training. This training should be tailored to their specific role.

Executive buy-in is important for the success of a new application, and meaningful user adoption applies to this group of users just as it does to system users. To take advantage of the extra effect that executive buy-in might have, you should consider "visibly" training these users, so that other members of your organization know that training is ongoing. You can also notify these stakeholders about training that other roles are expected to undergo. This approach can help from a buy-in perspective.

### Support desk and administrators

Another critical group of people who need training consists of support and administrative users. These users might require a specific amount of training on the application and specific business processes. However, they must become familiar with the application from a maintenance perspective. Training for these users focuses on tasks that are related to system maintenance, troubleshooting, and administration.

## Training scope

After you've defined the distinct groups (and subgroups) that should receive training, you should work on matching the different training areas that are defined in the [Scope](#scope) section of this article with the groups of users that were defined earlier. Each group of users requires a specific set of training (based on training areas). In your training plan, we recommend creating a matrix that shows training role against training subject area. You can then refer to this matrix when you create training materials, plan training delivery, and so on.

When you determine which personas need which types of training, refer again to your user stories as a baseline. You should also consider which groups need training in nonfunctional areas and administrative areas.

> [!NOTE]
> Some groups of users might require different levels of training on identical subjects. For example, trainers might require only basic training on Dynamics 365 administration (so that they can help other users during training and implement training tools). However, administrators and support desk personnel might require advanced training on the same topic. You should structure your assignment of training topics to users in a way that is comprehensive but not superfluous.

## Next steps

- [Define the training schedule](training-strategy-training-plan-schedule-and-materials.md)
- [Delivery approach for the training plan](training-strategy-training-plan-delivery-approach.md)
- [Training process and best practices](training-strategy-process-and-best-practices.md)
- [Checklist for your training strategy](training-strategy-checklist.md)
- [Case study for your training strategy](training-strategy-case-study.md)
- [Training strategy](training-strategy.md)
