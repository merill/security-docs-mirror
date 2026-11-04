---
layout: Conceptual
title: Step 1. Implement App Protection Policies | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/manage-devices-with-intune-app-protection
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
ms.subservice: zero-trust
ms.date: 2025-03-14T00:00:00.0000000Z
ms.topic: how-to
description: Configure mobile app protection with App Protection policies (APP) to prevent specified corporate data from being copied and pasted to other apps.
ms.service: security
ms.localizationpriority: high
ms.collection:
- highpri
- M365-security-compliance
- m365solution-managedevices
- m365solution-scenario
- zerotrust-solution
ms.custom: 
keywords: 
locale: en-us
document_id: 7bf7286c-ce8e-7f08-5ac8-03f27f4a5f9f
document_version_independent_id: 7bf7286c-ce8e-7f08-5ac8-03f27f4a5f9f
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/manage-devices-with-intune-app-protection.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/manage-devices-with-intune-app-protection
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/manage-devices-with-intune-app-protection.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7ebba99b-05c3-4387-8883-f7bbf6632cb8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/a72e95ff-4b4f-4cc1-90c6-7dcba67ff05f
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/006ab567-b18c-4cf1-9a25-c24daa46ede1
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/24dc3ccd-591a-4415-a1fe-8759afafcb12
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 938cbba3-b2eb-c72f-4861-8ab85ec0f083
---

# Step 1. Implement App Protection Policies | Microsoft Learn

Microsoft Intune app protection policies, sometimes referred to as Mobile Application Management (MAM), protect corporate data even if a device itself is not managed. This allows you to enable bring-your-own (BYO) and personal devices at work where users might be reluctant to "enroll" their device into management. App protection policies ensure corporate data in the apps you specify can't be copied and pasted to other apps on the device.

[![Steps for creating App Protection Policies to separate organization and personal data on a device.](media/devices/intune-app-steps.png)](media/devices/intune-app-steps.png#lightbox)

In this illustration:

- With app protection policies, Intune creates a wall between your organization data and personal data. The app protection policies define which apps are allowed to access your data.
- If a user signs in with their organization credentials, Intune applies a policy at the app layer to prevent copy and paste of your organization data to personal apps and to require PIN access to this data.
- After creating an app protection policy, you enforce data protection with a Conditional Access policy.

This configuration greatly increases your security posture with almost no impact on the user experience. Employees can use apps like Microsoft Office and Microsoft Teams, that they know and love, while at the same time your organization can protect the data contained within the apps and devices.

If you have custom line-of-business applications that need protection, currently you can use the app wrapping tool to support using app protection policies with these applications. Or, you can integrate using the Intune App SDK. When your app has app protection policies applied to it, it can be managed by Intune and is recognized by Intune as a managed app.

For more information about protecting your line-of-business applications using Intune, see [Prepare apps for mobile application management with Microsoft Intune](/en-us/mem/intune-service/developer/apps-prepare-mobile-application-management).

## Configuring mobile app protection

This guidance is tightly coordinated with the recommended [Zero Trust identity and device access policies](zero-trust-identity-device-access-policies-overview). After you create the mobile app protection policies in Intune, work with your identity team to configure the Conditional Access policies in Microsoft Entra ID that enforce mobile app protection.

This illustration highlights the two policies (also described in the table following the illustration).

[![Highlighted Zero Trust identity and device access policies to enforce mobile app protection.](media/devices/identity-device-starting-point.svg)](media/devices/identity-device-starting-point.svg#lightbox)

To configure these policies, use the recommended guidance and settings prescribed in [Zero Trust identity and device access policies](zero-trust-identity-device-access-policies-overview). The following table links directly to the instructions for configuring these policies in Intune and Microsoft Entra ID.

| Policy | More information | Licensing |
| --- | --- | --- |
| [Apply application protection policies for data protection](zero-trust-identity-device-access-policies-common#app-protection-policies) | One Intune App Protection policy per platform (Windows, iOS/iPadOS, Android). | Microsoft 365 E3 or E5 |
| [Require approved apps and app protection](zero-trust-identity-device-access-policies-common) | Enforces mobile app protection for phones and tablets using iOS, iPadOS, or Android. | Microsoft 365 E3 or E5 |