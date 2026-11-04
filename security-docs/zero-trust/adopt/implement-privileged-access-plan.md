---
layout: Conceptual
title: Plan a privileged access architecture | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/adopt/implement-privileged-access-plan
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn how to plan a privileged access architecture
ms.date: 2026-05-24T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
ms.collection:
- zerotrust-adopt
ms.custom: sfi-image-nochange
locale: en-us
document_id: 62c240a7-7d54-01d8-a65d-49565aabaaf9
document_version_independent_id: 62c240a7-7d54-01d8-a65d-49565aabaaf9
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/adopt/implement-privileged-access-plan.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/adopt/implement-privileged-access-plan
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/adopt/implement-privileged-access-plan.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/a3955c7b-f5ee-420d-aff5-d7119738f38b
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/062d60c9-ee0f-402e-a046-b4e67c3572d6
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/b31948f4-2f38-404b-ac93-c3c8c5b3ae33
- https://authoring-docs-microsoft.poolparty.biz/devrel/17d3b3f6-a66e-4c69-9774-14a73c38e669
platformId: 8ad37fb4-5559-4114-1341-9588b2abb83a
---

# Plan a privileged access architecture | Microsoft Learn

This article is part of the [Implement a privileged access architecture](implement-privileged-access) solution guide.

Privileged access presents a critical security risk in most organizations because it enables direct control over identity systems, cloud control planes, and business‑critical assets.

Learn how a [secure privileged access architecture](../security-adoption-scenario-privileged-access) plays a critical role in your business scenario - *[Protect critical business assets](../security-adoption-scenario-secure-assets)* - by reducing this risk and strengthening control over sensitive systems.

Planning is the first step. This article is aimed at implementers and security architects who translate the privileged access architecture into a practical rollout plan (scope, prerequisites, sequencing, and ownership).

During planning you identify which privileged access paths matter most, decide which paths are allowed and which are blocked, and map those decisions directly to the phased implementation to follow.

## Before you start

- Our adoption model defines a set of critical business scenarios aimed at business leaders and decision makers. Learn more about the business outcome [securing and governing privileged access to critical systems](../security-adoption-scenario-privileged-access).
- We use [security disciplines](../security-adoption-discipline-overview) to help teams deliver security outcomes across the business. Learn about the [disciplines associated with privileged access architecture](../security-adoption-discipline-identity-access-privileged-model)

## Planning outcomes

You should finish planning with:

- A shared understanding of which privileged access paths matter most in your environment.
- Agreement on which access paths are allowed, restricted, or eliminated.
- A defined implementation sequence for reducing risk without breaking operations.
- Clear ownership for approving, changing, and reviewing privileged access decisions.
- Direct mapping from planning decisions to implementation phases.

## Implementation goals

Implementation planning translates design goals into enforceable decisions.

Multiple security disciplines and technologies drive outcomes for this solution. The table below shows how planning goals relate to disciplines and downstream implementation.

| **Implementation goal** | **Disciplines involved** | **Planning outcome** |
| --- | --- | --- |
| **Limit exposure of privileged credentials**Minimize when, where, and how privileged credentials can be used. | Strategy and Governance Access and IdentitiesSecurity Architecture | A documented list of roles, actions, and systems that constitute privileged access. Clear rules for when elevation is allowed, how long, and with what approval. Aids enforcement of just‑in‑time access and eliminates standing privilege. |
| **Isolate and monitor privilege access paths**Enforce strong authentication and device trust.Continuously monitor for anomalous behavior. Prioritize detection and response because of high impact. | Security Architecture Access and IdentitiesSecOps | Explicitly defined privileged access paths that are allowed, restricted, or eliminated. For example, PAWs only, approved portals and APIs, no legacy protocols, no direct admin access from personal devices. Provides a solid allow/block model for Conditional Access, interface security, and monitoring. |
| **Reduce the privileged attack surface** Reduce the attack surface by minimizing the number of privileged identities, roles, and assignments. | Strategy, Integration, GovernanceAccess and IdentitiesSecurity Posture Management. | Complete privileged role rationalization.Which roles are required or can be removed, and which workflows must change to avoid standing privilege. Agreement on which roles to remove from permanent assignment.Success measurements. For example, reduction in standing privileged roles. |
| **Separate productivity and administrative workflows** Separate workflows to eliminate the bridge between common attack vectors and enterprise-wide control. | Security Architecture InfrastructureAccess and Identities. | Decisions on where privileged work can occur.Whether dedicated admin accounts and devices are required.Which activities are prohibited from standard productivity environments.Which workflows must move to privileged devices or sessions.These decisions enable device deployment and access enforcement phases without ambiguity. |

