---
title: TechTalk Migrate to subscription billing from revenue recognition in Dynamics 365 Finance 
description: Summary of TechTalk video that talks about how a business can streamline financial operations by migrating from revenue recognition to subscription billing in Dynamics 365 Finance. 
ms.date: 10/14/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Migrate to subscription billing from revenue recognition in Dynamics 365 Finance

Migrating from traditional *revenue recognition* to *subscription billing* is a crucial step for businesses aiming to streamline financial operations. This process is becoming increasingly essential as businesses adopt more recurring revenue models. Dynamics 365 Finance offers a comprehensive solution that helps manage this transition smoothly by aligning both configurations and entity mappings between these modules.

We based this article on [a TechTalk](https://youtu.be/ISj9xncsfqE) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/finance-subscription-billing-migrate-slide.svg" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/ISj9xncsfqE":::

> [!IMPORTANT]
> The *revenue recognition* module is deprecated in Dynamics 365 Finance and replaced by the *subscription billing* functionality. The shift offers better flexibility and greater accuracy in handling recurring revenue streams, ultimately allowing businesses to align their financials with modern-day service delivery models. Learn more at [Features removed or deprecated in the Finance 10.0.30 release](/dynamics365/finance/get-started/removed-deprecated-features-finance#features-removed-or-deprecated-in-the-finance-10030-release).  

## Why the shift matters

Revenue recognition is a critical function in traditional financial setups, where businesses would allocate revenue based on completed sales. However, with the growing trend of subscription-based services, the approach needs an update. With *subscription billing*, businesses can manage revenue more dynamically, ensuring that revenue is recognized more accurately over time as services are delivered.

The **Revenue recognition convention** determines the dates that are set on the revenue schedule for the invoice. In contrast, with *subscription billing*, the deferral start date is determined based on the **Revenue and expense deferral** parameter, **Default deferral start date**. The following image aims to explain how the start dates for recognizing revenue and deferring expenses are set. The table highlights the flexibility in setting these parameters based on the revenue and expense deferral parameter **Default deferral start date**.

:::image type="content" source="media/finance-subscription-billing-migrate-compare.svg" alt-text="Image shows a table with two columns. The first column lists actual start date, first day of month/period, mid-month split, and end of month/period. The second column shows when deferral can start, including the transaction date, beginning of the current month, rule of 15, and beginning of the next month." lightbox="media/finance-subscription-billing-migrate-compare.svg":::

## Configuration and mapping entities

One of the most crucial aspects of migrating from *revenue recognition* to *subscription billing* is understanding how configurations and entity mappings translate between the two modules. In Dynamics 365 Finance, the mapping process ensures that businesses can continue their operations seamlessly without disrupting ongoing transactions.

The following table maps fields on the **Deferred Line / RevRecDeferredLineEntity** entity that the now deprecated *revenue recognition* module used to fields on the **Subscription billing deferral table / SubBillDeferralScheduleTableEntity** entity that the *subscription billing* module uses.

| Deferred line | Subscription billing deferral table | Notes |
|--|--|--|
|  | Deferral schedule number | Specify the number, or copy the sales order number that was the revenue schedule number in *Revenue recognition*. Each *deferral schedule* must have a unique combination of *schedule number* and *item number*. |
|  | Schedule type | Straight-line or event-based. |
| Revenue schedule description | Description |  |
| Deferred revenue account | Deferral account | The value must match the dimension structure for integrating applications. Empty dimensions must be shown with a delimiter. |
| RevAccount | Recognition Account | The value must match the dimension structure for integrating applications. Empty dimensions must be shown with a delimiter. |
|  | Recognition type | Credit for revenue schedules and debit for consumption. |
| Date of invoice | Date |  |
|  | Start date | The deferral start date. |
|  | End date | The deferral end date. |

For example, the *recognition basis* in the *revenue recognition* module is equivalent to the *deferral template* in *subscription billing*. In both cases, period frequencies and occurrences can be specified, either by month or fiscal period. These settings allow businesses to manage recurring payments and revenue recognition according to their fiscal calendars.

### Parameter control and customization

A key customization option that differentiates the two modules is how revenue is prorated. In *revenue recognition*, the prorated amount can be calculated by the number of days in a month, a feature controlled by the "equal amounts per period" parameter in *subscription billing*. This parameter is useful in *subscription billing*, as it determines whether the prorated amount should vary depending on the number of days in each billing cycle.

In the past, businesses could put revenue schedule lines on hold automatically in *revenue recognition*. With *subscription billing*, deferral schedules can still be placed on hold, but it's done individually rather than as an all-encompassing hold.

## Migration process in practice

When you migrate to *subscription billing*, it's essential that you understand how the deferral schedule works. When you import data from *revenue recognition*, you must carefully manage fields such as **Deferral schedule number** and **Schedule type**. Each deferral schedule is assigned a unique schedule number and item combination, ensuring that businesses can track *revenue recognition* appropriately across multiple products and services.

Businesses can import existing deferral schedules, whether based on straight-line or event-based recognition, ensuring flexibility depending on the type of subscription service offered.

### Deferral templates and proration

An essential aspect of the *subscription billing* setup is the deferral template, which dictates how often revenue is recognized. For example, a business can opt for equal monthly periods over a year, prorated based on the number of days in each month. These setups allow businesses to ensure that *revenue recognition* is aligned with the actual service delivery and customer payments, avoiding discrepancies between earned and unearned revenue.

## Real-world examples of migration

Consider a scenario where a business recognizes $1,500 in revenue over a 12-month period. In the *revenue recognition* module, the revenue would be spread across 12 equal occurrences with an actual start date. *Subscription billing* mirrors this setup through the deferral template, which makes sure that each period reflects equal amounts based on the days in each month.

In another example, a business has a subscription plan where the amounts are recognized based on fiscal periods rather than calendar months. Subscription billing allows this flexibility by using the fiscal period settings in the deferral template. This way, revenue aligns with the business's financial year, whether it operates on a traditional monthly calendar or a custom fiscal calendar.

## Roadmap for the future

Businesses still have time to complete their migration. However, we strongly encourage everyone to move fully to *subscription billing*. The *subscription billing* module continues to get more capabilities, so keep an eye on [the release plans](/dynamics365/release-plans/) to stay on top of what's coming.

## Conclusion

The shift from *revenue recognition* to *subscription billing* in Dynamics 365 isn't just a technical upgrade but a strategic decision that streamlines financial operations in an evolving marketplace. The new module offers better management of recurring revenue, flexibility in deferral schedules, and alignment with modern business models. If your businesses still uses the deprecated *revenue recognition* module, now is the time to plan and move to *subscription billing* before it becomes a mandatory switch.

Transition to *subscription billing*, and your businesses can remain competitive, agile, and aligned with financial best practices that support the recurring revenue model.

For more detailed resources and guidance, visit [Subscription billing overview](/dynamics365/finance/accounts-receivable/subscription-billing-summary). Find more resources in the Microsoft Tech Community.  

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [TechTalk: Subscription billing and deferral schedules with project management and accounting](finance-subscription-billing-deferral-schedules-project-management-accounting.md)  
- [Subscription billing overview](/dynamics365/finance/accounts-receivable/subscription-billing-summary)  
- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)  
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)  
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)  
