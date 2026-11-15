---
layout: Conceptual
title: Securing privileged access overview - Privileged access | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/privileged-access-workstations/overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: None
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: How can organizations secure privileged with Azure resources?
ms.service: security
ms.subservice: privileged-access
ms.topic: overview
ms.date: 2026-11-10T00:00:00.0000000Z
ai-usage: ai-assisted
ms.reviewer: mas
locale: en-us
document_id: bd336460-7f23-85de-3b43-85d8fda09431
document_version_independent_id: bd336460-7f23-85de-3b43-85d8fda09431
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/privileged-access-workstations/overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: privileged-access-workstations/overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/privileged-access-workstations/overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: 3c67ba0d-d641-8801-fc5b-f01abaccee53
---

# Securing privileged access overview - Privileged access | Microsoft Learn

Organizations should make securing privileged access the top security priority because of the significant potential business impact, and high likelihood, of attackers compromising this level of access.

Privileged access includes IT administrators with control of large portions of the enterprise estate and other users with access to business-critical assets.

Attackers frequently exploit weaknesses in privileged access security during [human-operated ransomware attacks](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/) and targeted data theft. Privileged access accounts and workstations are so attractive to attackers because these targets allow them to rapidly gain broad access to the business assets in the enterprise, often resulting in rapid and significant business impact.

The following diagram summarizes the recommended privileged access strategy to create an isolated virtual zone that these sensitive accounts can operate in with low risk.

![An end to end approach is required for meaningful security](media/overview/end-to-end-approach.png)

Securing privileged access effectively seals off unauthorized pathways completely and leaves a select few authorized access pathways that are protected and closely monitored. This diagram is discussed in more detail in the article, [Privileged Access Strategy](privileged-access-strategy).

Building this strategy requires a holistic approach combining multiple technologies to protect and monitor those authorized escalation paths using Zero Trust principles including explicit validation, least privilege, and assume breach. This strategy requires multiple complementary initiatives that establish a holistic technology approach, clear processes, and rigorous operational execution to build and sustain assurances over time.

Connect this privileged-access guidance to the current Microsoft Security Adoption Framework (SAF): [establish an Access and Identities discipline](../zero-trust/security-adoption-discipline-identity-access), [build a privileged-access architecture strategy](../zero-trust/security-adoption-discipline-identity-access-privileged-strategy), and [review the current privileged-access architecture model](../zero-trust/security-adoption-discipline-identity-access-privileged-model).

## Get started and measure progress

| Image | Description | Image | Description |
| --- | --- | --- | --- |
| ![Rapid Modernization Plan](media/overview/ramp.png) | [Rapid Modernization Plan (RaMP)](security-rapid-modernization-plan) - Plan and implement the most impactful quick wins | ![Best practices checklist](media/overview/checklist.png) | [Best practices](/en-us/security/compass/critical-impact-accounts)[Videos and Slides](/en-us/security/compass/administration-videos-and-decks) |

## Industry references

Securing privileged access is also addressed by these industry standards and best practices.

| [UK National Cyber Security Center (NCSC)](https://www.ncsc.gov.uk/collection/secure-system-administration) | [Australian Cyber Security Center (ACSC)](https://www.cyber.gov.au/acsc/view-all-content/publications/secure-administration) | [MITRE ATT&CK](https://attack.mitre.org/mitigations/M1026/) |
| --- | --- | --- |