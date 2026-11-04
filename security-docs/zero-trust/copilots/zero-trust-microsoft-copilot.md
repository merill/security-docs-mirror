---
layout: Conceptual
title: How do I apply Zero Trust principles to Microsoft Copilot Chat for web-grounded prompts? | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/copilots/zero-trust-microsoft-copilot
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: How to apply Zero Trust principles to Microsoft Copilot Chat for web-grounded prompts.
ms.date: 2026-05-21T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
ms.collection:
- M365copilot
- msec-ai-copilot
- msftsolution-copilot
- msftsolution-scenario
- zerotrust-solution
- zerotrust-copilot
- trust-pod
ms.custom:
- copilot-learning-hub
locale: en-us
document_id: f0858a97-bcad-9b0e-4fb8-afd9c4196162
document_version_independent_id: f0858a97-bcad-9b0e-4fb8-afd9c4196162
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/copilots/zero-trust-microsoft-copilot.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/copilots/zero-trust-microsoft-copilot
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/copilots/zero-trust-microsoft-copilot.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
- https://authoring-docs-microsoft.poolparty.biz/devrel/5287f575-02f0-405f-92b7-800456526b0c
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
- https://authoring-docs-microsoft.poolparty.biz/devrel/06e86142-34c2-4b94-ab9c-9477c21f7152
platformId: 972dea4c-e928-3e8d-d150-d23f6c82efd2
---

# How do I apply Zero Trust principles to Microsoft Copilot Chat for web-grounded prompts? | Microsoft Learn

**Summary:** To apply Zero Trust principles to Microsoft Copilot Chat, you need to:

1. Implement security protections for web-grounded prompts to the Internet.
2. Add security protections for Microsoft Edge browser summarization.

## Introduction

Microsoft Copilot Chat is an AI companion in the Microsoft Copilot app, in Edge, and at the following URLs — M365copilot.com and Copilot.cloud.microsoft. It's provided for Entra account users with a [qualifying license](/en-us/copilot/manage#microsoft-365--chat-eligibility). Copilot Chat includes enterprise data protection. Enterprise data protection isn't included in Copilot Chat for personal use (consumer version). This article helps you implement security protections to keep your organization and data safe while using Copilot Chat. By implementing these protections, you're building a foundation of Zero Trust.

Zero Trust security recommendations for Copilot Chat focus on protection for user accounts, user devices, and your organization data that Copilot Chat can summarize in Edge.

## How does Zero Trust help with AI?

Security, especially data protection, is often a top concern when introducing AI tools into an organization. Zero Trust is a security strategy that verifies every user, device, and resource request to ensure that each of these is allowed. The term "Zero Trust" refers to the strategy of treating each connection and resource request as though it originated from an uncontrolled network and a bad actor. Regardless of where the request originates or what resource it accesses, Zero Trust teaches us to “never trust, always verify.”

As a leader in security, Microsoft provides a practical roadmap and clear guidance for implementing Zero Trust. Microsoft’s set of Copilots are built on top of existing platforms, which inherit the protections applied to those platforms. For the details of applying Zero Trust to Microsoft’s platforms, see the [Zero Trust Guidance Center](/en-us/security/zero-trust/). By implementing these protections, you're building a foundation of Zero Trust security.

This article draws from that guidance to prescribe the Zero Trust protections that relate to Copilot.

## What’s included in this article

This article walks through the security recommendations that apply in two stages. This provides a path for you to introduce Copilot Chat into your environment while you apply security protections for users, devices, and the data accessed by Copilot.

| Stage | Configuration | Components to secure |
| --- | --- | --- |
| 1 | Web-grounded prompts to the Internet | Basic security hygiene for users and devices using identity and access policies. |
| 2 | Web-grounded prompts to the Internet with Edge browser page summarization enabled | Your organization data on local, intranet, and cloud locations that Copilot in Edge can summarize. |

## Stage 1. Start with security recommendations for web-grounded prompts to the Internet

The simplest configuration of Copilot provides AI assistance with web-grounded prompts.

