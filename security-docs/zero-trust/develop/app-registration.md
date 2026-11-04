---
layout: Conceptual
title: Register applications | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/develop/app-registration
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: Learn about application registration process and requirements to ensure Zero Trust principles of use least privileged access and assume breach.
ms.subservice: zero-trust
ms.topic: concept-article
ms.service: security
ms.date: 2025-02-24T00:00:00.0000000Z
ms.custom: template-concept
ms.collection:
- zerotrust-dev
locale: en-us
document_id: 7ad78d81-1e43-cd3b-3b2d-c9279be0836e
document_version_independent_id: 7ad78d81-1e43-cd3b-3b2d-c9279be0836e
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/develop/app-registration.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/develop/app-registration
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/develop/app-registration.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
- https://authoring-docs-microsoft.poolparty.biz/devrel/5fc61396-d075-4560-aece-fdbda73d243f
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
- https://authoring-docs-microsoft.poolparty.biz/devrel/ad9437c1-8cda-4537-ad69-b4b263652e13
platformId: 747fc839-591a-5582-4abd-cda1a5e2ce8d
---

# Register applications | Microsoft Learn

The [Microsoft identity platform](/en-us/entra/identity-platform/)[app registration portal](/en-us/entra/identity-platform/quickstart-register-app) is the primary entry point for applications that use the platform for authentication and associated needs. As a developer, when your register and configure your apps, your choices drive and affect how well your application satisfies [Zero Trust principles](../zero-trust-overview). Effective app registration considers the principles of *use least privileged access* and *assume breach*. This article helps you to learn about the application registration process and its requirements to ensure that your apps follow a Zero Trust approach to security.

[Application management in Microsoft Entra ID](/en-us/entra/identity/enterprise-apps/what-is-application-management) (Microsoft Entra ID) helps you to securely create, configure, manage, and monitor applications in the cloud. When you register your application in a Microsoft Entra tenant, you configure secure user access.

Microsoft Entra ID represents applications by [application objects](/en-us/entra/identity-platform/app-objects-and-service-principals#application-object) and [service principals](/en-us/entra/identity-platform/app-objects-and-service-principals#service-principal-object). With some [exceptions](/en-us/entra/identity-platform/how-applications-are-added#notes-and-exceptions), applications are application objects. Think of a service principal as an instance of an application that references an application object. Multiple service principals across directories can reference a single application object.

You can configure your application to use Microsoft Entra ID through three methods: [in Visual Studio](/en-us/visualstudio/azure/vs-active-directory-add-connected-service), with the Microsoft Graph API, or with PowerShell. There are developer experiences in Azure and in [API Explorer](/en-us/iis-administration/api-explorer/) across developer centers. Reference the required decisions and tasks for the [developer and IT Pro roles](identity-developer-administrator-responsibilities) to build and deploy secure applications in the Microsoft identity platform.

## Who can add and register applications

Admins and, when the tenant permits users and developers, might create application objects when they register applications in the Azure portal. By default, all users in a directory can [register application objects](/en-us/entra/identity-platform/how-applications-are-added#who-has-permission-to-add-applications-to-my-azure-ad-instance) that they develop. Application object developers decide which applications share and give access to organizational data through [consent](/en-us/entra/identity-platform/v2-admin-consent).

When the first user in a directory signs in to an application and grants consent, the system creates a service principal in the tenant that stores all user consent information. Microsoft Entra ID automatically creates a service principal for a newly registered app in the tenant before a [user authenticates](user-authentication).

Users with at least the [Application Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference#application-administrator) or [Cloud Application Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference#cloud-application-administrator) role can perform specific application tasks (such as adding applications from the app gallery and configuring applications to use application proxy).

## Register application objects

As a developer, you register your apps that use the Microsoft identity platform. Register your apps in the Azure portal or by calling [Microsoft Graph application APIs](/en-us/graph/api/resources/application). After you register your app, it communicates with the Microsoft identity platform by sending requests to the endpoint.

You might not have permission to create or modify an application registration. When administrators don't give you permissions to register your applications, ask them how you can convey necessary app registration information to them.

[Application registration properties](/en-us/entra/identity-platform/how-applications-are-added#what-are-application-objects-and-where-do-they-come-from) might include the following components.

- Name, logo, and publisher
- Redirect Uniform Resource Identifiers (URI)
- Secrets (symmetric and/or asymmetric keys used to authenticate the application)
- API dependencies (OAuth)
- Published APIs/resources/scopes (OAuth)
- App roles for role-based access control
- Metadata and configuration for single sign-on (SSO), user provisioning, and proxy

A required part of app registration is your selection of [supported account types](identity-supported-account-types) to define who can use your app based on the user's account type. Microsoft Entra administrators follow the [application model](/en-us/entra/identity-platform/application-model) to manage application objects in the Azure portal through the [App registrations](https://aka.ms/appregistrations) experience and define application settings that tell the service how to issue tokens to the application.

During registration, you receive the identity of your application: the **application (client) ID**. Your app uses its **client ID** every time it performs a transaction through the Microsoft identity platform.

## App registration best practices

Follow [security best practices for application properties](/en-us/entra/identity-platform/security-best-practices-for-app-registration) when you register your application in Microsoft Entra ID as a critical part of its business use. Aim to prevent downtime or compromise that might affect the entire organization. The following recommendations help you to develop your secure application around Zero Trust principles.

- **Use the [Microsoft identity platform integration checklist](/en-us/entra/identity-platform/identity-platform-integration-checklist)** to ensure high quality and secure integration. Maintain the quality and security of your app.
- **Properly define your redirect URLs**. Reference the [Redirect URI (reply URL) restrictions and limitations](/en-us/entra/identity-platform/reply-url) to avoid compatibility and security issues.
- **Check redirect URIs in your app registration for ownership to avoid domain takeovers**. Redirect URLs should be on domains that you know and own. Regularly review and remove unnecessary and unused URIs. Don't use non-https URIs in production apps.
- **Always define and maintain app and service principal owners for your registered apps in your tenant**. Avoid orphaned apps (apps and [service principals](/en-us/entra/identity-platform/app-objects-and-service-principals) without assigned owners). Ensure that IT admins can easily and quickly identify app owners during an emergency. Keep the number of app owners small. Make it difficult for a compromised user account to affect multiple applications.
- **Avoid using the same app registration** **for multiple apps**. Separating app registrations helps you to enable least privileged access and reduce impact during a breach.
    - Use separate app registrations for apps that sign in users and apps that expose data and operations via API (unless tightly coupled). This approach allows permissions for a higher privileged API, such as Microsoft Graph and credentials (like secrets and certificates), at a distance from apps that sign in and interact with users.
    - Use separate app registrations for web apps and APIs. This approach helps ensure that, if the web API has a higher set of permissions, then the client app doesn't inherit them.
- **Define your application as a multi-tenant app only when necessary**. [Multitenant apps](/en-us/entra/identity-platform/howto-convert-app-to-be-multi-tenant) allow for provisioning in tenants other than yours. They require more management overhead to filter unwanted access. Unless you intend to develop your app as a multitenant app, start with a SignInAudience value of AzureADMyOrg.