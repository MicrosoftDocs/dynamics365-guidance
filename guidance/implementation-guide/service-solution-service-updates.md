---
title: Stay current with Dynamics 365 service updates
description: Learn about the types, cadence, and benefits of service updates for Dynamics 365, and how to plan, test, and deploy them in your environment.
author: taksatoms
ms.author: tsato
ms.date: 01/30/2024
ms.topic: conceptual
ms.custom:
 - ai-seo-date: 01/30/2024
 - ai-gen-docs-bap
 - ai-gen-title
 - ai-gen-desc
content_well_notification: AI-contribution
---

# Stay current with Dynamics 365 service updates

Dynamics 365 is a cloud-based platform that evolves constantly with new features and improvements. To help you take advantage of these enhancements and keep your solution running smoothly, Microsoft provides service updates that you can apply to your environment. This article helps you understand how service updates work for Dynamics 365, and how you can prepare for them in a consistent, predictable, and seamless way.

Service updates are continuous, touchless updates that add new capabilities and fix issues. They don't require costly upgrades every few years. The service updates maintain backward compatibility, and include application and platform changes that are critical for the service, such as regulatory updates.

## The benefits of One Version

One of the advantages of Dynamics 365 is that every customer runs on the same version of the service. This means that you get faster access to new features, improved performance and reliability, and reduced operating expenses. You also avoid the hassle of managing multiple releases or dealing with outdated features.

We call this approach One Version or Run One. It's a solution that's evergreen in the modern world.

One Version offers these benefits:

- Predictable updates with continuous deployment

  - Regular intervals for major releases of performance and reliability improvement updates throughout the year

  - Safe deployment practices and close monitoring of updates for any issues

  - Known cadence up front so that you can work updates into your project schedule

- Early visibility of upcoming changes

  - Access to release notes well before the release for readiness so that you know what the new changes are and the dates to start planning early

  - Visibility into new features and updates for business sponsors that can help their team be trained in new features

- Ability to test new capabilities ahead of time

  - Option to opt in for early access to the release

  - Fully supported, production-ready updates that can be tested in your sandbox environments

  - Control over when to turn on features instead of having them forced on your environment

- Opportunities to advance your knowledge

  - Faster access to new features

  - Ease in sharing ideas and collaborating with the greater community because everyone is on the same version

[Read our blog post about the benefits of continuous deployment](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/07/06/modernizing-the-way-we-update-dynamics-365/).

> [!TIP]
> Watch the Servicing, Supporting, and Maintaining Dynamics 365 Finance and Operations Apps TechTalk for best practices in servicing your solution.

With One Version, Dynamics 365 addresses the common challenges that customers and partners face and reduces the impact of deployments. One Version reduces the effort and capacity needed to test an update. It makes it easier to manage business change and encourage adoption.

However, One Version doesn't mean that you don't have any responsibilities for your solution. You still need to make sure that you plan for the update, assign ownership of the tasks, raise awareness of coming changes, and support adoption. We cover these items throughout this section.

## How to prepare for service updates

System administrators and others who have signed up for service notifications are alerted about upcoming releases, minor updates, and bug fixes. Being properly prepared is the key to successfully managing your solution. It's not just up to the Dynamics 365 administrator. You need tight coordination between systems administrators, the Dynamics 365 project team that works on the platform, and the business user groups and subject matter experts (SMEs) who are the users and champions of the system.

These notifications provide the information you need to start your planning: dates of release availability, release notes, and the process to opt in for early access.

### Release notes and feature deprecation

Great planning starts with education and learning when and what is being rolled out. The notifications explain the upcoming changes and include a link to online documentation for more details. This information can help you assess the impact to your organization so that you can decide when and how to take action.

Administrators are notified of upcoming releases through the message center and by email. Notes for major releases are available months before availability and provide several key pieces of information. First, they list the features in the release, including a description of each one and the general availability (GA) date. They also show if the feature will be available for public preview and early access.

Let's break down the three types of release dates:

- **Public preview**: These are prerelease features that you can try out to give early feedback. They aren't intended for production use. Not every feature is available through a public preview.

