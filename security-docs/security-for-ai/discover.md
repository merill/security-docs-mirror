---
layout: Conceptual
title: How do I discover AI apps and the sensitive data these use in my organization? | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/security-for-ai/discover
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: guywild
author: guywi-ms
manager: orspodek
ms.service: security
ms.subservice: ''
description: How to use Microsoft capabilities to discover AI apps and data use in your environment.
ms.date: 2025-04-01T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.topic: concept-article
ms.collection:
- msftsolution-security-for-ai
- msftsolution-scenario
- zerotrust-solution
- msec-ai-copilot
locale: en-us
document_id: a1b270bf-b96d-a5db-d8c7-b8a4f35467c5
document_version_independent_id: a1b270bf-b96d-a5db-d8c7-b8a4f35467c5
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/security-for-ai/discover.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: security-for-ai/discover
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/security-for-ai/discover.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
- https://authoring-docs-microsoft.poolparty.biz/devrel/57eae111-0f3b-497e-be07-450fd1409dea
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ac8bf8ab-8134-4c9a-9f2e-58b31575b492
platformId: 110a36b8-c496-9de2-b136-7f9e8004aecd
---

# How do I discover AI apps and the sensitive data these use in my organization? | Microsoft Learn

Generative AI (GenAI) is being adopted at an unprecedented rate as organizations actively engage with or experiment with GenAI in various capacities. Security teams can mitigate and manage risks more effectively by proactively gaining visibility into AI usage within the organization and implementing corresponding controls. This article describes how to discover AI app use within your organization, including assessing the risk to your sensitive data.

This is the second article in a series. Before using this article, be sure you accomplished the tasks in [Prepare for AI security](prepare) to prepare your environment with capabilities prescribed in this article.

![Diagram that shows the second article in series of security for ai, that is Discover.](media/security-for-ai-step-discover.svg)

Microsoft provides tools to help you gain visibility into data, access, user, and application risks for the AI you build and use. These capabilities help you proactively address vulnerabilities while you build a strong security posture for AI.

