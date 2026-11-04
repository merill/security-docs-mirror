---
layout: Conceptual
title: Minimize business damage from security incidents | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-scenario-minimize-impact
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Use the Microsoft security adoption model to minimize impact from security threats based on Zero Trust principles and security best practices.
ms.date: 2026-05-24T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 5f596ad2-9431-2d8d-2e90-a16dab3bf795
document_version_independent_id: 5f596ad2-9431-2d8d-2e90-a16dab3bf795
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-adoption-scenario-minimize-impact.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-adoption-scenario-minimize-impact
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-adoption-scenario-minimize-impact.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/43093068-2dda-408b-b3fe-dfd705c84f78
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/e453d60d-ba7e-43bc-8028-ec38e6b62512
platformId: bb4011cf-fc9b-1a4e-29fc-ffe86c5d0ee9
---

# Minimize business damage from security incidents | Microsoft Learn

This article explains how to manage security incidents and minimize their impact by using Zero Trust principles, as part of the Microsoft [security adoption model](security-adoption-model).

This business scenario helps you achieve the following outcome:

**Minimize business damage from security incidents**

As a business leader, you know that cyberattacks are inevitable. What matters is how quickly you can detect, contain, and recover from security incidents to reduce operational disruption, financial loss, and reputational impact.

This guidance helps your organization reduce the business impact of security incidents by strengthening resilience, improving response effectiveness, and accelerating recovery across the enterprise.

## How this guidance works

This article is part of a [structured adoption model](security-adoption-model) that connects security strategy to implementation:

- Start with a [business scenario](security-adoption-business-scenarios-overview) like this one to define the outcome you want to achieve.
- Identify the [security disciplines](security-adoption-discipline-overview) that apply to this scenario.

    Use those disciplines to define the required strategy, architecture, processes, and controls for the scenario. Work through each discipline to understand what needs to be planned, designed, and implemented across the organization.
- Use [technical solutions](implement-overview) to implement those requirements by using Microsoft technologies, applying controls across [technology pillars](deploy/overview) such as identity and data.

This approach ensures that security incident response and recovery are integrated into your overall Zero Trust architecture, enabling faster detection, containment, and recovery.

## Why minimizing attack damage requires a new approach

Security success is attacker failure, but you can't guarantee that you stop every attack. Because damage from successful cybersecurity attacks is inevitable, focus on building resilience by ensuring that you can:

- **Prevent** as many attacks as possible.
- **Respond** effectively when attacks happen to limit damage, and rapidly recover business assets and services.
- **Learn** to apply lessons learned and continuously increase resilience.

