---
layout: Conceptual
title: Secure applications with Continuous Access Evaluation | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/develop/secure-with-cae
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: Learn how to improve application security with Continuous Access Evaluation and acquire access tokens from Microsoft Entra ID.
ms.date: 2025-02-24T00:00:00.0000000Z
ms.subservice: zero-trust
ms.topic: concept-article
ms.service: security
ms.custom: template-concept
ms.collection:
- zerotrust-dev
locale: en-us
document_id: e01b09bc-4fa7-cea1-f2d1-f93648b754b0
document_version_independent_id: e01b09bc-4fa7-cea1-f2d1-f93648b754b0
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/develop/secure-with-cae.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/develop/secure-with-cae
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/develop/secure-with-cae.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
platformId: cb083206-638a-bf0a-dca9-0c9874b42c2d
---

# Secure applications with Continuous Access Evaluation | Microsoft Learn

This article helps you, as a developer, to improve application security with Continuous Access Evaluation. You learn how to [ensure Zero Trust support](overview) in your apps that receive [authorization to access resources](acquire-application-authorization-to-access-resources) when they acquire access tokens from Microsoft Entra ID.

When Microsoft Entra ID issues these access tokens, it fully evaluates the [conditions for that authorization](/en-us/entra/identity/conditional-access/overview). Microsoft Entra ID performs standard authorization actions, such as [ensuring consent](identity), every time it issues tokens for initial token requests and when it refreshes tokens.

Microsoft Entra ID primarily uses JSON Web Tokens (JWT) for access tokens. A resource API can decode, validate, and interpret the JWT without needing to call back to Microsoft Entra ID on every call to the resource API. The [JWT standard](https://www.rfc-editor.org/rfc/rfc7519) defines an exp claim that identifies the *on-or-after* expiration time that you must not accept the JWT token for processing. By default, Microsoft Entra tokens expire 60 to 90 minutes after issue. Ensure that your applications cache and use access tokens for the period during which Microsoft Entra ID doesn't evaluate authorization conditions.

## Evaluate conditions outside of issuing the token

Lags can occur between user condition changes and policy change enforcement when Microsoft Entra ID issues tokens. A reduced token lifetime approach can degrade user experiences and reliability without eliminating risks.

One solution is to evaluate conditions on every call to a protected resource. The most common way to implement this enforcement is token introspection. Token introspection doesn't use a JWT format for the token. Instead, token introspection uses an opaque string that the resource API can't interpret. The resource API sends the token to the identity provider on each call. The identity provider then checks for any conditions and returns data that the resource API can use to complete the operation. This process can be expensive as it adds another round trip web request to every API call.

To remedy this expense with [Continuous Access Evaluation](/en-us/entra/identity/conditional-access/concept-continuous-access-evaluation) (CAE), a resource API can listen for events that Microsoft Entra ID pushes about the tokens that Microsoft Entra ID issues for the resource API. For example, when your application calls the Microsoft Graph API, Microsoft Graph can check if it received events from Microsoft Entra ID about the token. If the conditions of the original authentication are different and the user needs to reauthenticate, Microsoft Graph returns an error to the calling app.

Microsoft Entra ID sends an event to CAE-enabled Microsoft resources when any of these events occur:

- Disabled or deleted user account
- Changed or reset user password
- Enabled user multifactor authentication
- Administrator explicitly revokes all refresh tokens for a user
- Microsoft Entra ID Protection detects elevated user risk

In addition, CAE-enabled Microsoft resources can enforce location-based conditional access policies.

## Improve application security and resilience with CAE

The following [More secure and resilient apps built on Microsoft Entra Continuous Access Evaluation](https://www.youtube.com/watch?v=Yc9b7L3srrE) video demonstrates building a client app with CAE support.

The video presentation describes how applications work with modern authentication and these steps:

1. App asks Microsoft identity for tokens
2. App receives an access token
3. App calls API / Authorization with JWT
4. Introspection
5. Shared signals and events
6. Critical event evaluation
7. Conditional Access policy evaluation
8. Called API Continuous Access Evaluation
9. Claims challenge

Continuous Access Evaluation enables an application's authorization to access a resource revoked outside the lifetime of the access token. For example, an application has a token that is valid for 75 more minutes. A user has a high-risk state due to breached credentials. CAE blocks the app's access to the resource, requiring the user to reauthenticate before continuing. Thus, CAE achieves its primary goal to improve app security.

As access to a resource can be revoked outside a token's lifetime, Microsoft Entra ID can issue tokens for a longer lifetime. For apps that support CAE, Microsoft Entra ID can issue tokens that are valid for up to 28 hours. Although this longer token lifetime doesn't improve the app's resilience, it reduces application costs as the app needs to request tokens much less frequently.

CAE improves an app's resilience to issues that the app could encounter in acquiring an access token from Microsoft Entra ID. Whenever possible, Microsoft Entra ID issues a refresh time as part of a token response that contains an access token. Microsoft Authentication Libraries (MSAL) use this refresh time to proactively refresh the token. The refresh time is some fraction (usually half) of the token's expiration time. As long as MSAL can refresh the access token before the token's expiration time, the app is resilient to token refresh problems.

For example, when an app supports CAE, Microsoft Entra ID issues a token that authorizes the app to call Microsoft Graph that is valid for 24 hours. Microsoft Entra ID then tells MSAL to proactively refresh the token after 12 hours. If MSAL attempts to refresh the access token fail because the original access token is still valid for 12 more hours, the app is more resilient to problems when it acquires tokens from Microsoft Entra ID.

## Implement Continuous Access Evaluation in your app

As described in [How to use Continuous Access Evaluation enabled APIs in your applications](/en-us/entra/identity-platform/app-resilience-continuous-access-evaluation?tabs=dotnet), both your app and the resource API it's accessing must be CAE-enabled. However, preparing your code to use a CAE-enabled resource doesn't prevent you from using APIs that aren't CAE-enabled. Applications that don't use MSAL can add support for [claims challenges, claims requests, and client capabilities](/en-us/entra/identity-platform/claims-challenge?tabs=dotnet) to use CAE.