---
title: Go-live checklist
description: Learn how to use the go-live checklist to verify interactions between all parts of your Microsoft Dynamics 365 solution and implement with confidence.
ms.date: 06/06/2023
ms.topic: conceptual
author: vaniusca
ms.author: vaniaf
ms.custom:
 - ai-gen-docs-bap
 - ai-gen-desc
 - ai-seo-date:08/22/2023
 - bap-template
---

# Go-live checklist

The go-live checklist is a list of the requirements that a Dynamics 365 implementation project needs to meet before it launches. It includes mandatory activities and recommended practices. Use it both to help your organization prepare for implementation and to assess the readiness of your solution to go live.

In this article, we discuss in depth the main subjects in the go-live checklist:

- [Go-live readiness](#go-live-readiness)
- [Cutover](#cutover)
- [Solution scope review](#solution-scope-review)
- [Solution acceptance review](#solution-acceptance-review)
- [UAT completion](#user-acceptance-test-completion)
- [Performance testing completion](#performance-testing-completion)
- [SIT completion](#system-integration-testing-completion)
- [Data migration readiness and validation](#data-migration-readiness-and-validation)
- [Confirmation of external dependencies](#confirmation-of-external-dependencies)
- [Change management for initial operations readiness](#change-management-for-initial-operations-readiness)
- [Operational support readiness](#operational-support-readiness)

For requirements for specific products, see [Go live with finance and operations apps](prepare-go-live-finance-and-operations-apps.md) or [Go live with customer engagement apps](prepare-go-live-dynamics-365-customer-engagement.md).

## Go-live readiness

Assess go-live readiness early and often through quality gate reviews. These assessments provide clarity on the status, readiness, completeness, and maturity of each activity. They also help project stakeholders and the steering committee make decisions to go live or not.

Make sure the solution scope is aligned with the solution that's going to be live, that it's been shared with stakeholders, and that business stakeholders and leadership agree that the expected scope is covered.

Make sure the solution has completed all test cycles with exit criteria satisfied and signed off on by the business stakeholders. The recommended test cycles cover system integration, performance, user acceptance, and other tests.

Make sure all scripts and processes planned for the cutover migration are tested and that stakeholders have signed off.

Make sure external dependencies, such as ISVs and third-party systems and services, are aligned with the timelines and scope for go-live.

Plan all change management activities, such as training, user support, user engagement, and communication. Implement all pre&ndash;go-live change management activities from the Initiate through the Prepare phases.

Have a plan for monitoring and a maintenance routine for production and for transitioning to support teams.

Make sure the production environment is prepared and that administrators and IT are familiar with monitoring, troubleshooting procedures, and avenues of support.

Create a cutover plan that considers all dependencies, the timing of activities, roles and responsibilities, instructions, verification steps, and any other documentation associated with each activity.

## Cutover

Implement the cutover plan by completing all activities in sequence, satisfying the exit criteria, and including sign-off at the cutover go/no-go checkpoint.

## Solution scope review

The solution scope conceptualizes the solution that's ready to go live. Review the solution scope to make sure that all requirements that are designed and developed during the Implement phase align with business needs.

### What to check in a solution scope review

Make sure business stakeholders understand the scope in the language of the business. For example, don't assume they read the fit-gap analysis or functional design document. Instead, they read the scope of the project to understand the business processes that the solution must support.

Consider the following items during the solution scope review:

- The business processes the solution will support
- The applications and solutions that are used in the solution
- Whether the solution contains customizations and independent software vendor (ISV) solutions
- The type and volume of integrations
- The number of go-lives or rollouts
- The number of users at go-live and in future rollouts

Make sure business stakeholders have signed off on the solution scope.

### Why you review the solution scope

The scope helps stakeholders understand the completeness, suitability, complexity, and magnitude of the solution. Even though the scope was defined at the beginning of the project and you're running the project according to it, reviewing the scope at this point can help determine other actions and identify potential risks.

Consider a "big bang" go-live of a heavily customized solution with multiple integrations. The more functionalities that go live on the first day, the greater the risk that issues will occur. If the risk is higher, be sure to assemble a strong support team and the right escalation path. The solution scope must be representative of the scope of your go-live event. The recommendations you follow for a "big bang" go-live might be different from the recommendations for a smaller implementation.

### Expected outcome of the solution scope review

The expected outcome of the solution scope review is that the scope aligns with the solution that's going to be live, that it's been shared with stakeholders, and that business stakeholders and leadership agree that the expected scope is covered.

#### Risks of not reaching the expected outcome of the solution scope review

 If the solution scope isn't clearly defined and shared, stakeholders don't have an understanding of what the solution includes. The solution might not include all requirements, or it might include developments that don't meet business expectations, either of which might cause delays. A well-defined solution scope significantly increases the probability of the project's success.

### Solution scope review mitigation plan

 Compare the solution scope with the solution that's delivered for go-live. Share the scope and comparison results with key stakeholders and determine whether the solution is complete or functionalities are missing. If any are missing, prioritize them and assign level of risks, owners, and expected completion dates.

## Solution acceptance review

After reviewing and verifying the solution scope, make sure that business stakeholders accept the solution that's being delivered.

### What to check in a solution acceptance review

Make sure the complete solution has passed all required types of testing and that business stakeholders accept it.

### Why you review the solution acceptance

The quality, coverage, and outcome of testing are reliable indicators of the solution's readiness for go-live, making sure unexpected scenarios don't come up after users start working with the new system.

A solid [testing strategy](testing-strategy.md) measures a solution's quality and effectiveness by simulating how the solution will operate in real life. Testing builds a solid foundation on which to determine whether the solution is acceptable, allowing the business to make a go/no-go decision. The business is required to sign off on the solution after objective and rigorous testing proves it fulfills the business vision.

### Expected outcome of the solution acceptance review

End-to-end unit testing is completed successfully and business stakeholders sign off on the results. Their sign-off indicates the solution as built meets their end-to-end process needs and that those processes are ready to be executed on the new solution.

#### Risks of not reaching the expected outcome of the solution acceptance review

Incomplete testing or not having sign-off from the business means that you can't validate you have a reliable solution that works properly in production. The risk is high that business processes can't be completed as required, causing  operational difficulties. You also risk technical issues, such as slow performance, unstable integrations, security holes, last-minute developments, rollbacks, and platform churn.

### Solution acceptance review mitigation plan

 Follow the [testing strategy](testing-strategy.md) best practices to make sure of the solution's integrity and effectiveness, minimize go-live blockers, and avoid the need to fix unexpected and critical bugs close to go-live. The testing strategy includes several types of tests, some of which are included in the go-live checklist. The main testing types are user acceptance testing (UAT), performance testing, and system integration testing (SIT).

## User acceptance test completion

In some cases, it's acceptable that the UAT isn't completed, provided no outstanding significant cases are found.

### What to check during UAT

Make sure UAT completed successfully and that stakeholders have signed off. UAT should include different types of personas, various geographic locations, and different environments (such as virtualized, physical, and remote) and devices (such as laptops, mobile devices, and tablets).

### Why you perform UAT

UAT helps validate that all the expected business processes affected by the system have been included. The solution might still have some minor bugs and need some fixes, but you can be confident that no critical part is missing. Users have a chance to try out the system and understand how to perform activities, and to bring up scenarios that might have been missed.

UAT often reveals edge cases that were overlooked earlier, requiring continuous fixes and improvements to the solution during this period.

### Expected outcome of UAT

 UAT should include the following requirements:

- Test cases cover the entire scope of the requirements, both "happy path" and edge scenarios.

- Tests use migrated data to validate how data in the system behaves in real life.

- Tests are performed with the correct security roles assigned to users. Don't use a general security role or assign the System Admin role to all users.

- The solution complies with regulatory requirements that are specific to the company, industry, or country/region. All features and testing results are documented.

- UAT is conducted in an environment in a Microsoft apps subscription so that its properties approximate your production environment as much as possible.

Make sure business stakeholders have signed off on the UAT.

#### Risks of not reaching the expected outcome of UAT

If UAT isn't completed sufficiently before the expected go-live date, the live operations might be delayed by issues such as unsuitable processes, poor system performance, and inadequate training. If the project team decides to go live with an incomplete UAT, they might discover the solution doesn't work properly after it's implemented. Recovery could be difficult, costly, and take a lot of time and resources. In extreme cases, production might shut down.

### UAT mitigation plan

Typically, UAT is considered complete when all the cases are covered and no blocking issues or high-impact bugs are identified. Establish a plan to address items identified during UAT, with an owner and an estimated completion date for each.

## Performance testing completion

Performance testing helps make sure the system performs as expected in all the circumstances in which it's expected to operate.

### What to check during performance testing

Make sure performance testing is completed successfully and that stakeholders have signed off. Performance testing should include the following aspects of the system:

- Load times with peak volumes of transactions
- Data search performance
- End-to-end processes and specific business processes
- Performance on different devices and in different browsers and virtualized environments
- Integrations
- Environments, data, and test cases are representative, and the results can be used to reliably predict performance in the production system

### Why you perform performance testing

Performance testing helps avoid issues with the system's performance after go-live. Implementations often fail because performance testing is conducted late in the project or overlooked altogether. For example, some teams delay performance testing until the production environment is ready and then use it as a test environment. Your production environment shouldn't be used for testing of any kind. It's easier to fix performance issues in a proper test environment than in a live environment. Fixing issues in production may also require downtime.

Any open issues that are critical for production need to be addressed before going live.

### Expected outcome of performance testing

The solution that's delivered performs as expected and meets the business performance criteria: It supports the load of expected transactions and user concurrency and usage, and the speed, system response time, stability, and scalability are acceptable.

#### Risks of not reaching the expected outcome of performance testing

A common misconception is that a production environment performs better than a test environment. This belief is sometimes used to justify skipping performance testing. However, [performance isn't only about infrastructure](performing-solution.md). A production environment can't be used to conduct core testing. It should be used for mock cutover, cutover, final validations, and live operations. We highly recommend that you conduct performance testing in a test environment before going live.

Another common misconception is that performance testing can be done during UAT. It might not be a good representation of the actual usage after go-live. For example, coverage of roles and personas, regional access, devices, and environments during UAT is thorough, but they're for a small percentage of users. UAT can validate the solution's readiness in terms of functional and even end-to-end performance of each business process. However, it doesn't represent the anticipated peak load and concurrency of critical business processes during actual usage in production. Consider defining a separate performance testing strategy that can simulate stress on the solution and concurrent usage.

### Performance testing mitigation plan

Execute performance testing in parallel with UAT. Establish a plan to address issues and assign owners and expected completion dates. Identify the root cause of issues so that you don't replicate them in the production environment.

## System integration testing completion

During SIT, it's important not only to test and verify the interactions between all parts of the solution, but also to plan for the unexpected.

### What to check during SIT

Make sure SIT is completed successfully and that stakeholders have signed off. It's important to test with expected peak volumes. Your system integration [testing strategy](testing-strategy.md) should include simulations of external systems that are down, how those scenarios are communicated, and the impact on the user experience.

### Why you perform SIT

SIT validates that the solution, including integrations between different applications and with external systems, works as expected.

### Expected outcome of SIT

The solution and its various integrations work as expected and you have a plan for handling unexpected outages in external systems.

#### Risks of not reaching the expected outcome of SIT

Going live without fully testing the integrations might result in incomplete, delayed, or invalid business process results. You also risk unsteady and ineffective system connectivity, performance issues, flawed and weak interfaces, and data flow issues, such as data inconsistency and data not being available on time.

### SIT mitigation plan

Perform SIT before you start UAT or you risk significant failures during UAT. If you conduct SIT during or after UAT and find out that you chose the incorrect [integration pattern](integrate-other-solutions.md) and must redesign your integrations, it puts your go-live at risk.

Complete SIT with peak volumes that are close to actual peak volumes and get sign-off from the business that the integration testing strategy works.

## Data migration readiness and validation

Make sure the data the solution needs is available where and when it's needed.

### What to check for data migration readiness

It's essential to have a well-designed data migration plan for go-live. It's also important to have a plan to validate the data after migration. You should plan to validate the quality of the data in the source system as close as possible to the source system, as well as testing the post-migration result in the Dynamics 365 application.

### Why you check data migration readiness

Data migration is a key activity during cutover. When you're moving from a legacy system, you need to make sure your data is accurate and complete on day one of your live operations. Having the right data at the right time in the right place is vital for the success of your implementation.

You also need to verify the quality of the data that's migrated. You should work to make sure you don't import bad data from your legacy systems into Dynamics 365 applications.

### Expected outcome of data migration readiness

Migration of data is tested several times before it's executed during the cutover. Testing should validate your strategy and processes, identify and address issues of data corruption or duplicated data, and make sure performance is measured and validated and fits in the cutover time window.

All scripts and processes planned for the cutover migration are tested and signed off by the business.

Any migration issues and risks are logged and a mitigation plan is established.

#### Risks of not reaching the expected outcome of data migration readiness

It's important to carry out all the steps of your data migration plan. It gives stakeholders confidence that the information reflects accurate data. If you skip steps or start with a poorly designed plan, concerns will arise about the implementation team's ability to complete the go-live migration in a timely manner. This risk is especially true if record quantities are exceptionally large.

Data quality is a key factor in the user experience. For example, if leads are imported with critical information missing, inaccurate, or corrupted, the sales team's trust in the new solution is reduced. It might even eventually lower solution adoption. Incorrect data will also be reflected when communicating with your customers through the system when it's live, reducing your customers' confidence in your organization.

### Data migration readiness mitigation plan

Prepare a migration plan and execute multiple dry runs to improve certainty about how long migration takes and the number of records that need to be migrated. Prepare configuration data, master data, security configurations, open transactions, and balances with enough time in advance to address any issues. Follow recommended practices for [data management](data-management.md).

## Confirmation of external dependencies

Document and monitor your solution's external dependencies.

### What to check when confirming external dependencies

Make sure any external dependencies, such as ISV solutions and third-party systems and services, align with your timelines and scope for go-live.

### Why you check external dependencies

ISV solutions, third-party systems and services, and other external dependencies are by definition outside the direct control of the implementation team. That means it's even more important that you account for them when you're building the project plan and managing the schedule.

### Expected outcome of confirming external dependencies

The implementation team coordinates with providers to make sure expectations are aligned, their solutions are aligned with the roadmap timelines, and all requirements are met.

#### Risks of not reaching the expected outcome of confirming external dependencies

Lack of coordination and communication with external providers might result in a delay in implementation.

### Confirmation of external dependencies mitigation plan

It's good practice to have regular meetings with providers to review status.

## Change management for initial operations readiness

It's important to include change management at the beginning of the project and assess the level of change readiness throughout.

### What to check for change management readiness

A change management plan prepares users for the changes they can expect to find, especially regarding the legacy system they're used to.

### Why you check for change management readiness

When you deliver a business solution, the success of the technical implementation and the solution's alignment with business needs and goals are paramount&mdash;but not sufficient to deliver the expected return on the company's investment. The true value of the solution is only realized when users actively adopt and engage with it.

It's natural to resist change, even if it's positive and can significantly improve an experience. Several resources and strategies are available to help your organization's efforts to change the way it works be successful. They include ways to communicate, reduce resistance, and allow feedback. Our goal here isn't to explore the plethora of change and adoption strategies, but to highlight the key principles and activities that are critical before the rollout of a new business solution.

### Expected outcome of change management readiness

The implementation team assesses change readiness early in the project, and reassesses throughout the project the changes the organization makes to help ensure the new system's smooth adoption.

The following key elements help drive change management close to go-live:

- **Training**: For a new system to succeed, it's vital that users know how to use it on day one of operations. Effective training helps them achieve the desired results and leads to higher rates of adoption. Failure to establish and deliver on a [training strategy](training-strategy.md) negatively impacts usage and adoption. The most common training strategy is a formal set of sessions delivered in a classroom setting or online.

  When possible, training should be delivered early enough before the go-live date to prevent delayed access to the new solution, but not so early that users forget what they've learned by the time they're hands-on. Earlier training can contribute to higher adoption if users feel included and had the opportunity to share feedback before the new solution went into production.

- **User engagement strategy**: A user-centered mindset helps address not just a solution's functional requirements, but also the unspoken needs of the user. Telling a story of empowerment&mdash;showing how the solution helps users be more efficient in their jobs, for example&mdash;is a message that strongly resonates. Your program must have an effective way to engage the solution's users to help drive adoption and eliminate the risk of building a solution that doesn't meet user requirements.

  A key activity to perform early in the project is identifying super-users, or influencers, who are willing to actively engage with the project team. Provide opportunities throughout the project for these people to provide input and feedback. The following project milestones benefit most from super-user feedback:

  - Early minimum viable product or proof-of-concept demonstration
  - Sprint demonstrations during implementation to highlight business functionality
  - User experience and information architecture design
  - Data mapping and validation that data migration activities are involved in the project
  - Baseline performance metrics for frequently accessed components
  - Expectations for user devices and accessibility
  - Review of the timing of key milestones such as go-live and cutover
  - Backlog prioritization and setting expectations for gaps, open issues, and future functionality

  A well-structured nurture program for business users that focuses on effective communication keeps them up to date and engaged in the project.

  Although most of this work happens throughout the implementation project, the culmination of all this planning at go-live should be a change readiness review that's validated and signed off on.

- **Business sponsorship**: The business sponsor, or executive sponsor, is a trusted and influential leader who makes cultural changes possible and accepted. This person plays an essential role in championing transformation throughout the organization by communicating the value of the new solution. Creating an awareness of key executive sponsors and bringing them before the user community to articulate the value of the new solution can positively influence adoption and usage. Users are less resistant to adopting novel solutions when business sponsors serve as a role model.

  As part of go-live activities, the executive sponsor's communication strategy needs to be well planned. This strategy includes the types of communication, the stakeholders, the timing, and recognizing the contributions of users.

- **User support**: Create a community of super-users and provide resources such as videos, tutorials, knowledge base articles, and business process guidance to help with user adoption after go-live and encourage ongoing user engagement. Establish a well-defined channel to communicate upcoming changes, open issues, and service notifications for planned and unplanned maintenance and outages.

#### Risks of not reaching the expected outcome of change management readiness

A poor change management plan might cause ineffective execution of processes on the first day of go-live. Users might develop a lack of confidence in the new solution, which is counterproductive for a successful rollout.

### Change management readiness mitigation plan

Reassess the change management plan throughout the implementation project.

## Operational support readiness

Have a support plan in place to make sure users can easily and quickly get help if they run into trouble.

### What to check for support readiness

Make sure to have a system monitoring and maintenance plan for the production environment and a plan for [transitioning operational support](transition-to-support.md) from the implementation team to a support team.

### Why you check for support readiness

The support team is responsible for the health and availability of the solution after it's live and for providing support to the people who use it. Before go-live, have a plan to make sure that support transitions from the implementation team to the support team as smoothly as possible.

### Expected outcome of support readiness

Support teams, whether they're internal or provided by a partner, have the resources, tools, and access they need to the system, related infrastructure, and subject matter experts, business analysts, process specialists, and change management champions. They're trained on the solution. A help desk and ticket management process are in place.

When all parties agree that the system is ready to go into production, notify stakeholders and send them a list of people who will use the new system. Notify users of any unresolved issues or required workarounds and provide them with a support contact.

The following items should be included in the operational support and maintenance plan:

- [**Continuous deployment plan**](service-solution.md): It's important to go live on the latest available serviceable version of the system. You can take advantage of the latest updates, have access to the best quality solution, and have the support you need if a hotfix is required.

  It's also important to understand the release cadence of your new solution so that you can incorporate updates and new features and replace deprecated ones quickly. Make it part of your maintenance plan. It's vital for the continuity of your operations in production.

- **Monitoring**: Establish a monitoring strategy for performance issues, errors, feature usage, and adoption. It makes the post&ndash;go-live process easier to manage and easier to provide updates to stakeholders.

- **Hypercare**: Consider providing an [elevated level of support](transition-to-support.md), or hypercare, immediately after go-live to ensure the seamless adoption of the new system.

#### Risks of not reaching the expected outcome of support readiness

If you don't have a well-defined plan to support production, or if the plan isn't properly shared before go-live, it's difficult, if not impossible, to communicate issues when they start popping up. That makes it harder to assign resources and severity levels.

You also risk going live in a system version that's out of service. If an issue is uncovered in production, you must update the solution to the latest version before you can apply the hotfix. Automatic updates that install unexpectedly might affect system operations.

### Support readiness mitigation plan

It's important that you have a plan to transition support before go-live. With a support plan, support teams can be proactive and preventive rather than reactive.

## Next steps

- Learn how to [prepare your production environment](prepare-go-live-production-environment-readiness.md) for go-live.
- Learn the important of [cutover](prepare-go-live-cutover-strategy.md) in the go-live process.
- Review the specific guidelines for [finance and operations apps](prepare-go-live-finance-and-operations-apps.md) and [customer engagement apps](prepare-go-live-dynamics-365-customer-engagement.md).
