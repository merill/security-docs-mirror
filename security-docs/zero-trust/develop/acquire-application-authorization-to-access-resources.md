---
layout: Conceptual
title: Acquire authorization to access resources | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/develop/acquire-application-authorization-to-access-resources
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: As a developer, learn how to best ensure Zero Trust when acquiring resource access permissions for your application.
ms.subservice: zero-trust
ms.topic: how-to
ms.service: security
ms.date: 2025-02-24T00:00:00.0000000Z
ms.collection:
- zerotrust-dev
ms.custom:
- template-concept
- sfi-ropc-nochange
locale: en-us
document_id: 7bdbe45f-d332-9e07-093d-d4ef8ed0eb93
document_version_independent_id: 7bdbe45f-d332-9e07-093d-d4ef8ed0eb93
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/develop/acquire-application-authorization-to-access-resources.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/develop/acquire-application-authorization-to-access-resources
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/develop/acquire-application-authorization-to-access-resources.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
- https://authoring-docs-microsoft.poolparty.biz/devrel/5fc61396-d075-4560-aece-fdbda73d243f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
- https://authoring-docs-microsoft.poolparty.biz/devrel/ad9437c1-8cda-4537-ad69-b4b263652e13
platformId: 60fca58a-607c-55dd-8841-60993a4918eb
---

# Acquire authorization to access resources | Microsoft Learn

This article helps you, as a developer, to understand how to best ensure [Zero Trust](overview) when acquiring resource access permissions for your application. To access protected resources like email or calendar data, your application needs the resource owner's *authorization*. The resource owner can *consent* to or deny your app's request. Your app receives an access token when the resource owner grants consent; your app doesn't receive an access token when the resource owner denies access.

## Conceptual review

You can use the Microsoft identity platform to [authenticate and authorize](/en-us/entra/identity-platform/authentication-vs-authorization) your applications and manage [permissions and consent](/en-us/entra/identity-platform/permissions-consent-overview). Let's start with some concepts:

- *Authentication* (sometimes shortened to *AuthN*) is the process of proving that your claimed identity is accurate. The Microsoft identity platform uses the [OpenID Connect](https://openid.net/connect/) protocol for handling authentication. *Authorization* (sometimes shortened to *AuthZ*) grants an authenticated party permission to do something. It specifies what data the authenticated party can access. The Microsoft identity platform uses the [OAuth2.0](https://oauth.net/2/) protocol for handling authorization. [Authorization options](/en-us/entra/identity-platform/authorization-basics) include access control lists (ACL), role-based access control, and attribute access control (ABAC). Authentication is often a factor of authorization.
- *Delegated access* (acting on behalf of a signed-in user) or *direct access* (acting only as the application's own identity) allows your application to access data. [Delegated access](/en-us/entra/identity-platform/permissions-consent-overview#delegated-access-access-on-behalf-of-a-user) requires delegated permissions (also known as [scopes](/en-us/entra/identity-platform/permissions-consent-overview#scopes-and-permissions)). The client and the user must be separately authorized to make the request. [Direct access](/en-us/entra/identity-platform/permissions-consent-overview#direct-access-app-only-access) might require application permissions (also known as [app roles](/en-us/entra/identity-platform/howto-add-app-roles-in-apps)). When applications receive app roles, they can be called applications permissions.
- *Delegated permissions*, used with delegated access, allow an application to act on behalf of a user, accessing only what the user can access. *Application permission*, used with direct access, allow an application to access any data with which the permission is associated. Only administrators and owners of [service principals](/en-us/entra/identity-platform/how-applications-are-added#what-are-service-principals-and-where-do-they-come-from) can consent to application permissions.
- *Consent* is the manner in which applications receive permissions. Users or admins authorize an application to access a protected resource. A [consent prompt](/en-us/entra/identity-platform/application-consent-experience) lists the permissions that the application requires along with publisher information.
- *Preauthorization* is the manner in which resource application owners grant access to client apps. They can do so in the Azure portal or with PowerShell and APIs like Microsoft Graph. They can grant resource permissions without requiring users to see a consent prompt for the set of [preauthorized](/en-us/entra/identity-platform/permissions-consent-overview#preauthorization) permissions.

## Difference between delegated and application permission

Applications work in two modes: when a user is present (delegated permission) and [when there's no user](identity-non-user-applications) (application permission). When there's a user in front of an application, you're compelled to act on behalf of that user. You shouldn't be acting on behalf of the application itself. When a user is directing your application, you're acting as the delegate for that user. You're getting permission to act on behalf of the user that the token identifies.

Service type applications (background tasks, daemons, server-to-server processes) don't have users who can identify themselves or type in a password. They require an application permission to act on behalf of itself (on behalf of the service application).

## Zero Trust application authorization best practices

Your [authorization approach](/en-us/entra/identity-platform/authorization-basics) has authentication as a component when you connect to a user present to the application and to the resource you're calling. When your application is acting on behalf of a user, we don't trust a calling application to tell us who the user is or let the application decide who the user is. Microsoft Entra ID verifies and directly provides information about the user in the token.

When you need to allow your application to call an API or authorize your application so that the application can access a resource, modern authorization schemes can require authorization through a [permission and consent framework](/en-us/entra/identity-platform/application-consent-experience). Reference [Security best practices for application properties](/en-us/entra/identity-platform/security-best-practices-for-app-registration) that include redirect URI, access tokens (used for implicit flows), certificates and secrets, application ID URI, and application ownership.