---
title: Choose a support model for your Dynamics 365 solutions
description: Learn about the options and factors to consider when you choose a support model for your Dynamics 365 implementation projects.
author: taksatoms
ms.author: edupont
ms.date: 01/31/2024
ms.topic: concept-article
ms.custom:
  - evergreen
  - ai-seo-date: 01/31/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Choose a support model

A support model defines how you provide technical assistance and maintenance for your Dynamics 365 solution. You should start planning your support model in the **Implement** phase of your project, so that you can test it before user acceptance testing (UAT), use it during the **Prepare** phase, and have it fully operational by the **Operate** phase.

## Support model options

Your support model depends on several factors, such as:

- Your business needs and priorities
- Your internal resources and skills
- Your outsourcing strategy and agreements
- Your existing IT support and service frameworks

You can choose from three main types of support models:

- **Fully outsourced**  

  In this model, you rely on an external partner to handle all aspects of support. This model works best for smaller projects that don't involve many critical business processes or require a lot of internal expertise. You need to have a good relationship with your partner and communicate clearly about your business needs, expectations, and priorities. Your partner also needs to understand your business well and have access to the right information and approvals.

- **Fully internal**  

  In this model, you manage all aspects of support with your own staff. This model works best for larger projects that have a lot of internal resources and skills across different areas, such as business workstreams, technical areas, and servicing. You also need to have specialists for any custom code or integrations. This model allows you to have more control over your solution and drive improvements and innovation. However, you also need to cope with the fluctuations in demand and keep up with the latest updates and best practices.

- **Mixed**  

  In this model, you combine internal and external resources to provide support. This is the most common model because it offers a balanced approach. You can have internal staff who know your business well and can handle simple issues, training, and triage. External partners offer strategic advice, cope with peaks in demand, and provide support for custom code or integrations.

## Considerations per support level

You can also define different levels of support based on the complexity of the issues and the roles involved. The following diagram shows an example of how you can structure your support levels:

:::image type="content" source="media/transition-to-support-models.png" alt-text="Diagram showing five levels of support, from first level (super users) to fifth level (Microsoft or ISV support)." lightbox="media/transition-to-support-models.png":::

### First level

The first level of support is usually provided by super users within each business unit. Super users are people who have deeper knowledge of the system and processes and can help other users with simple questions or issues. Super users can also:

- Provide immediate assistance and unblock users in most cases
- Filter out simple questions such as "How do I do this?" or "Is this what I should expect?"
- Provide as-needed training at a business unit level
- Triage and communicate issues to the next level of support
- Collate best practices, FAQs, and issues and provide feedback to the core team
- Provide early warning on issues that might escalate and help with user adoption

Super users are usually identified during the project phase and participate in testing and training activities. You should formalize the super-user role with funding, time allocation, performance objectives, and compensation. This way, you can ensure that super users have the motivation and resources to perform their role well.

### Second level

The second level of support is usually provided by an internal helpdesk function for IT systems or business applications. The helpdesk registers the issues and assigns them to the appropriate resolving authority, either internal or external. The helpdesk also tracks the progress and status of the issues.

The helpdesk needs to have clear criteria and processes for determining the resolving authority, especially for complex or customized systems. The helpdesk also needs to manage the access and security of business data and process steps that might be needed by the resolving authority.

Some organizations have a Dynamics 365 Center of Excellence (CoE) that works with the helpdesk to ensure common standards, policies, and best practices for the Dynamics 365 environment. The CoE can also provide functional and technical expertise for resolving issues.

### Third level

The third level of support is usually provided by a small internal Dynamics 365 team that triages the issues and tries to resolve them. If they can't resolve them, they work with the CoE or an external partner to find a solution. The Dynamics 365 team is also responsible for ensuring that the issues are resolved, regardless of how many parties are involved.

The Dynamics 365 team needs to have a good understanding of both the business needs and the technical aspects of the solution. They also need to communicate effectively with all stakeholders and coordinate the resolution process.

### Fourth level

The fourth level of support is usually provided by an external partner or an internal IT team that can handle more complex or specialized issues, such as custom code or integrations. The partner or IT team diagnoses and resolves the issues and follows the expected standards, testing regimen, and deployment process for any fixes.

The partner or IT team needs to have deep expertise in Dynamics 365 and related technologies. They also need to work closely with the Dynamics 365 team or CoE to ensure alignment and quality.

### Fifth level

The fifth level of support is usually provided by Microsoft or an ISV when the issue is related to standard Dynamics 365 software or service or an ISV solution. The Dynamics 365 team or CoE registers the issue with Microsoft or the ISV and works with them to get it resolved.

The Dynamics 365 team or CoE needs to have a support and maintenance contract with Microsoft or the ISV and follow their procedures and guidelines. They also need to provide clear and accurate information about the issue and its impact.

## Next steps

- Learn how to set up your [support operations](transition-to-support-operations.md)
- Understand the roles and responsibilities of your [support team](transition-to-support-team.md)
- Review a [checklist](transition-to-support-checklist.md) for implementing your support model
- Read a [case study](service-solution-case-study.md) to understand why you need to develop and audit your support strategy in the cloud world
