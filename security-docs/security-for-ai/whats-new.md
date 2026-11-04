---
layout: Conceptual
title: What's new in Microsoft AI security? | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/security-for-ai/whats-new
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: guywild
author: guywi-ms
manager: orspodek
ms.service: security
ms.subservice: ''
description: What are new Microsoft AI security capabilities and blog articles?
ms.date: 2026-04-28T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.topic: concept-article
ms.collection:
- msftsolution-security-for-ai
- msftsolution-scenario
- zerotrust-solution
- msec-ai-copilot
locale: en-us
document_id: d24ba350-7415-c94b-4bff-c64c8770cf62
document_version_independent_id: d24ba350-7415-c94b-4bff-c64c8770cf62
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/security-for-ai/whats-new.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: security-for-ai/whats-new
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/security-for-ai/whats-new.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
- https://authoring-docs-microsoft.poolparty.biz/devrel/57eae111-0f3b-497e-be07-450fd1409dea
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ac8bf8ab-8134-4c9a-9f2e-58b31575b492
platformId: 1db09380-82cc-7bb7-3717-c88fddb0218f
---

# What's new in Microsoft AI security? | Microsoft Learn

This article lists new capabilities and resources (blogs and videos) related to Microsoft AI security.

## April 2026

| Product | Feature updates |
| --- | --- |
| Security Dashboard for AI | - [General availability of Security Dashboard for AI](security-dashboard-for-ai)- **Security Reader role support** — Minimum Microsoft Entra role required to view all dashboard data and assign recommendations. See [Permissions](security-dashboard-for-ai#permissions).- **Recommendation assignments with due dates** — Assign recommendations to users or groups with due date tracking and Teams or email notifications. |

## November 2025

| Product | Feature updates |
| --- | --- |
| Microsoft Agent 365 (Preview) | [Microsoft Agent 365 is a unified control plane that lets you secure AI agents across the enterprise](agent-365-security) |
| Microsoft Purview | - [Data Loss Prevention (DLP) enforcement, insider risk management, audit, and compliance for agents](https://techcommunity.microsoft.com/blog/microsoft-security-blog/announcing-new-microsoft-purview-capabilities-to-protect-genai-agents/4470696)- [Enhanced Data Security Posture Management](https://techcommunity.microsoft.com/blog/microsoft-security-blog/beyond-visibility-the-new-microsoft-purview-data-security-posture-management-dsp/4470984)- [Enhanced security for Microsoft 365 Copilot](https://techcommunity.microsoft.com/blog/microsoft-security-blog/announcing-new-microsoft-purview-capabilities-to-protect-genai-agents/4470696) - Including data loss prevention, priority cleanup for Microsoft 365 Copilot assets, and on-demand classification for meeting transcripts- [AI regulation compliance capabilities](https://techcommunity.microsoft.com/blog/microsoft-security-blog/announcing-new-microsoft-purview-capabilities-to-protect-genai-agents/4470696) - Including AI-powered regulatory templates, visibility into agent activity, monitoring for risky agent prompts and responses, retention and deletion policies for agent-generated content |
| Microsoft Entra | - [Microsoft Entra Agent ID](/en-us/entra/agent-id/identity-platform/what-is-agent-id-platform) - Identity and access management capabilities specifically designed for AI agents, applying Zero Trust principles to autonomous systems.- [Conditional Access for Agent ID (Preview)](/en-us/entra/identity/conditional-access/agent-id?tabs=custom-security-attributes) - Extends the same Zero Trust conditional access controls that already protect human users and apps to your agents. - [Microsoft Entra Agent Platform](/en-us/entra/agent-id/identity-platform/what-is-agent-id-platform) - A developer-first platform for managing AI agent identities and access - [Microsoft Entra Agent Registry](/en-us/entra/agent-id/identity-platform/what-is-agent-registry) - Provides a complete inventory of all agents used in your organization, including Microsoft and third-party agents.  - [Agent risk management in Microsoft Entra ID Protection (Preview)](/en-us/entra/id-protection/concept-risky-agents)- [AI Prompt Shield (Preview)](/en-us/entra/global-secure-access/how-to-ai-prompt-shield) - Real-time blocking of prompt injection attacks at the network layer- [Specialized roles for Agent ID management](/en-us/entra/agent-id/identity-platform/agent-owners-sponsors-managers) |
| Microsoft Defender | [Security posture management and threat protection for agents](https://techcommunity.microsoft.com/blog/microsoft-security-blog/start-secure-and-stay-secure-on-your-ai-agent-journey-with-microsoft-defender/4469430), including:  - [Microsoft Copilot Studio AI agent protection (Preview)](/en-us/defender-cloud-apps/ai-agent-protection) - [Security posture management for AI apps and agents](/en-us/azure/defender-for-cloud/ai-security-posture) |
| Microsoft Foundry (formerly called Azure AI Foundry) | [Agent control plane for Microsoft Foundry](/en-us/azure/ai-foundry/control-plane/overview):  - Secure, observe, and operate agents directly in Microsoft Foundry - Identify code and runtime risks in Microsoft Defender and auto-fix in GitHub with Copilot |

**Additional blogs, videos, and other resources**

- [Microsoft Agent 365: The control plane for AI agents](https://www.microsoft.com/en-us/microsoft-365/blog/2025/11/18/microsoft-agent-365-the-control-plane-for-ai-agents/)
- [Security as the core primitive in the agentic era: New innovations to secure AI agents and apps](https://techcommunity.microsoft.com/blog/microsoft-security-blog/security-as-the-core-primitive-in-the-agentic-era-new-innovations-to-secure-ai-a/4470197)

## May 2025

| Product | Feature updates |
| --- | --- |
| Microsoft Purview | Microsoft Purview capabilities extended to support custom-built AI apps and agents - [Data security and compliance controls through Microsoft Purview native integration with Microsoft Foundry](https://www.microsoft.com/security/blog/2025/05/19/microsoft-extends-zero-trust-to-secure-the-agentic-workforce/) - [Data security and compliance controls extended to any new custom AI app with Microsoft Purview Software Development Kit (SDK)](https://aka.ms/SecurityforAIBuildnews) - [Purview data protections extended to Copilot Studio agents grounded in Microsoft Dataverse data](https://aka.ms/SecurityforAIBuildnews) - [Purview DSPM for AI can now provide visibility into unauthenticated interactions with Copilot Studio agents](https://techcommunity.microsoft.com/blog/microsoft-security-blog/enterprise-grade-controls-for-ai-apps-and-agents-built-with-azure-ai-foundry-and/4414757) - [Data Loss Prevention (DLP) for Microsoft 365 Copilot Agents](https://aka.ms/SecurityforAIBuildnews)[Public Preview of DLP for Microsoft 365 Copilot in Word, Excel, and PowerPoint](https://techcommunity.microsoft.com/blog/microsoft-security-blog/announcing-public-preview-of-dlp-for-m365-copilot-in-word-excel-and-powerpoint/4409809)[DSPM discoverability for Communication Compliance (public preview)](https://techcommunity.microsoft.com/blog/microsoft-security-blog/enhance-ai-security-and-governance-across-multi-model-and-multi-cloud-environmen/4395593) |
| Microsoft Entra | [Microsoft Entra Agent ID](https://techcommunity.microsoft.com/blog/microsoft-entra-blog/announcing-microsoft-entra-agent-id-secure-and-manage-your-ai-agents/3827392)—unified directory of all agent identities created across Microsoft Copilot Studio and Foundry |
| Defender for Cloud | [Microsoft Defender security alerts and recommendations now available in Foundry (Preview)](https://techcommunity.microsoft.com/blog/microsoft-security-blog/enterprise-grade-controls-for-ai-apps-and-agents-built-with-azure-ai-foundry-and/4414757)[General Availability for Defender for Foundry Tools](/en-us/azure/defender-for-cloud/release-notes#general-availability-for-defender-for-ai-services)[General Availability Data and AI security dashboard](/en-us/azure/defender-for-cloud/release-notes#general-availability-data-and-ai-security-dashboard) |
| Foundry | [Foundry enhancements for model security and safety](https://techcommunity.microsoft.com/blog/microsoft-security-blog/enterprise-grade-controls-for-ai-apps-and-agents-built-with-azure-ai-foundry-and/4414757):  - **Spotlighting** to detect and block prompt injection attacks in real time  - **Task adherence evaluation and mitigation** to ensure agents remain within scope  - **Continuous evaluation and monitoring of agentic system**[Foundry evaluation integrations with Microsoft Purview, Credo AI, and Saidot](https://techcommunity.microsoft.com/blog/microsoft-security-blog/enterprise-grade-controls-for-ai-apps-and-agents-built-with-azure-ai-foundry-and/4414757) |

**Additional blogs, videos, and other resources**

- [Enterprise-grade controls for AI apps and agents built with Foundry and Copilot Studio](https://techcommunity.microsoft.com/blog/microsoft-security-blog/enterprise-grade-controls-for-ai-apps-and-agents-built-with-azure-ai-foundry-and/4414757) (May 19, 2025)
- [Microsoft extends Zero Trust to secure the agentic workforce](https://www.microsoft.com/en-us/security/blog/2025/05/19/microsoft-extends-zero-trust-to-secure-the-agentic-workforce/) (May 19, 2025)
- [Announcing Microsoft Entra Agent ID: Secure and manage your AI agents](https://techcommunity.microsoft.com/blog/microsoft-entra-blog/announcing-microsoft-entra-agent-id-secure-and-manage-your-ai-agents/3827392) (May 19, 2025)
- [Microsoft Purview SDK Public Preview](https://techcommunity.microsoft.com/blog/microsoft-security-blog/microsoft-purview-sdk-public-preview/4414240)

## April 2025

| Product | Feature updates |
| --- | --- |
| Microsoft Purview and Edge for Business | [Enhanced Purview data security capabilities for the browser—inline discovery & protection controls](https://techcommunity.microsoft.com/blog/microsoft-security-blog/building-layered-protection-new-microsoft-purview-data-security-controls-for-the/4395071) |
| Microsoft Purview | [New data security capabilities for the network—integration with your SASE technology of choice](https://techcommunity.microsoft.com/blog/microsoft-security-blog/building-layered-protection-new-microsoft-purview-data-security-controls-for-the/4395071)[On-demand classification for SharePoint and OneDrive (public preview)](https://techcommunity.microsoft.com/blog/microsoft-security-blog/protecting-sensitive-information-in-the-era-of-ai-with-microsoft-purview-informa/4395541)[Protection policies for Azure SQL, Data Lake, and Blob Storage (public preview)](https://techcommunity.microsoft.com/blog/azurestorageblog/microsoft-purview-protection-policies-for-azure-data-lake--blob-storage-availabl/4382887)[Optical character recognition enhancements](https://techcommunity.microsoft.com/blog/microsoft-security-blog/protecting-sensitive-information-in-the-era-of-ai-with-microsoft-purview-informa/4395541)[Dynamic watermarking in Word, Excel, and PowerPoint (general availability)](https://techcommunity.microsoft.com/blog/microsoft-security-blog/general-availability-dynamic-watermarking-for-sensitivity-labels-in-word-excel-a/4382614) |
| Microsoft Entra Internet Access | [Granular access controls for generative AI apps](https://techcommunity.microsoft.com/blog/microsoft-entra-blog/new-innovations-in-microsoft-entra-to-strengthen-ai-security-and-identity-protec/3827393) |
| Defender for Cloud | [AI Posture Management in GCP vertex AI (Preview)](/en-us/azure/defender-for-cloud/release-notes#ai-posture-management-in-gcp-vertex-ai-preview) |

**Additional blogs, videos, and other resources**

- [Microsoft 365 Copilot: Built for the era of human–agent collaboration](https://www.microsoft.com/en-us/microsoft-365/blog/2025/04/23/microsoft-365-copilot-built-for-the-era-of-human-agent-collaboration/)
- [RSAC™ 2025: Unveiling new innovations in cloud and AI security](https://techcommunity.microsoft.com/blog/microsoftdefendercloudblog/rsac%E2%84%A2-2025-unveiling-new-innovations-in-cloud-and-ai-security/4408140)
- [How to use DSPM for AI Data Risk Assessment to Address Internal Oversharing](https://techcommunity.microsoft.com/blog/microsoft-security-blog/how-to-use-dspm-for-ai-data-risk-assessment-to-address-internal-oversharing/4399785)
- [Explore practical best practices to secure your data with Microsoft Purview](https://www.microsoft.com/en-us/security/blog/2025/04/25/explore-practical-best-practices-to-secure-your-data-with-microsoft-purview/)
- [Enhance AI security and governance across multi-model and multicloud environments](https://techcommunity.microsoft.com/blog/microsoft-security-blog/enhance-ai-security-and-governance-across-multi-model-and-multi-cloud-environmen/4395593)

## Additional what's new resources

- [What's new in Microsoft Purview](/en-us/purview/whats-new)
- [What's new in Compliance Manager](/en-us/purview/compliance-manager-whats-new)
- [What's new in Microsoft Priva](/en-us/privacy/priva/priva-whats-new)
- [What's new in Microsoft Defender for Cloud Apps](/en-us/defender-cloud-apps/release-notes)
- [What's new in Defender for Cloud](/en-us/azure/defender-for-cloud/release-notes)
- What's new in Foundry: [Foundry blog](https://devblogs.microsoft.com/foundry/)
- [What's new in Azure AI Content Safety](/en-us/azure/ai-services/content-safety/whats-new)