---
layout: Conceptual
title: Security for the AI era | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/saf/scenarios/ai-security/overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Learn how to secure AI, strengthen security foundations, defend with AI agents, secure AI agents, and use the Microsoft Security Adoption Framework to turn AI-era security priorities into action.
ms.date: 2026-11-15T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 17da4563-6124-7b17-0822-daaf11586eab
document_version_independent_id: 17da4563-6124-7b17-0822-daaf11586eab
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/saf/scenarios/ai-security/overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../../../zero-trust/toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: saf/scenarios/ai-security/overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/saf/scenarios/ai-security/overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 0eb980a5-2e62-c85c-c0c4-dac7943f24f1
---

# Security for the AI era | Microsoft Learn

AI is changing the speed, scale, and economics of cybersecurity. Attackers can discover and exploit weaknesses faster. Organizations are deploying AI agents that can access sensitive data and tools. Security teams must operate at machine speed without giving up human judgment, control, and accountability.

Three connected priorities are emerging for this environment: secure your foundations, defend with agents, and secure your agentic insider. Together, they help organizations adopt AI with confidence while strengthening protection across the existing digital estate.

Microsoft security guidance helps organizations turn these priorities into action by connecting business priorities and risk to governance, operating-model changes, roles, security disciplines, and technology implementation.

## Why security must change for the AI era

AI amplifies existing exposure, enables attacks to operate with greater autonomy, and introduces agents that can act as trusted participants inside the organization. Security must address three connected challenges:

- **AI-amplified exposure:** AI makes existing identity, data, software, infrastructure, and configuration weaknesses easier to find and exploit.
- **Autonomous attacks:** AI can reduce the time and expertise required to discover, develop, and execute attacks.
- **Agentic-insider risk:** AI agents can use identities, access data, invoke tools, communicate with services, and take actions that affect business processes.

Organizations need security capabilities that can keep pace with AI-enabled change and threats while keeping people responsible for policy, risk acceptance, and consequential decisions.

## Strategic security priorities for the AI era

As organizations expand their use of AI, three connected priorities are shaping security strategy and near-term action: strengthen the foundations that AI depends on, use agents to improve defense, and govern agents that operate with trusted access.

### Secure your foundations

Reduce preventable exposure and strengthen the identity, data, development, infrastructure, endpoint, network, operational, and governance capabilities on which AI depends. Prioritize risk, coordinate ownership, apply Zero Trust principles, and measure continuous improvement.

### Defend with agents

Use AI-assisted and agentic capabilities to increase the speed, reach, consistency, and quality of security operations. Redesign suitable workflows so agents perform repeatable analysis and response while people retain judgment, approval authority, and accountability.

### Secure your agentic insider

An AI agent isn't a person and isn't inherently malicious, but it can have insider-like access and must be governed and monitored. The "agentic insider" analogy describes an agent that has legitimate access and can take actions with business impact.

Know which agents exist, who owns them, which identities they use, what data and tools they can access, and what actions they can take. Apply least privilege, lifecycle governance, monitoring, containment, and incident response so intended, mistaken, manipulated, or compromised behavior remains within acceptable risk boundaries.

## Secure AI across its lifecycle

Securing AI systems and agents requires a full lifecycle approach across four connected areas:

- **Discover and understand:** Inventory AI applications and agents. Identify ownership, identities, data paths, connected tools, permissions, usage, and risk.
- **Protect and govern:** Protect identities, data, applications, models, endpoints, infrastructure, networks, and runtimes. Define policy, ownership, approval, and evidence requirements.
- **Constrain and contain:** Apply least privilege, task- and time-bound access, network and execution controls, policy enforcement, isolation, and recovery options.
- **Monitor, respond, and adapt:** Observe behavior and changing risk. Detect unsafe or compromised activity, respond quickly, and adjust access, policy, monitoring, and controls.

## Turn priorities into action

Addressing these priorities requires coordinated changes across strategy, governance, people, processes, and technology. Microsoft provides technology and guidance to help organizations plan and implement these changes.

