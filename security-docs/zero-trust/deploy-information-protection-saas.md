---
layout: Conceptual
title: Deploy information protection for SaaS apps | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/deploy-information-protection-saas
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: macapara
author: mjcaparas
description: Learn how to deploy information protection for SaaS apps to prevent inadvertent exposure of sensitive information.
ms.date: 2024-04-18T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: solution-overview
ms.collection:
- m365solution-saas
- m365solution-scenario
- m365solution-zero-trust
- zerotrust-solution
- highpri
locale: en-us
document_id: dbac0ab5-b9fa-7854-9e8d-e9dbbbc33d02
document_version_independent_id: dbac0ab5-b9fa-7854-9e8d-e9dbbbc33d02
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/deploy-information-protection-saas.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/deploy-information-protection-saas
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/deploy-information-protection-saas.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/57eae111-0f3b-497e-be07-450fd1409dea
- https://authoring-docs-microsoft.poolparty.biz/devrel/8e3fdb08-a059-4277-98f6-c0e21e940707
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ac8bf8ab-8134-4c9a-9f2e-58b31575b492
- https://authoring-docs-microsoft.poolparty.biz/devrel/88291526-9c74-4f87-878c-de0a82134421
platformId: 7027ea37-4b95-e3fc-2479-202d72621e99
---

# Deploy information protection for SaaS apps | Microsoft Learn

While protecting access to apps and session activities are important, the data that SaaS apps contain may be one of the most critical resources to protect. Deploying information protection for SaaS apps is a key step in preventing inadvertent or malicious exposure of sensitive information.

[Microsoft Purview Information Protection](/en-us/purview/information-protection) is natively integrated in Microsoft 365 apps and services such as SharePoint, OneDrive, Teams, and Exchange. For other SaaS apps, you might want to integrate them with Microsoft Purview to ensure your sensitive data is protected wherever it is. There are various ways to integrate information protection with other apps you use. You can use Microsoft Defender for Cloud Apps to integrate labeling with apps or have an app developer integrate directly using an SDK. For more information, see [About Microsoft Information Protection SDK](/en-us/information-protection/develop/overview).

This step builds on the [Deploy information protection with Microsoft Purview](/en-us/microsoft-365/compliance/information-protection-solution) solution guidance and guides you on how to use Defender for Cloud Apps to extend information protection to data in SaaS apps. You may want to review the guidance to gain a better understanding of the overall workflow.

The scope of this article focuses on protecting Microsoft Office and PDF files and document repositories within SaaS applications.

The key concepts surrounding information protection involves knowing your data, protecting your data, and preventing data loss. The following diagram shows how to perform these key functions with the Purview compliance portal and the Defender for Cloud Apps portal.

