---
layout: Conceptual
title: Compromised and malicious applications investigation | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-operations-playbook-compromised-malicious-app
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Learn how to investigate if one or more applications in a customer tenant are compromised.
keywords: compromise, malicious, applications, investigation, attack, microsoft threat protection, microsoft 365, search, query, telemetry, security events, antivirus, firewall, incident response, playbook, guidance, Microsoft Defender XDR
search.product: DART
ms.service: security
ms.subservice: zero-trust
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
manager: CelesteDG
ms.date: 2025-03-12T00:00:00.0000000Z
ms.collection:
- msftsolution-secops
ms.topic: how-to
ms.custom:
- cxdef-zt-ransomware
- has-azure-ad-ps-ref
- azure-ad-ref-level-one-done
- sfi-image-nochange
locale: en-us
document_id: b26f8e7f-0193-2f76-f5b4-a4389c76f2b9
document_version_independent_id: b26f8e7f-0193-2f76-f5b4-a4389c76f2b9
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-operations-playbook-compromised-malicious-app.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-operations-playbook-compromised-malicious-app
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-operations-playbook-compromised-malicious-app.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
- https://authoring-docs-microsoft.poolparty.biz/devrel/5fc61396-d075-4560-aece-fdbda73d243f
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
- https://authoring-docs-microsoft.poolparty.biz/devrel/ad9437c1-8cda-4537-ad69-b4b263652e13
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: 76f215ce-ead3-5d5e-24c1-b3cb8812ec22
---

# Compromised and malicious applications investigation | Microsoft Learn

This article provides guidance on identifying and investigating malicious attacks on one or more applications in a customer tenant. The step-by-step instructions help you take the required remedial action to protect information and minimize further risks.

It is part of the incident response guidance for the Security Operations (SecOps) discipline in the **Microsoft Security Adoption Framework (SAF)**.

- **Prerequisites:** Covers the specific requirements you need to complete before starting the investigation. For example, logging that should be turned on, roles and permissions required, among others.
- **Workflow:** Shows the logical flow that you should follow to perform this investigation.
- **Investigation steps:** Includes a detailed step-by-step guidance for this specific investigation.
- **Containment steps:** Contains steps on how to disable the compromised applications.
- **Recovery steps:** Contains high-level steps on how to recover/mitigate from a malicious attack on compromised applications.
- **References:** Contains other reading and reference materials.

## Prerequisites

Before starting the investigation, make sure you have the correct tools and permissions to gather detailed information.

- To use Identity protection signals, the tenant must be licensed for Microsoft Entra ID P2.

    - Understanding of the [Identity Protection risk concepts](/en-us/azure/active-directory/identity-protection/concept-identity-protection-risks)
    - Understanding of the [Identity Protection investigation concepts](/en-us/azure/active-directory/identity-protection/howto-identity-protection-investigate-risk)
