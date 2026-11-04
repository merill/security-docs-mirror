---
layout: Conceptual
title: Use the Microsoft security adoption model to modernize SecOps | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-discipline-security-operations
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Use the Microsoft security adoption model to modernize security operations, based on Zero Trust principles.
ms.date: 2026-05-24T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: f1079e61-4a86-22d7-7c7d-b0e87b9b898c
document_version_independent_id: f1079e61-4a86-22d7-7c7d-b0e87b9b898c
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-adoption-discipline-security-operations.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-adoption-discipline-security-operations
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-adoption-discipline-security-operations.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/43093068-2dda-408b-b3fe-dfd705c84f78
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/e453d60d-ba7e-43bc-8028-ec38e6b62512
platformId: 28d05408-c12b-eedc-e4c6-c63f1a2f497b
---

# Use the Microsoft security adoption model to modernize SecOps | Microsoft Learn

This article helps security and technology teams establish and modernize a Security Operations (SecOps) discipline that detects, investigates, and responds to active threats that bypass preventive controls.

This guidance is part of the **Microsoft Security Adoption Framework (SAF)**, a broader body of guidance for planning, prioritizing, and implementing end-to-end security modernization. SAF connects business scenarios, security disciplines, and technical implementation so that strategy, architecture, operations, and controls work together rather than as isolated recommendations.

Within SAF, SecOps is an operational security discipline. It defines the mission, outcomes, roles, processes, and operating model needed to manage active attacks across the technology estate. Use [SecOps technology](security-operations-technology) and related implementation guidance when you need control-specific and product-level implementation details.

## What's SecOps?

SecOps maintain and restore the security assurances of the system as live adversaries attack it. The NIST Cybersecurity Framework describes the SecOps functions of Detect, Respond, and Recover well.

- **Detect** - SecOps must detect the presence of adversaries in the system, who are incentivized to stay hidden in most cases, allowing them to achieve their objectives unimpeded. This can take the form of reacting to an alert of suspicious activity or proactively hunting for anomalous events in the enterprise activity logs.
- **Respond** - Upon detection of potential adversary action or campaign, SecOps must rapidly investigate to identify whether it's an actual attack (true positive) or a false alarm (false positive) and then enumerate the scope and goal of the adversary operation.
- **Recover** - The ultimate goal of SecOps is to preserve or restore the security assurances (confidentiality, integrity, availability) of business services during and after an attack.

### Risk mitigation

The most significant security risk most organizations face is from human attack operators.

With notable exceptions, risk from automated/repeated attacks have been mitigated significantly for most organizations by signature and machine learning based approaches built into anti-malware.

While human attack operators are challenging to face because of their adaptability, they're operating at the same "human speed" as defenders, which help level the playing field.

SecOps has a critical role to play in limiting the time and access an attacker can get to valuable systems and data. Each minute that an attacker has in the environment allows them to continue to conduct attack operations and access sensitive or valuable systems.

## Why this discipline?

Not all attacks can be prevented. Even with strong security architecture and posture management that blocks most attacks, threat actors sometimes gain initial access to environments.

SecOps focuses on managing those active attacks and security incidents, limiting the damage attackers can cause after compromise. Effective SecOps reduces risk by:

- Detecting malicious activity quickly.
- Shortening attacker dwell time.
- Containing lateral movement and impact.
- Supporting recovery and organizational resilience.

Within the security adoption model, SecOps represents the post‑compromise, reactive side of security, complementing security posture management, which focuses on proactive risk reduction and attack prevention.

