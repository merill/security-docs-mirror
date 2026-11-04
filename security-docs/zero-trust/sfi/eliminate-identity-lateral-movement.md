---
layout: Conceptual
title: Eliminate identity lateral movement – Zero Trust | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/eliminate-identity-lateral-movement
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Eliminate identity lateral movement is part of the protect tenants and isolate production systems pillar of the Secure Future Initiative (SFI), focusing on minimizing the potential impact of security incidents through strong tenant isolation, segmentation, and attack surface reduction.
ms.date: 2025-08-05T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: best-practice
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
locale: en-us
document_id: 2ca0efa5-d40e-a5ac-5135-2b7900fd7d02
document_version_independent_id: 2ca0efa5-d40e-a5ac-5135-2b7900fd7d02
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/eliminate-identity-lateral-movement.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/eliminate-identity-lateral-movement
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/eliminate-identity-lateral-movement.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/062d60c9-ee0f-402e-a046-b4e67c3572d6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
- https://authoring-docs-microsoft.poolparty.biz/devrel/17d3b3f6-a66e-4c69-9774-14a73c38e669
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
platformId: a8bfd619-cf1b-1d8b-758d-7390e3b281ad
---

# Eliminate identity lateral movement – Zero Trust | Microsoft Learn

**Pillar name: Protect tenants and isolate production systems** **Pattern name: Eliminate identity lateral movement**

Eliminate identity lateral movement is a core focus of the protect tenants and isolate production systems pillar of the Secure Future Initiative (SFI). This pillar focuses on minimizing the potential impact of security incidents through strong tenant isolation, segmentation, and attack surface reduction.

## Context and problem

Identity lateral movement is a tactic threat actors use to exploit compromised credentials to pivot across systems and elevate privileges. Unlike brute-force attacks or malware-based exploits, identity-based lateral movement can blend in with legitimate user behavior, making it difficult to detect and even harder to stop without strong access to governance.

Recent attacks—such as the Midnight Blizzard—demonstrated how lateral movement can be enabled through overlooked accounts, external guest access, or pivot points created by multitenant Entra applications. These scenarios bypass traditional defenses and allow threat actors to move across organizational boundaries.

Once inside, attackers often:

- Target privileged accounts to escalate access
- Move between tenants or services using shared credentials
- Abuse application permissions or misconfigured roles
- Remain undetected by mimicking normal tenant behavior

## Solution

Combined, the following efforts prevent compromised accounts or applications from becoming springboards for lateral movement within or between tenants:

- Creating a tenant layering standard that allows Microsoft to categorize tenants into layers and define the valid direction for service principal creation.
- Moving customer support workflows and scenarios into a dedicated tenant to reduce the risk of lateral movement.
- Moving off legacy authentication protocols and instead enforce phishing-resistant MFA for all users, including guest accounts.
- Segmenting access by device compliance, location, and risk level using conditional access policies.
- Enforcing least privilege with role-based access controls (RBAC) and time-bound role assignment.
- Replacing password-based application credentials with managed identities and secure key storage.
- Blocking all but explicitly approved external guest user authentication requests to sensitive Entra applications.

## Guidance

Organizations can adopt a similar pattern using the following actionable practices:

| Use case | Recommended action | Resource |
| --- | --- | --- |
| Strengthen authentication | - Require phishing-resistant MFA for all users, including guests<br>- Block legacy authentication and enforce Conditional Access policies<br>- Monitor the dark web for credential leaks and enforce password hygiene for users | [Microsoft Entra Conditional Access documentation](/en-us/entra/identity/conditional-access/) |
| Control privileged access | - Use Microsoft Entra Privileged Identity Management (PIM) to enforce just-in-time and just-enough access<br>- Implement Secure Admin Workstations (SAWs) to separate admin activity from daily use<br>- Limit admin roles to specific apps, groups, or tenants using Restricted Management Administrative Units (RMAU) | [What is Microsoft Entra Privileged Identity Management?](/en-us/entra/id-governance/privileged-identity-management/pim-configure) |
| Segment environments | - Separate production and non-production environments at the tenant and device level<br>- Apply network segmentation in Azure using VNets, subnets, and Network Security Groups (NSGs)<br>- Enforce identity context–based policies for resource access | [Azure network security groups overview](/en-us/azure/virtual-network/network-security-groups-overview) |
| Mitigate pivot points | - Prefer single-tenant app registrations when cross-tenant access is unnecessary<br>- Review and restrict access for multitenant applications and service principals<br>- Disable Entra All Users group and apply Access Reviews to clean up guest accounts | - [What are access reviews?](/en-us/entra/id-governance/access-reviews-overview)<br>- [Microsoft Entra ID Governance documentation](/en-us/entra/id-governance/) |
| Monitor and detect movement | - Use Microsoft Sentinel to detect anomalous privilege escalation, file access, or identity behavior<br>- Integrate Entra ID risk signals and user behavior analytics for early threat detection<br>- Set up alerting for external app consents, dormant accounts, and sudden privilege changes | [Microsoft Sentinel documentation](/en-us/azure/sentinel/) |

## Outcomes

### Benefits

- **Reduced pivot paths:** Guest users and multitenant apps are tightly scoped and actively monitored.
- **Stronger privileged access management:** Admin accounts operate in secure contexts (e.g., Secure Admin Workstations).
- **Improved detection:** Identify and monitor behavioral anomalies and high-risk events.
- **Policy-driven control:** Conditional Access and identity governance tools enforce identity separation and activity boundaries.

### Trade-offs

Implementation requires:

- Coordination across multiple security and identity teams to apply Conditional Access and app controls
- Enforcement of stricter authentication policies, which impacted guest access and collaboration workflows
- Migration from legacy applications that use passwords or weak secrets
- Investment in governance tools to automate reviews and lifecycle management for applications, users, and guest access

## Key success factors

Monitor the following KPIs:

- Reduction in guest users with elevated or group access
- Number of active Conditional Access policies applied to applications and admin roles
- MFA coverage across all identity types
- Frequency of identity-related incident response events
- Percentage of privileged actions originating from secure, segmented devices
- Volume of cross-tenant authentication attempts blocked

## Summary

When threat actors can move laterally across the network, they can access sensitive digital assets, breach data, and disrupt operations. Using stolen credentials, they can elevate their privileges and manipulate backend systems for malicious purposes. This kind of lateral movement is difficult to detect because it looks like standard user behavior.

**Begin eliminating the pathways for identity lateral movement today—and secure every access path, application, and account against silent intrusions.**