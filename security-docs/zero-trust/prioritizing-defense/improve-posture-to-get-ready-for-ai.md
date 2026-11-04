---
layout: Conceptual
title: Microsoft Security Exposure Management for AI | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/prioritizing-defense/improve-posture-to-get-ready-for-ai
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn how security practitioners can improve security posture for AI readiness by managing devices, reducing exposure, and securing software.
ms.date: 2026-10-23T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
ms.custom: msecd-doc-authoring-1028
ai-usage: ai-assisted
locale: en-us
document_id: 996e97b9-a8b4-cbeb-2a53-9e5b0764dcc6
document_version_independent_id: 996e97b9-a8b4-cbeb-2a53-9e5b0764dcc6
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/prioritizing-defense/improve-posture-to-get-ready-for-ai.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/prioritizing-defense/improve-posture-to-get-ready-for-ai
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/prioritizing-defense/improve-posture-to-get-ready-for-ai.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e9e4163d-5abc-4b31-8602-bd8826f5d740
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/062d60c9-ee0f-402e-a046-b4e67c3572d6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/a72e95ff-4b4f-4cc1-90c6-7dcba67ff05f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/a225912b-c498-48b4-a85f-d3e64981cbdc
- https://authoring-docs-microsoft.poolparty.biz/devrel/17d3b3f6-a66e-4c69-9774-14a73c38e669
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/24dc3ccd-591a-4415-a1fe-8759afafcb12
platformId: 9468f777-9d7a-e6c6-ecd3-0912a652c45d
---

# Microsoft Security Exposure Management for AI | Microsoft Learn

**Security imperative: Get ready for AI** **Job to be done: Improve posture**

Improving posture to get ready for AI focuses on establishing a defensible device baseline, cutting reachable attack surface, and closing gaps across the software estate. It ensures effort lands where it reduces risk, and that controls an AI agent inherits are already governed.

### Context and problem

AI gives attackers new tools to discover, analyze, and chain vulnerabilities faster, letting them probe more paths and move through environments more quickly. Yet most of the weaknesses they exploit are familiar: unmanaged devices, devices that don't meet compliance requirements, work data that leaves managed apps, unnecessary internet-facing exposure, unpatched software, vulnerable open-source dependencies, and flaws in the code organizations write.

What's changed is how quickly attackers can link those gaps into a path to critical systems, so one weak spot can lead to a much broader compromise. AI adoption raises the stakes, because AI agents can inherit the posture they're deployed into: the devices they run on, the services they can reach, and the software they depend on. That makes basic security hygiene urgent: organizations need a strong security foundation in place before they adopt AI, and they need to keep it strong as threats evolve.

## Solution

To help your organization establish a strong security foundation, we have guidance outlined in [Secure Now](https://aka.ms/SecureNow), within [Microsoft Security Exposure Management](/en-us/security-exposure-management/microsoft-security-exposure-management). These initiatives closes one of those familiar gaps:

- Manage organizational devices brings devices under management in Microsoft Intune.
- Implement device compliance requirements holds them to a standard enforced through Conditional Access.
- Protect organizational data in managed applications keeps work data in managed apps, even on devices you don't manage.
- Internet-Facing Exposure cuts what's reachable from the internet and protects the services that must stay exposed.
- Patching and vulnerability management keeps software and operating systems current.
- Software Supply Chain Security secures the open-source dependencies and pipelines you build on.
- Code scanning and remediation finds and fixes vulnerabilities in the code you write.

Together, they help you improve posture to get ready for AI transformation. Secure Now is updated as threats and Microsoft security capabilities evolve, so check it for the latest recommended actions and use [security initiatives](/en-us/security-exposure-management/initiatives) to track progress against your targets.

## Guidance

Security practitioners can improve posture in their organizations by following these initiatives informed by Secure Now. Learn more about how to [prioritize strengthening AI-readiness.](prioritizing-defense-overview)

| **Initiatives** | **Resource** |
| --- | --- |
| Manage organizational devices | [Secure Now - Manage organizational devices](https://sip.security.microsoft.com/secure-now) |
| Implement device compliance requirements | [Secure Now - Implement device compliance requirements](https://sip.security.microsoft.com/secure-now) |
| Protect organizational data in managed applications | [Secure Now - Protect organizational data in managed applications](https://sip.security.microsoft.com/secure-now) |
| Internet-Facing Exposure | [Secure Now - Internet-Facing Exposure](https://sip.security.microsoft.com/secure-now) |
| Patching and vulnerability management | [Secure Now - Patching and vulnerability management](https://sip.security.microsoft.com/secure-now) |
| Software Supply Chain Security | [Secure Now - Software Supply Chain Security](https://sip.security.microsoft.com/secure-now) |
| Code scanning and remediation | [Secure Now - Code scanning and remediation](https://sip.security.microsoft.com/secure-now) |

## Outcomes

- Devices meets a known standard: managed, compliant devices share one security configuration, and helps protect organizational data in managed apps, even on devices you don’t manage.
- Effort lands where it reduces risk: internet exposure and attack paths to critical assets set the order of work, not severity score alone.
- Address underlying sources of findings: each step removes a class of finding—an unmanaged device, an exposed endpoint, an outdated component, a leaked secret—rather than one instance at a time.
- AI agents inherit governed foundations: managed devices, a measured external footprint, and a current, scanned software estate are in place before agents arrive, rather than bolted on after.

## Key success factors

Consider tracking the following indicators with the tools and reporting your organization already uses, and compare results over time against your own baseline:

- Percentage of critical assets with a named accountable owner
- Percentage of corporate devices enrolled in Microsoft Intune and compliant with policy
- Percentage of Microsoft 365 app users covered by app protection policies, including on devices you don’t manage
- Number of attack paths from internet-facing assets to a critical asset, trending down
- Patch compliance against service level agreement, reported by internet exposure and asset criticality
- Percentage of production builds that automatically produce a software bill of materials
- Initiative score against target score, with the 14-day drift for each domain

## Summary

The initiatives with recommended actions can help measurably reduce risk. Create a strong foundation, cut the exposed surface, patch what you buy, patch what you borrow, and secure what you build.

**By prioritizing posture initiatives, you can reduce your organization’s exposure before AI agents inherit it.**