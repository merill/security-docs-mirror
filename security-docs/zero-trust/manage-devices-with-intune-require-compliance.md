---
layout: Conceptual
title: Step 4. Require healthy and compliant devices with Intune | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/manage-devices-with-intune-require-compliance
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
ms.subservice: zero-trust
ms.date: 2025-03-14T00:00:00.0000000Z
description: Create a conditional access policy in Microsoft Entra ID to require compliant devices, keeping corporate data secure when users work from any device in any location.
ms.topic: how-to
ms.service: security
ms.localizationpriority: high
ms.collection:
- highpri
- Conditional access policy
- Microsoft Intune
- M365-security-compliance
- m365solution-managedevices
- m365solution-scenario
- zerotrust-solution
ms.custom: 
locale: en-us
document_id: 812d100e-60e0-665c-8b6e-30d9d2e8b4b4
document_version_independent_id: 812d100e-60e0-665c-8b6e-30d9d2e8b4b4
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/manage-devices-with-intune-require-compliance.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/manage-devices-with-intune-require-compliance
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/manage-devices-with-intune-require-compliance.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
platformId: d51a0b03-b4e2-b633-faef-5c3cd988b926
---

# Step 4. Require healthy and compliant devices with Intune | Microsoft Learn

Conditional Access provides another verification of device status before allowing access to a service. Conditional Access doesn’t work unless you specify conditions. In [Step 3. Set up compliance policies](manage-devices-with-intune-compliance-policies), you defined compliance policies that specify the minimum requirements a device must meet to access your environment. As described in this article, you’ll create the corresponding Conditional Access policy in Microsoft Entra ID to require compliant devices. This helps keep your corporate data secure while giving users the ability to work from any device and from any location.

After setting up device compliance policies and assigning these to user groups, Intune lets Microsoft Entra ID know if a device is compliant or not. To use this status as a condition for access, you must work with your Microsoft Entra administrator to create a Conditional Access rule to require compliant PCs and mobile devices.

[![The third step of Mobile Device Management to restrict access to managed and compliant devices.](media/devices/intune-mdm-step-3.png)](media/devices/intune-mdm-step-3.png#lightbox)

The recommended Zero Trust identity and device access rule set includes this rule. See [Require compliant PCs and mobile devices](zero-trust-identity-device-access-policies-common#require-compliant-pcs-and-mobile-devices), as seen in the following illustration.

[![Highlighted Zero Trust identity and device access policies to require compliant PCs and mobile devices.](media/devices/identity-device-require-compliance.svg)](media/devices/identity-device-require-compliance.svg#lightbox)

Be sure to:

- Coordinate the user groups you assigned to your compliance policies with the user groups assigned to the Conditional Access policy.
- Test out your Conditional Access policies using the What If and Audit Mode capabilities before fully assigning the Conditional Access policy. These capabilities help you understand the results of the policy.
- Set a grace period in line with the confidentiality of the data or app being accessed.
- Make sure your compliance policies don't interfere with any regulatory or other compliance requirements.
- Understand the device check-in intervals for compliance policies.
- Avoid conflicts between compliance policies and configuration profiles.

For information about these policies, including troubleshooting device profiles in Intune and understanding conflicts between policies, see [Common questions and answers with device policies and profiles in Microsoft Intune](/en-us/mem/intune-service/configuration/device-profile-troubleshoot).

To learn more about implementing common identify and device access policies, see [Common security policies for Microsoft 365 organizations](zero-trust-identity-device-access-policies-common).