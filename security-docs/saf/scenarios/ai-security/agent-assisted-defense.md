---
layout: Conceptual
title: Defend with agents using SAF | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/saf/scenarios/ai-security/agent-assisted-defense
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Translate the defend with agents theme into durable security operations outcomes and use SAF and Microsoft guidance to implement governed, AI-assisted defense.
ms.date: 2026-11-08T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 89c4f951-2f63-9e18-4e45-920bf39b8206
document_version_independent_id: 89c4f951-2f63-9e18-4e45-920bf39b8206
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/saf/scenarios/ai-security/agent-assisted-defense.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../../../zero-trust/toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: saf/scenarios/ai-security/agent-assisted-defense
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/saf/scenarios/ai-security/agent-assisted-defense.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/43093068-2dda-408b-b3fe-dfd705c84f78
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e453d60d-ba7e-43bc-8028-ec38e6b62512
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 0595d25a-ced8-cd10-1078-63e67a5a5f5f
---

# Defend with agents using SAF | Microsoft Learn

**Defend with agents** is a current AI security transformation theme. The name can evolve, but the underlying objective is durable: increase the speed, reach, consistency, and quality of security operations without surrendering accountability or high-impact decisions to ungoverned automation.

This page translates the theme into durable outcomes and execution paths. It does not create a separate operating model for AI-assisted security. Use the Microsoft Security Adoption Framework (SAF) to organize the work and canonical Microsoft guidance to implement it.

## What this theme means

Defend with agents means using AI-assisted and agentic capabilities to help security teams collect and correlate signals, detect suspicious behavior, prioritize risk, investigate incidents, recommend actions, and automate bounded response steps.

AI changes the speed and scale at which security operations can work. Agents and automation can perform repeatable analysis, investigation, and response at machine speed, while people provide judgment, expertise, oversight, and accountability where these are required.

Defending at machine scale is not simply adding AI to existing manual processes. Organizations should redesign suitable security workflows so that agents, automation, tools, and people each perform the work they are best suited to perform.

Prioritize redesigned workflows and automations that reduce meaningful risk. Start with well-understood, repeatable activities, establish evidence and approval boundaries, and expand autonomy only when quality, resilience, and control are demonstrated.

## Durable outcome

The durable outcome is a measurable, resilient security operations capability in which people and AI work together under clear governance.

Success looks like:

- Relevant signals from identity, endpoints, applications, data, infrastructure, network, and AI systems are available for detection and investigation.
- AI-assisted triage and investigation improve speed and consistency without obscuring evidence or decision rationale.
- Automated actions have defined scope, prerequisites, approval requirements, rollback paths, and accountable owners.
- High-impact containment and recovery decisions remain subject to appropriate human judgment and authorization.
- Security teams measure detection quality, investigation time, containment time, false positives, automation reliability, and business impact.
- Incident response includes AI systems and attacks that use AI, while continuing to address classic threats.
- Lessons from incidents improve posture, architecture, development, policy, and future detection logic.

## SAF work

### Business scenarios

Use these SAF business scenarios to define outcomes and priorities:

- [Minimize damage from security incidents](/en-us/security/zero-trust/security-adoption-scenario-minimize-impact) - Improve readiness, detection, containment, recovery, and learning.
- [Protect critical business assets](/en-us/security/zero-trust/security-adoption-scenario-secure-assets) - Prioritize monitoring and response around the assets that matter most to the business.
- [Adopt and secure AI](/en-us/security/zero-trust/security-adoption-scenario-secure-ai) - Include AI systems and agents in operational security and use AI safely as part of the defense.
- [Strengthen posture and compliance](/en-us/security/zero-trust/security-adoption-scenario-improve-posture) - Use operational evidence to reduce exposure before the next incident.

### Security disciplines

Coordinate the work across these SAF disciplines:

- [SecOps](/en-us/security/zero-trust/security-adoption-discipline-security-operations) owns the detection, investigation, response, recovery, and improvement mission.
- [SecOps implementation patterns](/en-us/security/saf/disciplines/security-operations/implementation-patterns) provide repeatable approaches for putting the operating model into practice.
- [Incident operations](/en-us/security/zero-trust/security-adoption-discipline-security-operations-incidents) establish preparation, authority, coordination, and response processes.
- [Security posture](/en-us/security/zero-trust/security-adoption-discipline-posture) turns exposure and incident findings into prioritized prevention work.
- [Security architecture](/en-us/security/zero-trust/security-adoption-discipline-architecture) designs telemetry, control points, isolation paths, and resilient response patterns.
- [Strategy, integration, and governance](/en-us/security/zero-trust/security-adoption-discipline-strategy) defines risk tolerance, automation policy, accountability, and measures.
- [Access and identities](/en-us/security/zero-trust/security-adoption-discipline-identity-access), [Data](/en-us/security/zero-trust/security-adoption-discipline-data), [Development](/en-us/security/zero-trust/security-adoption-discipline-development), and [Infrastructure](/en-us/security/zero-trust/security-adoption-discipline-infrastructure) provide the domain expertise needed for safe investigation and response.

