---
title: TechTalk Performance improvements for continuous number sequences
description: Summary of TechTalk video that talks about the performance improvements for the continuous number sequences capability in Dynamics 365 finance and operations apps.
ms.date: 11/07/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Performance improvements for continuous number sequences in Dynamics 365 finance and operations apps

The performance of continuous number sequences is a long-standing challenge for users of Dynamics 365, especially in organizations with legal requirements that demand gapless numbering in transactions. Historically, using continuous number sequences came with performance trade-offs. However, recent updates in Dynamics 365 offer significant improvements to this vital functionality, providing enhanced system performance and improved compliance with regulatory standards.

We based this article on [a TechTalk](https://youtu.be/q-oxbuBcElc) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/finance-operations-continuous-number-sequence-performance-improvements-slide.png" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/q-oxbuBcElc":::

> [!TIP]
> Continuous number sequences are important across business solutions. This TechTalk is about the feature in finance and operations apps such as Dynamics 365 Finance or Dynamics 365 Supply Chain Management. It's not about the similar capability in Dynamics 365 Business Central.

## Understand continuous number sequences

In Dynamics 365, number sequences are used across various modules for generating unique identifiers for different records like invoices, vouchers, and sales orders. These sequences can either be continuous or not continuous. Continuous sequences don't allow gaps between numbers. Number sequences that are *not* continuous allow gaps due to processes like restarts or system failures.

The following image shows the pages where you define number sequences, include the scope and segments that apply to the new number sequence. Learn more at [Number sequences overview](/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview?context=%2Fdynamics365%2Fcontext%2Ffinance).  

:::image type="content" source="media/finance-operations-continuous-number-sequence-performance-improvements-ui.png" alt-text="Screenshot of the interfaces for setting up a number sequence in Supply Chain Management with many fields, including the Scope field that's expanded to show the list of parameter values: Shared, Company, Legal entity, Operating unit, Company and Fiscal calendar period, Legal entity and Fiscal calendar period, and Operating unit type." lightbox="media/finance-operations-continuous-number-sequence-performance-improvements-ui.png":::

One issue with continuous number sequences is related to system performance. The mechanism for continuous numbering means that every transaction that requires a new number demands interaction with the database. These frequent interactions with the database lead to frequent locking, increased resource usage, and system slowdowns—especially in high-volume environments.

## Why continuous number sequences?

For many businesses, especially in industries with regulatory oversight, continuous number sequences are mandatory. In regions like Europe, APAC, and India, businesses must ensure that no numbers are skipped in their transaction records to comply with legal standards. These companies, whether public, private, or semi-public, rely on continuous numbering for financial audits, regulatory filings, and other critical operations.

However, continuous number sequences historically presented significant performance challenges. The system often encounters SQL table locking, blocking, and general slowdowns, particularly when handling high transaction volumes. These issues make it difficult to maintain optimal system performance while meeting compliance requirements.

## Address performance issues

The Dynamics 365 development team recognized the need to improve the performance of continuous number sequences and introduced new features that mitigate many of the common issues. Recent updates have focused on optimizing database calls and reducing contention on the number sequence tables.

### Key performance optimizations

- Reduced database calls  

  In the past, every number sequence request involved multiple calls to the database. By reducing these calls, the system now minimizes the load on the database, allowing for faster processing and fewer instances of SQL blocking.

- Locking optimization  

  The system now effectively uses *read past* locks that allow for nonblocking reads of available records. This way,  operations aren't held up by other concurrent processes. The use of row-level locking during updates also minimizes performance bottlenecks further.

- Prefetching numbers  

  One of the most significant improvements is the introduction of prefetching for continuous number sequences. Prefetching allows the system to allocate a batch of numbers in advance, reducing the need for frequent database access. The default prefetch value is set to 5, but you can adjust the value based on the business's volume requirements.

The new continuous number sequence functionality can handle larger transaction volumes without the performance degradation experienced in earlier versions of Dynamics 365.

## System changes

In older versions, the process for allocating a continuous number involved multiple SQL calls to retrieve and update the number sequence tables. This approach often resulted in significant locking and blocking, especially in environments with high transaction volumes. The performance improvements introduced several changes that streamline the allocation process and reduce contention on the database.

Today, Dynamics 365 preallocates a batch of numbers and stores them in memory. When a transaction needs a number, it pulls from this preallocated pool, significantly reducing the number of database calls. If a system crash or restart occurs, the system can track and clean up unused numbers, ensuring that the sequence remains continuous without sacrificing performance.

Watch the recording of the TechTalk for a more comprehensive comparison of the original system for number sequences and the current system.

## Continuous number sequences in action with performance benchmarks

Microsoft conducted extensive benchmarking to measure the performance improvements brought about by the new continuous number sequence features. We tested two key areas:  

- General ledger (GL) posting  

  When processing up to a million lines with continuous number sequences, the system performance improved by up to 400% after enabling the new features. Without the feature, the system couldn't handle the load and experienced frequent crashes. Once the new capability was switched on, the system handled the load smoothly, with no crashes and faster processing times.
- Free text invoice posting

  In [Free Text Invoice posting](/dynamics365/finance/accounts-receivable/free-text-invoice-optimization), the new feature brought the performance of continuous number sequences almost on par with noncontinuous sequences. This means businesses can now achieve the same level of performance while meeting their legal and compliance requirements for gapless numbering.

## Implementation and rollout

The continuous number sequence performance improvements became available in preview in version 10.0.29 of Dynamics 365. Many organizations adopted the feature and reported significant improvements in system performance and stability. <!--The feature is part of the general release in version 10.0.34, where it can be enabled through the **Feature management** workspace.-->

The feature was turned on by default in version 10.0.36 so that all users benefit from these optimizations. However, businesses can still choose to disable the feature if necessary through the **Feature management** workspace.

For solutions with earlier versions of Dynamics 365, such as 10.0.33, the feature can be enabled by reaching out to Microsoft support. Businesses can request the *nonblocking number sequence* flight to be activated, allowing them to take advantage of these performance improvements without upgrading to the latest version immediately.

## Conclusion

Continuous number sequences are a critical requirement for many businesses, but they came with significant performance challenges in Dynamics 365. The new performance improvements introduced by Microsoft address these challenges head-on, offering businesses a way to maintain compliance with legal standards without sacrificing system performance.

With the ability to preallocate numbers, reduce database contention, and improve system throughput, businesses can now confidently use continuous number sequences in high-volume environments. These improvements represent a significant step forward for Dynamics 365 users, ensuring that their systems can scale with their operations while maintaining the compliance and accuracy they require.

Learn more about these updates at [Stay current with Dynamics 365 service updates](../implementation-guide/service-solution-service-updates.md).  

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [Number sequences overview](/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview?context=%2Fdynamics365%2Fcontext%2Ffinance)
- [Numbering documents and vouchers chronologically](/dynamics365/finance/accounts-receivable/chrono-numbers)  
- [Feature management overview](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview?context=%2Fdynamics365%2Fcontext%2Ffinance)  
- [Create number series in Dynamics 365 Business Central](/dynamics365/business-central/ui-create-number-series)  
- [Stay current with Dynamics 365 service updates](../implementation-guide/service-solution-service-updates.md)  
- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
