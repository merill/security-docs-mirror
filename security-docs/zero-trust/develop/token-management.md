---
layout: Conceptual
title: Manage tokens for Zero Trust | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/develop/token-management
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: Learn how to build security into applications with ID tokens, access tokens, and security tokens from the Microsoft identity platform.
ms.subservice: zero-trust
ms.topic: best-practice
ms.date: 2025-02-24T00:00:00.0000000Z
ms.custom: template-concept
ms.service: security
ms.collection:
- zerotrust-dev
locale: en-us
document_id: 29529eb8-439b-6ba9-ff6f-dddefd697b73
document_version_independent_id: 29529eb8-439b-6ba9-ff6f-dddefd697b73
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/develop/token-management.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/develop/token-management
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/develop/token-management.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
- https://authoring-docs-microsoft.poolparty.biz/devrel/5f286262-a4cb-47f4-92d3-dc24f172492b
- https://authoring-docs-microsoft.poolparty.biz/devrel/1e31b9be-b6e9-4221-a20b-d1460dbd5dfa
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
- https://authoring-docs-microsoft.poolparty.biz/devrel/90571f66-8410-4272-8117-79ce87fc2dcc
- https://authoring-docs-microsoft.poolparty.biz/devrel/8d63a4c4-4889-43b4-a98e-8e50dbfdb083
platformId: 07808fec-dbc3-89a1-0b8d-4223cf0750ca
---

# Manage tokens for Zero Trust | Microsoft Learn

In [Zero Trust application development](overview), it's important to specifically define your application's intention and its resource access requirements. Your app should request only the access it requires to function as intended. This article helps you, as a developer, to build security into your applications with [ID tokens](/en-us/entra/identity-platform/id-tokens), [access tokens](/en-us/entra/identity-platform/access-tokens), and [security tokens](/en-us/entra/identity-platform/security-tokens) that your app can receive from the [Microsoft identity platform](/en-us/entra/identity-platform/)*.*

Ensure that your application adheres to the Zero Trust [principle of least privilege](/en-us/entra/identity-platform/secure-least-privileged-access) and prevents usage in ways that compromise your intention. Limit user access with Just-In-Time and Just-Enough-Access (JIT/JEA), risk-based adaptive policies, and data protection. Separate your app's sensitive and powerful sections. Provide only authorized user access to these areas. Limit users who can use your application and the capabilities that they have in your app.

Build least privilege into how your application manages ID tokens that it receives from the Microsoft identity platform. Information in ID Tokens allows you to verify that a user is who they claim to be. The user or their organization might specify authentication conditions such as MFA, managed devices, and correct locations.

Make it easy for your customers to manage authorizations to your app. Reduce user creation and configuration overhead and manual processes. [Automatic user provisioning](/en-us/entra/identity/app-provisioning/plan-auto-user-provisioning) allows IT admins to automate user identity creation, maintenance, and removal in target identity stores. Your customers can base automation on changes to users and groups with [app provisioning](/en-us/entra/identity/app-provisioning/user-provisioning) or [HR driven provisioning](/en-us/entra/identity/app-provisioning/what-is-hr-driven-provisioning) in Microsoft Entra ID.

## Use token claims in your apps

Use claims in ID tokens for user experience inside your application as keys in a database. Provide access to the client application. The ID token is the core extension that [OpenID Connect](/en-us/entra/identity-platform/v2-protocols-oidc) (OIDC) makes to OAuth 2.0. Your app can receive ID tokens alongside or instead of access tokens.

In the standard pattern for security token authorization, an issued ID token allows the application to receive information about the user. Don't use the ID token as an authorization process to access resources. The authorization server issues ID tokens that contain claims with user information that include the following.

