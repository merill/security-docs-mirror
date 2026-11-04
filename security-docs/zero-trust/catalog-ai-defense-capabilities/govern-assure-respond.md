---
layout: Conceptual
title: 1. Govern, Assure, and Respond | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/catalog-ai-defense-capabilities/govern-assure-respond
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: ridive
author: richarddiver-ms
description: Enterprise governance, assurance, and incident-response capabilities for managing AI risk, controlling autonomous actions, and aligning AI systems with leading security frameworks
ms.date: 2026-07-28T00:00:00.0000000Z
ms.custom: msecd-doc-authoring-1012
ms.topic: concept-article
ms.service: security
ms.subservice: zero-trust
locale: en-us
document_id: 1fed2221-801b-3fe5-25fb-44cf8aca58b8
document_version_independent_id: 1fed2221-801b-3fe5-25fb-44cf8aca58b8
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/catalog-ai-defense-capabilities/govern-assure-respond.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/catalog-ai-defense-capabilities/govern-assure-respond
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/catalog-ai-defense-capabilities/govern-assure-respond.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/0850fefd-e402-4507-ae98-46cfdfc2e16c
- https://authoring-docs-microsoft.poolparty.biz/devrel/57eae111-0f3b-497e-be07-450fd1409dea
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/de19c5b8-e208-412e-9238-db3f631dea5b
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/6ecf98a5-97c7-4249-b209-a9d9e42633a0
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ac8bf8ab-8134-4c9a-9f2e-58b31575b492
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ea7bf5d6-7154-4ba9-8ebc-59117ccacd49
platformId: 9aee6559-9a41-238b-c913-68973cecedba
---

# 1. Govern, Assure, and Respond | Microsoft Learn

## What this group defends against

The organizational layer ties every scenario together: unmanaged autonomy, overreliance on AI outputs, weak ownership of AI risk, regulatory noncompliance, and the absence of a repeatable way to model, test, and recover from AI-specific failures. It is the home for agentic-AI risk principles such as task adherence, human oversight, intelligibility, and disclosure, and for AI threat modeling as an ongoing engineering discipline rather than a one-time checklist.

## Core capabilities

Effective governance makes AI risk an owned, repeatable lifecycle discipline rather than a collection of isolated technical controls. The enterprise should define acceptable use, regulatory and policy obligations, accountability, assurance criteria, human-oversight requirements, and response processes from procurement through deployment and decommissioning. Threat modeling, evaluation, documentation, inventory, and incident preparedness should operate as a continuous feedback loop so new capabilities, integrations, and failure modes are assessed as the system changes.

- **Design for accountable use:** define owners, decision rights, human review points, disclosure requirements, and limits on autonomous action.
- **Assure continuously:** maintain model cards and system documentation, conduct AI threat modeling, red-team and test/evaluate/validate/verify (TEVV) activities, and preserve evidence of release decisions. Attest each agent’s identity, configuration, permissions, and policy state before broad release; certify expected behavior for high-impact workflows; re-attest on change to detect drift or unauthorized modification; and classify agents into risk tiers by data access, tool access, and business impact so the highest-risk agents receive the strongest controls.
- **Govern autonomous actions by risk tier:** classify actions by business impact and reversibility, and require graduated controls as impact rises—approval chains, dual authorization, deterministic validation before execution, reversible-only constraints, action replay for reconstruction, and an emergency-stop path that can halt or roll back a workflow already in progress.
- **Prepare to respond:** maintain an AI asset inventory and AI-BOM, rehearse incident playbooks and kill switches, and limit unnecessary public release of technical or model details.

## Which technologies do we use?

This control family depends on a coordinated technology stack rather than a single governance product. The platforms and implementation practices below combine enterprise data-risk visibility, centralized AI inventory and oversight, repeatable evaluation and guardrails, and auditable evidence so policy requirements can be translated into enforceable controls and operational response.:

- **Microsoft Purview Data Security Posture Management (DSPM)** — a data-security and compliance platform that discovers sensitive data, assesses oversharing and exposure, and brings together DLP, information protection, insider-risk, audit, and investigation signals. For AI systems, use its AI dashboards, data-risk assessments, policy recommendations, and activity visibility to identify risky prompts, responses, agent access, and sensitive-data use.
- **Microsoft Foundry Control Plane** — the centralized management interface for an enterprise fleet of AI agents, models, and tools. Its useful capabilities here are inventory, cross-project observability, guardrail-policy enforcement, compliance views, prohibited-behavior tracking, cost and token oversight, and integration with Microsoft Defender, Purview, and Entra.
- **Foundry evaluations and guardrails** — built-in services for testing model and agent quality and applying safety controls. Use repeatable evaluations, content filters, Prompt Shields, policy checks, and deployment-level guardrail configurations to verify intended behavior before release and detect regressions after changes.
- **AI asset inventory and AI-BOM** — not a single product, but a maintained record of the models, datasets, prompts, agents, tools, APIs, owners, versions, dependencies, and deployment locations that make up an AI system. Implement it by combining Foundry inventory, Azure Machine Learning registries, software bills of materials, data catalogs, and configuration-management records.
- **Logging, attribution, and audit trails** — an instrumentation pattern rather than a standalone product. Preserve the initiating user or agent, system and user prompts, retrieved context, model and version, safety decisions, tool calls, approvals, outputs, and correlation IDs in tamper-resistant stores so incidents can be reconstructed and controls can be evidenced.

## Framework mapping

**[OWASP Top 10 for LLM and Generative AI](https://genai.owasp.org/llm-top-10/) (2025)**: Maps to LLM06 Excessive Agency and LLM09 Misinformation. Governance, approval gates, human oversight, disclosure, red-teaming, and incident response reduce unmanaged autonomy and help prevent users or downstream processes from treating incorrect or misleading model output as authoritative.

**[MITRE ATLAS](https://atlas.mitre.org/mitigations)**: Maps to AML.M0000 Limit Public Release of Information, AML.M0001 Limit Model Artifact Release, and the current AML.M0023 AI Bill of Materials mitigation, together with organizational threat modeling, assurance, incident response, and accountable ownership. These practices reduce reconnaissance value, improve preparedness, and make AI risk management repeatable across the lifecycle.

**[NIST AI RMF 1.0 and NIST AI 600-1](https://www.nist.gov/itl/ai-risk-management-framework)**: Supports the **GOVERN** and **MANAGE** functions by defining accountability, policy, risk ownership, compliance obligations, lifecycle standards, documented oversight, incident response, and feedback loops. The Generative AI Profile adds suggested actions for transparency, human oversight, evaluation, monitoring, and recovery from generative-AI-specific failures.