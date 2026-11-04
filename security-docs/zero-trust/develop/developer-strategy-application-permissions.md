---
layout: Conceptual
title: Develop application permissions strategy | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/develop/developer-strategy-application-permissions
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: Learn how to define an application permission approach to credential management to authenticate, authorize, and manage permissions and consent.
ms.subservice: zero-trust
ms.topic: how-to
ms.service: security
ms.date: 2025-02-24T00:00:00.0000000Z
ms.custom: template-concept
ms.collection:
- zerotrust-dev
locale: en-us
document_id: 44a72d59-cc39-fa0e-41db-7214c0ca4d4d
document_version_independent_id: 44a72d59-cc39-fa0e-41db-7214c0ca4d4d
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/develop/developer-strategy-application-permissions.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/develop/developer-strategy-application-permissions
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/develop/developer-strategy-application-permissions.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 05a955e8-4073-6e52-4f70-efa8ad82221d
---

# Develop application permissions strategy | Microsoft Learn

As you learn to [develop using Zero Trust principles](overview), reference this article after your review [Acquire authorization to access resources](acquire-application-authorization-to-access-resources) and [Develop delegated permissions strategy](developer-strategy-delegated-permission). Define your application permissions approach to credential management when you use the Microsoft identity platform to [authenticate and authorize](/en-us/entra/identity-platform/authentication-vs-authorization) your applications and manage [permissions and consent](/en-us/entra/identity-platform/permissions-consent-overview).

When [no user is involved](identity-non-user-applications), you don't have an [effective permission model](developer-strategy-delegated-permission) because your application always receives its preassigned permissions.

- **App proves it's the app requesting permission.** Your application [proves its own identity](identity-non-user-applications) with one of the following methods:

    - A certificate, which is the best option.
    - A secret in a sophisticated secret management system.
    - When you develop your services on Azure, use [Managed Identities for Azure resources](/en-us/entra/identity/managed-identities-azure-resources/overview), review the following Manage application credentials section.
- **App always requires advance admin consent.** Your application requests this permission with the `.default` scope. It requests the permissions the admin assigns to the application.
- **Trans user functionality.** By default, `User.ReadWrite.All` allows your application to update every user's profile. As an application permission, it allows your application to read and update the profile of every user in the tenant.
- **Permissions granted the app are always the permissions used.** Unlike a [delegated permission](developer-strategy-delegated-permission), application permissions aren't bounded by what any particular user can do.

## Limit application permissions

There are three ways to limit an application to less than global access.

- Microsoft Teams apps have [resource-specific consent](/en-us/microsoftteams/platform/graph-api/rsc/resource-specific-consent) (RSC) that allows an application to access a specific team rather than access all teams in the enterprise. RSC is a Microsoft Teams and Microsoft Graph API integration that allows your app to use API endpoints and manage specific resources. Its permissions model enables Teams and Chat owners to grant consent for your application to access and modify their Teams and Chat data.
- To limit app access to specific mailboxes with a PowerShell script, Microsoft Exchange administrators can create [Exchange application policies](/en-us/graph/auth-limit-mailbox-access). They can limit a particular application to specific mailboxes with `Calendar.Read` or `Mail.Read` access. That allows you to, for example, build an automation that can only read one mailbox or only send mail from one mailbox and not from everyone in the enterprise.
- To allow granular permissions for accessing SharePoint with an application, SharePoint has [Sites.Selected as a specific scope](https://devblogs.microsoft.com/microsoft365dev/controlling-app-access-on-specific-sharepoint-site-collections/). Choose `Sites.Selected` for your application instead of one of the other permissions results, by default, in applications without access to SharePoint site collections. The administrator uses the site permissions endpoint to grant Read, Write, or Read and Write permissions to your application.

## Manage applications credentials

Credential hygiene can ensure that your application quickly recovers from a potential breach. The following best practices guide you in developing applications that carry out detection and remediation while avoiding downtime and affecting legitimate users. These recommendations support the [Zero Trust principle of assume breach](../zero-trust-overview) in preparing you to respond to a security incident.

- **Remove all secrets from code and configuration**. When you use the Azure platform, place secrets in [Key vault](/en-us/azure/key-vault/general/basic-concepts) and access them via [Managed Identities for Azure resources](/en-us/entra/identity/managed-identities-azure-resources/overview). Make your code resilient to handle secret rotations if a compromise occurs. IT admins can remove and rotate secrets and certificates without taking down your application or affecting legitimate users.
- **Use certificates instead of client secrets unless a secure process is in place to manage secrets**. Attackers know that client secrets tend to be less securely handled and leaked secret usage is difficult to track. Certificates can be better managed and revoked if compromised. When you use secrets, build or use a secure no-touch deployment and rollover process for them. Use secrets with a set expiry time period (for example, one year, two years) and avoid *never expires*.
- **Regularly roll over certificates and secrets** to [build resiliency](/en-us/entra/architecture/resilience-app-development-overview) in your application and avoids outage due to an emergency rollover.