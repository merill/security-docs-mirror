---
layout: Conceptual
title: Microsoft Zero Trust Workshop - AI security | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/workshop-zero-trust-ai-security
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Learn about the AI security pillar in the Microsoft Zero Trust Workshop
ms.date: 2026-11-12T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 3baaa249-dbc8-33a3-9d1f-23d2adfe4257
document_version_independent_id: 3baaa249-dbc8-33a3-9d1f-23d2adfe4257
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/workshop-zero-trust-ai-security.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/workshop-zero-trust-ai-security
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/workshop-zero-trust-ai-security.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/64b65f6c-101f-411a-9b83-9f577fab52d0
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/1a667fd1-8145-4b11-af0f-9f5de205a6e5
platformId: 718678de-dfdf-2f6a-6054-a7593e78a2d1
---

# Microsoft Zero Trust Workshop - AI security | Microsoft Learn

AI amplifies existing security risks and introduces new risks across identities, data, applications, infrastructure, models, agents, tools, memory, and user interactions. Applying Zero Trust principles helps organizations verify access explicitly, minimize privileges and data exposure, and assume that AI systems and their dependencies can be misused or compromised.

The AI security workshop pillar helps organizations discover and govern AI usage, secure users and agent identities, protect prompts, grounding data and outputs, control network and tool access, build and operate agents securely, validate AI quality and safety, and integrate AI-specific signals into security operations. The Workshop turns these capabilities into a prioritized implementation roadmap.

The AI security workshop pillar corresponds to the AI technology defined in the [Microsoft Security Adoption Framework (SAF)](deploy/overview).

## Why focus on AI security?

AI systems can act on behalf of users, access large volumes of organizational data, invoke tools and APIs, retain memory, and produce content at scale. Weak ownership, excessive permissions, data oversharing, unapproved applications, insecure agent development, prompt injection, unsafe tool use, or insufficient monitoring can extend existing attack paths and create new ones. AI security therefore requires coordinated controls across identity, data, network, infrastructure, applications, DevSecOps, compliance, and security operations.

The expected output is an actionable backlog of AI security projects prioritized into First, Then, and Next based on risk, dependencies, implementation effort, user impact, licensing, regulatory requirements, and readiness.

## AI security implementation areas

