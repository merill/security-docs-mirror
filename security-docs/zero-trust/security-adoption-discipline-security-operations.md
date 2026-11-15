---
layout: Conceptual
title: Establish a Security Operations discipline | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-discipline-security-operations
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Establish a Security Operations discipline that limits the business impact of active threats and continuously improves security.
ms.date: 2026-11-09T00:00:00.0000000Z
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
- https://authoring-docs-microsoft.poolparty.biz/devrel/43093068-2dda-408b-b3fe-dfd705c84f78
- https://authoring-docs-microsoft.poolparty.biz/devrel/540ac133-a371-4dbb-8f94-28d6cc77a70b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/e453d60d-ba7e-43bc-8028-ec38e6b62512
- https://authoring-docs-microsoft.poolparty.biz/devrel/60bfc045-f127-4841-9d00-ea35495a5800
platformId: 28d05408-c12b-eedc-e4c6-c63f1a2f497b
---

# Establish a Security Operations discipline | Microsoft Learn

This article helps security and technology teams establish and modernize a Security Operations (SecOps) discipline that detects, investigates, contains, and supports recovery from active threats.

This guidance is part of the **Microsoft Security Adoption Framework (SAF)**. SAF connects business scenarios, security disciplines, and technical implementation so that strategy, architecture, engineering, operations, and controls work together.

Within SAF, **SecOps** is the discipline for managing active threats and compromise. A **security operations center (SOC)** is one organizational construct for executing SecOps functions. Organizations can use other structures while delivering the same SecOps outcomes.

Use [SecOps implementation patterns](/en-us/security/saf/disciplines/security-operations/implementation-patterns), [technology guidance for SecOps](security-operations-technology), and related implementation guidance for control-specific and product-level details. For high-impact compromise pathways, align SecOps with the [privileged access scenario](security-adoption-scenario-privileged-access) and [SecOps incident operations](security-adoption-discipline-security-operations-incidents).

## Mission and outcomes

The mission of SecOps is to limit the business impact of cyberattacks by rapidly detecting, investigating, containing, and learning from threats across the technology estate.

Active attackers adapt as defenders detect and disrupt them. Combine automation and machine-speed analysis with human expertise, judgment, accountability, and oversight to act quickly without losing decision quality.

SecOps complements Security Posture Management. Security Posture Management reduces exposure and prevents attacks; SecOps detects and manages active threats and compromise. Both continuously exchange insights to reduce organizational risk.

Regardless of team size or operating model, deliver these outcomes:

- **Rapid threat response**: Detect, investigate, and contain threats across identities, endpoints, infrastructure, applications, data, networks, operational technology (OT), and AI.
- **Coordinated recovery**: Restore the confidentiality, integrity, and availability of affected business services through coordinated technical and operational action.
- **Shared threat intelligence**: Convert signals, investigations, and external intelligence into actionable insights for analysts, automation, security controls, and partner teams.
- **Proactive threat discovery**: Use threat hunting and attack simulation to find attacker activity, test assumptions, and identify detection or control gaps.
- **Continuous improvement**: Feed incident and exercise learning into SecOps, Security Posture Management, architecture, engineering and operations, and security strategy.

## Apply Zero Trust to SecOps

Zero Trust assumes compromise and limits the effect of control failure. Apply that principle to SecOps:

- **Establish visibility**: Integrate relevant telemetry across the environment so SecOps can detect compromise, investigate attacker behavior, and understand business impact.
- **Verify through detection and investigation**: Use analytics, threat intelligence, hunting, and investigation to validate activity instead of trusting a single signal.
- **Contain rapidly and limit blast radius**: Use tested processes, automation, and orchestration to disrupt attacks while preserving evidence and avoiding unnecessary business impact.
- **Learn and improve**: Use incidents, exercises, threat intelligence, and operational metrics to improve detections, playbooks, preventive controls, architecture, and priorities.

## Apply the discipline

Use a continuous operating loop that aligns SecOps work to business risk:

1. **Align to business risk** Prioritize business services, attack paths, and threat scenarios by potential organizational impact.
2. **Establish visibility** Define telemetry, detection, investigation, and data-retention requirements across the technology estate.
3. **Detect and investigate** Identify suspicious activity, validate incidents, determine scope and impact, and preserve evidence.
4. **Contain and recover** Coordinate technical and business actions that disrupt attackers and restore security assurances.
5. **Learn and improve** Convert incident and exercise findings into improvements across detection, posture, architecture, engineering and operations, and strategy.

## Manage change

Modernize SecOps as a continuous improvement program, not a one-time tooling deployment. Prioritize:

- **Mission alignment**: Focus limited human and automated capacity on threats and assets with the greatest potential business impact.
- **Operational learning**: Adapt detections, skills, processes, and technology as attackers, platforms, and business priorities change.
- **Cross-functional collaboration**: Integrate SecOps with teams that design, build, operate, govern, and rely on the environment.
- **Sustainable execution**: Measure operational effectiveness, reduce unnecessary analyst workload, and preserve critical monitoring and response during major incidents.

[![Diagram showing the SecOps mission, operating loop, and Zero Trust alignment.](media/security-adoption-discipline-operations-mission.png)](media/security-adoption-discipline-operations-mission.png#lightbox)

## Discipline roles and collaborators

SecOps job functions describe the work and outcomes required. Organizations can assign these functions across people, teams, service providers, AI agents, tools, and automation while preserving human accountability, decision authority, and oversight.

Define accountability for SecOps outcomes, responsibility for execution, decision authority for incident and business-impact decisions, and escalation paths for risk acceptance. Assign risk-acceptance decisions only to people with delegated authority.

See [SecOps roles](security-adoption-discipline-security-operations-roles) for the durable job functions and partner relationships used to execute this discipline.

## Alignment with other disciplines

Integrate SecOps with the broader security operating model:

- **Security Posture Management**: Use incident and threat insights to prioritize exposure reduction, preventive controls, and remediation.
- **Access and Identities**: Use identity telemetry to detect and investigate attacks; improve identity controls based on incident learning.
- **Data Security**: Coordinate investigations of data theft, extortion, insider risk, and privacy-related events.
- **Security Architecture**: Use attack and incident findings to improve system design, trust boundaries, resilience, and detection requirements.
- **Development Security and technical engineering and operations**: Add telemetry, correct weaknesses, improve recovery, and sustain controls in the systems these teams build and operate.
- **Strategy, Integration, and Governance**: Set priorities, success measures, accountability, decision authority, and investment direction based on business risk and operational evidence.

Effective SecOps creates a feedback loop from active threats to prevention and long-term modernization:

**Detect and investigate → contain and recover → learn → improve posture, architecture, engineering and operations, and strategy**

## Alignment with technology pillars

Apply SecOps across the technology estate:

- **Identities**: Detect account compromise, privilege abuse, token theft, and lateral movement.
- **Endpoints**: Find and contain compromised devices and collect evidence about attacker activity.
- **Infrastructure**: Detect and respond to threats in cloud, on-premises, edge, and operational environments.
- **Applications**: Monitor email, collaboration, business, custom, and software-as-a-service applications for attack activity.
- **Data**: Investigate theft, manipulation, destruction, encryption, and misuse of sensitive data.
- **Networks**: Use network telemetry and controls for investigation context and containment, including when encryption limits content visibility.
- **AI**: Detect attacks on AI systems and use governed AI capabilities to accelerate analysis and execution under human oversight.

## Related SAF guidance

- [Establish a Security Posture discipline](security-adoption-discipline-posture)
- [Secure and govern privileged access](security-adoption-scenario-privileged-access)
- [Plan and run SecOps incident operations](security-adoption-discipline-security-operations-incidents)
- [Prepare for incident response](security-operations-incident-response-readiness)
- [Incident response playbooks](security-operations-incident-response-playbooks)
- [Security roles and responsibilities in SAF](security-adoption-roles)