---
layout: Conceptual
title: Zero Trust Assessment Overview | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/assessment/overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Explore the Zero Trust Assessment to automate security checks, implement industry standards, and strengthen your organization’s Zero Trust architecture.
ms.service: security
ms.subservice: zero-trust
ms.topic: overview
ms.date: 2025-10-30T00:00:00.0000000Z
ms.reviewer: joflore
locale: en-us
document_id: 6c83bbaa-56db-1823-ab2e-e4c568aaf992
document_version_independent_id: 6c83bbaa-56db-1823-ab2e-e4c568aaf992
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/assessment/overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/assessment/overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/assessment/overview.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/a72e95ff-4b4f-4cc1-90c6-7dcba67ff05f
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/24dc3ccd-591a-4415-a1fe-8759afafcb12
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
platformId: 08b7a66c-3fc0-d7b4-52bb-8faa1001ae6b
---

# Zero Trust Assessment Overview | Microsoft Learn

We publish extensive guidance on how to configure [Microsoft Entra](/en-us/entra/fundamentals/configure-security), [Microsoft Intune](/en-us/intune/intune-service/protect/zero-trust-configure-security), [Azure networks](/en-us/azure/networking/security/zero-trust-network-security) and [Microsoft Purview](/en-us/purview/configure-security) for increased security, but manually checking these against a tenant's configuration can be time-consuming and error-prone. The Zero Trust Assessment transforms this process with automation to test for hundreds of security configuration items aligned with the Secure Future Initiative (SFI) and Zero Trust pillars, then guides you through remediation steps to help operationalize Zero Trust principles.

These tests are drawn from trusted sources in cybersecurity, including:

- Industry standards like those developed by NIST, CISA, and CIS
- Microsoft's internal security baselines that protect Microsoft's own infrastructure
- Real-world customer insights from thousands of security implementations

[![Screenshot of a sample report output from the Zero Trust Assessment tool.](media/results-overview.png)](media/results-overview-full.png#lightbox)

## Why run this assessment?

Running this assessment helps you confirm you've configured a strong baseline of security for your tenant. It lets you know where you might need to make investments and where you already align with best practices. From this baseline, you might implement even stronger or more advanced controls.

## Open source and transparent

**See exactly what the assessment does.** The entire codebase is open source and available for review:

- View the source code: [GitHub repository](https://github.com/microsoft/zerotrustassessment/tree/main/src/powershell)
- Report issues: [GitHub issues](https://github.com/microsoft/zerotrustassessment/issues)
- Contribute improvements: Community contributions welcome