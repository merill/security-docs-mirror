---
layout: Conceptual
title: Secure app identity with permissions and access | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/develop/identity
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: Learn how to authenticate users, authorize access, minimize permissions, protect APIs and tokens, and operate application identities by using Zero Trust principles.
ms.date: 2026-11-10T00:00:00.0000000Z
ai-usage: ai-assisted
ms.subservice: zero-trust
ms.topic: hub-page
ms.service: security
ms.collection:
- zerotrust-dev
locale: en-us
document_id: 96b969cd-5e6b-ccdb-e1ab-4b5d92390097
document_version_independent_id: 5ee81712-a589-f1d8-8f7e-7faedd9388e6
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/develop/identity.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/develop/identity
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/develop/identity.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: 7bb57b48-2931-f857-bc13-fd9e9a7fff0c
---

# Secure app identity with permissions and access | Microsoft Learn

Use this guide to build applications that authenticate identities, authorize access, minimize privilege, and protect APIs and tokens by using Zero Trust principles. It's for developers, application architects, identity professionals, and platform teams that design or govern application access.

Start with the task that matches your current decision. If you're designing a new application identity, use this sequence: **register -&gt; authenticate -&gt; authorize -&gt; minimize permissions -&gt; protect APIs and tokens -&gt; validate continuously**.

## Register and authenticate applications

Establish the application's identity boundary, supported account types, and authentication method.

- [Integrate applications with Microsoft Entra ID and the Microsoft identity platform](integrate-apps-microsoft-identity-platform) to build apps that IT professionals can secure in the enterprise.
- [Register applications](app-registration) by using least privilege and assume-breach principles.
- [Choose supported identity and account types](identity-supported-account-types) for single-tenant, multitenant, and personal Microsoft account scenarios.
- [Authenticate users for Zero Trust](user-authentication) by verifying explicitly and applying least privilege.

## Choose delegated or application permissions

Choose whether the application acts on behalf of a user or uses its own identity, then design authorization and consent accordingly.

- [Acquire authorization to access resources](acquire-application-authorization-to-access-resources).
- [Develop a delegated permissions strategy](developer-strategy-delegated-permission) for applications that act on behalf of a signed-in user.
- [Develop an application permissions strategy](developer-strategy-application-permissions) for services and background processes that act without a user.
- [Request permissions that require administrative consent](permissions-require-admin-consent).
- [Apply authorization best practices](developer-strategy-authorization-best-practices).
- [Coordinate developer and administrator responsibilities](identity-developer-administrator-responsibilities) for registration, authorization, and access.

## Reduce excessive privilege and protect workload identities

Limit access to what the application needs, and use managed identities where possible.

- [Reduce overprivileged permissions and apps](overprivileged-permissions).
- [Provide application identity credentials when there's no user](identity-non-user-applications) by using managed identities for Azure resources.

## Protect APIs and tokens

Treat tokens, API permissions, and downstream calls as part of the application's security boundary.

- [Manage tokens for Zero Trust](token-management).
- [Customize tokens](zero-trust-token-customization).
- [Configure group claims and app roles in tokens](configure-tokens-group-claims-app-roles).
- [Protect APIs](protect-api) through registration, permissions, consent, and access enforcement.
- [Review an API protected by the Microsoft identity consent framework](protected-api-example).
- [Call an API from another API](api-calls-api) when the application works on behalf of a user.

## Operate and validate continuously

Reevaluate access as risk, session context, application behavior, and organizational policy change.

- [Secure applications with Continuous Access Evaluation](secure-with-cae).
- [Understand Zero Trust compliance for applications](identity-zero-trust-compliance).
- Use [Zero Trust identity and access management development best practices](identity-iam-development-best-practices) throughout the software development lifecycle.
- Apply [standards-based development methodologies](identity-standards-based-development-methodologies).