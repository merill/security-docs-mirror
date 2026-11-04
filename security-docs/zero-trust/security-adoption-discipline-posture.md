---
layout: Conceptual
title: Establish a Security Posture discipline | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-discipline-posture
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Use the Microsoft security adoption model to optimize security posture across the business, based on Zero Trust principles.
ms.date: 2026-05-24T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 1771139f-1ba6-ac48-3a59-a472e82e2f0b
document_version_independent_id: 1771139f-1ba6-ac48-3a59-a472e82e2f0b
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-adoption-discipline-posture.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-adoption-discipline-posture
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-adoption-discipline-posture.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/64b65f6c-101f-411a-9b83-9f577fab52d0
- https://authoring-docs-microsoft.poolparty.biz/devrel/97159432-14a9-4307-a469-d2f2c75f0e33
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/1a667fd1-8145-4b11-af0f-9f5de205a6e5
- https://authoring-docs-microsoft.poolparty.biz/devrel/50565c62-5f6b-4687-be38-323113c72c2e
platformId: 1710b1c3-9ec3-bb92-d3d2-921ea27cea3a
---

# Establish a Security Posture discipline | Microsoft Learn

This article helps security and technology leaders establish or modernize a Security Posture Management discipline. This discipline focuses on continuously reducing the organizational exposure to attacks by identifying and eliminating the most likely attack paths to critical assets.

This guidance is part of the **Microsoft Security Adoption Framework (SAF)**, a broader body of guidance for planning, prioritizing, and implementing end-to-end security modernization. SAF connects business scenarios, security disciplines, and technical implementation so that strategy, architecture, operations, and controls work together rather than as isolated recommendations.

Within SAF, Security Posture Management is an operational discipline that complements [SecOps](security-adoption-discipline-security-operations) by reducing the likelihood of compromise before incident response is required.

## Why this discipline

Most successful cyberattacks don’t begin with advanced exploits. They start by abusing well-known, easily exploitable weaknesses—often in identity, endpoints, infrastructure, applications, or configuration hygiene.

The Security Posture discipline exists to prevent attacks before they occur, complementing the Security Operations (SecOps) discipline, which focuses on detection, investigation, and response after compromise.

- Security Posture reduces opportunity for attackers.
- Security Operations limits impact when prevention fails.

Together, they form a complete security operating model.

Without a dedicated Security Posture discipline, organizations often treat posture management as:

- A periodic vulnerability scan.
- A compliance checkbox.
- A collection of disconnected remediation projects.

This approach leaves systemic weaknesses in place until attackers exploit them.

This diagram illustrates the complementary nature of Security Posture Management and Security Operations:

