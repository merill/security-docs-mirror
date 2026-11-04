---
layout: Conceptual
title: Microsoft Security Adoption Framework (SAF) | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-model
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Learn about the adoption model for Microsoft security.
ms.date: 2026-05-24T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 75fc3d02-2483-9165-b604-90e1e61a3769
document_version_independent_id: 75fc3d02-2483-9165-b604-90e1e61a3769
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-adoption-model.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-adoption-model
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-adoption-model.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 6696170c-5817-ab69-cc8d-a91ceaec420b
---

# Microsoft Security Adoption Framework (SAF) | Microsoft Learn

To build effective security foundations and defend against attacks in the age of artificial intelligence (AI) and AI agents, organizations must follow Zero Trust principles.

**Adopting Zero Trust security principles across your organization** is a complex, multiyear effort that spans business strategy and planning, technical design and architecture, deployment, and operations.

Without a structured adoption approach, security modernization programs can become fragmented, reactive, and difficult to sustain.

The Microsoft Security Adoption Framework (SAF) provides you with a structured security adoption model with standardized, repeatable, role-aware processes that help you plan, prioritize, and implement end-to-end security modernization across hybrid, multicloud, and multiplatform environments.

This framework aligns critical business outcomes, security disciplines, and solution implementations so that business leaders, security managers, architects, and practitioners can move forward together at a controlled and sustainable pace across the organization.

SAF helps you avoid common mistakes, often called [antipatterns](security-adoption-antipatterns), in your security modernization journey.

Tip

Microsoft offers a rich set of security adoption workshops - the *Security Adoption Framework (SAF) workshops*. Our structured adoption model guidance aligns with the expert-led guidance from Microsoft Unified delivered in those workshops. Learn more about [SAF workshops](workshop-business-overview).

## Adoption model structure

The adoption model is built on three core components that help organizations move from business intent to detailed implementation:

- **Business scenarios** define typical business outcomes and how security must be adapted to achieve them.
- **Security disciplines** define how teams organize, plan, and operate to modernize security and achieve business outcomes.
- **Technology pillars** describe organizational assets and resources that you want to secure. For example identity, devices, and data.

[![Diagram showing overall structure of the Microsoft Security Adoption Framework (SAF).](media/adoption-navigation-structure.png)](media/adoption-navigation-structure.png#lightbox)

## Why use an adoption model?

A structured adoption model helps you to:

- **Align with security best practices** - Align with [Zero Trust principles](zero-trust-overview), [Microsoft Secure Future Initiative (SFI) patterns](sfi/secure-future-initiative-overview), [open standards and guidance](security-zero-trust-frameworks), and [other security best practices](security-best-practices-overview).
- **Maximize existing investments** - Get value from your existing tools before introducing new capabilities.
- **Deliver an end-to-end security strategy** - Connect business priorities to security architecture, controls, processes, and operations.
- **Adapt continuously** - Evolve security posture and strategy as threats, business needs, and technologies change.
- **Prioritize action** - Provide practical role-specific guidance for teams and stakeholders, grounded in best practices, lessons learned, and real-world examples.

This diagram illustrates how SAF brings these elements together into a single adoption model.

[![Diagram showing how the adoption model includes learnings and guidance from Microsoft and external sources.](media/adoption-guidance-context.png)](media/adoption-guidance-context.png#lightbox)

## Enable roles with the adoption model

By organizing this guidance around common business scenarios, disciplines, and implementation steps, the model helps you move from isolated recommendations to a cohesive approach for planning, implementing, and measuring security improvements. Microsoft will continue to enrich the adoption model content over time.

Each component of the adoption model targets a specific audience and role.

| **Section** | **Primary audience** | **Aim** |
| --- | --- | --- |
| **[Business scenarios](security-adoption-business-scenarios-overview)** | Business leaders | Identify, define, and communicate critical business outcomes that security must support.Translate business priorities into actionable security goals that guide planning and decision-making.Provide practical, repeatable guidance for business outcomes, with clear paths to the roles and disciplines involved in delivering the outcome. |
| **[Security disciplines](security-adoption-discipline-overview)** | Security leaders and teams, IT leaders, designers, architects. | Bridge business scenarios and security deployment/implementation. Ensure that security investments and priorities translate into measurable outcomes through clear planning, architecture, and operational practices.Business scenarios usually map to multiple security disciplines. |
| **[Technology pillars](implement-overview)** | Technical and security implementers and partners. | Define what types of assets must be secured, and where Zero Trust principles and security controls must be applied.Connect security strategy to implementation by grouping related technologies, controls, and capabilities.Business scenarios are likely to cross multiple technology pillars. For example, if our business outcome is to improve security posture across the enterprise, then we must improve posture across devices, data, infrastructure, networks, and more. |

[![Diagram showing how the adoption model serves different roles across the organization.](media/adoption-model-roles.png)](media/adoption-model-roles.png#lightbox)

## Adoption guidance

Structured adoption guidance focuses on:

- End-to-end guidance across the security journey for common business-critical outcomes.
- Clear guidance for roles and security disciplines.
- Product-agnostic recommendations based on Zero Trust principles, Microsoft best practices, and external frameworks.
- Detailed implementation guidance using Microsoft security products and services.
- Alignment with Zero Trust principles and security best practices.

[![Diagram showing how the Security Adoption Framework (SAF) connects the business with security and technology.](media/adoption-journey.png)](media/adoption-journey.png#lightbox)

## Existing guidance integration

This adoption model brings together Microsoft security guidance that was historically published across multiple frameworks and resources, aligning it into a single, actionable structure.

It integrates and builds on established guidance, including these content sources:

- [Microsoft Cybersecurity Reference Architecture (MCRA)](microsoft-reference-architecture)
- [Security Development Lifecycle (SDL)](https://www.microsoft.com/securityengineering/sdl/practices).
- [Zero Trust](workshop-business-overview) and [CISO](workshop-business-security-leaders) workshops
- The [Immutable Laws of Security](security-adoption-discipline-architecture-tips)
- [Privileged access/workstation guidance](security-adoption-discipline-identity-access-privileged-model).
- [Incident response playbooks](security-operations-playbook-phishing)

[![Diagram showing how the adoption model integrates existing security content.](media/adoption-model-integrate-content.png)](media/adoption-model-integrate-content.png#lightbox)

## Additional SAF resources

Use these resources to complement the adoption model with focused guidance and workshop material:

- [SAF workshops overview](workshop-business-overview)
- [CISO workshop](workshop-business-security-leaders) and [videos](workshop-business-security-leaders-video)
- [Microsoft Cybersecurity Reference Architectures (MCRA)](microsoft-reference-architecture)
- [Avoid common security adoption antipatterns](security-adoption-antipatterns)
- [Rapidly modernize your security posture for Zero Trust](adopt/rapidly-modernize-security-posture)
- [Secure remote and hybrid work with Zero Trust](adopt/secure-remote-hybrid-work)
- [Identify and protect sensitive business data with Zero Trust](adopt/identify-protect-sensitive-business-data)
- [Meet regulatory and compliance requirements with Zero Trust](adopt/meet-regulatory-compliance-requirements)