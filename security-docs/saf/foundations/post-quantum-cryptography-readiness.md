---
layout: Conceptual
title: Plan cryptographic agility and post-quantum readiness | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/saf/foundations/post-quantum-cryptography-readiness
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Learn how to use SAF to plan cryptographic agility and post-quantum readiness across strategy, architecture, and operations.
ms.date: 2026-11-04T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 00a2ad89-bd63-39bb-5455-bfb5a6f7f55f
document_version_independent_id: 00a2ad89-bd63-39bb-5455-bfb5a6f7f55f
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/saf/foundations/post-quantum-cryptography-readiness.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../../zero-trust/toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: saf/foundations/post-quantum-cryptography-readiness
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/saf/foundations/post-quantum-cryptography-readiness.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/5287f575-02f0-405f-92b7-800456526b0c
- https://authoring-docs-microsoft.poolparty.biz/devrel/68cb9039-df60-49b0-8ef8-89ad96497f63
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/06e86142-34c2-4b94-ab9c-9477c21f7152
- https://authoring-docs-microsoft.poolparty.biz/devrel/725b6df3-93e8-472d-834e-e7e0d2953d35
platformId: bc6d65d3-4d56-f40f-c37b-780db7ad418c
---

# Plan cryptographic agility and post-quantum readiness | Microsoft Learn

This article is part of the Microsoft Security Adoption Framework (SAF) concept and reference guidance.

Post-quantum readiness is primarily a cryptographic agility challenge: your organization must be able to discover, prioritize, and update cryptographic dependencies over time at enterprise scale.

Cryptographic agility is the ability of an organization to rapidly and safely change which cryptographic algorithms it uses. Building this capability is foundational for becoming quantum-safe.

The likelihood is increasing that quantum computing will eventually defeat some current cryptographic algorithms that underpin technical controls across modern environments. This topic is commonly referred to as post-quantum cryptography (PQC).

## How this impacts security and organizational risk

If quantum-capable attackers can break vulnerable public-key cryptography in use, they can undermine trust in core security controls and significantly increase organizational risk.

Cryptography provides foundational trust for much of the technology environment. Authentication, digital signatures, software integrity, and secure communications such as TLS depend directly on cryptography, while many other security controls depend indirectly on those capabilities. This means post-quantum readiness affects far more than encryption: it can affect identities, applications, infrastructure, devices, software updates, communications, and the trust relationships between them.

PQC readiness affects almost all security domains because authentication, signing, and encryption are embedded across:

- Cloud and on-premises applications
- Identity and access systems
- Security service edge (SSE) and VPN infrastructure
- Network, storage, and platform infrastructure
- IoT and OT systems
- Partner and supply-chain integrations

## What causes this challenge

Current cryptography depends on hard mathematical problems that are practical in one direction and difficult to reverse with classical computing.

Quantum computing changes this balance for some algorithm families. As capability matures, organizations need to:

1. Identify vulnerable algorithms and dependencies.
2. Replace them with quantum-resistant alternatives.
3. Maintain readiness to evolve again as standards and implementation guidance continue to mature.

This is why cryptographic agility is critical, not optional.

The objective isn't only to replace today's vulnerable algorithms. Organizations need the ability to change cryptography repeatedly as standards, threats, implementations, and cryptanalytic understanding evolve. **PQC creates the immediate migration need; cryptographic agility creates the durable ability to adapt as cryptography changes again.**

## How urgent is quantum-safe planning

Two factors make early action important:

- **Transition lead time is long**: large estates need multiyear planning, dependency mapping, and phased rollout.
- **Harvest now, decrypt later risk exists now**: long-lived sensitive data can be captured today and decrypted later.

At an operational level, becoming quantum-safe is a large-scale software, hardware, and infrastructure modernization program. Cryptography is embedded throughout operating systems, applications, services, protocols, certificates, libraries, firmware, devices, and partner dependencies. Organizations should therefore treat PQC readiness as a multiyear migration rather than a single cryptographic upgrade.

Starting early can also help organizations avoid resource and supply constraints as adoption accelerates. Some changes might require only software or configuration updates, while others might require new libraries, firmware, certificates, hardware, or replacement of systems whose vendors no longer provide suitable updates. Many organizations could need the same specialized products and services at roughly the same time.

This creates a dynamic similar to preparing for a natural disaster: organizations that prepare early can obtain the resources they need deliberately, while organizations that wait until urgency is widespread might face shortages, higher costs, limited alternatives, and increased exposure to low-quality products or scams.

Delaying increases the chance of compressed timelines, supplier constraints, and rushed implementation risk.

## SAF approach for PQC readiness

Use SAF to coordinate cross-functional execution:

1. **Strategy and governance**: establish ownership, sponsorship, priorities, and risk tolerance.
2. **Architecture**: build enterprise cryptography and trust-chain inventory and dependency maps.
3. **Disciplined execution**: sequence changes by risk, business criticality, and attack-path impact.
4. **Operations and validation**: monitor rollout quality, regressions, and control effectiveness.

## Planning a quantum-safe program

A practical transition plan should include:

1. **Discover** where vulnerable algorithms are used and which systems depend on them.
2. **Evaluate** vendor and platform support timelines for quantum-resistant options.
3. **Plan** phased migration waves and rollback-safe change windows.
4. **Implement** with governance, testing, and evidence tracking.

Additional planning considerations:

- **Treat this as a program**: PQC readiness spans multiple teams and disciplines.
- **Prepare for different update types** - Migration paths can vary significantly. Some dependencies can be addressed through software or configuration updates, while others might require new cryptographic libraries, certificates, firmware, hardware, or replacement of systems whose vendors no longer provide suitable updates. Track vendor support and quantum-resistant implementation timelines as part of migration planning.
- **Prioritize strategically**: focus first on high-value assets, identity/control planes, core trust services, and long-sensitivity data paths.