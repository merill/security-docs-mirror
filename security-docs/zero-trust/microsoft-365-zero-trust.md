---
layout: Conceptual
title: Zero Trust deployment plan with Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/microsoft-365-zero-trust
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
ms.subservice: zero-trust
description: Learn how to apply Zero Trust security principles with Microsoft 365 to defend against threats and protect sensitive data.
ms.topic: solution-overview
ms.service: security
ms.localizationpriority: medium
ms.collection:
- m365solution-zerotrust
- m365solution-overview
- m365-security
- zerotrust-solution
- highpri
- tier1
ms.date: 2025-04-14T00:00:00.0000000Z
locale: en-us
document_id: b5008a63-8821-c0b2-0a7d-627e8b5fc6f2
document_version_independent_id: b5008a63-8821-c0b2-0a7d-627e8b5fc6f2
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/microsoft-365-zero-trust.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/microsoft-365-zero-trust
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/microsoft-365-zero-trust.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/a3955c7b-f5ee-420d-aff5-d7119738f38b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/b31948f4-2f38-404b-ac93-c3c8c5b3ae33
platformId: 45a52720-99d1-621f-92a5-0c020cbb2767
---

# Zero Trust deployment plan with Microsoft 365 | Microsoft Learn

This article provides a deployment plan for building **Zero Trust** security with Microsoft 365. Zero Trust is a security model that assumes breach and verifies each request as though it originated from an uncontrolled network. Regardless of where the request originates or what resource it accesses, the Zero Trust model teaches us to "never trust, always verify."

Use this article together with this poster.

