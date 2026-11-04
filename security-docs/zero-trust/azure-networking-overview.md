---
layout: Conceptual
title: How do I apply Zero Trust principles to Azure networking? | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/azure-networking-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: duau
author: duongau
description: An overview of how to apply Zero Trust principles to Azure networking infrastructure.
ms.date: 2024-05-29T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.reviewer: adtork, maroja, maalgeba
ms.topic: overview
ms.collection:
- msftsolution-azureiaas
- msftsolution-scenario
- zerotrust-solution
- zerotrust-azure
locale: en-us
document_id: 02ca0121-1932-a950-fa1e-39c5e1714046
document_version_independent_id: 02ca0121-1932-a950-fa1e-39c5e1714046
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/azure-networking-overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/azure-networking-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/azure-networking-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
platformId: d23c4449-1827-ee73-5e75-71119d67b9b0
---

# How do I apply Zero Trust principles to Azure networking? | Microsoft Learn

This series of articles help you apply the [principles of Zero Trust](zero-trust-overview) to your networking infrastructure in Microsoft Azure based on a multi-disciplinary approach. Zero Trust is a security strategy. It isn't a product or a service, but an approach in designing and implementing the following set of security principles:

- Verify explicitly
- Use least privileged access
- Assume breach

Implementing the Zero Trust mindset to "assume breach, never trust, always verify" requires changes to cloud networking infrastructure, deployment strategy, and implementation.

The following articles show you how to apply Zero Trust approach to networking for commonly deployed Azure infrastructure services:

- [Encryption](azure-networking-encryption)
- [Segmentation](azure-networking-segmentation)
- [Gain visibility into your network traffic](azure-networking-visibility)
- [Discontinue legacy network security technology](azure-networking-legacy)

Important

This Zero Trust guidance describes how to use and configure several security solutions and features available on Azure for a reference architecture. Several other resources also provide security guidance for these solutions and features, including:

- [Microsoft Cloud Security Benchmark](/en-us/security/benchmark/azure/introduction)
- [Microsoft Cloud Security Baseline](/en-us/security/benchmark/azure/security-baselines-overview)

To describe how to apply a Zero Trust approach, this guidance targets a common pattern used in production by many organizations: a virtual-machine-based application hosted in a VNet (and IaaS application). This is a common pattern for organizations migrating on-premises applications to Azure, which is sometimes referred to as "lift-and-shift."

## Threat Protection with Microsoft Defender for Cloud

For the **Assume breach** Zero Trust principle for Azure networking, Microsoft Defender for Cloud is an extended detection and response (XDR) solution that automatically collects, correlates, and analyzes signal, threat, and alert data from across your environment. Defender for Cloud is intended to be used together with Microsoft Defender XDR to provide a greater breadth of correlated protection of your environment, as shown in the following diagram.

[![Diagram of the logical architecture of Microsoft Defender for Cloud and Microsoft Defender XDR that provides threat protection for Azure networking.](media/azure-infra-overview/azure-infra-overview-threat-protection.svg)](media/azure-infra-overview/azure-infra-overview-threat-protection.svg#lightbox)

In the diagram:

- Defender for Cloud is enabled for a management group that includes multiple Azure subscriptions.
- Microsoft Defender XDR is enabled for Microsoft 365 apps and data, SaaS apps that are integrated with Microsoft Entra ID, and on-premises Active Directory Domain Services (AD DS) servers.

For more information about configuring management groups and enabling Defender for Cloud, see:

- [Organize subscriptions into management groups and assign roles to users](/en-us/azure/defender-for-cloud/management-groups-roles)
- [Enable Defender for Cloud on all subscriptions in a management group](/en-us/azure/defender-for-cloud/onboard-management-group)