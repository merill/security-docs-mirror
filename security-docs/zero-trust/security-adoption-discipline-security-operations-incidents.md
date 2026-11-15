---
layout: Conceptual
title: Plan and run SecOps incident operations | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-discipline-security-operations-incidents
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Plan and run incident operations across preparation, investigation, containment, recovery, and continuous improvement.
ms.date: 2026-11-09T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 094ad6c7-1b88-16ce-f649-d078829a634b
document_version_independent_id: 094ad6c7-1b88-16ce-f649-d078829a634b
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-adoption-discipline-security-operations-incidents.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-adoption-discipline-security-operations-incidents
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-adoption-discipline-security-operations-incidents.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/43093068-2dda-408b-b3fe-dfd705c84f78
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/e453d60d-ba7e-43bc-8028-ec38e6b62512
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: 0d16d6c4-c582-2d53-f341-cec8e44cbaf5
---

# Plan and run SecOps incident operations | Microsoft Learn

This article helps security and technology teams plan and run incident operations that investigate, contain, and support recovery from active cyberattacks while limiting business, operational, legal, and reputational impact.

This guidance is part of the [Security Operations (SecOps) discipline](security-adoption-discipline-security-operations) in the **Microsoft Security Adoption Framework (SAF)**.

Use this article for durable incident operating principles. Use [Prepare for incident response](security-operations-incident-response-readiness) for readiness activities, [Incident response playbooks](security-operations-incident-response-playbooks) for scenario-specific execution guidance, and [technology guidance for SecOps](security-operations-technology) for control-specific and product-level implementation.

## Establish incident governance

Define how the organization makes and executes decisions before an incident occurs.

An **incident response plan** defines accountability, decision paths, escalation, communications, and coordination across the organization. **Playbooks** define repeatable technical and operational actions for specific attack scenarios. Playbooks operationalize the plan but don't replace recovery procedures or business, legal, regulatory, and executive decision processes.

Establish:

- **Accountability** for incident outcomes and the effectiveness of the response process.
- **Responsibility** for investigation, coordination, containment, recovery, communications, and documentation.
- **Decision authority** for actions that affect business operations, customers, legal or regulatory obligations, public communications, and recovery sequencing.
- **Risk-acceptance authority** for residual risk and exceptions, assigned only to people with delegated authority.
- **Escalation paths** for decisions that exceed a responder's authority or require specialized expertise.

Humans, service providers, AI agents, tools, and automation can execute incident tasks. Preserve human accountability, decision authority, and oversight, especially for disruptive or irreversible actions.

## Use the incident lifecycle

Organize incident operations around a consistent lifecycle:

**Plan → detect and investigate → coordinate and contain → recover → learn and improve**

The phases can overlap during active incidents. Keep authority, decisions, evidence, and actions clear as the situation changes.

### Plan

Prepare the organization to make high-quality decisions under pressure:

- Define incident severity, escalation triggers, authority, and cross-functional coordination.
- Develop and validate playbooks for priority attack scenarios.
- Establish secure collaboration, evidence-handling, communications, and documentation processes.
- Identify internal and external expertise for critical platforms, applications, infrastructure, forensics, legal, privacy, communications, and recovery.
- Exercise plans and playbooks to find gaps in people, process, technology, and authority.
- Define metrics that measure detection, investigation, containment, recovery, and learning outcomes.

### Detect and investigate

Determine whether malicious activity is occurring and understand its scope, impact, objectives, and persistence:

- Prioritize business-critical services, privileged access, and high-impact attack paths.
- Validate signals using available telemetry, threat intelligence, analytics, and system expertise.
- Preserve evidence and maintain chain-of-custody practices when legal, regulatory, or investigative requirements apply.
- Focus investigation on decisions and actions that materially affect containment and recovery.
- Document findings, assumptions, decisions, and incident-driven changes.
- Engage specialists when the attack or affected technology exceeds available expertise.

Balance urgency with precision. Act quickly enough to limit attacker impact while avoiding unnecessary disruption, evidence loss, incomplete remediation, or actions that prevent learning.

### Coordinate and contain

Disrupt attacker activity and limit business impact through coordinated technical and operational action:

- Assign incident coordination responsibility and confirm current decision authority.
- Define containment objectives, sequencing, dependencies, and expected business impact.
- Coordinate SecOps with engineering and operations, system and product teams, business leadership, and organizational crisis functions.
- Use tested automation and orchestration for repeatable actions; require human oversight for actions with material business or safety impact.
- Establish information flows for responders, leadership, affected business teams, and approved external parties.
- Follow organizational legal, privacy, regulatory, and communications processes for sensitive information and external communications.
- Preserve routine detection, triage, and monitoring so the organization can identify concurrent or expanding attacks.

Containment decisions often involve tradeoffs between attacker disruption, evidence preservation, operational continuity, and business risk. Escalate decisions that exceed delegated authority.

### Recover

Restore security assurances and business operations through a coordinated recovery plan:

- Confirm recovery scope, priorities, dependencies, leadership, and decision authority.
- Sequence identity, endpoint, infrastructure, application, data, network, and business recovery actions.
- Address known persistence and validate that recovery actions achieve the intended security outcome.
- Coordinate technical restoration with system owners, business teams, and continuity or disaster-recovery processes.
- Monitor for recurrence, attacker adaptation, and unintended impact.
- Document residual risk and obtain acceptance only from people with delegated authority.

Treat recovery as coordinated change across connected systems and business processes, not as isolated technical fixes.

### Learn and improve

Complete the incident lifecycle by converting evidence and experience into durable improvements:

- Update detections, hunting hypotheses, playbooks, automation, telemetry, and evidence-retention practices.
- Improve Security Posture Management priorities, baselines, and preventive controls.
- Feed findings into security and enterprise architecture, including trust boundaries, resilience, and observability requirements.
- Assign engineering and operations improvements to the teams that build and run affected systems.
- Update SecOps strategy, investments, metrics, training, and exercises based on demonstrated risk.
- Track improvement actions to completion and verify that they reduce recurrence or impact.

Post-incident learning is complete only when findings change SecOps, posture, architecture, engineering and operations, or strategy—not when the review meeting ends.

## Principles for effective incident operations

Apply these principles throughout the lifecycle:

- **Focus on business impact**: Prioritize actions that protect critical services, people, data, and obligations.
- **Preserve evidence and reversibility**: Avoid unnecessary changes, document incident-driven actions, and preserve rollback options when practical.
- **Integrate deep expertise**: Include the people who design, build, and operate affected systems, not only security generalists.
- **Separate execution from authority**: Enable fast execution while keeping accountability and decision rights explicit.
- **Communicate deliberately**: Share accurate information through defined channels and organizational legal, privacy, regulatory, and communications processes.
- **Sustain operations**: Maintain essential SecOps monitoring and response for threats outside the primary incident.
- **Improve the system**: Use every incident and exercise to strengthen detection, prevention, resilience, and decision quality.