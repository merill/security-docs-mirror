---
layout: Conceptual
title: Protect networks in the Microsoft Secure Future Initiative (SFI) | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/secure-future-initiative-network-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn how to protect networks in Microsoft's Secure Future Initiative (SFI).
ms.date: 2025-11-03T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: overview
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
locale: en-us
document_id: f503f865-0cf3-c9f8-162e-ee4a5cb3b317
document_version_independent_id: f503f865-0cf3-c9f8-162e-ee4a5cb3b317
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/secure-future-initiative-network-overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/secure-future-initiative-network-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/secure-future-initiative-network-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/540ac133-a371-4dbb-8f94-28d6cc77a70b
- https://authoring-docs-microsoft.poolparty.biz/devrel/0661002d-4d3e-4257-b5a8-1276befa15d4
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/60bfc045-f127-4841-9d00-ea35495a5800
- https://authoring-docs-microsoft.poolparty.biz/devrel/05df39fb-4203-4146-99d8-5ff1e833520c
platformId: ff4dfea4-98c4-8f2e-f293-814e60c4e67d
---

# Protect networks in the Microsoft Secure Future Initiative (SFI) | Microsoft Learn

The [Secure Future Initiative (SFI) initiative](secure-future-initiative-overview) is a multiyear, cross-Microsoft initiative to increasingly secure the way in which Microsoft designs, builds, tests, and operates its products and services. SFI is build upon:

- A set of security principles that drive the way in which we innovate on security design, implement those innovations into Microsoft products as secure defaults and standards, and provide internal and external security guidance. [Learn more](secure-future-initiative-overview#security-principles).
- A set of prioritized security pillars and objectives. [Learn more](secure-future-initiative-overview#sfi-pillars-zero-trust-and-nist).

This article summarizes the "Protect networks" SFI pillar.

## Before you start

- [Learn about](secure-future-initiative-overview#sfi-pillars-zero-trust-and-nist) the SFI pillars.
- [Review and track the latest progress on pillar objectives](secure-future-initiative-whats-new#progress-on-pillar-objectives) in the SFI What's New article.
- Learn about [Zero Trust principles](../zero-trust-overview), and [NIST CSF functions and categories](https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf).
- [Get a list of NIST categories and acronyms](secure-future-initiative-overview#nist-functions) to help as you review the table in this article.

## Pillar and objectives

The aim of the "Protect networks" pillar is to limit adversary movement and unauthorized access across corporate networks. Networks are segmented and isolated with fine-grained network controls. Every connection is verified, controlled, and continuously monitored.

Microsoft objectives and Zero Trust/NIST mapping for this pillar are summarized in the following table.

| **Objective** | **Zero Trust** | **NIST mapping** |
| --- | --- | --- |
| **1. Inventory and security standards**Secure Microsoft production networks and systems connected to networks with improved network isolation, monitoring, accurate inventory, and secure operations. | **Verify explicitly**: Know what devices are present and who/what they connect to.**Assume breach**: Full inventory supports detection and containment of breaches. | **ID.AM-01** (*Physical devices and systems within the organization are inventoried*).  All network devices are inventoried and tracked, recognized, managed, and governed.**ID.AM-03** (*Assets are classified—consistent with organizational risk strategy*).Networks and infrastructure are inventoried and classified. **PR.AA-05** (*Access permissions and authorizations are managed, enforced, and periodically verified*). SFI applied security standards to network infrastructure.**PR.PS-01** (*Assets are formally evaluated to ensure they meet security, compliance, and resilience requirements before being approved for use*). Network assets are only allowed when they pass baseline security requirements.**PR.PS-04** (*Assets are evaluated and validated against security requirements before being authorized for use*).Network infrastructure must meet SFI security standards before use. |
| **2. Network isolation**Apply identity-aware network isolation and microsegmentation to Microsoft production environments, creating additional layers of defense against attackers. | **Verify explicitly**: Authenticate and authorize network flows before allowing communication. **Use least privileged access**: Restrict lateral movement and limit network access rights.**Assume breach**: Assume attackers may be in the network; isolate segments for containment. | **PR-IR-01** (*Processes are established to prepare for incident response and reduce potential impact*).**PR-PS-01** (*Security configuration requirements are established and applied*). Network isolation requires enforcing standardized network‑security baselines (segmentation rules, ACLs, routing controls, boundary protections).**PR-PS-04** (*Assets are validated to meet security requirements before being authorized for use*). Network segments, gateways, and boundary systems must meet SFI isolation standards (hardening, compliance, segmentation posture) before being allowed to connect to production networks. |
| **3. Secure customer cloud networks**Accelerate adoption of network security perimeter (NSP) to place entries resources under modern perimeter enforcement and segmentation to ensure network traffic is validated and only allowed where necessary to reduce the risk of lateral movement and unauthorized access. | **Verify explicitly**: NSP enforces strong validation of traffic entering protected segments. **Use least privileged access**: Only necessary traffic is allowed to traverse network boundaries.**Assume breach**: Perimeter enforcement assumes threat presence and restricts spread. | **PR.IR-01** (*Processes are established to prepare for incident response and reduce potential impact)*.Network hardening and isolation of customer cloud networks reduce blast radius and ensure Microsoft can contain incidents quickly by limiting pivot paths into or across customer environments.**PR-PS-01** (*Security configuration requirements are established and applied*). Customer cloud networks must meet SFI security baselines (segmentation, routing controls, firewall posture, logging, access restrictions) before being connected or allowed to serve production workloads. |