[![Diagram showing security success equals attacker failure through a continuous cycle of prevent attacks, respond and recover when attacks succeed, and learn to improve resilience](media/security-adoption-minimize-damage-success.png)](media/security-adoption-minimize-damage-success.png#lightbox)

## Business value

The value of investing in minimizing business damage benefits the entire organization, but differs by role.

| **Roles** | **Value** |
| --- | --- |
| **Business leadership** | Reduces business disruption, downtime, and risk from security incidents by limiting the frequency and severity of breaches and improving recovery speed. Faster restoration of operations and data integrity minimizes regulatory and reputational impact while reducing the number of incidents that require public disclosure. Security becomes an enabler of business agility, ensuring execution and investment decisions are informed by risk context rather than constrained by incidents. |
| **Technology roles** | Reduces operational friction while meeting security and technology requirements by automating controls and standardizing access and recovery processes. Lower incident frequency and impact decrease the effort required for remediation and rebuild activities, enabling teams to focus on delivering reliable, scalable services that support remote and hybrid work. |
| **Security roles** | Increases attacker friction and reduces attacker return on investment by enforcing consistent, identity‑centric controls across users, devices, and applications. Improved visibility and automation reduce repetitive “groundhog day” incidents, allowing security teams to spend less time on recurring containment tasks and more time on proactive risk reduction and resilience. |

## Align security disciplines

Security disciplines represent the structured areas of accountability required to deliver this business scenario.

- Planning and oversight disciplines define the strategy, governance, and cross‑organization coordination required.
- Technical strategy disciplines define the architectural, operational, and control capabilities required.
- Operational disciplines ensure that security controls remain effective over time through monitoring, response, and continuous improvement. They detect misuse, respond to threats, and drive ongoing security posture improvements.

### Planning and oversight disciplines

| **Discipline** | **Action** |
| --- | --- |
| **[Strategy, integration, and governance](security-adoption-discipline-strategy)** | Set up cross-team processes and governance to guide the prevention, response, and learning across the security, technology, and business teams. |
| **[End-to-end security architecture](security-adoption-discipline-architecture)** | Ensure that technical controls and capabilities are integrated to rapidly apply lessons learned across the organization. This integration includes establishing effective security controls across all processes, people, and technology - both existing technology and new technology like Artificial Intelligence.Require the logging of activity and detection of anomalous activity (potential attacks) to enable effective response and recovery. Prioritize security activities using threat intelligence insights from SecOps. |

### Technical strategy disciplines

| **Discipline** | **Action** |
| --- | --- |
| **[Access and identities](security-adoption-discipline-identity-access)** | Establish strong controls, such as multifactor authentication and phishing-resistant credentials, to prevent well-known attack techniques.Support the logging of activity and detection of anomalous activity (potential attacks) to enable effective response and recovery. Prioritize security activities using threat intelligence insights from SecOps. |
| [**Infrastructure security**](security-adoption-discipline-infrastructure) | Establish strong controls to prevent well-known attack techniques across all infrastructure assets in the technical estate, including multicloud and on-premises datacenters.Support the logging of activity and detection of anomalous activity (potential attacks) to enable effective response and recovery.Prioritize security activities using threat intelligence insights from SecOps. |
| [**Development security**](security-adoption-discipline-development) | Establish strong controls to prevent well-known attack techniques across all new development and existing applications.Support the logging of activity and detection of anomalous activity (potential attacks) to enable effective response and recovery.  Establish processes to rapidly support attack investigations, recovery, and integration of fixes for security flaws. Prioritize security activities using threat intelligence insights from SecOps. |
| [**Data security**](security-adoption-discipline-data) | Establish strong controls to prevent the loss, encryption, alteration, or other security or privacy impact to data assets that store intellectual property, trade secrets, regulated data, and other sensitive information. Support the logging of activity and detection of anomalous activity (potential attacks) to enable effective response and recover Prioritize security activities using threat intelligence insights from SecOps. |
| [**OT and IoT security**](security-adoption-discipline-iot) | Establish strong controls to prevent successful attacks on these assets, which directly interact with physical processes and the physical world and can cause life, safety, financial, and other negative impacts. Support the logging of activity and detection of anomalous activity (potential attacks) to enable effective response and recovery. Prioritize security activities using threat intelligence insights from SecOps. |

### Operational disciplines

| **Discipline** | **Action** |
| --- | --- |
| [**SecOps**](security-adoption-discipline-security-operations) | Establish a continuous learning approach to improve SecOps response and share threat intelligence insights on top attack techniques and threat actors. This approach enables improvements to focus on the highest business impact attacks, the most frequently seen attacks, and others that disproportionately affect SecOps, security, and technology staff. |
| [**Security posture management**](security-adoption-discipline-posture) | Establish a continuous learning approach to integrate threat intelligence insights from SecOps and business context to monitor and help technology teams mitigate high vulnerabilities with high business impact that disproportionately impact business risk. |

## Required technology pillars

Technology pillars represent the core Microsoft security capabilities that support this business scenario.

| **Technology pillar** | **Defender XDR** | **Microsoft Sentinel** |
| --- | --- | --- |
| **Cross-pillar** | Correlates signals for Defender for Endpoint, Defender for Identity, Defender for Office 365, and Defender for Cloud Apps to detect, investigate, and respond to threats as coordinated incidents. | Ingests and analyzes data across technology pillars from Microsoft and third-party sources to enable centralized detection, investigation, and automated response. |
| **Identity** | Defender for Identity detects hybrid identity issues such as credential misuse, lateral movement, and privilege abuse. These identity signals are correlated within Defender XDR to detect and respond to attacks. | Ingests identity logs from Microsoft Entra and external providers to identify suspicious authentication and account behavior. |
| **Endpoints** | Microsoft Defender for Endpoint detects, investigates, and responds to threats on devices. These endpoint signals are correlated within Defender XDR to detect and respond to attacks. | Correlates endpoint telemetry from Microsoft and third-party sources to detect attacks and track activity across devices. |
| **Networks** | Correlates network-related signals across endpoints, identities, applications, and infrastructure to detect network-based threats. | Analyzes network logs and flow data from multiple sources to detect command-and-control activity and network attacks. |
| **Apps** | Microsoft Defender for Office 365 protects email and collaboration tools from phishing, malware, and business email compromise attacks. Microsoft Defender for Cloud Apps provides visibility and control over SaaS/cloud apps. | Monitors activity across Microsoft and third-party SaaS applications to detect anomalous behavior and threats. |
| **Data** | Microsoft Defender XDR correlates signals with Microsoft Purview to detect sensitive data exposure and potential data exfiltration across workloads. | Analyzes data access and movement patterns across sources to detect exfiltration and insider risks. |
| **Infrastructure** | Microsoft Defender for Cloud detects threats and misconfigurations across cloud and hybrid workloads. These signals are correlated within Defender XDR to detect infrastructure-based attacks. | Ingests infrastructure telemetry across cloud and on-premises environments to detect compromised resources and attacks. |
| **AI** | Applies AI-driven investigation and automated attack disruption across correlated signals to accelerate detection and response. | Applies analytics and machine learning to prioritize threats and reduce noise across large-scale data sets. |