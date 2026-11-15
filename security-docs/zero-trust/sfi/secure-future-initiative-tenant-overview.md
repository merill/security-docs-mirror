---
layout: Conceptual
title: Protect tenants and isolate systems in the Microsoft Secure Future Initiative (SFI) | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/secure-future-initiative-tenant-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Learn the security outcomes, priorities, and lessons from the tenant isolation pillar in Microsoft's Secure Future Initiative.
ms.date: 2026-11-09T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: overview
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
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0661002d-4d3e-4257-b5a8-1276befa15d4
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/05df39fb-4203-4146-99d8-5ff1e833520c
platformId: 39ddf497-831f-07d7-11b6-26982af2d7f2
---

# Protect tenants and isolate systems in the Microsoft Secure Future Initiative (SFI) | Microsoft Learn

This pillar focuses on reducing blast radius by enforcing stronger boundaries between tenants, environments, and administrative paths.

## Security outcome Microsoft prioritized

Microsoft prioritized containment of lateral movement and reduction of cross-tenant and cross-environment risk through explicit boundary design and governance.

## What Microsoft prioritized

- Stronger tenant and environment isolation boundaries
- Reduced implicit trust in cross-tenant access paths
- Hardened controls for privileged administration and service identities
- Retirement of legacy systems that weaken boundary security
- Improved consistency of tenant baselines and policy enforcement

## Lessons from SFI implementation

- Boundary controls are most effective when identity, device, and tenant governance are implemented together.
- Legacy dependencies can reintroduce trust paths unless they are actively removed.
- Isolation standards must be continuously validated as environments change.

## Zero Trust and NIST CSF alignment

This pillar primarily applies **Verify explicitly**, **Use least privilege access**, and **Assume breach**.

Representative NIST CSF mappings:

- **Identify (ID)** for tenant and identity inventory
- **Protect (PR)** for boundary, access, and configuration controls
- **Detect (DE)** for lateral movement and policy-violation detection

## Use canonical implementation guidance

Use these resources for implementation details:

- [Cross-tenant access settings](/en-us/entra/external-id/cross-tenant-access-overview)
- [Tenant restrictions v2](/en-us/entra/external-id/tenant-restrictions-v2)
- [Privileged access strategy](/en-us/security/zero-trust/security-adoption-discipline-identity-access-privileged-strategy)
- [Azure security benchmark](/en-us/security/benchmark/azure/)

## Related SFI pattern pages

- [Eliminate identity lateral movement](eliminate-identity-lateral-movement)
- [Remove legacy systems that risk security](remove-legacy-systems-that-risk-security)
- [Higher security for Microsoft Entra ID apps](higher-security-microsoft-entra-id-apps)
- [Secure all tenants and their resources](secure-all-tenants-resources)
- [Secure Admin Workstations (SAW) devices and how they are used](saw-devices)