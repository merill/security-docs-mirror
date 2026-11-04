---
layout: Conceptual
title: What do we mean by Zero Trust compliance? | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/develop/identity-zero-trust-compliance
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: Get an overview of application security from a developer's perspective to address the guiding principles of Zero Trust.
ms.subservice: zero-trust
ms.topic: concept-article
ms.service: security
ms.date: 2025-02-24T00:00:00.0000000Z
ms.custom: template-concept
ms.collection:
- zerotrust-dev
locale: en-us
document_id: dc1bc1e4-8915-8f98-6d16-4c8b91c5336b
document_version_independent_id: dc1bc1e4-8915-8f98-6d16-4c8b91c5336b
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/develop/identity-zero-trust-compliance.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/develop/identity-zero-trust-compliance
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/develop/identity-zero-trust-compliance.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/a3955c7b-f5ee-420d-aff5-d7119738f38b
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/b31948f4-2f38-404b-ac93-c3c8c5b3ae33
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
platformId: bb18dbab-d55e-cc3e-5514-fcb6970261e0
---

# What do we mean by Zero Trust compliance? | Microsoft Learn

This article provides overview of application security from a developer's perspective to address the guiding principles of [Zero Trust](overview). In the past, code security was all about your own app: if you got it wrong, your own app was at risk. Today, cybersecurity is a high priority for customers and governments worldwide.

Compliance with cybersecurity requirements is a prerequisite for many customers and governments to purchase applications. Your application needs to meet customer requirements.

Cloud security is a consideration of organization infrastructure that is only as secure as the weakest link. When a single app is the weakest link, bad actors can gain access to business-critical data and operations.

Application security from a developer perspective includes a Zero Trust approach: applications address the guiding principles of Zero Trust. As a developer, continuously update your application as the threat landscape and security guidance changes.

## Support Zero Trust principles in your code

Two keys to compliance with Zero Trust principles are the ability of your application to verify explicitly and to support least privilege access. Your application should [delegate identity and access management](identity-iam-development-best-practices) to Microsoft Entra ID so that it can use Microsoft Entra tokens. Delegating identity and access management enables your application to support customer technologies such as multifactor authentication, passwordless authentication, and conditional access policies.

With the [Microsoft identity platform](/en-us/entra/identity-platform/v2-overview) and Zero Trust enabling technologies, using Microsoft Entra tokens helps your application to integrate with Microsoft's entire suite of security technologies.

If your application requires passwords, you might be exposing your customers to avoidable risk. Bad actors view the shift to working from any location with any device as an opportunity to access corporate data by perpetrating activities such as password spray attacks. In a password spray attack, bad actors try a promising password across a set of user accounts. For example, they might try `GoSeaHawks2022!` against user accounts in the Seattle area. This successful attack type is one justification for passwordless authentication.

## Acquire access tokens from Microsoft Entra ID

At a minimum, your application needs to [acquire access tokens](acquire-application-authorization-to-access-resources) from Microsoft Entra ID that issues OAuth 2.0 access tokens. Your client application can use these tokens to obtain limited access to user resources via API calls on the user's behalf. You use an access token to call each API.

When a delegated identity provider verifies identity, your customer's IT department can enforce least privilege access with Microsoft Entra permission and consent. Microsoft Entra ID determines when it issues tokens to applications.

When your customers understand which corporate resources your application needs to access, they can correctly grant or deny access requests. For example, if your application needs to access Microsoft SharePoint, document this requirement so that you can help customers grant the correct permissions.