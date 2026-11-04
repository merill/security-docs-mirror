---
layout: Conceptual
title: 6. Runtime Isolation and Sandboxing | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/catalog-ai-defense-capabilities/runtime-isolation-sandboxing
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: ridive
author: richarddiver-ms
description: Explains how runtime isolation and sandboxing limit AI actions and reduce risk
ms.date: 2026-07-28T00:00:00.0000000Z
ms.custom: msecd-doc-authoring-1012
ms.topic: concept-article
ms.service: security
ms.subservice: zero-trust
locale: en-us
document_id: cc0bc29d-7a0c-eab8-82e1-b859537f616c
document_version_independent_id: cc0bc29d-7a0c-eab8-82e1-b859537f616c
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/catalog-ai-defense-capabilities/runtime-isolation-sandboxing.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/catalog-ai-defense-capabilities/runtime-isolation-sandboxing
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/catalog-ai-defense-capabilities/runtime-isolation-sandboxing.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
- https://authoring-docs-microsoft.poolparty.biz/devrel/dcc344b3-3794-4849-9766-7ea55b09218c
- https://authoring-docs-microsoft.poolparty.biz/devrel/d44a5346-5de4-439c-b804-7b2a536cbb55
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
- https://authoring-docs-microsoft.poolparty.biz/devrel/54120bfe-7774-429b-9674-ff285a2c9445
- https://authoring-docs-microsoft.poolparty.biz/devrel/da41a22b-b7a0-42d3-9c35-50da1c2b7b87
platformId: affc5352-0f2f-13f6-6a91-77f559cd3225
---

# 6. Runtime Isolation and Sandboxing | Microsoft Learn

## What this group defends against

What the AI and its tools can actually do at execution time. Contains insecure output handling, vulnerable plugins, excessive agency, agent sprawl, and grounding-driven harmful actions.

## Core capabilities

Runtime isolation constrains what an AI system can do when a prompt, model response, plugin, or generated code path behaves unexpectedly. Rather than allowing open-ended access to hosts, networks, files, or APIs, the runtime should expose narrowly defined capabilities inside short-lived, segmented environments. Each tool call should pass through a policy-enforcing mediation layer, and higher-risk actions should require stronger identity checks, approval, and auditable execution.

- **Isolate execution:** run generated code and third-party components in hardened containers, sandboxes, or confidential environments with restricted filesystems, resources, libraries, and lifetimes.
- **Mediate capabilities:** place schemas, argument validation, authorization, quotas, and approval gates in front of plugins and tools instead of exposing general shell, database, or network access.
- **Contain communications:** segment agents, services, and environments; use private connectivity and egress allow lists; and separate development, test, production, internal, and external trust zones.

## Which technologies do we use?

Runtime protection is implemented as a layered execution architecture. The technologies below isolate code and plugins, mediate every API and tool call, protect sensitive computation while data is in use, constrain network paths, and expose only narrowly defined capabilities so a compromised or misdirected agent cannot freely reach the host, network, or downstream systems.

- **Azure Container Instances, Azure Kubernetes Service, and container runtimes** — isolated execution environments for generated code, tools, and plugins. Use non-root identities, read-only filesystems, minimal images, resource limits, short-lived containers, restricted mounts, seccomp, AppArmor or SELinux profiles, image scanning, and workload isolation to constrain compromise.
- **Azure API Management** — a managed API gateway that mediates access to tools and model endpoints. Use Microsoft Entra token validation, client-certificate checks, IP restrictions, request and response transformation, schema and content validation, rate and token limits, quotas, logging, and backend routing to enforce an agent’s allowed actions.
- **Azure Confidential Computing** — hardware-backed trusted execution environments that protect code and data while in use. Confidential virtual machines and confidential containers can reduce exposure of sensitive prompts, model weights, keys, and intermediate data to host administrators or a compromised hypervisor, with attestation used to verify the trusted environment.
- **Azure network security services** — services such as virtual networks, network security groups, Azure Firewall, private endpoints, Private DNS, and service tags. Use them to deny public exposure, segment agents from tools and data stores, restrict east-west traffic, allow-list outbound destinations, and separate development, test, and production trust zones.
- **Sandboxes, API wrappers, and capability mediation** — architectural patterns rather than products. Expose narrow typed operations instead of general shell, filesystem, database, or network access; validate every argument; apply time, memory, recursion, and egress limits; and require approval for high-impact operations.

## Framework mapping

**[OWASP Top 10 for LLM and Generative AI](https://genai.owasp.org/llm-top-10/) (2025)**: Maps to LLM05 Improper Output Handling and LLM06 Excessive Agency by constraining how generated code, plugins, tools, and agents execute. Isolation, capability mediation, egress controls, and approval gates prevent model output or tool calls from becoming uncontrolled production actions.

**[MITRE ATLAS](https://atlas.mitre.org/mitigations)**: Maps directly to AML.M0011 Restrict Library Loading and AML.M0012 Encrypt Sensitive Information. Sandboxing, capability mediation, network segmentation, confidential computing, and controlled deployment paths are complementary implementation controls; the prior reference to AML.M0017 was removed because AI Model Distribution Methods is not a runtime-isolation mitigation.

**[NIST AI RMF 1.0 and NIST AI 600-1](https://www.nist.gov/itl/ai-risk-management-framework)**: Supports **MANAGE** through containment, separation of environments, safe failure modes, resilience boundaries, and controls that limit blast radius when an agent, plugin, generated-code path, or external tool behaves unexpectedly.