---
layout: Conceptual
title: Protect networks in the Microsoft Secure Future Initiative (SFI) | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/secure-future-initiative-network-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Learn the security outcomes, priorities, and lessons from the network pillar in Microsoft's Secure Future Initiative.
ms.date: 2026-11-09T00:00:00.0000000Z
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
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0661002d-4d3e-4257-b5a8-1276befa15d4
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/05df39fb-4203-4146-99d8-5ff1e833520c
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: ff4dfea4-98c4-8f2e-f293-814e60c4e67d
---

# Protect networks in the Microsoft Secure Future Initiative (SFI) | Microsoft Learn

This pillar focuses on reducing unauthorized connectivity and limiting lateral movement across Microsoft network environments.

## Security outcome Microsoft prioritized

Microsoft prioritized stronger segmentation, clearer boundary controls, and higher assurance for access to sensitive network paths and management planes.

## What Microsoft prioritized

- Better inventory and governance for production network assets
- Stronger isolation and segmentation controls
- Identity-aware policy enforcement for network access
- Reduced implicit trust in internal network paths
- Stronger monitoring for network boundary violations

## Lessons from SFI implementation

- Segmentation succeeds when inventory quality and ownership are clear.
- Boundary and identity controls are interdependent for practical containment.
- Network hardening has to be treated as a continuous operating process, not a one-time project.

## Zero Trust and NIST CSF alignment

This pillar primarily applies **Verify explicitly**, **Use least privilege access**, and **Assume breach**.

Representative NIST CSF mappings:

- **Identify (ID)** for network asset inventory and classification
- **Protect (PR)** for segmentation, isolation, and policy enforcement

## Use canonical implementation guidance

Use these resources for implementation details:

- [Secure networks with Zero Trust](/en-us/security/zero-trust/deploy/networks)
- [Azure network security architecture](/en-us/azure/architecture/reference-architectures/hybrid-networking/)
- [Azure landing zone network topology and connectivity](/en-us/azure/cloud-adoption-framework/ready/landing-zone/design-area/network-topology-and-connectivity)

## Related SFI pattern pages

- [Network isolation](network-isolation)
- [Teams end-to-end encryption](teams-end-to-end-encryption)