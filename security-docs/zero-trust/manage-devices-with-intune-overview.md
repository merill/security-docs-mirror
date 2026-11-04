---
layout: Conceptual
title: Manage devices with Intune | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/manage-devices-with-intune-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
ms.subservice: zero-trust
ms.date: 2025-03-14T00:00:00.0000000Z
ms.topic: solution-overview
description: Enroll your endpoint devices in Microsoft Intune as part of your Zero Trust security architecture, protecting against ransomware while building in protection for remote workers.
ms.service: security
ms.localizationpriority: high
ms.collection:
- highpri
- M365-security-compliance
- m365solution-managedevices
- m365solution-overview
- zerotrust-solution
ms.custom: 
keywords: 
locale: en-us
document_id: ad6b7e77-1edb-5613-292e-2c62bbd5c97d
document_version_independent_id: ad6b7e77-1edb-5613-292e-2c62bbd5c97d
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/manage-devices-with-intune-overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/manage-devices-with-intune-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/manage-devices-with-intune-overview.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/a72e95ff-4b4f-4cc1-90c6-7dcba67ff05f
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/24dc3ccd-591a-4415-a1fe-8759afafcb12
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: ca0f52ad-8765-f208-3e0b-e0e6f2f42e5a
---

# Manage devices with Intune | Microsoft Learn

A core component of enterprise-level security includes managing and protecting devices. Whether you’re building a Zero Trust security architecture, hardening your environment against ransomware, or building in protections to support remote workers, managing devices is part of the strategy. While Microsoft 365 includes several tools and methodologies for managing and protecting devices, this guidance walks through Microsoft’s recommendations using Microsoft Intune. This is the right guidance for you if you:

- Plan to enroll devices into Intune through Microsoft Entra join (including Microsoft Entra hybrid join).
- Plan to manually enroll devices into Intune.
- Allow bring your own devices (BYOD) with plans to implement protection for apps and data and/or enroll these devices in Intune.

On the other hand, if your environment includes plans for co-management including Microsoft Configuration Manager, see [Co-management documentation](/en-us/mem/configmgr/comanage/) to develop the best path for your organization. If your environment includes plans for Windows 365 Cloud PC, see [Windows 365 Enterprise documentation](/en-us/windows-365/enterprise/) to develop the best path for your organization.

Watch this video for an overview of the deployment process. 

## Why manage endpoints?

The modern enterprise has an incredible diversity of endpoints accessing its data. This setup creates a massive attack surface, and as a result, endpoints can easily become the weakest link in your Zero Trust security strategy.

Mostly driven by necessity as the world shifted to a remote or hybrid work model, users work from anywhere, from any device, more than at any time in history. Attackers are quickly adjusting their tactics to take advantage of this change. Many organizations face constrained resources as they navigate these new business challenges. Virtually overnight, companies have accelerated digital transformation. Simply stated, the way people work has changed. We no longer expect to access the myriad corporate resources only from the office and on company-owned devices.

Gaining visibility into the endpoints that access your corporate resources is the first step in your Zero Trust device strategy. Typically, companies are proactive in protecting PCs from vulnerabilities and attacks, while mobile devices often go unmonitored and without protections. To ensure you’re not exposing your data to risk, we need to monitor every endpoint for risks and employ granular access controls to deliver the appropriate level of access based on organizational policy. For example, if a personal device is jailbroken, you can block its access to prevent enterprise applications from being exposed to known vulnerabilities.

This series of articles walks through a recommended process for managing devices that access your resources. If you follow the recommended steps, your organization will achieve very sophisticated protection for your devices and the resources they access.

## Implementing the layers of protection on and for devices

Protecting the data and apps on devices and the devices themselves is a multi-layer process. There are some protections you can gain on unmanaged devices. After enrolling devices into management, you can implement more sophisticated controls. When threat protection is deployed across your endpoints, you gain even more insights and the ability to automatically remediate some attacks. Finally, if your organization has put the work into identifying sensitive data, applying classification and labels, and configuring Microsoft Purview Data Loss Prevention policies, you can obtain even more granular protection for data on your endpoints.

The following diagram illustrates building blocks to achieve a Zero Trust security posture for Microsoft 365 and other SaaS apps that you introduce to this environment. The elements related to devices are numbered 1 through 7. Device admins will coordinate with other administrators to accomplish these layers of protection.

