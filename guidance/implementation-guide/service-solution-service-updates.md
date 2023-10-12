---
title: Service updates for Dynamics 365
description: Understand how major and minor releases and updates work for Dynamics 365. Learn the importance of best practice for readiness for new versions and updates
author: taksatoms
ms.author: tsato
ms.date: 10/02/2023
ms.topic: conceptual

---

# Service updates

To enable businesses everywhere to accelerate their digital transformation, Microsoft continuously enhances Dynamics 365 with new capabilities. We add product enhancements and performance improvements at a rapid pace. This article provides tips to help you keep your computing environment current in a consistent, predictable, and seamless manner.  

Service updates are continuous, touchless updates that provide new features and functionality. They eliminate the need to do expensive upgrades every few years. The service updates maintain backward compatibility, and contain application and platform changes that are critical improvements to the service, including regulatory updates.

## Microsoft's push to One Version

One of the benefits of Dynamics 365 is that every customer runs on the same version of the service. With market demand for increased agility to gain incremental benefits of these cloud offerings at reduced operating expense costs, Dynamics 365 took a bold step to refrain from multiple releases. Now every security patch, bug fix, performance enhancement, and functional improvement accrue to all implementations across the globe.

We call it One Version, also referred to as Run One, a solution that is evergreen in the modern world.

One Version promises to bring predictable release management to these areas:

- Predictable updates with continuous deployment

  - Regularly scheduled intervals for major releases of performance and reliability improvement updates throughout the year

  - Using safe deployment practices and monitoring updates closely for any issues

  - Knowing the cadence up front so you can work it into your project schedule

- Early visibility of upcoming changes

  - Access to release notes well before the release for readiness so you know what the new changes are and the dates to start planning early

  - Visibility into new features and updates for business sponsors that can help their team be trained in new features

- Test new capabilities ahead of time

  - Ability for customers to opt in for early access to the release

  - Fully supported, production-ready updates that can be tested in your sandbox environments

  - Turning on features when you're ready instead of having it forced upon your environment

- Opportunities to advance your knowledge

  - Faster access to new features

  - Ease in sharing ideas and collaborating with the greater community because everyone is on the same version

> [!NOTE]
> Refer to ["Modernizing the way we update Dynamics 365"](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/07/06/modernizing-the-way-we-update-dynamics-365/) by Mo Osborne, Microsoft COO Business Applications, for details on the benefits of continuous deployment.

> [!TIP]
> Review the Servicing, Supporting and Maintaining Dynamics 365 Finance and Operations Apps TechTalk for best practices in servicing your solution.

With One Version, Dynamics 365 addresses the tough challenges faced by customers and partners and reduces common rollout concerns. The solution automatically enhances the predictability of product updates. For example, One Version reduces the effort and capacity needed to test the update. It makes it easier to manage business change and facilitate appropriate adoption.

:::image type="content" source="media/projectchallenges.png" alt-text="Tough Challenges" :::

Although One Version greatly reduces the impact of deployments, the solution owner and the implementation team are still responsible for making sure certain tasks are addressed. These include planning for the update, assigning ownership of the tasks, raising awareness of coming changes, and supporting adoption. We cover these items throughout this section.

## Release readiness

System administrators and others who have signed up for service notifications are alerted about upcoming releases, minor updates, and bug fixes. Being properly prepared is the key to successfully managing your solution. It's not just up to the Dynamics 365 administrator. You need tight coordination between systems administrators, the Dynamics 365 project team that works on the platform, and the business user groups and subject matter experts (SMEs) who are the end users and champions of the system.

These notifications provide the information you need to start your planning: dates of release availability, release notes, and the process to opt in for early access.

### Release notes and feature deprecation

Great planning starts with education and learning when and what is being rolled out. Your notifications explain the upcoming changes with a link to online documentation for more details. This information can help you gauge the impact to your organization so that you can determine when and how to take action.

Administrators are notified of upcoming releases through the message center and by email. Notes for major releases are made available months before availability and provide several key pieces of information. First, the notes list the features in the release, including a description of the feature and the general availability (GA) date. The notes also show if the feature will be available for public preview and early access. This information will help in your readiness tasks.

Let's break down the three types of release dates:

- **Public preview**  

  These capabilities are pre-release features intended to collect early feedback and aren't intended for production use. For planning purposes, these public previews can give you a good idea of what's coming up in the short-term roadmap. Not every feature is available through a public preview.

