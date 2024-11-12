---
title: TechTalk Optimize the experience in Dynamics 365 
description: Summary of TechTalk video that talks about how to design the optimal user experiences in solutions with Dynamics 365 apps, using Dynamics 365 Finance or Dynamics 365 Supply Chain Management as examples.
ms.date: 11/07/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Optimize the experience in Dynamics 365

In today's fast-paced business environment, efficiency and user experience are paramount for organizations relying on enterprise resource planning (ERP) systems, such as solutions with Dynamics 365 apps. We can't overstate the importance of optimizing the user experience in apps such as Dynamics 365 Finance or Supply Chain Management. Organizations are constantly seeking ways to streamline processes and improve user satisfaction, ensuring that employees feel empowered by their tools rather than hindered by them.

We based this article on [a TechTalk](https://youtu.be/5qechZ8ytpY) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/impl-opti-exp-slide.png" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/5qechZ8ytpY":::

> [!TIP]
> The TechTalk session was about finance and operations apps, but this article reflects that the general guidance applies to all solutions with Dynamics 365 apps.

## The power of personalization in ERP

Personalization in ERP systems is more than a buzzword; it's a necessity. A few years ago, businesses often faced significant challenges in adopting ERP solutions because of usability issues. While Dynamics 365 offers a broad range of functionalities out of the box, not every user needs access to the entire suite of tools available. The key to a seamless user experience is tailoring the interface to meet specific job roles and responsibilities.

Take, for example, a purchasing agent who spends most of their time creating non-inventory purchase orders. A standard interface designed for all users might not suit their needs, leading to frustration and inefficiency. Personalization, such as hiding unused fields and actions, helps the agent focus on what matters most, cutting down on wasted time and unnecessary steps. The personalization not only improves productivity but also boosts job satisfaction. The lesson is simple: less is more.

## Meeting user expectations

In the world of business applications, user expectations change drastically. In 2022, Forrester Research suggested that eight out of 10 users are connoisseurs of great user experience. They demand the same level of ease of use from their work tools as they do from their favorite consumer apps. This shift blurs the lines between personal and work tools, driven by advancements in mobile, social, and cloud technologies.

The following image presents the *consumer-grade product experience framework*, which is a decision-making tool for building successful human-centered products.

:::image type="content" source="media/impl-opti-exp-framework.png" alt-text="Screenshot of a slide with four boxes with text that we repeat below the image. On top of the four boxes is a heart shape with the words Customer Love." lightbox="media/impl-opti-exp-framework.png":::

The conceptual framework consists of four main elements:  

- *Enjoyable experience*  

  The experience must be easy to understand and rewarding to use.
- *Enormous value*  

  The experience makes more possible.
- *Easy total experience*  

  Even complex tasks feel effortless.
- *Outstanding design*  

  The design promotes a better way of working.

Dynamics 365 users expect the system to work seamlessly, be designed with their specific roles in mind, and help them perform their tasks efficiently. However, the standard interface can sometimes feel overwhelming, with users reporting that they use less than half of the available features. This makes personalization critical—not just for individual users, but for entire teams and organizations. When ERP software feels more like a burden than a help, it's time to rethink the user experience.

## A new approach to design

At Microsoft, there's a growing emphasis on creating "consumer-grade" experiences for ERP users. This involves simplifying the interface, making it more visually appealing, and ensuring that it's intuitive from the first use. Designing for every possible role, industry, and country7region can be a daunting task, but the goal is to create a base experience that can be easily optimized for specific needs.

A great analogy is that of a skilled craftsperson entering a workshop full of tools. At first glance, the sheer number of tools can be overwhelming, leading to confusion and inefficiency. However, if the tools are arranged specifically for their craft, with the most important ones within easy reach, the experience becomes smoother. The vision for Dynamics 365 is to provide a system where each role feels like the interface was designed just for them.

## Desire paths - how users seek efficiency

A term often used in user experience design is "desire paths"—the shortcuts that users naturally take to make their tasks more efficient. Just as a college student might cut across a grassy area rather than use the sidewalk, users of Dynamics 365 seek out ways to streamline their workflows. Whether it's creating favorite menu items, memorizing keyboard shortcuts, or working with Excel for bulk data entry, desire paths help users get more done in less time.

In ERP systems, encouraging and enabling these desire paths is crucial for maximizing productivity. For instance, users can create personalized views of frequently accessed data, saving them from having to apply filters or search for the same information repeatedly. These shortcuts not only reduce the time spent on tasks but also enhance the overall user experience, making the system feel more responsive to their needs.

## Optimizing for roles and workspaces

One of the most effective ways to personalize Dynamics 365 is by optimizing it for specific roles within the organization. Different roles require different tools, and the solution should reflect these differences. When you provide role-specific workspaces, users can access the most relevant information and actions quickly and easily.

The following two images are screenshots of slides in the presentation to illustrate how you optimize design for a role. This setup is aimed at streamlining user interactions and enhancing productivity by ensuring that a dashboard effectively supports the specific needs and actions associated with different job roles.

:::image type="content" source="media/impl-opti-exp-task.png" alt-text="The image outlines a four step process aimed at improving job-specific workflows. The steps are: Identify jobs to be done - Highlighting the preliminary step of defining tasks required for specific roles. Design a workspace for each job - Illustrating the customization of workspaces tailored to each identified job to enhance efficiency. Create filtered views for each list - Describing the creation of streamlined views that focus on relevant data for each job. Create optimized task views for each form - Depicting the final step of refining the user interface for each task to facilitate easier completion of work. To the right, icons to illustrate different tasks." lightbox="media/impl-opti-exp-task.png":::

:::image type="content" source="media/impl-opti-exp-dashboard.png" alt-text="The image illustrates step 5 in a workflow optimization series that focuses on the customization of a dashboard. It displays a schematic view where a central dashboard, highlighted at the top of the image, feeds information into various task-oriented interfaces. Lines connect the dashboard to each of these task views, symbolizing the flow of information and how the dashboard controls or influences the content and layout of the individual task views." lightbox="media/impl-opti-exp-dashboard.png":::

For example, an accounts payable clerk should see a dashboard with only the workspaces they need, without distractions from other areas of the system. These workspaces should include tiles that give a quick overview of outstanding tasks, such as invoices to be processed or payments to be approved. When organizations tailor the experience to the role, they can improve efficiency and satisfaction, reducing the likelihood of errors and frustration.

## The corporate view and going deeper

A common best practice is to start with a corporate view for frequently used forms across the organization. This baseline experience can then be tailored further for specific departments or roles. The corporate view removes unnecessary fields and actions, providing a streamlined experience for most users. Once the corporate view is established, the next step is to go deeper and optimize for individual roles.

For each role, it's important to identify key tasks and create workspaces that house all the necessary tools to complete those tasks. Users should be able to navigate to these workspaces without having to hunt through menus or switch between different screens. Additionally, filtered views can be created to show only the most relevant data, reducing clutter and making it easier for users to focus on their work.

## Overcoming concerns with personalization

Some organizations might be hesitant to embrace personalization due to concerns about performance, updates, or tech support. However, these concerns are largely myths. The Dynamics 365 apps change the standard experience over time. In Dynamics 365 finance and operations apps, personalizations are stable across updates and don't negatively affect system performance in most cases.

For example, hiding fields or reordering items on a form should have a minimal impact on performance, while the benefits of a cleaner, more intuitive interface far outweigh any minor delays in applying these changes. Additionally, personalizations can be managed centrally, ensuring that tech support teams can easily revert to standard views when troubleshooting issues.

## Conclusion

The future of ERP lies in personalization. By optimizing the experience in Dynamics 365  organizations can ensure that users are more efficient, less frustrated, and ultimately more satisfied with their work tools. Whether through role-specific views, personalized workspaces, or encouraging users to create their own shortcuts, the key to success lies in making the system work for the user—not the other way around.

For more information on how to personalize your Dynamics 365 experience, visit the official Microsoft documentation or reach out to Microsoft support for personalized guidance.

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [TechTalk: Implementation approach with agile techniques for Dynamics 365 business solutions](implement-use-agile-techniques.md)  
- [TechTalk: Unified developer experience for Dynamics 365 finance and operations apps and customer engagement apps](unified-developer-experience.md)  
- [TechTalk: Performance test the user interface with JMeter in Dynamics 365 finance and operations apps](finance-operations-ui-performance-test-jmeter.md)  
- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
