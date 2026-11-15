---
layout: Conceptual
title: Understand SecOps roles and operating models | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-discipline-security-operations-roles
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Understand the durable job functions, execution models, and partner relationships required for effective Security Operations.
ms.date: 2026-11-09T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: b535e209-402c-9a3d-e857-5404c540ecd8
document_version_independent_id: b535e209-402c-9a3d-e857-5404c540ecd8
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-adoption-discipline-security-operations-roles.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-adoption-discipline-security-operations-roles
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-adoption-discipline-security-operations-roles.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/540ac133-a371-4dbb-8f94-28d6cc77a70b
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/60bfc045-f127-4841-9d00-ea35495a5800
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 9395fca3-f61c-5184-babe-b5bf647774a7
---

# Understand SecOps roles and operating models | Microsoft Learn

As you develop a [Security Operations (SecOps) discipline](security-adoption-discipline-security-operations), use this article to define the job functions, execution model, and internal partnerships required for effective SecOps.

This guidance is part of the **Microsoft Security Adoption Framework (SAF)**. It describes durable SecOps job functions rather than prescribing an organizational chart or staffing hierarchy.

**SecOps** is the discipline for detecting, investigating, containing, and learning from active threats. A **security operations center (SOC)** is one organizational construct for executing SecOps functions; SecOps functions can also be distributed across teams, service providers, and other models.

## Define the operating model

SecOps outcomes depend on clear accountability, decision authority, effective execution, and strong collaboration with the teams that design, build, and operate the environment.

Define:

- **Accountability** for SecOps outcomes, operational effectiveness, and improvement.
- **Responsibility** for performing each job function and incident task.
- **Decision authority** for containment, business disruption, communications, recovery sequencing, and other material incident decisions.
- **Risk-acceptance authority** for residual risk and exceptions, assigned only to people with delegated authority.
- **Escalation paths** for decisions and work that exceed current authority, capacity, or expertise.

Job functions describe required work and outcomes. Assignment and execution can vary by organization. Assign functions across people, teams, service providers, AI agents, tools, and automation while preserving human accountability, decision authority, and oversight.

Common labels such as Tier 1, Tier 2, and Tier 3 describe one staffing pattern, not a required SecOps hierarchy. Route work by risk, complexity, context, expertise, and authority instead of assuming a fixed human escalation path.

The job-function names in this article align with the evolving role vocabulary in The Open Group Security Roles and Glossary Snapshot series. Adapt assignment and titles to the organization's needs.

[![Diagram showing durable SecOps job functions and their relationships.](media/security-adoption-discipline-operations-roles.png)](media/security-adoption-discipline-operations-roles.png#lightbox)

## Core SecOps job functions

| Job function | Primary outcome |
| --- | --- |
| **SecOps leadership** | Aligns SecOps to business risk, sustains the operating model, develops the workforce, and is accountable for operational effectiveness and improvement. |
| **Triage** | Validates and prioritizes detections, performs well-understood investigations and response actions, and routes work that requires additional context, expertise, or authority. |
| **Investigation** | Determines attack scope, impact, objectives, and persistence; coordinates complex containment and remediation; and produces learning for detections and controls. |
| **Threat hunting** | Uses hypotheses, intelligence, and analytics to find attacker activity that evaded existing detections and to expose visibility or control gaps. |
| **Detection engineering** | Designs, tests, tunes, and maintains detections and investigation procedures based on threat models, hunting, incidents, and operational feedback. |
| **SecOps platform and data engineering** | Delivers reliable SecOps platforms, telemetry pipelines, integrations, data quality, and automation that enable the other functions. |
| **Threat intelligence** | Converts internal and external threat information into decisions and actions for SecOps, security leadership, and partner teams. |
| **Incident coordination and management** | Coordinates technical and business response, maintains shared situational awareness, and routes decisions to people with the required authority. |
| **Attack simulation** | Tests readiness and controls through penetration testing, red teaming, purple teaming, technical exercises, and discussion-based exercises. |
| **Reverse engineering** | Analyzes malicious code, tools, and adversary techniques to improve investigations, detections, and defenses. |
| **Digital forensics** | Preserves and analyzes evidence using approved procedures and chain-of-custody practices when legal, regulatory, or investigative requirements apply. |

Organizations can combine several functions in one role or distribute one function across multiple teams. Keep the functions and intended outcomes explicit even when assignment changes.

## Coordinate the functions

Connect triage, investigation, and hunting with the engineering, intelligence, simulation, and specialist functions that improve detection and readiness. Use incident coordination to connect technical execution with business decisions, and use SecOps leadership to align priorities, capacity, accountability, and improvement to business risk.

During incidents, separate task execution from decision authority. Automation or an assigned responder can execute an approved action, but people with delegated authority remain accountable for decisions with material business, legal, safety, or risk consequences.

## Integrate key partners

SecOps depends on teams that understand and control the affected environment. Define partner responsibilities before incidents and use incident learning to improve the systems they design, build, operate, and govern.

### Technical engineering and operations

Identity, endpoint, network, infrastructure and platform, data and AI, OT, application, and service-management teams provide telemetry and system context; support investigation, containment, recovery, and validation; and implement sustainable fixes.

### Architecture

Enterprise, security, infrastructure, data, access, solution, and software architects define operational requirements and use incident findings to improve trust boundaries, attack-path resistance, resilience, and observability.

### Application and product development

Product and engineering teams provide application context, support investigation and remediation, generate security telemetry, preserve required evidence, and correct product weaknesses based on SecOps learning.

### Security Posture Management

Security Posture Management teams translate incident and threat findings into exposure-reduction priorities, improved baselines and preventive controls, and verified remediation.

### Strategy, governance, and organizational crisis functions

Security strategy and governance, legal, privacy, communications, business continuity, risk, and executive leadership define priorities, accountability, authority, and success measures; support major-incident decisions; and adjust strategy, investments, policies, and exercises based on operational evidence.

Create a closed improvement loop across these partners:

**Incident and threat learning → Security Posture Management → architecture → engineering and operations → strategy and priorities**