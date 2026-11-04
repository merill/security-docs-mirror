---
layout: Conceptual
title: Prerequisite work for implementing Zero Trust identity and device access policies | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/zero-trust-identity-device-access-policies-prerequisite
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: chrisda
author: chrisda
description: This article describes the prerequisites you need to meet to use Zero Trust identity and device access policies and configurations.
ms.subservice: zero-trust
manager: dansimp
ms.service: security
ms.topic: checklist
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- m365-security
- m365solution-identitydevice
- m365solution-scenario
- zerotrust-solution
- tier2
ms.date: 2025-03-10T00:00:00.0000000Z
locale: en-us
document_id: 9084e978-793d-31de-fe8c-6e4bb37113f7
document_version_independent_id: 9084e978-793d-31de-fe8c-6e4bb37113f7
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/zero-trust-identity-device-access-policies-prerequisite.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/zero-trust-identity-device-access-policies-prerequisite
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/zero-trust-identity-device-access-policies-prerequisite.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
platformId: ac8490c3-ab5e-36c5-b09d-9ddfc9cabcaf
---

# Prerequisite work for implementing Zero Trust identity and device access policies | Microsoft Learn

This article describes the prerequisites admins must meet to use recommended Zero Trust identity and device access policies, and to use Conditional Access. It also discusses the recommended defaults for configuring client platforms for the best single sign-on (SSO) experience.

## Prerequisites

Before using the Zero Trust identity and device access policies that are recommended, your organization needs to meet prerequisites. The requirements are different for the various identity and authentication models listed:

- Cloud-only
- Hybrid with password hash sync (PHS) authentication
- Hybrid with pass-through authentication (PTA)
- Federated

The following table details the prerequisite features and their configuration that apply to all identity models, except where noted.