[![Diagram of Security Operations and Security Posture Management showing their complementary roles in risk reduction.](media/security-adoption-discipline-operations.png)](media/security-adoption-discipline-operations.png#lightbox)

Without an effective SecOps discipline, attackers who gain access can operate undetected, escalate privileges, move laterally, and inflict maximum business damage.

## Mission and outcomes

The mission of the SecOps discipline is to limit the business impact of cyberattacks by rapidly detecting, investigating, and responding to threats across the modern technology estate.

Regardless of team size or operating model, mature SecOps delivers these outcomes:

- **Rapid threat response** – Timely detection and containment of threats across identities, endpoints, infrastructure, applications, and data
- **Shared threat intelligence** – Centralized signals and insights that inform analysts, automation, and downstream security controls
- **Proactive threat discovery** – Threat hunting and attack simulation to uncover emerging techniques and attacker behavior

SecOps teams may range from a single individual to large globally distributed 24/7 operations, and functions may be partially or fully outsourced. Regardless of structure and size, the outcomes remain the same.

### Adopt Zero Trust in SecOps

Security Operation (SecOps) is foundational to a Zero Trust strategy. Zero Trust assumes compromise and focuses on minimizing impact when controls fail. SecOps turns that assumption into action by continuously detecting, investigating, and responding to threats across the environment.

In a Zero Trust model, prevention alone is insufficient. Organizations must expect attackers to bypass controls and rely on SecOps to identify malicious activity early, contain attacks quickly, and generate insights that improve security posture over time.

Within our security adoption model, SecOps guidance focuses on the operational capabilities required to support Zero Trust across the organization, including monitoring, detection, investigation, response, automation, and continuous learning.

- **Centralize detection and visibility**: Integrate logs and telemetry from across the environment—including identities, endpoints, applications, and infrastructure—into a centralized detection and investigation capability. This ensures SecOps has consistent, cross‑domain visibility to detect compromise early and understand attacker behavior.
- **Automate response and containment**: Use orchestration and automation to execute repeatable response actions, such as isolating compromised devices or disabling risky accounts. Automation reduces response time, lowers analyst cognitive load, and ensures consistent execution under pressure.
- **Proactively hunt for threats**: Treat threat hunting as a core SecOps capability. Use hypothesis‑driven hunting and advanced analytics to find attacker activity that evades automated detections, reducing dwell time and uncovering gaps in controls.
- **Manage alerts and incidents effectively**: Tune detections to reduce noise and ensure analysts focus on meaningful alerts. Standardize investigation and response workflows using playbooks so incidents are handled consistently and efficiently.
- **Continuously reduce exposure based on risk**: Use attack‑path analysis and exposure insights to identify conditions that could enable compromise. Prioritize remediation based on business impact and likelihood, so effort is focused where it matters most.
- **Continuously evolve SecOps processes**: Regularly review detections, playbooks, and response outcomes based on real incidents and threat intelligence. Feed these learnings back into SecOps strategy to ensure capabilities adapt as attackers, technologies, and business priorities change.

By aligning SecOps to Zero Trust principles, organizations move from reactive incident handling to a resilient operating model where every incident strengthens detection, response, and prevention across the enterprise.

## How to apply this discipline

To apply the SecOps discipline effectively, focus on establishing a coordinated approach to detecting, responding to, and recovering from threats across the organization:

1. **Define a threat detection and response strategy aligned to business risk** Establish a clear approach for identifying, prioritizing, and responding to threats based on their potential business impact.
2. **Ensure consistent detection and response across the environment** Apply a unified approach to monitoring, investigation, and response across identities, devices, applications, and infrastructure.
3. **Standardize processes for detection, response, and recovery** Provide clear guidance to ensure incidents are handled consistently, reducing response time and limiting impact.
4. **Align SecOps with business priorities and critical scenarios** Prioritize detection and response efforts to focus on protecting critical assets and minimizing the impact of security incidents.
5. **Continuously improve through insights and feedback** Use learnings from incidents, threat intelligence, and operational metrics to strengthen detection capabilities and improve response over time.

## Manage change

SecOps modernization is a continuous improvement journey, not a one-time tooling deployment. The goal is to steadily improve the organization’s ability to reduce attacker impact when compromises occur.

[![Screenshot of security operations mission summary with key actions and Zero Trust alignment highlighted.](media/security-adoption-discipline-operations-mission.png)](media/security-adoption-discipline-operations-mission.png#lightbox)

A modern SecOps approach aligned with Zero Trust principles emphasizes:

- **Mission alignment** - Prioritizing what matters most to the business when alerts and threats exceed your capacity to respond with humans and automation, including AI.
- **Continuous learning** - Adapting detections, skills, and processes as threat actors, platforms, and business priorities change.
- **Collaboration and sharing** - Treating SecOps as a team effort across security, IT operations, engineering, legal, communications, and leadership.

Threat actors tend to reuse techniques that are cheap, effective, and reliable until they fail, so it's critical to capture and share threat intelligence as insights on past attacks. SecOps threat intelligence should directly inform security control design, prioritization, and posture improvement, alongside business and compliance requirements.

## Discipline roles and collaborators

The SecOps discipline is typically led by a dedicated SecOps team. In smaller organizations, SecOps responsibilities might be part-time or shared across roles but still require clear ownership.

Primary roles in this discipline typically include:

- SecOps / SOC manager
- Tier 1 triage analysts
- Tier 2 investigation analysts
- Threat hunters (Tier 3)
- Detection engineers
- SecOps platform and data engineers
- Digital forensics and incident response specialists
- Threat intelligence analysts
- Incident coordination and management roles
- Attack simulation specialists (red team, purple team, penetration testing)

Key collaborators include:

- **Technical engineering and operations teams** – Enable logging and support investigation, containment, and recovery of systems they design and run.
- **Architecture roles** – Continuously improve the design of systems and controls based on incident learnings from SecOps threat intelligence.
- **Application and product teams** – Update software and services in response to incident insights.
- **Security Strategy, Integration, and Governance discipline** – Set priorities, metrics, and accountability for SecOps investments. Provide support and coordination during major incidents.

Effective SecOps depends on tight feedback loops between incident response and system design.

## Alignment with other disciplines

SecOps operates as part of a broader security operating model and is tightly integrated with other disciplines:

- **Security Posture Management discipline**: Focuses on preventing incidents; SecOps manages the incidents that still occur.
- **Access and Identities discipline**: Identity telemetry is a primary detection and investigation signal.
- **Data Security discipline**: SecOps investigates data theft, extortion, insider risk, and privacy incidents.
- **Security Architecture discipline**: Ensures detection and response mechanisms align with intended system design.
- **Strategy, Integration, and Governance discipline**: Defines SecOps priorities, metrics, and success criteria.

## Alignment with technology pillars

The SecOps discipline operates across all technology pillars and must detect and contain attacks wherever they occur.

- **Identities**: This is a top priority for SecOps because identities are primary attack entry points. Almost all multi-stage attacks rely on identity attacks (pass-the-hash/ticket/etc.) to laterally traverse and gain access to more organizational assets, often using privileged accounts associated with IT administrators or administrative service accounts.
- **Endpoints**: Endpoints are common footholds, a base of operations, and local attack tool storage for attackers. It's critical to quickly locate compromised endpoints to contain damage and gain insights into attackers objectives and capabilities.
- **Infrastructure**: Effective detection and response are important because threat actors frequently target high-value cloud and on-premises infrastructure assets that enable broad compromise when breached.
- **Apps**: Rapidly detection and response to attacks on email, collaboration, line of business, and other apps is critical because attackers often use them to enter and laterally traverse an organization to access business assets.
- **Data**: Attackers often target data for intellectual property theft, encryption to gain leverage for extortion or ransomware, planning future attacks, and other purposes. Additionally, SecOps may be involved in or collaborate on data related investigations related to privacy, insider risk, and others.
- **Network**: Just like legitimate communications, threat actor communications and attack operations travel over network connections. SecOps focuses on network sensor and data is still valuable for context and containment, even as encryption reduces visibility.
- **AI**: As AI emerges as an attack surface, new tools and skills are needed for effective detection and investigation. AI attack volume is increasing as threat actors adopt AI technology. SecOps can also take advantage of AI to automate analysis and other processes.