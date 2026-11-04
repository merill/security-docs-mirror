---
layout: Conceptual
title: Secure autonomous agentic AI systems | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/secure-agentic-systems
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn about securing autonomous agaentic AI systems
ms.date: 2026-03-19T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: design-pattern
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
locale: en-us
document_id: 252e0f0b-15d8-f5d1-c1d3-c6fd23b0d898
document_version_independent_id: 252e0f0b-15d8-f5d1-c1d3-c6fd23b0d898
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/secure-agentic-systems.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/secure-agentic-systems
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/secure-agentic-systems.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/de19c5b8-e208-412e-9238-db3f631dea5b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ea7bf5d6-7154-4ba9-8ebc-59117ccacd49
platformId: 72a2a70c-61f7-e7fe-753a-0ecbf8fc33aa
---

# Secure autonomous agentic AI systems | Microsoft Learn

**Pillar name: Monitor and detect threats** **Pattern name: Secure agentic AI systems**

## Context and problem

Autonomous agentic AI systems can plan, invoke tools, access data, and execute actions with limited human intervention. As autonomy increases, so does the potential impact of misalignment, misuse, and compromise.

The companion Patterns & Practices article [Reduce risk for autonomous agentic AI systems](manage-agentic-risk) outlines the design, security, and governance risks introduced by agentic behavior. This pattern shifts from **risk identification** to **risk reduction**, focusing on the controls and design decisions that mitigate those risks in practice.

## Solution

Securing agentic systems requires a **defense‑in‑depth** strategy that assumes failure at individual layers and designs systems so that no single failure results in unacceptable harm.

### Controls within mitigation layers

#### Model layer controls

The model acts as the agent's reasoning engine and influences how the agent interprets instructions, plans actions, and responds to adversarial inputs. Different models offer varying capabilities and safety features that influence the agent’s outputs and actions. Selecting an appropriate model helps avoid misalignment, errors, and unsafe results.

**Recommended controls:**

- **Intentional model selection:** Choose models whose reasoning depth, refusal behavior, and tool use characteristics match the agent’s autonomy and risk profile. Mitigates task misalignment and unsafe actions.
- **Model supply chain governance:** Treat models as security dependencies by tracking versions, reviewing updates, and validating changes before deployment. Mitigates supply chain compromise.
- **Evaluation and red teaming:** Continuously test models for agentic threats such as cross‑prompt injection, intent breaking, and unsafe tool selection. Mitigates agent hijacking and unintended actions.
- **Capability alignment:** Avoid over‑capable models when simpler or more constrained models meet the system’s needs. Mitigates excessive autonomy and increased blast radius.

#### Safety system layer controls

The safety system layer intercepts failures at runtime, when agents are interacting with untrusted content, tools, APIs, and users. These safeguards form an essential defense against operational risks, including agent hijacking, harmful outputs, sensitive data leakage, and runtime misuse.

**Recommended controls:**

- **Input and output filtering:** Detect and block malicious, manipulative, or unsafe inputs and outputs, including indirect prompt injection. Mitigates agent hijacking and sensitive data leakage.
- **Agent guardrails:** Enforce task adherence and prevent out‑of‑scope or unsafe tool invocations during execution. Mitigates unintended actions and high‑impact misuse.
- **Logging and observability:** Capture agent plans, tool calls, decisions, and outcomes to support audit, incident response, and improvement. Mitigates intelligibility failures and undetected misuse.
- **Abuse and anomaly detection:** Monitor for repeated bypass attempts or anomalous behavior patterns. Mitigates persistent probing and stealthy exfiltration.

#### Application layer controls

The application layer defines how the agent is architected, what actions it can take, and how controls are enforced. This is where safety principles become enforceable system behavior.

**Recommended controls:**

- **Agents as microservices:** Design agents like microservices with isolated permissions and narrowly scoped tool access. Mitigates misalignment, blast radius, and sensitive data leakage.
- **Explicit action schemas:** Define allowed actions, required inputs, risk levels, execution constraints, and logging requirements. Mitigates unintended actions and unsafe tool invocation.
- **Deterministic human‑in‑the‑loop (HITL):** Enforce human review for high‑risk or irreversible actions through orchestrator logic rather than model reasoning. Mitigates oversight control gaps and misalignment.
- **Least privilege and least action design:** Start with no permitted actions by default and incrementally enable capabilities based on role and risk. Assign each agent a unique, verifiable identity to enforce RBAC. Mitigates sensitive data leakage, agent sprawl, and over‑permissioning.
- **System messages as reinforcement:** Use structured system instructions to reinforce roles and boundaries, always backed by deterministic controls. Mitigates agent hijacking and misalignment.

#### Positioning layer controls

The positioning layer shapes how people understand, trust, and rely on an agentic system. Poor positioning can introduce risk even when technical controls are strong.

**Recommended controls:**

- **Clear disclosure:** Make it explicit when users are interacting with an autonomous AI agent. Mitigates transparency and disclosure failures.
- **Capability transparency:** Communicate what the agent can and cannot do, including limitations and uncertainty. Avoid positioning agents as authoritative or infallible. Mitigates inappropriate reliance.
- **User‑visible boundaries:** Surface planned actions, approvals, and outcomes so users can detect abnormal behavior. Mitigates intelligibility failures.
- **Secure UX patterns:** Ensure review, approval, and shutdown mechanisms are accessible and protected. Mitigates misuse and over‑reliance.

