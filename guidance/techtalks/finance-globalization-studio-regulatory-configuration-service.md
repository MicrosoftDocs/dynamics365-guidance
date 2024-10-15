---
title: TechTalk Regulatory Configuration Service moved to Globalization Studio workspace
description: Summary of TechTalk video that talks about the move to the Globalization Studio workspace for solutions with Dynamics 365 finance and operations apps
ms.date: 10/15/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Regulatory Configuration Service moved to Globalization Studio workspace

The evolution of enterprise software often involves significant shifts in how services are delivered and managed. One such development is the recent merge of the Regulatory Configuration Service (RCS) into the Globalization Studio workspace in Dynamics 365 Finance. This article delves into the purpose of this merge, its effect on users, and the changes it brings to regulatory and tax functionality. Learn more at [Regulatory Configuration Service merge to the Globalization Studio workspace](/dynamics365/finance/localizations/global/workspace/merge-rcs-to-gsw).  

We based this article on [a TechTalk](https://youtu.be/g7krfDHH_x8) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/DTV042EXT-slide.png" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/g7krfDHH_x8":::

## The purpose of RCS and its integration

RCS, or Regulatory Configuration Service, was a standalone solution for managing globalization functionalities such as electronic reporting, tax calculation, and invoicing services. It was built as a lifecycle management tool for setting up and deploying these services. It also enabled Application Lifecycle Management (ALM) processes, such as publication, storage, and managing custom configurations. However, RCS required separate deployment and maintenance, often adding complexity to solutions with Dynamics 365 finance and operations apps. As a result, users had to manage two distinct environments, switching between them to validate and deploy configurations.

The primary goal of merging RCS into the Globalization Studio workspace is to simplify this process. With the merge, all the necessary globalization functionalities are now directly available within the Finance instance, eliminating the need for a separate RCS environment. Users can now deploy, configure, and validate globalization features like tax calculation or electronic invoicing directly within a unified workspace. This integration streamlines the setup, validation, and deployment processes, making it easier for users to manage their regulatory configurations without the need to toggle between systems. Learn more at [Regulatory Configuration Service merge to the Globalization Studio workspace](/dynamics365/finance/localizations/global/workspace/merge-rcs-to-gsw).  

The following image compares the experiences with Regulatory Configuration Service and Dynamics 365 Finance, respectively, regarding electronic invoicing.

:::image type="content" source="media/DTV042EXT-changes-electronic-invoicing.png" alt-text="Image with a flowchart layout with two main columns labeled RCS and Dynamics 365. Each column lists related components such as service environments, users, number sequences, Key Vault parameters, and globalization features for RCS, and electronic documents, features, electronic invoicing, and integration channels for Dynamics 365." lightbox="media/DTV042EXT-changes-electronic-invoicing.png":::

## Key changes

### Simplified deployment and user experience

One of the major improvements with the RCS merge is the simplification of deployment. Previously, organizations had to deploy the RCS instance separately from Finance, configure it, and ensure that the environments were correctly linked. Now, with RCS integrated into the Globalization Studio workspace, the entire deployment process occurs within the Finance environment. This shift makes it easier for both Microsoft and users to deploy globalization features and reduces the number of steps required to validate configurations.

Learn more about how to migrate RCS configurations to Dynamics 365 Finance at [Regulatory Configuration Service merge to the Globalization Studio workspace](/dynamics365/finance/localizations/global/workspace/merge-rcs-to-gsw) and the related articles.

Additionally, the merge brings improvements to the user interface. Previously, users needed to know how to connect to Dynamics 365 from RCS, and full testing required switching back and forth between the two. Now, with a single Finance environment, users can perform end-to-end setup and validation directly in the Globalization Studio workspace.

### Improved geographic coverage

Before the merge, RCS didn't support all regions where Finance was deployed, creating gaps in globalization coverage. The merge into the Globalization Studio workspace resolves this issue. Now, all regions supported by Dynamics 365 Finance are also covered by the globalization functionalities, enabling users across the globe to use the power of this unified platform.

### ALM alignment with Power Platform

Another significant change involves the Application Lifecycle Management (ALM) framework. The new Globalization Studio workspace aligns with Microsoft's Power Platform, marking a shift toward a "One Dynamics, One Platform" approach. By transitioning the ALM story to Dataverse solutions, users can now manage their globalization configurations and lifecycle management within the same platform used for other Finance functionalities.

For those familiar with the Global Repository, this merge replaces the Global APO approach with Dataverse solutions, providing a consistent and streamlined way to manage ALM across the entire platform. This transition allows Finance customers and partners to take full advantage of the capabilities offered by the Power Platform while simplifying the overall management process.

## Impact on specific features

### Tax Calculation Service

The merge brings similar changes to the Tax Calculation Service (TCS). While the user experience for configuring tax features remains largely unchanged, the installation process is simpler. The requirement to install the TCS extension no longer exists, and the setup process now allows for easier deployment of master data lookups, which previously required multiple steps.

### Electronic reporting and invoicing

One of the biggest concerns users had with this merge was the potential impact on electronic reporting and business document management functionalities. However, there's no change to the electronic reporting runtime or designers, ensuring a smooth transition for users who rely on these tools. The only changes relate to ALM and RCS-related scenarios, with the migration of functionalities into the Globalization Studio workspace.

### Transition timeline

The rollout of the RCS merge was part of the public preview for version 10.0.39, with a full migration later in 2024. While new RCS instances will no longer be provisioned after this date, existing instances will continue to function, giving customers time to migrate their data using tools and services provided by Microsoft. Although this timeline might seem tight, Microsoft assured our customers that exceptions can be made based on business needs, allowing for support requests where necessary.

## Future globalization management

The merge of RCS into the Globalization Studio workspace represents a major step toward simplifying the management of regulatory configurations within Dynamics 365. By consolidating these features into a single environment, Microsoft is making it easier for users to deploy and manage globalization functionalities while taking full advantage of the capabilities offered by the Power Platform.

As this transition continues, Microsoft continues to listen to user feedback and provide tools to ensure a smooth migration. Learn more about the RCS merge at [Regulatory Configuration Service merge to the Globalization Studio workspace](/dynamics365/finance/localizations/global/workspace/merge-rcs-to-gsw).

In conclusion, the merge of RCS into the Globalization Studio workspace offers a unified approach to managing globalization features in Dynamics 365, reducing deployment complexity, and aligning ALM with the Power Platform. With this integration, users can expect a more streamlined experience that simplifies the deployment, validation, and management of regulatory configurations.

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [Regulatory Configuration Service merge to the Globalization Studio workspace](/dynamics365/finance/localizations/global/workspace/merge-rcs-to-gsw)  
- [Globalization Studio overview](/dynamics365/finance/localizations/global/globalization-studio-overview)  
- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
