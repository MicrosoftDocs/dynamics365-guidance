---
title:  Transition to support - support models
description: This article is covers the different support models for a Dynamics 365 implementation and considerations when choosing a model.
author: taksatoms
ms.author: tsato
ms.date: 04/11/2023
ms.topic: conceptual
---

# Support models

Defining the support model is ideally started in the Implement phase so that it can be ready and exercised prior to user acceptance testing (UAT), can help with the transition during the Prepare phase, and be fully effective and working by the Operate phase.

## Support model options

Thus far, we have discussed topics that help define the scope of responsibilities and actions for a support team. Now we look more at the "who" and the "how," starting with an examination of the spectrum of support models.

One of the foundations of the support strategy is defining the operational model for the support organization. Some of the factors may be driven by enterprise-level strategies, including on outsourcing or existing commercial agreements. Some organizations reference independent, formal IT support and service frameworks such as Information Technology Infrastructure Library (ITIL) or ISO 20000, or other formal standards and methodologies. These are typically adopted at an enterprise level, rather than system-by-system. Regardless of the framework, you have some key options to choose from:

- **Fully outsourced**  

  This support model is more often seen in smaller projects that don't have many critical business processes within their scope or have insufficient internal resources to create a critical mass for any dedicated internal support members. This model requires the outsourced support organization to be more immersed in the business and understand the business well to navigate the organization when looking for decisions, diagnostic data, and approvals, as well as have a good understanding of the business priorities. To succeed, it needs the business and partner to have a common language to communicate business needs and technical application processes between each other so that expectations remain aligned.

- **Fully internal**  

  A support model without partner support isn't seen very often because it's a difficult model to sustain on an active project without a larger internal team that can cope with peaks and troughs of demand and has the necessary distribution of skills across business workstreams, technical areas, and servicing, including any specialist skills. If internal resources are constrained, you run the risk that the business stops being ambitious and outward looking in driving improvements and encouraging innovation. The solution can become stagnant, where assumed stability can come at the expense of extracting optimum value from the application.

- **Mixed**  

  This is probably the most common model. It has a balanced blend of internal resources that develops expertise in the application and retains a deep understanding of the business. Partner organizations can offer strategic advice based on their wider experience across multiple implementations and provide support for any custom code, resources to cope with peaks, and specialists when required.

### Considerations per support level

In this section, we break down the business considerations by each support level.

:::image type="content" source="media/transition-to-support-models.png" alt-text="Support models" :::

#### First level

Many customers have a concept of identifying and nominating super users within a business unit. Typically, the super users gained their deeper knowledge of the system and processes in their previous role as subject matter experts (SMEs) during the project cycle.

Super users can provide the following benefits:

- Provide immediate assistance to a user to unblock someone in most simple cases

- Filter out the simple questions such as "How do I do this?" or "Is this what I should expect?"

- Provide ad-hoc training at a business unit level

- Triage and communicate issues in a way that makes it easier for the helpdesk or resolving authority to understand the issue, replicate it, and fix it rapidly

- Collate best practices, FAQs, and issues, and provide the core team better data on areas of priority for them to tackle

- Provide early warning on issues that have the potential to escalate and help with better adoption by the business

This model helps organizations scale out application support without having to create a large central support team or pay external parties to resolve day-to-day queries on internal business process or simple application questions.

For larger business units, super users may be further divided by functional area, such as Finance or Operations. These super users are typically identified during the project phase and participate in formulating and implementing testing (such as UAT) and may also become the trainers for cascade training. This allows them to gain the necessary experience and skills to provide first-line support.

Consider formalizing the super-user role with funding and consider formal titles or dedicated time to perform that role. Formal performance objectives and compensation also help ensure this is not just one more assigned task. Informal super-user roles don't always succeed because day-to-day operational tasks tend to be given a higher priority.

#### Second level

Almost all customers have some internal helpdesk function for IT systems, and many also have them for business applications. The size and nature of the helpdesk varies depending on the model adopted.

