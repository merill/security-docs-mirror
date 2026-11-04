---
layout: Conceptual
title: Adopt security business scenarios in the Microsoft security adoption model | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-business-scenarios-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn how to get started with common business scenarios in the Microsoft security adoption model
ms.date: 2026-05-24T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 9dbc046f-b026-fd02-4fcc-32adfef83324
document_version_independent_id: 9dbc046f-b026-fd02-4fcc-32adfef83324
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-adoption-business-scenarios-overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-adoption-business-scenarios-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-adoption-business-scenarios-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/c6f99e62-1cf6-4b71-af9b-649b05f80cce
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3f56b378-07a9-4fa1-afe8-9889fdc77628
platformId: 5b9c5f48-1107-439e-f95c-4bc46dd8388f
---

# Adopt security business scenarios in the Microsoft security adoption model | Microsoft Learn

This article explains how business scenarios help you prioritize security adoption based on business outcomes rather than individual technologies.

Organizations rarely modernize security all at once. Instead, most focus first on the risks that matter most to the business.

Our [structured adoption model](security-adoption-model) starts with business scenarios. Business scenarios:

- Describe common and high-priority organizational risk situations, and help you determine which security capabilities to adopt first.
- Provide a shared starting point for business leaders, security leaders, architects, and technical teams to align on *where to begin* and *why.*

Tip

Microsoft offers a rich set of security adoption workshops - the *Security Adoption Framework (SAF) workshops*. Our structured adoption model guidance aligns with the expert-led guidance from Microsoft Unified delivered in those workshops. Learn more about [SAF workshops](workshop-business-overview).

## Why business scenarios matter

As a business leader, you're accountable for managing cybersecurity risk as part of protecting the organization.

Meeting that responsibility requires a clear, practical way to set priorities, communicate intent, and track progress - one that connects technical security work to the business outcomes you care about.

Business scenarios provide that connection. They frame security efforts in terms of business outcomes such as enabling secure work from anywhere, and help translate technical initiatives into business-relevant goals in language that resonates with leadership.

This outcome‑based framing helps you to:

- **Connect security and business**: Understand why specific security initiatives matter.
- **Prioritize security initiatives**: Set business‑aligned priorities for your security team.
- **Set expectations**: Understand what to expect from security investments and teams.
- **Make decisions**: Make informed decisions about prioritization, investment, risk, tradeoffs, and resource allocation.
- **Track adoption**: Track security adoption and modernization progress without too much deep technical detail.

## What is a business scenario?

A business scenario represents a recognizable business situation that drives security risk. Each scenario:

- Reflects a common organizational challenge or operating model.
- Highlights the most critical security risks in that situation,
- Emphasizes the security outcomes that should be prioritized first.

For example, an organization modernizing legacy infrastructure faces different risks than a "digital-native" business that only operates and builds in the cloud.

Business scenarios capture these differences so that security investments can be aligned to real business needs.

**Business scenarios are**:

- A prioritization tool for security modernization.
- A way to connect business risk to security outcomes.
- A communication mechanism between business and technical stakeholders.

Business scenarios don't describe how to implement security controls. Implementation is covered by [security disciplines](security-adoption-discipline-overview) and [technical solutions](implement-overview) that align to the priorities and outcomes of business scenarios.

## Align with security disciplines and solutions

Our security adoption model intentionally separates intent, design, and execution:

- **Business scenarios** define the business context and capture the business problem we want address and what outcomes matter.
- **Security disciplines** provide foundational, cross‑cutting practices that apply across all scenarios and solutions.
- **Technology pillars** represent the core areas of a security architecture such as identity, data, and devices. They provide stable boundaries in which to design and implement security controls across the organization.
- **Technical solutions** show how to implement a business scenario using Microsoft security products. Technical solutions usually focus on a specific technology pillar and integrate other pillars as needed to provide and end-to-end implementation.

A single business scenario is often supported by multiple security disciplines, multiple technology pillars, and multiple technical solutions. You can learn more about how these components integrate on a per-business scenario basis.

## How do I use the model?

1. Select one or more business scenarios that most closely matches your prioritized business goals.
2. Review security disciplines associated with the scenario.
3. Deploy a scenario using its mapped technology pillars and technical solutions.

Following this model ensures that you start with business priorities, maintain consistency, avoid duplicate work, and implement using prescriptive solution guidance based on security best practices.

## Structure of business scenarios

Each business scenario includes:

- **Overview** - A concise, plain‑language description that enables rapid understanding and shows how the scenario fits within the adoption model.
- **Business value** - Explains why the scenario matters to business leaders, technology roles, and security teams, supporting prioritization and executive alignment.
- **Technical strategy and architecture** - Describes how planning, and oversight, technical strategy, and operational security disciplines work together to enable the scenario and its outcome.