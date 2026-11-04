---
layout: Conceptual
title: Catalog of AI Attack Techniques for Enterprise Security | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/catalog-ai-attack-techniques/catalog-ai-attack-techniques
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: ridive
author: richarddiver-ms
description: Introduces a catalog of fourteen AI attack techniques across five macro families, with controls, technologies, and OWASP/MITRE mappings for security teams.
ms.date: 2026-07-28T00:00:00.0000000Z
ms.custom: msecd-doc-authoring-1012
ms.topic: concept-article
ms.service: security
ms.subservice: zero-trust
locale: en-us
document_id: 91896bfb-704f-ef88-98a5-e13fe5ca534e
document_version_independent_id: 91896bfb-704f-ef88-98a5-e13fe5ca534e
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/catalog-ai-attack-techniques/catalog-ai-attack-techniques.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/catalog-ai-attack-techniques/catalog-ai-attack-techniques
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/catalog-ai-attack-techniques/catalog-ai-attack-techniques.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/a3955c7b-f5ee-420d-aff5-d7119738f38b
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/2624a017-7337-44fa-9494-a407bb0e59fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/b31948f4-2f38-404b-ac93-c3c8c5b3ae33
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/a438284e-c3c3-4c36-ab0b-aa7c244b912c
platformId: dfb2a41b-a066-19ce-2400-c71c74ea595a
---

# Catalog of AI Attack Techniques for Enterprise Security | Microsoft Learn

As artificial intelligence is rapidly integrated into enterprise environments, organizations face a new set of complex risks that span technical vulnerabilities, human factors, and procedural weaknesses. This guide provides a comprehensive overview of the evolving AI threat landscape, detailing fourteen distinct attack techniques including prompt manipulation, data poisoning, insecure plugin design, supply chain vulnerabilities, excessive agent autonomy, and more.

Each scenario is accompanied by actionable controls, relevant technologies, and clear OWASP/MITRE mappings to support effective risk mitigation.

The 14 techniques can be grouped into 5 macro technique families:

- **Instruction Manipulation** Attacks that manipulate prompts, instructions, context, or model-facing content
- **State and Memory Manipulation** Attacks that corrupt training data, grounding data, embeddings, memory, or persistent context
- **Trust and Supply Chain Abuse** Attacks that exploit trusted agents, tools, plugins, dependencies, or insiders
- **Execution and Autonomy Abuse** Attacks that misuse tools, permissions, autonomous actions, or execution paths
- **Resource and Extraction Abuse** Attacks that abuse model access, compute, APIs, or outputs to extract value or exhaust resources

Almost every attack maps to one of three control failures:

- **No trust boundary on input**
- **No integrity on data**
- **No containment on execution**

## How to use this guide

The content is organized for quick navigation. Each section introduces a specific attack scenario, explains what happens and why it succeeds, and identifies the security controls needed to reduce risk. The sections that follow provide executive-level summaries with real-world examples, required controls, and relevant technologies.

Together, these scenarios form a structured taxonomy of enterprise AI attack techniques, related business risks, and recommended mitigations.

**Intended Audience:** This guide is intended for CISOs, security architects, IT managers, AI developers, and risk professionals responsible for protecting enterprise systems. It also supports executives who need a practical view of AI security and operational teams implementing defensive controls.

**Key Lessons and Takeaways:** Readers will learn how to recognize AI-specific risks, apply layered mitigations, and strengthen collaboration across IT, security, and AI development teams. The guide emphasizes proactive risk management as the foundation for safe AI adoption, helping organizations move beyond traditional cybersecurity practices toward controls designed for the evolving AI threat landscape.

## Attack scenarios

- [1. Rug-Pull Attack (Agent / MCP Server)](rug-pull-attack)
- [2. Prompt Injection (Direct / Indirect)](prompt-injection)
- [3. Insecure Output Handling (Developer)](insecure-output-handling)
- [4. AI Memory / Context Poisoning (Corruption)](ai-memory-context-poisoning)
- [5. Unbounded AI Consumption and Agentic DoS (DoS / Wallet Attack)](unbounded-ai-consumption-and-agentic-dos)
- [6. Supply Chain Vulnerabilities (OSS)](supply-chain-vulnerabilities)
- [7. Sensitive Information Disclosure (Data Leak)](sensitive-information-disclosure)
- [8. Insecure Plugin Design (Tools/Plugins)](insecure-plugin-design)
- [9. Excessive Agency (Agents)](excessive-agency)
- [10. Overreliance on AI (Misuse & Human Factor)](overreliance-on-ai)
- [11. Model Theft (IP Theft)](model-theft)
- [12. Unmanaged Agent Sprawl & Collusion (Agents)](unmanaged-agent-sprawl)
- [13. Training Data Poisoning (Model backdoor)](training-data-poisoning)
- [14. Grounding Data Compromise (Retrieval Layer)](grounding-data-compromise)