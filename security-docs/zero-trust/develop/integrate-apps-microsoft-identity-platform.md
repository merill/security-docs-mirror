---
layout: Conceptual
title: Integrate apps with Microsoft Entra ID | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/develop/integrate-apps-microsoft-identity-platform
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: Build and integrate apps to secure in the enterprise. Understand how to securely integrate your app with Microsoft Entra ID and the Microsoft identity platform.
ms.date: 2025-04-18T00:00:00.0000000Z
ms.subservice: zero-trust
ms.topic: how-to
ms.service: security
ms.custom: template-concept
ms.collection:
- zerotrust-dev
locale: en-us
document_id: 310e9ffb-b50a-212d-71d7-c366b9c85cea
document_version_independent_id: 310e9ffb-b50a-212d-71d7-c366b9c85cea
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/develop/integrate-apps-microsoft-identity-platform.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/develop/integrate-apps-microsoft-identity-platform
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/develop/integrate-apps-microsoft-identity-platform.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
platformId: 8b188b06-3d69-e6d5-956d-fcc82f0db30d
---

# Integrate apps with Microsoft Entra ID | Microsoft Learn

As a developer, you can build and integrate apps that IT pros can secure in the enterprise. This article helps you to understand how to [use Zero Trust principles](overview) to securely integrate your app with Microsoft Entra ID and the Microsoft identity platform.

The Microsoft cloud-based identity and access management service, Microsoft Entra ID, provides developers with these [application integration](/en-us/entra/identity-platform/how-applications-are-added) benefits:

- Application authentication and authorization
- User authentication and authorization
- [Single sign-on (SSO)](/en-us/entra/identity-platform/single-sign-on-saml-protocol) using federation or password
- User provisioning and synchronization
- Role-based access control
- OAuth authorization services
- Application publishing and proxy
- Directory schema extension attributes

[!\[Diagram illustrates the unified toolkit of the Microsoft identity platform for developers that supports several identities and industry standards.\](../media/develop/integrate-apps-microsoft-identity-platform/diagram-microsoft-identity-platform-for-developers-inline.png)
 Diagram title: Microsoft identity platform for developers. Diagram subtitle: Build applications and integrate identity with one unified toolkit.](../media/develop/integrate-apps-microsoft-identity-platform/diagram-microsoft-identity-platform-for-developers-expanded.png#lightbox)

The preceding diagram illustrates the unified toolkit of the Microsoft identity platform for developers that supports several identities and industry standards. You can build applications and integrate identity with endpoints, libraries, web APIs, publisher verification, user provisioning, and auth brokers.

## Get started with app integration

The [Microsoft identity platform documentation](/en-us/entra/identity-platform/) site is the best starting point for you to learn how to integrate your applications with the Microsoft identity platform. You can find developer workshops, workshop materials, links to workshop recordings, and information about upcoming live events at https://aka.ms/UpcomingIDLOBDev.

While designing your app, you need to:

- Identify resources that your app needs to access.
- Consider whether your app has interactive users and workload components.
- Access resources that Microsoft Entra ID secures by [building apps that secure identity through permissions and access](identity).

## App types that you can integrate

The Microsoft identity platform performs [identity and access management](identity-iam-development-best-practices) (IAM) only for registered and [supported applications](identity-supported-account-types). To integrate with the Microsoft identity platform, your app must be able to provide a web browser-based component that can connect to the Microsoft identity platform's authorization endpoints under the `https://login.microsoftonline.com` address. Your app calls the token endpoint under the same address.

An integrated app can run from any location, including these examples:

- Microsoft Azure
- Other cloud providers
- Your own data centers and servers
- Desktop computers
- Mobile devices
- Internet of Things devices

The app or device, such as a web browser app accessing the authorization endpoint, can natively provide requirements. Cooperation between a disconnected browser and the application satisfies the requirements. For example, apps running on televisions might have the user perform the initial authentication with a browser on a desktop or mobile device.

You register your client application (web or native app) or web API to establish a trust relationship between your application and the Microsoft identity platform. Microsoft Entra application registration is critical because misconfiguration or lapse in hygiene of your application can result in downtime or compromise. Follow the [Security best practices for application properties in Microsoft Entra ID](/en-us/entra/identity-platform/security-best-practices-for-app-registration).

## Publish to Microsoft Entra application gallery

The [Microsoft Entra application gallery](/en-us/entra/identity/enterprise-apps/overview-application-gallery) is a collection of software as a service (SaaS) [applications in Microsoft Entra ID](/en-us/entra/identity-platform/app-objects-and-service-principals) preintegrated with Microsoft Entra ID. It contains thousands of applications that make it easy to deploy and configure SSO and automatic user provisioning.

[Automatic user provisioning](/en-us/entra/identity/app-provisioning/user-provisioning#what-applications-and-systems-can-i-use-with-azure-ad-automatic-user-provisioning) refers to creating user identities and roles in cloud applications that users need to access. Automatic provisioning includes maintaining and removing user identities as status or roles change. To provision users to SaaS apps and other systems, the Microsoft Entra provisioning service connects to a System for Cross-domain Identity Management (SCIM) 2.0 user management API endpoint that the application vendor provides. This SCIM endpoint allows Microsoft Entra ID to programmatically create, update, and remove users.

When you develop apps for Microsoft Entra ID, you can use the SCIM 2.0 user management API to build a SCIM endpoint that integrates Microsoft Entra ID for provisioning. For details, reference the [Develop and plan provisioning for a SCIM endpoint in Microsoft Entra ID](/en-us/entra/identity/app-provisioning/use-scim-to-provision-users-and-groups) tutorial.

[Publish your application](/en-us/entra/identity/enterprise-apps/v2-howto-app-gallery-listing) to the Microsoft Entra application gallery and make them publicly available for users to add to their tenants by completing these tasks:

- Complete the prerequisites.
- Create and publish documentation.
- Submit your application.
- Join the Microsoft partner network.

## Become a verified publisher

[Publisher verification](/en-us/entra/identity-platform/publisher-verification-overview) provides information to app users and organization admins about authenticity of developers who publish apps that integrate with the Microsoft identity platform. When you're a verified publisher, users can more easily decide if they want to allow your application to sign them in and access their profile information. They can base their decision on the information and access that your app requests in tokens.

App publishers verify their identity with Microsoft by associating their app registration with their verified [Microsoft Partner Network (MPN)](https://partner.microsoft.com/membership) account. During verification, Microsoft requests verification documentation. After you become a verified publisher, a blue verified badge displays in your app's Microsoft Entra consent prompts and web pages.