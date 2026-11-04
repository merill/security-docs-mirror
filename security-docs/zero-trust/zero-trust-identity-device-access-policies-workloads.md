---
layout: Conceptual
title: Recommended policies for specific Microsoft 365 workloads | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/zero-trust-identity-device-access-policies-workloads
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: chrisda
author: chrisda
description: Describes the recommended Zero Trust policies to secure specific workloads in Microsoft 365.
ms.subservice: zero-trust
ms.service: security
ms.topic: best-practice
ms.reviewer: martincoetzer
ms.date: 2025-03-20T00:00:00.0000000Z
locale: en-us
document_id: 4fc4efce-1a7d-9298-8fe4-84e6a7fb1947
document_version_independent_id: 4fc4efce-1a7d-9298-8fe4-84e6a7fb1947
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/zero-trust-identity-device-access-policies-workloads.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/zero-trust-identity-device-access-policies-workloads
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/zero-trust-identity-device-access-policies-workloads.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/3e34b70d-bca0-4369-a01b-71d1edfd427b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/8ca32b3f-fa14-46df-b09a-9c4a591d6396
platformId: f5c81e29-4cf4-5737-5136-512c2c807a5e
---

# Recommended policies for specific Microsoft 365 workloads | Microsoft Learn

After you configure the [common security policies for Zero Trust](zero-trust-identity-device-access-policies-common) in your Microsoft 365 organization, you need to configure extra policies and settings for specific apps and workloads based on the three guiding principles of [Zero Trust](zero-trust-identity-device-access-policies-overview):

- Verify explicitly
- Use least privilege
- Assume breach

The extra policies and settings for specific apps and workloads are described in this article.

Tip

If possible, test your policies in a nonproduction environment before you roll them out to your production users. Testing is critical to identify and communicate any possible effects to your users.

## Microsoft Copilot recommendations for Zero Trust

For more information, see [Use Zero Trust security to prepare for AI companions, including Microsoft Copilots](copilots/apply-zero-trust-copilots-overview).

## Exchange Online recommendations for Zero Trust

This section describes the recommended settings for Zero Trust in Exchange Online.

### Verify automatic email forwarding to external recipients is disabled

By default, outbound spam policies in [the built-in security features for all cloud mailboxes](/en-us/defender-office-365/eop-about) block automatic email forwarding to external recipients done by [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) or by [mailbox forwarding](/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as *SMTP forwarding*). For more information, see [Control automatic external email forwarding in Microsoft 365](/en-us/defender-office-365/outbound-spam-policies-external-email-forwarding).

In all outbound spam policies, verify the value of the **Automatic forwarding rules** setting is **Automatic - System-controlled** (the default value) or **Off - Forwarding is disabled**. Both values block automatic email forwarding to external recipients by affected users. A default policy applies to all users, and admins can create custom policies that apply to specific groups of users. For more information, see [Configure outbound spam policies in Exchange Online Protection (EOP)](/en-us/defender-office-365/outbound-spam-policies-configure).

### Block Exchange ActiveSync clients

[Exchange ActiveSync](/en-us/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync) is a client protocol that synchronizes email and calendar data on desktop and mobile devices. Block access to company email by insecure ActiveSync clients as described in following procedures:

- **Mobile devices**: To block email access from the following types of mobile devices, create the Conditional Access policy described in [Require approved apps or app protection policies](zero-trust-identity-device-access-policies-common#require-approved-apps-or-app-protection-policies):

    - ActiveSync clients that use basic authentication.
    - ActiveSync clients that support modern authentication, but not Intune app protection policies.
    - Devices that support Intune app protection policies, but aren't defined in an app protection policy. For more information, see [Require an app protection policy](/en-us/entra/identity/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

    Tip

    We recommend Microsoft Outlook for iOS and Android as the app to access company email from iOS/iPadOS and Android devices.
- **PCs and other devices**: To block all ActiveSync clients that use basic authentication, create the Conditional Access policy described in [Block Exchange ActiveSync on all devices](/en-us/entra/identity/conditional-access/policy-all-users-approved-app-or-app-protection#block-exchange-activesync-on-all-devices).

### Limit access to email attachments in Outlook on the web and the new Outlook for Windows

You can restrict how users on unmanaged devices can interact with email attachments in Outlook on the web (formerly known as Outlook Web App or OWA) and in the new Outlook for Windows:

- Prevent users from downloading email attachments. They can view and edit these files using Office Online without leaking and storing the files on the device.
- Block users from even seeing attachments.

You enforce these restrictions using Outlook on the web mailbox policies. Microsoft 365 organizations with Exchange Online mailboxes have the built-in, default Outlook on the web mailbox policy named OwaMailboxPolicy-Default. By default, this policy is applied to all users. Admins can also [create custom policies](/en-us/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy) that apply to specific groups of users.

Here are the steps to limit access to email attachments on unmanaged devices:

1. [Connect to Exchange Online PowerShell](/en-us/powershell/exchange/connect-to-exchange-online-powershell).
2. To see the available Outlook on the web mailbox policies, run the following command:

    ```powershell
    Get-OwaMailboxPolicy | Format-Table Name,ConditionalAccessPolicy
    ```
3. Use the following syntax to limit access to email attachments in Outlook on the web and the new Outlook for Windows on unmanaged devices:

    ```powershell
    Set-OwaMailboxPolicy -Identity "<PolicyName>" -ConditionalAccessPolicy <ReadOnly | ReadOnlyPlusAttachmentsBlocked>
    ```

    This example **allows viewing but not downloading attachments** in the default policy.

    ```powershell
    Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ConditionalAccessPolicy ReadOnly
    ```

    This example **blocks viewing attachments** in the default policy.

    ```powershell
    Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
    ```
4. On the **Conditional Access | Overview** page in the Microsoft Entra admin center at [https://entra.microsoft.com/#view/Microsoft_AAD_ConditionalAccess/ConditionalAccessBlade/~/Overview](https://entra.microsoft.com/#view/Microsoft_AAD_ConditionalAccess/ConditionalAccessBlade/%7E/Overview), [create a new Conditional Access policy](/en-us/entra/identity/conditional-access/concept-conditional-access-policies) with the following settings:

    - **Assignments**section:
        - **Users**: Select appropriate users and groups to include and exclude on the **Include** and **Exclude** tabs.
        - **Target resources**: **Select what this policy applies to** &gt; **Resources (formerly cloud apps)** &gt; **Include** tab &gt; **Select resources** &gt; **Select** &gt; find and select **Office 365 Exchange Online**.
    - **Access controls** section: **Session** &gt; select **Use app enforced restrictions**.
    - **Enable policy** section: Select **On**.

### Set up message encryption

With Microsoft Purview Message Encryption, which uses protection features in Azure Information Protection, your organization can easily share protected email with anyone on any device. Users can send and receive protected messages with other organizations that use Microsoft 365, Outlook.com, Gmail, and other email services.

For more information, see [Set up Message Encryption](/en-us/purview/set-up-new-message-encryption-capabilities).

## SharePoint recommendations for Zero Trust

This section describes the recommended settings for Zero Trust in SharePoint.

### Configure SharePoint access control to limit access by unmanaged devices

Tip

The settings in this section require Microsoft Entra ID P1 or P2. For more information, see [Microsoft Entra plans and pricing](https://www.microsoft.com/security/business/microsoft-entra-pricing).

When you configure access control for unmanaged devices in the SharePoint, a corresponding Conditional Access policy to enforce the access level is automatically created in Microsoft Entra ID. This organization-wide setting applies to all users, but only affects access to sites specifically included in SharePoint access control.

In particular, you need to include sites in SharePoint access control that use **enterprise** or **specialized security** for Zero Trust as described in the following steps:

1. Configure [Allow limited, web-only access](/en-us/sharepoint/control-access-from-unmanaged-devices#limit-access) or [Block access](/en-us/sharepoint/control-access-from-unmanaged-devices#block-access) for unmanaged devices in SharePoint access control. This setting applies to all users, but doesn't affect their access to sites where they already have site permissions unless the site is included in SharePoint access control (the next step).

    Tip

    Site-level access can't be more permissive than the organization access control setting. For example, select **Allow limited, web-only access** for unmanaged devices in organization-wide access control so you can use `AllowLimitedAccess` or `BlockAccess` on specific sites. If you select **Block access** for unmanaged devices in organization-wide access control, you can't use `AllowLimitedAccess` on specific sites (only `BlockAccess` is available).
2. [Connect to SharePoint Online PowerShell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and use the *ConditionalAccessPolicy* parameter on the **Set-SPOSite** cmdlet to include the site in SharePoint access control for unmanaged devices:

    - **Enterprise sites**: Use the value `AllowLimitedAccess` to prevent users on unmanaged devices from downloading, printing, or syncing files.
    - **Specialized security sites**: Use the value `BlockAccess` to block access from unmanaged devices.

    For instructions, see [Block or limit access to a specific SharePoint site or OneDrive](/en-us/sharepoint/control-access-from-unmanaged-devices#block-or-limit-access-to-a-specific-sharepoint-site-or-onedrive)

Traditionally, site owners manage SharePoint site permissions based on the business need to access the site. Configuring SharePoint access control for unmanaged devices at the organization level and site level ensures consistent protection for these sites based on the Zero Trust protection level.

Consider the following example sites in the Contoso organization. SharePoint access control for unmanaged devices is configured at the **Allow limited, web-only access** level for the organization:

- **The Analytics team site configured with enterprise protection**: The site is configured with `AllowLimitedAccess` for unmanaged devices in SharePoint access control. Users with site permissions get browser-only access to the site on unmanaged devices. They can access the site using other apps on managed devices.
- **The Trade secrets site configure with specialized security protection**: The site is configured with `Block` for unmanaged devices in SharePoint access control. Users with site permissions are blocked from accessing the site on unmanaged devices. They can access the site only on managed devices.

## Microsoft Teams recommendations for Zero Trust

This section describes the recommended settings for Zero Trust in Microsoft Teams.

### Teams dependent services architecture

The diagram at [Microsoft Teams and related productivity services in Microsoft 365 for IT architects](/en-us/microsoft-365/solutions/productivity-illustrations#microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects) illustrates the services used by Microsoft Teams.

### Guest and external access for Teams

Microsoft Teams defines the following access types for users outside the organization:

- **Guest access**: Uses a Microsoft Entra B2B account for each user that can be added as a member of a team. Guest access allows access to Teams resources and interaction with internal users in group conversations, chats, and meetings.

    For more information about guest access and how to implement it, see [Guest access in Microsoft Teams](/en-us/microsoftteams/guest-access).
- **External access**: Users outside the organization who don't have Microsoft Entra B2B accounts. External access can include invitations and participation in calls, chats, and meetings, but doesn't include team membership or access to the resources of the team. External access is a way for Teams users in an external domain to find, call, chat with, and set up meetings in Teams with users in your organization.

    Teams admins can use custom policies to configure external access for the organization, groups of users, or individual users. For more information, see [IT Admins - Manage external meetings and chat with people and organizations using Microsoft identities](/en-us/microsoftteams/trusted-organizations-external-meetings-chat).

External access users have less access and functionality than guest access users. For example, external access users can chat with internal users using Teams, but they can't access team channels, files, or other resources.

Conditional Access policies apply only to guest access users in Teams because there are corresponding Microsoft Entra B2B accounts. External access doesn't use Microsoft Entra B2B accounts and therefore can't use Conditional Access policies.

For recommended policies to allow access with a Microsoft Entra B2B account, see [Policies for allowing guest and external B2B account access](zero-trust-identity-device-access-policies-guest-access).

## SaaS app recommendations for Zero Trust

Microsoft Defender for Cloud Apps builds on Microsoft Entra Conditional Access policies to enable real-time monitoring and control of granular actions with software as a service (SaaS) apps, such as blocking downloads, uploads, copy/paste, and printing. This feature adds security to sessions that carry inherent risk, such as when corporate resources are accessed from unmanaged devices or by guests.

For more information, see [Integrate SaaS apps for Zero Trust with Microsoft 365](integrate-saas-apps).