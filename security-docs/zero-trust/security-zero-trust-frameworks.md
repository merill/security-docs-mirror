---
layout: Conceptual
title: Map Zero Trust standards and frameworks to SAF | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-zero-trust-frameworks
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Find authoritative Zero Trust standards and framework mappings to Microsoft Security Adoption Framework disciplines, technologies, roles, and implementation guidance.
ms.date: 2026-11-09T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 4b20952a-71ee-bba4-9370-7b1cc16f708c
document_version_independent_id: 4b20952a-71ee-bba4-9370-7b1cc16f708c
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-zero-trust-frameworks.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-zero-trust-frameworks
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-zero-trust-frameworks.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 409881d4-0981-f95a-f8de-06f02fefe69b
---

# Map Zero Trust standards and frameworks to SAF | Microsoft Learn

Zero Trust is a security approach expressed through multiple industry and government standards, reference models, strategies, and maturity models. Each source answers a different question. The Microsoft Security Adoption Framework (SAF) mappings help organizations connect that external structure to security work, roles, technologies, architecture, and implementation guidance.

Use this page as a router. The mappings don't replace the authoritative sources, imply one-to-one structural equivalence with SAF, or by themselves demonstrate achievement, maturity, or compliance. Start with the canonical [Security standards and frameworks](security-standards-and-frameworks) hub for the broader relationship between standards, SAF, and implementation.

Tip

Microsoft offers expert-led Security Adoption Framework (SAF) workshops through Microsoft Unified. SAF guidance aligns with these workshops. Learn more about [SAF workshops](workshop-business-overview).

## Choose the source that fits the decision

| Source | Best used for | Continue to |
| --- | --- | --- |
| **NIST SP 800-207, Zero Trust Architecture** | A vendor-neutral definition of Zero Trust architecture, policy decision and enforcement concepts, deployment models, and use cases. | [NIST SP 800-207](https://csrc.nist.gov/pubs/sp/800/207/final) and [NIST SP 1800-35 implementation guidance](https://csrc.nist.gov/pubs/sp/1800/35/final) |
| **CISA Zero Trust Maturity Model** | Assessing progress across five pillars, three cross-cutting capabilities, and four maturity stages. | [CISA Zero Trust Maturity Model mapping and implementation guidance](cisa-zero-trust-maturity-model-intro) |
| **The Open Group Security and Zero Trust body of knowledge** | Connecting Zero Trust principles, capabilities, roles, collaboration models, and Architecture Building Blocks across business, security, and technology teams. | [The Open Group Zero Trust model mapping](/en-us/security/saf/framework-mappings/open-group-zero-trust) |
| **DoD Zero Trust Strategy** | Navigating U.S. Department of Defense Zero Trust pillars, capability areas, activities, and implementation outcomes. | [DoD Zero Trust Strategy mapping and implementation guidance](dod-zero-trust-strategy-intro) |

## NIST Zero Trust Architecture

[NIST SP 800-207](https://csrc.nist.gov/pubs/sp/800/207/final) defines an abstract Zero Trust architecture in which access to resources isn't implicitly trusted. It describes continuous, context-informed evaluation, policy decision logic, and enforcement close to protected resources.

[NIST SP 1800-35](https://csrc.nist.gov/pubs/sp/1800/35/final) provides implementation examples developed by the NIST National Cybersecurity Center of Excellence with collaborators, including Microsoft. Use it when moving from the SP 800-207 concepts to reference designs and technology integration.

## CISA Zero Trust Maturity Model

The [CISA Zero Trust Maturity Model](https://www.cisa.gov/zero-trust-maturity-model) organizes maturity around Identity, Devices, Networks, Applications and Workloads, and Data, with the cross-cutting capabilities Visibility and Analytics, Automation and Orchestration, and Governance.

Use the existing [CISA mapping and implementation guidance](cisa-zero-trust-maturity-model-intro) to connect these areas to relevant SAF security disciplines and technologies and then to Microsoft implementation guidance. CISA remains the authoritative source for maturity expectations.

## The Open Group Zero Trust model

The Open Group material provides an enterprise capability and integration perspective. It connects durable Zero Trust capabilities to security roles and to process and technology Architecture Building Blocks.

Some Open Group material is published, while the Zero Trust Reference Model and relevant Security Roles and Glossary material are evolving through the Snapshot release process. Snapshot documents are draft standards that publish interim direction for feedback before any formal standard publication. Use the [dedicated Open Group mapping](/en-us/security/saf/framework-mappings/open-group-zero-trust) for current publication-status notes, capability and role graphics, SAF mappings, and detailed ABB-to-Microsoft technology examples.

## DoD Zero Trust Strategy

The U.S. Department of Defense publishes the authoritative DoD Zero Trust Strategy, supporting architecture, and execution guidance.

Use the existing [DoD mapping and implementation guidance](dod-zero-trust-strategy-intro) to navigate from DoD Zero Trust pillars and capability areas to relevant SAF security disciplines and technologies, then continue to Microsoft implementation guidance. The mapping doesn't claim a capability-by-capability or activity-by-activity structural crosswalk.