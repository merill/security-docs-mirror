---
layout: Conceptual
title: Step 3. Set up compliance policies for devices with Intune | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/manage-devices-with-intune-compliance-policies
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
ms.subservice: zero-trust
ms.date: 2025-03-14T00:00:00.0000000Z
description: Learn how to create device compliance policies that specify the minimum requirements for a device to access your environment.
ms.topic: how-to
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
document_id: b98b3b7c-610c-5143-93b7-9d64b6e15e7e
document_version_independent_id: b98b3b7c-610c-5143-93b7-9d64b6e15e7e
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/manage-devices-with-intune-compliance-policies.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/manage-devices-with-intune-compliance-policies
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/manage-devices-with-intune-compliance-policies.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/a72e95ff-4b4f-4cc1-90c6-7dcba67ff05f
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/24dc3ccd-591a-4415-a1fe-8759afafcb12
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
platformId: 4563fe6b-038f-067b-77cd-feaf0823e49d
---

# Step 3. Set up compliance policies for devices with Intune | Microsoft Learn

Enrolling devices to Microsoft Intune gives you the ability to achieve even greater security and control of data in your environment. [Step 2. Enroll devices in Intune](manage-devices-with-intune-enroll) details how to accomplish this using Intune. This article covers the next step, which is to configure device compliance policies.

[![The second step of Mobile Device Management to create compliance policies.](media/devices/intune-mdm-step-2.png)](media/devices/intune-mdm-step-2.png#lightbox)

You want to be sure devices that access your apps and data meet minimum requirements. For example, that they’re password or PIN-protected and the operating system is up to date. Compliance policies are the way to define the requirements that devices must meet. Intune uses these compliance policies to mark a device as compliant or non-compliant. This binary status is passed to Microsoft Entra which can use this status in Conditional Access rules to allow or prevent a device from accessing resources.

## Configuring device compliance policies

This guidance is tightly coordinated with the recommended [Zero Trust identity and device access policies](zero-trust-identity-device-access-policies-overview).

This illustration highlights where the work of defining compliance policies fits into the overall Zero Trust recommended policy set.

[![Highlighted Zero Trust identity and device access policies for Intune device compliance.](media/devices/identity-device-define-compliance.svg)](media/devices/identity-device-define-compliance.svg#lightbox)

In this illustration, defining device compliance policies is a dependency for achieving the recommended level of protection within the Zero Trust framework.

To configure device compliance policies, use the recommended guidance and settings prescribed in [Zero Trust identity and device access policies](zero-trust-identity-device-access-policies-overview). The following table links directly to the instructions for configuring these policies in Intune, including the recommended settings for each platform.

| Policies | More information | Licensing |
| --- | --- | --- |
| [Define device compliance policies](zero-trust-identity-device-access-policies-common#create-device-compliance-policies) | One policy for each platform | Microsoft 365 E3 or E5 |