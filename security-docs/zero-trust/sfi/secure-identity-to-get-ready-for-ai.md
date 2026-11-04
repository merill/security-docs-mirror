---
layout: Conceptual
title: Secure identity to get ready for AI with Microsoft Entra | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/secure-identity-to-get-ready-for-ai
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn how to prepare identities for AI with Microsoft Entra through phishing-resistant authentication, privileged access controls, and monitoring.
ms.date: 2026-10-27T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
ai-usage: ai-assisted
ms.custom: msecd-doc-authoring-1028
locale: en-us
document_id: 28d6288e-3724-03a9-f150-a1db08a90f4e
document_version_independent_id: 28d6288e-3724-03a9-f150-a1db08a90f4e
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/secure-identity-to-get-ready-for-ai.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/secure-identity-to-get-ready-for-ai
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/secure-identity-to-get-ready-for-ai.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
platformId: 27744fd4-3808-1090-990d-ea5e341ca390
---

# Secure identity to get ready for AI with Microsoft Entra | Microsoft Learn

**Security imperative: Get ready for AI** **Job to be done: Secure identity**

Securing identity to get ready for AI starts with your existing identities: get users and admins onto phishing-resistant MFA and eliminate standing privilege with Privileged Identity Management (PIM). That foundation is what lets the new AI identities you add inherit least privilege rather than excess, and lets AI-powered capabilities detect, investigate, and respond to threats faster.

## Context and problem

AI has made identity attacks easier to run at scale. Phishing, social engineering, credential attacks, and privilege escalation now can arrive faster, and SMS codes and push approvals can be intercepted. They land on exposure most tenants already carry. Passwords and basic MFA sit on accounts that can change everything, and privilege is assigned permanently rather than activated when needed. Identities commonly hold far more access than they use, so one compromised account inherits that blast radius.

## Solution

Six sequential steps can help you secure identity to get ready for AI: start secure, take back standing privilege, and extend one policy engine to identities. Phishing-resistant credentials make least privilege enforceable, least privilege makes policy meaningful, and enforceable identity policies lay the foundation for AI – including securing new AI identities and using AI to defend the environment.

## Guidance

Security practitioners, including identity administrators, can secure identity in their organizations by following this step-by-step actionable guidance, implemented through Microsoft Entra.

| **Step** | **Recommended action** | **Resource** |
| --- | --- | --- |
| 1. Protect privileged accounts first | Require MFA for every administrator through Microsoft-managed Conditional Access policies or security defaults, then move administrators to device-bound passkeys or FIDO2 security keys. Use cloud-only accounts for privileged roles and keep at least two emergency access accounts. | [Secure your Microsoft Entra identity infrastructure](/en-us/azure/security/fundamentals/steps-secure-identity) |
| 2. Extend phishing-resistant authentication to the workforce | Plan a phishing-resistant passwordless rollout first. Match methods to user persona, industry, and device readiness: typically Windows Hello for Business, device-bound passkeys for admins and highly regulated users, synced passkeys for others, and certificate-based authentication only where necessary. Then enforce gradually with Conditional Access authentication strengths across users and resources. | [Plan a phishing-resistant passwordless authentication deployment](/en-us/entra/identity/authentication/how-to-deploy-phishing-resistant-passwordless-authentication) |
| 3. Eliminate standing privilege | Run Privileged Identity Management discovery and insights to baseline permanent roles and privileged service principals, then trim, convert to eligible, or remove each one. Make activation time-bound, justified, and MFA-gated, and govern guest and partner access through access packages that expire. | [Microsoft Entra roles Discovery and insights (preview) in Privileged Identity Management former Security Wizard - Microsoft Entra ID Governance](/en-us/entra/id-governance/privileged-identity-management/pim-security-wizard) |
| 4. Cover every user, and resource with Conditional Access | Scope policies broadly across users and resources, block legacy authentication, and require Intune device compliance. | [Azure identity management and access control best practices](/en-us/azure/security/fundamentals/identity-management-best-practices) |
| 5. Respond to identity risk in real time | Enable Microsoft Entra ID Protection with sign-in risk policies that require MFA at medium risk and above and user risk policies that require a secure credential reset at high risk. Turn on continuous access evaluation and integrate Microsoft Defender XDR signals. | [Continuous access evaluation in Microsoft Entra](/en-us/entra/identity/conditional-access/concept-continuous-access-evaluation) |
| 6. Make coverage continuous | Export sign-in and audit logs to Microsoft Sentinel or Azure Monitor, alert on privileged activations, run recurring access reviews, and audit application consent grants. | [Secure your Microsoft Entra identity infrastructure](/en-us/azure/security/fundamentals/steps-secure-identity) |

## Outcomes

- Fewer attacks succeed at the credential: phishing-resistant methods remove the password and SMS paths that AI-scaled phishing and voice impersonation depend on.
- The blast radius is bounded: an administrator without standing privilege holds a time-boxed activation window.
- Investigations are attributable: every user has an identity, with audit signals that link back to a named owner.

## Key success factors

To measure progress, track the following:

- Percentage of users and administrators protected by phishing-resistant authentication methods
- Number of successful SMS, voice, and legacy authentication sign-ins, trending toward zero
- Percentage of privileged roles converted from permanent assignment to eligible, just-in-time activation
- Percentage of users and workloads on their own identity, with a named owner and sponsor
- Conditional Access coverage across users, devices, applications, and user identities, with remaining gaps named
- Time to revoke access for a risky session, measured in minutes
- [Identity Secure Score](https://zt.microsoft.com/) against target, trending up quarter over quarter

## Summary

Securing identity to get ready for AI changes the question from who a person is to what each identity is allowed to do. These six steps can help you answer that question: protect the administrators, move the workforce off phishable factors, take back standing privilege, put one policy engine in front of everything, respond to risk in the moment, and keep looking for what the policies missed. The first three steps alone are critical: removing the password from your most powerful accounts and putting a clock on every privileged session.

**By securing identity in sequence, you can govern access to get ready for AI.**