---
layout: Conceptual
title: Overview - Use Zero Trust security to prepare for AI companions, including Microsoft Copilots | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/copilots/apply-zero-trust-copilots-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn how to apply the principles of Zero Trust to your environment to prepare for AI tools that include Web-grounded prompts, Microsoft 365-grounded prompts, and prompts grounded in data from your security tools.
ms.date: 2025-02-06T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.service: security
ms.subservice: zero-trust
ms.topic: overview
ms.collection:
- msftsolution-copilot
- msftsolution-scenario
- zerotrust-m365-security
- zerotrust-solution
- zerotrust-copilot
- msec-ai-copilot
- trust-pod
locale: en-us
document_id: a95ccfe1-7f00-109d-e495-d469362fd496
document_version_independent_id: a95ccfe1-7f00-109d-e495-d469362fd496
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/copilots/apply-zero-trust-copilots-overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/copilots/apply-zero-trust-copilots-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/copilots/apply-zero-trust-copilots-overview.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: fd8df7cf-2d50-4472-7c5c-ce0a5c0967a1
---

# Overview - Use Zero Trust security to prepare for AI companions, including Microsoft Copilots | Microsoft Learn

Security, especially data protection, is a top concern when introducing AI tools into an organization. Security recommendations for AI are anchored in Zero Trust. As a leader in security, Microsoft provides a practical roadmap and clear guidance for Zero Trust. By implementing recommended protections as you introduce AI tools and companions, you're building a foundation of Zero Trust security.

This series of articles helps you apply the [principles of Zero Trust](../zero-trust-overview) to Microsoft’s Copilots and similar AI companions. Zero Trust is a security strategy. It isn't a product or a service, but an approach in designing and implementing the following set of security principles:

- Verify explicitly
- Use least privileged access
- Assume breach

Implementing the Zero Trust "never trust, always verify" mindset requires changes to cloud infrastructure, deployment strategy, and implementation.

## Layer in protections for AI companions

Microsoft helps you prepare for AI tools and companions and build a Zero Trust foundation at the same time. Take a staged approach starting with protections for web-grounded prompts and maturing to protections for Microsoft 365 graph-grounded prompts. Protections for prompts grounded with data provided by your security tools (Security Copilot) focus on tuning up least privilege practices and honing threat protection.

[![Mapping of Copilots to web-grounded prompts, Microsoft 365-grounded prompts, and prompts grounded with security tools.](../media/copilot/microsoft-copilot-grounding.svg)](../media/copilot/microsoft-copilot-grounding.svg#lightbox)

In the illustration:

- Web-grounded prompts are issued by Copilot Chat. Microsoft Copilot includes the features of Copilot Chat (for example, when the work/web toggle is set to web).
- Microsoft 365 graph-grounded prompts are issued by Microsoft Copilot (for example, when the work/web toggle is set to work).
- Prompts grounded with your security tools are issued by Microsoft Security Copilot.

## Get started with Zero Trust by preparing your environment for AI companions

You can build a Zero Trust foundation by preparing your environment for AI companions.

[![Mapping of Zero Trust work to preparing for AI companions.](../media/copilot/use-zero-trust-to-prepare-for-ai.svg)](../media/copilot/use-zero-trust-to-prepare-for-ai.svg#lightbox)

The following table summarizes the illustration and links to articles for implementing the recommended protections.

| Prepare for | Protections | See these Zero Trust articles |
| --- | --- | --- |
| Web-grounded prompts | User accounts, devices, and some app data. | [Copilot Chat](zero-trust-microsoft-copilot) |
| Microsoft 365 graph-grounded prompts | Includes the previous protections plus more robust protection for app data and cloud apps. It also includes adding in threat protection. | [Microsoft Copilot](zero-trust-microsoft-365-copilot) |
| Prompts grounded with security tools | Focuses on tuning up least privilege access, a key principle of Zero Trust. | [Microsoft Security Copilot](zero-trust-microsoft-copilot-for-security) |

For more information on implementing Zero Trust, see the [Zero Trust Guidance Center](/en-us/security/zero-trust/).

## References

- [Microsoft Copilot Chat](/en-us/copilot/)
- [Microsoft Copilot](/en-us/microsoft-365-copilot/)
- [Data, Privacy, and Security for Microsoft Copilot](/en-us/microsoft-365-copilot/microsoft-365-copilot-privacy)