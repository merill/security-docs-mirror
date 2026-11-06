---
layout: Conceptual
title: Adopt and secure AI and data | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-scenario-secure-ai
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Use the Microsoft security adoption model to rapidly adopt and secure AI based on Zero Trust principles.
ms.date: 2026-11-06T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 2ffc74ed-6d1b-c4c7-d21a-b0d2fd8475b8
document_version_independent_id: 2ffc74ed-6d1b-c4c7-d21a-b0d2fd8475b8
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-adoption-scenario-secure-ai.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-adoption-scenario-secure-ai
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-adoption-scenario-secure-ai.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: 546a3eb6-3478-a336-f62f-fb01ee73b9e1
---

# Adopt and secure AI and data | Microsoft Learn

This article explains how to rapidly and securely adopt AI using Zero Trust principles, as part of the Microsoft [security adoption model](security-adoption-model).

This business scenario helps you achieve the following outcome:

**Rapidly and securely adopt AI technology**

As a business leader, you're under pressure to adopt AI quickly for competitive advantage, while protecting your organization from new and evolving risks.

This business scenario is part of our [structured adoption model](security-adoption-model) that helps you to achieve business goals using a modern security approach grounded in Zero Trust principles.

This guidance helps organizations adopt AI quickly and confidently while maintaining strong security, protecting sensitive data, and preserving business resilience.

## How this guidance works

This article is part of a [structured adoption model](security-adoption-model) that connects security strategy to implementation:

- Start with a [business scenarios](security-adoption-business-scenarios-overview) like this one to define the outcome you want to achieve.
- Identity the [security disciplines](security-adoption-discipline-overview) that apply to this scenario.

    Use those disciplines to define the required strategy, architecture, processes, and controls for the scenario. Work through each discipline to understand what needs to be planned, designed, and implemented across the organization.
- Use [technical solutions](implement-overview) to implement those requirements using Microsoft technologies, applying controls across [technology pillars](deploy/overview) such as identity and data.

This approach ensures that AI adoption is secured as part of your overall Zero Trust architecture, rather than as a separate effort.

## Why AI adoption requires a new approach

