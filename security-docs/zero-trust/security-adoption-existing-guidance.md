---
layout: Conceptual
title: How existing security guidance fits into SAF | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-existing-guidance
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Learn how established Microsoft security guidance relates to the Microsoft Security Adoption Framework (SAF) and where to use each resource.
ms.date: 2026-11-06T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 41486e12-9a07-8a3b-6664-e4bac9121502
document_version_independent_id: 41486e12-9a07-8a3b-6664-e4bac9121502
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-adoption-existing-guidance.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-adoption-existing-guidance
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-adoption-existing-guidance.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: 081aa481-2faf-afb0-d2cc-198a37683945
---

# How existing security guidance fits into SAF | Microsoft Learn

The Microsoft Security Adoption Framework (SAF) builds on established Microsoft security guidance rather than replacing it. SAF provides the adoption structure that connects business outcomes, roles, security disciplines, technologies, and technical solutions.

Existing guidance relates to SAF in three ways:

- **Integrated into SAF:** Relevant concepts or guidance are incorporated into SAF. Start with the corresponding SAF content.
- **SAF-aligned experience:** The resource helps stakeholders apply SAF through facilitated planning, assessment, or decision-making.
- **Companion guidance:** The resource remains independent and provides specialized depth for architecture, engineering, implementation, or operations.

The relationships in this article identify useful reading and implementation paths. They aren't compliance mappings or statements of equivalence.

[![Diagram showing how SAF integrates selected guidance and connects to complementary Microsoft security guidance.](media/adoption-guidance-context.png)](media/adoption-guidance-context.png#lightbox)

## Guidance mapping

| Existing Microsoft guidance | Where it fits in SAF | Relationship to SAF |
| --- | --- | --- |
| **[CISO workshop](workshop-business-security-leaders)** | [Strategy, integration, and governance](security-adoption-discipline-strategy) | **Integrated component of SAF.** Provides strategy, program, and governance guidance for security leaders. |
| **[Microsoft Cybersecurity Reference Architectures (MCRA)](microsoft-reference-architecture)** | [Security architecture](security-adoption-discipline-architecture) | **Integrated component of SAF.** Provides reference architectures and technical planning guidance across security disciplines and technologies. |
| **[Immutable Laws of Security](security-adoption-discipline-architecture-tips)** | [Security architecture](security-adoption-discipline-architecture) and [security disciplines](security-adoption-discipline-overview) | **Integrated component of SAF.** Provides durable security design principles used to inform and validate security decisions. |
| **[Privileged access guidance](/en-us/security/privileged-access-workstations/overview)** | [Access and identity](security-adoption-discipline-access-identity.md) | **Integrated component of SAF.** Provides guidance for protecting privileged access, including privileged access workstations and related controls. |
| **[Microsoft Security Development Lifecycle (SDL)](https://www.microsoft.com/securityengineering/sdl/)** | [Development security](security-adoption-discipline-development) | **Complements SAF.** Provides deeper engineering practices and lifecycle guidance for secure development. |
| **[Incident-response playbooks](security-operations-incident-response-playbooks)** | [Security operations (SecOps)](security-adoption-discipline-security-operations) | **Integrated component of SAF.** Provides operational guidance for preparing for and responding to security incidents. |
| **[SAF workshops](workshop-business-overview)** | [Multiple security disciplines](security-adoption-discipline-overview) | **Integrated component of SAF.** Provides facilitated planning, stakeholder alignment, decision-making, and roadmap development across multiple SAF disciplines. |
| **[Zero Trust assessment](assessment/overview)** | [Technologies](deploy/overview) and [technical solutions](implement-overview) | **Complements SAF.** Helps organizations assess and improve implementation of Zero Trust technology controls. |

## Use the mapping

Integrated components such as the CISO workshop, MCRA, privileged access guidance, the Immutable Laws of Security, and incident-response playbooks contribute directly to SAF disciplines and guidance. Other resources, such as SDL and the Zero Trust assessment and workshops, complement SAF with deeper engineering, assessment, and implementation guidance.

Use these resources as part of an integrated security program rather than as separate or competing frameworks. SAF provides the organizing model that connects this guidance to business outcomes, security disciplines, technologies, roles, and implementation.