[![Diagram of the Zero Trust security posture building blocks.](media/devices/m365-zero-trust-deployment-stack-devices.svg)](media/devices/m365-zero-trust-deployment-stack-devices.svg#lightbox)

In this illustration:

| - | Step | Description | Licensing requirements |
| --- | --- | --- | --- |
| 1 | Configure starting-point Zero Trust identity and device access policies | Step 1. [Implement app protection policies](manage-devices-with-intune-app-protection) to lay a foundation to protect devices by using Intune app protection policies, which don’t require device management. Then, collaborate with your identity team admin to implement Conditional Access policies that require approved apps and set [level 2 enterprise enhanced data protection](/en-us/mem/intune-service/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection), which is the recommended starting level for devices where users access sensitive information. | E3, E5, F1, F3, F5 |
| 2 | Enroll devices to Intune | This task requires more planning and time to implement. Microsoft recommends using Intune to enroll devices because this tool provides optimal integration. There are several options for enrolling devices, depending on the platform. For example, Windows devices can be enrolled by using Microsoft Entra join or by using Autopilot. You need to review the options for each platform and decide which enrollment option is best for your environment. See [**Step 2. Enroll devices in Intune**](manage-devices-with-intune-enroll) for more information. | E3, E5, F1, F3, F5 |
| 3 | Configure compliance policies | You want to be sure devices that are accessing your apps and data meet minimum requirements. For example, devices are password or PIN-protected and the operating system is up to date. Compliance policies are the way to define the requirements that devices must meet. [**Step 3. Set up compliance policies**](manage-devices-with-intune-compliance-policies) helps you configure these policies. | E3, E5, F3, F5 |
| 4 | Configure Enterprise (recommended) Zero Trust identity and device access policies | Now that your devices are enrolled, you can work with your identity admin to [**tune Conditional Access policies to require healthy and compliant devices**](manage-devices-with-intune-require-compliance). | E3, E5, F3, F5 |
| 5 | Deploy configuration profiles | As opposed to device compliance policies that simply mark a device as compliant or not based on criteria you configure, configuration profiles actually change the configuration of settings on a device. You can use configuration policies to harden devices against cyberthreats. See [**Step 5. Deploy configuration profiles**](manage-devices-with-intune-configuration-profiles). | E3, E5, F3, F5 |
| 6 | Monitor device risk and compliance with security baselines | In this step, you connect Intune to Microsoft Defender for Endpoint. With this integration, you can then monitor device risk as a condition for access. Devices that are found to be in a risky state are blocked. You can also monitor compliance with security baselines. See [**Step 6. Monitor device risk and compliance to security baselines**](manage-devices-with-intune-monitor-risk). | E5, F5 |
| 7 | Implement data loss prevention (DLP) with information protection capabilities | If your organization has put the work into identifying sensitive data and labeling documents, you can work with your information protection admin to [**protect sensitive information and documents on your devices**](manage-devices-with-intune-dlp-mip). | E5, F5 compliance add-on |

## Coordinating endpoint management with Zero Trust identity and device access policies

This guidance is tightly coordinated with the recommended [**Zero Trust identity and device access policies**](zero-trust-identity-device-access-policies-overview). You'll work with your identity team to carry through protection that you configure with Intune into Conditional Access policies in Microsoft Entra ID.

Following is an illustration of the recommended policy set with step callouts for the work you'll do in Intune and the related Conditional Access policies you'll help coordinate in Microsoft Entra ID.

[![Zero Trust identity and device access policies.](media/devices/identity-device-overview-steps.svg)](media/devices/identity-device-overview-steps.svg#lightbox)

In this illustration:

- In Step 1, [level 2 app protection policies](manage-devices-with-intune-app-protection) are configured as the recommended level of data protection with Intune app protection policies. Then you work with your identity team to configure the related Conditional Access rule to require the use of this protection.
- In Steps 2, 3 and 4, you enroll devices into management with Intune, define device compliance policies, and then coordinate with your identity team to configure the related Conditional Access rule to only allow access to compliant devices.

## Enrolling devices vs. onboarding devices

If you follow this guidance, you'll enroll devices into management using Intune and then onboard devices for the following Microsoft 365 capabilities:

- Microsoft Defender for Endpoint
- Microsoft Purview (for endpoint data loss prevention (DLP))

The following illustration details how this works using Intune.

[![Process for enrolling and onboarding devices.](media/devices/devices-enroll-onboard-process.svg)](media/devices/devices-enroll-onboard-process.svg#lightbox)

In the illustration:

1. Enroll devices into management with Intune.
2. Use Intune to onboard devices to Defender for Endpoint.
3. Devices that are onboard to Defender for Endpoint are also onboarded for Microsoft Purview features, including Endpoint DLP.

Note that only Intune is managing devices. Onboarding refers to the ability for a device to share information with a specific service. The following table summarizes the differences between enrolling devices into management and onboarding devices for a specific service.

| - | Enroll | Onboard |
| --- | --- | --- |
| Description | Enrollment applies to managing devices. Devices are enrolled for management with Intune or Configuration Manager. | Onboarding configures a device to work with a specific set of capabilities in Microsoft 365. Currently, onboarding applies to Microsoft Defender for Endpoint and Microsoft compliance capabilities.  On Windows devices, onboarding involves toggling a setting in Microsoft Defender that allows Defender to connect to the online service and accept policies that apply to the device. |
| Scope | These device management tools manage the entire device, including configuring the device to meet specific objectives, like security. | Onboarding only affects the services that apply. |
| Recommended method | Microsoft Entra join automatically enrolls devices into Intune. | Intune is the preferred method for onboarding devices to Windows Defender for Endpoint, and consequently Microsoft Purview capabilities.  Devices that are onboarded to Microsoft Purview capabilities using other methods aren't automatically enrolled for Defender for Endpoint. |
| Other methods | Other methods of enrollment depend on the platform of the device and whether it's BYOD or managed by your organization. | Other methods for onboarding devices include, in recommended order: - Configuration Manager<br>- Other mobile device management tool (if the device is managed by one)<br>- Local script<br>- VDI configuration package for onboarding non-persistent virtual desktop infrastructure (VDI) devices<br>- Group Policy |

## Learning for administrators

The following resources help administrators learn concepts about using Intune:

- [Simplify device management with Microsoft Intune](/en-us/training/modules/simplify-device-management-with-microsoft-endpoint-manager/) training module

    Learn about how the business management solutions through Microsoft 365 provide people with a secure, personalized desktop experience and help organizations easily manage updates for all devices with a simplified admin experience.
- [Evaluate Microsoft Intune](/en-us/training/modules/set-up-microsoft-intune/)

    Microsoft Intune helps you protect the devices, apps, and data that people at your organization use to be productive. This article tells you how to set up Microsoft Intune. Setup includes reviewing the supported configurations, signing up for Intune, adding users and groups, assigning licenses to users, granting admin permissions, and setting the Mobile Device Management (MDM) authority.