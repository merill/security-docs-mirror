---
layout: Conceptual
title: AI Defense Capabilities for Enterprise AI Security | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/catalog-ai-defense-capabilities/catalog-ai-defense-capabilities
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: ridive
author: richarddiver-ms
description: A framework-aligned guide to the defensive capabilities enterprises need to mitigate AI attack techniques and adopt AI securely
ms.date: 2026-07-28T00:00:00.0000000Z
ms.custom: msecd-doc-authoring-1012
ms.topic: concept-article
ms.service: security
ms.subservice: zero-trust
locale: en-us
document_id: 7cf5da04-5782-17bd-c839-1b6911c7b8e8
document_version_independent_id: 7cf5da04-5782-17bd-c839-1b6911c7b8e8
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/catalog-ai-defense-capabilities/catalog-ai-defense-capabilities.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/catalog-ai-defense-capabilities/catalog-ai-defense-capabilities
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/catalog-ai-defense-capabilities/catalog-ai-defense-capabilities.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/a3955c7b-f5ee-420d-aff5-d7119738f38b
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/062d60c9-ee0f-402e-a046-b4e67c3572d6
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/b31948f4-2f38-404b-ac93-c3c8c5b3ae33
- https://authoring-docs-microsoft.poolparty.biz/devrel/17d3b3f6-a66e-4c69-9774-14a73c38e669
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: 17212888-1f92-6c74-1804-cd20caea305b
---

# AI Defense Capabilities for Enterprise AI Security | Microsoft Learn

Where the [Catalog of AI Attack Techniques](https://aka.ms/CAAT) sets out how enterprise AI systems are attacked, this companion sets out how they are defended. The defensive capabilities here are derived from the catalog’s scenario controls, technology references, and defensive mitigations, then normalized against [MITRE ATLAS](https://atlas.mitre.org), the [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/) (2025), and the [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) and Generative AI Profile.

The result is a single, framework-aligned view of the defensive capabilities an enterprise needs to adopt AI safely — grouped into the simplest set of families that still covers the full attack surface. It is intended for the same audience as the attack catalog: CISOs, security architects, IT managers, AI developers, and risk professionals.

This companion is organized as a defensive-control view of the attack catalog rather than as a one-for-one retelling of each attack technique. Readers should use the Catalog of AI Attack Techniques to identify the relevant attack path, then use this document to identify the control family, technology choices, and framework mappings that reduce risk across that path.

For prioritization, start with controls that constrain blast radius across many attack paths: identity and least privilege for users, agents, and tools; input and retrieval hygiene for anything the model reads; runtime containment for anything the model can do; and monitoring that preserves prompt, context, tool-call, and output evidence for investigation.

Security architecture should own the control framework, product engineering should own implementation in AI systems, security operations should own detection and response, and governance or risk teams should own policy, inventory, and assurance. The same capability may therefore require multiple owners, with accountability split between design-time control and run-time operation.

## Summary

The Catalog of AI Attack Techniques cluster around three recurring control failures: weak trust boundaries on input, weak integrity guarantees for data and models, and weak containment of execution. The defensive capabilities are the inverse — each capability strengthens one or more of three control objectives:

- **Establish a trust boundary on input** — nothing the model reads is trusted by default.
- **Enforce integrity on data and models** — provenance, signing, and verification across the lifecycle.
- **Impose containment on execution** — least privilege, isolation, and limits on what AI can do.

These objectives resolve into nine capability families. They mirror the nine mitigation types already identified in the attack catalog, now consolidated and cross-referenced:

| **Capability family** | **What it secures** |
| --- | --- |
| **1. Govern, Assure, and Respond** | Policy, threat modeling, human oversight, red-teaming, incident response |
| **2. Supply-chain and Provenance** | Models, datasets, libraries, plugins, and agents from upstream tampering |
| **3. Identity, Access, and Least Privilege** | Verified identity and minimum rights for every user, agent, and tool |
| **4. Input, Context, and Retrieval Hygiene** | Prompts, documents, retrieval, and memory treated as untrusted |
| **5. Model Hardening and Alignment** | Behavioral robustness of the model against jailbreaks and backdoors |
| **6. Runtime Isolation and Sandboxing** | What the AI and its tools can do at execution time |
| **7. Output Safety and Downstream Handling** | The model’s output as untrusted input to the next system |
| **8. Monitoring, Detection, and Forensics** | Visibility, anomaly detection, and traceability across the stack |
| **9. Resource Governance and Abuse Prevention** | Availability and budget against denial-of-service and wallet attacks |

## Table of contents

- [1. Govern, Assure, and Respond](govern-assure-respond)
- [2. Supply-chain and Provenance](supply-chain-provenance)
- [3. Identity, Access, and Least Privilege](identity-access-least-privilege)
- [4. Input, Context, and Retrieval Hygiene](input-context-retrieval-hygiene)
- [5. Model Hardening and Alignment](model-hardening-alignment)
- [6. Runtime Isolation and Sandboxing](runtime-isolation-sandboxing)
- [7. Output Safety and Downstream Handling](output-safety-downstream-handling)
- [8. Monitoring, Detection, and Forensics](monitoring-detection-forensics)
- [9. Resource Governance and Abuse Prevention](resource-governance-abuse-prevention)