| Item | Description |
| --- | --- |
| [![Illustration of the Microsoft 365 Zero Trust deployment plan.](media/m365-zero-trust-deployment-plan-thumb.png)](https://download.microsoft.com/download/f/d/b/fdb6ab0c-34bb-4cb8-84e6-5de8f13298da/m365-zero-trust-deployment-plan.pdf)[PDF](https://download.microsoft.com/download/f/d/b/fdb6ab0c-34bb-4cb8-84e6-5de8f13298da/m365-zero-trust-deployment-plan.pdf) | [Visio](https://download.microsoft.com/download/f/d/b/fdb6ab0c-34bb-4cb8-84e6-5de8f13298da/m365-zero-trust-deployment-plan.vsdx) Updated April 2025 | **Related solution guides**<br>- [Deploy your identity infrastructure for Microsoft 365](/en-us/microsoft-365/enterprise/deploy-identity-solution-overview)<br>- [Recommended identity and device access configurations](zero-trust-identity-device-access-policies-overview)<br>- [Manage devices with Intune](/en-us/microsoft-365/solutions/manage-devices-with-intune-overview)<br>- [Pilot and deploy Microsoft Defender XDR](/en-us/defender-xdr/pilot-deploy-overview)<br>- [Deploy an information protection solution with Microsoft Purview](/en-us/purview/information-protection-solution)<br>- [Discover, protect, and govern AI apps and data](/en-us/security/security-for-ai/)<br>- [Manage data privacy regulations with Microsoft 365](/en-us/microsoft-365/solutions/data-privacy-protection) |

## Zero Trust principles and architecture

Zero Trust is a security strategy. It isn't a product or a service, but an approach in designing and implementing the following set of security principles.

| Principle | Description |
| --- | --- |
| Verify explicitly | Always authenticate and authorize based on all available data points. |
| Use least privilege access | Limit user access with Just-In-Time and Just-Enough-Access (JIT/JEA), risk-based adaptive policies, and data protection. |
| Assume breach | Minimize blast radius and segment access. Verify end-to-end encryption and use analytics to get visibility, drive threat detection, and improve defenses. |

The guidance in this article helps you apply these principles by implementing capabilities with Microsoft 365.

A Zero Trust approach extends throughout the entire digital estate and serves as an integrated security philosophy and end-to-end strategy.

This illustration provides a representation of the primary elements that contribute to Zero Trust.

[![Diagram that shows the Zero Trust security architecture.](media/zero-trust/zero-trust-architecture.svg)](media/zero-trust/zero-trust-architecture.svg#lightbox)

In the illustration:

- Security policy enforcement is at the center of a Zero Trust architecture. This includes multifactor authentication with Conditional Access that takes into account user account risk, device status, and other criteria and policies that you set.
- Identities, devices, data, apps, network, and other infrastructure components are all configured with appropriate security. Policies that are configured for each of these components are coordinated with your overall Zero Trust strategy. For example, device policies determine the criteria for healthy devices and Conditional Access policies require healthy devices for access to specific apps and data.
- Threat protection and intelligence monitors the environment, surfaces current risks, and takes automated action to remediate attacks.

For more information about Zero Trust, see Microsoft's [***Zero Trust Guidance Center***](/en-us/security/zero-trust).

## Deploying Zero Trust for Microsoft 365

Microsoft 365 is built intentionally with many security and information protection capabilities to help you build Zero Trust into your environment. Many of the capabilities can be extended to protect access to other SaaS apps your organization uses and the data within these apps.

This illustration represents the work of deploying Zero Trust capabilities. This work is aligned to Zero Trust business scenarios in the [Zero Trust adoption framework](/en-us/security/zero-trust/adopt/zero-trust-adoption-overview).

[![Diagram that shows the Microsoft 365 Zero Trust deployment plan across five swim lanes.](media/zero-trust/m365-zero-trust-deployment-swim-lanes.svg)](media/zero-trust/m365-zero-trust-deployment-swim-lanes.svg#lightbox)

In this illustration the deployment work is categorized into five swim lanes:

- **Secure remote and hybrid work** — This work builds a foundation of identity and device protection.
- **Prevent or reduce business damage from a breach** — Threat protection provides real-time monitoring and remediation of security threats. Defender for Cloud Apps provides discovery of SaaS apps, including AI apps, and allows you to extend data protection to these apps.
- **Identify and protect sensitive business data** — Data protection capabilities provide sophisticated controls targeted at specific types of data to protect your most valuable information.
- **Secure AI apps and data** — Rapidly protect your organization's use of AI apps and the data these interact with.
- **Meet regulatory and compliance requirements** — Understand and track your progress toward complying with regulations that affect your organization.

This article assumes you're using cloud identity. If you need guidance for this objective, see [**Deploy your identity infrastructure for Microsoft 365**](/en-us/microsoft-365/enterprise/deploy-identity-solution-overview).

Tip

When you understand the steps and the end-to-end deployment process, you can use the [Set up your Microsoft Zero Trust security model](https://go.microsoft.com/fwlink/?linkid=2224820) advanced deployment guide when signed in to the Microsoft 365 admin center. This guide steps you through applying Zero Trust principles for standard and advanced technology pillars.

## Swim lane 1 — Secure remote and hybrid work

Securing remote and hybrid work involves configuring identity and device access protection. These protections contribute to the Zero Trust principle **verify explicitly**.

Accomplish the work of securing remote and hybrid work in three phases.

#### Phase 1 — Implement starting-point identity and device access policies

Microsoft recommends a comprehensive set of identity and device access policies for Zero Trust in this guide — [Zero Trust identity and device access configurations](/en-us/security/zero-trust/zero-trust-identity-device-access-policies-overview).

In phase 1, start by implementing the starting-point tier. These policies don't require enrolling devices into management.

[![Diagram that shows the Zero Trust identity and access policies for the Starting-point tier.](media/zero-trust/identity-access-starting-point-tier.svg)](media/zero-trust/identity-access-starting-point-tier.svg#lightbox)

Go to [***Zero Trust identity and device access protection***](zero-trust-identity-device-access-policies-overview) for detailed prescriptive guidance. This series of articles describes a set of identity and device access prerequisite configurations and a set of Microsoft Entra Conditional Access, Microsoft Intune, and other policies to secure access to Microsoft 365 for enterprise cloud apps and services, other SaaS services, and on-premises applications published with Microsoft Entra application proxy.

| Includes | Prerequisites | Doesn't include |
| --- | --- | --- |
| Recommended identity and device access policies for three levels of protection: <br>- Starting point<br>- Enterprise (recommended)<br>- Specialized<br><br> More recommendations for: <br>- External users (guests)<br>- Microsoft Teams<br>- SharePoint | Microsoft E3 or E5  Microsoft Entra ID in either of these modes: <br>- Cloud-only<br>- Hybrid with password hash sync (PHS) authentication<br>- Hybrid with pass-through authentication (PTA)<br>- Federated | Device enrollment for policies that require managed devices. See [Manage devices with Intune](/en-us/microsoft-365/solutions/manage-devices-with-intune-overview) to enroll devices. |

#### Phase 2 — Enroll devices into management with Intune

Next, enroll your devices into management and begin protecting them with more sophisticated controls.

See [***Manage devices with Intune***](/en-us/microsoft-365/solutions/manage-devices-with-intune-overview) for detailed prescriptive guidance on enrolling devices into management.

| Includes | Prerequisites | Doesn't include |
| --- | --- | --- |
| Enroll devices with Intune: <br>- Corporate-owned devices<br>- Autopilot/automated<br>- enrollment<br><br> Configure policies: <br>- App Protection policies<br>- Compliance policies<br>- Device profile policies | Register endpoints with Microsoft Entra ID | Configuring information protection capabilities, including: <br>- Sensitive information types<br>- Labels<br>- DLP policies<br><br> For these capabilities, see Swim lane 3 — Identify and protect sensitive business data (later in this article). |

For more information, see [Zero Trust for Microsoft Intune](/en-us/mem/intune/fundamentals/zero-trust-with-microsoft-intune).

#### Phase 3 — Add Zero Trust identity and device access protection: Enterprise policies

With devices enrolled into management, you can now implement the full set of recommended Zero Trust identity and device access policies, requiring compliant devices.

Return to [***Common identity and device access policies***](zero-trust-identity-device-access-policies-common) and add the policies in the Enterprise tier.

[![Diagram that shows the Zero Trust identity and access policies for the Enterprise (recommended) tier.](media/zero-trust/identity-access-enterprise-tier.svg)](media/zero-trust/identity-access-enterprise-tier.svg#lightbox)

Read more about how to secure remote and hybrid work in the **Zero Trust adoption framework** — [Secure remote and hybrid work](/en-us/security/zero-trust/adopt/secure-remote-hybrid-work).

## Swim lane 2 — Prevent or reduce business damage from a breach

Microsoft Defender XDR is an extended detection and response (XDR) solution that automatically collects, correlates, and analyzes signal, threat, and alert data from across your Microsoft 365 environment, including endpoint, email, applications, and identities. Additionally, Microsoft Defender for Cloud Apps helps organizations identify and manage access to SaaS apps, including GenAI apps.

Prevent or reduce business damage from a breach by piloting and deploying Microsoft Defender XDR.

[![Diagram that shows the process of adding Microsoft Defender XDR to the Zero Trust architecture.](media/zero-trust/m365-zero-trust-architecture-defender.svg)](media/zero-trust/m365-zero-trust-architecture-defender.svg#lightbox)

Go to [***Pilot and deploy Microsoft Defender XDR***](/en-us/defender-xdr/pilot-deploy-overview) for a methodical guide to piloting and deploying Microsoft Defender XDR components.

| Includes | Prerequisites | Doesn't include |
| --- | --- | --- |
| Set up the evaluation and pilot environment for all components: <br>- [Defender for Identity](/en-us/defender-for-identity/zero-trust)<br>- [Defender for Office 365](/en-us/defender-office-365/zero-trust-with-microsoft-365-defender-office-365)<br>- [Defender for Endpoint](/en-us/defender-endpoint/zero-trust-with-microsoft-defender-endpoint)<br>- [Defender for Cloud Apps](/en-us/defender-cloud-apps/zero-trust)<br><br> Protect against threats  Investigate and respond to threats | See the guidance to read about the architecture requirements for each component of Microsoft Defender XDR. | Microsoft Entra ID Protection isn't included in this solution guide. It's included in Swim lane 1 — Secure remote and hybrid work. |

Read more about how to prevent or reduce business damage from a breach in the **Zero Trust adoption framework** — [Prevent or reduce business damage from a breach](/en-us/security/zero-trust/adopt/prevent-reduce-business-damage-breach).

## Swim lane 3 — Identify and protect sensitive business data

Implement Microsoft Purview Information Protection to help you discover, classify, and protect sensitive information wherever it lives or travels.

Microsoft Purview Information Protection capabilities are included with Microsoft Purview and give you the tools to know your data, protect your data, and prevent data loss. You can begin this work anytime.

Microsoft Purview Information Protection provides a framework, process, and capabilities you can use to accomplish your specific business objectives.

![Diagram that shows the overview of Microsoft Purview Information Protection.](media/zero-trust/m365-protection-solution-overview.png)

For more information on how to plan and deploy information protection, see [***Deploy a Microsoft Purview Information Protection solution***](/en-us/purview/information-protection-solution).

Read more about how to identify and protect sensitive business data in the **Zero Trust adoption framework** — [Identify and protect sensitive business data](/en-us/security/zero-trust/adopt/identify-protect-sensitive-business-data).

## Swim lane 4 — Secure AI apps and data

Microsoft 365 includes capabilities to help organizations rapidly secure AI apps and the data these use.

Start by using Purview Data Security Posture Management (DSPM) for AI. This tool focuses on how AI is used in your organization, especially your sensitive data that interacts with AI tools. DSPM for AI provides deeper insights for Microsoft Copilots and third-party SaaS applications like ChatGPT Enterprise and Google Gemini.

The following diagram shows one of the aggregated views into the impact of AI use on your data—Sensitive interactions per generative AI app.

[![Diagram that shows the sensitive interactions per generative AI app.](media/zero-trust/ai-hub-sensitive-interactions-report.png)](media/zero-trust/ai-hub-sensitive-interactions-report.png#lightbox)

Use DSPM for AI to:

- Gain visibility into AI usage, including sensitive data.
- Review data assessments to learn about gaps in oversharing that can be mitigated with SharePoint oversharing controls.
- Find gaps in your policy coverage for sensitivity labels and data loss prevention (DLP) policies.

Defender for Cloud Apps is another powerful tool to discover and govern SaaS GenAI apps and usage. Defender for Cloud Apps includes more than a thousand generative AI-related apps in the catalog, providing visibility into how generative AI apps are used in your organization and helping you manage them securely.

In addition to these tools, Microsoft 365 provides a comprehensive set of capabilities for securing and governing AI. See [**Discover, protect, and govern AI apps and data**](/en-us/security/security-for-ai) to learn how to get started with these capabilities.

[![Diagram that shows the Microsoft 365 capabilities for protecting and governing AI.](media/zero-trust/security-for-ai-m365-composite.svg)](media/zero-trust/security-for-ai-m365-composite.svg#lightbox)

The following table lists the Microsoft 365 capabilities with links to more information in the [Security for AI library](/en-us/security/security-for-ai).

| Capability | More information |
| --- | --- |
| SharePoint oversharing controls, including SharePoint Advanced Management | [Apply SharePoint oversharing controls](/en-us/security/security-for-ai/protect#step-1--apply-sharepoint-oversharing-controls) |
| DSPM for AI | [Gain visibility into AI usage with (DSPM) for AI](/en-us/security/security-for-ai/discover#step-1gain-visibility-into-ai-usage-with-data-security-posture-management-dspm-for-ai)[Protect data through DSPM for AI](/en-us/security/security-for-ai/protect#step-2--protect-data-through-dspm-for-ai) |
| Sensitivity labels and DLP policies | [Continue to identify gaps in sensitivity labels and DLP policies](/en-us/security/security-for-ai/protect#step-3continue-to-identify-gaps-in-sensitivity-labels-and-dlp-policies) |
| Insider Risk Management (IRM) — Risky AI usage policy template | [Apply the Risky AI template](/en-us/security/security-for-ai/protect#step-4apply-the-risky-ai-template-in-insider-risk-management-irm) |
| Adaptive protection | [Configure Adaptive Protection for Insider Risk Management](/en-us/security/security-for-ai/protect#step-5configure-adaptive-protection-for-insider-risk-management) |
| Defender for Cloud Apps | [Discover, sanction, and block AI apps](/en-us/security/security-for-ai/discover#step-2discover-sanction-and-block-ai-apps-with-microsoft-defender-for-cloud-apps)[Triage and protect use of AI apps](/en-us/security/security-for-ai/protect#step-1use-defender-for-cloud-apps-to-triage-and-protect-use-of-ai-apps)[Manage AI apps based on compliance risk](/en-us/security/security-for-ai/govern#step-2use-defender-for-cloud-apps) |
| Purview Compliance Manager | [Build and manage assessments for AI-related regulations](/en-us/security/security-for-ai/govern#step-1build-and-manage-assessments-in-microsoft-purview-compliance-manager) |
| Purview Communication Compliance | [Analyze prompts and responses entered into generative AI applications to help detect inappropriate or risky interactions or sharing of confidential information](/en-us/security/security-for-ai/govern#step-4configure-purview-communication-compliance) |
| Purview Data Lifecycle Management | [Proactively delete content you’re no longer required to keep to reduce the risk of data overexposure in AI tools](/en-us/security/security-for-ai/govern#step-5configure-purview-data-lifecycle-management) |
| eDiscovery | [Search for keywords in prompts and responses, manage the results within eDiscovery cases](/en-us/security/security-for-ai/govern#step-6use-ediscovery-together-with-audit-logs-for-microsoft-365-copilot) |
| Audit logs for Copilot and AI activities | [identify how, when, and where Copilot interactions occurred and which items were accessed, including any sensitivity labels on those items](/en-us/security/security-for-ai/govern#step-6use-ediscovery-together-with-audit-logs-for-microsoft-365-copilot) |
| Priva Privacy Assessments | [Initiate privacy impact assessments for AI apps you build](/en-us/security/security-for-ai/govern#step-7use-priva-privacy-assessments) |

## Swim lane 5 — Meet regulatory and compliance requirements

Regardless of the complexity of your organization’s IT environment or the size of your organization, new regulatory requirements that might affect your business are continually adding up. A Zero Trust approach often exceeds some types of requirements imposed by compliance regulations, for example, those controlling access to personal data. Organizations that have implemented a Zero Trust approach may find that they already meet some new conditions or can easily build upon their Zero Trust architecture to be compliant.

Microsoft 365 includes capabilities to assist with regulatory compliance, including:

- Compliance Manager
- Content explorer
- Retention policies, sensitivity labels, and DLP policies
- Communication compliance
- Data lifecycle management
- Priva Privacy Risk Management

Use the following resources to meet regulatory and compliance requirements.

| Resource | More information |
| --- | --- |
| Zero Trust adoption framework — [Meet regulatory and compliance requirements](/en-us/security/zero-trust/adopt/meet-regulatory-compliance-requirements) | Describes a methodical approach your organization can follow, including defining strategy, planning, adopting, and governing. |
| [Govern AI apps and data for regulatory compliance](/en-us/security/security-for-ai/govern) | Addresses regulatory compliance for the emerging AI-related regulations, including specific capabilities that help. |
| [Manage data privacy and data protection with Microsoft Priva and Microsoft Purview](/en-us/microsoft-365/solutions/data-privacy-protection) | Assess risks and take appropriate action to protect personal data in your organization's environment using Microsoft Priva and Microsoft Purview. |