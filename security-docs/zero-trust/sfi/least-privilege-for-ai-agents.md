---
layout: Conceptual
title: Least privilege for AI agents with Microsoft Entra Agent ID | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/least-privilege-for-ai-agents
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn how to apply least-privilege identity, authorization, tool access, auditing, and revocation controls to AI agents.
ms.date: 2026-07-14T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: design-pattern
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
locale: en-us
document_id: 6b4d1b58-facf-9ac1-98e6-6708562df2ae
document_version_independent_id: 6b4d1b58-facf-9ac1-98e6-6708562df2ae
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/least-privilege-for-ai-agents.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/least-privilege-for-ai-agents
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/least-privilege-for-ai-agents.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
- https://authoring-docs-microsoft.poolparty.biz/devrel/43093068-2dda-408b-b3fe-dfd705c84f78
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
- https://authoring-docs-microsoft.poolparty.biz/devrel/e453d60d-ba7e-43bc-8028-ec38e6b62512
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 0026c1d0-5934-48bc-125f-54165931a02b
---

# Least privilege for AI agents with Microsoft Entra Agent ID | Microsoft Learn

**Pattern:** Least-privilege AI agents

**Practice:** Protect identities and secrets; Secure by design; Secure by default

As organizations adopt agentic AI, the security question shifts from whether an agent can complete a task to whether it should be allowed to perform each action, against which resources, and under whose authority. This pattern frames least privilege as a design requirement for agents: identity, scope, tool access, and auditability must be defined before autonomy expands.

## Context and problem

Agentic AI systems can plan and execute multistep workflows by calling tools (APIs, plugins, automation runbooks) and accessing enterprise data. Unlike traditional automation, agents often chain actions across multiple systems, sometimes across tenants, and can take delegated actions with minimal or no human intervention.

Without a first-class identity model, explicit scoping, and enforceable authorization checks, agents might accumulate excessive permissions, operate outside intended boundaries, or create unclear accountability for actions taken. A practical approach is to maintain a stable, lifecycle-managed agent identity while making privileges *time-limited* through just-in-time (JIT) entitlements (temporary role activation, short-lived tokens, or approvals) so higher privilege exists only for the duration of a specific workflow.

This scenario presents the following security challenges:

