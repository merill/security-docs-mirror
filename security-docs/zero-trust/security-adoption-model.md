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
description: Learn how the Microsoft Security Adoption Framework (SAF) connects business priorities, risk, Zero Trust principles, security disciplines, technologies, and implementation guidance.
ms.date: 2026-11-06T00:00:00.0000000Z
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

The Microsoft Security Adoption Framework (SAF) is a practical operating model for turning business priorities, risk, and Zero Trust principles into coordinated action. It connects business, technology, and security roles across strategy, architecture, implementation, and operations.

Use SAF to define shared outcomes, clarify responsibilities, select the disciplines and technologies that matter, implement protections, and measure progress across hybrid, multicloud, and multiplatform environments.

[![Diagram showing the four connected SAF components: business scenarios, security disciplines, technologies, and technical solutions, with roles and Zero Trust principles applying across the framework.](media/adoption-navigation-structure.png)](media/adoption-navigation-structure.png#lightbox)

## Why use SAF?

Use SAF to:

- **Align security work to business priorities and risk.** Connect business, technology, and security decisions and investments to the outcomes the organization needs to achieve and protect.
- **Coordinate shared responsibility.** Clarify how business, technology, and security roles make decisions and deliver outcomes together.
- **Apply Zero Trust consistently.** Use Zero Trust principles across strategy, governance, architecture, implementation, and operations.
- **Connect strategy to implementation.** Link desired outcomes to security disciplines, technologies, and technical solutions.
- **Measure progress and adapt.** Track results and adjust as business needs, technology, threats, and organizational capabilities change.

## How SAF works

SAF connects business priorities and risk to coordinated security work and technology implementation. Four connected components help business, technology, and security teams understand desired outcomes, the security work needed, what must be protected, and how protections are implemented and operated.

The four components are:

- **[Business scenarios](security-adoption-business-scenarios-overview)** connect important business or technology initiatives to desired outcomes and risk.
- **[Security disciplines](security-adoption-discipline-overview)** organize the security work needed to manage risk, make decisions, and improve security capabilities.
- **[Technologies](deploy/overview)** identify what must be protected, including identities, endpoints, applications, data, infrastructure, networks, and AI.
- **[Technical solutions](implement-overview)** translate security requirements into implementation and sustainable operations across products and platforms.

Business priorities and risk provide context. Business scenarios describe desired outcomes. Security disciplines organize how teams work. Technologies identify what must be protected. Technical solutions turn this direction into implementation and operations.

Zero Trust principles inform decisions across all four SAF components—from business priorities and governance through architecture, implementation, and operations.

## How roles use SAF

| Role group | How the group uses SAF | Common SAF focus |
| --- | --- | --- |
| **Business leaders and risk owners** | Define desired outcomes, business priorities, risk, accountability, and measures of success. | [Business scenarios](security-adoption-business-scenarios-overview), strategy, and risk |
| **Technology and product teams** | Translate priorities and security requirements into architecture, engineering, delivery, implementation, and sustainable operations. | [Technologies](deploy/overview) and [technical solutions](implement-overview) |
| **Security teams** | Provide risk insight, security expertise, governance, architecture, guardrails, validation, detection and response, and security measurement. | [Security disciplines](security-adoption-discipline-overview) and security requirements |

These roles contribute to shared outcomes and collaborate to achieve them. SAF provides shared context to help business, technology, and security roles coordinate decisions and responsibilities rather than treating security modernization as the work of a single team. Partners can contribute specialized expertise, implementation, and operational services.

## Choose where to start

You don't need to use SAF in a fixed sequence. Choose a starting point that matches your current context:

- **[Start with strategy and transformation](security-adoption-discipline-strategy)** when there's leadership sponsorship for coordinated modernization and the organization needs shared strategic direction.
- **[Start with a priority risk or problem](security-adoption-discipline-posture)** when an urgent gap or high-value opportunity needs attention.
- **[Start with a business or technology initiative](security-adoption-business-scenarios-overview)** when a specific initiative needs coordinated protection across roles, disciplines, and technologies.
- **[Start with a security standard or framework](security-standards-and-frameworks)** when the organization must align security work to defined objectives or practices.

These starting points are common, not required stages. Organizations can combine them or move between them as priorities, risks, and capabilities change.

### Guidelines for using SAF effectively

Organizations can use SAF in different ways depending on their priorities, risks, and current security maturity. Regardless of where you start:

- **Align work to business priorities and risk.**
- **Apply Zero Trust principles across business decisions, security practices, technology design, delivery, and operations.**
- **Coordinate responsibilities across business, technology, and security teams.**
- **Connect focused improvements to broader security strategy and architecture.**
- **Measure outcomes and adapt as priorities, risks, and conditions change.**

For goal-based and role-based reading paths, see [Using SAF effectively](security-adoption-journey).

## How existing security guidance fits into SAF

SAF builds on established Microsoft security guidance rather than replacing it. Some existing guidance is incorporated into the SAF structure, while other resources remain independent and complement SAF with deeper architecture, engineering, assessment, workshop, or operational guidance.

[![Diagram showing how SAF integrates selected guidance and connects to complementary Microsoft security guidance.](media/adoption-guidance-context.png)](media/adoption-guidance-context.png#lightbox)

Microsoft provides complementary guidance in several areas:

- **Strategy and architecture:**[CISO workshop](workshop-business-security-leaders) and [Microsoft Cybersecurity Reference Architectures (MCRA)](microsoft-reference-architecture)
- **Assessment and technology implementation:**[Zero Trust assessment](assessment/overview) and [technology implementation guidance](deploy/overview)
- **Engineering:**[Microsoft Security Development Lifecycle (SDL)](https://www.microsoft.com/securityengineering/sdl/), [DevSecOps Capability Model](/en-us/devops/devsecops/capability-model), and [Secure Future Initiative (SFI)](sfi/secure-future-initiative-overview)
- **Operations and response:**[Privileged access guidance](/en-us/security/privileged-access-workstations/overview) and [incident-response playbooks](security-operations-incident-response-playbooks)

For details on how these and other Microsoft security resources relate to SAF, see [How existing security guidance fits into SAF](security-adoption-existing-guidance).

## Explore SAF

- [Using SAF effectively](security-adoption-journey).
- [Explore business scenarios](security-adoption-business-scenarios-overview).
- [Explore security disciplines](security-adoption-discipline-overview).
- [Secure technologies](deploy/overview).
- [Implement technical solutions](implement-overview).
- [Use SAF workshops](workshop-business-overview).