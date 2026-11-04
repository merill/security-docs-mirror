---
layout: Conceptual
title: Phishing-resistant MFA | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/phishing-resistant-mfa
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Phishing-resistant multifactor authentication (MFA) is part of the protect identities and secrets pillar of the Secure Future Initiative (SFI), focusing on hardening authentication, eliminating unmanaged credentials, enforcing Zero Trust principles, and protecting cryptographic keys.
ms.date: 2025-08-05T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
locale: en-us
document_id: 52cc54c8-b13d-0410-451f-e410c39a2cef
document_version_independent_id: 52cc54c8-b13d-0410-451f-e410c39a2cef
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/phishing-resistant-mfa.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/phishing-resistant-mfa
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/phishing-resistant-mfa.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/5686b492-7c45-4088-8291-ecc0458747d3
- https://authoring-docs-microsoft.poolparty.biz/devrel/43093068-2dda-408b-b3fe-dfd705c84f78
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/798bd9d1-9cc5-4fc7-b0e5-8699d1f6ce2a
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/838f4f15-80c1-4d49-b873-501fe4ed2d28
- https://authoring-docs-microsoft.poolparty.biz/devrel/e453d60d-ba7e-43bc-8028-ec38e6b62512
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5dc5f65-34a8-4bfc-9917-97d1e20c88b2
platformId: c48b7d9e-9a6b-7b16-f05f-80a539df060c
---

# Phishing-resistant MFA | Microsoft Learn

**Pillar name: Protect identities and secrets** **Pattern name: Phishing-resistant MFA**

Phishing-resistant multifactor authentication (MFA) is part of the protect identities and secrets pillar of the Secure Future Initiative (SFI), which focuses on hardening authentication, eliminating unmanaged credentials, enforcing Zero Trust principles, and protecting cryptographic keys. It ensures identity is verifiable, access is accountable, and secrets are defended with rigor across the digital estate.

## Context and problem

Traditional MFA methods such as SMS codes, email-based OTPs, and push notifications are becoming less effective against today’s attackers. Sophisticated phishing campaigns have demonstrated that second factors can be intercepted or spoofed. Attackers now exploit social engineering, man-in-the-middle tactics, and user fatigue (e.g., MFA bombing) to bypass these mechanisms. These risks are amplified in distributed, cloud-first organizations with hybrid workforces and varied device ecosystems.

Traditional MFA is no longer enough—phishing-resistant MFA is the new baseline.

## Solution

To address these challenges, Microsoft launched the phishing-resistant MFA objective under the Secure Future Initiative. The goal: to drive a companywide shift to phishing-resistant MFA, with 100% of user accounts protected with securely managed, phishing-resistant multifactor authentication.

This transformation was implemented through a phased rollout built on:

- Use of passkeys (including but not limited to FIDO2 security keys, Microsoft Authenticator app, Windows Hello for business, macOS Platform SSO Secure enclave etc.)
- Conditional Access enforcement across owned and affiliated tenants
- Identifying and migrating user-based automation (service accounts) to workload identities, depending on the scenario and requirements
- Strong onboarding protections, including Temporary Access Pass (TAP) and video-based identity verification aligned with NIST SP 800-63-4

Microsoft also incorporated phishing-resistant MFA into every stage of the employee lifecycle, embedding it in onboarding, transitions, and deactivation workflows resulting in:

- 92% of employee productivity accounts are protected by phishing-resistant authentication methods
- External user access is secured via phishing-resistant credentials.
- Remote onboarding at scale is achieved with high-assurance identity proofing.

## Guidance

Organizations can adopt a similar pattern using the following actionable practices:

| Use case | Recommended action | Resource |
| --- | --- | --- |
| Workload identities | Identify and migrate user-based automation (service accounts) to workload identities—or consider using certificate-based authentication. | [What are workload identities?](/en-us/entra/workload-id/workload-identities-overview) |
| Time-bound credentials | Use temporary access passes (TAP) to secure onboarding and recovery with time-bound credentials. | [Configure Temporary Access Pass](/en-us/entra/identity/authentication/howto-authentication-temporary-access-pass) |
| Secure onboarding | Use video verification and liveness detection to prevent fraudulent access. | [Face liveness detection](/en-us/azure/ai-services/computer-vision/concept-face-liveness-detection) |
| Stronger authentication methods | Prioritize authentication methods that cannot be phished or reused by deploying FIDO2 or passkey solutions. | [What is FIDO2?](https://www.microsoft.com/security/business/security-101/what-is-fido2)[Passwordless deployment guide](/en-us/entra/identity/authentication/how-to-plan-prerequisites-phishing-resistant-passwordless-authentication) |
| Conditional Access | Align sign-in policies across all tenants and environments using Conditional Access Policies. | [Conditional Access policy templates](/en-us/entra/identity/conditional-access/concept-conditional-access-policy-common?tabs=secure-foundation) |
| User Lifecycle Workflows | Implement user Lifecycle Workflows to register credentials that are resistant to phishing attacks. | [What are lifecycle workflows?](/en-us/entra/id-governance/what-are-lifecycle-workflows) |
|  | Generate TAP credentials based on customized logic. Ensure secure MFA registration and deactivation occur at each user stage. | [Lifecycle Workflow built-in tasks](/en-us/entra/id-governance/lifecycle-workflow-tasks) |

### Benefits

- Strong defense against phishing: Eliminates the most common compromise vectors.
- Reduced user interaction: Cryptographic keys streamline access and reduce fatigue.
- Scalable identity security: Works across platforms, user types, and geographies.
- Improved recovery and support: TAP and liveness verification ensure secure reauthentication.
- Elevated baseline for tenants: Consistent Conditional Access policies raise security for internal and external identities alike.

### Trade-offs

- Device provisioning complexity: Hardware keys and passkeys needed to be distributed to both onsite and remote users.
- Platform disparities: Limited native support for passkeys in some operating systems may require engineering workarounds.
- User experience adjustment: Changing behaviors requires training and communication to ensure adoption.
- Increased implementation effort: Identity infrastructure modernization, conditional policies, and support for segmented rollouts add project scope.

## Key success factors

To track success, measure the following:

- Percentage of users protected with phishing-resistant MFA
- Percentage of sign-ins requiring phishing-resistant methods
- Percentage of accounts onboarded with secure proofing workflows (e.g., TAP + liveness)
- Conditional Access enforcement coverage across tenants
- Decrease in support tickets related to MFA fatigue or lockouts
- Mean time to adopt new credentials securely post-incident
- Inventory applications and migrate applications to use Entra for authentication

## Summary

Phishing-resistant MFA is no longer optional—it is essential for reducing the risk of credential-based attacks. By replacing vulnerable MFA methods with phishing-resistant solutions, Microsoft is advancing both identity security and user trust. Organizations can replicate this model to protect their own environments from today’s most common identity threats.

**By implementing phishing-resistant MFA, you can reduce your organization’s exposure to credential-based attacks.**