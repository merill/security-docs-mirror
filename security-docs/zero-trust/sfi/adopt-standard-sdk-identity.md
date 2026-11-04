---
layout: Conceptual
title: Adopt standard SDKs for identity | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/adopt-standard-sdk-identity
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Adopt standard SDKs for identity is part of the Protect identities and secrets pillar of the Secure Future Initiative (SFI), which focuses on hardening authentication, eliminating unmanaged credentials, enforcing Zero Trust principles, and protecting cryptographic keys. It ensures identity is verifiable, access is auditable, and secrets are defended with rigor across the digital estate.
ms.date: 2025-11-06T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: design-pattern
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
locale: en-us
document_id: 463b1fc4-d1a5-ff11-5fa6-5c4468ef4f6d
document_version_independent_id: 463b1fc4-d1a5-ff11-5fa6-5c4468ef4f6d
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/adopt-standard-sdk-identity.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/adopt-standard-sdk-identity
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/adopt-standard-sdk-identity.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/5f286262-a4cb-47f4-92d3-dc24f172492b
- https://authoring-docs-microsoft.poolparty.biz/devrel/1e31b9be-b6e9-4221-a20b-d1460dbd5dfa
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/90571f66-8410-4272-8117-79ce87fc2dcc
- https://authoring-docs-microsoft.poolparty.biz/devrel/8d63a4c4-4889-43b4-a98e-8e50dbfdb083
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 53d4fd21-1a20-2eab-31d2-40cbaf9054fa
---

# Adopt standard SDKs for identity | Microsoft Learn

**Pillar name: Protect identities and secrets** **Pattern name: Adopt standard SDKs for identity**

The “Adopt standard SDKs for identity” pattern is part of the protect identities and secrets pillar of the Secure Future Initiative (SFI), which focuses on hardening authentication, eliminating unmanaged credentials, enforcing Zero Trust principles, and protecting cryptographic keys. It ensures identity is verifiable, access is auditable, and secrets are defended with rigor across the digital estate.

## Context and problem

In 2023, the Storm-0558 incident exposed inconsistencies in Microsoft’s identity infrastructure: varied approaches to token validation across services created vulnerabilities to identity-based attacks, causing authentication problems for customers and giving attackers unauthorized access to protected resources like email accounts. Different teams implemented authentication logic independently, often relying on custom code or outdated libraries that created vulnerabilities.

This fragmentation created exploitable seams in enforcement—where slightly different interpretations of identity claims or token validation could allow malicious access to sensitive systems. Even minor variations in token signature handling or scope enforcement were enough to allow forged tokens to slip past security controls.

## Solution

To address this, Microsoft introduced a new objective under the Protect identities and secrets pillar of the Secure Future Initiative: adopt a single, standardized identity SDK for token validation.

This SDK consolidates identity enforcement logic into one security-hardened, well-maintained library.

**Key features include:**

- Consistent validation of token claims, scopes, signatures, and issuers
- Resilient handling of signing keys and decrypt keys metadata
- Built-in telemetry for security monitoring and audit readiness
- Support for technologies like Continuous Access Evaluation (CAE) that implement the Zero Trust principle of explicitly validating all access requests
- Secure defaults that simplify developer implementation

Microsoft’s internal token validation SDK is used across major Microsoft development platforms and is integrated with Microsoft Entra, ensuring consistency at scale.

Since rolling out this pattern, Microsoft has replaced decentralized authentication logic across services with SDK-based validation. The centralized SDK provides a uniform method for verifying identity and enforcing policy—closing dangerous inconsistencies and enabling Microsoft to respond faster to token-based threats. 

By April 2025, 90% of identity tokens issued by Microsoft Entra ID for Microsoft applications were being validated using the standard SDK—up from 73% just six months earlier.

## Guidance

Organizations can adopt a similar pattern using the following actionable practices:

| **Use case** | **Recommended action** | **Resource** |
| --- | --- | --- |
| **Consistent authentication** | - Use Microsoft Authentication Library (MSAL) to simplify and standardize authentication flows across applications.<br>- For services on .NET use Microsoft.Identity.Web that wraps MSAL. | - [Learn about MSAL | Microsoft Learn](/en-us/entra/msal/overview)<br>- [Microsoft Identity Web authentication library | Microsoft Learn](/en-us/entra/msal/dotnet/microsoft-identity-web) |
| **Token management** | Adopt SDK features that securely acquire, cache, and refresh tokens, instead of building custom token handling logic. | [Acquiring and using an access token - Microsoft Authentication Library for JavaScript | Microsoft Learn](/en-us/entra/msal/javascript/browser/acquire-token) |
| **Security best practices** | Apply built-in SDK features like secure defaults, token validation, and certificate handling to reduce misconfigurations. | [Secure applications and APIs by validating claims | Microsoft Learn](/en-us/entra/identity-platform/claims-validation) |
| **Integration with the Microsoft identity platform** | Use SDKs to connect applications with Microsoft Entra ID, enabling modern authentication protocols such as OAuth 2.0 and OpenID Connect. | [Microsoft identity platform overview | Azure Docs](/en-us/entra/identity-platform/v2-overview) |

## Benefits

- Improved security posture by eliminating fragmented token validation.
- Faster incident response with centralized logging and policy enforcement.
- Reduced technical debt through managed SDK versioning and secure defaults.
- Better developer experience via simplified authentication libraries.
- Improved auditability and consistent enforcement of access policies.

## Trade-offs

- **Refactoring required:** Legacy systems had to be updated or rebuilt to use the SDK.
- **Developer training:** Teams had to learn new identity libraries and workflows.
- **Governance complexity:** Versioning and rollout of the SDK required oversight and coordination.

## Key success factors

To track success, measure the following:

- Percentage of applications using the standard SDK for token validation
- Mean time to detect and respond to token misuse
- Reduction in token-related vulnerabilities or incidents
- Number of audit exceptions tied to nonstandard identity implementations
- Developer adoption and support satisfaction with the SDK

## Summary

Token validation is a foundational control in identity security. Variations in how it's implemented across services can introduce unseen risks, delay incident response, and erode trust in security controls. By adopting a single, secure SDK for identity token validation, Microsoft closed critical gaps, standardized enforcement, and created a stronger foundation for Zero Trust operations.

**By adopting standard SDKs for identity, you can help eliminate fragmented authentication logic and strengthen the integrity of your organization’s identity security.**