Generative AI technologies and AI agents are powerful business enablers, but they also introduce new classes of risk. These include (but aren't limited to):

- Acceleration and amplification of existing cybersecurity risk using AI.
- Unintended data exposure causing loss of intellectual property (IP) and competitive advantage.
- Alteration of data, records, or processes through attacks such as data poisoning.

## Secure AI adoption

To enable AI safely while managing these risks, organizations must do two things in parallel:

- **Secure AI technology** - Adopt new security controls and practices designed for AI, while reprioritizing existing security investments. For example:

    - Classify and protect sensitive data to prevent unauthorized disclosure through AI models, applications, or users.
    - Apply Zero Trust principles to AI identities, access, and data flows.
    - Extend security monitoring and controls to AI-enabled workloads and agents.
- **Use AI to improve security** — Use AI to increase the speed, scale, and effectiveness of security operations, including:

    - Security posture management.
    - Vulnerability discovery and mitigation.
    - Incident detection, investigation, and response.
    - Skills enablement for security and IT teams.

Both are required. Securing AI reduces risk, while using AI for security helps teams keep pace with the increased attack volume and sophistication driven by AI

## Business value

The value of rapidly and securely adopting AI differs by role, but benefits the entire organization.

| **Roles** | **Value** |
| --- | --- |
| **Business leadership** | Capture new opportunities and efficiencies while limiting AI-related risks such as IP loss, reputational damage, and operational disruption. |
| **Technology roles** | Reduce incident frequency, impact, and recovery effort while lowering friction for security and compliance requirements. |
| **Security roles** | Improve the effectiveness and efficiency of security operations by using AI to detect threats faster, prioritize risks more accurately, and automate time‑consuming tasks. |

## Align security disciplines

Security disciplines represent the structured areas of accountability required to deliver this business scenario.

- Planning and oversight disciplines define the strategy, governance, and cross‑organization coordination required.
- Technical strategy disciplines define the architectural, operational, and control capabilities required.
- Operational disciplines ensure that security controls remain effective over time through monitoring, response, and continuous improvement. They detect misuse, respond to threats, and drive ongoing security posture improvements.

### Planning and oversight disciplines

| **Discipline** | **Action** |
| --- | --- |
| **[Strategy, integration, and governance](security-adoption-discipline-strategy)** | Establish or update cross-team processes to ensure a coordinated approach across security, technology, and business teams, including:Define a clear strategy for securing AI and using AI for security.Update governance, policies, and processes to address AI‑specific risks.Continuously learn and adapt as AI capabilities and threats evolve. |
| **[End-to-end security architecture](security-adoption-discipline-architecture)** | Ensure that security architecture and technical controls and capabilities include controls for AI technologies and AI usage. Drive an integrated approach that allows lessons learned in one area to be rapidly applied across the organization, keeping pace with the speed of AI-driven change. |

### Technical strategy disciplines

| **Discipline** | **Action** |
| --- | --- |
| **[Access and identities](security-adoption-discipline-identity-access)** | Ensure AI agents and applications use managed, secure identities.Apply least‑privilege access, informed by business priorities and threat intelligence. Enable comprehensive logging and anomaly detection to support rapid response and recovery. |
| [**Infrastructure security**](security-adoption-discipline-infrastructure) | Use threat modeling to evaluate and mitigate risks introduced by AI infrastructure and AI‑enabled applications. Apply AI to enhance vulnerability discovery, prioritization, and remediation. Ensure robust logging and detection capabilities. |
| [**Development security**](security-adoption-discipline-development) | Evaluate application risks introduced by AI components, including both traditional software vulnerabilities and social engineering or prompt‑based manipulation. Use AI to accelerate vulnerability discovery and remediation, guided by business risk and threat intelligence.Support the logging of activity and detection of anomalous activity (potential attacks) to enable effective response and recovery. |
| [**Data security**](security-adoption-discipline-data) | Classify and label sensitive data to prevent AI models from ingesting or exposing it inappropriately. Extend data security controls—such as data loss prevention (DLP) to cover AI applications and agents. Ensure visibility and monitoring for data‑related threats. Support the logging of activity and detection of anomalous activity (potential attacks) to enable effective response and recovery. |
| [**OT and IoT security**](security-adoption-discipline-iot) | Apply threat modeling to AI interactions with OT/IoT systems, especially where AI affects physical processes.  Prioritize protections and monitoring based on business impact and threat intelligence. Support the logging of activity and detection of anomalous activity (potential attacks) to enable effective response and recovery. |

### Operational disciplines

| **Discipline** | **Action** |
| --- | --- |
| [**SecOps**](security-adoption-discipline-security-operations) | Prepare for higher quality and higher volume of established attack techniques. Integrate AI analysis to amplify and augment human activities and skills for investigating, hunting for, and simulating threats.Use AI to increase skills readiness of junior analysts. Prioritize security activities using business priorities and threat intelligence insights. |
| [**Security posture management**](security-adoption-discipline-posture) | Focus on rapidly building and maturing this discipline to address increasing quality and volume of attacks accelerated by AI. Integrate use of AI to more quickly analyze data, identify mitigations, and increase skills readiness of posture management professionals. |

## Required technical pillars

Technology pillars represent the core Microsoft security capabilities that support this business scenario.

| **Pillar** | **Purview** | **Github Advanced Security** |
| --- | --- | --- |
| **AI** | Microsoft Purview provides AI security and governance capabilities including AI Hub for visibility into AI usage, sensitivity labels for AI-generated content, and compliance controls for Copilot and other AI services. | GitHub Advanced Security applies AI-powered code analysis through Copilot Autofix to automatically suggest security fixes for identified vulnerabilities, accelerating remediation. |