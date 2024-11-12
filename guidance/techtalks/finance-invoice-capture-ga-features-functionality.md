---
title: TechTalk Invoice capture features and functionality
description: Summary of TechTalk video that talks about the invoice capture capabilities that are generally available in Dynamics 365 Finance.
ms.date: 10/08/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Invoice capture features and functionality

As the digital landscape continues to advance, automation is essential for businesses seeking to enhance operational efficiency. Dynamics 365 Finance offers a powerful solution for invoice capture, allowing organizations to automate their accounts payable (AP) processes and reduce the time and effort required for manual tasks. The general availability (GA) release of invoice capture brings several key enhancements over the preview version, offering robust functionality to optimize invoice processing from end to end.

We based this article on [a TechTalk](https://youtu.be/YEF3NAHnQsU) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/finance-invoice-capture-slide.svg" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/YEF3NAHnQsU":::

## Invoice capture in Dynamics 365 Finance

Invoice capture in Dynamics 365 Finance aims to automate the process of receiving, validating, and processing vendor invoices. This solution enables AP clerks to handle invoices from multiple external sources, such as email, file servers, or SharePoint, in a centralized platform. The current version of invoice capture includes essential features like improved automation, error correction, and vendor account validation.

The following image depicts the invoice automation process flow for accounts payable.  

:::image type="content" source="media/finance-invoice-capture-ap-invoice-automation.svg" alt-text="Screenshot of a slide with three main stages: Capture, Process, and Pay." lightbox="media/finance-invoice-capture-ap-invoice-automation.svg":::

In the *Capture* stage, invoices can be received through electronic means, manual input, batch import, or invoice capture. The *Process* stage involves tasks such as applying prepayment, receipt matching, invoice validation, workflow approval, and posting. Finally, the *Pay* stage ends with a proposal for automatic payment. Channels for receiving invoices include file servers, email (Microsoft 365 Outlook), and APIs.  

Historically, invoice processing was a tedious and time-consuming task for AP teams. Invoices were often captured manually, entered into an business solution, validated through a three-way matching process (invoice, purchase order, and product receipt), and then approved or posted. This manual workflow significantly increased the workload for AP clerks. With Microsoft's invoice capture solution, businesses now have an end-to-end automated process that saves both time and resources, allowing AP clerks to focus on more strategic tasks.

## Key features of the GA release

The GA release of Dynamics 365's invoice capture solution introduces several enhancements that address both usability and functionality. One of the most notable improvements is the ability to handle paper invoices, with plans to support electronic invoices (E-invoices) later. The roadmap for invoice capture includes expanding the solution's capabilities to capture all types of invoices, ensuring they're processed in a central location.

The following image outlines the process of invoice processing with the invoice capture capability in detail, highlighting both touchless and manual intervention workflows.

:::image type="content" source="media/finance-invoice-capture-process-invoice.svg" alt-text="Screenshot of a slide with arrows to indicate a flow." lightbox="media/finance-invoice-capture-process-invoice.svg":::

The flow begins with an invoice being captured and classified. The *touchless* process involves *derivation* that determines details such as the legal entity, vendor account, invoice type, stock item, service item, procurement category, currency code, and purchase order. It also includes *validation*, meaning checking the required fields  to make sure there are no confidence score errors, validating the currency code, and checking for consistency with the purchase order. If manual intervention is required, the invoice is reviewed and corrected before being finalized. Once complete, the invoice is transferred asynchronously or synchronized for further processing.

The solution relies on Microsoft's AI Builder technology for optical character recognition (OCR) to automatically capture and process invoice data. By using pre-built AI models, which require no training from the user, the system accurately recognizes and extracts information from invoices. After capturing the invoice, the system applies validation and derivation logic, ensuring that the appropriate legal entity and vendor account are associated with each invoice. If discrepancies occur, a user-friendly "side-by-side" viewer interface allows AP clerks to quickly review and correct the information.

Once the data is validated, the invoice is transferred to the F&O system, where businesses can choose to process it using one of two frameworks: the vendor invoice or the invoice journal. This flexibility allows companies to tailor the process according to their specific requirements.

## Automation and touchless processing

The GA release also introduces enhanced automation features. One of the core improvements is the system's ability to automate prepayment applications, receipt matching, validation workflows, and auto-posting. When an invoice is received, the solution automatically processes it using batch jobs running in the background, which significantly reduces manual intervention.

In addition to automation, the invoice capture solution offers *touchless* processing. That means that once an invoice passes validation, it can be automatically posted without the need for manual review. For invoices that contain errors or need further validation, the *touchless* process can be overridden, and AP clerks can use the side-by-side viewer to make necessary adjustments.

Another crucial feature of the GA release is the ability to automatically generate payment proposals. Once an invoice is successfully posted, the payment journal is created automatically, further streamlining the AP process and reducing manual effort.

## User interface and experience

The side-by-side viewer interface is one of the standout features in the GA release. This modern interface allows users to view the original invoice document on one side and the extracted data on the other. AP clerks can easily zoom in, rotate, or highlight specific fields within the invoice, ensuring accuracy and completeness during the review process.

Additionally, the viewer includes real-time error notifications and warnings, providing a comprehensive overview of any issues that may need to be addressed. The system also incorporates continuous learning capabilities, allowing it to "remember" previous corrections and apply them to future invoices. This continuous learning reduces the need for repetitive manual corrections, increasing the overall touchless processing rate over time.

## Deployment and configuration

Deploying the invoice capture solution in Dynamics 365 is straightforward, but there are some prerequisites. First, businesses must ensure that their version of Finance meets specific requirements and that their environment is integrated with the Power Platform. The invoice capture solution is available for installation through AppSource, and once installed, users can begin configuring it to meet their business needs.

The following image illustrates requirements for deployment and configuration, specifically for preparing environments in Dynamics 365 Finance and the integration with Power Platform.

:::image type="content" source="media/finance-invoice-capture-deploy-config.svg" alt-text="Screenshot of a slide with two screenshots that show the versions of finance and operations apps and how the configuration looks in Power Platform admin center." lightbox="media/finance-invoice-capture-deploy-config.svg":::

The configuration process includes defining legal entities, vendor synchronization settings, and framework mappings for invoice posting. Users can also create custom channels to receive invoices from different sources and assign legal entities to each channel. Additionally, the GA release introduces options for managing attachments and filtering nonrelevant documents, further optimizing the invoice capture process.

## Roadmap and future enhancements

Microsoft continues to invest in the development of its invoice capture solution, with several significant features planned for future releases. One of the most anticipated updates is the integration of custom AI models, allowing businesses to train the system to recognize and process complex invoice layouts. This feature enhances the OCR capabilities of the solution, making it even more versatile for handling various invoice formats.

Another key feature on the roadmap is support for financial dimensions on cost invoices. Financial dimensions are critical for accurate expenditure tracking and approval workflows, and their inclusion significantly increases the touchless processing rate for cost invoices. Additionally, Microsoft plans to introduce support for E-invoices, QR code scanning, and other advanced customization options.

## Conclusion

The GA release of invoice capture for Dynamics 365 Finance offers businesses a comprehensive solution to automate their AP processes. By using AI-driven automation, user-friendly interfaces, and seamless integration with the Power Platform, invoice capture streamlines the procurement-to-pay process, saving time and reducing the burden on AP teams. As Microsoft continues to enhance the solution with new features and functionalities, businesses can expect even greater efficiency and scalability in their finance operations.

For more information on the invoice capture solution and pricing, visit [Microsoft Dynamics 365 Pricing Guide](https://dynamics.microsoft.com/pricing/).

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [Invoice capture solution - Finance](/dynamics365/finance/accounts-payable/invoice-capture-overview)  
- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