### Plan and organize

Build a clear path from business priorities and security risks to the people, processes, and technology needed to manage them. Use Microsoft security guidance to:

- **Define outcomes and risks.** Identify the business outcomes you’re enabling, the risks that could affect them, and the security outcomes needed to manage those risks.
- **Establish governance and accountability.** Define policies, decision rights, responsibilities, delegated authority, and risk ownership.
- **Design the operating model.** Define how people, AI agents, automation, security teams, technology teams, and business stakeholders work together.
- **Coordinate security disciplines.** Connect the specialized security work required across identity, data, applications, infrastructure, devices, security operations, AI, and other areas.
- **Select and prioritize controls.** Translate risks and security outcomes into technology and process requirements.
- **Implement the controls.** Use Microsoft product guidance and reference architectures to configure, deploy, and operate the required capabilities.
- **Measure and improve.** Track risk reduction, operational effectiveness, resilience, and business outcomes.

The [Microsoft Security Adoption Framework (SAF)](/en-us/security/saf/) connects these activities through guidance for security strategy, governance, operating models, security disciplines, technologies, and adoption. Zero Trust principles are embedded throughout SAF to guide security decisions across these areas. Learn more in the [Zero Trust Guidance Center](/en-us/security/zero-trust/).

### Implement and operate

Use Microsoft security capabilities to implement controls, perform analysis, and automate security processes so that you can continuously improve protection and response. These are key examples of relevant Microsoft technologies and guidance:

| Strategic priority | Representative Microsoft connections | Primary outcome |
| --- | --- | --- |
| **Secure your foundations** | [Microsoft Security Exposure Management](/en-us/security-exposure-management/); [Microsoft Entra](/en-us/entra/); [Microsoft Purview](/en-us/purview/); [Microsoft Defender](/en-us/defender/); Microsoft Intune; [Microsoft Sentinel and integrated security operations](/en-us/azure/sentinel/); [Zero Trust and SFI-aligned guidance](/en-us/security/zero-trust/). | Reduce preventable exposure and strengthen the controls on which AI depends. |
| **Defend with agents** | [Microsoft Perception](/en-us/security/agentic-security/agentic-security-overview); [Microsoft Security Copilot](/en-us/copilot/security/); [Microsoft Defender](/en-us/defender/); [Microsoft Sentinel and integrated security operations](/en-us/azure/sentinel/); [agent playbooks](/en-us/security/agentic-security/agentic-security-overview), attack disruption, investigation, and governed response. | Increase defensive speed and reach while keeping people in control of consequential decisions. |
| **Secure your agentic insider** | [Microsoft Agent 365](/en-us/microsoft-agent-365/overview); [Microsoft Entra Agent ID and governance](/en-us/entra/); [Conditional Access](/en-us/entra/); [Microsoft Purview](/en-us/purview/); Microsoft Intune and execution controls; [Microsoft Defender runtime protection](/en-us/defender/); [Global Secure Access](/en-us/entra/). | Discover, govern, constrain, monitor, and respond to agents throughout their lifecycle. |

The [Microsoft Zero Trust Workshop](/en-us/security/zero-trust/) can help you assess your current state, align stakeholders, and build a prioritized implementation roadmap. The [Zero Trust Assessment](/en-us/security/zero-trust/) can help you evaluate supported Microsoft 365 and Azure configurations, identify gaps, and provide evidence for planning improvements.

## Recommended next steps

Choose the action that best matches your current needs:

- **Plan your security transformation.** Use the [Microsoft Security Adoption Framework](/en-us/security/saf/) to connect business priorities and risk to strategy, governance, operating models, security disciplines, technologies, and implementation.
- **Establish a baseline and roadmap.** Use the [Microsoft Zero Trust Workshop and Zero Trust Assessment](/en-us/security/zero-trust/) to identify gaps, align stakeholders, and prioritize improvements.
- **Choose and implement capabilities.** Explore Microsoft Security product documentation and use the linked product guidance in the preceding sections to plan, configure, deploy, and operate the capabilities that support your priorities.