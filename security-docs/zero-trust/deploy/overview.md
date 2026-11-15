---
layout: Conceptual
title: Technologies in the Security Adoption Framework | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/deploy/overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Learn how the Security Adoption Framework organizes security guidance across identity, endpoints, applications, data, infrastructure, network, and AI technologies.
ms.date: 2026-11-09T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 241412a7-aa89-5648-2860-4aa3e8e4c204
document_version_independent_id: a90de4a9-78c1-45d8-e77a-67035ace1b0d
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/deploy/overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/deploy/overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/deploy/overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: bad8ce03-c2e9-cf81-62cf-63c97c6bb30a
---

# Technologies in the Security Adoption Framework | Microsoft Learn

Organizations must protect different types of technology assets with controls appropriate to the nature of each technology, including identity, endpoints, applications, data, infrastructure, network, and AI.

Each technology presents different security requirements, risks, and implementation considerations. Security disciplines apply security practices across these technologies, and technical solutions implement controls and capabilities across one or more of them.

Zero Trust principles apply across all of these technology areas. Rather than organizing guidance around individual products or features, the [Security Adoption Framework](../security-adoption-model) uses technologies as durable areas for understanding and applying security guidance.

![Diagram showing elements of visibility, automation, and orchestration in Zero Trust.](../media/diagram-zero-trust-security-elements.png)

## Technologies in SAF

These areas are represented as technologies in the Microsoft Security Adoption Framework (SAF) and are also used as pillars in the [Zero Trust Workshop](../workshop-zero-trust-overview).

SAF connects four complementary components:

- [Business scenarios](../security-adoption-business-scenarios-overview) define desired security outcomes based on business priorities and risk.
- [Security disciplines](../security-adoption-discipline-overview) describe the security work needed to manage risk, make decisions, and improve security capabilities.
- **Technologies** identify areas of the environment that must be protected, including identity, endpoints, applications, data, infrastructure, network, and AI.
- [Technical solutions](../implement-overview) provide implementation guidance for security requirements and capabilities that often span multiple technologies.

These components work together rather than forming a sequential process. A business scenario can require work across multiple security disciplines and technologies, while a technical solution can implement security requirements across several technology areas.

Zero Trust principles apply across this model, from business and security decisions through architecture, technology, implementation, and operations.

## Technologies

| Technology | Description |
| --- | --- |
| [![Fingerprint icon](../media/icon-identity-small.png)](identity)[Identity](identity) | Protect identities and access. Verify identities, manage privileges, and make access decisions based on appropriate context and risk. |
| [![Endpoints icon](../media/icon-endpoints-small.png)](endpoints)[Endpoints](endpoints) | Protect devices that access organizational resources. Assess device state and risk and apply appropriate configuration, protection, and access controls. |
| [![Ones and zeroes icon](../media/icon-data-small.png)](data)[Data](data) | Protect data throughout its lifecycle using capabilities such as classification, access control, encryption, and monitoring. |
| [![Application window icon](../media/icon-applications-small.png)](applications)[Applications](applications) | Protect applications, services, and APIs and the identities, permissions, sessions, and data they use. |
| [![Data storage disks icon](../media/icon-infrastructure-small.png)](infrastructure)[Infrastructure](infrastructure) | Protect compute, platforms, and supporting infrastructure through secure configuration, access control, protection, and monitoring. |
| [![Network diagram icon](../media/icon-networks-small.png)](networks)[Network](networks) | Protect connectivity and communications using controls such as segmentation, traffic inspection, secure access, and monitoring. |
| [![AI diagram icon](../media/icon-ai-small.png)](/en-us/security/saf/technologies/ai/overview)[AI](/en-us/security/saf/technologies/ai/overview) | Protect AI applications, agents, models, data, prompts, context, and tool integrations. Apply appropriate security controls across identity, data, applications, infrastructure, and network technologies. |

## How Zero Trust workshop pillars map to SAF

The [Zero Trust Workshop](../workshop-zero-trust-overview) uses **pillars** as its organizing concept for planning and implementation. Most workshop pillars correspond to technologies in SAF, including identity, endpoints, applications, data, infrastructure, network, and AI.

Two workshop pillars map differently in SAF:

- **SecOps** maps to the SAF [SecOps](../security-adoption-discipline-security-operations) security discipline.
- **DevSecOps/Development Security** maps to the SAF [Development Security](../security-adoption-discipline-development) security discipline.

This approach allows the Zero Trust Workshop to retain its familiar pillar-based structure while SAF distinguishes between technologies that must be protected and the security disciplines that perform security work across them.

## Zero Trust implementation workshops

The [Zero Trust Workshop](../workshop-zero-trust-overview) provides practical guidance for applying Zero Trust principles across these areas.

## What's next?

- Review [Technical solutions](../implement-overview) for guidance on implementing security requirements and capabilities.
- Learn about the [Security Adoption Framework](../security-adoption-model) and how its components work together.
- Review [business scenarios](../security-adoption-business-scenarios-overview) to connect security improvements to business priorities and risk.