For a fully outsourced model, the internal helpdesk registers the issue and assigns it to the resolving authority (internal or external). This fully outsourced model is tougher to deliver for highly-customized business systems compared to less customized ones. Determining the correct resolving authority can be tricky in business systems, even assuming the super-user roles have eliminated the cause as a business process or training issue, you may have many different system layers, such as an internal network, infrastructure software managed internally or by Microsoft, standard Dynamics 365, custom code, ISV code, or integration software at either end.

Determining how to prioritize and who should drive the issue to resolution is a typical deficiency seen in this fully outsourced model, because very often the issue can bounce around various parties. The other consideration for business systems is managing what business data and process steps should be made available to the next resolving authority. Additionally, if the partner is driving this in a fully outsourced model, you need a clear definition of the access the partner is given to users, the business data, and what can be further passed on the next resolving authority.

In the fully internal model, the internal helpdesk also routes the issue to a small internal 365 Dynamics team that triages the issue and helps determine the best resolving authority. This team is also responsible for ensuring the issue is driven to resolution, regardless of the number of parties (internal or external) that may need to be involved. The difference is that the next resolving authority may be the internal Dynamics 365 Center of Excellence (CoE).

For multi-company or multi-project organizations, many create a CoE that works with group IT to ensure the following:

- Common standards on the Azure environment

- Operational and maintenance policies on backups, business continuity, and disaster recovery

- IT security and policies (such as password policies, MFA, SSO, and firewall rules)

- Regulatory needs, including access and security, data retention

In the mixed model, which many customers adopt, the internal helpdesk routes the issue to a small internal Dynamics 365 team that triages the issue and helps determine the best resolving authority. This team is also responsible for ensuring the issue is driven to resolution, regardless of the number of parties (internal or external) that may need to be involved.

#### Third level

In a fully outsourced model, the partner is responsible for triage and resolution. In the mixed model, the most common scenario is for the internal Dynamics 365 support team to determine if they can resolve the issue; if not, they work with the Dynamics 365 CoE and the partner to ensure it's well understood and correctly prioritized.

In the fully internal and mixed model, the Dynamics 365 CoE includes functional and technical experts (including developers) who can resolve issues with custom code. If the issue is seen to be with standard Dynamics 365 or an ISV, the CoE logs the issue and works with Microsoft or the ISV to get it resolved.

#### Fourth level

In the fully outsourced model, the partner manages the process and the customer is involved as necessary. Most customers tend to have some parts of the solution written or managed by their internal IT team (such as integrations), so you still need a definition of how the partner should work with the customer.

In the fully internal model, the Dynamics 365 CoE takes on the diagnosis and resolution if it's within their control. They only involve external parties if the issue lies with standard Dynamics 365, platform hosting, or an ISV.

In the mixed model, the internal Dynamics 365 CoE or core team typically fixes the simpler issues, but involve a partner for issues that require deeper Dynamics 365 knowledge or for complex issues.

When the issue is resolved, the method to get the fix back into production also requires a clear definition of the expected standards, testing regimen, and deployment process. Even in a mostly outsourced model, the partner drives this to a pre-production environment and the internal team deploys to production. Most customers don't give partners admin access to production environments.

#### Fifth level

Registering the issue with Microsoft support tends to be the common escalation point, after the determination is made that the most likely root cause is the standard Dynamics 365 software or service.

Similarly, most customers have a support and maintenance contract with their ISV suppliers. In the fully outsourced model and in some mixed mode models, the partner is contractually responsible to work with the ISV for resolution.

## Next steps

- Review how to construct a strategy to help you prepare, define, and operate a support model in the section [overview](transition-to-support.md)  
- Learn about the importance of defining the [support scope](transition-to-support-scope.md)  
- Learn about the different [support models](transition-to-support-models.md)  
- Uncover the requirements related to [support operations](transition-to-support-operations.md)
- Review the [checklist](transition-to-support-checklist.md) to help with implementing your support model
- Read the [case study](service-solution-case-study.md) to understand the need to develop and continually audit an organization's support strategy in the cloud world