[![Diagram of the process of knowing your data, protecting your data, and preventing data loss with the Purview compliance portal and the Defender for Cloud Apps portal.](media/information-protection-saas-apps.svg)](media/information-protection-saas-apps.svg#lightbox)

In this diagram:

- To protect data in SaaS apps, you must first determine the information in your organization that is sensitive. After doing that, check to see if any of the sensitive information types (SITs) map to the determined sensitive information. If none of the SITs meet your needs, you can modify them or create custom SITs with the Microsoft Purview compliance portal.
- Using the defined SITs, you can discover items that contain sensitive data in SaaS apps.

    Tip

    To learn about the full list of supported apps for Microsoft Purview Information Protection, see [Information Protection](/en-us/defender-cloud-apps/enable-instant-visibility-protection-and-governance-actions-for-your-apps#information-protection)
- After discovering items that contain sensitive data, you can extend labels to SaaS apps and then apply them.
- To prevent data loss, you can define and then extend data loss prevention (DLP) policies. With a DLP policy, you can identify, monitor, and automatically protect sensitive items across services. An example of a protective action of DLP policies is showing a pop-up policy tip to a user when they try to share a sensitive item inappropriately. Another example is blocking the sharing of sensitive items.

Use the following steps to apply information protection capabilities for your SaaS apps.

## Discover sensitive information in SaaS apps

To discover sensitive information contained in SaaS apps, you'll need to:

- Enable the Microsoft Purview Information Protection integration with Defender for Cloud Apps.
- Create policies to identify sensitive information in files.

Microsoft Purview Information Protection is a framework that includes Defender for Cloud Apps. Integrating Defender for Cloud Apps in Microsoft Purview will help you better protect sensitive information in your organization. For more information, see [How to integrate Microsoft Purview Information Protection with Defender for Cloud Apps](/en-us/defender-cloud-apps/azip-integration#how-to-integrate-microsoft-purview-information-protection-with-defender-for-cloud-apps).

Once you know the kinds of information you want to protect, you create policies to detect them. You can create policies for:

- **Files:** File policies scan the content of files stored in your connected cloud apps via API, for supported apps.
- **Sessions:** Session policies scan and protect files in real time upon access to prevent data exfiltration, protect files on download, and prevent the upload of unlabeled files.

For more information, see [Microsoft Data Classification Services integration](/en-us/defender-cloud-apps/dcs-inspection).

## Apply sensitivity labels to protect data

After discovering and sorting sensitive information, you can apply sensitivity labels. When a sensitivity label is applied to a document, any configured protection settings for that label are enforced on the content. For example, a file that is labeled "Confidential" may be encrypted and have its access limited. Access limitations can include individual user accounts or groups.

Defender for Cloud Apps is natively integrated with Microsoft Purview Information Protection and the same sensitivity types and labels are available throughout both services. When you want to define sensitive information, use the Microsoft Purview compliance portal to create them and they will be available in Defender for Cloud Apps.

Defender for Cloud Apps lets you automatically apply sensitivity labels from Microsoft Purview Information Protection. These labels are applied to files as a file policy governance action and, depending on the label configuration, can apply encryption for another layer of protection.

For more information, see [Apply Microsoft Purview Information Protection labels automatically](/en-us/defender-cloud-apps/use-case-information-protection).

## Extend DLP policies to SaaS apps

Depending on the SaaS apps that you have in your environment, you have various options to choose from to deploy a DLP solution. Use the following table to guide you in your decision-making process.

| Scenario | Tool |
| --- | --- |
| Your environment has the following products: - Exchange Online email  - SharePoint Online sites - OneDrive accounts - Teams chat and channel messages  - Microsoft Defender for Cloud Apps - Windows 10, Windows 11, and macOS (Catalina 10.15 and higher) devices  - On-premises repositories- Power BI sites | Use Microsoft Purview.  For more information, see [Learn about DLP](/en-us/microsoft-365/compliance/dlp-learn-about-dlp). |
| Your organization uses other apps that aren't covered in Microsoft Purview, but can be connected to Microsoft Defender for Cloud Apps via API such as: - Atlassian  - Azure  - AWS  - Box  - DocuSign - Egnyte  - GitHub  - Google Workspace  - GCP  - NetDocuments  - Office 365  - Okta  - OneLogin  - Salesforce  - ServiceNow  - Slack  - Smartsheet  - Webex  - Workday  - Zendesk | Use Defender for Cloud Apps.  To use a DLP policy that's scoped to a specific non-Microsoft cloud app, the app must be connected to Defender for Cloud Apps. For more information, see [Connect apps](/en-us/defender-cloud-apps/enable-instant-visibility-protection-and-governance-actions-for-your-apps). |
| The apps that your organization uses aren't yet supported in Defender for Cloud Apps via API, but can be added using app connectors and you can use session policies to apply DLP policies in real time. | Use Defender for Cloud Apps.  For more information, see [Connect apps](/en-us/defender-cloud-apps/enable-instant-visibility-protection-and-governance-actions-for-your-apps) and [Use data loss prevention policies for non-Microsoft cloud apps](/en-us/microsoft-365/compliance/dlp-use-policies-non-microsoft-cloud-apps). |

For guidance on licensing, see [Microsoft 365 guidance for security & compliance](/en-us/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## Monitor your data

Now that your policies are in place, you'll want to check the Microsoft Defender portal to monitor the effect of your policies and remediate incidents. Microsoft Defender XDR gives you visibility into DLP alerts and incidents from Microsoft Purview and Defender for Cloud apps in a single pane of glass.

Your security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.

For more information, see [Microsoft Defender portal](/en-us/microsoft-365/security/defender/microsoft-365-defender-portal).