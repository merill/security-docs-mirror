---
layout: Conceptual
title: Avoid common security adoption antipatterns | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-antipatterns
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Learn common security adoption antipatterns in the Microsoft Security Adoption Framework (SAF) and how to avoid them across disciplines.
ms.date: 2026-11-03T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 2242bb2e-7d85-ea9c-5b88-c806920d48c8
document_version_independent_id: 2242bb2e-7d85-ea9c-5b88-c806920d48c8
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-adoption-antipatterns.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-adoption-antipatterns
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-adoption-antipatterns.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: 990fc81a-0789-e56d-754a-1f4dd3739c18
---

# Avoid common security adoption antipatterns | Microsoft Learn

Security modernization can be slowed by recurring decision patterns that introduce avoidable risk, rework, and fragmentation. In the **Microsoft Security Adoption Framework (SAF)**, these recurring patterns are treated as antipatterns and are addressed by aligning business outcomes, security disciplines, and implementation decisions.

An **antipattern** is a commonly repeated approach that might seem effective in the short term but often leads to issues or failure over the long term. If you don't address these patterns, they can cause slowdowns or failures.

## Why antipatterns matter

Antipatterns commonly appear during high-pressure modernization efforts when local optimization is prioritized over end-to-end outcomes.

If you leave them unaddressed, they can:

- Delay or fragment security modernization.
- Increase operational overhead and tool sprawl.
- Reduce detection and response effectiveness.
- Create governance gaps and unclear accountability.

## Common cross-discipline antipatterns

Use this table to identify common antipatterns and the SAF guidance that helps address each one.

| **Antipattern area** | **Typical symptoms** | **SAF guidance** |
| --- | --- | --- |
| **Strategy and governance gaps** | Security decisions are reactive, inconsistent, or disconnected from business priorities. | [Establish Security Strategy, Integration, and Governance](security-adoption-discipline-strategy) and [engage business leaders in strategy](security-adoption-discipline-strategy-engage). |
| **Architecture fragmentation** | Technical solutions are deployed without an end-to-end architecture or clear integration model. | [Establish a Security Architecture discipline](security-adoption-discipline-architecture) and [review architecture antipatterns and tips](security-adoption-discipline-architecture-tips). |
| **Identity and access silos** | Identity, network, and privileged access are planned separately, producing inconsistent controls and user friction. | [Establish an Identity and Access discipline](security-adoption-discipline-identity-access) and [design a privileged access architecture](security-adoption-discipline-identity-access-privileged-model). |
| **SecOps tool-first execution** | Large volumes of telemetry are collected or tools are deployed without measurable detection and response outcomes. | [Establish a SecOps discipline](security-adoption-discipline-security-operations) and [avoid SecOps antipatterns](security-adoption-discipline-security-operations-common-issues). |
| **Posture without prioritization** | Findings accumulate but remediation focus is weak, resulting in little measurable risk reduction. | [Establish a Security Posture discipline](security-adoption-discipline-posture) and [improve posture and compliance outcomes](security-adoption-scenario-improve-posture). |
| **Implementation not tied to outcomes** | Controls are implemented without clear business-scenario mapping, resulting in uneven adoption and low confidence. | [Review business scenarios](security-adoption-business-scenarios-overview) and [connect scenarios to technologies](security-adoption-business-scenarios-technologies). |

## Use workshop resources

For teams that want structured facilitation, SAF workshops can help identify and correct antipatterns in planning and execution:

- [SAF workshops overview](workshop-business-overview)
- [CISO workshop](workshop-business-security-leaders)
- [SecOps workshop](workshop-business-security-operations)

## Download consolidated antipattern reference

Use this reference for discussion and planning sessions:

- [Common security antipatterns (PDF)](https://download.microsoft.com/download/5/d/3/5d3058a9-501b-4c13-9c95-9664c303bb97/antipatterns.pdf)