- **Early access**  

  You can apply these production-ready, fully supported updates and features to your environment prior to the GA date. See more details in the following section about the process of opting in early.

- **General availability**  

  This is the date that these features are deployed to your environment if the administrator hasn't opted in for early access.

Each release wave includes features and functionalities that you can enable for different types of users:

- **Users, automatically**  

  These features include changes to the user experience for users and are enabled automatically.

- **Administrators, makers, or analysts, automatically**  

  These features are meant to be used by administrators, makers, or business analysts. They're enabled automatically.

- **Users by administrators, makers, or analysts**  

  These features must be switched on or configured centrally before users get access to them.

If you choose to opt in, you get features that are typically mandatory changes automatically enabled for users. Each feature in the release notes indicates which category it falls under.

There may also be announcements about deprecated features. Deprecation notices provide a timeline for when the capability goes away. These announcements are equally important because they allow you time to gauge the impact and work with your business sponsor and technical team to address any concerns.

Deprecation of features is an important part of a solution's growth. As business and technology needs evolve, the solution needs to change to keep up with new requirements for security, compliance, and overall modernization. As a result, some features are deprecated and replaced by a better solution.

Deprecated features continue to work and are fully supported until they're officially removed. After removal, the feature or capability no longer works. The deprecation notes provide information on what features are being removed, when it'll happen, why it's happening, and what actions you can take to address the impact. Just as for new features, organizations must plan and prepare well before the removal of features to avoid negative impact from the deprecation.

> [!TIP]
> Refer to the Message center for detailed information on notifications, email preferences, and recipients for service updates.

For finance and operations apps, refer to the [One Version service updates overview](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview?toc=/dynamics365/finance/toc.json) for details on release planning, [release notes](/dynamics365/fin-ops-core/fin-ops/get-started/whats-new-changed), [deprecations](/dynamics365/fin-ops-core/dev-itpro/get-started/removed-deprecated-features-platform-updates), and [release cadence](/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy).

For customer engagement apps and the Power Platform, refer to the [release notes](/dynamics365/release-plans/), [deprecation announcements](/power-platform/important-changes-coming), and [release cadence](/dynamics365/get-started/release-schedule).

### Opt in for early access

At this point, you have the release notification and reviewed the release notes to do an impact assessment. The next step is to work with the project team to test the release with your solution. Some features available through our public preview program may be of interest for your organization.

Microsoft recommends creating a sandbox instance from a backup of your test instances prior to update deployment. The environment should be running your latest solution with enough data for meaningful testing. If you already have automated tests, you can speed up this process by validating that your solution functions as expected. If you need to fix any areas, you can flag them and work them into your project plan.

If your solution has been developed using supported methods for customization, the release in most cases will have little to no effect on it. Scenarios regarding deprecation that weren't addressed previously may surface from testing and need to be fixed.

Another important area to cover for early access is to work with the business sponsors to help them understand the impact to the end users. As part of the release, some updates may impact user experience, such as user interface (UI) navigation changes. Even small differences can have a meaningful impact. Imagine users in a large call center scenario, in which every extra second on a call with a customer can impact their service goals. In such a case, business managers want to make sure that the user group receives proper communication and takes time to provide training if necessary.

After this due diligence, your organization can schedule and apply the new release to the production environment. You should time this task for when it's most convenient to the users and administrators. Your organization can determine the best time to apply the release, when there will be the least amount of disruption to end users, other technical dependencies, and impact to other projects. Don't wait for the release to be automatically applied to your environment.

Microsoft has deliberately planned the release cadence to give you enough time to prepare. Aligning your own internal deployment planning with this schedule allows you to benefit from the new features and bug fixes and make sure that any customizations specific to your environment continue to function as expected. Thorough planning is key so that there are no unexpected results from the updates and you have control of when these releases are applied to your environment.

## Service updates for finance and operations apps

With continuous touchless service updates in finance and operations apps, the system maintains backward-compatibility, so you don't need to merge your code.

### Safe deployment practices

Three new innovations provide additional enablement for the new modern application lifecycle: safe deployment rings, automated regression testing, and the customer Release Validation Program (RVP). In this section, we explain these and how they apply to you.

