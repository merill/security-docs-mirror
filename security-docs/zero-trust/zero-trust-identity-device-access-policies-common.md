---
layout: Conceptual
title: Zero Trust Identity and Device Access Policies for Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/zero-trust-identity-device-access-policies-common
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn about Zero Trust identity and device access policies for Microsoft 365, including configurations and benefits for secure deployments.
ms.subservice: zero-trust
ms.service: security
ms.topic: best-practice
ms.reviewer: martincoetzer
ms.date: 2025-06-18T00:00:00.0000000Z
locale: en-us
document_id: 5e99fe3e-6e2c-0cee-45d1-ec8fdbcb2891
document_version_independent_id: 5e99fe3e-6e2c-0cee-45d1-ec8fdbcb2891
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/zero-trust-identity-device-access-policies-common.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/zero-trust-identity-device-access-policies-common
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/zero-trust-identity-device-access-policies-common.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
platformId: 4fc1ca99-ba00-67c6-ea6b-37d16c5f1408
---

# Zero Trust Identity and Device Access Policies for Microsoft 365 | Microsoft Learn

Many organizations have questions when deploying Microsoft 365 in a secure fashion. The Conditional Access, app protection, and device compliance policies in this article are based on Microsoft's recommendations and the three guiding principles of [Zero Trust](zero-trust-overview).

Organizations can use these policies as is or customize them to fit their needs. Test your policies in a nonproduction environment to identify potential effects and communicate them to users before rolling them out to production. Testing is critical to identify and communicate possible effects to users.

We group these policies into three protection levels based on where you are on your deployment journey:

- **Starting point**: Basic controls that introduce multifactor authentication, secure password changes, and Intune app protection policies for mobile devices.
- **Enterprise**: Enhanced controls that introduce device compliance.
- **Specialized security**: Policies that require multifactor authentication every time for specific data sets or users.

This diagram shows the protection levels for each policy and the types of devices they apply to:

[![A diagram showing common identity and device policies that support Zero Trust principles.](media/microsoft-365-policies-configurations/identity-device-access-policies-three-tiers.svg)](media/microsoft-365-policies-configurations/identity-device-access-policies-three-tiers.svg#lightbox)

You can download this diagram as a [PDF](https://download.microsoft.com/download/3d22de2e-38d8-4119-9f26-f6122b567909/zero-trust-id-and-device-access-policies-contoso.pdf) file or an editable [Visio](https://download.microsoft.com/download/8/b/2/8b23ab16-a3de-4b4e-b8a0-95b393cfbcee/zero-trust-id-and-device-access-policies-contoso.vsdx) file.

Tip

Require multifactor authentication (MFA) for users before enrolling devices in Intune to confirm the device is with the intended user. MFA is on by default thorough [security defaults](/en-us/entra/fundamentals/security-defaults#enforced-security-policies), or you can use Conditional Access policies to [require MFA for all users](/en-us/entra/identity/conditional-access/policy-all-users-mfa-strength).

Devices must be enrolled in Intune before you can enforce device compliance policies.

## Prerequisites

### Permissions

The following permissions in Microsoft Entra are required:

- **Manage Conditional Access policies**: The [Conditional Access Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference#conditional-access-administrator) role.
- **Manage app protection and device compliance policies**: The [Intune Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference#intune-administrator) role.
- **View configurations only**: The [Security Reader](/en-us/entra/identity/role-based-access-control/permissions-reference#security-reader) role.

For more information about roles and permissions in Microsoft Entra, see [Overview of role-based access control in Microsoft Entra ID](/en-us/entra/identity/role-based-access-control/custom-overview).

### User registration

Ensure users register for MFA before they're required to use it. If your licenses include Microsoft Entra ID P2, you can use the [MFA registration policy within Microsoft Entra ID Protection](/en-us/entra/id-protection/howto-identity-protection-configure-mfa-policy) to require users to register. We provide [communication templates](https://aka.ms/mfatemplates) that you can download and customize to promote user registration.

### Groups

All Microsoft Entra groups used in these recommendations must be Microsoft 365 Groups, **not** security groups. This requirement is important for the deployment of sensitivity labels to secure documents in Microsoft Teams and SharePoint. For more information, see [Learn about groups and access rights in Microsoft Entra ID](/en-us/entra/fundamentals/concept-learn-about-groups#group-types).

### Assigning policies

You can assign Conditional Access policies to users, groups, and administrator roles. You can assign Intune app protection and device compliance policies to *groups only*. Before you configure your policies, identify who should be included and excluded. Typically, starting point protection level policies apply to everyone in the organization.

The following table describes example group assignments and exclusions for MFA after users complete user registration:

| - | Microsoft Entra Conditional Access policy | Include | Exclude |
| --- | --- | --- | --- |
| **Starting point** | Require multifactor authentication for **Medium** or **High** sign-in risk | *All users* | - Emergency access accounts<br>- Conditional Access exclusion group |
| **Enterprise** | Require multifactor authentication for **Low**, **Medium**, or **High** sign-in risk | *Executive staff group* | - Emergency access accounts<br>- Conditional Access exclusion group |
| **Specialized security** | Require multifactor authentication **always** | *Top Secret Project Buckeye group* | - Emergency access accounts<br>- Conditional Access exclusion group |

Tip

Apply higher levels of protection to users and groups carefully. Security's goal isn't to add unnecessary friction to the user experience. For example, members of the *Top Secret Project Buckeye group* are required to use MFA every time they sign in, even if they aren't working on the specialized content for their project. Excessive security friction can lead to fatigue. Enable [phishing-resistant authentication methods](/en-us/entra/identity/authentication/concept-authentication-passwordless) (for example, Windows Hello for Business or FIDO2 security keys) to help reduce the friction caused by security controls.

### Emergency access accounts

Every organization needs at least one emergency access account that is monitored for use and excluded from policies. Larger organizations might require more accounts. **These accounts are only used in case all other administrator accounts and authentication methods become locked out or otherwise unavailable**. For more information, see [Manage emergency access accounts in Microsoft Entra ID](/en-us/entra/identity/role-based-access-control/security-emergency-access).

### Excluding users

We recommend crating a Microsoft Entra group for Conditional Access exclusions. This group gives you a means to provide access to a user while you troubleshoot access issues. Features like access reviews in Microsoft Entra ID Governance help you [manage users excluded from Conditional Access policies](/en-us/entra/id-governance/conditional-access-exclusion)

Warning

We recommend an exclusion group as a temporary solution only. Continuously monitor this group for changes and ensure it's used only for its intended purpose.

Use the following steps to add an exclusion group to existing policies.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Conditional Access Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference#conditional-access-administrator).
2. Browse to **Protection** &gt; **Conditional Access** &gt; **Policies**.
3. Select an existing policy by clicking on the name.
4. Under **Assignments**, select **Users or workload identities**. a. Under **Exclude**, select **Users and groups**, and choose the following identities:
    - **Users**: Your emergency access accounts.
    - **Groups**: Your Conditional Access exclusion group. b. Select **Select**.
5. Make any other modifications.
6. Select **Save**.

### Excluding applications

We recommend creating a baseline multifactor authentication policy targeting all users and all resources (without any application exclusions), like the one explained in [Require multifactor authentication for all users](/en-us/entra/identity/conditional-access/policy-all-users-mfa-strength). Excluding certain applications might have unintended security and usability consequences described in [Conditional Access behavior when an all resources policy has an app exclusion](/en-us/entra/identity/conditional-access/concept-conditional-access-cloud-apps#conditional-access-behavior-when-an-all-resources-policy-has-an-app-exclusion). Applications, like Microsoft 365 and Microsoft Teams, depend on multiple services making behavior unpredictable when exclusions are made.

Important

**Enforcement change rolling out March–June 2026:** Conditional Access policies that target *All resources* are enforced for sign-ins requesting only [OIDC scopes](/en-us/entra/identity-platform/scopes-oidc#openid-connect-scopes) or a [limited set of directory scopes](/en-us/entra/identity/conditional-access/concept-conditional-access-cloud-apps#legacy-conditional-access-behavior-when-an-all-resources-policy-has-a-resource-exclusion), even when resource exclusions are present. Users in affected tenants might receive Conditional Access challenges (such as MFA or device compliance) where previously they were allowed access without enforcement. Review any *All resources* policies that include resource exclusions and validate impacted sign-in flows. For more information, see [Conditional Access behavior change for all resources policies with resource exclusions](/en-us/entra/identity/conditional-access/concept-conditional-access-cloud-apps#new-conditional-access-behavior-when-an-all-resources-policy-has-a-resource-exclusion).

## Deployment

We recommend implementing the starting point policies in the order listed in the following table. You can implement the MFA policies for enterprise and specialized security levels of protection at any time.

**Starting point**:

| Policy | More information | Licensing |
| --- | --- | --- |
| Require MFA when sign-in risk is *Medium* or *High* | Require MFA only when risk is detected by Microsoft Entra ID Protection. | - Microsoft 365 E5<br>- Microsoft 365 E3 with the E5 Security add-on<br>- Microsoft 365 with EMS E5<br>- Individual Microsoft Entra ID P2 licenses |
| Block clients that don't support modern authentication | Clients that don't use modern authentication can bypass Conditional Access policies, so it's important to block them. | Microsoft 365 E3 or E5 |
| High risk users must change password | Force users to change their password when signing in if high-risk activity is detected for their account. | - Microsoft 365 E5<br>- Microsoft 365 E3 with the E5 Security add-on<br>- Microsoft 365 with EMS E5<br>- Individual Microsoft Entra ID P2 licenses |
| Apply Application Protection Policies (APP) for data protection | One Intune APP per mobile device platform (Windows, iOS/iPadOS, and Android). | Microsoft 365 E3 or E5 |
| Require approved apps and app protection policies | Enforces app protection policies for mobile devices using iOS, iPadOS, or Android. | Microsoft 365 E3 or E5 |

**Enterprise**:

| Policy | More information | Licensing |
| --- | --- | --- |
| Require MFA when sign-in risk is **Low**, **Medium**, or **High** | Require MFA only when risk is detected by Microsoft Entra ID Protection. | - Microsoft 365 E5<br>- Microsoft 365 E3 with the E5 Security add-on<br>- Microsoft 365 with EMS E5<br>- Individual Microsoft Entra ID P2 licenses |
| Define device compliance policies | Set minimum configuration requirements. One policy for each platform. | Microsoft 365 E3 or E5 |
| Require compliant PCs and mobile devices | Enforces the configuration requirements for devices accessing your organization | Microsoft 365 E3 or E5 |

**Specialized security**:

| Policy | More information | Licensing |
| --- | --- | --- |
| Require MFA **Always** | Users are required to do MFA anytime they sign in to services in the organization. | Microsoft 365 E3 or E5 |

## App protection policies

[App protection policies](/en-us/intune/intune-service/apps/app-protection-policy) specify allowed apps and the actions they can take with your organization's data. Although there are many policies to choose from, the following list describes our recommended baselines.

Tip

Although we provide three templates, most organizations should choose Level 2 (maps to starting point or enterprise level security) and Level 3 (maps to specialized security).

- [Level 1 enterprise basic data protection](/en-us/intune/intune-service/apps/app-protection-framework#level-1-enterprise-basic-data-protection): We recommend this configuration as the minimum data protection for enterprise devices.
- **[Level 2 enterprise enhanced data protection](/en-us/intune/intune-service/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)**: We recommend this configuration for devices that access sensitive data or confidential information. This configuration applies to most mobile users who access work or school data. Some of the controls might affect the user experience.
- **[Level 3 enterprise high data protection](/en-us/intune/intune-service/apps/app-protection-framework#level-3-enterprise-high-data-protection)**: We recommend this configuration in the following scenarios:

    - Organizations with larger or more sophisticated security teams.
    - Devices used by specific users or groups who are at uniquely high risk. For example, users who handle highly sensitive data where unauthorized disclosure would cause considerable loss to the organization

    Organizations likely targeted by well-funded and sophisticated attackers should aspire to this configuration.

Create a new app protection policy for each device platform within Microsoft Intune (iOS/iPadOS and Android) using the data protection framework settings by using either of the following methods:

- Manually create the policies by following the steps in [How to create and deploy app protection policies with Microsoft Intune](/en-us/intune/intune-service/apps/app-protection-policies).
- Import the sample Intune App Protection Policy Configuration Framework JSON templates with [Intune's PowerShell scripts](https://github.com/microsoftgraph/powershell-intune-samples).

## Device compliance policies

Intune device compliance policies define the requirements for devices to be compliant. You need to create a policy for each PC, phone, or tablet platform. The following sections describe the recommendations for the following platforms:

- Android
- iOS/iPadOS
- Windows 10 and later

### Create device compliance policies

Follow these steps to create device compliance policies:

1. Sign in to the [Microsoft Intune admin center](https://intune.microsoft.com/) as an [Intune Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference#intune-administrator).
2. Browse to **Devices** &gt; **Compliance** &gt; **Create policy**.

For step-by-step guidance, see [Create a compliance policy in Microsoft Intune](/en-us/intune/intune-service/protect/create-compliance-policy).

### Enrollment and compliance settings for iOS/iPadOS

iOS/iPadOS supports several enrollment scenarios, two of which are covered by this framework:

- [Device enrollment for personally owned devices](/en-us/intune/intune-service/fundamentals/deployment-guide-enrollment-ios-ipados#byod-user-and-device-enrollment): Personally owned devices (also known as bring your own device or BYOD) that are also used for work.
- [Automated device enrollment for corporate-owned devices](/en-us/intune/intune-service/enrollment/device-enrollment-program-enroll-ios): Organization-owned devices that are associated with a single user, and are used exclusively for work.

Tip

As previously described, Level 2 maps to starting point or enterprise level security, and Level 3 maps to specialized security. For more information, see [Zero Trust identity and device access configurations](zero-trust-identity-device-access-policies-overview).

#### Compliance settings for personally enrolled devices

- [Personal basic security (Level 1)](/en-us/mem/intune-service/protect/ios-ipados-personal-device-security-configurations#personal-basic-security-level-1): We recommend this configuration as the minimum security for personal devices that access work or school data. You achieve this configuration by enforcing password policies, device lock characteristics, and disabling certain device functions (for example, untrusted certificates).
- **[Personal enhanced security (Level 2)](/en-us/mem/intune-service/protect/ios-ipados-personal-device-security-configurations#personal-enhanced-security-level-2)**: We recommend this configuration for devices that access sensitive data or confidential information. This configuration enables data sharing controls. This configuration applies to most mobile users who access work or school data.
- **[Personal high security (Level 3)](/en-us/mem/intune-service/protect/ios-ipados-personal-device-security-configurations#personal-high-security-level-3)**: We recommend this configuration for devices used by specific users or groups who are at uniquely high risk. For example, users who handle highly sensitive data where unauthorized disclosure would cause considerable loss to the organization. This configuration enables stronger password policies, disables certain device functions, and enforces extra data transfer restrictions.

#### Compliance settings for automated device enrollment

- [Supervised basic security (Level 1)](/en-us/mem/intune-service/protect/ios-ipados-supervised-device-security-configurations#supervised-basic-security-level-1): We recommend this configuration as the minimum security for enterprise devices that access work or school data. You achieve this configuration by enforcing password policies, device lock characteristics, and disabling certain device functions (for example, untrusted certificates).
- **[Supervised enhanced security (Level 2)](/en-us/mem/intune-service/protect/ios-ipados-supervised-device-security-configurations#supervised-enhanced-security-level-2)**: We recommend this configuration for devices that access sensitive data or confidential information. This configuration enables data sharing controls and blocks access to USB devices. This configuration is applicable to most mobile users accessing work or school data on a device.
- **[Supervised high security (Level 3)](/en-us/mem/intune-service/protect/ios-ipados-supervised-device-security-configurations#supervised-high-security-level-3)** : We recommend this configuration for devices used by specific users or groups who are at uniquely high risk. For example, users who handle highly sensitive data where unauthorized disclosure would cause considerable loss to the organization. This configuration enables stronger password policies, disables certain device functions, enforces extra data transfer restrictions, and requires apps to be installed through Apple's volume purchase program.

### Enrollment and compliance settings for Android

Android Enterprise supports several enrollment scenarios, two of which are covered by this framework:

- [Android Enterprise work profile](/en-us/intune/intune-service/enrollment/android-work-profile-enroll): Personally owned devices (also known as bring your own device or BYOD) that are also used for work. Policies controlled by the IT department ensure that work data can't be transferred into the personal profile.
- [Android Enterprise fully managed devices](/en-us/intune/intune-service/enrollment/android-fully-managed-enroll): Organization-owned devices that are associated with a single user, and are used exclusively for work.

The Android Enterprise security configuration framework is organized into several distinct configuration scenarios that provide guidance for work profile and fully managed scenarios.

Tip

As previously described, Level 2 maps to starting point or enterprise level security, and Level 3 maps to specialized security. For more information, see [Zero Trust identity and device access configurations](zero-trust-identity-device-access-policies-overview).

#### Compliance settings for Android Enterprise work profile devices

- There's no basic security (Level 1) offering for personally owned work profile devices. The available settings don't justify a difference between Level 1 and Level 2.
- **[Work profile enhanced security (Level 2)](/en-us/intune/intune-service/protect/android-personally-owned-security-configurations#personally-owned-work-profile-enhanced-security-level-2)**: We recommend this configuration as the minimum security for personal devices that access work or school data. This configuration introduces password requirements, separates work and personal data, and validates Android device attestation.
- **[Work profile high security (Level 3)](/en-us/intune/intune-service/protect/android-personally-owned-security-configurations#personally-owned-work-profile-high-security-level-3)**: We recommend this configuration for devices used by specific users or groups who are at uniquely high risk. For example, users who handle highly sensitive data where unauthorized disclosure would cause considerable loss to the organization. This configuration introduces mobile threat defense or Microsoft Defender for Endpoint, sets the minimum Android version, enables stronger password policies, and further separates work and personal data.

#### Compliance settings for Android Enterprise fully managed devices

- [Fully managed basic security (Level 1)](/en-us/intune/intune-service/protect/android-fully-managed-security-configurations#fully-managed-basic-security-level-1): We recommend this configuration as the minimum security for an enterprise device. This configuration applies to most mobile users who work or school data. This configuration introduces password requirements, sets the minimum Android version, and enables specific device restrictions.
- **[Fully managed enhanced security (Level 2)](/en-us/intune/intune-service/protect/android-fully-managed-security-configurations#fully-managed-enhanced-security-level-2)**: We recommend this configuration for devices that access sensitive data or confidential information. This configuration enables stronger password policies and disables user/account capabilities.
- **[Fully managed high security (Level 3)](/en-us/intune/intune-service/protect/android-fully-managed-security-configurations#fully-managed-high-security-level-3)**: We recommend this configuration for devices used by specific users or groups who are at uniquely high risk. For example, users who handle highly sensitive data where unauthorized disclosure would cause considerable loss to the organization. This configuration increases the minimum Android version, introduces mobile threat defense or Microsoft Defender for Endpoint, and enforces extra device restrictions.

### Recommended compliance settings for Windows 10 and later

Configure the following settings as described in [Device Compliance settings for Windows 10/11 in Intune](/en-us/intune/intune-service/protect/compliance-policy-create-windows). These settings align with the principles outlined in [Zero Trust identity and device access configurations](zero-trust-identity-device-access-policies-overview).

- **Device health** &gt; **Windows Health Attestation Service evaluation rules**:

    | Property | Value |
    | --- | --- |
    | Require BitLocker | Require |
    | Require Secure Boot to be enabled on the device | Require |
    | Require code integrity | Require |
- **Device properties** &gt; **Operating System Version**: Enter appropriate values for operating system versions based on your IT and security policies.

    | Property | Value |
    | --- | --- |
    | Minimum OS version |  |
    | Maximum OS version |  |
    | Minimum OS required for mobile devices |  |
    | Maximum OS required for mobile devices |  |
    | Valid operating system builds |  |
- **Configuration Manager Compliance**:

    | Property | Value |
    | --- | --- |
    | Require device compliance from Configuration Manager | Select **Required** in environments that are co-managed with Configuration Manager. Otherwise, select **Not configured**. |
- **System security**:

    | Property | Value |
    | --- | --- |
    | **Password** |  |
    | Require a password to unlock mobile devices | Require |
    | Simple passwords | Block |
    | Password type | Device default |
    | Minimum password length | 6 |
    | Maximum inactivity in minutes before a password is required | 15 minutes |
    | Password expiration (days) | 41 |
    | Number of previous passwords to prevent reuse | 5 |
    | Require password when device returns from idle state (Mobile and Holographic) | Require |
    | **Encryption** |  |
    | Require encryption of data storage on device | Require |
    | **Firewall** |  |
    | Firewall | Require |
    | **Antivirus** |  |
    | Antivirus | Require |
    | **Antispyware** |  |
    | Antispyware | Require |
    | **Defender** |  |
    | Microsoft Defender anti-malware | Require |
    | Microsoft Defender anti-malware minimum version | We recommend a value that's no more than five versions behind the most recent version. |
    | Microsoft Defender anti-malware signature up to date | Require |
    | Real-time protection | Require |
- **Microsoft Defender for Endpoint**:

    | Property | Value |
    | --- | --- |
    | [Require the device to be at or under the machine-risk score](/en-us/intune/intune-service/protect/advanced-threat-protection-configure#create-and-assign-compliance-policy-to-set-device-risk-level) | Medium |

## Conditional Access policies

After you create app protection policies and device compliance policies in Intune, you can enable enforcement with Conditional Access policies.

### Require MFA based on sign-in risk

Follow the guidance in: [Require multifactor authentication for elevated sign-in risk](/en-us/entra/identity/conditional-access/policy-risk-based-sign-in) to create a policy that requires multifactor authentication based on sign-in risk.

When configuring the policy, use the following risk levels:

| Protection level | Risk levels |
| --- | --- |
| Starting point | Medium and High |
| Enterprise | Low, Medium, and High |

### Block clients that don't support multifactor authentication

Follow the guidance in: [Block legacy authentication with Conditional Access](/en-us/entra/identity/conditional-access/policy-block-legacy-authentication).

### High risk users must change password

Follow the guidance in: [Require a secure password change for elevated user risk](/en-us/entra/identity/conditional-access/policy-risk-based-user) to require users with compromised credentials to change their password.

Use this policy along with [Microsoft Entra password protection](/en-us/entra/identity/authentication/concept-password-ban-bad), which detects and blocks known weak passwords, their variants, and specific terms in your organization. Using Microsoft Entra password protection ensures that changed passwords are stronger.

### Require approved apps or app protection policies

You need to create a Conditional Access policy to enforce app protection policies that you create in Intune. Enforcing app protection policies requires a Conditional Access policy **and** a corresponding app protection policy.

To create a Conditional Access policy that requires approved apps or app protection, follow the steps in [Require approved client apps or app protection policy](/en-us/entra/identity/conditional-access/policy-all-users-approved-app-or-app-protection). This policy only allows accounts within apps protected by app protection policies to access Microsoft 365 endpoints.

Blocking legacy authentication for other apps on iOS/iPadOS and Android devices ensures that these devices can't bypass Conditional Access policies. By following the guidance in this article, you're already blocking clients that don't support modern authentication.

### Require compliant PCs and mobile devices

Caution

Verify your own device is compliant before you enable this policy. Otherwise, you could get locked out and need to use an emergency access account to recover your access.

Allow access to resources only after the device is determined to be compliant with your Intune compliance policies. For more information, see [Require device compliance with Conditional Access](/en-us/entra/identity/conditional-access/policy-all-users-device-compliance).

You can enroll new devices to Intune, even if you select **Require device to be marked as compliant** for **All users** and **All cloud apps** in the policy. **Require device to be marked as compliant** doesn't block Intune enrollment or access to the Microsoft Intune Web Company Portal app.

#### Subscription activation

If your organization uses [Windows subscription Activation](/en-us/windows/deployment/windows-subscription-activation) to enable users to "step-up" from one version of Windows to another, you should exclude the Universal Store Service APIs and Web Application (AppID: 45a330b1-b1ec-4cc1-9161-9f03992aa49f) from your device compliance.

### Always require MFA

Require MFA for all users by following the guidance in this article: [Require multifactor authentication for all users](/en-us/entra/identity/conditional-access/policy-all-users-mfa-strength).