- The [audience](/en-us/entra/identity-platform/access-tokens#payload-claims) (`aud`) claim is your app's client ID. Accept only tokens for your API client ID.
- The `tid` claim is the ID of the tenant that issued the token. The `oid` claim is an immutable value that uniquely identifies the user. Use the unique combination of the `tid` and `oid` claims as a key when you need to associate data with the user. Use these claim values to connect your data back to the user's ID in Microsoft Entra ID.
- The `sub` claim is an immutable value that uniquely identities the user. The subject claim is also unique for your application. If you use the `sub` claim to associate data with the user, it's impossible to go from your data and connect it with a user in Microsoft Entra ID.

Your apps can use the `openid` scope to request an ID token from the Microsoft identity platform. The OIDC standard governs the `openid` scope along with the format and contents of the ID token. OIDC specifies these [scopes](/en-us/graph/permissions-reference#openid-connect-oidc-scopes):

- Use the `openid` scope to sign in the user and add a `sub` claim to the ID token. These scopes provide a user ID that is unique to the app and the user and calls the [UserInfo endpoint](/en-us/entra/identity-platform/userinfo).
- The `email` scope adds an `email` claim containing the user's email address to the ID token.
- The `profile` scope adds claims with basic profile attributes of the user (name, username) to the ID token.
- The `offline_access` scope allows the app to access user data even when the user isn't present.

The [Microsoft Authentication Library](/en-us/entra/identity-platform/msal-overview) (MSAL) always adds the openid, email, and `profile` scopes to every token request. As a result, MSAL always returns an ID token and an access token on every call to `AcquireTokenSilent` or AcquireTokenInteractive. MSAL always requests the `offline_access` scope. The Microsoft identity platform always returns `offline_access` scope even when the requesting app doesn't specify the `offline_access` scope.

Microsoft uses the OAuth2 standard to issue access tokens. The OAuth2 standard says that you receive a token, but it doesn't specify the token format or what needs to be in the token. When your application needs to access a resource that Microsoft Entra ID protects, it should use a scope that the resource defined.

For example, Microsoft Graph defines the `User.Read` scope that authorizes the application to access the current user's full user profile and the tenant's name. Microsoft Graph defines [permissions](/en-us/graph/permissions-reference) across the full range of functionality available in that API.

Upon authorization, the Microsoft identity platform returns an access token to your application. When you call the resource, your app provides this token as part of the authorization header of the HTTP request to the API.

## Manage token lifetimes

Applications can create a session for a user after the authentication successfully completes with Microsoft Entra ID. User session management drives how frequently a user needs repeat authentication. Its role in keeping an explicitly verified user in front of the app with the right privilege and for the right amount of time is crucial. Session lifetime must be based on the `exp` claim in the ID token. The `exp` claim is the time at which the ID token expires and the time after which you can no longer use the token to authenticate the user.

Always respect the [token lifetime](/en-us/entra/identity-platform/configurable-token-lifetimes) as provided in the token response for access tokens or the `exp` claim in the ID token. Conditions that govern token lifetime can include sign-in frequency for an enterprise. Your application can't configure the token lifetime. You can't request a token lifetime.

In general, ensure that tokens are valid and unexpired. The audience claim (`aud`) must match your client ID. Make sure the token comes from a trusted issuer. If you have a multitenant API, you might choose to filter so that only specific tenants can call your API. Make sure you enforce the token's lifetime. Check the `nbf` (not before) and the `exp` (expiration) claims to ensure the current time is within those two claims' values.

Don't aim for exceptionally long or short session lifetimes. Let the granted [ID token lifetime](/en-us/entra/identity-platform/id-tokens#id-token-lifetime) drive this decision. Keeping your app's sessions active beyond token validity violates the rules, policies, and concerns that drove an IT admin to set a token validity duration to prevent unauthorized access. Short sessions degrade user experience and don't necessarily increase the security posture. Popular frameworks like ASP.NET allow you to set session and cookie time-outs from Microsoft Entra ID token expiry time. Follow the identity provider's token expiry time to ensure that your user's sessions are never longer than the policies that the identity provider dictates.

## Cache and refresh tokens

Remember to appropriately cache tokens. MSAL automatically caches tokens but the tokens have lifetimes. Use tokens through the full length of their lifetimes and appropriately cache them. If you repeatedly ask for the same token, throttling causes your application to become less responsive. If your app abuses the token issuance, the time to issue new tokens to your app lengthens.

MSAL libraries manage the details of the OAuth2 protocol including the mechanics of refreshing tokens. If you aren't using MSAL, ensure that your library of choice makes effective use of [refresh tokens](/en-us/entra/identity-platform/refresh-tokens).

When your client acquires an access token to access a protected resource, it receives a refresh token. Use the refresh token to obtain new access/refresh token pairs after the current access token expires. Use refresh tokens to acquire extra access tokens for other resources. Refresh tokens are bound to a combination of user and client (not to a resource or tenant). You can use a refresh token to acquire access tokens across any combination of resource and tenant where your app has permissions.

## Manage token errors and bugs

Your application should never attempt to validate, decode, inspect, interpret, or examine the contents of an access token. These operations are strictly the responsibility of the resource API. If your app attempts to examine the contents of an access token, it's highly likely that your application breaks when the Microsoft identity platform issues encrypted tokens.

Rarely, a call to retrieve a token fails due to issues like network, infrastructure, or authentication service failure or outage. [Increase authentication experience resiliency](/en-us/entra/architecture/resilience-app-development-overview) in your application if a token acquisition failure occurs by following these best practices:

- Locally cache and secure tokens with encryption.
- Don't pass security artifacts like tokens around on nonsecure channels.
- Understand and act on exceptions and service responses from the identity provider.

Developers often have questions about looking inside tokens to debug issues such as receiving a 401 error from calling the resource. As more encrypted tokens prevent you from looking inside an access token, you need to find alternatives to looking inside access tokens. For debugging, the token response that contains the access token provides the information that you need.

In your code, check for error classes rather than individual error cases. For example, handle user interaction required rather than individual errors when the system doesn't grant permission. Because you might miss those individual cases, it's better to check for a classifier like user interaction rather than dig into individual error codes.

You might need to fall back to `AcquireTokenInteractive` and provide claims challenges that the `AcquireTokenSilent` call requires. Doing so ensures effective management of the interactive request.