---
title: Dynamics 365 guidance documentation overview
description: Get an introduction to the types of guidance content, best practices, and recommendations Microsoft publishes for Dynamics 365.
author: edupont04
ms.author: edupont
ms.topic: overview
ms.date: 05/11/2026
---

# What is Dynamics 365 guidance?

Welcome to the various types of implementation guidance that Microsoft provides for Dynamics 365. Get an overview of already published content at [Dynamics 365 guidance documentation](index.yml), and submit new content here.

## Overview

In this section, you get an overview of what Microsoft means by the term *guidance*. At Microsoft, the term *guidance* refers to design patterns, reference architectures, deployment diagrams, and other recommended approaches to implement Microsoft services in an organization. Solution architects, administrators, functional consultants, and many more use the content to start conversations or implementations. For Dynamics 365, the guidance includes end-to-end business process descriptions, and best practices for how to configure and set up Dynamics 365 for an organization.

Microsoft believes that every business is in the business of creating great customer experiences. To achieve that goal, business applications must do more than just run your back office, marketing, supply chain, or even field operations as discrete entities. Businesses don't just implement technology solutions, they implement business applications to solve real-life business problems. These investments often come with an expectation of a return on investment, a reduction in total cost of ownership, or another perceived and measurable business objective. The [end-to-end business processes](#end-to-end-business-processes) content helps guide your implementation to success faster and easier.

Find related content at [Power Platform guidance documentation](/power-platform/guidance/) and the [Azure Architecture Center](/azure/architecture/). Also, the [Microsoft Cloud Adoption Framework for Azure](/azure/cloud-adoption-framework/) contains proven guidance and best practices that help you confidently adopt the cloud and achieve business outcomes.

## End-to-end business processes

Dynamics 365 is a suite of applications that help organizations meet their goals by aligning with a variety of business processes focused on specific industries. [!INCLUDE [daf-business-process-def](~/../shared-content/shared/guidance-includes/daf-business-process-def.md)] In these articles, flowcharts illustrate the sequence of steps. Learn more at [About the business process guide](business-processes/about.md).  

The business process content is structured into six levels:

- *End-to-end processes*

  This level represents the complete flow of activities from the initial trigger to the final outcome.
- *Areas*

  This level represents a significant grouping of related activities that contribute to the overall objective.
- *Business processes*

  This level represents specific sets of activities or tasks that accomplish a particular business function within a business process area.
- *Scenarios*

  This level is for unique ways of carrying out a specific business process, often tailored to different scenarios, industries, or requirements.
- *System processes*

  This level is for portions of a business process that use a specific form, page, or UI element in Dynamics 365.  
- *Test cases*

  This level is for a detailed set of conditions and steps you use to determine whether a software application or system functions correctly.

