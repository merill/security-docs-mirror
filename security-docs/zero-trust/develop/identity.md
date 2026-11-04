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
description: Learn about authentication, authorization, and identity management with a Zero Trust approach to identity in your software development lifecycle (SDLC).
ms.date: 2025-02-24T00:00:00.0000000Z
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
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
- https://authoring-docs-microsoft.poolparty.biz/devrel/a3955c7b-f5ee-420d-aff5-d7119738f38b
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
- https://authoring-docs-microsoft.poolparty.biz/devrel/b31948f4-2f38-404b-ac93-c3c8c5b3ae33
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
platformId: 7bb57b48-2931-f857-bc13-fd9e9a7fff0c
---

# Secure app identity with permissions and access | Microsoft Learn

This article continues from the [Zero Trust identity and access management development best practices](identity-iam-development-best-practices) article to help you use a Zero Trust approach to identity in your software development lifecycle (SDLC).

Here's an overview of the **Permissions and access** articles in this [Developer Guide](overview) so that you can dive into identity components that include authentication, authorization, and identity management.

- [Integrate applications with Microsoft Entra ID and the Microsoft identity platform](integrate-apps-microsoft-identity-platform) helps developers to build and integrate apps that IT pros can secure in the enterprise.
- [Register applications](app-registration) introduces developers to the application registration process and its requirements. It helps them to ensure that apps satisfy Zero Trust principles of use least privileged access and assume breach.
- [Supported identity and account types for single- and multitenant apps](identity-supported-account-types) explains how you can choose if your app allows only users from your Microsoft Entra tenant, any Microsoft Entra tenant, or users with personal Microsoft accounts.
- [Authenticate users for Zero Trust](user-authentication) helps developers to learn best practices for authenticating application users in Zero Trust application development. It describes how to enhance application security with the Zero Trust principles of least privilege and verify explicitly.
- [Acquire authorization to access resources](acquire-application-authorization-to-access-resources) helps you to understand how to best ensure Zero Trust when acquiring resource access permissions for your application.
- [Develop delegated permissions strategy](developer-strategy-delegated-permission) helps you to implement the best approach for managing permissions in your application and develop with Zero Trust principles.
- [Develop application permissions strategy](developer-strategy-application-permissions) helps you to decide upon your application permissions approach to credential management.
- [Request permissions that require administrative consent](permissions-require-admin-consent) describes the permission and consent experience when application permissions require administrative consent.
- [Reduce overprivileged permissions and apps](overprivileged-permissions) helps you to understand why applications shouldn't request more permissions than they need (overprivileged). Learn how to limit privilege to manage access and improve security.
- [Provide application identity credentials when there's no user](identity-non-user-applications) explains Managed Identities for Azure resources best practices for services (nonuser applications).
- [Manage tokens for Zero Trust](token-management) helps developers to build security into applications with ID tokens, access tokens, and security tokens that they can receive from the Microsoft identity platform.
- [Customize tokens](zero-trust-token-customization) describes the information that you can receive in Microsoft Entra tokens and how you can customize tokens.
- [Secure applications with Continuous Access Evaluation](secure-with-cae) helps developers to improve application security with Continuous Access Evaluation. Learn how to [ensure Zero Trust support](overview) in your apps that receive authorization to access resources when they acquire access tokens from Microsoft Entra ID.
- [Configure group claims and app roles in tokens](configure-tokens-group-claims-app-roles) shows you how to configure your apps with app role definitions and assign security groups.
- [API Protection](protect-api) describes best practices for protecting your API through registration, defining permissions and consent, and enforcing access to achieve your Zero Trust goals.
- [Example of API protected by Microsoft identity consent framework](protected-api-example) helps you to design least privilege application permissions strategies for the best user experience.
- [Call an API from another API](api-calls-api) helps you to ensure Zero Trust when you have one API that needs to call another API. Learn how to securely develop your application when it's working on behalf of a user.
- [Authorization best practices](developer-strategy-authorization-best-practices) helps you to implement the best authorization, permission, and consent models for your applications.