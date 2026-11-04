---
layout: Conceptual
title: Identity and device access policies for allowing guest and external user B2B access - Microsoft 365 for enterprise | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/zero-trust-identity-device-access-policies-guest-access
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: chrisda
author: chrisda
description: Describes the recommended Conditional Access and related policies for protecting access of guests and external users.
ms.service: security
ms.topic: best-practice
ms.subservice: zero-trust
manager: dansimp
ms.reviewer: martincoetzer
ms.date: 2025-03-10T00:00:00.0000000Z
locale: en-us
document_id: 5a51de59-253e-26dd-b0bc-60411805d2c1
document_version_independent_id: 5a51de59-253e-26dd-b0bc-60411805d2c1
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/zero-trust-identity-device-access-policies-guest-access.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/zero-trust-identity-device-access-policies-guest-access
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/zero-trust-identity-device-access-policies-guest-access.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/5331c238-d256-4c32-9beb-4e965c2dbacd
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/5d107fce-b800-428d-888b-eb0d58a91d06
platformId: 322b1267-ce2a-f480-1972-b080a263bb58
---

# Identity and device access policies for allowing guest and external user B2B access - Microsoft 365 for enterprise | Microsoft Learn

This article discusses adjusting the recommended Zero Trust identity and device access policies to allow access for guests and external users that have a Microsoft Entra Business-to-Business (B2B) account. This guidance builds on the [common identity and device access policies](zero-trust-identity-device-access-policies-common).

These recommendations are designed to apply to the **starting point** tier of protection. But you can also adjust the recommendations based on your specific needs for **enterprise** and **specialized security** protection.

Providing a path for B2B accounts to authenticate with your Microsoft Entra organization doesn't give these accounts access to your entire environment. B2B users and their accounts have access to services and resources (for example, files) designated by Conditional Access policy.

## Updating the common policies to allow and protect guests and external user access

The following table lists the policies you need to create and update. The common policies link to the associated configuration instructions in [Common identity and device access policies](zero-trust-identity-device-access-policies-common).

| Protection level | Policies | More information |
| --- | --- | --- |
| **Starting point** | [Require MFA always for guests and external users](zero-trust-identity-device-access-policies-common#require-mfa-based-on-sign-in-risk) | Create this new policy and configure the following settings: <br>- **Assignments** &gt; **Users** &gt; **Include** &gt; **Select users and groups**: Select **Guest or external users**, and then select all of the available user types:<br>    - **B2B collaboration guest users**<br>    - **B2B collaboration member users**<br>    - **B2B direct connect users**<br>    - **Local guest users**<br>    - **Service provider users**<br>    - **Other external users**<br>- **Assignments** &gt; **Conditions** &gt; **Sign-in risk**: Select all of the available risk values:<br>    - **No risk**<br>    - **Low**<br>    - **Medium**<br>    - **High** |
|  | [Require MFA when sign-in risk is *medium* or *high*](zero-trust-identity-device-access-policies-common#require-mfa-based-on-sign-in-risk) | Modify this policy to exclude guests and external users. |

To exclude guests and external users from Conditional Access policies, go to **Assignments** &gt; **Users** &gt; **Exclude** &gt; **Select users and groups**: Select **Guest or external users**, and then select all of the available user types:

- **B2B collaboration guest users**
- **B2B collaboration member users**
- **B2B direct connect users**
- **Local guest users**
- **Service provider users**
- **Other external users**

[![Screenshot of the controls for excluding guests and external users.](media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)](media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png#lightbox)

## More information

### Guests and external user access with Microsoft Teams

Microsoft Teams defines the following users:

- **Guest access** uses a Microsoft Entra B2B account that can be added as a member of a team and have access to the communications and resources of the team.
- **External access** is for an external user that doesn't have a B2B account. External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.

For more information, see [Compare external access and guest access in Teams](/en-us/microsoftteams/communicate-with-users-from-other-organizations#compare-external-access-and-guest-access).

For more information on securing identity and device access policies for Teams, see [Zero Trust considerations for Microsoft Teams](zero-trust-identity-device-access-policies-workloads#microsoft-teams-recommendations-for-zero-trust).

### Require MFA always for guest and external users

This policy requires guests to register for MFA in your organization, regardless of whether they're registered for MFA in their home organization. Guests and external users in your organization are required to use MFA for every request to access resources.

### Excluding guests and external users from risk-based MFA

While organizations can enforce risk-based policies for B2B users using Microsoft Entra ID Protection, there are limitations in a resource directory because their identity exists in their home directory. Due to these limitations, we recommend that you exclude guests from risk-based MFA policies and require these users to always use MFA.

For more information, see [Limitations of ID Protection for B2B collaboration users](/en-us/entra/id-protection/concept-identity-protection-b2b#limitations-of-id-protection-for-b2b-collaboration-users).

### Excluding guests and external users from device management

Only one organization can manage a device. If you don't exclude guests and external users from policies that require device compliance, these policies block these users.