---
layout: Conceptual
title: Step 7. Implement data loss prevention (DLP) with information protection capabilities | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/manage-devices-with-intune-dlp-mip
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Implement Endpoint DLP by working with your data security and privacy team to create DLP policies for your organization.
ms.subservice: zero-trust
ms.date: 2025-02-28T00:00:00.0000000Z
ms.topic: how-to
ms.service: security
ms.localizationpriority: high
ms.collection:
- highpri
- endpoint dlp
- data loss prevention
- dlp policies
- M365-security-compliance
- m365solution-managedevices
- m365solution-scenario
- zerotrust-solution
ms.custom: 
keywords: 
locale: en-us
document_id: 9f1bc20d-bb9a-ecec-048f-e8b640cfd7b5
document_version_independent_id: 9f1bc20d-bb9a-ecec-048f-e8b640cfd7b5
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/manage-devices-with-intune-dlp-mip.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/manage-devices-with-intune-dlp-mip
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/manage-devices-with-intune-dlp-mip.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/57eae111-0f3b-497e-be07-450fd1409dea
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/19ec6774-09b8-473e-a17e-b17b518bbad7
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ac8bf8ab-8134-4c9a-9f2e-58b31575b492
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ade36b61-c646-4bd8-87ee-f3a843461962
platformId: b87d8048-f5e7-8153-6904-624c5ca9e399
---

# Step 7. Implement data loss prevention (DLP) with information protection capabilities | Microsoft Learn

If your organization has already put the time into understanding your data, developing a data sensitivity schema, and applying the schema, you might be ready to extend elements of this schema to endpoints by using Microsoft Purview Data Loss Prevention (DLP) policies.

Endpoint data loss prevention (Endpoint DLP) currently applies to:

- Windows 10 and Windows 11
- macOS

DLP policies are created by your data security and privacy team. Each DLP policy defines what elements within a data set to look for, like sensitive information types or labels, and how to protect this data.

For example, a DLP policy can look for personal data like a passport number. The DLP policy includes a condition that triggers the policy to take action, such as when a passport number is shared with people outside your organization. The action the policy takes can be configured as well. Options range from simply reporting the action to admins, warning users, or even preventing the data from being shared.

The DLP policy also specifies the location to apply the policy to, such as Exchange email and SharePoint sites. One of the locations available to admins is devices. If devices are selected, you can specify which users and user groups to apply the policy to. You can also specify users and user groups to exclude from the policy.

If your data security and privacy team is ready to extend DLP policies to endpoints, you need to coordinate with them to enable devices for Endpoint DLP, test and tune DLP policies, train users, and monitor the results.

[![The three steps to implement Endpoint DLP steps for device admins.](media/devices/endpoint-dlp-steps.png)](media/devices/endpoint-dlp-steps.png#lightbox)

Use the following steps to work with your information protection team.

| Step | Description |
| --- | --- |
| 1 | [Learn about Endpoint DLP](/en-us/purview/endpoint-dlp-learn-about). |
| 2 | Enable devices for Endpoint DLP. If you onboarded devices to Microsoft Defender for Endpoint, your devices are already enabled for Endpoint DLP. If your devices aren't onboarded to Defender for Endpoint, see [Get started with Endpoint data loss prevention](/en-us/purview/endpoint-dlp-getting-started) for instructions. |
| 3 | Work with your data security and privacy team to define, test, and tune policies. This includes monitoring the results. See these resources:  - [Using Endpoint data loss prevention](/en-us/purview/endpoint-dlp-using) - [Get started with Activity Explorer](/en-us/purview/data-classification-activity-explorer) |