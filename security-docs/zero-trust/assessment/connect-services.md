---
layout: Conceptual
title: Connect to Zero Trust Assessment Services | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/assessment/connect-services
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: anstayk
author: astaykov
description: Connect to Microsoft 365 and Azure services interactively or with an application certificate before running a Zero Trust Assessment.
ms.reviewer: joflore
ms.service: security
ms.subservice: zero-trust
ms.topic: how-to
ms.date: 2026-11-11T00:00:00.0000000Z
ms.custom: msecd-doc-authoring-1032
ai-usage: ai-generated
locale: en-us
document_id: d4ec7bf6-8bda-1e49-c0c4-84b1c71b6ff8
document_version_independent_id: d4ec7bf6-8bda-1e49-c0c4-84b1c71b6ff8
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/assessment/connect-services.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/assessment/connect-services
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/assessment/connect-services.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: cb8f69ff-5dbc-c0b5-6723-73cf14e77dd3
---

# Connect to Zero Trust Assessment Services | Microsoft Learn

Connect the Zero Trust Assessment to the Microsoft 365 and Azure services you want to assess. Use interactive sign-in for a user-run assessment or certificate authentication for app-only access without storing user credentials. Prepare the module and service permissions before connecting.

These instructions describe the development connector. App-only support and connection options can differ between published packages.

## Prerequisites

- Completion of the [assessment installation](get-started#install-the-powershell-modules).
- The [interactive user access](permissions#interactive-user-access) or [application permissions and roles](permissions#app-only-permissions-and-roles) for the services and resource scopes to assess.
- For app-only access, an app registration and a certificate with its private key available to the assessment machine, as described in the certificate procedure in the following section.

## Connect interactively

Choose the tenant explicitly to reduce the risk of assessing the wrong organization.

1. Activate eligible roles through Microsoft Entra Privileged Identity Management before connecting. Arrange consent separately from the assessment user's runtime roles.
2. Connect to the tenant you want to assess, replacing the example domain:

    ```powershell
    Connect-ZtAssessment -Tenant contoso.onmicrosoft.com
    ```
3. Complete the service prompts and review the connection status messages. Services authenticate separately, but cached sessions and single sign-on can reduce prompts. SharePoint interactive authentication uses the system browser.
4. Reconnect after changing access or context. Use `-Force` when you need to refresh existing connections.

`-Tenant` is an alias for `-TenantId` and accepts a tenant GUID or verified domain name for interactive sign-in. If you don't include this parameter, Microsoft Graph uses an organizations context and derives the tenant from sign-in.

Consent is requested when the application lacks the required grants. New scopes can require consent again.

## Select services and connection options

By default, `Connect-ZtAssessment` connects to all available services. Select services only after considering the effect on assessment coverage.

1. Identify the services you want to assess:

    | Service selector | Underlying command |
    | --- | --- |
    | **`Graph`** | `Connect-MgGraph`. |
    | **`Azure`** | `Connect-AzAccount`. |
    | **`AipService`** | `Connect-AipService`. |
    | **`SharePointOnline`** | `Connect-SPOService`. |
    | **`ExchangeOnline`** | `Connect-ExchangeOnline`. |
    | **`SecurityCompliance`** | `Connect-IPPSSession`. |
2. Use `-Service` to select services. For example, `Connect-ZtAssessment -Tenant contoso.onmicrosoft.com -Service Graph,Azure` selects Graph and Azure. The connector adds Graph first if it isn't already connected.
3. Review connection outcomes before running the assessment. Skipping Azure limits Infrastructure, Network, and security operations (SecOps) coverage, not just audit and sign-in log export checks.

Use these additional options when needed:

| Option | Purpose or constraint |
| --- | --- |
| **`-Force`** | Refresh existing connections after access or context changes. |
| **`-SharePointAdminUrl`** | Supply the tenant admin URL if the connector can't infer it. |
| **`-UserPrincipalName`** | Supply the user identity for Security & Compliance. |
| **`-Environment`**, **`-ExchangeEnvironmentName`** | Select cloud environments. Use the values documented by `Get-Help Connect-ZtAssessment -Full`. |
| **`-UseDeviceCode`** | Not an all-service unattended mode. Security & Compliance doesn't support that flow in this connector. SharePoint and Azure Information Protection (AIP) have their own authentication behavior. |

## Connect with an application certificate

Authorize the application identity at each service, not just the person who configures it.

1. Register an application in the target tenant. Record its application/client ID and tenant GUID.
2. Configure and grant consent for the [app-only permissions](permissions#app-only-permissions-and-roles). Assign workload and Azure resource roles to the service principal.
3. Upload the certificate's public key to the app registration. Install the corresponding certificate and private key in the local user's certificate store on the assessment machine. For Exchange, follow the certificate-provider requirements in the [app-only authentication guide](/en-us/powershell/exchange/app-only-auth-powershell-v2?view=exchange-ps).
4. If connecting to SharePoint, provide an exportable private key. The current connector passes a temporary certificate file into its Windows PowerShell compatibility session. Protect the key and follow any temporary-file cleanup warning.
5. Connect with the client ID, tenant GUID, and certificate thumbprint. Replace the placeholders with your values:

    ```powershell
    Connect-ZtAssessment -ClientId '<application-id>' -TenantId '<tenant-guid>' -Certificate '<certificate-thumbprint>' -Service All
    ```
6. Review each service's connection status and any authorization errors before running the assessment.

Both `-ClientId` and `-TenantId` are required with `-Certificate`. Don't combine certificate authentication with `-UseDeviceCode`. For cross-service app-only connections, use the tenant GUID rather than assuming every service accepts a domain name. The connector resolves the initial `.onmicrosoft.com` domain for Exchange and Security & Compliance.

App-only coverage depends on the package, dependency versions, permissions, and commands used by individual checks. Missing connections produce service-related skips; other authorization errors can appear in test diagnostics. Review those outcomes before treating an unattended run as complete.