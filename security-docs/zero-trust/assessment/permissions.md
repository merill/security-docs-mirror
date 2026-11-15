---
layout: Conceptual
title: Zero Trust Assessment Permissions and Roles | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/assessment/permissions
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: anstayk
author: astaykov
description: Review Zero Trust Assessment permissions, consent, and service roles to authorize interactive users and certificate-based applications.
ms.reviewer: joflore
ms.service: security
ms.subservice: zero-trust
ms.topic: reference
ms.date: 2026-11-11T00:00:00.0000000Z
ms.custom: msecd-doc-authoring-1032
ai-usage: ai-generated
locale: en-us
document_id: 1f5a4c63-5bd0-5f39-f93b-e2d487bb9756
document_version_independent_id: 1f5a4c63-5bd0-5f39-f93b-e2d487bb9756
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/assessment/permissions.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/assessment/permissions
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/assessment/permissions.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
- https://authoring-docs-microsoft.poolparty.biz/devrel/c900d0ba-7127-44a2-8ba8-afc4f786377d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
- https://authoring-docs-microsoft.poolparty.biz/devrel/179dea74-32c0-4804-9e75-383800f5d15e
platformId: fa48716a-3566-0181-e8e3-ef5cf056ed23
---

# Zero Trust Assessment Permissions and Roles | Microsoft Learn

To run the Zero Trust Assessment, arrange API permissions, administrator consent, directory roles, workload roles, and Azure resource access. Treat these as separate requirements. Grant access only to the services and resources you intend to assess.

