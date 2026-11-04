---
layout: Conceptual
title: Protect engineering systems in the Microsoft Secure Future Initiative (SFI) | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/secure-future-initiative-engineering-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn how to protect engineering systems in Microsoft's Secure Future Initiative (SFI).
ms.date: 2025-11-03T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: overview
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
locale: en-us
document_id: fce775e2-e1db-30fc-4c70-18733400381d
document_version_independent_id: fce775e2-e1db-30fc-4c70-18733400381d
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/secure-future-initiative-engineering-overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/secure-future-initiative-engineering-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/secure-future-initiative-engineering-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/5bd2b3fa-c186-4b92-a3c8-09f22a249d37
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/540ac133-a371-4dbb-8f94-28d6cc77a70b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7eba7926-b7b2-4a7a-bf89-e6ac53b3e7f6
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/60bfc045-f127-4841-9d00-ea35495a5800
platformId: 88d5919d-9680-7dea-ad2b-4cfc47c5c67b
---

# Protect engineering systems in the Microsoft Secure Future Initiative (SFI) | Microsoft Learn

The [Secure Future Initiative (SFI) initiative](secure-future-initiative-overview) launched in November 2023 as a multiyear effort to increasingly secure the way in which Microsoft designs, builds, tests, and operates its products and services.

SFI architecture design focuses on a set of security principles that are adopted and integrated into Microsoft culture and governance. These security principles are applied to a set of focused engineering pillars by means of processes, standards, and continuous improvements.

This article summarizes the "Protect engineering systems" SFI pillar.

## Before you start

- [Learn about](secure-future-initiative-overview#sfi-pillars-zero-trust-and-nist) the SFI pillars.
- [Review and track the latest progress on pillar objectives](secure-future-initiative-whats-new#progress-on-pillar-objectives) in the SFI What's New article.
- Learn about [Zero Trust principles](../zero-trust-overview), and [NIST CSF functions and categories](https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf).
- [Get a list of NIST categories and acronyms](secure-future-initiative-overview#nist-functions) to help as you review the table in this article.

## Pillar and objectives

The "Protect engineering systems" pillar aims for strengthening security across development and engineering by operationationalizing the asset inventory, implementing Zero Trust principles, securing pipelines, and strengthening isolation and resiliency.

Microsoft objectives and Zero Trust/NIST mapping for this pillar are summarized in the following table.

| **Pillar objective** | **Zero Trust** | **NIST mapping** |
| --- | --- | --- |
| **1. Complete software asset inventory**Inventory spans all Azure DevOps repositions and pipelines with full metadata. StartRight tooling ensures that 80% of assets are inventoried at creation, and rest are captured within 24 hours. This enables rapid incident response and universal policy enforcements. We increased inventory scope with more fine-grained ownership for better response. | **Verify explicitly**: Protect identity signing assets. Strong attestation of keys built into workflow. &gt;**Assume breach**: Protect keys as if compromise can occur, using hardware‑assisted isolation. | **ID.AM-02** (*Software platforms and applications within the organization are inventoried*). Maintaining a complete inventory of all engineering software assets aligns directly with NIST’s requirement to track and govern all software/platform components. |
| **2. Zero Trust for source code access**Reduced standing access for admin roles, and just-in-time elevation required. Azure DevOps OAuth-based apps leverage Microsoft Entra authentication with conditional access enforcement. Proof-of-presence checks cover almost all production code changes. | **Verify explicitly**: Standard validated libraries reduce variability and risk. Use consistent validation.**Assume breach**: Reduces attack surface from custom implementations. | **PR.AA-01** (*Identities are authenticated commensurate with risk*).**PR.AA-02** (*Access is authorized using role‑based attributes*). Strong authentication before code access.**PR.AA-03** (*Access is managed using contextual attributes*).  Device, location, session risk checked before repo access.**PR.AA-04** (*Access is restricted based on segmentation and least privilege*).  Enforcement of repo, branch, and environment segmentation.**PR.AA-05** (*Permissions are managed, enforced, and periodically verified*).  Continuous review of code‑access permissions.**PR.AA-06** (*Access aligns with least privilege*).  Zero Trust assures minimal access to code repos.**PR.DS-01** (*Data is managed consistent with enterprise policies*).  Controls for handling sensitive source code.**PR.DS-02** (*Data is protected when stored*).  Repo encryption and secure storage for code.**PR.DS-10** (*Access to data is monitored to detect unauthorized activity*).  Monitoring source code for anomalies. |
| **3. Secure code development**Code signing access is almost entirely locked to production identities. Repositories enforce branch policies with minimum approver counts. The scope of this objective has increased to optimize our secrets detection capabilities. We introduced analytics-driven validation to strengthen compliance and durability, positioning us to reduce systemic risk across engineering workflows. | **Verify explicitly**: Strong authentication techniques verify user identity every access attempt.**Use least privilege**: MFA strengthens least‑privilege enforcement by reducing unauthorized access. | **PR.AA-04** (*Access is restricted using segmentation and least privilege*).  Pipeline design enforces code‑handling rules.**PR.PS-06** (*Services/processes are validated to comply with security requirements before execution*). Code must meet policy + pipeline security gates before deployment. |
| **4. Standardize secure dev pipelines** Supply chain protections are maturing: Internal artifact feeds are broadly adopted and Component Governance runs by default. AI agents now remediate open-source vulnerabilities asynchronously, reducing latency between detection and resolution. These steps deliver significant gains in security posture and operational resilience, ensuring the engineering system maintains high standards across the software supply chain. | **Use least privilege**: Restrict secret access. Avoid hard‑coded or persistent credentials.**Assume breach**: Treat every secret as potentially compromised unless strongly guarded. | **PR.DS-02** (*Data is protected when stored*).  Secure storage for build artifacts and secrets.**PR.DS-10** (*Access to data is monitored*).  Monitoring pipeline artifacts and logs**PR.IR-01** (*Processes prepare for effective incident response*).  Pipelines include logging, alerting, rollback, provenance.**PR.PS-06** (*Processes/services are checked against security requirements before execution)*.  Pipelines enforce mandatory security gates. |
| **5. Protect the software supply chain**Ensure identity tokens are protected with stateful and duration validation. | **Verify explicitly**: Fully validate identity tokens at every enforcement point.**Assume breach**: Ensure invalid or malformed tokens are rejected. | **GV.SC-01** (*Supply chain risk governance is established*).**GV.SC-02** (*Suppliers and dependencies are identified*).**GV.SC-03** (*Suppliers are evaluated for risk*).**GV.SC-04** (*Security requirements for suppliers are established*).**GV.SC-07** (*Supply chain components are monitored for risk*).**GV.SC-09** (*Suppliers/components are validated to meet requirements)*.**ID.RA-10** (*Risks from suppliers and dependencies are assessed*).**PR.PR-06** (*Processes/services are validated to meet security requirements before execution*). |