| Configuration | Exceptions | Licensing |
| --- | --- | --- |
| [Configure password hash synchronization (PHS)](/en-us/entra/identity/hybrid/connect/how-to-connect-password-hash-synchronization). This feature must be enabled to detect leaked credentials and to act on them for risk-based Conditional Access. This configuration is required regardless of whether your organization uses federated authentication. | Cloud-only | Microsoft 365 E3 or E5 |
| [Enable seamless single sign-on](/en-us/entra/identity/hybrid/connect/how-to-connect-sso) to automatically sign in users on their organization devices connected to your organization network. | Cloud-only and federated | Microsoft 365 E3 or E5 |
| [Configure network locations](/en-us/entra/identity/conditional-access/concept-assignment-network). Microsoft Entra ID Protection collects and analyzes all available session data to generate a risk score. We recommend you specify your organization's public IP ranges for your network in the Microsoft Entra ID named locations configuration. Traffic from these ranges gets a reduced risk score, and traffic from outside these ranges gets a higher risk score. |  | Microsoft 365 E3 or E5 |
| [Register all users for self-service password reset (SSPR) and multifactor authentication (MFA)](/en-us/entra/identity/authentication/concept-registration-mfa-sspr-combined). We recommend you do this step ahead of time. Microsoft Entra ID Protection uses Microsoft Entra multifactor authentication for added security verification. For the best sign-in experience, we recommend using the [Microsoft Authenticator app](https://support.microsoft.com/account-billing/351498fc-850a-45da-b7b6-27e523b8702a) and the Microsoft Company Portal app on devices. Users can install these apps from the app store for their device platform. |  | Microsoft 365 E3 or E5 |
| [Plan your Microsoft Entra hybrid join implementation](/en-us/entra/identity/devices/hybrid-join-plan). Conditional Access verifies devices connecting to apps are domain-joined or compliant. To support this requirement on Windows computers, the device must be registered with Microsoft Entra ID. This article discusses how to configure automatic device registration. | Cloud-only | Microsoft 365 E3 or E5 |
| **Prepare your support team**. Have a plan for users that can't do MFA. For example, add them to a policy exclusion group, or register new MFA information for them. If you make security-sensitive exceptions, verify the user is actually making the request. Requiring managers to help with the approval for users is an effective step. |  | Microsoft 365 E3 or E5 |
| [Configure password writeback to on-premises Active Directory](/en-us/entra/identity/authentication/tutorial-enable-sspr). Password writeback allows Microsoft Entra ID to require that users change their on-premises passwords when a high-risk account compromise is detected. You can enable this feature using Microsoft Entra Connect in one of two ways: <br>- Enable **Password Writeback** on the optional features page of Microsoft Entra Connect setup.<br>- Enable it via Windows PowerShell. | Cloud-only | Microsoft 365 E3 or E5 |
| [Configure Microsoft Entra password protection](/en-us/entra/identity/authentication/concept-password-ban-bad). Microsoft Entra Password Protection detects and blocks known weak passwords and their variants, and can also block other weak terms that are specific to your organization. Default global banned password lists are automatically applied to all users in a Microsoft Entra organization. You can define other entries in a custom banned password list. When users change or reset their passwords, these banned password lists are checked to enforce the use of strong passwords. |  | Microsoft 365 E3 or E5 |
| [Enable Microsoft Entra ID Protection](/en-us/entra/id-protection/overview-identity-protection). Microsoft Entra ID Protection enables you to detect potential vulnerabilities affecting your organization's identities and configure an automated remediation policy to Low, Medium, and High sign-in risk and user risk. |  | Microsoft 365 E5 or Microsoft 365 E3 with the E5 Security add-on |
| [Enable continuous access evaluation](/en-us/entra/identity/conditional-access/concept-continuous-access-evaluation) for Microsoft Entra ID. Continuous access evaluation proactively terminates active user sessions and enforces organization policy changes in near real-time. |  | Microsoft 365 E3 or E5 |

## Recommended client configurations

This section describes the recommended default platform client configurations for the best SSO experience, and the technical prerequisites for Conditional Access.

### Windows devices

We recommend Windows 11 or Windows 10 (version 2004 or later), as Azure is designed to provide the smoothest SSO experience possible for both on-premises and Microsoft Entra ID. Configure organization-owned devices using either of the following options:

- Join Microsoft Entra ID directly.
- Configure on-premises Active Directory domain-joined devices to [automatically and silently register with Microsoft Entra ID](/en-us/entra/identity/devices/hybrid-join-plan)

For personal (bring your own device (BYOD)) Windows devices, users can use **Add work or school account**. Google Chrome users on Windows 11 or Windows 10 devices need to [install an extension](https://chromewebstore.google.com/detail/microsoft-single-sign-on/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) to get the same smooth sign-in experience as Microsoft Edge users.

### iOS/iPadOS devices

We recommend installing the [Microsoft Authenticator app](https://support.microsoft.com/account-billing/351498fc-850a-45da-b7b6-27e523b8702a) on user devices before deploying Conditional Access or MFA policies. If you can't, install the app in the following scenarios:

- When users are asked to register their device with Microsoft Entra ID by adding a work or school account.
- When users install the Intune company portal app to enroll their device into management.

The request depends on the configured Conditional Access policy.

### Android devices

We recommend users install the [Intune Company Portal app](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and [Microsoft Authenticator app](https://support.microsoft.com/account-billing/351498fc-850a-45da-b7b6-27e523b8702a) before Conditional Access policies are deployed or during specific authentication attempts. After app installation, users might be asked to register with Microsoft Entra ID or enroll their device with Intune, depending on the configured Conditional Access policy.

We also recommend that organization-owned devices support Android for Work or Samsung Knox to allow mail account management and protection by Intune mobile device management (MDM) policies.

### Recommended email clients

The email clients in the following table support modern authentication and Conditional Access:

| Platform | Client | Version/Notes |
| --- | --- | --- |
| **Windows** | Outlook | 2016 or later [Required updates](/en-us/officeupdates/outlook-updates-msi) |
| **iOS/iPadOS** | Outlook for iOS | [Latest](https://apps.apple.com/app/microsoft-outlook/id951937596) |
| **Android** | Outlook for Android | [Latest](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook) |
| **macOS** | Outlook | 2016 or later |
| **Linux** | Not supported |  |

### Recommended client platforms when securing documents

We recommend the client apps in the following table when a secure documents policy is applied:

| Platform | Word/Excel/PowerPoint | OneNote | OneDrive app | SharePoint app | [OneDrive sync client](/en-us/sharepoint/enable-conditional-access) |
| --- | --- | --- | --- | --- | --- |
| Windows 11 or Windows 10 | Supported | Supported | N/A | N/A | Supported |
| Android | Supported | Supported | Supported | Supported | N/A |
| iOS/iPadOS | Supported | Supported | Supported | Supported | N/A |
| macOS | Supported | Supported | N/A | N/A | Not supported |
| Linux | Not supported | Not supported | Not supported | Not supported | Not supported |

### Microsoft 365 client support

For more information about client support in Microsoft 365, see [Deploy your identity infrastructure for Microsoft 365](/en-us/microsoft-365/enterprise/deploy-identity-solution-overview).

## Protecting administrator accounts

For Microsoft 365 E3 or E5 or with separate Microsoft Entra ID P1 or P2 licenses, you can require phishing-resistant MFA for administrator accounts with a manually created Conditional Access policy. For more information, see [Conditional Access: Require phishing-resistant MFA for administrators](/en-us/entra/identity/conditional-access/policy-admin-phish-resistant-mfa).

For editions of Microsoft 365 or Office 365 that don't support Conditional Access, you can enable [security defaults](/en-us/entra/fundamentals/security-defaults) to require MFA for all accounts.

Here are some other recommendations:

- Use [Microsoft Entra Privileged Identity Management](/en-us/entra/id-governance/privileged-identity-management/pim-getting-started) to reduce the number of persistent administrative accounts.
- [Use privileged access management](/en-us/purview/privileged-access-management) to protect your organization from breaches that might use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.
- Create and use separate accounts that are assigned [Microsoft 365 administrator roles](/en-us/entra/identity/role-based-access-control/manage-roles-portal)*only for administration*. Admins should have their own user account for regular use. They should use an administrative account only when necessary to complete a task associated with their role or job function.
- Follow [best practices](/en-us/entra/identity/role-based-access-control/best-practices) for securing privileged accounts in Microsoft Entra ID.