| **Area** | **Details** |
| --- | --- |
| **Establish AI security governance and accountability** | Define AI security principles, acceptable-use policies, risk ownership, privileged administrative roles, approval and exception processes, regulatory and compliance mappings, documentation requirements, and measurable outcomes across business, technology, security, privacy, legal, and compliance stakeholders. |
| **Discover and assess AI applications, agents, models, and workloads** | Create a consolidated inventory across Microsoft and external platforms, including generative AI applications, agents, models, endpoints, workload identities, and local or shadow AI. Classify criticality and risk, assign owners, review findings, delegate remediation, and maintain continuous monitoring. |
| **Register and govern AI agents throughout their lifecycle** | Use Agent 365 Registry or appropriate alternatives to register, classify, organize, publish, certify, activate, update, suspend, and retire agents. Assign sponsors and owners, establish governance templates and collections, synchronize external registries where supported, and automate registry management at scale. |
| **Secure users, agent identities, and privileged administration** | Require supported user authentication, use dedicated agent identities rather than shared credentials, and apply least privilege, Conditional Access, risk-based controls, custom security attributes, identity governance, access packages, lifecycle workflows, and Privileged Identity Management to users, agents, workload identities, and administrators. |
| **Govern agent access to resources, tools, and other agents** | Define approved resources, connectors, plugins, actions, MCP servers, and connected-agent scenarios. Scope permissions by agent purpose and risk, require approval for high-impact capabilities, apply Copilot Studio data policies where appropriate, and review access as agents and dependencies change. |
| **Secure network paths and AI gateways** | Route supported AI and agent traffic through identity-aware network controls such as Global Secure Access and secure AI or API gateways. Apply filtering, segmentation, rate limits, token controls, egress restrictions, prompt inspection, and protections for custom LLM endpoints and MCP servers. |
| **Protect prompts, grounding data, outputs, and agent memory** | Use Microsoft Purview capabilities such as Data Security Posture Management for AI, sensitivity labels, Data Loss Prevention, audit, collection policies, insider-risk controls, retention, and communication compliance. Reduce oversharing, protect grounding sources and embedded content, govern output-label inheritance, and define isolation, provenance, retention, deletion, and observability requirements for agent memory. |
| **Manage AI application discovery and sanctioned use** | Use Microsoft Defender for Cloud Apps, endpoint controls, and organizational policy to discover generative AI applications and local agents, classify sanctioned and unsanctioned services, manage access, and block or restrict high-risk applications while preserving approved business scenarios. |
| **Build and publish AI agents securely** | Establish secure-development requirements for identity, authorization, data handling, content safety, logging, memory, dependencies, deployment, and environment isolation. Require publishing and certification controls, review connector and tool risks, and align agent development with DevSecOps and software supply-chain practices. |
| **Validate AI safety, security, and quality** | Use content safety controls, Prompt Shields, adversarial and red-team testing, groundedness evaluations, runtime groundedness detection, data-quality rules, abuse testing, and defined release thresholds. Retest after material model, prompt, tool, data, memory, or configuration changes. |
| **Protect AI infrastructure, models, and runtime environments** | Discover AI workloads and models with cloud security posture capabilities, apply Azure Policy or equivalent governance, isolate sensitive infrastructure, protect AI services and agent runtimes, secure API and model endpoints, and monitor exposure, vulnerabilities, configurations, and runtime threats. |
| **Log and monitor AI activity** | Enable audit and diagnostic logging for AI applications, agents, identities, services, prompts, responses, tool use, memory operations, model endpoints, and governance actions where supported. Define retention, privacy, data minimization, health monitoring, and access controls for AI telemetry. |
| **Detect and respond to AI-specific threats** | Connect AI data sources to Microsoft Sentinel, Microsoft Defender XDR, or another SIEM/XDR platform. Implement detections for prompt injection, anomalous agent behavior, risky AI use, data exposure, identity compromise, unsafe tools, and runtime attacks, and use dashboards, hunting queries, playbooks, and automated response with appropriate safeguards. |
| **Continuously improve AI security posture** | Establish recurring reviews for AI inventory, risk findings, DLP and insider-risk alerts, agent permissions, publishing controls, incident trends, model and agent evaluations, regulatory evidence, and remediation progress. Update policies and controls as AI capabilities, threats, and business use evolve. |

These areas summarize the AI security workshop pillar. Use the detailed AI project guidance to review individual projects, dependencies, licensing considerations, and implementation guidance.

## How to use the AI Workshop

Use the web-based Workshop with AI platform and application teams, agent makers, identity, data protection, networking, infrastructure, DevSecOps, security operations, privacy, legal, compliance, and business stakeholders. For each relevant project:

- Review the project objective and applicability to your environment.
- Record the current status, notes, decisions, owners, and known dependencies.
- Consider licensing, implementation effort, user impact, data and regulatory requirements, technical prerequisites, coverage, and cross-pillar dependencies.
- Prioritize the project into First, Then, or Next and incorporate it into the implementation roadmap.

[Open the Zero Trust Workshop](https://aka.ms/ztworkshop) and select the AI pillar.

[Review the detailed AI project guidance](https://microsoft.github.io/zerotrustassessment/docs/category/ai) for project-level information.

## Assess your AI security posture

The Microsoft Zero Trust Assessment complements the Workshop by evaluating supported AI security configurations and practices against security best practices. Use its findings as an additional input when validating the current state and prioritizing AI security projects. Assessment results do not replace the cross-functional inventory, risk, architecture, development, data, and operational review completed in the Workshop.

[Learn about the Zero Trust Assessment](/en-us/security/zero-trust/assessment/overview).

## Who should participate?

- AI platform owners, AI application teams, agent makers, data scientists, machine-learning engineers, application architects, and software engineering teams.
- Identity, data governance, data protection, networking, infrastructure, cloud platform, endpoint management, and DevSecOps teams.
- Security architecture, application security, cloud security, security operations, incident response, exposure management, and threat-intelligence teams.
- Privacy, legal, compliance, responsible AI, governance, risk, procurement, business owners, data owners, and application owners.