[![Diagram showing Security Posture Management focuses on preventing attacks (left of bang) while Security Operations manages incidents that occur (right of bang).](media/security-adoption-discipline-posture.png)](media/security-adoption-discipline-posture.png#lightbox)

## Mission and outcomes

Reduce the likelihood and impact of cyberattacks by continuously identifying and eliminating the most exploitable risks across the organization’s technology estate.

Organizations that mature this discipline achieve:

- Continuous discovery of assets across the modern estate.
- Prioritized visibility into exploitable vulnerabilities and attack paths.
- Faster, more effective remediation by asset-owning teams.
- Reduce attack surface and blast radius.
- Improved resilience against business disruption.

Security posture acts as the operational extension of governance, translating enterprise risk priorities into day-to-day remediation work.

## How to apply this discipline

To apply the Security Posture Management discipline effectively, focus on establishing a continuous, risk-driven approach to understanding and improving your organization’s security posture:

1. **Define a posture management strategy aligned to business risk** Establish a clear approach for identifying, measuring, and prioritizing security risks based on their potential impact on the business.
2. **Ensure continuous visibility across the environment** Maintain an up-to-date understanding of assets, configurations, and exposures across identities, devices, applications, infrastructure, and data.
3. **Standardize how security risks are assessed and prioritized** Provide clear guidance to ensure that vulnerabilities, misconfigurations, and risks are evaluated consistently and addressed based on impact.
4. **Align posture management with business priorities and critical assets** Focus remediation efforts on the most important risks affecting high-value assets and key business scenarios.
5. **Continuously improve posture through measurement and remediation** Use insights from assessments, risk trends, and remediation efforts to reduce exposure and strengthen security over time.

## Manage change

Modern Security Posture management represents a shift from static vulnerability reporting to continuous risk reduction.

| **Traditional approach** | **Modern discipline** |
| --- | --- |
| Periodic vulnerability scans | Continuous asset and risk discovery. |
| Compliance-driven prioritization | Threat-informed prioritization. |
| Security-owned findings | Shared accountability with engineering teams and business owners of systems. |
| One-time remediation | Continuous remediation and improvement. |
| Patch by exception | Patch by default. |

The following diagram shows the key elements of the Security Posture discipline.

[![Diagram showing Security Posture Management mission with key elements: continuously discover assets, identify and prioritize vulnerabilities, and enable mitigation.](media/security-adoption-discipline-posture-mission.png)](media/security-adoption-discipline-posture-mission.png#lightbox)

### Key principles

Key modernization principles include:

- **Enablement**: Go beyond tools and reports. Equip engineering and operations teams with guidance, context, automation, and education to reduce risk as part of their normal work.
- **Scope**: Address weaknesses across multiple dimensions:
    - **Functional** - Address Design and implementation flaws.
    - **Configuration** -Address misconfiguration and configuration drift over time.
    - **Operational** - Address administrative and operational practices that enable abuse (for example, weak credential handling).
- **Operations**: Make posture improvement a continuous engineering activity—not a one-time cleanup. This requires sustained collaboration, cultural change, and incremental progress.

This discipline requires cultural change, sustained collaboration, and incremental improvement rather than one-time remediation projects.

## Security posture strategy

An effective security posture strategy focuses on three continuous activities:

1. **Discover assets**: Continuously identify assets across the entire modern estate, including:

    - Identity systems
    - Endpoints
    - SaaS applications
    - Cloud and on-premises infrastructure
    - OT, IoT, and emerging platforms

    This requires close collaboration with asset ownership, configuration, and platform teams.
2. **Identify and prioritize exploitable risk**: Focus on vulnerabilities and attack paths that are:

    - Cheap for attackers to exploit.
    - Reliable at scale.
    - Common entry points for multistage attacks.

    Threat intelligence and real-world attack patterns should inform prioritization—not severity scores alone.
3. **Enable mitigation**: work with asset-owning teams to:

    - Integrate remediation into existing workflows.
    - Reduce friction and repeat effort.
    - Track progress against risk reduction goals.

    Security Posture succeeds when remediation becomes faster and easier than ignoring risk.

## Discipline roles and collaborators

Security Posture is inherently cross-functional.

Primary roles include:

- **Engineering and Operations teams**: Technology and Security Managers, Security and Automation Engineers accountable for implementing mitigations and maintaining hygiene across:

    - Identity and access
    - Networking
    - Endpoints and user productivity
    - Infrastructure and platforms (cloud, on-premises, CI/CD)
    - Data
    - AI
    - OT environments
- **Architecture Roles**: Design the systems and controls the Security Posture discipline monitors and improves:

    - Enterprise Architect
    - Security Architect
    - Infrastructure, identity, application, data, and AI architects.
    - Data and Artificial Intelligence (AI) architects.
- **Security Strategy, Integration, & Governance (All Others)**: Provide direction and support through:

    - Risk prioritization and metrics
    - Compliance and policy alignment
    - Security education and engagement
- **Threat Intelligence and SecOps**: Inform prioritization based on attacker behavior, active campaigns, and emerging techniques.

## Alignment with other disciplines

Security Posture Management works closely with other disciplines:

- **SecOps**: Prevention complements detection and response.
- **Security Strategy, Integration, and Governance**: Risk prioritization and metrics.
- **Security Architecture**: Consistent control placement.
- **Access and Identities**: Reducing identity-based attack paths.
- **Infrastructure**, **Development**, and **Data Security**: Eliminating systemic weaknesses.

Together, these disciplines create a cohesive security operating model.

## Alignment with technology pillars

Security Posture spans all technology pillars:

- **Identities** – This pillar is a top-priority for security posture because identity is a High-risk entry point that's foundational to nearly all attacks. Almost all multistage attacks rely on identity attacks, such as pass-the-hash, ticket, and other methods, to laterally traverse and gain access to additional organizational assets. These attacks often use privileged accounts associated with IT administrators or administrative service accounts.
- **Endpoints**: Endpoints are a common attacker foothold and staging environment. It's critical to quickly find and fix endpoint vulnerabilities.
- **Infrastructure**: Rapidly finding and mitigating infrastructure vulnerabilities is important since infrastructure has broad impact due to shared dependencies for hosted workloads and data.
- **Apps**: Rapidly finding and mitigating these vulnerabilities is important because threat actors often target email, collaboration, line of business, and other apps to enter and laterally traverse across an organization to access business assets.
- **Data**: Data provides a high-value target for theft, extortion, and disruption. Attackers often target data for intellectual property theft, encryption to gain leverage for extortion or ransomware, planning future attacks, and other purposes.
- **Networks**: Threat actors attack operations that rely on network connectivity. Network security controls restrict communication paths, constrain attacker movement and detect abnormal flows.
- **AI**: Emerging AI attack surfaces require new discovery and protection capabilities.

The discipline builds consistent skills, tooling, and processes across all pillars.