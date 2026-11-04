---
layout: Conceptual
title: Customize Microsoft Entra tokens | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/develop/zero-trust-token-customization
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: Learn about information in Microsoft Entra tokens and how to customize tokens to improve flexibility and control.
ms.subservice: zero-trust
ms.topic: concept-article
ms.date: 2025-02-24T00:00:00.0000000Z
ms.custom: template-concept
ms.service: security
ms.collection:
- zerotrust-dev
locale: en-us
document_id: 27ab8b6a-356e-a206-9497-dae9db2e8b10
document_version_independent_id: 27ab8b6a-356e-a206-9497-dae9db2e8b10
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/develop/zero-trust-token-customization.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/develop/zero-trust-token-customization
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/develop/zero-trust-token-customization.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
- https://authoring-docs-microsoft.poolparty.biz/devrel/5fc61396-d075-4560-aece-fdbda73d243f
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
- https://authoring-docs-microsoft.poolparty.biz/devrel/ad9437c1-8cda-4537-ad69-b4b263652e13
platformId: fda8acfa-ed2b-d9a4-3710-aa56f9759280
---

# Customize Microsoft Entra tokens | Microsoft Learn

As a developer, your primary interaction with Microsoft Entra ID is in requesting a token to identify the user. You also request a token to get authorization to call a web API. The web API token determines what that API can do when it services a particular request. In this article, you learn about the information that you can receive in tokens and how you can customize tokens. These [Zero Trust](overview) developer best practices improve flexibility and control while [increasing application security with least privilege](/en-us/entra/identity-platform/secure-least-privileged-access).

Your reasons for customizing your application tokens depend on the process you use to drive more granular authorization in your applications and APIs. For example, you might have different user roles, access levels, and functionalities in your app that rely on information from tokens.

The Microsoft Graph API provides a robust set of directory information and data across Microsoft 365. You can develop a fine-grained and rich authorization system by building on the data in Microsoft Graph. For example, you can access information from the user's group membership, detailed profile data, SharePoint, and Outlook to use in your authorization decisions. You can include authorization data in the token from Microsoft Entra ID.

## Application-level authorization

It's possible for IT Pros to add app-level authorization without token customization or code additions.

IT Pros can prevent tokens from being issued to any app in the tenant with the [user assignment required](/en-us/entra/identity/enterprise-apps/assign-user-or-group-access-portal) flag. This approach ensures that only a set of users can sign in to the application. Without this flag, all users in a tenant can access the application. With this flag, only assigned users and groups can access the application. When an assigned user accesses the app, the app receives a token. If the user doesn't have an assignment, the app doesn't receive a token. Remember to always gracefully handle token requests that don't receive tokens.

## Token customization methods

There are two ways to customize tokens: optional claims and claims mapping.

### Optional claims

[Optional claims](/en-us/entra/identity-platform/optional-claims) specify which claims you want Microsoft Entra ID to send to your application in tokens. You can use optional claims to:

- Select more claims to include in your application tokens.
- Change the behavior of claims that the Microsoft identity platform returns in tokens.
- Add and access custom claims for your application.

Optional claims hang off of the application registration object with a defined schema. They apply to the application no matter where it was running. When you're writing a multitenant application, optional claims work well because they're consistent across every tenant in Microsoft Entra ID. For example, an IP address isn't tenant-specific whereas an application has an IP address.

By default, guest users in a tenant can also sign in to your app. If you want to block guest users, [opt-in to the optional claim](/en-us/entra/identity-platform/optional-claims) (acct). If it's `1`, then the user has a guest classification. If you want to block guests, then block tokens with `acct==1`.

### Claims mapping policies

In Microsoft Entra ID, policy objects represent sets of rules on individual applications or on all applications in an organization. A [claims mapping policy](/en-us/entra/identity-platform/reference-claims-mapping-policy-type) modifies the claims that Microsoft Entra ID issues in tokens for specific applications.

You use claims mapping for tenant-specific information that has no schema (for example, `EmployeeID`, `DivisionName`). Claims mapping applies at the service principal level that the tenant admin controls. Claims mapping corresponds to the enterprise app or the service principal for that application. Each tenant can have its own claims mapping.

When you develop a line of business application, look specifically at what your tenant does (what specific claims your tenant has available that you can use in your token). For example, if an organization has a user's division name property (not a standard field in Microsoft Entra ID) in their on-premises Active Directory, use [Microsoft Entra Connect](/en-us/entra/identity/hybrid/connect/how-to-connect-sync-feature-directory-extensions) to sync it to Microsoft Entra ID.

To contain that information, use one of the standard extension attributes. Define your token with a division name claim that you can compose from the corresponding extension (even if it doesn't apply across every tenant). For example, an organization puts their division name in extension attribute 13.

With claims mapping, you can make it work for another tenant that puts their division name in attribute seven.

## Plan token customization

Which token you customize depends on your type of application: client application or API. There's no difference in what you can do to customize your token. What you can put in the token is the same for each of them. Which token you choose to customize depends upon which token your app consumes.

### Customize ID tokens

If you're developing a client application, you customize the [ID token](/en-us/entra/identity-platform/id-tokens) because it's the token that you request to identify the user. A token belongs to your app when the audience claim (`aud`) in the token matches the client ID of your application. For a client application that calls APIs but doesn't implement them, make sure you only customize your app's ID token.

The Azure portal and Microsoft Graph API allow you to customize the access token for your app as well, but those customizations have no effect. You can't customize an access token for an API that you don't own. Remember, your app must not attempt to decode or inspect an access token that your client app receives as authorization to call an API.

### Customize access tokens

When you develop an API, you customize the [access token](/en-us/entra/identity-platform/access-tokens) because your API receives access tokens as part of the client's call to your API.

Client applications always customize the ID token that they receive to identity the user. APIs customize the access tokens that the API receives as part of the call to the API.

## Groups and app roles

One of the most common authorization techniques is to base access on a user's group membership or assigned roles. [Configure group claims and app roles in tokens](configure-tokens-group-claims-app-roles) shows you how to configure your apps with app role definitions and assign security groups to app roles. These methods help to improve flexibility and control while increasing application Zero Trust security with least privilege.