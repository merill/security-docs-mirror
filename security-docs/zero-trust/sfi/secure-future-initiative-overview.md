---
layout: Conceptual
title: Microsoft Secure Future Initiative (SFI) overview | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/secure-future-initiative-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn what Microsoft's Secure Future Initiative is, why Microsoft launched it, and how SFI priorities map to Zero Trust and NIST CSF.
ms.date: 2026-11-09T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: overview
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
locale: en-us
document_id: 1045f075-512f-a8dc-f741-bf196d8e938a
document_version_independent_id: 1045f075-512f-a8dc-f741-bf196d8e938a
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/secure-future-initiative-overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/secure-future-initiative-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/secure-future-initiative-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/0661002d-4d3e-4257-b5a8-1276befa15d4
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/05df39fb-4203-4146-99d8-5ff1e833520c
platformId: 817e61fb-c12b-8df2-57f2-a9e17ca35c00
---

# Microsoft Secure Future Initiative (SFI) overview | Microsoft Learn

The Microsoft Secure Future Initiative (SFI) is a multiyear security transformation program focused on improving how Microsoft designs, builds, tests, and operates products, services, and infrastructure.

SFI helps customers understand what Microsoft prioritized, what changed, and what was learned through implementation at scale. SFI is not a replacement for security frameworks. It provides lessons and practices from Microsoft's experience that reflect Zero Trust principles and inform Security Adoption Framework (SAF) guidance.

## Why Microsoft launched SFI

SFI was launched in November 2023 to drive coordinated, enterprise-wide security improvements across engineering, operations, and governance. The initiative established clear priorities, operating standards, and accountability for reducing systemic risk.

SFI continues to evolve in structured waves as Microsoft learns from implementation and from the changing threat landscape.

## SFI security principles

SFI work is organized around these principles:

- **Secure by design**: Integrate security requirements into architectures and engineering decisions from the start.
- **Secure by default**: Ship and operate services with stronger baseline protections and safer defaults.
- **Secure operations**: Continuously detect, respond, recover, and improve based on threat intelligence and operational evidence.

## Six SFI engineering pillars

SFI execution is organized into six engineering pillars:

1. Protect identities and secrets
2. Protect tenants and isolate systems
3. Protect networks
4. Protect engineering systems
5. Monitor and detect cyberthreats
6. Accelerate response and remediation

These pillars represent where Microsoft prioritized change in its own environment. They are not a replacement taxonomy for Zero Trust, SAF, or NIST CSF.

## Relationship to SAF, Zero Trust, and NIST CSF

The Security Adoption Framework incorporates relevant lessons and practices from Microsoft's SFI experience while connecting organizations to durable architecture, operational, and technology guidance for implementation.

- **SFI**: What Microsoft prioritized, changed, and learned through security transformation
- **SAF**: How organizations can structure and sustain security modernization based on their priorities and risks
- **Zero Trust**: Security principles that guide strategy, architecture, implementation, and operations
- **NIST CSF**: Cybersecurity outcomes and categories used to understand, assess, prioritize, and communicate cybersecurity risk

SFI practices apply Zero Trust principles:

- **Verify explicitly**
- **Use least privilege access**
- **Assume Compromised (Assume breach)**

For more detail on how lessons from SFI connect to customer-facing SAF guidance, see [How Microsoft Secure Future Initiative (SFI) informs SAF](../../saf/foundations/sfi/saf-mapping).

## Pillar mapping

The following table summarizes how each SFI pillar relates to Zero Trust principles and representative NIST CSF functions.

| SFI pillar | Zero Trust emphasis | Representative NIST CSF functions |
| --- | --- | --- |
| Protect identities and secrets | Verify explicitly, Use least privilege, Assume breach | Protect (PR), Detect (DE) |
| Protect tenants and isolate systems | Verify explicitly, Use least privilege, Assume breach | Identify (ID), Protect (PR), Detect (DE) |
| Protect networks | Verify explicitly, Use least privilege, Assume breach | Identify (ID), Protect (PR) |
| Protect engineering systems | Verify explicitly, Use least privilege, Assume breach | Identify (ID), Protect (PR), Govern (GV) |
| Monitor and detect cyberthreats | Verify explicitly, Assume breach | Identify (ID), Protect (PR), Detect (DE), Respond (RS) |
| Accelerate response and remediation | Verify explicitly, Use least privilege, Assume breach | Identify (ID), Respond (RS), Recover (RC), Govern (GV) |

For a more detailed mapping between NIST CSF 2.0 and Microsoft security guidance, see [Integrate NIST CSF 2.0 governance](integrate-nist-2-governance).

## SFI progress reports

Use SFI progress reports to track changes in Microsoft priorities, implementation experience, and outcomes over time.

- [What's new in SFI?](secure-future-initiative-whats-new)
- [July 2026 SFI progress report](https://www.microsoft.com/en-us/trust-center/security/secure-future-initiative/sfi-progress-report-july-2026)
- [November 2025 SFI progress report](https://www.microsoft.com/en-us/trust-center/security/secure-future-initiative/sfi-progress-report-november-2025)
- [April 2025 SFI progress report](https://cdn-dynmedia-1.microsoft.com/is/content/microsoftcorp/microsoft/final/en-us/microsoft-brand/documents/sfi-april-2025-progress-report.pdf)
- [September 2024 SFI progress report](https://cdn-dynmedia-1.microsoft.com/is/content/microsoftcorp/microsoft/final/en-us/microsoft-brand/documents/SFI_September_2024_progress_report.pdf)