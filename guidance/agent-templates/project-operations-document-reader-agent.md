---
title: Document Reader Agent
description: Discover how to streamline project setup with AI-driven data extraction in Dynamics 365 Project Operations. Reduce manual effort and ensure consistency in your workflows.
#customer intent: As a Dynamics 365 administrator, I want to learn how AI can automate how projects are created and updated in Project Operations.
author: edupont04
ms.author: ajjaiswa
ms.date: 03/25/2026
ms.topic: concept-article
ms.collection: bap-ai-copilot
---

# Agent for document reading in Dynamics 365 Project Operations

***Applies to***: ***Dynamics 365 Project Operations, Copilot Studio***

This agent analyzes engagement information and extracts key project and commercial details from engagement letters or statements of work (SOW). Use these details to create or update a *Project* or *Project Contract* in Dynamics 365 Project Operations.

> [!NOTE]
> The agent template isn't yet available for download. If you're interested in the template for a document reader agent, fill in [this form](https://forms.office.com/r/kdvS5NNuZ1).

## Overview

The agent identifies structured data such as project name, customer, dates, budget, scope, deliverables, milestones, and resource roles. It organizes the extracted information into a structured format that you can review and use when you create or update a project or project contract.

## Key benefits

- Extracts structured project and contract data from engagement details.

- Prepares standardized information for setting up projects and project contracts.

- Reduces manual interpretation and data entry effort.

- Improves data accuracy and consistency.

- Supports human validation and controlled data entry.

- Provides traceability of extracted information.

## Scenarios

- Review engagement details before you create a new project.

- Prepare structured inputs for setting up project contracts.

- Identify updates required for existing projects.

- Extract milestone schedules for planning purposes.

- Capture commercial and scope details for internal validation.

## Industries

- Professional services  
- Consulting  
- IT services  
- Engineering and construction  

## Supported channels

- Copilot in Dynamics 365 Project Operations  
- Custom copilots built with Microsoft Copilot Studio  

## Input and output

The Document Reader agent takes the following input:

- Engagement information containing project and commercial details.
- Optional configuration for mapping extracted fields to Project Operations schema.

The agent delivers the following outputs:

- Structured summary of extracted information that you can use to create a project or project contract, and to update a project or project contract.  
- Optional structured data format (JSON or table view) for downstream processing.

## Pipeline

The following list outlines the pipeline for extracting and processing data.

1. Engagement analysis  

    The agent analyzes the provided engagement information and identifies relevant project and contract data.

1. Entity extraction  

    The agent extracts key data elements by using natural language processing and structures them into a consistent schema.

1. Schema mapping  

    The agent maps the extracted values to the corresponding fields on projects and project contracts for reference.

1. Validation and review  

    The agent presents the structured output to the user for validation and manual action.

1. User-driven action  

    Users can use the reviewed information to create or update projects and project contracts in Project Operations.

## Required products and services

- Dynamics 365 Project Operations  
- Microsoft Copilot Studio  
- Copilot Studio Credits Capacity  

## Related content

- [Introduction to the Dynamics 365 agent templates](overview.md)  
- [Dynamics 365 Project Operations overview](/dynamics365/project-operations/welcome-to-project-operations)
- [Microsoft Copilot Studio documentation](/microsoft-copilot-studio/)
