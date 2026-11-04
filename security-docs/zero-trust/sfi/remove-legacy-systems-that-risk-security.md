---
layout: Conceptual
title: Remove legacy systems that risk security – Zero Trust | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/remove-legacy-systems-that-risk-security
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Remove legacy systems that risk security is part of the protect tenants and isolate production systems pillar of the Secure Future Initiative (SFI), focusing on removing legacy and unmanaged tenants to reduce Microsoft’s attack surface.
ms.date: 2026-03-05T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: design-pattern
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
locale: en-us
document_id: 28dde300-9c60-0da2-59fd-9c0c128bfb96
document_version_independent_id: 28dde300-9c60-0da2-59fd-9c0c128bfb96
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/remove-legacy-systems-that-risk-security.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/remove-legacy-systems-that-risk-security
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/remove-legacy-systems-that-risk-security.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/062d60c9-ee0f-402e-a046-b4e67c3572d6
- https://authoring-docs-microsoft.poolparty.biz/devrel/4e834929-0ce1-4c1d-9c81-fcb14721edfb
- https://authoring-docs-microsoft.poolparty.biz/devrel/f488294d-f483-456e-94e3-755f933b811b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/17d3b3f6-a66e-4c69-9774-14a73c38e669
- https://authoring-docs-microsoft.poolparty.biz/devrel/75670257-a3f0-4627-9981-8046f99219e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/02662057-0b9b-40f4-a3c7-537125b6d283
platformId: c50c7f58-4c05-6a78-3c73-7c83d58f1f19
---

# Remove legacy systems that risk security – Zero Trust | Microsoft Learn

**Pillar name: Protect tenants and isolate production systems** **Pattern name: Remove legacy systems that risk security**

## Context and problem

Modern threat actors actively target unmanaged, legacy, or employee-created tenants that lack modern security controls. These tenants often:

- Operate outside centralized governance
- Lack strong authentication, Conditional Access, and compliance enforcement
- Introduce configuration drift and lateral movement paths
- Persist well past their intended purpose (for example, abandoned test/demo environments)

In production environments, these risks are amplified. A single compromised legacy tenant can be used as a launchpad for broader attacks, undermining Zero Trust principles and exposing sensitive systems. Real-world incidents include password spray against non-production tenants and abuse of legacy test apps to pivot into corporate environments.

Tenant sprawl inflates attack surface, complicates governance, and slows incident response. Reducing and governing the tenant footprint is one of the highest leverage security investments most enterprises can make.

## Solution

Microsoft implemented a comprehensive cleanup and segmentation initiative under the Secure Future Initiative (SFI) to eliminate legacy and unmanaged tenants, while hardening the remaining estate. Key actions included:

- **Discovery and cleanup at scale**: Comprehensive inventory across the Microsoft cloud footprint and removal of millions of unused or insecure tenants via automated workflows and time‑bound scream tests. Microsoft removed 6.9 million unused and aged tenants as of November 2025.
- **Segmentation and hardening**: Clear classification of tenants (Primary production environments, Additional production environments, and Temporary non-production environments), Conditional Access enforcement, logical isolation, and secure‑by‑default baselines.
- **Tenant lifecycle policy**: Automated creation guardrails and 90‑day expiration for non‑production/ephemeral tenants, with extensions requiring deputy CISO approval.
- **Modernization**: Migration of legacy platforms (for example, ASM → ARM), secrets hygiene (managed identities, Key Vault), and elimination of shared secrets.
- **Governed creation**: Policy‑driven tenant creation with approval workflows and attribution; default block by default cross‑tenant trust.

## How does Microsoft classify their tenants?

To make risk explicit and controls predictable, Microsoft internal tenants are scoped by persona, business purpose, and risk profile.

The resulting classifications are summarized in the following table.

| **Class** | **Examples** | **Lifecycle** | **Cross‑tenant posture** | **Typical controls** |
| --- | --- | --- | --- | --- |
| **Primary production environments** (core tenants)Primary production and productivity tenants that run Microsoft's most critical services and operations.Tightly governed with the highest security standards. | Microsoft's main productivity environment supporting daily operations for our workforce. Environments running Microsofts cloud services for our customers. | Long‑lived | Strict, minimal exceptions | Strong authentication only (FIDO2/Auth App)JIT elevation Guest users restricted permissions Secure Access Workstation (SAW) for admins Admin‑approved app consentApps must register in authoritative CMDBTwo‑year log retention Centralized certificate lifecycle. |
| **Additional production environments** (auxiliary tenants) Production scenarios intentionally isolated from core.Used when isolation reduces risk to primary environments or avoids constraints like product limitations. | Mergers and acquisitions (for example, LinkedIn).Use-case specific environments (for example, PCI resources). | Long‑lived | Strict, governed intake and triage. | Same security bar as core. |
| **Temporary non-production environments** (ephemeral tenants)Short‑lived tenants. | Temporary environments for validating functionality.Short‑term environments used for demonstrations or troubleshooting. | 90‑day maximum with extensions by deputy CISO. | No B2B or multi‑tenant app paths to production environments. | Strong MFAFIDO2/Auth App only Baseline CA policiesMicrosoft Entra ID P2 or E5 required for advanced security features. |
| **Unsanctioned tenants** (satellite tenants) Legacy, non‑compliant, weak attribution. Historically had unintended access paths. | NA | Target state: decommission | Quarantined.Scream test and accelerated retirement | Only temporary containmentMigrate/adopt ephemeral or converge into a few auxiliary tenants where justified. |