## Microsoft solutions

The controls above describe what to implement. The following Microsoft solutions help operationalize these mitigations across identity, governance, runtime enforcement, and detection.

### Primary control plane

- **Microsoft Agent 365**:
    - Provides centralized inventory, governance, access boundaries, and cross‑agent visibility.
    - Supports: agent sprawl prevention, least privilege, and governance. Supports: agent sprawl prevention, least privilege, governance.

### Model selection and svaluation

- [Microsoft Foundry’s Model Catalogue](https://ai.azure.com/catalog) to evaluate and select models appropriate for the use case, including safety and security baselines.
- [Microsoft Foundry’s AI Red Teaming Agent](/en-us/azure/foundry/concepts/ai-red-teaming-agent) and [Python Risk Identification Tool (PyRIT)](https://github.com/Azure/PyRIT) for red team and continuous evaluation.

### Safety system and runtime mitigations

- **Microsoft Foundry (Guardrails, Content Filters, Abuse Monitoring)**
    - Enforces task adherence, filter untrusted inputs and outputs, and detect misuse patterns.
    - Supports: Prompt injection mitigation, leakage prevention.

### Identity and data protection

- **Microsoft Entra**:

    - Provides identity, conditional access, and role‑based access control for agents.
    - Supports: least privilege, access control.
- **Microsoft Purview**:

    - Provides data classification, governance, and policy enforcement.
    - Supports: sensitive data protection.

### UX design

- [Human AI Interaction (HAX) Toolkit](https://www.microsoft.com/research/project/hax-toolkit/?msockid=3e0d92e1b3a76fa41e1685f0b7a76104) for disclosure and human-centered UX patterns.
- [Secure by Design UX Toolkit](https://microsoft.design/articles/secure-by-design-a-ux-toolkit/) for secure UX patterns

### Detection and response (supporting)

- **Microsoft Defender** and **Microsoft Sentinel** for security posture management, signal correlation, and incident response across agent workloads.
- **Azure Monitor** and **Application Insights** for telemetry and observability for agent behavior and performance.

## Guidance

Organizations seeking to adopt this pattern can apply the following actionable practices:

| Practice Category | Recommended Actions | Resource |
| --- | --- | --- |
| Governance for tools, agents, and models | Onboard agents to Foundry using supported frameworks or register custom agents | [Microsoft Foundry Control Plane](/en-us/azure/foundry/control-plane/overview) |
| Content safety & prompt injection resilience | Filter inputs and outputs; treat retrieved content as untrusted; block indirect prompt injection | [Foundry Content Filtering and Prompt Shields](/en-us/azure/ai-services/content-safety/overview) |
| Task adherence & tool safety | Enforce tool allowlists and deterministic validation | [Foundry Agent Guardrails](/en-us/azure/machine-learning/concept-responsible-ai-dashboard) |
| AI red‑teaming | Continuously test for prompt injection, intent breaking, unsafe tool selection, and leakage | [Foundry AI Red Teaming Agent / PyRIT](/en-us/azure/foundry/concepts/ai-red-teaming-agent) |
| Identity & access for agents | Apply least privilege, conditional access, and lifecycle governance | [Microsoft Entra](/en-us/entra/agent-id/) |
| Data governance & compliance | Classify and protect sensitive data | [Microsoft Purview](/en-us/purview/data-security-posture-management-learn-about) |
| Posture management | Assess configuration and vulnerabilities | [Microsoft Defender for Cloud](/en-us/azure/defender-for-cloud/concept-cloud-security-posture-management) |
| Detecting misuse | Correlate logs and traces | [Microsoft Sentinel](https://www.microsoft.com/security/business/siem-and-xdr/microsoft-sentinel) |

## Outcomes

### Benefits

- Agents operate within defined intent, permissions, and boundaries.
- High‑risk actions require deterministic human approval.
- Agent behavior is observable, auditable, and governable at scale.
- Sensitive data exposure is reduced through least privilege and policy enforcement.
- Organizations retain visibility and control as agent usage grows.
- Trust is built through transparency, accountability, and predictable behavior.

### Trade‑offs

- Additional engineering effort is required to implement layered controls.
- Autonomous systems introduce architectural and operational complexity.
- Human oversight adds friction to high‑risk workflows.
- Governance and observability require sustained operational investment.

## Key success factors

- Task adherence
- Human involvement
- Deterministic safeguards
- Transparency and disclosure
- Hijacking resistance
- Least privilege and governance
- Supply chain awareness

## Summary

Unlocking human potential starts with trust. The ability of agentic systems to plan, decide, and act autonomously means that small misalignments, oversights, or security gaps can lead to significant consequences and loss of trust.

As these systems become more deeply integrated with tools, APIs, and other agents, their behavior becomes increasingly complex—and so do the pathways through which harm can occur. The risks associated with agentic behavior are systemic and require mitigation strategies that span the full system stack.

By applying defense in depth across model, safety system, application, and positioning layers, and by leveraging Microsoft’s integrated security and agent management ecosystem, organizations can deploy agentic systems that are autonomous, observable, and resilient by design.