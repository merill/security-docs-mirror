---
layout: Conceptual
title: Step 6. Monitor device risk and compliance for security baselines | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/manage-devices-with-intune-monitor-risk
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn how to connect Microsoft Intune to Defender for Endpoint and monitor device risk as a condition for access.
ms.subservice: zero-trust
ms.date: 2025-03-14T00:00:00.0000000Z
ms.topic: how-to
ms.service: security
ms.localizationpriority: high
ms.collection:
- highpri
- M365-security-compliance
- deploy security baselines
- m365solution-managedevices
- m365solution-scenario
- zerotrust-solution
ms.custom: 
keywords: 
locale: en-us
document_id: 18eee31d-2947-9203-346c-a22dad32d0f9
document_version_independent_id: 18eee31d-2947-9203-346c-a22dad32d0f9
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/manage-devices-with-intune-monitor-risk.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/manage-devices-with-intune-monitor-risk
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/manage-devices-with-intune-monitor-risk.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/8b9ae643-2e85-42b8-beb2-eef4bae8c4bc
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/a72e95ff-4b4f-4cc1-90c6-7dcba67ff05f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/e047e27d-b5f3-43a8-b4b0-4f6dca95e7c9
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/24dc3ccd-591a-4415-a1fe-8759afafcb12
platformId: c1409c44-c9c3-4151-0bc9-e7a3c8d21b06
---

# Step 6. Monitor device risk and compliance for security baselines | Microsoft Learn

After your organization deploys Microsoft Defender for Endpoint, you can gain greater insights and protection of your devices by integrating Microsoft Intune with Defender for Endpoint. For mobile devices, this includes the ability to monitor device risk as a condition for access. For Windows devices, you can monitor compliance of these devices to security baselines.

Deploying Microsoft Defender for Endpoint includes onboarding endpoints. If you used Intune to onboard endpoints (recommended), then you've connected Intune to Defender for Endpoint. If you used a different method to onboard endpoints to Defender for Endpoint, see [Configure Microsoft Defender for Endpoint in Intune](/en-us/mem/intune-service/protect/advanced-threat-protection-configure) to ensure you set up the service-to-service connection between Intune and Defender for Endpoint.

[![The integration of Microsoft Intune with Microsoft Defender for Endpoint, including how Defender for Endpoint shares its signals with Microsoft Defender XDR.](media/devices/devices-defender-for-endpoint-steps.svg)](media/devices/devices-defender-for-endpoint-steps.svg#lightbox)

In this illustration:

- Microsoft Defender for Endpoint greatly increases the sophistication of threat protection for devices.
- Microsoft Intune allows you to set app protection policies and manage devices (including configuration changes). Defender for Endpoint continuously monitors your devices for threats, and can take automated action to remediate attacks.
- You can use Intune to onboard devices to Defender for Endpoint, which enables these devices to work with Microsoft Purview Endpoint Data Loss Prevention (DLP).

This article includes these steps:

- Monitor device risk
- Monitor compliance for security baselines

If Defender for Endpoint hasn’t already been set up, work with your threat protection admin to [set up the evaluation and pilot environment](/en-us/defender-xdr/pilot-deploy-defender-endpoint). You can work with the pilot group to try out the capabilities in this article.

## Monitor device risk as a condition for access

With Microsoft Defender for Endpoint deployed, you can take advantage of threat risk signals. This allows you to block access to devices based on their risk score. Microsoft recommends allowing access to devices with a risk score of medium or lower.

For Android and iOS/iPadOS, threat signals can be used within your app protection policies. For more information, see [Create and assign app protection policy to set device risk level](/en-us/mem/intune-service/protect/advanced-threat-protection-configure#create-and-assign-compliance-policy-to-set-device-risk-level).

For all platforms, you can set the risk level in the existing device compliance policies. For more information, see [Create a Conditional Access policy](/en-us/mem/intune-service/protect/advanced-threat-protection-configure#create-a-conditional-access-policy).

## Deploy security baselines and monitor compliance for these settings

Applies to: Windows 10, Windows 11

The [Step 5. Deploy configuration profiles](manage-devices-with-intune-configuration-profiles) article recommends getting started with configuration profiles by using the Intune security baselines that are available for Windows 10 and Windows 11. Intune also includes security baselines for Microsoft Defender for Endpoint that provide settings to optimize all the security controls in the Defender for Endpoint stack, including settings for endpoint detection and response (EDR).

Ideally, devices onboarded to Defender for Endpoint would receive both baselines: the security baseline for Windows to initially secure Windows, and then the Defender for Endpoint security baseline layered on top to optimally configure the Defender for Endpoint security controls.

To benefit from the latest data on risks and threats and to minimize conflicts as baselines evolve, always apply the latest versions of the baselines across all products as soon as they're released.

Using Defender for Endpoint, you can monitor compliance for these baselines.

[![A screenshot example of the card in Defender for Endpoint for monitoring compliance for security baselines.](media/devices/secconmgmt-baseline-card.png)](media/devices/secconmgmt-baseline-card.png#lightbox)

To deploy security baselines and monitor compliance for these settings, use the steps in this table.

| Step | Description |
| --- | --- |
| 1 | Review key concepts and compare the Microsoft Defender for Endpoint and the Windows security baselines in Intune.  To learn about recommendations for Defender for Endpoint, see [Increase compliance to the Microsoft Defender for Endpoint security baseline](/en-us/defender-endpoint/configure-machines-security-baseline).  To review the list of security baselines that are available with Intune, and how to avoid conflicts, see [Use security baselines to configure Windows devices in Intune](/en-us/mem/intune-service/protect/security-baselines). |
| 2 | Use Intune to deploy the security baseline for Windows settings. For more information, see related guidance in [Step 5. Deploy device profiles](manage-devices-with-intune-configuration-profiles). |
| 3 | Use Intune to deploy Defender for Endpoint baseline settings. To create the profile and choose the correct baseline, see [Manage security baseline profiles in Microsoft Intune](/en-us/intune/intune-service/protect/security-baselines-configure).  You can also follow the instructions as [Review and assign the Microsoft Defender for Endpoint security baseline](/en-us/defender-endpoint/configure-machines-security-baseline#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline) in the Defender for Endpoint documentation. |
| 4 | In the Defender for Endpoint documentation, review [Ensure your devices are configured properly](/en-us/defender-endpoint/configure-machines) and the [Security baseline card on device configuration management](/en-us/defender-endpoint/configure-machines-security-baseline#monitor-compliance-to-the-defender-for-endpoint-security-baseline). |