## Guidance

Designing the right Microsoft Entra tenant architecture is a strategic decision that balances security, compliance, administrative complexity, and user experience.

- While a single production tenant is recommended for simplicity and user experience optimization, some organizations (including Microsoft) face business and technical requirements that drive the adoption of multiple tenants.
- Organizations must minimize the number of tenants while meeting isolation and regulatory needs, using multiple tenants only where they add clear, intentional value to reduce risk.

| **Use case** | **Recommended action** | **Resource** |
| --- | --- | --- |
| **Discover and classify** | - Restrict create tenant permissions in sanctioned/managed tenants with Microsoft Entra.- Discover your Microsoft cloud footprint and build a full inventory across Microsoft cloud footprint using billing/subscription telemetry, M365 sign‑in/audit logs, and app consent data. - - Define your own tenant classification nomenclature based on your requirements. - Classify tenants per your organizations criteria and attribute clear ownership. | [Default user permissions](/en-us/entra/fundamentals/users-default-permissions)[Discover your Microsoft cloud footprint](/en-us/azure/cost-management-billing/manage/discover-cloud-footprint). |
| **Quarantine and regain control** | - Quarantine unknown/legacy tenants with tenant restrictions and block-by-default inbound trust using cross-tenant access settings. - Use time‑bound scream tests to validate business dependency and reduce false positives. - Where you own the tenant but lack admin rights, open a support process to regain access and bring to baseline. | [Cross-tenant access overview](/en-us/entra/external-id/cross-tenant-access-overview)[Configure tenant restrictions](/en-us/entra/external-id/tenant-restrictions-v2) |
| **Enforce lifecycle and baselines** | - Enforce classification criteria and security controls through controlled tenant creation workflows.- These workflows should include mechanisms to attribute ownership to individuals in the organization.- Actively retire environments that don't meet standards. | NA |
| **Modernize platforms and secrets** | - Migrate off legacy stacks (for example, ASM → ARM).- Eliminate shared secrets.- Prioritize managed identities.- Store secrets in Azure Key Vault. | [Architecture strategies for protecting application secrets](/en-us/azure/well-architected/security/application-secrets)[Managed identity best practice recommendations](/en-us/entra/identity/managed-identities-azure-resources/managed-identity-best-practice-recommendations) |

## Outcomes

### Benefits

- **Reduced attack surface:** Eliminates outdated/misconfigured tenants and removes unintended traversal paths
- **Containment of compromise:** Strong isolation and policy enforcement limit lateral movement
- **Improved governance:** Lifecycle and intake policies drive a secure-by-default approach
- **Operational efficiency:** Less technical debt, clearer ownership, and simpler access models

### Trade‑offs

- Cross‑business coordination to classify, migrate, and retire tenants
- Investment in automation for discovery, classification, and expiration
- Temporary disruption for low‑value test environments during cleanup
- Cultural change to adopt tenant lifecycle patterns (including time-bound if applicable) and to standardize exception handling

## Key success factors

Track and review, at least quarterly:

- Number of unused or unmanaged tenants identified and removed.
- Percentage of tenant environments classified and governed under standardized policies, with up-to-date ownership information.
- Migration rate from legacy infrastructure (for example, ASM to ARM).
- Reduction in authentication activity from legacy systems or high-risk tenants.
- Enforcement rate of Conditional Access policies and additional security controls across all tenant types.

## Summary

Organizations that systematically discover, segment, and eliminate legacy systems and unmanaged tenants dramatically improve their security posture. As enterprises shrink the attack surface, enforce tenant lifecycle governance, and align with Zero Trust architecture, they build resilience against modern threats without sacrificing agility where short‑lived tenants are appropriate.

By removing legacy systems that risk security, you can improve your organization's security posture by reducing attack surfaces and eliminating legacy vulnerabilities.