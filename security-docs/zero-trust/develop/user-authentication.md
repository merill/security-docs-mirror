---
layout: Conceptual
title: Authenticate users for Zero Trust | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/develop/user-authentication
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: Learn best practices to authenticate app users and enhance application security with Zero Trust principles of least privilege and verify explicitly.
ms.subservice: zero-trust
ms.topic: best-practice
ms.date: 2025-04-18T00:00:00.0000000Z
ms.custom: template-concept
ms.service: security
ms.collection:
- zerotrust-dev
locale: en-us
document_id: 33c8be7d-a4aa-de62-71d0-9e83c7faacef
document_version_independent_id: 33c8be7d-a4aa-de62-71d0-9e83c7faacef
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/develop/user-authentication.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/develop/user-authentication
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/develop/user-authentication.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/062d60c9-ee0f-402e-a046-b4e67c3572d6
- https://authoring-docs-microsoft.poolparty.biz/devrel/1e31b9be-b6e9-4221-a20b-d1460dbd5dfa
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
- https://authoring-docs-microsoft.poolparty.biz/devrel/17d3b3f6-a66e-4c69-9774-14a73c38e669
- https://authoring-docs-microsoft.poolparty.biz/devrel/8d63a4c4-4889-43b4-a98e-8e50dbfdb083
platformId: b1411f0d-26ab-0522-34c6-13d0e757c842
---

# Authenticate users for Zero Trust | Microsoft Learn

This article helps you, as a developer, to learn best practices for authenticating your application users in [Zero Trust application development](/en-us/entra/identity-platform/zero-trust-for-developers). Always enhance your application security with the Zero Trust principles of [least privilege and verify explicitly](/en-us/entra/identity-platform/secure-least-privileged-access).

## ID tokens in user authentication

When you need a user to authenticate to your app, rather than collecting a username and password, your application can request an [identity (ID) token](/en-us/entra/identity-platform/id-tokens). Authenticating users through the [Microsoft identity platform](/en-us/entra/identity-platform/v2-overview) avoids security risks that arise when your application retains user credentials. When you request ID tokens, if a bad actor breaches or compromises your application, there are no usernames and corresponding passwords in your app.

The Microsoft identity platform ID token is part of the [OpenID Connect](/en-us/entra/architecture/auth-oidc) (OIDC) standard that specifies ID tokens as [JSON Web Tokens](/en-us/entra/identity-platform/security-tokens) (JWT). The JWT long string comprises three components:

1. [Header claims](/en-us/entra/identity-platform/id-tokens#header-claims). The header claims present in ID tokens include `typ` (type claim), `alg` (algorithm for signing the token), and `kid` (thumbprint for the public key to validate the token's signature).
2. [Payload claims](/en-us/entra/identity-platform/id-tokens#payload-claims). The payload or body (the middle part of a JSON web token) contains a series of name attribute pairs. The standard requires that there be a claim with the `iss` (issuer name) that goes to the application that was issued the token (the `aud`, or audience claim).
3. [Signature](/en-us/entra/identity-platform/access-tokens#validating-the-signature). Microsoft Entra ID generates the token signature that apps can use to validate that the token is unmodified and you can trust it.

The following example of an ID token shows information about the user and confirms authentication to use the application.

```json
{
  "typ": "JWT",
  "alg": "RS256",
  "kid": "1LTMzakihiRla_8z2BEJVXeWMqo"
}.
{
  "ver": "2.0",
  "iss": "https://login.microsoftonline.com/3338040d-6c67-4c5b-b112-36a304b66dad/v2.0",
  "aud": "00001111-aaaa-2222-bbbb-3333cccc4444",
  "exp": 1536361411,
  "iat": 1536274711,
  "nbf": 1536274711,
  "sub": "AAAAAAAAAAAAAAAAAAAAAIkzqFVrSaSaFHy782bbtaQ",
  "name": "Abe Lincoln",
  "preferred_username": "AbeLi@microsoft.com",
  "oid": "aaaaaaaa-0000-1111-2222-bbbbbbbbbbbb",
  "tid": "aaaabbbb-0000-cccc-1111-dddd2222eeee",
}.
.[Signature]
```

## ID tokens in access management

To receive your application (client) ID, [register your app](app-registration) with the Microsoft identity platform. When you receive a token with an audience claim (`aud`) that matches your app's client ID, the identified user in the token authenticated to your app. IT admins might allow all users in the tenant to use your app. They might allow a group of which the user is a member to use your app.

If you receive a token whose audience claim is different from your app's client ID, immediately reject the token. The user isn't authenticated to your app because they signed into another app. Always make sure that the user has permission to use your app.

These claims details are important in user authentication:

- A JSON web token is valid until it expires. The `exp` (expiration) claim tells you when the token expires. If the current time is before the time in the `exp` claim, the token is valid.
- Don't consider the user as authenticated before the time specified in the `nbf` (not before time) claim. The `nbf` and `exp` times of the token define the token's valid lifetime. When the expiration time is imminent, make sure that you get a new ID token.
- The `sub` (subject claim) is a unique identifier for an application user. The same user has a different `sub` claim for other apps. If you want to store data to associate back to a user and prevent an attacker from making that association, use the subject claim. Because it doesn't expose the user's Microsoft Entra identity, it's the most private way to associate data to a user. The `sub` claim is immutable.
- If you want to share information across multiple applications, use the combination of tenant ID (`tid`) and object ID (`oid`) claims that are unique to the user. The combined tenant ID and object ID are immutable.
- No matter what happens to an individual's identity, the `sub`, `oid`, and `tid` claims remain immutable. Anything about the user can change and you can still key your data off identifying the user based on the subject or the combined `tid` and `oid` claims.

## Authentication with OIDC

To demonstrate user authentication, let's look at applications that use OIDC to authenticate a user. The same principles apply to apps that use Security Assertion Markup Language (SAML) or WS-Federation.

An app authenticates the user when the application requests an ID token from the Microsoft identity platform. Workloads (applications that don't have users present but rather run as services, background processes, daemons) skip this step.

You should always silently ask for this token first. To silently acquire a token in [Microsoft Authentication Libraries](/en-us/entra/identity-platform/msal-overview) (MSAL), your app can start with the `AcquireTokenSilent` method. If your app can authenticate without disturbing the user, it receives the requested ID token.

If the Microsoft identity platform can't complete the request without interacting with the user, then your app needs to fall back to the MSAL `AcquireTokenInteractive` method. To interactively acquire a token, perform the request by opening a web surface to an address under the `https://login.microsoftonline.com` domain.

From this web surface, the user has a private conversation with the Microsoft identity platform. Your app has no view into this conversation, nor does it have any control of the conversation. The Microsoft identity platform can ask for a user ID and password, multifactor authentication (MFA), passwordless authentication, or other authentication interaction that the IT admin or user configured.

Your application will receive an ID token after the user performed required authentication steps. When your app receives the token, you can be certain that the Microsoft identity platform authenticated the user. If your app doesn't receive an ID token, the Microsoft identity platform didn't authenticate the user. Don't allow unauthenticated users to continue into secured areas of your app.

It's best practice for applications to create a session for a user after it receives an ID token from Microsoft Entra ID. In the ID token that an app receives, an expiration (`exp`) claim with a Unix timestamp. This timestamp specifies the *on or after* expiration time for which the app mustn't accept the JWT for processing. Use this token expiration time to drive the lifetime of your user sessions. The `exp` claim plays a crucial role in keeping an explicitly verified user in front of the app with the right privilege and for the right amount of time.

## Single Sign On support

[Single sign-on](/en-us/entra/identity/enterprise-apps/what-is-single-sign-on) (SSO) authentication allows users to sign in with one set of credentials to multiple independent software systems. SSO allows application developers to not require a user to sign in to every application separately and repeatedly. At the core of SSO, developers ensure that all applications on the user's device share the web surface that authenticates the user. Artifacts on the web surface (such as session state and cookies) after successful authentication drive SSO.

As illustrated in the following diagram, the simplest use case of a shared web surface is an app that's running in a web browser (such as Microsoft Edge, Google Chrome, Firefox, Safari). Browser tabs share the SSO state.

[!\[Diagram illustrates the shared web surface scenario where an app is running in a browser.\](../media/develop/user-authentication/diagram-web-browser-simplest-case-inline.png)
 Diagram title: Web browser – simplest case. Appearing at the top center of the diagram is a cloud shape containing a Microsoft Entra ID icon. Below the cloud shape is a box. Connecting the cloud shape and the box is a line with an arrow on each end. The box label is "Keep me signed in, saves SSO state cookies across invocations." Inside the box, on the left side, is an icon that looks like a cookie. Below the cookie, the caption is "Private conversation with the user." Below the caption is an icon that represents the user. To the left of these three components, inside the box, is another box. The internal box label is "Tabs." Below the label are four square boxes that represent browser windows in tabs.](../media/develop/user-authentication/diagram-web-browser-simplest-case-expanded.png#lightbox)

The Microsoft identity platform manages the SSO state in any specific browser unless the user has different browsers open on the same device. On Windows 10 and newer, the Microsoft identity platform natively supports browser SSO Microsoft Edge. When the user signed into Windows, accommodations in Google Chrome (via the Windows 10 accounts extension) and in Mozilla Firefox v91+ (via a browser setting) allow each browser to share the SSO state of Windows itself.

As shown in the following diagram, the native application use case is more complicated.

[!\[Diagram illustrates the complicated native application use case of embedded browsers without SSO.\](../media/develop/user-authentication/diagram-native-app-embedded-browser-no-sso-inline.png)
 Diagram title: Native applications – embedded browsers – no SSO. Appearing at the top center of the diagram is a cloud shape containing a Microsoft Entra ID icon. At the bottom of the diagram are four boxes spread horizontally. At the bottom right corner of each box is an icon that represents a user. Inside each of the boxes is a representation of browser windows, including a cookie icon and a globe icon. Connecting each of the four boxes to the cloud shape is a line with an arrow on each end.](../media/develop/user-authentication/diagram-native-app-embedded-browser-no-sso-expanded.png#lightbox)

## Auth broker approach

A common pattern is for each native app to have its own embedded WebView that prevents it from participating in SSO. To address this scenario, Microsoft Entra ID uses an [authentication broker](/en-us/windows/uwp/security/web-authentication-broker) (auth broker) approach for native applications as illustrated in the following diagram.

[!\[Diagram illustrates the use of authentication brokers for native applications.\](../media/develop/user-authentication/diagram-auth-broker-approach-inline.png)
 Diagram title: Auth broker approach. Appearing at the top center of the diagram is a cloud shape containing a Microsoft Entra ID icon. Below the cloud shape is a rectangle shape with the label, Auth Broker. The rectangle shape contains a cookie icon and a globe icon. Connecting the cloud shape and the rectangle shape is a line with an arrow on each end. At the bottom of the diagram are four boxes spread horizontally. At the bottom right corner of each box is an icon that represents a user. Icons in each box represent browser windows. Connecting each of the four boxes to the rectangle shape is a line with an arrow on each end.](../media/develop/user-authentication/diagram-auth-broker-approach-expanded.png#lightbox)

With an auth broker in place, applications send authentication requests to the broker instead of directly to the Microsoft identity platform. In this way, the broker becomes the shared surface for all authentication on the device.

In addition to providing a shared surface, the auth broker provides other benefits. When adopting Zero Trust, enterprises might want to have applications run only from enterprise managed devices. Examples of enterprise device management include full Mobile Device Management (MDM) and scenarios where users bring their own devices that participate in Mobile Application Management (MAM).

By design, underlying operating systems (OS) isolate browsers. Developers need a closer connection with the OS to have full access to device details. In Windows, the auth broker is the Windows [Web Account Manager](/en-us/windows/uwp/security/web-account-manager) (WAM). On other devices, the auth broker is either the Microsoft Authenticator app (for devices running iOS or Android) or the Company Portal App (for devices running Android). Applications access the auth broker with MSAL. In Windows, an app can access the WAM without MSAL. However, MSAL is the easiest way for apps to access the auth broker (especially apps that aren't Universal Windows Platform apps).

Auth brokers work in combination with Microsoft Entra ID to utilize [Primary Refresh Tokens](/en-us/entra/identity/devices/concept-primary-refresh-token) (PRT) that reduce the need for users to authenticate multiple times. PRTs can determine whether the user is on a managed device. Microsoft Entra ID requires auth brokers as it introduces [Proof of Possession tokens](https://github.com/AzureAD/microsoft-authentication-library-for-dotnet/wiki/Proof-Of-Possession-%28PoP%29-tokens), a more secure option over the bearer tokens that are prevalent today.