These requirements describe the [development source](overview#source-and-package-versions). Published packages can differ. Activate eligible roles through Microsoft Entra Privileged Identity Management before connecting, and reconnect after changing access.

## Interactive user access

Use a highly privileged administrator for initial setup only, not for every assessment merely because that account granted consent.

For data loss prevention (DLP) checks, verify workload authorization as well as directory roles.

| Service or task | Required access and scope |
| --- | --- |
| **Initial Microsoft Graph consent** | For delegated permission grants, Cloud Application Administrator, Application Administrator, or another authorized consent role. Privileged Role Administrator can grant consent for any API, including Graph Application permissions; Global Administrator can also perform this setup. Consent doesn't assign runtime roles to the assessment user. |
| **Microsoft Graph assessment context** | All Graph permissions below and an active Global Reader or Global Administrator role. The module validates these roles for delegated authentication. Prefer Global Reader for the assessment account. |
| **Custom security attributes** | Attribute Assignment Reader, or Attribute Assignment Administrator, in addition to `CustomSecAttributeAssignment.Read.All`. Global Reader or Global Administrator alone doesn't grant access to attribute values. |
| **Azure** | Reader at the subscription/resource scopes to assess, or equivalent read permissions for the relevant resource providers. Azure access is separate from Microsoft Entra ID directory roles. Resource Graph only returns resources the caller can read; check coverage across every intended subscription. |
| **Exchange Online and Defender protection policies** | Global Reader plus Security Reader for protection-policy checks. With customized workload roles, verify access to `Get-AntiPhishPolicy`, `Get-HostedContentFilterPolicy`, `Get-MalwareFilterPolicy`, `Get-SafeAttachmentPolicy`, `Get-SafeLinksPolicy`, `Get-AtpPolicyForO365`, and `Get-TeamsProtectionPolicy`. |
| **Security & Compliance (Microsoft Purview)** | Global Reader provides the standard read-only role mapping, including Sensitivity Label Reader and View-Only DLP Compliance Management. Verify effective access to `Get-Label`, `Get-LabelPolicy`, `Get-DlpCompliancePolicy`, `Get-DlpComplianceRule`, `Get-DlpEdmSchema`, and `Get-DlpSensitiveInformationType`. Customized role groups can change access. |
| **SharePoint Online** | SharePoint Administrator for tenant administration commands, including `Get-SPOTenant`. Global Reader alone isn't sufficient for these PowerShell commands. |
| **Azure Information Protection (AIP)** | Azure Information Protection Administrator, Compliance Administrator, Compliance Data Administrator, or Global Administrator; alternatively, delegated AIP administrative access configured with `Add-AipServiceRoleBasedAdministrator`. Don't enable the AIP super-user feature or add yourself as a super user just to read its configuration. |
| **Defender advanced hunting** | `ThreatHunting.Read.All` plus access to the relevant Defender data through the user's effective security roles and data scope. Graph consent alone doesn't remove workload or licensing restrictions. |

These requirements don't guarantee that every check runs. Service configuration, licenses, scoped permissions, and supported authentication modes also affect coverage. Investigate permission errors rather than treating them as tenant security failures or granting broad administrator access without review.

For service-specific authorization details, see:

- [Consent administrator requirements](/en-us/entra/identity/enterprise-apps/grant-admin-consent).
- [Azure Resource Graph permissions](/en-us/azure/governance/resource-graph/overview#permissions-in-azure-resource-graph).
- [Exchange cmdlet permissions](/en-us/powershell/exchange/find-exchange-cmdlet-permissions?view=exchange-ps).
- [Defender and Purview role mappings](/en-us/defender-office-365/scc-permissions).
- [SharePoint tenant command requirements](/en-us/powershell/module/microsoft.online.sharepoint.powershell/get-spotenant?view=sharepoint-ps).
- [AIP connection requirements](/en-us/powershell/module/aipservice/connect-aipservice?view=azureipps).

## Microsoft Graph permissions

The development source requests these delegated permissions. For app-only authentication, configure the Application permission with the same name and grant administrator consent. A delegated grant doesn't authorize an application token.

- `Application.Read.All`.
- `AttackSimulation.Read.All`.
- `AuditLog.Read.All`.
- `CopilotPackages.Read.All`.
- `CrossTenantInformation.ReadBasic.All`.
- `CustomSecAttributeAssignment.Read.All`.
- `DeviceManagementApps.Read.All`.
- `DeviceManagementConfiguration.Read.All`.
- `DeviceManagementManagedDevices.Read.All`.
- `DeviceManagementRBAC.Read.All`.
- `DeviceManagementServiceConfig.Read.All`.
- `Directory.Read.All`.
- `DirectoryRecommendations.Read.All`.
- `EntitlementManagement.Read.All`.
- `IdentityRiskEvent.Read.All`.
- `IdentityRiskyServicePrincipal.Read.All`.
- `IdentityRiskyUser.Read.All`.
- `LifecycleWorkflows-Workflow.Read.All`.
- `NetworkAccess.Read.All`.
- `Policy.Read.All`.
- `Policy.Read.ConditionalAccess`.
- `Policy.Read.PermissionGrant`.
- `PrivilegedAccess.Read.AzureAD`.
- `PrivilegedAssignmentSchedule.Read.AzureADGroup`.
- `PrivilegedEligibilitySchedule.Read.AzureADGroup`.
- `Reports.Read.All`.
- `RoleManagement.Read.All`.
- `SecurityAlert.Read.All`.
- `SecurityEvents.Read.All`.
- `SecurityIdentitiesHealth.Read.All`.
- `SecurityIdentitiesSensors.Read.All`.
- `SecurityIncident.Read.All`.
- `ThreatHunting.Read.All`.
- `UserAuthenticationMethod.Read.All`.

To list the requirements for your installed version, import the module and query its scope helper:

```powershell
Import-Module ZeroTrustAssessment
Get-ZtGraphScope
```

The list comes from [Get-ZtGraphScope](https://github.com/microsoft/zerotrustassessment/blob/6a304637fc53846fd55182d495b6a2980f30b434/src/powershell/public/Get-ZtGraphScope.ps1). For permission definitions and supported types, see the [Microsoft Graph permissions reference](/en-us/graph/permissions-reference).

## App-only permissions and roles

Certificate authentication uses an application identity, not the signed-in user's roles. Configure the app registration, enterprise application/service principal, and resource assignments separately.

Graph Application permission consent requires Privileged Role Administrator, Global Administrator, or a suitable custom consent role. Application Administrator alone isn't sufficient. Azure resource-role assignment also requires administrative authority at the target scope.

| Service | Application permissions and authorization |
| --- | --- |
| **Microsoft Graph** | The Application permissions in the Graph list, with administrator consent. The module checks the complete list even for a single pillar. The delegated user's Global Reader role isn't the app-only Graph context check. |
| **Azure** | Reader, or equivalent resource-read permissions, assigned to the service principal on each intended subscription/resource scope. Graph permissions don't grant Azure access. |
| **Exchange Online** | **Office 365 Exchange Online &gt; Exchange.ManageAsApp**, with consent, plus supported directory roles or Exchange role-group assignments to the service principal. Global Reader and Security Reader are supported read-oriented directory roles; verify access to the protection cmdlets listed above. |
| **Security & Compliance** | **Microsoft Exchange Online Protection &gt; Exchange.ManageAsApp**, with consent, plus supported directory roles or Purview role-group assignments to the service principal. Follow the [Exchange/Purview app-only setup](/en-us/powershell/exchange/app-only-auth-powershell-v2?view=exchange-ps) and configure authorization for both services if using both. |
| **SharePoint Online** | **SharePoint &gt; Sites.FullControl.All** Application permission, with administrator consent, for tenant administration APIs. This is a broad permission, not a read-only scope or the Graph permission with the same name. See [SharePoint admin API authorization](/en-us/sharepoint/dev/sp-add-ins/sharepoint-admin-apis-authentication-and-authorization). |
| **Azure Information Protection** | The current connector expects **Azure Rights Management Services &gt; Application.Read.All**, with consent. This is separate from Graph `Application.Read.All`. The pinned AipService 3.1.0.0 exposes certificate service-principal parameter sets even though published cmdlet help doesn't list them. Verify effective access to `Get-AipServiceSuperUser` and `Get-AipServiceSuperUserFeature` in your environment. |

Caution

A read-only assessment doesn't mean every service offers read-only connection permissions. Review the SharePoint full-control grant with your tenant administrator. Don't add content-decryption or write permissions merely to suppress an error.

Exchange and Purview support built-in directory roles and custom workload role groups. Their role groups don't automatically share membership. Use the [app-only role-assignment procedure](/en-us/powershell/exchange/app-only-auth-powershell-v2?view=exchange-ps#step-5-assign-role-permissions-to-the-application) to scope commands.

Some service cmdlets don't support app-only authentication. A successful connection isn't proof of complete coverage; review connection outcomes and test diagnostics.