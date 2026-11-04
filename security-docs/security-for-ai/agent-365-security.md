---
layout: Conceptual
title: Secure AI agents at scale using Microsoft Agent 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/security-for-ai/agent-365-security
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: guywild
author: guywi-ms
manager: orspodek
ms.service: security
ms.subservice: ''
description: How to use Microsoft Agent 365 to secure all of the AI agents in your environment.
ms.date: 2026-04-29T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.topic: concept-article
ms.collection:
- msftsolution-security-for-ai
- msftsolution-scenario
- zerotrust-solution
- msec-ai-copilot
locale: en-us
document_id: 164ee800-34b3-92ce-f8d7-c13aa49f2fbc
document_version_independent_id: 164ee800-34b3-92ce-f8d7-c13aa49f2fbc
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/security-for-ai/agent-365-security.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: security-for-ai/agent-365-security
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/security-for-ai/agent-365-security.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/302444b9-4a43-4841-8014-3d9e4251ff15
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
- https://authoring-docs-microsoft.poolparty.biz/devrel/57eae111-0f3b-497e-be07-450fd1409dea
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bebd8809-dac1-4c22-83e2-66d98af8a94d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ac8bf8ab-8134-4c9a-9f2e-58b31575b492
platformId: 7ae2657e-0c5f-8c6c-72f4-7f52c0b0b099
---

# Secure AI agents at scale using Microsoft Agent 365 | Microsoft Learn

As organizations adopt AI agents at scale, securing them has become a critical concern. [Microsoft Agent 365](/en-us/microsoft-agent-365/overview/) extends your existing security infrastructure – Microsoft Defender, Microsoft Entra, and Microsoft Purview – to agents, with purpose-built capabilities for securing agents.

This article outlines how Microsoft Agent 365 secures AI agents.

## A distributed security model with centralized visibility

AI agents introduce new security challenges, including:

- Agent sprawl from user-created and SaaS agents that expands the attack surface
- Over-privileged agents with excessive resource access
- Tool misuse when agents are manipulated into abusing authorized tools
- Misconfigured or vulnerable agents without proper authentication or boundaries
- Traditional AI threats, such as prompt injection and data leakage, that now extend across agent interactions

As part of Microsoft Agent 365, Microsoft Defender, Microsoft Entra, and Microsoft Purview now provide purpose-built controls for agents. Security practitioners continue working in the tools they already use, with agent insights and recommendations surfaced directly in each product's portal.

The Agent 365 overview in the Microsoft 365 admin center provides centralized visibility into AI agents across the organization, including usage insights and security signals that help administrators take action.

[![A screenshot showing the Agent 365 overview page in Microsoft 365 Admin Center.](media/agent-365-admin-center.png)](media/agent-365-admin-center.png#lightbox)

Security teams define governance requirements by creating policy templates, such as access packages in Microsoft Entra. During onboarding, IT teams apply these templates to agents, ensuring governance and compliance are enforced from the start.

## Access control with Microsoft Entra

Agents that sprawl or accumulate excessive permissions create risk. Microsoft Entra gives you visibility into all agent identities and helps enforce least-privilege access:

- **Visibility into agent identities** – Get the complete view of all agents in your organization, including agents with an Entra Agent ID, agents you register yourself, and shadow agents.

    [![A screenshot showing the agent identities tab in Microsoft 365 Admin Center.](media/agent-365-registry.png)](media/agent-365-registry.png#lightbox)
- **Conditional access and identity protection** – Extend conditional access and identity protection policies from users to agents. Enforce real-time access decisions based on agent context, risk level, and resource sensitivity.

    [![A screenshot showing the Conditional Access page in Microsoft 365 Admin Center.](media/agent-365-conditional-access.png)](media/agent-365-conditional-access.png#lightbox)
- **Secure Access Service Edge (SASE)** – Monitor and block malicious and non-compliant network traffic from agents running on user devices, including Copilot Studio agents.
- **Agent governance and lifecycles** – Ensure agents have responsible sponsors providing oversight, and manage access so it doesn't persist longer than needed.

Learn more about access control:

- [Protect agent identities with Microsoft Entra](/en-us/microsoft-agent-365/admin/capabilities-entra)
- [What is Microsoft agent identity platform?](/en-us/entra/agent-id/identity-platform/what-is-agent-id-platform)
- [Governing agent identities (Preview)](/en-us/entra/id-governance/agent-sponsor-tasks)
- [Conditional Access for Agent ID](/en-us/entra/identity/conditional-access/agent-id?tabs=custom-security-attributes)
- [Secure Access Service Edge for agents](/en-us/entra/global-secure-access/how-to-ai-prompt-shield)

## Data security with Microsoft Purview

Agents create, access, and share data across systems – increasing the risk of oversharing and sensitive data exposure. Microsoft Purview controls what data agents can access and how they use it, and helps you meet compliance obligations across the agent lifecycle:

- **Data security posture management** – Get deep interaction visibility for agents and identify AI-related data exposure risks.
- **Sensitivity labels** – Agents inherit and honor data sensitivity labels, ensuring consistent data protection across human and agent interactions.
- **Data loss prevention** – Block agents from accessing and sharing sensitive content based on data security labels and policies.
- **Insider risk management and communication compliance** – Detect risky activity and monitor interactions for policy violations.
- **Auditing** – Log and audit all agent interactions for compliance review and forensic investigation.
- **Data lifecycle management** – Apply retention and deletion policies to agent-generated content so data is kept only as long as needed.
- **eDiscovery** – Search, preserve, and export agent interactions and outputs to support legal, regulatory, and internal investigations.
- **Compliance Manager** – Assess agent instances against AI regulations using built-in assessments to track and improve your compliance posture.

[![A screenshot showing the Agent page in Microsoft Purview.](media/agent-365-purview.png)](media/agent-365-purview.png#lightbox)

Learn more about data security and compliance:

- [Data security in Microsoft Agent 365](/en-us/microsoft-agent-365/admin/data-security)
- [Microsoft Purview data security and compliance protections for Microsoft Agent 365](/en-us/purview/ai-agent-365)

## Threat protection with Microsoft Defender

Agents can be manipulated into misusing authorized tools, misconfigured without proper authentication, or targeted by prompt injection attacks. Microsoft Defender identifies these risks and enables rapid response:

- **Agent security posture management** – Identify and remediate agent misconfigurations and exposure risks. Visualize attack paths from agents to critical assets.

    [![A screenshot showing the Overview tab on the Agent page in Microsoft Defender.](media/agent-365-microsoft-defender-posture.png)](media/agent-365-microsoft-defender-posture.png#lightbox)
- **Threat detection and blocking** – Detect suspicious agent activity, receive alerts, and block malicious tool invocations in real-time.

    [![A screenshot showing the Incident page in Microsoft Defender.](media/agent-365-microsoft-defender-incident.png)](media/agent-365-microsoft-defender-incident.png#lightbox)
- **Threat investigation and hunting** – Collect unified agent observability logs and hunt for threats across agent activity.

    [![A screenshot showing the threat investigation and hunting page in Microsoft Defender.](media/agent-365-runtime-defense.png)](media/agent-365-runtime-defense.png#lightbox)

Learn more about threat protection:

- [AI agent inventory in Microsoft Defender XDR](/en-us/defender-xdr/security-for-ai/ai-agent-inventory)
- [AI agent detection and protection in Microsoft Defender XDR](/en-us/defender-xdr/security-for-ai/ai-agent-detection-protection)