---
title: TechTalk - Performance improvements for continuous number sequences in Dynamics 365 finance and operations apps
description: Get a summary of a TechTalk video about performance improvements for the continuous number sequence capability in Dynamics 365 finance and operations apps.
ms.date: 11/07/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Performance improvements for continuous number sequences in Dynamics 365 finance and operations apps

The performance of continuous number sequences is a long-standing challenge for users of Dynamics 365, especially in organizations where legal requirements demand gapless numbering of transactions. Historically, the use of continuous number sequences came with performance trade-offs. However, recent updates in Dynamics 365 significantly improve this vital functionality by providing enhanced system performance and improved compliance with regulatory standards.

We based this article on [a TechTalk](https://youtu.be/q-oxbuBcElc) that you can find online in the Dynamics 365 channel on YouTube.

:::image type="content" source="media/finance-operations-continuous-number-sequence-performance-improvements-slide.png" alt-text="Thumbnail of the title slide for the 'Continuous Number Sequence - Performance Improvements' TechTalk presentation." link="https://youtu.be/q-oxbuBcElc":::

> [!NOTE]
> Continuous number sequences are important across business solutions. This TechTalk is about the feature in Dynamics 365 finance and operations apps such as Dynamics 365 Finance and Dynamics 365 Supply Chain Management. It isn't about the similar capability in Dynamics 365 Business Central.

## Overview of continuous number sequences

In Dynamics 365, number sequences are used across various modules to generate unique identifiers for records such as invoices, vouchers, and sales orders. Number sequences can be either continuous or noncontinuous. Continuous number sequences don't allow gaps between numbers. Noncontinuous number sequences *do* allow gaps. Those gaps might be caused by processes such as restarts or system failures.

The following image shows the pages where you define number sequences, including the scope and segments that apply to each new number sequence. Learn more in [Number sequences overview](/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview?context=%2Fdynamics365%2Fcontext%2Ffinance).

:::image type="content" source="media/finance-operations-continuous-number-sequence-performance-improvements-ui.png" alt-text="Screenshot of the interfaces for setting up a number sequence in Dynamics 365 Supply Chain Management, including the Scope field, which is expanded to show the following list of values: Shared, Company, Legal entity, Operating unit, Company and Fiscal calendar period, Legal entity and Fiscal calendar period, and Operating unit type." lightbox="media/finance-operations-continuous-number-sequence-performance-improvements-ui.png":::

One issue with continuous number sequences is related to system performance. Because of the way that the mechanism for continuous numbering works, every transaction that needs a new number demands interaction with the database. The frequent interactions with the database lead to frequent locking, increased resource usage, and system slowdowns, especially in high-volume environments.

## Why use continuous number sequences?

For many businesses, especially in industries that have regulatory oversight, continuous number sequences are mandatory. To comply with legal standards, businesses in regions such as Europe, APAC, and India must ensure that no numbers are skipped in their transaction records. Regardless of whether these companies are public, private, or semipublic, they rely on continuous numbering for financial audits, regulatory filings, and other critical operations.

However, continuous number sequences historically presented significant performance challenges. The system often encountered SQL table locking, blocking, and general slowdowns, especially when it handled high transaction volumes. These issues made it difficult to maintain optimal system performance and still meet compliance requirements.

## Address performance issues

The Dynamics 365 development team recognized the need to improve the performance of continuous number sequences. Therefore, it introduced new features that mitigate many common issues. Recent updates have focused on optimizing database calls and reducing contention on the number sequence tables.

### Key performance optimizations

- **Reduced database calls** – In the past, every number sequence request involved multiple calls to the database. By reducing these calls, the system now minimizes the load on the database. Therefore, processing is faster, and fewer instances of SQL blocking are encountered.
- **Locking optimization** – The system now effectively uses *read past* locks that allow for nonblocking reads of available records. Therefore, operations aren't held up by other concurrent processes. The use of row-level locking during updates further minimizes performance bottlenecks.
- **Prefetching numbers** – One of the most significant improvements is the introduction of prefetching for continuous number sequences. With prefetching, the system can allocate a batch of numbers in advance. Therefore, the need for frequent database access is reduced. The default prefetch value is set to *5*, but you can adjust the value based on the business's volume requirements.

The new continuous number sequence functionality can handle larger transaction volumes without the performance degradation that was experienced in earlier versions of Dynamics 365.

## System changes

In older versions, the process for allocating a continuous number involved multiple SQL calls to retrieve and update the number sequence tables. This approach often resulted in significant locking and blocking, especially in environments that had high transaction volumes. The performance improvements introduced several changes that streamline the allocation process and reduce contention on the database.

Today, Dynamics 365 preallocates a batch of numbers and stores them in memory. Then when a transaction needs a number, it's pulled from this preallocated pool. Therefore, the number of database calls is significantly reduced. If a system crash or restart occurs, the system can track and clean up unused numbers. This behavior ensures that the sequence remains continuous without sacrificing performance.

For a more comprehensive comparison of the original system for number sequences and the current system, watch the TechTalk video.

## Continuous number sequences in action with performance benchmarks

Microsoft conducted extensive benchmarking to measure the performance improvements that the new continuous number sequence features bring. We tested two key areas:

- **General ledger (GL) posting** – When up to a million lines that had continuous number sequences were processed, system performance improved by up to 400% after the new features were enabled. The system handled the load smoothly. No crashes occurred, and processing times were faster. Without the features, the system could not handle the load and experienced frequent crashes.
- **Free text invoice posting** – In [free text invoice posting](/dynamics365/finance/accounts-receivable/free-text-invoice-optimization), the new features brought the performance of continuous number sequences almost to a par with noncontinuous sequences. Therefore, businesses can now achieve the same level of performance but still meet their legal and compliance requirements for gapless numbering.

## Implementation and rollout

The performance improvements for continuous number sequence became available in preview in version 10.0.29 of Dynamics 365. Many organizations adopted the feature and reported significant improvements in system performance and stability. <!--The feature is part of the general release in version 10.0.34, where it can be enabled through the **Feature management** workspace.-->

In version 10.0.36, the feature was turned on by default, so that all users benefit from the optimizations. However, businesses can still disable the feature as necessary through the **Feature management** workspace.

For solutions that use earlier versions of Dynamics 365, such as version 10.0.33, businesses can enable the feature by contacting Microsoft Support and requesting to have the *nonblocking number sequence* flight activated. In this way, they can take advantage of the performance improvements without having to upgrade to the latest version right away.

## Conclusion

Continuous number sequences are a critical requirement for many businesses, but they presented significant performance challenges in Dynamics 365. The new performance improvements that Microsoft introduced address these challenges head-on. They give businesses a way to maintain compliance with legal standards without sacrificing system performance.

Because of the capabilities for preallocating numbers, reducing database contention, and improving system throughput, businesses can now confidently use continuous number sequences in high-volume environments. These improvements represent a significant step forward for Dynamics 365 users. They ensure that a business's system can scale with its operations but still maintain the compliance and accuracy that the business requires.

Learn more about these updates in [Stay current with Dynamics 365 service updates](../implementation-guide/service-solution-service-updates.md).

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
