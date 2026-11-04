---
layout: Conceptual
title: Protect tenants and isolate systems in the Microsoft Secure Future Initiative (SFI) | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/secure-future-initiative-tenant-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn how to protect tenants and isolate systems in Microsoft's Secure Future Initiative (SFI).
ms.date: 2025-11-03T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: how-to
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
locale: en-us
document_id: c1d5e4fd-3181-e81e-d9ed-5ecc05abdf6c
document_version_independent_id: c1d5e4fd-3181-e81e-d9ed-5ecc05abdf6c
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/secure-future-initiative-tenant-overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/secure-future-initiative-tenant-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/secure-future-initiative-tenant-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/0661002d-4d3e-4257-b5a8-1276befa15d4
- https://authoring-docs-microsoft.poolparty.biz/devrel/540ac133-a371-4dbb-8f94-28d6cc77a70b
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/05df39fb-4203-4146-99d8-5ff1e833520c
- https://authoring-docs-microsoft.poolparty.biz/devrel/60bfc045-f127-4841-9d00-ea35495a5800
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
platformId: 39ddf497-831f-07d7-11b6-26982af2d7f2
---

# Protect tenants and isolate systems in the Microsoft Secure Future Initiative (SFI) | Microsoft Learn

The [Secure Future Initiative (SFI) initiative](secure-future-initiative-overview) is a multiyear, cross-Microsoft initiative to increasingly secure the way in which Microsoft designs, builds, tests, and operates its products and services. SFI is built upon:

- A set of security principles that drive the way in which we innovate on security design, implement those innovations into Microsoft products as secure defaults and standards, and provide internal and external security guidance. [Learn more](secure-future-initiative-overview#security-principles).
- A set of prioritized security pillars and objectives. [Learn more](secure-future-initiative-overview#sfi-pillars-zero-trust-and-nist).

This article summarizes the "Protect tenants and isolate systems" SFI pillar.

## Before you start

- [Learn about](secure-future-initiative-overview#sfi-pillars-zero-trust-and-nist) the SFI pillars.
- [Review and track the latest progress on pillar objectives](secure-future-initiative-whats-new#progress-on-pillar-objectives) in the SFI What's New article.
- Learn about [Zero Trust principles](../zero-trust-overview), and [NIST CSF functions and categories](https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf).
- [Get a list of NIST categories and acronyms](secure-future-initiative-overview#nist-functions) to help as you review the table in this article.

## Pillar and objectives

The aim of the "Protect tenants and isolate systems" pillar is to contain potential threat blast radius by preventing lateral movement or privilege escalation. It ensures that tenant-level security boundaries are correctly configured, hardened, and isolated.

Microsoft objectives and Zero Trust/NIST mapping for this pillar are summarized in the following table.

| **Objective** | **Zero Trust** | **NIST mapping** |
| --- | --- | --- |
| **1. Remove legacy systems that risk security** Maintain the security posture and commercial relationship of tenants by removing all unused, aged, or legacy systems. | **Verify explicitly**: All identity and resource systems are authenticated and validated through modern control planes.**Use least privilege**: Eliminates old systems without modern, fine‑grained controls. **Assume breach**: Removes legacy trust paths and minimizes blast radius. | **ID.AM-02** (*Software platforms and applications within the organization are inventoried*).The first step in removing legacy systems is to discover system elements for full visibility.**ID.AM-08** (*Identities and associated accounts (including service accounts and applications) are inventoried*). Track, manage, and decommission unmanaged accounts, service, machine, and app identities. **PR.PS-01** (*Configuration management practices are established and applied*) Secure platforms and services on a modern foundation. |
| **2. Secure all tenants and their resources** Protect Microsoft, acquired, and employee-created tenants, commerce accounts, and tenant resources in accordance with security best practice baselines. | **Verify explicitly**: Authenticate all tenant‑to‑tenant interactions.**Use least privilege**: Policies and segmentation limit permissions across environments. **Assume breach**: Tenant boundaries assume potential compromise and are designed to contain lateral movement. | **ID.AM-02** (*Software platforms and applications within the organization are inventoried*).Securing tenants requires a complete inventory of tenants, directories, apps, service principals, and platform resources. **PR.IR-01** (*Processes are established to prepare for incident response and reduce potential impact*).Securing tenants and assets enforces tenant-level isolation, baselines, segmentation, and health checks to reduce blast radius and contain incidents.**PR.AA-05** (*Permissions and authorizations are managed, enforced, and periodically verified*).Securing tenants requires consistent authorization and validation.**PR.PS-01** ((*Configuration management practices are established and applied*) Secure platforms and services on a modern foundation. |
| **3. Higher security for Entra ID apps**Manage Microsoft Entra ID applications with a high and consistent security bar. | **Verify explicitly**: Enforce strong authentication and app vetting.**Use least privilege**: App permissions restricted to minimal necessary rights. **Assume breach**: App access designed with containment and monitoring. | **ID.AM-08** (*Maintain an inventory of accounts—including service principals, applications, and identities—and ensure they are managed according to policy*).&lt; br/&gt;**PR.AA-01** (*Access control policy. Govern app access consistently*).**PR.AA-05** (*Authorization is enforced and governed. Enforce app authentication controls*).**PR.IR-01** (*Prepare for effective incident response by establishing processes, controls, and configurations that limit impact and support rapid containment*). |
| **4. Eliminate identity lateral movement**Eliminate identity lateral movement pivots between tenants, environments, and clouds. | **Verify explicitly**: Validate every token and trust boundary crossing.**Use least privilege**: Limit identity reuse and privilege escalation across tenants. **Assume breach**: Design boundaries to contain identity misuse. | **PR.AA-04** (*Access is restricted using segmentation and least‑privilege principles*).Preventing unauthorized lateral movement by enforcing segmentation, boundary controls, and scoped access.**PR.IR-01** (*Processes are established to prepare for incident response and reduce potential impact*).Prepare for effective incident response by implementing controls that reduce blast radius, limit attacker movement, and support rapid containment before an incident occurs.**DE.CM-01** (*Systems and assets are monitored to detect anomalous activity*).Continuously monitor identity, access, and system activity to detect anomalous behavior, policy violations, and indicators of lateral movement. |
| **5. Continuous least-privilege enforcement**Ensure continuous least-privilege access enforcement for apps and users. | **Verify explicitly**: Policies ensure least privilege decisions are verified at every access.**Use least privilege**: Core outcome of this objective — enforce only necessary permissions. | **PR.AA-05** (*Permissions and authorizations are managed, enforced, and periodically verified*).Access permissions and authorizations must be continually managed and enforced, and periodically verified. |
| **6. Secure devices used for access** Adopt fine-grained partitioning of identity signing keys and platform keys. Ensure that only secure, managed, healthy devices are granted access to Microsoft tenants. | **Verify explicitly**: Each device identity is validated and continuously assessed.**Use least privilege**: Device posture gating ensures minimal risk access. | **ID.AM-01** (*Physical devices and systems within the organization are inventoried*).Securing devices requires a complete inventory of all devices allowed to access tenants. **ID.AM-02** (*Software platforms and applications within the organization are inventoried*).Device security checks depend on tracking OS versions, configuration, management state and compliance posture of devices.**PR.AA-01** (*Identities are authenticated commensurate with risk*).Authentication includes device trust. Only secure, compliant devices are allowed.**PR.AA-06** (*Access aligns with least‑privilege principles*).Access is authorized using attributes such as roles, states, processes and aligned with least privilege. |