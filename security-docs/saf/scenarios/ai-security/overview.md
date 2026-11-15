---
layout: Conceptual
title: AI security transformation themes in SAF | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/saf/scenarios/ai-security/overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Understand the imperative to secure both classic and AI-era security outcomes and use SAF to execute consistently.
ms.date: 2026-11-08T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 17da4563-6124-7b17-0822-daaf11586eab
document_version_independent_id: 17da4563-6124-7b17-0822-daaf11586eab
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/saf/scenarios/ai-security/overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../../../zero-trust/toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: saf/scenarios/ai-security/overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/saf/scenarios/ai-security/overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/43093068-2dda-408b-b3fe-dfd705c84f78
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e453d60d-ba7e-43bc-8028-ec38e6b62512
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 0eb980a5-2e62-c85c-c0c4-dac7943f24f1
---

# AI security transformation themes in SAF | Microsoft Learn

Organizations are now operating in a hybrid AI and classic security environment where they must manage both familiar risks and new AI-driven risks at the same time. A practical way to do this is to focus on three connected security themes: secure your foundations, defend with agents, and secure your agentic insider.

This theme structure helps leaders and practitioners prioritize outcomes, explain tradeoffs, and coordinate execution across business, security, and technology teams. The operating imperative is balance: left-of-bang prevention and right-of-bang response, machine-speed automation and human judgment, and innovation and control.

These themes reinforce each other. Strong security foundations make AI adoption safer and provide the identity, data, telemetry, architecture, and operational capabilities needed to use AI effectively in defense. Securing AI introduces new requirements that must be integrated into those foundations, while agents and automation can help security teams operate at greater speed and scale.

SAF provides a durable execution model for turning changing security priorities into sustained outcomes. It connects business priorities and risk to security work, technologies, technical solutions, roles, and implementation guidance. Microsoft product guidance then provides the detailed steps for configuring and operating the required capabilities.

Use [AI security in the Security Adoption Framework](/en-us/security/saf/foundations/ai-security-governance) to understand how these transformation themes connect to SAF business scenarios, security disciplines, technologies, the Microsoft Zero Trust Workshop, and implementation guidance.

## Why these three themes matter

- [Secure your foundations](/en-us/security/saf/scenarios/ai-security/security-foundations) focuses on risk reduction across posture, identity, secrets, data, and governance so AI adoption does not outpace control maturity.
- [Defend with agents](/en-us/security/saf/scenarios/ai-security/agent-assisted-defense) focuses on defensive speed and quality so organizations can detect, investigate, and respond at machine tempo with human oversight.
- [Secure your agentic insider](/en-us/security/saf/scenarios/ai-security/ai-agent-security) focuses on constraining autonomous behavior so AI identities, actions, and data access stay within policy and accountability boundaries.

## How the themes relate to each other

These themes are interdependent, not sequential silos. Foundations make trusted automation possible. Agent-assisted defense improves detection and response for both classic and AI-native threats. Agentic-insider controls ensure that increased automation and autonomy do not create unmanaged internal risk. Together they create a durable model that can scale AI safely.

## How SAF enables execution

SAF connects business priorities and risk to execution through four connected components:

1. **Business scenarios** frame desired outcomes in plain language for business, security, and technology stakeholders.
2. **Security disciplines** organize the security work needed to manage risk and deliver and sustain those outcomes.
3. **Technologies** identify what must be protected across identity, endpoints, applications, data, infrastructure, network, and AI.
4. **Technical solutions** translate requirements into product-level implementation and sustainable operations.

Development and SecOps are security disciplines that shape and operate protections across technologies; they aren't technology pillars. Use [technology guidance](/en-us/security/zero-trust/deploy/overview) to determine **where** controls apply and [technical solutions](/en-us/security/zero-trust/implement-overview) for **how** to implement and operate them.

SFI provides important vendor transformation lessons and trust signals, while SAF provides the customer execution map. Use both together to connect strategy, foundations, and cutting-edge capabilities without creating a parallel framework.