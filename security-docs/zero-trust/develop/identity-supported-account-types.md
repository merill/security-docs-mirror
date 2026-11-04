---
layout: Conceptual
title: Identity and account types for single- and multitenant apps | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/develop/identity-supported-account-types
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: In this article, we explain how developers can determine, during app registration, which users their app allows from single- and multitenants.
ms.subservice: zero-trust
ms.topic: concept-article
ms.service: security
ms.date: 2025-04-18T00:00:00.0000000Z
ms.custom: template-concept
ms.collection:
- zerotrust-dev
locale: en-us
document_id: 3860a7bf-9304-560b-8da4-fc9e997233c2
document_version_independent_id: 3860a7bf-9304-560b-8da4-fc9e997233c2
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/develop/identity-supported-account-types.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/develop/identity-supported-account-types
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/develop/identity-supported-account-types.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
- https://authoring-docs-microsoft.poolparty.biz/devrel/49ce37d9-33ea-421e-9eb9-c852f2d9c13f
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
- https://authoring-docs-microsoft.poolparty.biz/devrel/d2e24716-af9a-48e2-bf0d-f248d9cc672a
platformId: e8343d2b-6e5c-2e25-92d9-b28a2fee3bf4
---

# Identity and account types for single- and multitenant apps | Microsoft Learn

This article explains how you, as a developer, can choose if your app allows only users from your Microsoft Entra tenant, any Microsoft Entra tenant, or users with personal Microsoft accounts. You can configure your app to be either [single tenant or multitenant](/en-us/entra/identity-platform/single-and-multi-tenant-apps) during [app registration](/en-us/entra/identity-platform/quickstart-register-app) in Microsoft Entra. Ensure the [Zero Trust](overview) principle of least privilege access so that your app only requests permissions it needs.

The Microsoft identity platform provides support for specific [identity types](identity-supported-account-types):

- Work or school accounts when the entity has an account in a Microsoft Entra ID.
- Microsoft personal accounts (MSA) for anyone who has account in Outlook.com, Hotmail, Live, Skype, Xbox, etc.
- [External identities](/en-us/entra/external-id/) in Microsoft Entra ID for partners (users outside of your organization).

A required part of application registration in Microsoft Entra ID is your selection of supported account types. While IT Pros in administrator roles decide who can consent to apps in their tenant, you, as a developer, specify who can use your app based on account type. When a tenant doesn't allow you to register your application in Microsoft Entra ID, administrators provide you with a way to communicate those details to them through another mechanism.

You choose from the following supported account type options when registering your application.

- `Accounts in this organizational directory only (O365 only - Single tenant)`
- `Accounts in any organizational directory (Any Azure AD directory - Multitenant)`
- `Accounts in any organizational directory (Any Azure AD directory - Multitenant) and personal Microsoft accounts (e.g. Skype, Xbox)`
- `Personal Microsoft accounts only`

## Accounts in this organizational directory only - single tenant

When you select **Accounts in this organizational directory only (O365 only - Single tenant)**, you allow only users and guests from the tenant where the developer registered their app. This option is the most common for Line of Business (LOB) applications.

## Accounts in any organizational directory only - multitenant

When you select **Accounts in any organizational directory (Any Microsoft Entra directory - Multitenant)**, you allow any user from any Microsoft Entra directory to sign in to your multitenant application. If you want to only allow users from specific tenants, you filter these users in your code by checking that the [tid claim in the id_token](/en-us/entra/identity-platform/id-tokens) is on your allowed list of tenants. Your application can use the organizations endpoint or the common endpoint to sign in users in the user's home tenant. To support guest users signing in to your multitenant app, you use the specific tenant endpoint for the tenant where the user is a guest to sign in the user.

## Accounts in any organizational account and personal Microsoft accounts

When you select **Accounts in any organizational account and personal Microsoft accounts (Any Microsoft Entra directory - Multitenant) and personal Microsoft accounts (e.g. Skype, Xbox)**, you allow a user to sign in to your application with their native identity from any Microsoft Entra tenant or consumer account. The same tenant filtering and endpoint usage apply to these apps as they do to multitenant apps as previously described.

## Personal Microsoft accounts only

When you select **Personal Microsoft accounts only**, you allow only users with consumer accounts to use your app.

## It's not just up to the developer

While you define in your application registration who can sign in to your app, the final say comes from the individual user or the admins of the user's home tenant. Tenant admins often want to have more control over an app than just who can sign in. For example, they might want to apply a Conditional Access policy to the app or control which group they allow to use the application. To enable tenant admins to have this control, there's a second object in the Microsoft identity platform: the Enterprise app. Enterprise apps are also known as [Service Principals](/en-us/entra/identity-platform/app-objects-and-service-principals).

## Apps with users in other tenants or other consumer accounts

Supported account types include the **Accounts in any organizational directory** option for a multitenant application so that you can allow organizational directory users. In other words, you allow a user to sign in to your application with their native identity from any Microsoft Entra ID. A Service Principal is automatically created in the tenant when first user from a tenant authenticates to the app.

There's only one application registration or application object. However, there's an Enterprise app, or Service Principal (SP), in every tenant that allows users to sign in to the app. The tenant admin can control how the app works in their tenant.

## Multitenant app considerations

Multitenant apps sign in users from the user's home tenant when the app uses the common or organization endpoint. The app has one app registration as shown in the following diagram. In this example, the application is registered in the Adatum tenant. User A from Adatum and User B from Contoso can both sign into the app with the expectation User A from Adatum accesses Adatum data and that User B from Contoso accesses Contoso data.

[!\[Diagram shows how multitenant apps sign in users from user's home tenant when app uses common or organization endpoint.\](../media/develop/identity-supported-account-types/diagram-multitenant-app-common-endpoint-inline.png)
 Diagram title: Multitenant App vs. External Identities, also known as B 2 B.](../media/develop/identity-supported-account-types/diagram-multitenant-app-common-endpoint-expanded.png#lightbox)

As a developer, it's your responsibility to keep tenant information separate. For example, if the Contoso data is from Microsoft Graph, the User B from Contoso only sees Contoso's Microsoft Graph data. There's no possibility for User B from Contoso to access Microsoft Graph data in the Adatum tenant because Microsoft 365 has true data separation.

In the diagram, User B from Contoso can sign in to the application and they can access Contoso data in your application. Your application can use the common (or organization) endpoints so the user natively signs in to their tenant, requiring no invitation process. A user can run and sign in to your application and it works after the user or tenant admin grants consent.