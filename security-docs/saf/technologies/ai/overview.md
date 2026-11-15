---
layout: Conceptual
title: Secure AI with Zero Trust | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/saf/technologies/ai/overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Learn how to secure AI systems and agents with Zero Trust principles in the Microsoft Security Adoption Framework (SAF).
ms.date: 2026-11-04T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: b7b000e8-9a7f-fd0f-e9a0-c9222e929b4a
document_version_independent_id: b7b000e8-9a7f-fd0f-e9a0-c9222e929b4a
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/saf/technologies/ai/overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../../../zero-trust/toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: saf/technologies/ai/overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/saf/technologies/ai/overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: 15245f0b-c33e-9a8e-e09a-184d47ca5b8f
---

# Secure AI with Zero Trust | Microsoft Learn

AI systems are now part of the core enterprise technology estate, including AI applications, agents, models, and the data and services they use. As organizations adopt AI, these systems introduce new access paths, dependencies, and risk conditions that must be governed as part of end-to-end security architecture.

In the Microsoft Security Adoption Framework (SAF), the AI pillar applies Zero Trust principles to AI workloads and operations: verify explicitly, use least privilege, and assume compromise. This guidance helps you protect AI capabilities while supporting business outcomes, operational reliability, and continuous improvement.

## What this technology pillar covers

This pillar focuses on securing AI systems as workloads and business-critical resources, including:

- AI applications and systems
- AI agents and agent runtimes
- AI and agent identities
- Models, prompts, and context
- Data used for grounding, training, and inference
- Tools, plugins, connectors, and external dependencies
- Agent-to-agent and agent-to-service communications
- AI infrastructure and hosting environments

## Core Zero Trust control areas for AI

Use this pillar to plan and implement controls across these areas, aligned to the implementation areas in the [AI security workshop](/en-us/security/zero-trust/workshop-zero-trust-ai-security):

1. **Map and assess AI risk**
    - Discover and inventory AI applications, agents, and services.
    - Prioritize risks and establish ownership, governance, and acceptable-use guardrails.
    - Continuously monitor risk signals and adjust priorities as usage evolves.
2. **Register agents and enforce lifecycle governance**
    - Register agents in a centralized inventory.
    - Classify agents by purpose, business criticality, and risk.
    - Define ownership, publishing, certification, and lifecycle controls.
3. **Secure AI authentication and access**
    - Require strong authentication and authorization for users, services, and agents.
    - Apply least privilege and delegated permissions for agent actions.
    - Continuously evaluate identity, device, and risk signals before and during access.
4. **Secure AI network and service access**
    - Control how AI services are reached across network paths and service boundaries.
    - Apply segmentation, filtering, and inspection for AI interactions.
    - Reduce exposure to prompt injection and unauthorized access paths.
5. **Secure AI data access and usage**
    - Classify and protect data used in prompts, context, grounding, and outputs.
    - Apply data loss prevention and usage controls to reduce oversharing and exfiltration risk.
    - Enforce governance and compliance policies for AI data handling.
6. **Build and deploy agents securely**
    - Secure AI apps, APIs, connectors, and tool-chain dependencies.
    - Validate trust boundaries and runtime controls before production use.
    - Apply secure development, testing, and release controls for AI-enabled systems.
7. **Detect and respond for AI**
    - Monitor AI activity, prompt flows, access patterns, and tool usage.
    - Detect misuse, anomalous behavior, and policy violations.
    - Integrate AI telemetry into incident detection, investigation, and response workflows.

## How this pillar connects to SAF

AI security relies on other SAF technologies and security disciplines:

- **Technologies**: [Identity](/en-us/security/zero-trust/deploy/identity), [Endpoints](/en-us/security/zero-trust/deploy/endpoints), [Applications](/en-us/security/zero-trust/deploy/applications), [Data](/en-us/security/zero-trust/deploy/data), [Infrastructure](/en-us/security/zero-trust/deploy/infrastructure), and [Network](/en-us/security/zero-trust/deploy/networks).
- **Security disciplines**: [Development](/en-us/security/zero-trust/security-adoption-discipline-development) for secure engineering practices and [SecOps](/en-us/security/zero-trust/security-adoption-discipline-security-operations) for detection and response operations.
- **Business scenarios**: [Adopt and secure AI](/en-us/security/zero-trust/security-adoption-scenario-secure-ai).

## Workshop and implementation guidance

- [AI security in the Microsoft Zero Trust Workshop](/en-us/security/zero-trust/workshop-zero-trust-ai-security)
- [Build a strong AI posture](/en-us/security/security-for-ai/posture)
- [Prepare for AI security](/en-us/security/security-for-ai/prepare)
- [Discover AI apps and data](/en-us/security/security-for-ai/discover)
- [Protect AI apps and data](/en-us/security/security-for-ai/protect)