- An account with at least the [Security Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference#security-administrator) role.
- Ability to use [Microsoft Graph Explorer](/en-us/graph/graph-explorer/graph-explorer-overview) and be familiar (to some extent) with the Microsoft Graph API.
- Familiarize yourself with the [application auditing concepts](/en-us/azure/active-directory/fundamentals/security-operations-applications) (part of https://aka.ms/AzureADSecOps).
- Make sure all Enterprise apps in your tenant have an owner set for the purposes of accountability. Review the concepts on [overview of app owners](/en-us/azure/active-directory/manage-apps/overview-assign-app-owners) and [assigning app owners](/en-us/azure/active-directory/manage-apps/assign-app-owners).
- Familiarize yourself with the concepts of the [App Consent grant investigation](security-operations-playbook-app-consent) (part of https://aka.ms/IRPlaybooks).
- Make sure you understand the following Microsoft Entra permissions:

    - [Risky permissions](security-operations-playbook-app-consent#classifying-risky-permissions)
    - [Consent model and the Admin consent workflow](/en-us/azure/active-directory/manage-apps/configure-admin-consent-workflow)
- Familiarize yourself with the concepts of [Workload identity risk detections](/en-us/azure/active-directory/identity-protection/concept-workload-identity-risk).
- You must have full Microsoft 365 E5 license to use Microsoft Defender for Cloud Apps.

    - Understand the concepts of [anomaly detection alert investigation](/en-us/defender-cloud-apps/app-governance-anomaly-detection-alerts)
- Familiarize yourself with the following application management policies:

    - [Microsoft Entra application authentication methods API overview (preview)](/en-us/graph/api/resources/applicationauthenticationmethodpolicy)
    - [appManagementPolicy resource type](/en-us/graph/api/resources/appmanagementpolicy)
- Familiarize yourself with the following app governance policies:

    - [The App Governance blog](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/announcing-public-preview-of-app-governance/ba-p/2543768)
    - [App governance in Defender for Cloud Apps](/en-us/defender-cloud-apps/app-governance-manage-app-governance)

### Required tools

For an effective investigation, install the following PowerShell module and the toolkit on your investigation machine:

- [Microsoft Entra Incident Response PowerShell Module](https://github.com/AzureAD/Azure-AD-Incident-Response-PowerShell-Module)
- [Microsoft Entra Toolkit](https://github.com/microsoft/AzureADToolkit)

## Workflow

![Detailed flowchart of investigation steps.](media/compromised-malicious-apps/ir-playbook-compromised-apps-flow.png)

## Investigation steps

For this investigation, assume that you either have an indication for a potential application compromise in the form of a user report, Microsoft Entra sign-in logs example, or an identity protection detection. Make sure to complete and enable all required prerequisite steps.

This playbook is created with the intention that not all Microsoft customers and their investigation teams have the full Microsoft 365 E5 or Microsoft Entra ID P2 license suite available or configured. This playbook highlights other automation capabilities when appropriate.

### Determine application type

It's important to determine the type of application (multi or single tenant) early in the investigation phase to get the correct information needed to reach out to the application owner. For more information, see [Tenancy in Microsoft Entra ID](/en-us/azure/active-directory/develop/single-and-multi-tenant-apps).

#### Multitenant applications

For multitenant applications, the application is hosted and managed by a third party. Identify the process needed to reach out and report issues to the application owner.

#### Single-tenant applications

Find the contact details of the application owner within your organization. You can find it under the **Owners** tab on the **Enterprise Applications** section. Alternatively, your organization might have a database that has this information.

You can also execute this Microsoft Graph query:

```HTTP
GET https://graph.microsoft.com/v1.0/applications/{id}/owners
```

### Check Identity Protection - risky workload identities

This feature is in preview at the time of writing this playbook and licensing requirements apply to its usage. Risky workload identities can be the trigger to investigate a Service Principal, but can also be used to further investigate into other triggers you've identified. You can check the **Risk State** of a Service Principal using the **Identity Protection - risky workload identities** tab, or you can use Microsoft Graph API. You can also use natural language prompts to get insights on risky workload identities with [Microsoft Security Copilot in Microsoft Entra](/en-us/entra/fundamentals/copilot-security-entra-investigate-risky-apps).

![Screenshot of the Risk Detection Details portal page.](media/compromised-malicious-apps/ir-workload-identity-risk-detection-signal-portal-2.png)

![Screenshot of the Risk Detection details user interface page.](media/compromised-malicious-apps/ir-workload-identity-risk-detection-signal-portal.png)

![A sample of Service Principal Risk Detection Graph API.](media/compromised-malicious-apps/ir-sp-risk-detection-graph-sample.png)

### Check for unusual sign-in behavior

The first step of the investigation is to look for evidence of unusual authentications patterns in the usage of the Service Principal. Within the Azure portal, Azure Monitor, Microsoft Sentinel, or the Security Information and Event Management (SIEM) system of your organization's choice, look for the following in the **Service principal sign-ins** section:

- Location - is the Service Principal authenticating from locations\IP addresses that you wouldn't expect?
- Failures - 's there a large number of authentication failures for the Service Principal?
- Timestamps - are there successful authentications that are occurring at times that you wouldn't expect?
- Frequency - is there an increased frequency of authentications for the Service Principal?
- Leak Credentials - are any application credentials hard coded and published on a public source like GitHub?

If you deployed Microsoft Entra ID Identity Protection - risky workload identities, check the **Suspicious Sign-ins and Leak Credentials detections**. For more information, see [workload identity risk detentions](/en-us/azure/active-directory/identity-protection/concept-workload-identity-risk#workload-identity-risk-detections).

### Check the target resource

Within Service principal sign-ins, also check the **Resource** that the Service Principal was accessing during the authentication. It's important to get input from the application owner because they're familiar with which resources the Service Principal should be accessing.

![Screenshot of how to check the resource for Service Principal.](media/compromised-malicious-apps/ir-target-resource.png)

### Check for abnormal credential changes

Use Audit logs to get information on credential changes on applications and service principals. Filter for **Category** by **Application Management**, and **Activity** by **Update Application – Certificates and secrets management**.

- Check whether there are newly created or unexpected credentials assigned to the service principal.
- Check for credentials on Service Principal using Microsoft Graph API.
- Check both the application and associated service principal objects.
- Check any [custom role](/en-us/azure/active-directory/roles/custom-enterprise-apps) that you created or modified. Note the permissions marked below:

![Screenshot of how to check custom roles that are created or have been modified.](media/compromised-malicious-apps/ir-custom-roles-to-check.png)

If you deployed app governance in Microsoft Defender for Cloud Apps, check the Azure portal for alerts relating to the application. For more information, see [Get started with app threat detection and remediation](/en-us/defender-cloud-apps/app-governance-detect-remediate-get-started).

If you deployed Identity Protection, check the "Risk detections" report and in the user or workload identity "risk history."

![Screenshot of the Risk Detection portal user interface.](media/compromised-malicious-apps/ir-workload-identity-risk-detection-signal-portal-2.png)

If you deployed Microsoft Defender for Cloud Apps, ensure that the "Unusual addition of credentials to an OAuth app" policy is enabled, and check for open alerts.

For more information, see [Unusual addition of credentials to an OAuth app](/en-us/defender-cloud-apps/investigate-anomaly-alerts#unusual-addition-of-credentials-to-an-oauth-app).

Additionally, you can query the [servicePrincipalRiskDetections](/en-us/graph/api/identityprotectionroot-list-serviceprincipalriskdetections) and user [riskDetections APIs](/en-us/graph/api/resources/riskdetection) to retrieve these risk detections.

### Search for anomalous app configuration changes

- Check the API permissions assigned to the app to ensure that the permissions are consistent with what is expected for the app.
- Check Audit logs (filter **Activity** by **Update Application** or **Update Service Principal**).
- Confirm whether the connection strings are consistent and whether has the sign out URL has been modified.
- Confirm whether the domains in the URL are in-line with those registered.
- Determine whether anyone has added an unauthorized redirect URL.
- Confirm ownership of the redirect URI that you own to ensure it didn't expire and was claimed by an adversary.

Also, if you deployed Microsoft Defender for Cloud Apps, check the Azure portal for alerts relating to the application you are currently investigating. Not all alert policies are enabled by default for OAuth apps, so ensure that these policies are all enabled. For more information, see the [OAuth app policies](/en-us/defender-cloud-apps/app-permission-policy). You can also view information about the apps prevalence and recent activity under the **Investigation** &gt; **OAuth Apps** tab.

### Check for suspicious application roles

- You can also use the Audit logs. Filter **Activity** by **Add app role assignment to service principal**.
- Confirm whether the assigned roles have high privilege.
- Confirm whether those privileges are necessary.

### Check for unverified commercial apps

- Check whether commercial gallery (published and verified versions) applications are being used.

### Check for indications of keyCredential property information disclosure

Review your tenant for potential keyCredential property information disclosure as outlined in [CVE-2021-42306](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-42306).

To identify and remediate impacted Microsoft Entra applications associated with impacted Automation Run-As accounts, navigate to the [remediation guidance GitHub Repo](https://github.com/microsoft/aad-app-credential-tools/blob/main/azure-automation/azure-automation-runas-credential-remediation.md).

Important

If you discover evidence of compromise, it's important to take the steps highlighted in the containment and recovery sections. These steps help address the risk, but perform further investigation to understand the source of the compromise to avoid further impact and ensure bad actors are removed.

There are two primary methods of gaining access to systems via the use of applications. The first involves an application being consented to by an administrator or user, usually via a phishing attack. This method is part of initial access to a system and is often referred to as "consent phishing".

The second method involves an already compromised administrator account creating a new app for the purposes of persistence, data collection and to stay under the radar. For example, a compromised administrator could create an OAuth app with a seemingly innocuous name, avoiding detection and allowing long term access to data without the need for an account. This method is often seen in nation state attacks.

Here are some of the steps that can be taken to investigate further.

### Check Microsoft 365 Unified Audit Log (UAL) for phishing indications for the past seven days

Sometimes, when attackers use malicious or compromised applications as a means of persistence or to exfiltrate data, a phishing campaign is involved. Based on the findings from the previous steps, you should review the identities of:

- Application Owners
- Consent Admins

Review the identities for indications of phishing attacks in the last 24 hours. Increase this time span if needed to 7, 14, and 30 days if there are no immediate indications. For a detailed phishing investigation playbook, see the [Phishing Investigation Playbook](security-operations-playbook-phishing).

### Search for malicious application consents for the past seven days

To get an application added to a tenant, attackers spoof users or admins to consent to applications. To know more about the signs of an attack, see the [Application Consent Grant Investigation Playbook](security-operations-playbook-app-consent#finding-signs-of-an-attack).

### Check application consent for the flagged application

#### Check Audit logs

To see all consent grants for that application, filter **Activity** by **Consent to application**.

- Use the Microsoft Entra admin center Audit Logs
- Use Microsoft Graph to query the Audit logs

    a) Filter for a specific time frame:

```HTTP
GET https://graph.microsoft.com/v1.0/auditLogs/auditLogs/directoryAudits?&$filter=activityDateTime le 2022-01-24
```

b) Filter the Audit Logs for 'Consent to Applications' audit log entries:

```http
https://graph.microsoft.com/v1.0/auditLogs/directoryAudits?directoryAudits?$filter=ActivityType eq 'Consent to application'

"@odata.context": "https://graph.microsoft.com/v1.0/$metadata#auditLogs/directoryAudits",
"value": [
    {
        "id": "Directory_0da73d01-0b6d-4c6c-a083-afc8c968e655_78XJB_266233526",
        "category": "ApplicationManagement",
        "correlationId": "aaaa0000-bb11-2222-33cc-444444dddddd",
        "result": "success",
        "resultReason": "",
        "activityDisplayName": "Consent to application",
        "activityDateTime": "2022-03-25T21:21:37.9452149Z",
        "loggedByService": "Core Directory",
        "operationType": "Assign",
       "initiatedBy": {
            "app": null,
            "user": {
                "id": "8b3f927e-4d89-490b-aaa3-e5d4577f1234",
                "displayName": null,
                "userPrincipalName": "admin@contoso.com",
                "ipAddress": "55.154.250.91",
                "userType": null,
                "homeTenantId": null,
                "homeTenantName": null
            }
        },
        "targetResources": [
            {
                "id": "d23d38a1-02ae-409d-884c-60b03cadc989",
                "displayName": "Graph explorer (official site)",
                "type": "ServicePrincipal",
                "userPrincipalName": null,
                "groupType": null,
                "modifiedProperties": [
                    {
                        "displayName": "ConsentContext.IsAdminConsent",
                        "oldValue": null,
                        "newValue": "\"True\""
                    },
```

c) Use Log Analytics

```
AuditLogs
| where ActivityDisplayName == "Consent to application"
```

For more information, see the [Application Consent Grant Investigation Playbook](security-operations-playbook-app-consent).

#### Determine if there was suspicious end-user consent to the application

A user can authorize an application to access some data at the protected resource, while acting as that user. The permissions that allow this type of access are called "delegated permissions" or [user consent](/en-us/azure/active-directory/manage-apps/consent-and-permissions-overview#user-consent).

To find apps that are consented by users, use LogAnalytics to search the Audit logs:

```
AuditLogs
| where ActivityDisplayName == "Consent to application" and (parse_json(tostring(parse_json(tostring(TargetResources[0].modifiedProperties))[0].newValue)) <> "True")
```

#### Check Audit logs to find whether the permissions granted are too broad (tenant-wide or admin-consented)

Reviewing the permissions granted to an application or Service Principal can be a time-consuming task. Start with understanding the potentially [risky permissions](security-operations-playbook-app-consent#classifying-risky-permissions) in Microsoft Entra ID.

Now, follow the guidance on how to enumerate and review permissions in the [App consent grant investigation](security-operations-playbook-app-consent#method-2---using-powershell).

#### Check whether the permissions were granted by user identities that shouldn't have the ability to do this, or whether the actions were performed at strange dates and times

Review using Audit Logs:

```
AuditLogs
| where OperationName == "Consent to application" 
//| where parse_json(tostring(TargetResources[0].modifiedProperties))[4].displayName == "ConsentAction.Permissions"
```

You can also use the Microsoft Entra audit logs, filter by **Consent to application**. In the Audit Log details section, click **Modified Properties**, and then review the **ConsentAction.Permissions**:

![Screenshot of how to use the Microsoft Entra audit logs.](media/compromised-malicious-apps/ir-audit-log-details-consent-permissions.png)

## Containment steps

After identifying one or more applications or workload identities as either malicious or compromised, you might not immediately want to roll the credentials for this application, nor you want to immediately delete the application.

Important

Before you perform the following step, your organization must weigh up the security impact and the business impact of disabling an application. If the business impact of disabling an application is too great, then consider preparing and moving to the Recovery stage of this process.

### Disable compromised application

A typical containment strategy involves the disabling of sign-ins to the application identified, to give your incident response team or the affected business unit time to evaluate the impact of deletion or key rolling. If your investigation leads you to believe that administrator account credentials are also compromised, this type of activity should be coordinated with an eviction event to ensure that all routes to accessing the tenant are cut off simultaneously.

![Screenshot of how to disable user sign-in.](media/compromised-malicious-apps/ir-disabled-app-example.png)

You can also use the following [Microsoft Graph PowerShell](/en-us/powershell/microsoftgraph) code to disable the sign-in to the app:

```powershell
# The AppId of the app to be disabled
$appId = "{AppId}"

# Check if a service principal already exists for the app
$servicePrincipal = Get-MgServicePrincipal -Filter "appId eq '$appId'"

if ($servicePrincipal) {
   # Service principal exists already, disable it

  $ServicePrincipalUpdate =@{
    "accountEnabled" = "false"
  }
   Update-MgServicePrincipal -ServicePrincipalId $servicePrincipal.Id -BodyParameter $ServicePrincipalUpdate
   
} else {
   # Service principal does not yet exist, create it and disable it at the same time
   
   $ServicePrincipalID=@{"AppId" = $appId"accountEnabled" = "false"
   }
   
   $servicePrincipal = New-MgServicePrincipal -BodyParameter $ServicePrincipalId
   
}
```

## Recovery steps

### Remediate Service Principals

1. List all credentials assigned to the **Risky Service Principal**. The best way to do this is to perform a Microsoft Graph call using GET ~/application/{id} where ID passed is the application object ID.

    - Parse the output for credentials. The output may contain passwordCredentials or keyCredentials. Record the keyIds for all.

        ```
        "keyCredentials": [],
             "parentalControlSettings": {
                 "countriesBlockedForMinors": [],
                 "legalAgeGroupRule": "Allow"
             },
             "passwordCredentials": [
                 {
                     "customKeyIdentifier": null,
                     "displayName": "Test",
                     "endDateTime": "2021-12-16T19:19:36.997Z",
                     "hint": "7~-",
                     "keyId": "aaaaaaaa-0b0b-1c1c-2d2d-333333333333",
                     "secretText": null,
                     "startDateTime": "2021-06-16T18:19:36.997Z"
                 }
             ],
        ```
2. Add a new (x509) certificate credential to the application object using the application addKey API.

    ```
    POST ~/applications/{id}/addKey
    ```
3. Immediately remove all old credentials. For each old password credential, remove it by using:

    ```
    POST ~/applications/{id}/removePassword
    ```

    For each old key credential, remove it by using:

    ```
    POST ~/applications/{id}/removeKey
    ```
4. Remediate all Service Principals associated with the application. Follow this step if your tenant hosts/registers a multitenant application, and/or registers multiple service principals associated to the application. Perform similar steps to what is previously listed:

- GET ~/servicePrincipals/{id}
- Find passwordCredentials and keyCredentials in the response, record all old keyIds
- Remove all old password and key credentials. Use:

    ```
    POST ~/servicePrincipals/{id}/removePassword and POST ~/servicePrincipals/{id}/removeKey for this, respectively.
    ```

### Remediate affected Service Principal resources

Remediate KeyVault secrets that the Service Principal has access to by rotating them, in the following priority:

- Secrets directly exposed with [GetSecret](/en-us/java/api/com.microsoft.azure.keyvault.keyvaultclient.getsecret) calls.
- The rest of the secrets in exposed KeyVaults.
- The rest of the secrets across exposed subscriptions.

For more information, see [Interactively removing and rolling over the certificates and secrets of a Service Principal or Application](https://github.com/microsoft/azureadtoolkit#interactively-removing-and-rolling-over-the-certificates-and-secrets-of-a-service-principal-or-application).

For Microsoft Entra SecOps guidance on applications, see [Microsoft Entra security operations guide for Applications](/en-us/azure/active-directory/fundamentals/security-operations-applications).

In order of priority, this scenario would be:

- Update Graph PowerShell cmdlets (Add/Remove ApplicationKey + ApplicationPassword) doc to include examples for credential roll-over.
- Add custom cmdlets to Microsoft Graph PowerShell that simplifies this scenario.

### Disable or delete malicious applications

An application can either be disabled or deleted. To disable the application, under **Enabled for users to sign in**, move the toggle to **No**.

You can delete the application, either temporarily or permanently, in the Azure portal or through the Microsoft Graph API. When you soft delete, the application can be recovered up to 30 days after deletion.

```
DELETE /applications/{id}
```

To permanently delete the application, use this Microsoft Graph API call:

```
DELETE /directory/deletedItems/{id}
```

If you disable or if you soft delete the application, set up monitoring in Microsoft Entra audit logs to learn if the state changes back to enabled or recovered.

**Logging for enabled:**

- **Service** - Core Directory
- **Activity Type** - Update Service Principal
- **Category** - Application Management
- **Initiated by (actor)** - UPN of actor
- **Targets** - App ID and Display Name
- **Modified Properties** - Property Name = account enabled, new value = true

**Logging for recovered:**

- **Service** - Core Directory
- **Activity Type** - Add Service Principal
- **Category** - Application Management
- **Initiated by (actor)** - UPN of actor
- **Targets** - App ID and Display Name
- **Modified Properties** - Property name = account enabled, new value = true

Note

Microsoft globally disables applications found to be violating its Terms of Service. In those cases, these applications show `DisabledDueToViolationOfServicesAgreement` on the `disabledByMicrosoftStatus` property on the related [application](/en-us/graph/api/resources/application) and [service principal](/en-us/graph/api/resources/serviceprincipal) resource types in Microsoft Graph. To prevent them from being instantiated in your organization again in the future, you can't delete these objects.

### Implement Identity Protection for workload identities

Microsoft detects risk on workload identities across sign-in behavior and offline indicators of compromise.

For more information, see [Securing workload identities with Identity Protection](/en-us/azure/active-directory/identity-protection/concept-workload-identity-risk).

These alerts appear in the Identity Protection portal and can be exported into SIEM tools through [Diagnostic Settings](/en-us/azure/active-directory/identity-protection/howto-export-risk-data) or the [Identity Protection APIs](/en-us/graph/api/resources/identityprotection-overview?view=graph-rest-1.0&amp;preserve-view=true).

![Screenshot of how to review risks and alerts in the Identity Protection portal.](media/compromised-malicious-apps/ir-playbook-workload-identity-detections.png)

### Conditional Access for risky workload identities

Conditional Access allows you to block access for specific accounts that you designate when Identity Protection marks them as “at risk.” The enforcement through Conditional Access is currently limited to single-tenant applications only.

![Screenshot of how to control user access based on conditional access policy.](media/compromised-malicious-apps/ir-risk-based-ca-policy-s.png)

For more information, see [Conditional Access for workload identities](/en-us/azure/active-directory/conditional-access/workload-identity).

### Implement application risk policies

#### Review user consent settings

Review the user consent settings under **Microsoft Entra ID** &gt; **Enterprise applications** &gt; **Consent and permissions** &gt; **User consent settings**.

![Screenshot of how to allow user consent for apps.](media/compromised-malicious-apps/ir-user-consent-settings.png)

To review configuration options, see [Configure how users consent to apps](/en-us/azure/active-directory/manage-apps/configure-user-consent?tabs=azure-portal).

#### Implement admin consent flow

When an application developer directs users to the admin consent endpoint with the intent to give consent for the entire tenant, it's known as admin consent flow. To ensure the admin consent flow works properly, application developers must list all permissions in the RequiredResourceAccess property in the application manifest.

Most organizations disable the ability for their users to consent to applications. To give users the ability to still request consent for applications and have administrative review capability, it's recommended to implement the admin consent workflow. Follow the [admin consent workflow steps](/en-us/azure/active-directory/manage-apps/configure-admin-consent-workflow) to configure it in your tenant.

For high privileged operations such as admin consent, have a privileged access strategy defined in our [guidance](/en-us/security/privileged-access-workstations/privileged-access-strategy).

### Review risk-based step-up consent settings

Risk-based step-up consent helps reduce user exposure to malicious apps. For example, consent requests for newly registered multitenant apps that are not publisher verified and require non-basic permissions are considered risky. If a risky user consent request is detected, the request requires a "step-up" to admin consent instead. This step-up capability is enabled by default, but it results in a behavior change only when user consent is enabled.

Make sure it's enabled in your tenant and review the configuration settings outlined [here](/en-us/azure/active-directory/manage-apps/configure-risk-based-step-up-consent).

## References

- [Incident Response Playbooks](security-operations-incident-response-playbooks)
- [App consent grant](security-operations-playbook-app-consent)
- [Microsoft Entra ID Protection risks](/en-us/azure/active-directory/identity-protection/concept-identity-protection-risks)
- [Microsoft Entra security monitoring guide](/en-us/azure/active-directory/fundamentals/security-operations-introduction)
- [Application auditing concepts](/en-us/azure/active-directory/fundamentals/security-operations-applications)
- [Configure how users consent to applications](/en-us/azure/active-directory/manage-apps/configure-user-consent)
- [Configure the admin consent workflow](/en-us/azure/active-directory/manage-apps/configure-admin-consent-workflow)
- [Unusual addition of credentials to an OAuth app](/en-us/defender-cloud-apps/investigate-anomaly-alerts#unusual-addition-of-credentials-to-an-oauth-app)
- [Securing workload identities with Identity Protection](/en-us/azure/active-directory/identity-protection/concept-workload-identity-risk)
- [Holistic compromised identity signals from Microsoft](https://techcommunity.microsoft.com/t5/microsoft-entra-azure-ad-blog/holistic-compromised-identity-signals-from-microsoft/ba-p/2365683)

## Additional incident response playbooks

Examine guidance for identifying and investigating these additional types of attacks:

- [Phishing](security-operations-playbook-phishing)
- [Password spray](security-operations-playbook-password-spray)
- [App consent grant](security-operations-playbook-app-consent)

## Incident response resources

- [Overview](security-adoption-discipline-security-operations-incidents) for Microsoft security products and resources for new-to-role and experienced analysts
- [Prepare for incident response](security-operations-incident-response-readiness) for your Security Operations Center (SOC)
- [Microsoft Defender XDR](/en-us/microsoft-365/security/defender/incidents-overview) incident response
- [Microsoft Defender for Cloud (Azure)](/en-us/azure/defender-for-cloud/managing-and-responding-alerts)
- [Microsoft Sentinel](/en-us/azure/sentinel/investigate-cases) incident response
- [Microsoft Incident Response team guide shares best practices for security teams and leaders](https://www.microsoft.com/security/blog/2023/12/11/new-microsoft-incident-response-team-guide-shares-best-practices-for-security-teams-and-leaders/)
- [Microsoft Incident Response guides help security teams analyze suspicious activity](https://www.microsoft.com/security/blog/2024/01/17/new-microsoft-incident-response-guides-help-security-teams-analyze-suspicious-activity/)