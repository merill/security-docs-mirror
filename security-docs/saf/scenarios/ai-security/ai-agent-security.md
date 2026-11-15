---
layout: Conceptual
title: Secure your agentic insider with SAF | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/saf/scenarios/ai-security/ai-agent-security
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Translate the secure your agentic insider theme into durable outcomes and use SAF and Microsoft guidance to govern agent identities, data access, actions, and behavior.
ms.date: 2026-11-08T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 6df78385-8491-4d87-19d9-1bdc3b72f498
document_version_independent_id: 6df78385-8491-4d87-19d9-1bdc3b72f498
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/saf/scenarios/ai-security/ai-agent-security.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../../../zero-trust/toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: saf/scenarios/ai-security/ai-agent-security
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/saf/scenarios/ai-security/ai-agent-security.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: a7c75e36-73c8-3146-f9e8-a454a8eab8c0
---

# Secure your agentic insider with SAF | Microsoft Learn

**Secure your agentic insider** is a current AI security transformation theme. The name can evolve, but the underlying challenge is durable: AI agents can use identities, access data, invoke tools, communicate with services and other agents, and take actions that affect business processes. Organizations must govern those capabilities as carefully as other trusted participants in the enterprise.

The insider analogy helps communicate the combination of legitimate access and potential impact. It does not mean that an agent is a person or that every agent is malicious. It means that intended, mistaken, manipulated, or compromised agent behavior can create insider-style risk when access and actions are not bounded and monitored.

This page translates the theme into durable outcomes and execution paths. It does not create a separate control framework. Use the Microsoft Security Adoption Framework (SAF) to organize the work and canonical Microsoft guidance to implement it.

## What this theme means

Secure your agentic insider means knowing which agents exist, who owns them, what identities they use, which data and tools they can access, what actions they can take, and how their behavior is monitored and constrained throughout the lifecycle.

This work connects several familiar priorities: secure AI and data together, apply least privilege, protect secrets, govern the software and model supply chain, prevent unauthorized actions, and prepare to detect and respond when an agent is manipulated, drifts from intended behavior, or is compromised.

Most of this work builds on established security foundations for identity, data, applications, development, infrastructure, posture, and operations. Agentic systems also introduce AI-specific risks involving delegated autonomy, tool use, memory, agent-to-agent interaction, and manipulation. Integrate protections for these risks into the existing foundations rather than treating agent security as a disconnected control model.

## Durable outcome

The durable outcome is an environment in which agent autonomy is deliberate, bounded, observable, and accountable.

Success looks like:

- Every production agent has a registered identity, accountable business owner, technical owner, purpose, risk classification, and lifecycle state.
- Agent permissions are limited to the data, tools, connectors, services, and actions required for the intended task.
- High-impact actions require stronger evidence, additional controls, or human authorization.
- Sensitive data, prompts, context, memory, model inputs and outputs, and secrets are protected according to business risk.
- Development teams threat-model agent workflows, validate trust boundaries, test failure modes, and secure dependencies before release.
- Security teams can observe agent decisions and actions with enough context to investigate misuse, manipulation, drift, and compromise.
- Response procedures can suspend identities, revoke tokens and secrets, isolate services, preserve evidence, and recover safely.
- Governance continuously reassesses agents as models, data, tools, permissions, and business use change.

## SAF work

### Business scenarios

Use these SAF business scenarios to define outcomes and priorities:

- [Adopt and secure AI](/en-us/security/zero-trust/security-adoption-scenario-secure-ai) - Establish guardrails and operating practices for safe AI adoption.
- [Protect critical business assets](/en-us/security/zero-trust/security-adoption-scenario-secure-assets) - Limit agent access and actions according to the business impact of assets and data.
- [Secure and govern privileged access](/en-us/security/zero-trust/security-adoption-scenario-privileged-access) - Protect control-plane access and other high-impact actions that agents or their operators can perform.
- [Minimize damage from security incidents](/en-us/security/zero-trust/security-adoption-scenario-minimize-impact) - Detect, contain, investigate, and recover from harmful agent behavior or compromise.
- [Strengthen posture and compliance](/en-us/security/zero-trust/security-adoption-scenario-improve-posture) - Continuously assess agent inventory, permissions, configuration, exposure, and policy coverage.

### Security disciplines

Coordinate the work across these SAF disciplines:

- [Strategy, integration, and governance](/en-us/security/zero-trust/security-adoption-discipline-strategy) defines acceptable use, autonomy boundaries, risk acceptance, policy, and accountability.
- [Security architecture](/en-us/security/zero-trust/security-adoption-discipline-architecture) defines agent trust boundaries, identity patterns, data flows, control points, and failure containment.
- [Access and identities](/en-us/security/zero-trust/security-adoption-discipline-identity-access) governs agent, workload, service, and human identities and applies least privilege.
- [Data](/en-us/security/zero-trust/security-adoption-discipline-data) protects prompts, context, memory, grounding data, outputs, and downstream information use.
- [Development](/en-us/security/zero-trust/security-adoption-discipline-development) integrates threat modeling, secure design, dependency controls, testing, deployment, and lifecycle management.
- [Security posture](/en-us/security/zero-trust/security-adoption-discipline-posture) inventories agents and exposure, validates policy coverage, and prioritizes gaps.
- [Infrastructure](/en-us/security/zero-trust/security-adoption-discipline-infrastructure) secures hosting environments, runtimes, models, tools, connectors, and supporting services.
- [SecOps](/en-us/security/zero-trust/security-adoption-discipline-security-operations) monitors behavior and coordinates investigation, containment, recovery, and improvement.

### Roles and collaboration

Use [Security roles and responsibilities in SAF](/en-us/security/zero-trust/security-adoption-roles) to assign accountability and decision rights.

The control model depends on collaboration among:

- Organizational leadership and governance to define risk appetite and accountability for agent use.
- Business and AI solution owners to define purpose, acceptable behavior, criticality, and business impact.
- Security strategy, architecture, identity, data, privacy, and compliance teams to establish policy and reusable controls.
- Application and product development teams to design, test, release, and maintain agent behavior safely.
- Technical engineering and operations teams to run identity, data, platform, infrastructure, network, endpoint, and observability controls.
- SecOps teams to detect anomalous behavior, investigate evidence, contain harmful actions, and coordinate recovery.
- Legal, human resources, procurement, and third-party risk teams where agent actions, vendors, or data use cross organizational boundaries.

### Technologies

Start with [AI technology guidance](/en-us/security/saf/technologies/ai/overview), and apply connected controls across:

- [Identity](/en-us/security/zero-trust/deploy/identity) for agent identities, authentication, authorization, and lifecycle.
- [Applications](/en-us/security/zero-trust/deploy/applications) for APIs, plugins, connectors, tools, and runtime behavior.
- [Data](/en-us/security/zero-trust/deploy/data) for prompts, context, memory, grounding, training, inference, and outputs.
- [Infrastructure](/en-us/security/zero-trust/deploy/infrastructure) for hosting, models, compute, services, and isolation.
- [Network](/en-us/security/zero-trust/deploy/networks) for service paths, segmentation, filtering, and agent-to-agent communication.
- [Endpoints](/en-us/security/zero-trust/deploy/endpoints) where agents interact with user devices, local data, or device-bound applications.

Agent risk emerges from the interaction among these technologies. Do not rely on a single AI-specific control to manage it.

## Implementation and product guidance

Use [Microsoft secure Zero Trust implementation solutions](/en-us/security/zero-trust/implement-overview) to connect the business outcome and operating model to technical controls. Start with the following canonical guidance:

1. [Secure AI with Zero Trust](/en-us/security/saf/technologies/ai/overview) to map agent identities, data, tools, connectors, communications, and runtime controls.
2. [AI security in the Microsoft Zero Trust Workshop](/en-us/security/zero-trust/workshop-zero-trust-ai-security) to align business, security, development, and operations stakeholders.
3. [Discover AI apps and data](/en-us/security/security-for-ai/discover) to identify usage, applications, agents, owners, and data paths.
4. [Protect AI apps and data](/en-us/security/security-for-ai/protect) to apply protection to AI applications, access, and information.
5. [Govern AI for compliance](/en-us/security/security-for-ai/govern) to establish policy, oversight, and evidence.
6. [Use Zero Trust security to prepare for AI companions, including Microsoft Copilots](/en-us/security/zero-trust/copilots/apply-zero-trust-copilots-overview) for Microsoft Copilot scenarios.

Use focused implementation guidance across the agent lifecycle:

- [Identify risk for autonomous agentic AI](/en-us/security/zero-trust/sfi/manage-agentic-risk)
- [Secure autonomous agentic AI systems](/en-us/security/zero-trust/sfi/secure-agentic-systems)
- [Least privilege for AI agents](/en-us/security/zero-trust/sfi/least-privilege-for-ai-agents)
- [Manage memory safety in agentic systems](/en-us/security/zero-trust/sfi/manage-agentic-memory-safety)
- [Complete AI threat modeling](/en-us/security/zero-trust/sfi/threat-modeling-ai)
- [Defend against indirect prompt injection attacks](/en-us/security/zero-trust/sfi/defend-indirect-prompt-injection)
- [Implement AI observability](/en-us/security/zero-trust/sfi/observability-ai-systems)
- [Respond to incidents in AI systems](/en-us/security/zero-trust/sfi/incident-response-ai-systems)
- [Safe Secrets Standard](/en-us/security/zero-trust/sfi/safe-secrets-standard)

Keep detailed product configuration in canonical Microsoft documentation. Use this page to define the durable outcome, assign work through SAF, and route each team to the implementation guidance for the controls it owns.