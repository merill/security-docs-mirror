---
layout: Conceptual
title: Microsoft security best practices overview | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-best-practices-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Overview of Microsoft security best practices
ms.topic: article
ms.service: security
ms.subservice: zero-trust
ms.date: 2026-05-24T00:00:00.0000000Z
locale: en-us
document_id: fa58daad-4451-5d5b-4dae-9eae4aed5195
document_version_independent_id: fa58daad-4451-5d5b-4dae-9eae4aed5195
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-best-practices-overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-best-practices-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-best-practices-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
- https://authoring-docs-microsoft.poolparty.biz/devrel/540ac133-a371-4dbb-8f94-28d6cc77a70b
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
- https://authoring-docs-microsoft.poolparty.biz/devrel/60bfc045-f127-4841-9d00-ea35495a5800
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
platformId: e3b70a1a-fbec-5350-af1d-5660151738d3
---

# Microsoft security best practices overview | Microsoft Learn

Microsoft security best practices are designed to help organizations protect their digital estates by reducing risk, improving resilience, and enabling secure productivity.

- At the core of these best practices is the [Zero Trust security model](zero-trust-overview). Zero Trust assumes that threats exist both inside and outside the network, and emphasizes verifying every access request, enforcing least privilege access, and segmenting resources as we assume breach.

Zero Trust principles are reinforced through a combination of engineering best practices, frameworks, benchmarks, and assessment tools.

## Best practices and recommendations

- **[Microsoft's Secure Future Initiative (SFI)](sfi/secure-future-initiative-overview)**

    A series of best practices and security learning based on Microsoft's multi-year efforts to increasingly secure the way in which we design, build, test, and operate our products. SFI provides a series of best practice patterns that you can learn from and implement. SFI tackles security by pillars. Objectives for each pillar align to one or more [NIST Cybersecurity Framework functions](sfi/secure-future-initiative-overview#sfi-pillars-zero-trust-and-nist).
- **[Microsoft Entra security recommendations](/en-us/entra/fundamentals/configure-security)**

    Check identity and app security configuration and posture. Recommendations aligns to SFI themes. These best practices are included in the [Zero Trust Assessment tool](assessment/overview).
- **[Microsoft Intune device security recommendations](/en-us/intune/intune-service/protect/zero-trust-configure-security)**

    Ensure tenant-level governance and device compliance. Protect data on devices and in transit, and enforce secure access to organizational data. These best practices are included in the [Zero Trust Assessment tool](assessment/overview).
- **[Azure networking security best practices](/en-us/azure/networking/security/zero-trust-network-security)**

    Assess and harden network posture with Azure DDoS protection, Azure Firewall, Azure Web Application Firewall on Application Gateway or Azure Front Door. These best practices are included in the [Zero Trust Assessment tool](assessment/overview).
- **[Data security best practices](/en-us/purview/zero-trust-microsoft-purview)**

    Check Microsoft Purview configuration settings for data security posture. These best practices are included in the [Zero Trust Assessment tool](assessment/overview).
- The **[Microsoft Cloud Security Benchmark (MCSB)](/en-us/security/benchmark/azure/overview)**

    Provides a series of best practices and recommendations for improving the security of workloads, data, and services on Azure.
- Other Microsoft Defender products such as [Defender for Cloud](/en-us/azure/defender-for-cloud/concept-cloud-security-posture-management) and [Security Exposure Management](/en-us/security-exposure-management/microsoft-security-exposure-management), and [Microsoft Purview Compliance Manager](/en-us/purview/compliance-manager) also monitor and assess your enterprise security posture, providing actionable security and compliance insights and recommendations.
- External best practices and framework also provide Zero Trust security principles and guidance. [Learn more](security-zero-trust-frameworks).