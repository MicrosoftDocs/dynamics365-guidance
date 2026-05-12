# Copilot Instructions for dynamics365-guidance-pr

## Repository Overview

This is a Microsoft Learn documentation repository for **Dynamics 365 guidance content**, published via the Open Publishing System (OPS/DocFX). It contains implementation guidance, business process catalog articles, reference architectures, and design patterns for Dynamics 365 apps and services.

The public-facing repo is `MicrosoftDocs/dynamics365-guidance`; this is the private working repo (`-pr` suffix).

## Architecture

- **`guidance/`** — The docset root (defined in `.openpublishing.publish.config.json`)
  - `business-processes/` — End-to-end business process catalog (the largest content area)
  - `implementation-guide/` — Success by Design framework guidance
  - `reference-architectures/` — Architecture patterns with Azure and Dynamics 365
  - `patterns/` — Reusable implementation and business process patterns
  - `agent-templates/` — Copilot Studio / AI agent scenario templates
  - `develop/` — UI/UX design guidance for Power Apps and Dynamics 365 Sales
  - `migrate/` — Migration/upgrade guidance (AX, CRM, GP, NAV, AIM)
  - `organizational-strategy/` — Organizational design and strategy content
  - `roles/` — Audience/role definitions and career guidance
  - `techtalks/` — TechTalk video summaries and landing pages
  - `resources/` — Implementation tools and sample solutions
  - `fasttrack/` — FastTrack-specific content
  - `isv/` — Guidance for independent software vendors
  - `includes/` — Reusable Markdown snippets (excluded from build output)
  - `media/` — Images (PNG, JPG, SVG)
- **`shared-content/`** — Pulled from `MicrosoftDocs/powerapps-docs-pr` as a dependent repository (referenced via `~/../shared-content/`)
- **`.openpublishing.redirection.json`** — URL redirections (add entries here when renaming/moving articles)

## Content Conventions

### Article metadata (YAML front matter)

Every `.md` file must start with YAML metadata:

```yaml
---
title: Short descriptive title
description: A 1-2 sentence summary for SEO (max ~160 chars).
#customer intent: As a <role>, I want to <goal> so that I can <outcome>.
author: githubusername
ms.author: microsoftalias
ms.topic: concept-article  # or reference-architecture, overview, how-to-guide, hub-page, landing-page
ms.date: MM/DD/YYYY
ms.custom: bap-template  # Required for most articles
---
```

- `ms.date` uses **MM/DD/YYYY** format and must reflect the last meaningful update.
- The `#Required; don't change.` comment appears after `bap-template` in many files — preserve it.
- `#customer intent` is a commented-out YAML field used in newer articles. Preserve it when present.
- Reference architecture articles use `ms.topic: reference-architecture`.

### Headings and structure

- The first line after front matter must be an H1 (`#`) matching the `title` metadata.
- Use sentence case for all headings.
- Two trailing spaces at end of paragraphs are used intentionally for line breaks in some articles.

### Include files

- Local includes: `[!INCLUDE [name](../includes/filename.md)]`
- Cross-repo includes: `[!INCLUDE [name](~/../shared-content/shared/guidance-includes/filename.md)]`

### Cross-references and links

- Internal links use relative paths: `[link text](../implementation-guide/article.md)`
- Links to other Microsoft Learn docsets use absolute paths without domain: `[text](/dynamics365/guidance/business-processes/)`
- TOC cross-references: `href: /dynamics365/path?toc=/dynamics365/guidance/toc.json`

### Images

- Store images in `media/` subdirectories adjacent to content.
- Use descriptive alt text.
- Supported formats: PNG, JPG, SVG.
- Use `:::image type="content" source="media/filename.ext" alt-text="Description." lightbox="media/filename.ext":::` — the `lightbox` attribute enables click-to-zoom and is used for all image types (not just SVGs).

### Alerts and callouts

Use Microsoft Learn alert syntax for notes, tips, warnings, and important callouts:

```markdown
> [!NOTE]
> Content for the note.

> [!TIP]
> Content for the tip.

> [!IMPORTANT]
> Content for the important callout.
```

### Contributors section

Articles with external contributors include a `## Contributors` section at the bottom following the pattern in `guidance/includes/daf-contributors-md.md` (with LinkedIn links and job titles).

## File Naming

- Use lowercase kebab-case: `area-topic-subtopic.md`
- Business process articles follow the pattern: `{end-to-end-scenario}-{process-name}-{qualifier}.md`
  - Example: `order-to-cash-monitor-customer-credit-collections-overview.md`
  - Example: `project-to-profit-pattern-enter-project-expenses-expense-management.md`

## Quality Checks

- **Acrolinx** is configured (`.acrolinx-config.edn`) with a minimum quality score of 80. It checks spelling, grammar, style, and Microsoft terminology.
- The VS Code extension `ms-learns.documentor` is recommended (`.vscode/extensions.json`).

## Redirections

When renaming or deleting an article, add an entry to `.openpublishing.redirection.json`:

```json
{
  "source_path": "guidance/old-path/old-file.md",
  "redirect_url": "/dynamics365/guidance/new-path/new-file",
  "redirect_document_id": "false"
}
```

## TOC Management

- `guidance/TOC.yml` is the main table of contents — update it when adding or moving articles.
- Use `href` for local files and full paths with `?toc=` parameter for cross-docset references.

## Business Process Article Templates

Business process content follows a strict hierarchy of article types, each with its own structure.

### 1. Introduction article (`{scenario}-introduction.md`)

Top-level entry point for an end-to-end business process scenario. Structure:

```markdown
# Introduction to Dynamics 365 {scenario} business process areas

***Applies to: {comma-separated list of Dynamics 365 apps}***

{Introductory paragraph referencing the catalog number}

## {Scenario} overview
{High-level description of the process}

## Effect
{Business impact of implementing technology for this process}

## Stakeholders
{Bulleted list of roles with descriptions}

## {Scenario} benefits
{H3 subheadings for each benefit with explanations}

## Next steps
{Numbered list with links to implementation resources}

## Related information
{Bulleted list of external links to docs, training, certifications}
```

### 2. Overview article (`{scenario}-overview.md`)

Describes the process flow and its relationship to upstream/downstream processes. Structure:

```markdown
# Overview of the {Scenario} end-to-end business process flow

***Applies to: {apps}***

## {Scenario} process relationship
{Diagram + explanation of upstream processes (bulleted with bold names and descriptions)}

{List of business process areas in this scenario}

{Explanation of downstream processes}

## Next steps
```

### 3. Areas article (`{scenario}-areas.md`)

Lists and describes all business process areas within the end-to-end scenario. Structure:

```markdown
# Overview of the {Scenario} business process areas

***Applies to: {apps}***

## {Area name}
{Description paragraph with "Learn more at [link]" reference}

## {Next area name}
...
```

### 4. Business process area overview (`{scenario}-{area}-overview.md`)

Deep dive into a specific business process area. Structure:

```markdown
# Overview of the {Area} business process within the {Scenario} end-to-end scenario

***Applies to: {apps}***

## Introduction to {area}
{Detailed description}

## {Area} stakeholders
{Bulleted role list with descriptions}

## {Area} process flow
{Flow diagram with numbered step-by-step walkthrough}

:::image type="content" source="media/{filename}.svg" alt-text="{description}" lightbox="media/{filename}.svg":::

## {Area} benefits
{H3 subheadings per benefit}

## Next steps
{Numbered list of sub-processes with links}
```

### 5. Pattern article (`pattern-{name}.md` or `{scenario}-pattern-{name}.md`)

Describes a specific reusable solution pattern. Structure:

```markdown
# {Pattern title}

***Applies to: {apps}***

## Context and problem
{When this situation arises}

## When to use this pattern
{Bulleted criteria for applicability and non-applicability}

## Solution: {solution name}
{Description of the approach}

### Procedure: {task name}
{Numbered steps with UI field references in bold}
```

### Common elements across all article types

- **Applies to line**: Always italic+bold (`***Applies to: ...***`), placed immediately after H1.
- **Italicized process names**: Business process names are always in italics (e.g., *acquire to dispose*).
- **Diagrams**: Use `:::image type="content"` with both `source` and `lightbox` attributes pointing to SVG files in `media/`.
- **Include references**: `[!INCLUDE [name](path)]` for reusable content blocks.
- **Cross-references**: "Learn more at [link text](relative-path.md)" is the standard phrasing.
- **Next steps**: Always present as the final content section before "Related information".

## Reference Architecture Article Template

Reference architecture articles follow a different structure from business process articles. Structure:

```markdown
# {Architecture title}

***Applies to***: ***{comma-separated products}***

{Introductory paragraph describing the solution}

## Use cases and industries
{Key use cases (bold titles with descriptions) and industries}

## Stakeholders
{Key stakeholders and their roles}

## Architecture
{Introductory sentence + architecture diagram}

:::image type="content" source="media/{filename}.svg" alt-text="{description}" lightbox="media/{filename}.svg":::

## Dataflow
{Numbered steps describing data flow through the architecture}

## Components
{List of components and their roles in the solution}

## Scenario details
{Additional context, assumptions, or considerations}

## Related content
{Links to related documentation}
```

**Key difference**: The "Applies to" line in reference architectures uses the format `***Applies to***: ***{products}***` (colon inside the first bold-italic block, products in a separate bold-italic block), versus business process articles which use `***Applies to: {products}***` (all in one block).

## Landing Page YAML Files (`index.yml`)

Section landing pages use YAML format instead of Markdown:

- **Hub pages** (top-level): Start with `### YamlMime:Hub` — used for `guidance/index.yml`.
- **Landing pages** (section-level): Start with `### YamlMime:Landing` — used for subsection indexes like `business-processes/index.yml`, `reference-architectures/index.yml`.

Both include `metadata` with standard fields and a `landingContent` or `highlightedContent` section with card-based link lists.