[![Diagram of Microsoft Copilot and the processing of Web-grounded prompts.](../media/copilot/microsoft-copilot-web-grounded-prompts.svg)](../media/copilot/microsoft-copilot-web-grounded-prompts.svg#lightbox)

In the illustration:

- Users can interact with Copilot Chat through M365copilot.com, Copilot.cloud.microsoft, the Microsoft Copilot app, and Edge.
- Prompts are web-grounded. Copilot Chat only uses publicly available data to respond to prompts.
- Edge browser page summarization is not enabled.

With this configuration, your organization data isn’t included in the scope of data that Copilot Chat references. However, you need to ensure that browser page summarization is not enabled. As an admin, you can do this by using the [*EdgeEntraCopilotPageContext*](/en-us/copilot/manage#manage--chat-in-edge) group policy setting.

Use this stage to implement identity and access policies for users and devices to prevent bad actors from using Copilot. At a minimum, you must configure Conditional Access policies that require:

- [Multifactor authentication for all users](zero-trust-microsoft-365-copilot#step-2-deploy-or-validate-your-identity-and-access-policies)
- [Trusted and healthy devices](zero-trust-microsoft-365-copilot#step-4-deploy-or-validate-your-device-management-and-protection)

### Additional recommendations for Microsoft 365 E3

- For user account authentication and access, also configure the identity and access policies to [Block clients that don’t support modern authentication](/en-us/microsoft-365/security/office-365-security/zero-trust-identity-device-access-policies-common#block-clients-that-dont-support-multifactor-authentication).
- [Use Windows protection capabilities](zero-trust-microsoft-365-copilot#windows-protection-capabilities).

### Additional recommendations for Microsoft 365 E5

Implement the recommendations for E3 and configure the following identity and access policies:

- [Require MFA when sign-in risk is medium or high](/en-us/microsoft-365/security/office-365-security/zero-trust-identity-device-access-policies-common#require-mfa-based-on-sign-in-risk)
- [High risk users must change their password](/en-us/microsoft-365/security/office-365-security/zero-trust-identity-device-access-policies-common#high-risk-users-must-change-password)

## Stage 2. Add security protections for Edge browser summarization

From the Microsoft Edge sidebar, Microsoft Copilot Chat helps you get answers and inspirations from across the web and, if enabled, from some types of information displayed in open browser tabs.

[![Diagram of Web-grounded prompts in Edge with browser tab summarization enabled.](../media/copilot/microsoft-copilot-edge-summarization-enabled.svg)](../media/copilot/microsoft-copilot-edge-summarization-enabled.svg#lightbox)

If you disable browser page summarization, you need to re-enable this feature. As an admin, you can do this by using the [*EdgeEntraCopilotPageContext*](/en-us/copilot/manage#manage--chat-in-edge) group policy setting.

Here are some examples of private or organization web pages and document types that Copilot in Edge can summarize:

- Intranet sites such as SharePoint, except embedded Office documents
- Outlook Web App
- PDFs, including those stored on the local device
- Sites not protected by Microsoft Purview DLP policies, Mobile Application Management (MAM) policies, or MDM policies

Note

For the current list of document types supported by Copilot in Edge for analysis and summarization, see [Copilot in Edge webpage summarization behavior](/en-us/DeployEdge/edge-learnmore-copilot-page-summary-results).

Potentially sensitive organization sites and documents that Copilot in Edge can summarize could be stored in local, intranet, or cloud locations. This organization data can be exposed to an attacker who has access to the device and uses Copilot in Edge to quickly produce summarizations of documents and sites.

The organization data that can be summarized by Copilot in Edge can include:

- Local resources on the user’s computer

    PDFs or information displayed in an Edge browser tab by local apps that are not protected with MAM policies
- Intranet resources

    PDFs or sites for internal apps and services that are not protected by Microsoft Purview DLP policies, MAM policies, or MDM policies
- Microsoft 365 sites that are not protected by Microsoft Purview DLP policies, MAM policies, or MDM policies
- Microsoft Azure resources

    PDFs on virtual machines or sites for SaaS apps that are not protected by Microsoft Purview DLP policies, MAM policies, or MDM policies
- Third-party cloud product sites for cloud-based SaaS apps and services that are not protected by Microsoft Purview DLP policies, MAM policies, or MDA policies

Use this stage to implement levels of security to prevent bad actors from using Copilot to more quickly discover and access sensitive data. At a minimum, you must:

- [Deploy data security and compliance protections with Microsoft Purview](/en-us/purview/ai-microsoft-purview)
- [Configure minimum user permissions to data](zero-trust-microsoft-365-copilot#step-7-deploy-or-validate-minimum-user-permissions-to-data)
- [Deploy threat protection for cloud apps with Microsoft Defender for Cloud Apps](/en-us/defender-cloud-apps/what-is-defender-for-cloud-apps)

For more information about Copilot in Edge, see:

- [Copilot in Edge](/en-us/copilot/edge)
- [Copilot in Edge webpage summarization behavior](/en-us/DeployEdge/edge-learnmore-copilot-page-summary-results)

### Recommendations for E3 and E5

- Implement Intune [app protection policies (APP)](/en-us/microsoft-365/security/office-365-security/zero-trust-identity-device-access-policies-common#app-protection-policies) for data protection. APP can prevent the inadvertent or intentional copying of Copilot-generated content to apps on a device that aren’t included in the list of permitted apps. APP can limit the blast radius of an attacker using a compromised device.
- **E3**: [Deploy](/en-us/defender-xdr/pilot-deploy-defender-office-365) Microsoft Defender for Office 365 Plan 1 (included), which provides Safe Attachments, Safe Links, impersonation protection, and phishing email thresholds. Optionally, [purchase](https://www.microsoft.com/security/business/siem-and-xdr/microsoft-defender-office-365#Pricing) Plan 2 for advanced investigation and response.
- **E5**: [Configure Microsoft Defender for Office 365 Plan 2](/en-us/defender-office-365/mdo-deployment-guide).