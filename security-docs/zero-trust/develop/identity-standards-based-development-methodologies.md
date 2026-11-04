---
layout: Conceptual
title: Standards-based development methodologies | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/develop/identity-standards-based-development-methodologies
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: Learn about the benefits of using supported standards in the Microsoft identity platform for Zero Trust development.
ms.subservice: zero-trust
ms.topic: concept-article
ms.service: security
ms.date: 2025-02-24T00:00:00.0000000Z
ms.custom: template-concept
ms.collection:
- zerotrust-dev
locale: en-us
document_id: 853395ac-947e-e94a-28c5-0449e3e942b6
document_version_independent_id: 853395ac-947e-e94a-28c5-0449e3e942b6
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/develop/identity-standards-based-development-methodologies.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/develop/identity-standards-based-development-methodologies
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/develop/identity-standards-based-development-methodologies.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/5f286262-a4cb-47f4-92d3-dc24f172492b
- https://authoring-docs-microsoft.poolparty.biz/devrel/1e31b9be-b6e9-4221-a20b-d1460dbd5dfa
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/90571f66-8410-4272-8117-79ce87fc2dcc
- https://authoring-docs-microsoft.poolparty.biz/devrel/8d63a4c4-4889-43b4-a98e-8e50dbfdb083
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
platformId: cf6e618d-3a97-4f79-affa-6d355e0d54fb
---

# Standards-based development methodologies | Microsoft Learn

As a developer, you can make good use of industry standards for software development augmented by the [Microsoft Authentication Library](/en-us/entra/identity-platform/msal-overview) (MSAL). In this article, we provide an overview of supported standards and their benefits in the [Microsoft identity platform](/en-us/entra/identity-platform/v2-overview). Ensure that your cloud applications meet Zero Trust requirements for optimal security.

## What about protocols?

When you implement protocols, consider costs that include time to write code that is fully up to date with all best practices and follows OAuth 2.0 best practices for secure implementation. Use a well-maintained library (with a preference for MSAL) when you build directly to Microsoft Entra ID or Microsoft Identity.

We optimize MSALs to build and work with Microsoft Entra ID. If your environment doesn't have MSAL or includes unlocked capabilities in its own library, develop your application with the Microsoft identity platform. Build on OAuth 2.0 capabilities and OpenID Connect. Consider costs of correctly falling back to a protocol.

## How the Microsoft identity platform supports standards

To achieve Zero Trust most efficiently and effectively, develop applications with industry standards that the Microsoft identity platform supports:

- [OAuth 2.0 and OpenID Connect](/en-us/entra/identity-platform/v2-protocols)
- [SAML](/en-us/entra/identity-platform/saml-protocol-reference)

### OAuth 2.0 and OpenID Connect

As the industry protocol for authorization, OAuth 2.0 allows users to grant limited access to protected resources. OAuth 2.0 works with Hypertext Transfer Protocol (HTTP) to separate the client role from the resource owner. Clients use tokens to access protected resources on a resource server.

OpenID Connect constructs allow Microsoft Entra extensions to enhance security. These Microsoft Entra extensions are the most common:

- [Conditional Access authentication context](/en-us/entra/identity-platform/developer-guide-conditional-access-authentication-context) allows apps to apply granular policies to protect sensitive data and actions instead of only at the app level.
- [Continuous Access Evaluation (CAE)](/en-us/entra/identity/conditional-access/concept-continuous-access-evaluation) enables Microsoft Entra applications to subscribe to critical events for evaluation and enforcement. CAE includes risky event evaluation such as disabled or deleted user accounts, password changes, token revocations, and detected users.

When your applications use enhanced security features like CAE and Conditional Access authentication context, they must include code to manage claims challenges. With open protocols, you use claims challenges and claims requests to invoke other client capabilities. For example, indicating to apps that they need to repeat interaction with Microsoft Entra ID due to an anomaly. Another scenario is when the user no longer satisfies conditions under which they had earlier authenticated. You can code for these extensions without disturbing primary authentication code flows.

### Security Assertions Markup Language (SAML)

The Microsoft identity platform uses SAML 2.0 to enable your Zero Trust applications to provide a single sign-on (SSO) user experience. SSO and Single Sign-Out SAML profiles in Microsoft Entra ID explain how the identity provider service uses SAML assertions, protocols, and bindings. The SAML protocol requires the identity provider (Microsoft identity platform) and the service provider (your application) to exchange information about themselves. When you register your Zero Trust application with Microsoft Entra ID, you register federation-related information that includes the Redirect URI and Metadata URI of the application with Microsoft Entra ID.

## Benefits of MSAL over protocols

Microsoft optimizes MSALs for the Microsoft identity platform and provides the best experience for SSO, token caching, and outage resilience. As MSALs are generally available, we continue to expand coverage of languages and frameworks.

Using MSAL, you acquire tokens for application types that include web applications, web APIs, single page apps, mobile and native applications, daemons, and server-side applications. MSAL enables fast and simple integration with secure access to users and data via Microsoft Graph and APIs. With best-in-class auth libs, you can reach any audience and follow the Microsoft Security Development Lifecycle.