- **Identity ambiguity.** Agents might run under shared secrets, service principals, or mixed "on behalf of user" modes, making it unclear which principal is responsible for an action and which approvals were required.
- **Permission creep and excessive aggregate privileges.** Teams grant broad roles to unblock pilots, then never narrow scopes as workflows stabilize. Alternatively, teams layer many "narrow" roles without task separation. The combined roles can create overly broad effective access. Without aggregate permissions analysis, the agent's true capability (what it can do across systems end-to-end) is easy to underestimate.
- **Over-broad tool access.** If an agent can invoke any available tool or action, a single prompt injection or workflow bug can trigger high-impact operations (export, delete, privilege changes) or chain actions across services. This risk is especially high in cross-tenant, guest, and ecosystem scenarios without explicit tool or action policy enforcement.
- **Weak audit trails.** Logs often capture the chat response, not the underlying tool actions, scopes, and downstream authorization decisions (with correlation IDs) needed for forensics and regulatory inquiry.
- **Slow revocation and incomplete containment.** If disabling an agent is complex or incomplete (tokens persist, keys are shared, downstream systems don't re-check authorization), incident response is delayed. This condition becomes more urgent when agents span production resources, multiple environments, or cross-tenant boundaries where tenant isolation and fast "kill switch" paths are essential.

## Guidance

Use the following table to map common agent deployment scenarios to recommended security controls. Replace "Resource" entries with your internal standards, platform documentation, and relevant Patterns and Practices (PnP) guidance.

| Use case | Recommended action | Resource |
| --- | --- | --- |
| Common security controls for agent deployments | - Use a unique, dedicated agent identity with a named owner/sponsor and approver.- Document the agent's purpose, approved data access, tool dependencies, and operating environment.- Review aggregate and effective permissions across roles, tools, and downstream systems.- Deny unreviewed tools, plugins, integrations, and cross-tenant or guest paths by default.- Log agent identity, role, effective scope, action, resource, correlation ID, and "on behalf of" user where applicable.- Test revocation paths, including disabling the agent, rotating credentials, invalidating tokens, and removing stale permissions.- Re-review access when workflows, tools, data scope, or deployment environment materially change. | [What is Microsoft Entra Agent ID?](/en-us/entra/agent-id/what-is-microsoft-entra-agent-id)[Overview of agent identities in Microsoft Entra](/en-us/entra/agent-id/agent-identities)[Microsoft Entra audit logs](/en-us/entra/identity/monitoring-health/concept-audit-logs)[Microsoft Entra Privileged Identity Management](/en-us/entra/id-governance/privileged-identity-management/) |
| Agent summarizes documents across a workspace | - Grant a task-based (read-only in this case) role scoped to the workspace or collection (resource boundary) and restrict to approved repositories and sites.- Apply data boundary controls (labels and sensitivity) to exclude restricted content and limit cross-label aggregation.- Allowlist retrieval tools and actions only; verify downstream authorization on each call (don't rely on the orchestrator alone).- Log retrieval sources, effective scope (resource and data), correlation IDs, and monitor for anomalous scope expansion. | [What is Microsoft Entra Agent ID?](/en-us/entra/agent-id/what-is-microsoft-entra-agent-id)[Overview of agent identities in Microsoft Entra](/en-us/entra/agent-id/agent-identities) |
| Agent creates or updates tickets based on findings | - Separate read role (evidence gathering) from write role (ticket creation).- Allowlist only "create or update ticket" actions; block delete and admin actions.- Require human approval for bulk updates.- Log all write actions with role, scope, and correlation IDs for traceability. | [Overview of agent identities in Microsoft Entra](/en-us/entra/agent-id/agent-identities)[What is the Microsoft agent identity platform?](/en-us/entra/agent-id/what-is-agent-id-platform) |
| Agent performs remediation (scripts and runbooks) | - Use JIT elevation or approval gates for execution.- Scope to specific resource groups and services; deny subscription-wide rights.- Maintain rollback procedures and change tracking.- Require step-up controls for destructive or high-impact actions (delete, privilege change). | [What is Microsoft Entra Agent ID?](/en-us/entra/agent-id/what-is-microsoft-entra-agent-id)[What is the Microsoft agent identity platform?](/en-us/entra/agent-id/what-is-agent-id-platform) |
| Agent accesses regulated data (PII, PHI, or finance) | - Require explicit data access approvals and stricter scopes.- Enforce strong auditing and retention for access events.- Validate that downstream systems enforce authorization (not just orchestrator).- Restrict cross-tenant or external data movement unless explicitly approved. | [What is Microsoft Entra Agent ID?](/en-us/entra/agent-id/what-is-microsoft-entra-agent-id)[Overview of agent identities in Microsoft Entra](/en-us/entra/agent-id/agent-identities) |

## Outcomes

### Benefits

- **Minimized impact of unintended agent actions through improved access controls and isolations.** Scoped RBAC, explicit resource, data, and action boundaries, and tool allowlists limit the impact of prompt injection, workflow drift, and chained tool execution.
- **Strengthens authorization controls across systems.** Revalidation of identity, roles, and scope at every hop (orchestrator → tool → downstream service) helps prevent a weak integration from bypassing intended controls.
- **Improves auditability and enhances incident response investigations.** End-to-end logging (identity, role, scope, tool, action, correlation IDs) enables rapid reconstruction of events, ownership, and containment boundaries during incidents.
- **Establishes accountability and ownership of agent actions.** Treating agents as first-class principals with named owners and explicit "on behalf of" context removes ambiguity in authorization and responsibility.
- **Reduces standing privilege through time-bound access.** Time-limited entitlements reduce standing access, ensuring higher privilege exists only for the duration of a workflow.
- **Enables safer cross-system and cross-tenant interactions.** Explicit scoping and safe tool binding help prevent unintended data correlation or high-impact action chaining across systems.
- **Enhances predictability and governance of change management processes.** Workflow changes require explicit re-evaluation of roles, scopes, and tool access, turning authorization into a controlled and reviewable decision.

### Trade-offs

- **Increased upfront design effort** Modeling task-based roles, scopes, and tool allowlists requires more initial planning than granting broad roles.
- **Operational complexity for lifecycle management** Requires ongoing processes for JIT entitlements, access reviews, role refinement, and revocation testing.
- **Friction for high-impact operations** Step-up approvals, JIT elevation, and restricted tool sets might slow workflows that require privileged or destructive actions.
- **Dependency on downstream enforcement** Security posture relies on integrated systems correctly re-validating authorization. Gaps can introduce risk if not validated end-to-end.

## Key success factors

- **Identity governance**
    - Percentage of production agents with a unique identity and named accountable owner
    - Percentage of agents operating as first-class principals (no shared credentials)
- **Scoped authorization**
    - Percentage of agents with roles scoped to resource, data, and action boundaries
    - Percentage reduction in broad (tenant-wide or subscription-wide) role assignments
- **Tool and action control**
    - Percentage of agent tool access governed by explicit allowlists of high-risk actions (delete, export, privilege changes) gated by approval or JIT elevation
- **Audit and monitoring coverage**
    - Percentage of agent actions emitting required audit fields (identity, role, scope, action, correlation ID)
    - Percentage of workflows with end-to-end traceability across orchestrator → tools → downstream systems
- **Revocation and containment readiness**
    - Mean time to revoke or disable an agent identity (including token invalidation)
    - Percentage of environments validated with tested kill-switch and recovery procedures

## Implementation guidance

The following implementation steps provide a recommended approach for applying this pattern using Microsoft Entra Agent ID and Microsoft Agent 365. Teams should adapt these steps based on their agent architecture, deployment model, and organizational requirements.

1. **Discover and assess agent access**: Inventory agents and tool integrations currently deployed (or planned), including cross-tenant and guest integrations. Identify their effective aggregate permissions end-to-end.
2. **Standardize agent identities and ownership**: Use [What is Microsoft Entra Agent ID?](/en-us/entra/agent-id/what-is-microsoft-entra-agent-id) to define agent identity standards, including naming, ownership, lifecycle, and credential handling. Create or convert agents to unique identities.
3. **Apply task-scoped authorization**: Model task-based roles and scopes. Replace overly broad roles with more narrowly scoped assignments where appropriate.
4. **Gate high-impact actions**: Introduce tool and action allowlists. Consider approval-based or time-bound elevation by using [Microsoft Entra Privileged Identity Management](/en-us/entra/id-governance/privileged-identity-management/pim-configure) for privileged operations.
5. **Validate logging, revocation, and downstream enforcement**: Use [Microsoft Entra audit logs](/en-us/entra/identity/monitoring-health/reference-audit-activities) and application permission activity logs to verify traceability, permission changes, and response readiness. Validate end-to-end authorization and JIT elevation.

## Summary

This pattern is intended to help teams deploy agentic AI systems more safely by treating agents as first-class identities, applying least-privilege RBAC with clearly defined scopes, and allowlisting tool actions, while supporting auditability and enabling revocation workflows when these controls are implemented and maintained appropriately. This pattern provides a foundation for securely scaling agent adoption by establishing consistent identity, access, governance, and lifecycle controls throughout the agent lifecycle.

> 
> **Secure least privilege access for agents with familiar Microsoft Entra controls** Manage, govern, and protect agent identities using identity, lifecycle, and access controls similar to those used for employees—with identity, lifecycle, and access controls for agents in Microsoft Entra, now available as part of Microsoft Agent 365. [Learn more](https://www.microsoft.com/security/business/identity-access/microsoft-entra-agent-id)