Learn more at [Overview of the business process catalog levels](business-processes/about-catalog-levels.md). [Learn how to contribute to this library](/dynamics365/get-started/contribute#business-process-contributions).

## Implementation guide

This section contains conceptual guidance for how to implement solutions that include Dynamics 365. The original *Dynamics 365 Implementation Guide* introduced the term *Success by Design* with four stages. But the guide now includes an earlier stage to the list so that there are five stages:

- *Discover*

  In this stage, the project team is in discovery mode, gathering and validating business requirements, and finalizing the high-level solution approach.
- *Initiate*

  In this stage, the project team defines all in-scope workstreams and updates the project plan to reflect these workstreams.
- *Implement*

  In this stage, the project team focuses on building the solution per the agreed upon solution design and scope.
- *Prepare*

  In this stage, the project team prepares for the final round of user acceptance testing (UAT) and training.
- *Operate*

  In this stage, the focus is on stabilization and a shift in focus towards functionality and enhancements that are earmarked for the next phase of the project.

Learn more at [Introduction to Dynamics 365 Implementation Guide](implementation-guide/introduction.md).

## Implementation tools and samples

This section provides an overview of the resources in the [Dynamics-365-FastTrack-Implementation-Assets](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/) GitHub repo. The tools and scripts are sorted by the Dynamics 365 apps that they support, or the technology or concept that they apply to.

Learn more at [What are the implementation tools and samples?](resources/overview.md).

<!--
## Architecture guide

In this section, you learn how understanding your needs and having a vision are the most important first steps in building the right solution. By using solution architecture design pillars, you can identify those needs and the elements essential to creating a blueprint of your solution.-->

## Guidance for software development companies

This section provides an overview of content that's relevant for software development companies that want to build solutions with Dynamics 365 and Power Platform. Learn more at [Tools and resources for software development companies](isv/index.yml).

## Administration guide

This section provides best practices for ongoing administrative tasks, such as data management, reporting and business intelligence, servicing the solution, and other aspects of administrative tasks. Learn more at [What is the administration guide?](implementation-guide/admin-guide-overview.md)

## Patterns

This section is still growing. It includes configuration patterns as part of the business process catalog. Patterns are configurations that admins and consultants use repeatedly to bring Dynamics 365 solutions to life. [Learn how to contribute to this library](/dynamics365/get-started/contribute#dynamics-365-guidance-content).

## Reference architectures

We're gradually building a library of reference architectures to help implementers get deployments and integrations right. We welcome architectures that solution architects get approved as part of the [FastTrack Recognized Solution Architect](fasttrack/instruction-guide-fasttrack-recognized-solution-architect.md) nomination. [Learn how to contribute to this library](/dynamics365/get-started/contribute#dynamics-365-guidance-content).

## Security and compliance

This section promotes a chapter from the implementation guide and adds more links to best practices for security and compliance. Learn more at [Secure your Dynamics 365 data and apps](implementation-guide/security.md).

## Migration from on-premises to online

In this section, you find information about the migration tools from Microsoft that can help organizations move to the cloud. Learn more at [Migrate to Dynamics 365 online from Dynamics on-premises products](migrate/overview.md).

## Development guides

This section provides an overview of design principles that you want to apply if you customize or extend the customer engagement apps. Learn more at [UI/UX Design for Dynamics 365](develop/introduction-customer-engagement-ui-ux-design-guide.md).    

## FastTrack

Microsoft FastTrack for Dynamics 365 is a customer success service that helps partners' customers implement and go live so they can realize business value faster. It's an onboarding program run by the product engineering team that offers best practices, tools, resources, and expert advice. The customer gains valuable insights with solution implementation, onboarding, and continued education. Learn more at [What is FastTrack for Dynamics 365?](fasttrack/overview.md)

## TechTalks

This section gives you easy access to video recordings of TechTalks that provide technical depth, best practices, and detailed knowledge that's specific to the relevant subject areas. Learn more at [What are the Dynamics 365 TechTalk videos?](roles/techtalk-videos.md)

## Product documentation

Wherever you are in the guidance content, the navigation panel shows links to the core docs for each Dynamics 365 app or service. You can also find these links on the [Dynamic 365 documentation hub page](/dynamics365/index).

## Get notified about changes through an RSS feed

[!INCLUDE [daf-rss](includes/daf-rss.md)]

## Tell us what you think

[!INCLUDE [feedback-docs](includes/feedback-docs.md)]

## Contribute

Our content is available as Markdown and YAML files in [a public GitHub repo](https://github.com/MicrosoftDocs/dynamics365-guidance). A benefit of GitHub is the ability for you to contribute to the content that the Microsoft team provides. Good advice and best practices are published in the [Microsoft Learn contributor guide](/contribute/). Learn more at [Contribute to Microsoft content for Dynamics 365](/dynamics365/get-started/contribute).

## Related information

[Overview of roles in Dynamics 365](roles/overview.md)  
[Available certifications for different roles in Dynamics 365](roles/certifications.md)  
[Dynamics 365 guidance documentation](index.yml)  
[Find your way in Dynamics 365](/dynamics365/get-started/navigate)  
[Microsoft Dynamics 365 documentation](/dynamics365/index)
