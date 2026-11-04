---
layout: Conceptual
title: Application identity credentials when there's no user | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/develop/identity-non-user-applications
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: Learn why the best Zero Trust client credentials practice for services (nonuser applications) on Azure is Managed Identities for Azure Resources.
ms.subservice: zero-trust
ms.topic: best-practice
ms.service: security
ms.date: 2025-02-24T00:00:00.0000000Z
ms.custom: template-concept
ms.collection:
- zerotrust-dev
locale: en-us
document_id: 65c70fc6-6f34-5d8a-fda4-66ef78078013
document_version_independent_id: 65c70fc6-6f34-5d8a-fda4-66ef78078013
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/develop/identity-non-user-applications.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/develop/identity-non-user-applications
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/develop/identity-non-user-applications.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
platformId: 57c10d83-9302-f05e-eaf6-da9453c32553
---

# Application identity credentials when there's no user | Microsoft Learn

When you, as a developer, build nonuser applications, you don't have a user whom you can prompt for a username and password or Multifactor Authentication (MFA). You need to provide the application's identity on its own. This article explains why the best Zero Trust client credentials practice for services (nonuser applications) on Azure is [Managed Identities for Azure resources](/en-us/entra/identity/managed-identities-azure-resources/overview-for-developers?tabs=portal%2Cdotnet).

## Issues with service accounts

Use of a *service account* (use of a user account for a service) isn't a good solution. Microsoft Entra ID doesn't have a service account concept. When admins create user accounts for services and then share passwords with developers, it's insecure. It can't be passwordless or have an MFA. Instead of using a user account as a service account, your best solution is to use one of the following client credential options.

## Client credential options

There are four types of client credentials that can identify an application.

- Secret key
- Certificate
- [Managed Identities for Azure resources](/en-us/entra/identity/managed-identities-azure-resources/overview-for-developers?tabs=portal%2Cdotnet)
- [Federated Credentials](/en-us/entra/workload-id/workload-identity-federation)

## Secret key or certificate?

Secret keys are acceptable in sophisticated secrets management infrastructures (such as [Azure Key Vault](/en-us/azure/key-vault/general/overview)). However, you can't properly protect secret keys in scenarios where the IT Pro generates a secret key and then emails it to a developer.

Certificate-based client credentials are more secure than secret keys. You can better manage certificates because they aren't the secret itself. The secret isn't part of a transmission. When you use a secret key, your client sends the actual value of the secret key to Microsoft Entra ID. When you use a certificate, the private key of the certificate never leaves the device. Even if someone intercepts, decodes, and de-encrypts the transmission, the secret is still secure because the intercepting party doesn't have the private key.

## Best practice: use Managed Identities for Azure Resources

When you develop services (nonuser applications) in Azure, Managed Identities for Azure Resources provide an automatically managed identity in Microsoft Entra ID. The app can authenticate to any service that supports Microsoft Entra authentication without managing credentials. You don't need to manage secrets. You don't need to address the possibility of losing or mishandling them. Bad actors can't intercept secrets that don't move across the network. [Managed Identities for Azure resources](/en-us/entra/identity/managed-identities-azure-resources/overview-for-developers?tabs=portal%2Cdotnet) is the best practice when you build services on Azure.