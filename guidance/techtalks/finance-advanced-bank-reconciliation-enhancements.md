---
title: TechTalk Advanced bank reconciliation enhancements for Dynamics 365 Finance
description: Summary of TechTalk video that talks about the advanced bank reconciliation capabilities in Dynamics 365 Finance.
ms.date: 10/08/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Advanced bank reconciliation enhancements for Dynamics 365 Finance

In today's fast-paced financial world, businesses need reliable, efficient tools to handle their day-to-day operations. Dynamics 365 Finance offers many features, and the advanced bank reconciliation process now includes significant enhancements. With the latest updates, users can streamline reconciliation tasks, improve matching accuracy, and enhance usability, making bank reconciliation more efficient than ever.

We based this article on [a TechTalk](https://youtu.be/gBdnfxUNcOw) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/DTV039EXT-slide.png" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/0VFeRi_S8r0":::

## Overview of advanced bank reconciliation

The advanced bank reconciliation capabilities in Dynamics 365 Finance covers the end-to-end reconciliation process, designed to reduce manual effort and ensure accuracy. The feature supports multiple bank formats, automatic and manual matching, and allows users to mark reconciliation as complete once all stages are done.

At its core, the process is broken down into four stages:  

1. Import bank statements  
2. Automatic matching  
3. Manual matching  
4. Complete the reconciliation  

Each stage comes with specific tools and enhancements that allow users to handle complex scenarios more effectively.

The following image provides an overview of the advanced bank reconciliation process in Dynamics 365 Finance. It describes the end to end workflow for reconciling bank statements with company records.

:::image type="content" source="media/DTV039EXT-adv-bank-rec-overview.png" alt-text="A screenshot of a slide form the presentation that we explain after the image." lightbox="media/DTV039EXT-adv-bank-rec-overview.png":::

The image visualizes the advanced bank reconciliation process in four main steps:  

- Import bank statements  

  Multiple formats such as MT940 and Camt053 are imported from sources like SharePoint.  
- Automatic matching  

  A process that handles matching and clearing statements.  

- Manual matching  

  A process that involves reviewing results and updating matches.  
- Complete reconciliation  

  A process that includes posting corrections and saving snapshots.

This streamlined approach enhances automation, reduces manual effort, and saves time for cash management clerks.

### Import bank statements

One of the primary features is the ability to import bank statements in various industry-standard formats such as ISO 20022, MT940, and BAI2. With electronic reporting (ER) framework integration, users can easily manage the configuration and setup required for importing data, making the process as seamless as possible. Additionally, the system now supports importing from SharePoint folders, allowing automated imports without manual intervention.

The system also allows for importing multiple bank accounts from a single file, making it possible to manage multiple accounts under one bank efficiently. For businesses handling international transactions, Dynamics 365 Finance provides time zone conversion features, which help ensure consistency across different time zones.

### Automatic matching

Once bank statements are imported, the system runs an automatic matching engine to reconcile transactions. This engine can match bank statements with company transactions using preconfigured matching rules that cover various business scenarios. With the recent updates, Dynamics 365 Finance supports more complex matching scenarios, such as one-to-many, many-to-one, and many-to-many matches.

The following image details three main activities within the automatic bank reconciliation feature of Dynamics 365 Finance. The first panel, **Match with company transactions**, lists the capabilities of matching individual or multiple bank statement lines with company transactions. The second panel, **Post new entries**, describes how to generate different types of journals and manage customer invoices. The third panel, **Clear errors**, explains procedures for clearing reversal transactions in company accounts and bank statements.

:::image type="content" source="media/DTV039EXT-adv-bank-rec-auto-match.png" alt-text="The image shows three boxes with bulleted text for the automatic bank reconciliation feature of Dynamics 365 Finance." lightbox="media/DTV039EXT-adv-bank-rec-auto-match.png":::

The following list contains the text that's show in the image for better accessibility.  

- Match with company transactions  

  - Match one bank statement line with one company transaction  
  - Match M bank statement lines with one company transaction  
  - Match one bank statement line with N company transactions  
  - Match M bank statement lines with N company transactions  

- Post new entries  

  - Generate GL vouchers  
  - Generate customer payment journals  
  - Generate vendor payment journals  
  - Settle open customer invoices  
  - Mark as new  

    - This option isn't available in the **Modern bank reconciliation** feature management is switched on  

- Clear errors  

  - Clear reversal company transactions  
  - Clear reversal statement lines  

For example, a bank statement line can now be matched with multiple company transactions and vice versa, significantly improving the reconciliation process for businesses that deal with a large volume of transactions. Additionally, users can configure custom payment journals directly from the reconciliation worksheet, posting new entries as needed.

### Manual matching and reversals

Despite the robust automatic matching capabilities, there are scenarios where manual intervention is required. The system provides a reconciliation worksheet for users to manually review and match transactions that the system couldn't reconcile automatically. This worksheet is now easier to use, so that users can easily switch between unmatched and matched transactions. It has a more streamlined interface for manual work.

The following image outlines four key areas of matching:  

:::image type="content" source="media/DTV039EXT-adv-bank-rec-manual-match.png" alt-text="Screenshot of slide with four boxes, each with a bulleted list and a screenshot of Dynamics 365 Finance." lightbox="media/DTV039EXT-adv-bank-rec-manual-match.png":::

The following list contains the text that's show in the image for better accessibility.  

- Redesigned reconciliation worksheet  

  - More lines displayed in matched and unmatched transactions  
  - Intuitive statistics for bank reconciliation progress  
  - Bank statement line status  

- Review automatic matching results - Planned  

  - Set up review criteria  
  - Manual review before posting automatic matching results  
  - Update automatic matching results  

- Manual matching  

  - Match with company transactions  
  - Generate payment journals  
  - Settle with customer and vendor invoices  
  - Post GL vouchers  
  - Clear errors

- Reverse matching  

  - Unmatch with company transactions  
  - Reverse voucher  
  - Cancel payment journal - planned  

Furthermore, if errors are made during the matching process, users can easily reverse matches, unposting journals or reversing transactions directly from the worksheet. The latest updates also include the ability to reverse posted payments and correct errors in company transactions without the need for a separate journal entry.

## Enhancing reconciliation with automation

One of the most exciting updates is the integration of advanced automation tools to handle post-reconciliation tasks. For example, businesses that use bridging payments no longer need to manually transfer balances from the interim account to the main bank account. This task is now handled automatically when the reconciliation is marked as complete, improving operational efficiency and reducing the risk of errors.

Another significant improvement is the introduction of the snapshot feature, which locks the reconciliation worksheet once it's marked as complete. This ensures that no new transactions are accidentally added to the completed reconciliation, making it easier to maintain accurate records for auditing purposes.

## New features and roadmap

The enhancements introduced in Dynamics 365 Finance in the 2023 and 2024 release waves represent a major investment in improving the bank reconciliation experience. Some of the key features include support for advanced matching scenarios, the ability to generate general ledger (GL) vouchers directly from the reconciliation process, and automatic posting of customer payments.

In future updates, Microsoft continues to focus on enhancing the cash application process. Planned features include improvements in automatically determining customer accounts, generating custom payment journals, and providing more options for matching invoices and payments. The introduction of AI-powered tools, such as Copilot, aims to assist users in the manual matching process, further increasing operational efficiency.

## Conclusion

The advanced bank reconciliation enhancements for Dynamics 365 Finance represent a significant step forward in improving efficiency and accuracy for businesses. By automating much of the reconciliation process, reducing manual intervention, and offering more robust matching capabilities, businesses can focus on strategic financial decisions rather than administrative tasks.

Learn more in the product documentation for [Dynamics 365 Finance](/dynamics365/finance/). You can also join the Microsoft FastTrack program, where users can get direct support and more resources to maximize their use of Dynamics 365 Finance.

These improvements make Dynamics 365 Finance an even more powerful tool for managing a business's financial operations, ensuring smooth and accurate bank reconciliations with minimal effort.

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)

- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)

- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)

- [Advanced bank reconciliation overview](/dynamics365/finance/cash-bank-management/advanced-bank-reconciliation-overview)  

- [Cash application in advanced bank reconciliation](/dynamics365/finance/cash-bank-management/apply-cash-adv-bank-rec)  

- [Generate a voucher in advanced bank reconciliation](/dynamics365/finance/cash-bank-management/vouchers-adv-bank-rec)  

- [Clear reversal company transactions in advanced bank reconciliation](/dynamics365/finance/cash-bank-management/clear-reverse-comp-trans)  

- [Clear bridging payments using advanced bank reconciliation](/dynamics365/finance/cash-bank-management/clear-bridging-pyts-adv-bank-rec)  