- **Early access**: You can apply these production-ready, fully supported updates and features to your environment before the GA date. [Learn how to opt in for early access](#how-to-opt-in-for-early-access).

- **General availability**: This is the date that these features are deployed to your environment if you haven't opted in for early access.

Each release wave includes features and functionalities that you can turn on for different types of users:

- **Users, automatically**: These features include changes to the user experience and are turned on automatically.

- **Administrators, makers, or analysts, automatically**: These features are meant to be used by administrators, makers, or business analysts. They're turned on automatically.

- **Users by administrators, makers, or analysts**: These features must be turned on or configured centrally before users get access to them.

If you choose to opt in, you get features that are typically mandatory changes automatically turned on for users. Each feature in the release notes indicates which category it falls under.

Update notifications might also include announcements about deprecated features. Deprecation notices provide a timeline for when a feature will be removed. These announcements are important because they give you time to assess the impact and work with your business sponsor and technical team to address any concerns.

Deprecation of features is an essential part of a solution's growth. As business and technology needs evolve, the solution needs to change to keep up with new requirements for security, compliance, and modernization. As a result, some features are deprecated and replaced by a better solution.

Deprecated features continue to work and are fully supported until they're officially removed, after which they no longer work. The deprecation notes provide information on what features are being removed, when it will happen, why it's happening, and what actions you can take to mitigate the impact. Just as for new features, you must plan and prepare well before the removal of features to avoid negative effects from the deprecation.

For finance and operations apps, see the [One Version service updates overview](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview?toc=/dynamics365/finance/toc.json) for details on release planning, [release notes](/dynamics365/fin-ops-core/fin-ops/get-started/whats-new-changed), [deprecations](/dynamics365/fin-ops-core/dev-itpro/get-started/removed-deprecated-features-platform-updates), and [release cadence](/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy).

For customer engagement apps and Power Platform, see the [release notes](/dynamics365/release-plans/), [deprecation announcements](/power-platform/important-changes-coming), and [release cadence](/dynamics365/get-started/release-schedule).

### How to opt in for early access

After you get the release notification and review the release notes to assess the impact, the next step is to work with the project team to test the release with your solution.

Microsoft recommends creating a sandbox instance from a backup of your test instances before the update deployment. The environment should run your latest solution with enough data for meaningful testing. If you have automated tests, you can use them to verify that your solution works as expected. If you find any issues, you can mark them and work them into your project plan.

If your solution uses supported methods for customization, the release will likely have little to no effect on it. However, you might encounter some scenarios related to deprecation that need to be fixed.

Another important area to cover for early access is to work with the business sponsors to help them understand the impact on users. Some updates might change the user experience, such as the user interface or navigation. Even small changes can make a big difference. For example, users in a large call center scenario might need every second they can save on a call with a customer. In such a case, business managers want to make sure that the user group gets proper communication and training if needed.

After this due diligence, your organization can schedule and apply the new release to the production environment. You should choose a time that's convenient for the users and administrators. Your organization can decide when to apply the release, when it will cause the least disruption to users, other technical dependencies, and other projects. Don't wait for the release to be applied automatically to your environment.

Microsoft has planned the release cadence carefully to give you enough time to prepare. By aligning your internal deployment planning with this schedule, you can enjoy the new features and bug fixes and ensure that your environment-specific customizations keep working as expected. Thorough planning is essential so that you don't face any surprises from the updates and you have control over when they're applied to your environment.

## Service updates for finance and operations apps

With continuous touchless service updates in finance and operations apps, the system maintains backward-compatibility, so that you don't need to merge your code.

### Safe deployment practices

Three innovations support the new modern application lifecycle: safe deployment rings, automated regression testing, and the customer Release Validation Program (RVP). In this section, we'll explain what they are and how they apply to you.

Deployment rings are a technique that's used to reduce any risk associated with rollouts for Azure and other Microsoft cloud services that are managed at global scale.

As Dynamics 365 updates are created each month, they move through a series of rings. Each ring provides wider exposure and usage and validation through system telemetry, as shown in the following diagram:

:::image type="content" source="media/deploymentpracticefno.png" alt-text="Diagram of deployment rings for Dynamics 365 finance and operations apps updates, from Microsoft Internal to General Availability." lightbox="media/deploymentpracticefno.png":::

The GA update benefits from extensive Microsoft testing and validation through each of the previous rings.

[Learn more about the Dynamics 365 cloud application lifecycle for finance and operations apps](https://info.microsoft.com/rs/157-GQE-382/images/D365-for-Finance-and-Operations-Cloud-Application-Lifecycle.pdf).

### Update cadence for finance and operations apps

Customers must take at least two and up to four service updates per year. We deliver service updates in February, April, July, and October. You can pause one consecutive update to fit your project schedule.

Pausing a service update can apply to the user acceptance testing (UAT) sandbox, the production environment, or both. If the pause window ends, and you haven't updated to a supported service update, Microsoft automatically applies the latest update based on your configuration in Lifecycle Services.

System updates follow these guidelines:

- Updates are backward-compatible and cumulative.
- Customers can set the update window.
- Quality updates with hotfixes are only released for in-service versions. View the [targeted release schedule](/dynamics365/fin-ops-core/dev-itpro/get-started/public-preview-releases#targeted-release-schedule-dates-subject-to-change) for end-of-service dates by version.
- System updates include new features that you can choose to turn on.

The update cadence for finance and operations apps microservices can vary based on the microservice state. Information about microservice updates isn't included in release notes unless they have notable changes that affect the customer experience.

### Release readiness for finance and operations apps

We strongly recommend that you plan ahead and work the updates into your internal project release cadence. To do so, follow these steps:

- **Step 1: Plan**  

  Understand the release schedule and plan to work it into your application lifecycle management (ALM) strategy. Because you can pause one consecutive update, you can set aside enough time for testing, impact analysis, and deployment planning.

- **Step 2: Test**  

  We recommend using a nonproduction environment like your UAT instance to opt in early and apply the release. In Lifecycle Services, you can specify how and when you get service updates from Microsoft to your environments. As part of the configuration, define the update environment (production) and an alternate sandbox (UAT). Use [automated regression testing solutions](testing-regression-tooling.md) to perform regression testing and find any issues. Work any fixes into your ALM cycle and deployment plans.

- **Step 3: Deploy**  

  After you define the environment and schedule for the service updates through Lifecycle Services, the back-end tools automatically update the system.

## Service updates for customer engagement apps

With continuous touchless service updates in customer engagement apps, the system maintains backward-compatibility, so that you don't need to merge your code.

### Safe deployment practices for customer engagement apps

When Microsoft rolls out major and minor releases, Dynamics 365 follows a series of progressive, staged deployments across the world to follow safe deployment practices. At each stage, we collect feedback and check quality for continuous improvement.

For customer engagement apps and Power Platform releases and updates, we use a station-based deployment plan, as shown in the following diagram:

:::image type="content" source="media/deploymentpracticece.png" alt-text="Diagram of deployment stations for customer engagement app and Power Platform updates, from Station 1 to Station 6." lightbox="media/deploymentpracticece.png":::

After thorough internal integration tests and validations, customer engagement apps and Power Platform updates are rolled out to Station 1. This first release station includes select customers and production-like environments. This is set up for early validation testing of the service update before it's rolled out to customer production environments. Based on the pass rate of the first release, the service update is rolled out to the customer environments in Stations 2&ndash;6.

Some organizations need instances to be in different regions, which might put them into different stations than their primary geographies. Therefore, as the deployment cycle of a new release starts, instances in different stations can be on different versions of the solution. As your project team develops new features that are used in your ALM deployment process, set up a version check for Dynamics 365 and make sure that there's a match so that your project doesn't face incompatibility issues. When the version of the source environments matches the destination, you can safely deploy your solutions.

Check the [latest release of station mapping and their corresponding regions](/dynamics365/released-versions/dynamics-365ce). Release updates to Station 1 through Station 6 follow the dark hours defined for each geography.

### Types of service updates

Four types of updates are available for customer engagement apps and Power Platform:

- **Major releases** happen in April and October. They add new capabilities and functionalities and are backward-compatible. New features with changes that might affect the user experience are turned off by default.

- **Minor service updates** are deployed weekly, region by region. They contain software customization changes that support new features, product improvements, and bug fixes.

- **Planned maintenance** includes updates and changes to the service to improve stability, reliability, and performance.

- **Unplanned maintenance** includes updates to fix unexpected issues that require changes to maintain availability. Microsoft tries to provide as much notification as possible for these events.

### Update cadence for customer engagement apps and Power Platform

Customers get two major updates per year, in the April and October GA releases. You can opt in for early access months before the GA dates. These updates apply to both Power Platform and Dynamics 365 apps.

The following diagram shows two release waves, with public preview and early access available two months before the GA date:

:::image type="content" source="media/cereleasecadence.png" alt-text="Diagram showing the release cadence for customer engagement apps and Power Platform updates." lightbox="media/cereleasecadence.png":::

We recommend that you opt in early to test and apply the release. The releases are production-ready and fully supported even before the GA date. Activation for major updates is automatic through safe deployment processes for the region where your Dynamics 365 instance is, on the deployment dates specified for the region.

Some Dynamics 365 apps have a different cadence from the major releases. For example, [Dynamics 365 Customer Insights - Journeys](/dynamics365/customer-insights/journeys/whats-new-marketing) has monthly updates. [Apps from AppSource](https://appsource.microsoft.com/marketplace/apps?product=dynamics-365) might also have a different release cadence. Check with the vendor for any non-Microsoft apps you use.

### Release readiness for customer engagement apps and Power Platform

We strongly recommend that you follow these steps to work updates into your internal project release cadence:

- **Step 1: Opt in for early access**  

  Create a new instance from a copy of your test environment, opt in for early access, and apply the new release capabilities. Some features are on by default. Others need an administrator to configure them. [Learn how creating new instances affects your Dataverse storage capacity](/power-platform/admin/capacity-storage).

- **Step 2: Test**  

  Run regression testing to make sure that the solution works as expected. Early opt-in features are production-ready and fully supported, so if you encounter any errors, you can submit a service request to report them and get help. Compare the current and opt-in versions and document any UI or navigation changes for users.

- **Step 3: Deploy**  

  When your testing is complete, turn on the early access features in other nonproduction instances so that the project team is developing new features and customizations in the early release solution. Keep some instances without the early access features for production bug fixes or urgent deployments. Turn on the early access features in the production instance and notify users of the new features and changes. It's important to time your deployment well. Don't opt in for early access at the same time as a new project release to production.

## Next steps

- Learn about the importance of [environment maintenance](service-solution-environment-maintenance.md)
- Find more resources to [continue your business application journey](service-solution-continue-the-business-application-journey.md)
- Read [the case study](service-solution-case-study.md) to understand how servicing your solution can make a difference for your organization