### Roles and collaboration

Use [Security roles and responsibilities in SAF](/en-us/security/zero-trust/security-adoption-roles) and [SecOps roles](/en-us/security/zero-trust/security-adoption-discipline-security-operations-roles) to define accountability and escalation.

The operating model depends on collaboration among:

- Organizational leadership and incident leadership to set decision authority and business priorities.
- SecOps/SOC analysts, threat hunters, incident responders, and detection engineers to supervise and improve agent-assisted workflows.
- Security architecture and posture teams to convert operational learning into durable controls.
- Identity, data, application, infrastructure, endpoint, and network teams to validate impact and execute domain-specific actions.
- Application and product development teams to provide telemetry and safe response mechanisms for AI-enabled systems.
- Legal, privacy, compliance, communications, and business continuity teams when incidents cross business or regulatory boundaries.

### Technologies

Agent-assisted defense is cross-cutting. Apply it across:

- [AI](/en-us/security/saf/technologies/ai/overview)
- [Identity](/en-us/security/zero-trust/deploy/identity)
- [Endpoints](/en-us/security/zero-trust/deploy/endpoints)
- [Applications](/en-us/security/zero-trust/deploy/applications)
- [Data](/en-us/security/zero-trust/deploy/data)
- [Infrastructure](/en-us/security/zero-trust/deploy/infrastructure)
- [Network](/en-us/security/zero-trust/deploy/networks)

The quality of AI-assisted defense depends on the quality, coverage, and context of the signals from these technologies.

## Implementation and product guidance

Use [Microsoft secure Zero Trust implementation solutions](/en-us/security/zero-trust/implement-overview) to connect operational outcomes to technical implementation. Start with the following canonical guidance:

1. [Secure SecOps with Zero Trust](/en-us/security/zero-trust/deploy/visibility-automation-orchestration) to integrate visibility, analytics, automation, and orchestration.
2. [Plan SecOps incident operations](/en-us/security/zero-trust/security-adoption-discipline-security-operations-incidents) to establish authority, process, communications, and decision paths.
3. [Prepare for incident response](/en-us/security/zero-trust/security-operations-incident-response-readiness) before increasing automation.
4. [Use incident response playbooks](/en-us/security/zero-trust/security-operations-incident-response-playbooks) to standardize repeatable actions and escalation.
5. [AI security in the Microsoft Zero Trust Workshop](/en-us/security/zero-trust/workshop-zero-trust-ai-security) to include AI systems and agents in the response model.
6. [Take the SecOps workshop](/en-us/security/zero-trust/workshop-zero-trust-security-operations) to align teams on end-to-end operational improvements.

Use focused implementation guidance where the risk requires it:

- [Implement AI observability](/en-us/security/zero-trust/sfi/observability-ai-systems)
- [Rapid anomaly detection and response](/en-us/security/zero-trust/sfi/rapid-anomaly-detection-response)
- [Centralize access to security logs](/en-us/security/zero-trust/sfi/centralize-access-to-security-logs)
- [Respond to incidents in AI systems](/en-us/security/zero-trust/sfi/incident-response-ai-systems)
- [Secure autonomous agentic AI systems](/en-us/security/zero-trust/sfi/secure-agentic-systems)
- [Identify risk for autonomous agentic AI](/en-us/security/zero-trust/sfi/manage-agentic-risk)
- [Defend against indirect prompt injection attacks](/en-us/security/zero-trust/sfi/defend-indirect-prompt-injection)
- [Incidents and alerts in the Microsoft Defender portal](/en-us/defender-xdr/incidents-overview)
- [Monitor Zero Trust with Microsoft Sentinel](/en-us/azure/sentinel/sentinel-solution)

Introduce automation in bounded stages: recommend, require approval, automate low-impact actions, and then expand autonomy where evidence supports it. Keep detailed configuration steps in canonical product documentation, and use SAF to keep people, process, architecture, and technology aligned.