## Use security levels for planning

Security levels are used during planning to classify privileged access paths, not just accounts or devices. For planning purposes we use three security levels when reviewing access paths. Note that this implementation guide only focuses on the privileged level.

| **Security level** | **Purpose** |
| --- | --- |
| **Enterprise** | Baseline security for all users and devices. |
| **Specialized** | Increased protection for elevated, high business‑impact roles. |
| **Privileged** | Maximum protection for control plane and tenant‑wide administration. |

When planning privileged access, use security levels to answer:

- Which access paths require the strongest protections?
- Which paths can remain at a lower level temporarily during modernization?
- Where must protections be mandatory before any privileged work is allowed?

Key planning principles:

- Security levels apply to access paths, not just identities.
- If work is performed through a privileged access path, that path must meet the required security level.
- Security levels guide:
    - Enforcement patterns
    - Configuration profiles
    - Conditional Access decisions
    - Implementation sequencing

This allows you to modernize privileged access incrementally while ensuring the highest‑risk paths are addressed first.

[![Diagram showing classifications for privileged identities.](../media/implement-privileged-access-user.png)](../media/implement-privileged-access-user.png#lightbox)

## Sequence implementation to reduce risk

Privileged access modernization must reduce risk without disrupting operations. Planning establishes the sequencing that implementation follows.

A typical planning sequence:

1. **Stop creating new privileged risk**. Prevent privileged activity from continuing on insecure paths while planning and auditing are underway.
    - No new standing privileged role assignments.
    - No new insecure access paths.
2. **Secure the highest-impact access paths first**: Start with the identity control plane (tenant and subscription administrators). Move on to core infrastructure and production systems.
3. **Establish safe foundations**. Defined privileged identities, then configure dedicated privileged devices, and approved access paths.
4. **Expand coverage incrementally**. Tighten enforcement as monitoring and validation mature. Use detection to identify and remediate new or unapproved paths.

This sequencing ensures audits, enforcement, and remediation are valid because protections exist before controls are tightened.

## Map planning to implementation

Implementation enforces the decisions produced during design and planning.

| **Planning output** | **Implementation enforcement** |
| --- | --- |
| **Privileged role definitions and scope** | [Phase 1: Secure the identity control plane](implement-privileged-access-identity). Secure role assignments, PIM configuration, approval workflows, and auditing. |
| **Privileged device requirements** | [Phase 2: Secure devices](implement-privileged-access-devices). Deploy and enforce use of hardened privileged access workstations (PAWs) |
| **Approved and blocked access paths** | [Phase 3: Configure policy](implement-privileged-access-enforce). Configure Conditional Access, interface restrictions, protocol blocking. |
| **Accepted trade-offs and exceptions** | [Phase 1: Secure the identity control plane](implement-privileged-access-identity) and [Phase 3: Configure policy](implement-privileged-access-enforce). Logging, review workflows, break-glass accounts. |
| **Monitoring for privileged access** | [Phase 4: Monitoring and threat detection](implement-privileged-access-monitor). Detection rules, alert prioritization, validation of approved paths. |

Before implementing each phase, make sure you've completed the corresponding planning actions.