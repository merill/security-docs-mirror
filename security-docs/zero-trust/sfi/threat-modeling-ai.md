---
layout: Conceptual
title: Complete AI threat modeling (Secure Future Initiative) – Zero Trust | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/threat-modeling-ai
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: AI threat modeling in the Microsoft SFI focuses on remediating unique security challenges for generative and agentic AI systems.
ms.date: 2025-08-05T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: design-pattern
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
locale: en-us
document_id: 519b4344-2262-568a-9420-5d72f997392e
document_version_independent_id: 519b4344-2262-568a-9420-5d72f997392e
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/threat-modeling-ai.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/threat-modeling-ai
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/threat-modeling-ai.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/062d60c9-ee0f-402e-a046-b4e67c3572d6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/c6f99e62-1cf6-4b71-af9b-649b05f80cce
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/17d3b3f6-a66e-4c69-9774-14a73c38e669
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3f56b378-07a9-4fa1-afe8-9889fdc77628
platformId: 9c015eff-5162-78e9-8863-7dbb7f22151a
---

# Complete AI threat modeling (Secure Future Initiative) – Zero Trust | Microsoft Learn

**Pillar name: Monitor and detect threats** **Pattern name: Complete AI threat modeling**

## Context and problem

Threat modeling is a structured method for proactively identifying, assessing, and addressing risks before they become real-world failures or attacks. While traditional software threat modeling focuses on predictable code paths and deterministic behavior, AI-enabled systems break many of those assumptions.

Generative and agentic AI systems are probabilistic, instruction-driven, and capable of interpreting natural language as executable intent. As a result, data and control paths blur, new attack surfaces emerge, and failures often occur at integration boundaries rather than in isolated components.

Key challenges include:

- Non-deterministic behavior that prevents reasoning about a single execution path or outcome.
- Instruction-following bias that makes models susceptible to prompt injection and unintended control.
- System expansion through tools, memory, and agents, increasing blast radius and compounding failures.
- Human-centered risks such as overreliance, erosion of trust, and harm from persuasive but incorrect outputs.

These challenges underscore the need for threat modeling approaches that explicitly account for AI-specific risks alongside traditional security concerns.

## Solution

Threat modeling for AI systems is an ongoing engineering mindset rather than a one-time checklist. It begins with identifying what must be protected, understanding how the real system behaves end to end, modeling intentional misuse, and designing architectural mitigations that constrain failure.

Organizations can use these functions to structure ongoing assessments as follows:

1. Identify and prioritize assets, including non-traditional assets such as user trust, response correctness, data privacy, and integrity of agent actions.
2. Map the real system architecture, including prompt construction, memory access, tool invocation, external data ingestion, and human approval points.
3. Map misuse scenarios based on adversarial intent, assess use impact and likelihood to inform your response plan, and design mitigations directly into the architecture.
4. Document AI data flows, trust boundaries, and tool permissions as part of the design phase. Apply scoped least privilege tool access, human-in-the-loop controls, and explicit separation of instructions and data.
5. Use logging and observability to detect misuse, attribute actions, and refine mitigations over time.

## Guidance

Organizations can adopt a similar pattern using the following actionable practices:

| Use case | Recommended action | Resource |
| --- | --- | --- |
| GenAI application handling sensitive data | Treat all external inputs as untrusted and isolate them from system instructions. | [Threat modeling AI/ML systems and dependencies](../../engineering/threat-modeling-aiml) |
| Agentic workflows with tool access | Apply least-privilege tool scoping and require confirmation for high-risk actions. | [OWASP-Agentic AI - Threats and mitigations](https://genai.owasp.org/resource/agentic-ai-threats-and-mitigations/) |
| Multi-agent coordination | Explicitly define trust relationships and permissions between agents. | [Microsoft Entra Agent ID](/en-us/entra/agent-id/) |
| High-impact decision support | Add uncertainty signaling and guardrails to prevent overreliance | [Microsoft Foundry-System message design](/en-us/azure/ai-foundry/openai/concepts/advanced-prompt-engineering) |
| Production AI systems | Implement logging, attribution, and audit trails for prompts, tools, and outputs | [Microsoft Incident Response](https://www.microsoft.com/security/business/microsoft-incident-response) |

### Benefits

- Earlier detection of misuse, abuse, or anomalous behavior.
- Better alignment between system design and real-world risk.
- Reduced likelihood of catastrophic or cascading AI failures.
- Improved user trust through explainable and auditable system behavior.

### Trade-offs

- Added architectural complexity and development effort.
- Performance and latency impacts from additional controls.
- Operational overhead from logging, review, and human approval paths.

## Key success factors

Track these KPIs to measure progress:

- AI‑specific risks are identified early and paired with clear, actionable mitigations (not just documented).
- High‑impact or irreversible actions are intentionally constrained through guardrails such as validation, policy checks, or human approval.
- System behavior is explainable and attributable, with prompts, context, and tool usage traceable for debugging and incident response.
- Misuse and anomalies are surfaced through logging and observability, not discovered primarily through user reports.

## Summary

Threat modeling for AI systems extends traditional security practices to address non-determinism, instruction sensitivity, and system expansion through tools and agents. By focusing on assets, real system behavior, intentional misuse, and observability, organizations can design AI systems that fail safely, contain risk, and improve over time rather than relying on fragile, last-mile controls.