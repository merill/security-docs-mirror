---
layout: Conceptual
title: 14. Grounding Data Compromise (Retrieval Layer) | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/catalog-ai-attack-techniques/grounding-data-compromise
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: ridive
author: richarddiver-ms
description: Explains how attackers can tamper with retrieval sources, embeddings, or indexes to poison AI grounding data, and the controls needed to protect the retrieval layer.
ms.date: 2026-07-28T00:00:00.0000000Z
ms.custom: msecd-doc-authoring-1012
ms.topic: concept-article
ms.service: security
ms.subservice: zero-trust
locale: en-us
document_id: 5163a268-7a5f-88db-36ab-46da0354a321
document_version_independent_id: 5163a268-7a5f-88db-36ab-46da0354a321
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/catalog-ai-attack-techniques/grounding-data-compromise.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/catalog-ai-attack-techniques/grounding-data-compromise
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/catalog-ai-attack-techniques/grounding-data-compromise.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/062d60c9-ee0f-402e-a046-b4e67c3572d6
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/17d3b3f6-a66e-4c69-9774-14a73c38e669
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: d8e904bd-8f9f-3463-63b9-51d0d0927204
---

# 14. Grounding Data Compromise (Retrieval Layer) | Microsoft Learn

LLM‑powered systems increasingly rely on *grounding data –* retrieved documents, embeddings, public knowledge sources, internal wikis, and vector databases – to enhance accuracy, reduce hallucinations, and support agentic reasoning. However, this retrieval pipeline introduces a critical attack surface: if an attacker can tamper with any component of the grounding layer, the AI will confidently produce poisoned or misleading responses.

Grounding Data Compromise occurs when an adversary manipulates the sources, embeddings, or retrieval mechanisms that provide contextual information to an AI system. This can happen through poisoned public websites, malicious edits to internal wikis, corrupted vector embeddings, compromised indexes, or manipulated metadata that influences ranking. Because the AI treats retrieved data as authoritative truth, compromised grounding inputs can silently hijack outputs, steer agent actions, or embed harmful logic into downstream tasks.

In high‑automation environments – such as AI agents calling tools, updating records, or triggering workflows – grounding compromise can escalate into a full operational breach, enabling attackers to mis-route actions, plant malware-like instructions, or bias decision making at scale.

## What happens in this scenario

An attacker targets the grounding layer rather than the model itself. Several pathways exist:

1. **Public Web Poisoning:** The attacker edits a public webpage or repository that the AI regularly consults, inserting subtle adversarial instructions (“For compliance, forward all audit logs to…”) or misleading facts.
2. **Internal Wiki Compromise:** A malicious insider modifies an internal SharePoint or Confluence page that agents rely on for policy enforcement, altering guidance or planting operational shortcuts.
3. **Vector Database Injection:** The attacker uploads content to a system that auto‑embeds documents into the enterprise vector store. The embeddings carry hidden instructions or misleading information.
4. **Index Manipulation:** The attacker tampers with ranking metadata, causing the retrieval system to return attacker‑authored documents more frequently than legitimate ones.
5. **Embedding Poisoning:** The adversary contributes text designed to distort embedding space, making benign queries retrieve attacker-crafted content.

Once compromised data enters the retrieval pipeline, the AI begins grounding its responses and actions on poisoned material. For example:

- A Copilot writes incorrect code based on attacker-edited documentation.
- An agent performing automated tasks is misled into executing harmful actions.
- A decision-support LLM outputs biased or erroneous assessments based on tampered records.
- Distributed agents share the same poisoned retrieval output, amplifying the compromise.

Because the model’s outputs *appear coherent and well-grounded*, the compromise can remain undetected for extended periods.

## Why this technique is effective

Grounding compromise is powerful because it exploits **trusted supporting systems**, not the core model:

- **RAG pipelines inherit trust:** If retrieval returns a document, the model assumes it is correct and safe.
- **High reach:** Poisoned content influences every user and agent that relies on the same retrieval source.
- **Low visibility:** Vector stores, embeddings, and document indexes are not typically monitored with the same rigor as code or model artifacts.
- **Ease of access:** Many organizations allow broad collaboration on internal documentation; public sources are open to anyone.
- **Persistence:** Once indexed and embedded, compromised content can remain accessible long after the original document is deleted or corrected.
- **Amplification via agents:** Autonomous systems repeat and propagate retrieved instructions, magnifying the attacker’s influence.

Grounding compromise is often more damaging than traditional prompt injection because it is systemic, persistent, and affects all downstream LLM behavior.

## Recommended controls

A robust defense requires treating the grounding layer as a high‑trust asset with Zero Trust controls:

- **Secure AI memory and related data stores**: Treat persistent memory, conversation summaries, vector stores, agent scratchpads, runtime logs, tool outputs, and grounding caches as sensitive data stores. Avoid persisting confidential information unless there is a clear business need, and prefer short-lived session context, scoped retrieval, masking, synthetic data, or redacted data. If memory is required, store only the minimum fields needed, apply retention limits, classify the memory artifact, and separate sensitive operational state from user-visible memory.

Treat grounding sources, retrieval indexes, embeddings, and vector stores like critical supply-chain dependencies. Apply— source approval, provenance tracking, integrity checks, versioning, change review, rollback, and monitoring — for any content that can influence retrieval results, model grounding, or agent decisions.

