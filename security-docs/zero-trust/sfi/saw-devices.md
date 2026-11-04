---
layout: Conceptual
title: Secure Admin Workstations with Microsoft Entra ID | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/saw-devices
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn how secure admin workstations isolate privileged access with hardened devices, Microsoft Entra ID controls, and continuous compliance monitoring.
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
ms.date: 2026-09-24T00:00:00.0000000Z
ms.custom: msecd-doc-authoring-1028
ai-usage: ai-assisted
locale: en-us
document_id: 296c1c96-e7d5-32fa-7d93-30a2a3cc00f1
document_version_independent_id: 296c1c96-e7d5-32fa-7d93-30a2a3cc00f1
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/saw-devices.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/saw-devices
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/saw-devices.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/062d60c9-ee0f-402e-a046-b4e67c3572d6
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
- https://authoring-docs-microsoft.poolparty.biz/devrel/17d3b3f6-a66e-4c69-9774-14a73c38e669
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: a572a7dd-0ae2-23f1-e21e-5d728074ddcc
---

# Secure Admin Workstations with Microsoft Entra ID | Microsoft Learn

**Pillar name: Protect tenants and isolate systems**

**Practice name: Isolating privileged access to hardened workstations**

Privileged access is one of the highest-risk attack surfaces in modern enterprise environments. If you don't deliberately isolate administrative credentials and sensitive operations, a single compromise can expose production systems, identities, and critical business assets. To address this systemic risk, Microsoft established Secure Admin Workstations (SAWs) as a foundational control under the Secure Future Initiative (SFI). By using SAWs, you ensure that privileged actions are performed only from hardened, purpose-built endpoints designed to protect high-impact access paths.

## Context and problem

Privileged operations against production systems introduce significant risk when you perform them from general-purpose or user-managed devices. Compromised endpoints, credential theft, and uncontrolled software execution often create direct paths to high-impact environments.

Challenges faced by organizations include:

- Attackers exploit compromised user devices to pivot into privileged sessions
- Securing third-party supply chains
- Credential theft techniques (phishing, pass-the-hash) that target administrative workflows
- Unrestricted internet and application access increases exposure to malware
- Lack of isolation between admin and everyday tasks expands the attack surface
- Physical or logical tampering that invalidates device trust and compromises systems

Administrative access is a high-value target. When admin accounts are compromised, attackers can rapidly move laterally and impact critical production services.

## Solution

Microsoft enforces the use of Secure Admin Workstations (SAWs) as hardened, dedicated environments for privileged access users who perform sensitive administrative and high-impact operations. These SAWs:

- Require all privileged operations to be performed from dedicated virtual or physical SAW devices
- Restrict application execution to approved software only after it passes a data security review
- Limit network access to approved destinations and enforce controlled browsing
- Separate administrative (host) and productivity (guest VM) environments
- Eliminate local administrative privileges on the workstation
- Enforce strong device authentication by using security keys and certificates
- Apply hardware-based protections, including tamper detection and secure boot
- Maintain continuous compliance through managed configuration and lifecycle controls

These controls create a high-assurance execution environment that reduces exposure and enforces isolation between privileged and non-privileged activities.

## Guidance

Adopt dedicated secure workstations for privileged operations. Apply least privilege, strong authentication, device isolation, and continuous compliance validation to reduce exposure from credential theft and administrative compromise.

| **Use case** | **Recommended action** | **Resource** |
| --- | --- | --- |
| Privileged cloud administration | Deploy hardened admin workstations Enforce Conditional Access Restrict admin sign-in locations | [Privileged access deployment](../../privileged-access-workstations/privileged-access-deployment) |
| DevOps and production engineering | Separate admin and developer context Use isolated virtual environments for privileged work Enforce least privilege with dedicated admin access paths | [Introduction to delegated administration and isolated environments](/en-us/entra/architecture/secure-introduction) |
| High-risk environment access | Require dedicated devices Restrict network paths Enforce device compliance checks | [Microsoft Entra Global Secure Access](/en-us/entra/global-secure-access/overview-what-is-global-secure-access) |
| Credential protection | Use hardware-backed authentication Rotate credentials Restrict reuse across environments | [Windows Hello for Business](/en-us/windows/security/identity-protection/hello-for-business/) |
| Device lifecycle and compliance | Enforce baseline policies Monitor compliance state Reimage or replace compromised devices | [Manage devices with Intune Overview](../manage-devices-with-intune-overview) |

## Outcomes

### Benefits

- Reduces risk of credential theft by isolating privileged workflows from user endpoints.
- Virtual SAW devices can reduce data exposure when you enforce hardened originating devices, network restrictions, and data-transfer controls.
- Limits attack surface through strict application and network controls.
- Increases assurance that production access originates from trusted devices.
- Improves containment by preventing lateral movement from compromised endpoints.

### Trade-offs

- Introduces operational overhead to provision and manage dedicated devices.
- Requires user behavior change to separate administrative and daily workflows.
- Might reduce flexibility due to restricted browsing and application access.
- Increases coordination across identity, endpoint, and security teams.

## Key success factors

Successful adoption depends on measurable enforcement and coverage that includes:

- Percentage of privileged actions executed from compliant secure workstations
- Reduction in privileged access from unmanaged or non-compliant devices
- Coverage of admin roles mapped to dedicated workstation requirements
- Frequency of device compliance validation and policy enforcement
- Rate of detected and remediated non-compliant admin access attempts

## Summary

Uncontrolled administrative access from standard devices creates a direct path for cyberattackers into production systems. Enforcing dedicated secure admin workstations isolates privileged operations, reduces credential exposure, and aligns with Zero Trust principles. Implement this pattern to ensure all high-risk access originates from hardened, compliant, and monitored environments.