Deployment rings are a technique used to decrease any risk associated with rollouts for Azure and other Microsoft cloud services managed at global scale.

As Dynamics 365 updates are created each month, they progress through a series of rings, with each ring providing broader exposure and usage and validation through system telemetry.

:::image type="content" source="media/deploymentpracticefno.png" alt-text="Safe Deployment Practice for finance and operations apps" :::

The GA update benefits from extensive Microsoft testing as well as validation through each of the earlier rings.

> [!NOTE]
> Refer to the [Dynamics 365 for Finance and Operations Cloud Application Lifecycle](https://info.microsoft.com/rs/157-GQE-382/images/D365-for-Finance-and-Operations-Cloud-Application-Lifecycle.pdf) for more information.

### Update cadence

Customers are required to take a minimum of two service updates per year, with a maximum of four service updates per year. We deliver service updates in the following months:

- February  
- April  
- July  
- October  

<!-- :::image type="content" source="media/fnoreleasecadence.png" alt-text="Finance and Operations Release Cadence" ::: 
-->
You can choose to pause one consecutive update to accommodate your project schedule.

Pausing a service update can apply to the designated user acceptance testing (UAT) sandbox, the production environment, or both. If the pause window ends, and the customer hasn't self-updated to a supported service update, Microsoft automatically applies the latest update based on the configuration selection available in Lifecycle Services.

System updates follow these guidelines:

- Updates are backward-compatible

- Updates are cumulative

- Customers can configure the update window

- Quality updates containing hotfixes are only released for in-service versions. See [Targeted release schedule](/dynamics365/fin-ops-core/dev-itpro/get-started/public-preview-releases#targeted-release-schedule-dates-subject-to-change) for end of service dates by version.

- System updates contain new features that you can selectively choose to enable

> [!NOTE]
> Update cadence for finance and operations apps microservices can vary based on the state of the microservice. Microservice update information is not currently surfaced in release notes unless there are notable changes that impact the customer experience.

### Release readiness

We strongly recommend that you plan ahead and work the updates into your internal project release cadence. To do so, take the following steps:

- **Step 1: Plan**  

  Have a good understanding of the release schedule and a plan to work this into your application lifecycle management (ALM) strategy. Because you have the option to pause one consecutive update, you can set aside plenty of time for testing, impact analysis, and developing a deployment plan.

- **Step 2: Test**  

  We recommend using a non-production environment such as your UAT instance to opt in early and apply the release. You can configure service updates through Lifecycle Services and specify how and when you receive service updates from Microsoft to your environments. As part of the configuration, define the update environment (production) and an alternate sandbox (UAT). Use <!-- Regression testing refactoring >the Regression Suite Automation Tool (RSAT) --> [automated regression testing solutions](testing-regression-tooling.md) to perform regression testing to identify any issues. Work any fixes into your ALM cycle and deployment plans.

- **Step 3: Deploy**  

  After you define environment and schedule for the service updates through Lifecycle Services, the back-end tools automatically update the system.

## Service updates for customer engagement apps

Dynamics 365 is continually updated to provide valuable functionality, fix any issues, and maintain the overall health of your solution. System administrators receive communications and are alerted to when changes will be made to their environments. Organizations need to plan to enable these service updates in alignment with their internal ALM process.

### Safe deployment practices for customer engagement apps

When rolling out the major and minor releases, Microsoft Dynamics 365 follows a series of progressive, staged deployments across the world to adhere to safe deployment practices. At each stage, feedback is gathered and quality is monitored for continuous improvement.

For example, for customer engagement apps and Power Platform releases and updates, a station-based deployment plan is followed (Figure 20-4).

:::image type="content" source="media/deploymentpracticece.png" alt-text="Deployment plan" :::

After thorough internal integration tests and validations, customer engagement apps and Power Platform updates are rolled out to Station 1. This first release station consists of select customers and production-like environments. This is set up for early validation testing of the service update before it's rolled out to customer production environments. Based on the pass rate of the first release, the service update gets rolled out to the customer environments by Stations 2–6.

Some organizations require instances to be in different regions, which may place them into different stations than that of their primary geographies. Therefore, as the deployment cycle of a new release commences, instances in different stations can be on different versions of the solution. As your project team is developing new features that are consumed into your ALM deployment process, set up a version check for Dynamics 365 and make sure that there is a match so that your project doesn't encounter incompatibility issues. When the version of the source environments matches the destination, you can safely deploy your solutions.

> [!NOTE]
> Check the [latest release of station mapping and their corresponding regions](/dynamics365/released-versions/dynamics-365ce). Release updates to Station 1 through Station 6 follow the dark hours defined for each geography.

### Types of service updates

There are four types of updates:

- **Major release** These happen twice per year in April and October. Major releases offer new capabilities and functionalities. These updates are backward-compatible. New features with changes that might be disruptive to the user experience are turned off by default.

- **Minor service updates** Minor service updates are deployed on a weekly basis, region-by-region. They contain software customization changes that support new features, product improvements, and bug fixes.

- **Planned maintenance** Planned maintenance includes updates and changes to the ser vice to provide increased stability, reliability, and performance.

- **Unplanned maintenance** Applications sometimes encounter unexpected issues that require changes to maintain availability. Microsoft strives to provide as much notification as possible around these events.

### Update cadence

Customers receive two major updates per year, in the April and October GA releases. You can get early access and opt in months before the GA dates. These updates apply to both Power Platform and Dynamics 365 apps. We encourage you to opt in early to test and apply the release. The releases are production-ready and fully supported even when applying prior to the GA date. Activation for major updates is automatic through safe deployment processes for the region where the Dynamics 365 instance resides, on the deployment dates specified for the region.

:::image type="content" source="media/cereleasecadence.png" alt-text="customer engagement apps Release Cadence" :::

> [!TIP]
> Dynamics 365 apps have a different cadence from the major releases. For example, [Dynamics 365 Customer Insights - Journeys](/dynamics365/customer-insights/journeys/whats-new-marketing) has monthly updates. [Apps from ISVs from AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?product=dynamics-365), Microsoft's app marketplace, may also have a different cadence. You should consult with the ISVs for any third-party apps you're using.

### Release readiness

We strongly recommend that organizations work updates into their internal project release cadence. To do so, take the following steps:

- **Step 1: Opt in for early access**  

  Before you apply the changes to existing production or non-production environments (which may disrupt users and developers), we recommend you create a new instance. You can't revert back to the previous version, so all testing should be done on a new instance. Take a copy of the test environment that has your latest solution and data and create a new instance from it. Enable early access to apply the new release capabilities. After you opt in, some features are turned on by default; others may require an administrator to explicitly configure them. The details are documented in the release notes.

- **Step 2: Test**  

  Run regression testing to make sure that the solution continues to function as expected. Early opt-in features are production-ready and fully supported, so if you encounter any errors, you can submit a service request to report and get help with issues. Another important aspect of enabling the early access capabilities is that some UI and navigation changes may impact users. Work with your user group to do a side-by-side comparison between the current and opt-in versions. Use the release notes to identify the areas where UI or navigation changes have been made. Document the change with screenshots to be shared with the users. Depending on the significance of the changes, it may warrant some level of end user training as well as communications out to the group.

- **Step 3: Deploy**  

  When the testing is complete, you can turn the early access features on in other non-production instances. This ensures that new features and customizations by the project team are developed on the upcoming early release solution. You may keep one or more instances without the early access features turned on to support production bug fixes or anything that needs to be deployed prior to enabling the early access features in the production environment. When it's time to deploy your solutions to production, you enable the early access features on the production instance. You should notify business users of the new features (within the product as well as anything custom built by the project team) and any changes to how end users will navigate through the system. Timing the deployment is important. Microsoft doesn't recommend opting in at the same time you have a new project release in the production environment. If you encounter deployment issues, it's easier to troubleshoot when you're not deploying multiple solutions to the environment.

> [!NOTE]
> Refer to the [Dataverse storage capacity](/power-platform/admin/capacity-storage) guidance to understand the impact on your storage allocation for your tenant when creating new instances from a backup.

## Next steps

- Understand the importance to service the solution by reviewing the [overview](service-solution.md)
- Review how to best [monitor the service health](service-solution-monitor-service-health.md) of your Dynamics 365 solution
- Learn about the importance of [environment maintenance](service-solution-environment-maintenance.md)
- Find additional resources to [continue the business application journey](service-solution-continue-the-business-application-journey.md)
- Read the [case study](service-solution-case-study.md) to understand the impact to an organization when servicing the solution is not top of mind