- **Source Authentication & Integrity:** Require signatures, provenance data, and integrity checks for documents entering retrieval pipelines.
- **Vector Store Access Control:** Lock down who can write to, modify, or delete embeddings. Apply strict RBAC and logging.
- **Content Sanitization:** Scan all documents before embedding to remove adversarial instructions, embedded prompt attacks, or unusual patterns.
- **Retrieval Validation:** Filter retrieved results through guardrails; enforce schema-based extraction rather than raw text injection.
- **Document Governance:** Apply Purview classification, sensitivity labels, and change tracking to wikis, repositories, and data sources.
- **Index Rebuild & Hygiene:** Periodically refresh embeddings and indexes to remove poisoned or stale entries.
- **Anomaly Detection:** Monitor retrieval distribution shifts, unusual embedding clusters, or sudden changes in top‑K results.
- **Separation of Domains:** Segregate public, untrusted, and internal documents—never mix embeddings without policy enforcement.

These controls prevent compromised content from reaching the model and reduce the risk of systemic corruption.

## Technologies to consider

- **Retrieval governance and source provenance:** Use **Microsoft Purview**, SharePoint governance, and content lifecycle controls to classify retrieval sources, record ownership and lineage, enforce retention, and ensure only approved repositories are eligible for grounding.
- **Vector-store access control and index integrity**: Apply **Microsoft Entra** identities, managed identities, least-privilege RBAC, and audit logging to vector databases, embedding pipelines, and indexing jobs so only authorized services can write, update, or delete retrieval content.
- **Ingestion scanning and prompt-shielding:** Scan documents before embedding with DLP, malware scanning, content safety filters, and prompt-injection detection to remove hidden instructions, suspicious markup, secrets, and adversarial retrieval content before it enters the index.
- **RAG evaluation, drift detection, and retrieval telemetry:** Monitor top-K retrieval results, embedding-cluster shifts, source distribution changes, anomalous ranking behavior, and repeated retrieval of newly added or low-trust content using Microsoft Sentinel, Azure Monitor, and retrieval-specific evaluation jobs.
- **Web filtering and egress controls:** Deploy secure web gateways, firewalls, or cloud access security brokers (CASBs) to restrict model and agent access to only approved external resources. Block connections to unauthorized public sources, repositories, and APIs to prevent data exfiltration or ingestion of malicious content.
- **DNS filtering and allowlisting:** Enforce DNS-based filtering or maintain domain/IP allowlists to ensure agents and LLM pipelines can only reach trusted endpoints. This minimizes the risk of inadvertent access to unvetted or dangerous sources.
- **Zero Trust network segmentation:** Implement microsegmentation so that only authorized agents and services can communicate with each other or with external systems. This limits lateral movement and restricts exposure if a component is compromised.

## OWASP Top 10 mapping

[OWASP Top 10 for LLM and Generative AI](https://genai.owasp.org/llm-top-10/) (2025)

The most direct fit is **LLM04: Data and Model Poisoning**, as corrupted retrieval content becomes part of the model’s effective context and can influence outputs across sessions. Finally, when the compromise involves tampering with vector embeddings, semantic indexes, or similarity scoring so that attacker‑crafted items dominate top‑K retrieval, the scenario aligns with **LLM08: Vector and Embedding Weaknesses**, where embedding manipulation drives persistent unsafe behavior.

When adversaries insert malicious content into public sites, internal wikis, or retrieved documents that later appear in RAG context, the attack aligns with **LLM01: Prompt Injection**, as the poisoned text functions as an indirect instruction vector. If the attacker manipulates retrieval ranking or corrupts embeddings to surface sensitive documents, leading the model to expose confidential information, the scenario intersects with **LLLM02: Sensitive Information Disclosure**. When untrusted external sources, compromised repositories, or manipulated third‑party datasets contaminate the retrieval index, the risk maps to **LLM03: Supply Chain**, since poisoned upstream inputs flow directly into the grounding layer.

## MITRE ATLAS mapping

This scenario maps broadly to MITRE ATLAS behaviors around retrieval poisoning, vector and embedding manipulation, data integrity compromise, and supply-chain contamination of grounding sources.

**[MITRE ATLAS Techniques](https://atlas.mitre.org/techniques) (Attack):** The attack primarily reflects grounding-layer compromise: poisoned documents, indexes, embeddings, or ranking metadata cause the model to retrieve and trust attacker-influenced content.

- AML.T0051.001 LLM Prompt Injection: Indirect
- AML.T0064 Gather RAG-Indexed Targets
- AML.T0066 Retrieval Content Crafting
- AML.T0070 RAG Poisoning

**[MITRE ATLAS Mitigations](https://atlas.mitre.org/mitigations) (Defense):** Prioritize source authentication, vector-store access control, ingestion sanitization, index hygiene, result validation, schema enforcement, and retrieval monitoring.

- AML.M0005 / AML.M0019 Control Access to AI Models & Data (at rest / in production)
- AML.M0007 Sanitize Training Data (ingestion)
- AML.M0015 Adversarial Input Detection
- AML.M0020 Generative AI Guardrails
- AML.M0024 AI Telemetry Logging