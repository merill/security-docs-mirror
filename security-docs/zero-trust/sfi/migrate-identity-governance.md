---
layout: Conceptual
title: Modernize Identity Governance with Microsoft Entra ID Governance | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/migrate-identity-governance
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn how Microsoft Entra ID Governance supports migration from legacy systems to cloud-native access packages, lifecycle controls, and access reviews.
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
ms.date: 2026-09-24T00:00:00.0000000Z
ms.custom: msecd-doc-authoring-1028
ai-usage: ai-assisted
locale: en-us
document_id: ed7e98b8-548d-4c0d-0f6d-3c58ade82bd7
document_version_independent_id: ed7e98b8-548d-4c0d-0f6d-3c58ade82bd7
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/migrate-identity-governance.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/migrate-identity-governance
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/migrate-identity-governance.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ac4b7417-d4c2-43d4-94bf-f22fa1416b34
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68876bab-7da4-4e70-b295-395b3a255a1f
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
platformId: 386ac409-f350-267b-01e9-35862bacb3e7
---

# Modernize Identity Governance with Microsoft Entra ID Governance | Microsoft Learn

**Pillar name: Protect identities and secrets**

**Practice name: Modernize Entitlement Governance with Cloud-Native Controls**

Many organizations still rely on legacy identity governance systems that were built for earlier operating models. These systems are now difficult to manage, customize, and scale. As identity becomes a primary security boundary, these systems can introduce unnecessary complexity, increase operational overhead, and make it harder to enforce consistent access controls. Microsoft addressed this challenge by shifting entitlement governance to Microsoft Entra ID Governance. By using cloud-native lifecycle controls, you can simplify access management, strengthen visibility, and reduce dependence on legacy infrastructure.

## Context and problem

Many organizations have an inconsistent approach to identity governance or rely on legacy identity governance systems. Legacy identity governance platforms, particularly on-premises or heavily customized third-party solutions, introduce significant operational, security, and cost challenges at scale. These systems often rely on bespoke workflows, hybrid dependencies, and manual interventions that slow response times, complicate audits, and increase the risk of misconfiguration.

At Microsoft scale, our previous third-party identity governance solution managed tens of thousands of entitlement objects across hundreds of thousands of users. While functionally comprehensive, the platform required customization and integration effort to meet Microsoft security and compliance requirements. It added complexity across hybrid environments and incurred high recurring costs. These characteristics conflicted with Secure Future Initiative (SFI) goals to reduce the attack surface, simplify identity infrastructure, and move toward cloud-native, policy-driven controls.

Organizations that rely on legacy identity governance systems encounter the same core problem: identity governance systems that are expensive to operate, difficult to evolve, and misaligned with modern Zero Trust and cloud-first security models.

## Solution

To address these challenges, Microsoft migrated identity governance workloads to Microsoft Entra ID Governance, complemented by a secondary in‑house hybrid identity solution for workloads that couldn't immediately transition to cloud‑only management.

The solution focused on:

- Cloud‑first entitlement governance using Microsoft Entra Entitlement Management (EM) and Entra ID Security Groups.
- Explicit classification of entitlements into cloud-only versus on‑premises‑dependent categories.
- Lifecycle‑driven access management, replacing static entitlement assignments with access packages, approvals, and time‑bound policies.
- Intentional non‑lift‑and‑shift migration, recreating access structures in the cloud to avoid propagating legacy misconfigurations.
- Accelerated deprecation timelines to reduce exposure and eliminate dependency on legacy platforms.

By aligning identity governance with Microsoft Entra ID’s native lifecycle, approval, and auditing capabilities, Microsoft reduced operational friction, improved access visibility, and strengthened compliance posture while eliminating a costly and complex third‑party dependency.

## Guidance

Organizations can adopt this pattern by using the following actionable practices:

| Use case | Recommended action | Resources |
| --- | --- | --- |
| Entitlement discovery and classification | Inventory all entitlements, groups, roles, and workflows before migration. Classify each object as cloud-only, hybrid, or on-premises-only based on actual usage patterns rather than design assumptions. Use historical access and provisioning data to identify hidden dependencies. Scope migration realistically to avoid failures caused by undocumented relationships. | [Microsoft Entra ID Governance documentation](/en-us/entra/id-governance/)[Entitlement management documentation](/en-us/entra/id-governance/entitlement-management-overview)[Access reviews documentation](/en-us/entra/id-governance/access-reviews-overview) |
| Cloud-first governance design | Design governance around identity governance primitives rather than recreating legacy workflow logic. Model access using access packages as the primary entitlement construct. Centralize approvals, expirations, and just-in-time access through policy-driven controls. Use security groups strictly as enforcement mechanisms rather than governance logic. | [Microsoft Entra entitlement management overview](/en-us/entra/id-governance/entitlement-management-overview)[Microsoft Entra ID documentation](/en-us/entra/identity/authentication/concept-fido2-compatibility?tabs=web)[Configure access package policies](/en-us/entra/id-governance/entitlement-management-access-package-create) |
| Intentional re-creation, not direct migration | Avoid directly migrating legacy group structures into the cloud. Create new cloud-native security groups with consistent naming conventions. Require entitlement owners to re-establish permissions intentionally. Reconstruct membership programmatically only after governance structures are validated. |  |
| Owner engagement at scale | Treat entitlement owners as active migration participants. Communicate expectations, timelines, and decision points early. Require owners to validate access structures and approve migration choices. Allow alternative solutions only where justified and time-bound. | [Identity governance lifecycle workflows documentation](/en-us/entra/id-governance/what-are-lifecycle-workflows) |
| Phased cloud adoption with clear exit criteria | Use hybrid identity solutions only as temporary off-ramps for workloads that can't yet move to cloud-only governance. Define explicit exit criteria. Track exceptions and review them regularly. Align teams around the benefits of cloud-native governance. | [Hybrid identity documentation](/en-us/entra/identity/hybrid/)[Identity modernization planning guidance](/en-us/azure/cloud-adoption-framework/ready/landing-zone/design-area/identity-access-active-directory-hybrid-identity) |
| Governance validation and continuous assurance | Validate governance outcomes, not just technical migration completion. Monitor provisioning, deprovisioning, and access review activity. Test joiner, mover, and leaver workflows against business expectations. Use audit evidence and review results as continuous assurance mechanisms. | [Access reviews in Microsoft Entra ID](/en-us/entra/id-governance/access-reviews-overview)[Audit logs in Microsoft Entra ID](/en-us/entra/id-governance/entitlement-management-reports) |

## Outcomes

### Benefits

- Reduced exposure to cyberattack by eliminating legacy governance infrastructure.
- Improved visibility into who has access to what, where, and why.
- Faster entitlement changes through automated workflows.
- Lower operational and licensing costs.
- Stronger alignment with Zero Trust and cloud‑native security principles.

### Trade‑offs

- Significant upfront effort for entitlement discovery and cleanup.
- Temporary user friction during access re‑assignment.
- Hybrid exceptions require governance discipline to avoid long‑term sprawl.

## Key success factors

- Executive sponsorship to enforce deprecation timelines.
- Clear entitlement ownership and accountability.
- Automation for migration, validation, and reporting.
- Early customer education on cloud governance benefits.
- Defined service limits and success criteria aligned to Microsoft Entra ID Governance capabilities.

## Summary

Migrating from legacy identity governance solutions to Microsoft Entra ID Governance enables organizations to simplify entitlement management, reduce operational complexity, and strengthen security. Organizations should adopt a cloud-first, lifecycle-driven model centered on access packages, policy-based controls, and continuous validation. By adopting this model, organizations eliminate legacy dependencies, improve visibility into access, and better align with Zero Trust principles.