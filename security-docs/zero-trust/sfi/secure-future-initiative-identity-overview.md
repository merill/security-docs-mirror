---
layout: Conceptual
title: Protect identities and secrets in the Microsoft Secure Future Initiative (SFI) | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/secure-future-initiative-identity-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn how to protect identities and secrets in Microsoft's Secure Future Initiative (SFI).
ms.date: 2025-11-03T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: overview
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
locale: en-us
document_id: b9c99b90-dc61-65e8-5017-d4fe3398db57
document_version_independent_id: b9c99b90-dc61-65e8-5017-d4fe3398db57
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/secure-future-initiative-identity-overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/secure-future-initiative-identity-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/secure-future-initiative-identity-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/0661002d-4d3e-4257-b5a8-1276befa15d4
- https://authoring-docs-microsoft.poolparty.biz/devrel/540ac133-a371-4dbb-8f94-28d6cc77a70b
- https://authoring-docs-microsoft.poolparty.biz/devrel/f488294d-f483-456e-94e3-755f933b811b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/05df39fb-4203-4146-99d8-5ff1e833520c
- https://authoring-docs-microsoft.poolparty.biz/devrel/60bfc045-f127-4841-9d00-ea35495a5800
- https://authoring-docs-microsoft.poolparty.biz/devrel/02662057-0b9b-40f4-a3c7-537125b6d283
platformId: ebd32cb0-166c-005f-8fa2-c77628b83de9
---

# Protect identities and secrets in the Microsoft Secure Future Initiative (SFI) | Microsoft Learn

The [Secure Future Initiative (SFI) initiative](secure-future-initiative-overview) is a multiyear, cross-Microsoft initiative to increasingly secure the way in which Microsoft designs, builds, tests, and operates its products and services. SFI is built upon:

- A set of security principles that drive the way in which we innovate on security design, implement those innovations into Microsoft products as secure defaults and standards, and provide internal and external security guidance. [Learn more](secure-future-initiative-overview#security-principles).
- A set of prioritized security pillars and objectives. [Learn more](secure-future-initiative-overview#sfi-pillars-zero-trust-and-nist).

This article provides an overview of the "Protect identities and secrets" SFI pillar.

## Before you start

- [Learn about](secure-future-initiative-overview#sfi-pillars-zero-trust-and-nist) the SFI pillars.
- [Review and track the latest progress on pillar objectives](secure-future-initiative-whats-new#progress-on-pillar-objectives) in the SFI What's New article.
- Learn about [Zero Trust principles](../zero-trust-overview), and [NIST CSF functions and categories](https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf).
- [Get a list of NIST categories and acronyms](secure-future-initiative-overview#nist-functions) to help as you review the table in this article.

## Pillar and objectives

The "Protect identities and secrets" pillar aims to:

- Strengthen trust in every identity and credential used across Microsoft systems by eliminating weaknesses in how accounts, tokens, and secrets are issued, stored, and used.
- Reduce the risk of unauthorized access by enforcing standards to harden the identity and secrets infrastructure, and to control user and application authentication and authorization.

Microsoft objectives and Zero Trust/NIST mapping for this pillar are summarized in the following table.

| **Pillar objective** | **Zero Trust** | **NIST mapping** |
| --- | --- | --- |
| **1. Protect cryptographic signing keys**Protect identity infrastructure signing and platform keys with rapid and automatic rotation of identity infrastructure keys, using hardware storage and protection. | **Verify explicitly**: Protect identity signing assets. Build strong attestation of keys into workflows.**Assume breach**: Protect keys as if compromise can occur, using hardware‑assisted isolation. | **PR.AA-04** (*Access is restricted using segmentation and least privilege*) Key protection relies on strict access segmentation and least-privilege authorization to restrict key use to isolated, dedicated key vault environments, and remove unneeded access and lateral movement paths to key storage.**PR.PS-01** (*Assets are formally evaluated to ensure they meet security requirements before being approved for use*) Keys must be generated and stored in accordance with secure-by-default standards. |
| **2. Adopt standard SDKs for identity**Strengthen identity standards and drive standards adoption with the use of standard SDKs across applications, so that apps and services use a uniform, hardened library for validating tokens. | **Verify explicitly**: Standard validated libraries reduce variability and risk. Use consistent validation.**Assume breach**: Reduces attack surface from custom implementations. | **PR.AA-01** (*Identities are authenticated commensurate with risk*) Using standard SDKs enforces strong, consistent authentication flows.**PR.AA-02** (*Access is authorized using role‑based attributes*) Standard SDKs integrate with Microsoft Entra RBAC and enforce role-aware token claims.**PR.AA-03** (*Access is authorized using attribute‑based/contextual attributes*) Standard SDKs automatically apply conditional access, device context, MFA requirements, and risk signals for contextual authorization. |
| **3. Enforce phishing-resistant MFA**Ensure user accounts are protected with securely manEnforcaged, phishing-resistant MFA. | **Verify explicitly**: Strong authentication techniques verify user identity every access attempt.**Use least privilege**: MFA strengthens least‑privilege enforcement by reducing unauthorized access. | **PR.AA-01** (*Identities are authenticated commensurate with risk*) Phishing-reisistant MFA uses strong, risk-appropriate authentication.**PR.AA-03** (*Access is authorized using attribute‑based and contextual attributes*) Phishing-resistant MFA strengthens contextual-access decisions. |
| **4. Safe secrets standard** Shift away from long-lived secrets such as service account credentials to ensure that applications are protected with system-managed credentials such as managed identities. | **Use least privilege**: Restrict secrets access. Avoid hard‑coded or persistent credentials.**Assume breach**: Treat every secret as potentially compromised unless strongly guarded. | **PR.AA-04** (*Access is restricted using segmentation and least‑privilege principle*) Safe secrets standards restrict which identity and services can access or use secrets, enforcing least-privilege and eliminating lateral movement paths caused by static credentials.**PR.DS-01** (*Data is managed consistent with enterprise requirements*) Secrets are handled in accordance with lifecycle and storage requirements such as centralized vaulting, rotation, and logging.**PR.PS-01** (*Assets are formally evaluated to ensure they meet security requirements before being approved for use*) Using safe secrets means that apps and services must comply with security baselines. |
| **5. Stateful validation for identity tokens**Ensure identity tokens are protected with stateful and duration validation. | **Verify explicitly**: Fully validate identity tokens at every enforcement point.**Assume breach**: Ensure invalid or malformed tokens are rejected. | **PR.AA-03** (*Access is authorized using attribute‑based and contextual attributes*) Token validation supplies real-time identity context for authorization decisions.**DE.AE-02** (*Detected events are analyzed to understand attack targets and methods*) Stateful validation detects anomalous activity such as forged tokens, and unusual token usage.**DE.AE-07** (*Processes detect and analyze anomalous activity to support response and recovery*)  Since tokens are checked continuously, SFI can identify and respond quickly to unauthorized token activity, to improve detection and shrink attacker dwell times. |
| **6. Fine-grained key partitioning**Adopt more fine-grained partitioning of identity signing keys and platform keys. | **Use least privilege**: Partitioning limits privilege scopes for key usage.**Assume breach**: Limits impact if key segment is compromised. | **PR.AA-04** (*Access is restricted using segmentation and least‑privilege principles*) Fine-grained key partitioning enforces strict segmentation of key material, preventing lateral movement across key assets.**PR.AA-05** (*Permissions and authorizations are managed, enforced, and periodically verified*) Partitioned keys require tight authorization controls, continuous verification, and boundary enforcement to ensure that only correct services identities can access isolated key partitions. |
| **7. Quantum-safe PKI systems**Ensure identity and certificate PKI systems are ready for a post-quantum cryptography world. | **Verify explicitly**: Use post‑quantum cryptography for identity assertions.**Assume breach**: Anticipate future threats; prepare for stronger resistance. | **PR.AA-04** (*Access is restricted using segmentation and least‑privilege principles*) Quantum-safe PKI requires segmented, least-privilege access to key-signing systems, CAs, HSMS, etc. |