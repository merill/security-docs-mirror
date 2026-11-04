---
layout: Conceptual
title: Microsoft Zero Trust Workshop - AI security | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/workshop-zero-trust-ai-security
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn about the AI security pillar in the Microsoft Zero Trust Workshop
ms.date: 2026-05-31T00:00:00.0000000Z
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
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/8a94907f-2511-4271-b5ca-ec7f2e75067c
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/bffa8e88-f633-409d-a24d-083bdbc68872
platformId: 718678de-dfdf-2f6a-6054-a7593e78a2d1
---

# Microsoft Zero Trust Workshop - AI security | Microsoft Learn

AI amplifies existing security risk and introduces new risks and considerations across identities, data, applications, and user interactions. These risks can be addressed using Zero Trust principles.

Securing AI isn't only about protecting the underlying AI models and services. We also need to ensure that AI system access, use, and governance aligns with Zero Trust principles.

AI pillar guidance focuses on establishing visibility into AI usage, enforcing strong identity and access controls, protecting data across prompts and outputs, securing agent development and runtime environments, and integrating AI signals into security operations.

## Workshop implementation

The AI workshop covers the implementation areas summarized in the table.

| **Area** | **Details** |
| --- | --- |
| **Map and assess AI risk** | Discover and inventory AI agents, applications, and services across the organization.Assess AI risks using centralized security insights, review inventory and prioritize findings, and establish governance, ownership, and acceptable-use policies.Implement continuous monitoring and remediation for evolving AI risks. |
| **Register agents** | Register AI agents in a centralized registry to maintain visibility and control.Classify and organize agents based on purpose and risk, assign ownership and accountability, and define publishing, certification, and lifecycle |
| **Secure AI authentication and access** | Enforce identity-based access controls for AI systems and agents.Apply Conditional Access, risk-based and attribute-based policies, and identity governance processes to ensure only authorized users and services can interact with AI resources. |
| **Secure AI network access** | Control how AI services are accessed across the network. Route traffic through secure access controls, apply filtering and inspection policies for AI interactions, and protect against risks such as prompt injection and unauthorized access paths. |
| **Secure AI data access** | Protect sensitive data used in AI prompts, grounding, and outputs.Apply classification, labeling, and DLP policies, control access to connected data sources, and monitor for oversharing and data exposure risks in AI interactions. |
| **Build agents securely** | Secure the development and deployment of AI agents by enforcing authentication, authorization, and data handling standards.Integrate content safety controls, require validation and red teaming, and establish secure publishing and deployment processes. |
| **Detect and respond for AI** | Monitor AI activity and detect threats such as misuse, anomalies, and prompt-based attacks.Integrate AI signals into security operations, enable investigation and response workflows, and continuously improve detection and response capabilities. |