[![Diagram that shows the capabilities of discovering AI.](media/security-for-ai-discover-capabilities.svg)](media/security-for-ai-discover-capabilities.svg#lightbox)

The following table describes the illustration and also walks through the steps of implementing these capabilities.

| Step | Task | Scope |
| --- | --- | --- |
| 1 | Gain visibility into all agent identities created across Microsoft Copilot Studio and Microsoft Foundry with Microsoft Entra Agent ID. | Agents created in Microsoft Copilot Studio and Foundry |
| 2 | Gain visibility into AI usage with Microsoft Purview Data Security Posture Management (DSPM) for AI. Apply policies to protect sensitive data. | Copilots, agents, and other AI apps that use third-party large language modules (LLMs), including [Supported AI sites](/en-us/purview/ai-microsoft-purview-supported-sites). |
| 3 | Discover, sanction, and block AI apps with Microsoft Defender for Cloud Apps | SaaS AI apps |
| 4 | Discover deployed AI workloads in your environment and gain security insights with Microsoft Defender for Cloud Security Posture Management (CSPM) | Custom-built Azure AI based AI applications |

## Step 1—Gain visibility into agents with Entra Agent ID (Preview)

As organizations build and adopt AI agents, it’s challenging to keep track of these non-human actors. The very thing that makes these agents powerful—their ability to autonomously handle complex tasks and act like virtual teammates—also raises concerns. That’s why it’s critical to track agent identities, manage their lifecycle and permissions, and carefully secure their access to your organization’s resources.

Microsoft Entra Agent ID (Preview) provides unified directory of all agent identities created across Microsoft Copilot Studio and Foundry. This is a first step in providing even greater visibility, protection, and governance of the rapidly growing volume of agents in organizations.

| Task | Recommended resources |
| --- | --- |
| View all agents in your organization | sign in to the Microsoft Entra admin center and navigate to [Enterprise applications](https://entra.microsoft.com/#view/Microsoft_AAD_IAM/StartboardApplicationsMenuBlade/%7E/AppAppsPreview). In the filter bar at the top of the list view, set the Application type dropdown to Agent ID (Preview). Instantly, your enterprise application list will narrow down to show the AI agents (created via Copilot Studio or Foundry) that are registered in your tenant. |
| Learn more by reviewing this blog | [Announcing Microsoft Entra Agent ID: Secure and manage your AI agents](https://techcommunity.microsoft.com/blog/microsoft-entra-blog/announcing-microsoft-entra-agent-id-secure-and-manage-your-ai-agents/3827392) |

## Step 2—Gain visibility into AI usage with Data Security Posture Management (DSPM) for AI

Microsoft Purview Data Security Posture Management (DSPM) for AI focuses on how AI is used in your organization, especially how your data interacts with AI tools. It works with generative AI sites. DSPM for AI provides deeper insights for Microsoft Copilots and third-party SaaS applications like ChatGPT Enterprise and Google Gemini.

The following diagram shows one of the aggregated views into the impact of AI use on your data—Sensitive interactions per generative AI app.

[![Screenshot of the sensitive interactions per generative AI app.](media/ai-hub-sensitive-interactions-report.png)](media/ai-hub-sensitive-interactions-report.png#lightbox)

DSPM for AI offers a set of capabilities that help you safely adopt AI without having to choose between productivity and protection:

- Insights and analytics into AI activity in your organization
- Ready-to-use policies to protect data and prevent data loss in AI prompts
- Data risk assessments to identify, remediate, and monitor potential oversharing of data
- Recommended actions based on data in your tenant
- Compliance controls to apply optimal data handling and storing policies

To monitor interactions with third-party AI sites, devices must be onboarded to Microsoft Purview. If you followed the guidance in [Prepare for AI security](prepare), you enrolled devices into management with Microsoft Intune, then onboarded these devices into Defender for Endpoint. Device onboarding is shared across Microsoft 365 (including Microsoft Purview) and Microsoft Defender for Endpoint (MDE).

Use the following resources to discover AI apps and data with DSPM for AI.

| Task | Recommended resources |
| --- | --- |
| Ensure devices are onboarded to Microsoft Purview. | If devices aren't yet onboarded to Defender for Endpoint, there are several methods to get them onboarded. See, [Onboard Windows devices into Microsoft 365](/en-us/purview/device-onboarding-overview). |
| Understand prerequisites and how DSPM for AI works | [Considerations for deploying Microsoft Purview Data Security Posture Management for AI](/en-us/purview/ai-microsoft-purview-considerations) |
| Start using DSPM for AI | [How to use Data Security Posture Management for AI](/en-us/purview/ai-microsoft-purview#how-to-use-data-security-posture-management-for-ai) |
| Review supported AI sites | [Supported AI sites by Microsoft Purview for data security and compliance protections](/en-us/purview/ai-microsoft-purview-supported-sites) |

## Step 3—Discover, sanction, and block AI apps with Microsoft Defender for Cloud Apps

Microsoft Defender for Cloud Apps helps security teams discover SaaS GenAI apps and usage.

The Defender for Cloud Apps app catalog includes a Generative AI category for large language model (LLM) apps, like Microsoft Bing Chat, Google Bard, ChatGPT, and more. Defender for Cloud Apps has added more than a thousand generative AI-related apps to the catalog, providing visibility into how generative AI apps are used in your organization and helping you manage them securely.

[![Screenshot of searching apps in cloud app catalog.](media/generative-ai.png)](media/generative-ai.png#lightbox)

With Defender for Cloud Apps, you can:

- Filter on Generative AI apps
- Discover the AI apps which are used at your organization
- View out-of-the-box risk assessments for each app, including 90+ risk factors across security and regulatory compliance
- Sanction or unsanction (block) the usage of specific apps
- Create policies that continue to discover AI apps based on criteria you set, including risk score, number of users per day, and others. You can even automatically unsanction apps that meet the criteria.

[![Screenshot of the Cloud Discovery page in the Microsoft Defender.](media/cloud-discovery-defender-cloud-apps.png)](media/cloud-discovery-defender-cloud-apps.png#lightbox)

Use the following resources for next steps.

| Task | Recommended resources |
| --- | --- |
| Pilot and deploy Defender for Cloud Apps | [How do I pilot and deploy Microsoft Defender for Cloud Apps?](/en-us/defender-xdr/pilot-deploy-defender-cloud-apps?toc=%2Fsecurity%2Fzero-trust%2Ftoc.json&amp;bc=%2Fsecurity%2Fbreadcrumb%2Ftoc.json#step-5-discover-and-manage-cloud-apps) |
| Review this video tutorial | [Discover Which Generative AI Apps Are Used in Your Environment Using Defender for Cloud Apps](https://www.youtube.com/watch?v=ZQI4A7W4E_4) |
| View discovered apps | [View discovered apps with the Cloud discovery dashboard](/en-us/defender-cloud-apps/discovered-apps) |
| Find your cloud app and calculate risk score | [Cloud app catalog and risk scores - Microsoft Defender for Cloud Apps](/en-us/defender-cloud-apps/risk-score) |
| Govern discovered apps | [Govern discovered apps - Microsoft Defender for Cloud Apps](/en-us/defender-cloud-apps/governance-discovery) |

## Step 4—Discover deployed AI workloads in your environment and gain security insights with Microsoft Defender for Cloud

The Defender Cloud Security Posture Management (CSPM) plan in Microsoft Defender for Cloud provides AI security posture management capabilities, starting with discovery of AI Apps built in your environments:

- Discovering generative AI Bill of Materials (AI BOM), which includes application components, data, and AI artifacts from code to cloud.
- Strengthening generative AI application security posture with built-in recommendations and by exploring and remediating security risks.
- Using the attack path analysis to identify and remediate risks.

Use the cloud security explorer to identify generative AI workloads and models running in your environment. Cloud security explorer includes preconfigured queries:

- AI workloads and models in use
- Generative AI vulnerable code repositories that provision Azure OpenAI
- Containers running container images with known Generative AI vulnerabilities.

[![Screenshot of the AI workloads and models in use ](media/defender-for-cloud.png)](media/defender-for-cloud.png#lightbox)

You can also configure your own queries.

[![Screenshot of the configuration page to configure own queries.](media/defender-for-cloud-configure.png)](media/defender-for-cloud-configure.png#lightbox)

Use the following resources for next steps.

| Task | Recommended resources |
| --- | --- |
| Learn about AI security posture management | [AI security posture management with Defender for Cloud](/en-us/azure/defender-for-cloud/ai-security-posture) |
| Discover AI workloads | [AI workloads and models in use](/en-us/azure/defender-for-cloud/identify-ai-workload-model) |
| Explore risks to predeployment generative AI artifacts | [Risks to predeployment generative AI artifacts](/en-us/azure/defender-for-cloud/explore-ai-risk) |

## Next step for securing AI

After discovering the AI usage in your organization, the next step is to apply protections:

- Protect sensitive data used with AI apps
- Implement threat protection specifically for AI use

See the next article in this series: [How do I protect my organization while using AI apps?](protect)