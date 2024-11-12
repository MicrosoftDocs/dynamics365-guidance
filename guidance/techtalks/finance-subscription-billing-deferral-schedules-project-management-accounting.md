---
title: TechTalk Subscription billing and deferral schedules with project management and accounting
description: Summary of TechTalk video that talks about managing revenue and expense deferrals for subscription billing in Dynamics 365 Finance with the Project management and accounting module.
ms.date: 10/14/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Subscription billing and deferral schedules with project management and accounting

The landscape of project management and accounting evolved dramatically with the integration of subscription billing and deferral schedules. These tools are designed to help businesses efficiently recognize revenue on a periodic basis while managing the complexities of project accounting. In this TechTalk, we explore the essential features and capabilities of subscription billing in Dynamics 365 Finance with the *Project management and accounting* module.

We based this article on [a TechTalk](https://youtu.be/OoHaQ-v23Ks) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/finance-subscription-billing-slide.png" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/OoHaQ-v23Ks":::

## Introduction to subscription billing

*Subscription billing* is the ability to recognize revenue at agreed-upon intervals, often tied to contractual terms between service providers and customers. This model is common in many industries, particularly businesses that offer recurring services or products. Dynamics 365 Finance incorporates this model so that businesses to streamline their revenue recognition processes while integrating it with project management.

The subscription billing module in Dynamics 365 Finance allows organizations to configure billing schedules, deferrals, and revenue recognition tied to project-based activities. These configurations are essential for industries where project management and accounting are crucial, particularly when dealing with customer-funded or grant-funded projects.

## Configurations for subscription billing

To use subscription billing with the *Project management and accounting* module, you must make several configurations, including the following list:

- Billing schedules  
- Deferrals for projects  
- Deferred costs or revenues in a project group  

Projects must typically be classified as time and material or none project types, and funding must come from customers or grants.

Once configured, deferral schedules are used to spread revenue and costs across multiple periods. This way, you have a smooth revenue recognition process aligned with the actual delivery of services or completion of project milestones.

## Real-life scenarios for project billing and deferrals

Let's consider a typical scenario where subscription billing is applied within a project. Imagine a one-year support project with a fixed fee, billed quarterly in advance. Dynamics 365 allows businesses to configure billing schedules for such projects, ensuring that revenue is recognized as services are provided over the course of the year.

The following image is a screenshot from Dynamics 365 Finance and shows the setup of project groups for handling deferred cost and revenue.

:::image type="content" source="media/finance-subscription-billing-set-up-posting-project-groups.png" alt-text="Image shows a page in Dynamics 365 Finance with a list of project groups and the project group T M Defer selected with options for posting costs and revenue  highlighted." lightbox="media/finance-subscription-billing-set-up-posting-project-groups.png":::

This setup is intended for project management and accounting configurations in Dynamics 365. The process involves creating a billing schedule, specifying the billing frequency (in this case, quarterly), and generating invoices automatically at the start of each quarter. Once the billing schedule is in place, businesses can use the invoice generation tool to post invoices automatically. This process links the invoice to the project, ensuring accurate tracking of billing and project progress.

Another scenario involves revenue and cost deferrals. In some projects, installment hours are invoiced to customers, but revenue and costs are deferred. As a result, the business doesn't recognize revenue immediately but spreads it over the life of the project, aligning it with the delivery of services.

For instance, in a prototype phase of an implementation project, hours are tracked and billed, but the corresponding revenue is deferred. Deferral schedules automatically allocate revenue and costs based on the configuration, ensuring proper recognition throughout the project timeline.

## Key features in subscription billing

Subscription billing in Dynamics 365 offers various features that enhance project management and accounting. For example, the ability to set up [billing schedules](/dynamics365/finance/accounts-receivable/sb-billing-schedules) for different types of transactions—project expenses, timesheets, and sales orders. Deferrals can also be customized to fit specific project needs. For example, spreading costs and revenue over equal periods, or adjusting the schedule based on the project's progress.

The following image is a screenshot from Dynamics 365 Finance with the *project billing schedule* interface. Highlighted in red are the actions for adding a new subscription billing to the selected project, and to navigate to all registered subscription billing projects.  

:::image type="content" source="media/finance-subscription-billing-set-up-project-billing schedule.png" alt-text="Image shows a page in Dynamics 365 Finance with a list of projects. In the ribbon at the top of the page, two actions are highlighted with red boxes and the text Subscription billing." lightbox="media/finance-subscription-billing-set-up-project-billing schedule.png":::

Businesses can also benefit from automated invoicing, where sales orders linked to projects are invoiced automatically, reducing manual intervention and errors. The module also integrates seamlessly with existing project management tools, ensuring that both project and financial teams have access to up-to-date information on billing, revenue recognition, and project status.

## The roadmap for subscription billing

The roadmap for subscription billing in Dynamics 365 Finance includes several key enhancements that aim to further streamline revenue recognition and project accounting. For example, *Multiple Element Revenue Allocation* (MERA), which allows for more flexible allocation of revenue across different project components. Learn more at [Set up multiple element revenue allocation](/dynamics365/finance/accounts-receivable/sb-rev-alloc-setup). Additionally, deferrals for stock service items and adjustments from inventory closing and recalculations are also being developed.

The *subscription billing* module continues to get more capabilities, so keep an eye on [the release plans](/dynamics365/release-plans/) to stay on top of what's coming.

## Conclusion

Subscription billing and deferral schedules are essential tools in project management and accounting, particularly for businesses that rely on recurring revenue models or manage long-term projects. By integrating these features into Dynamics 365 Finance, businesses can automate revenue recognition, reduce manual processes, and ensure compliance with accounting standards.

As Dynamics 365 continues to evolve, organizations can look forward to even more advanced features and capabilities in subscription billing and project management, empowering them to handle the complexities of modern project accounting with ease.

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [TechTalk: Migrate to subscription billing from revenue recognition in Dynamics 365 Finance](finance-subscription-billing-migrate.md)  
- [Subscription billing overview](/dynamics365/finance/accounts-receivable/subscription-billing-summary)  
- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
