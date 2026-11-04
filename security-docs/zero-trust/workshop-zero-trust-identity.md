---
layout: Conceptual
title: Microsoft Zero Trust Workshop - Identity | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/workshop-zero-trust-identity
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn about the Identity pillar in the Microsoft Zero Trust Workshop
ms.date: 2026-05-31T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 2360449d-545d-2f82-adb2-b356b9d75452
document_version_independent_id: 2360449d-545d-2f82-adb2-b356b9d75452
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/workshop-zero-trust-identity.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/workshop-zero-trust-identity
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/workshop-zero-trust-identity.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/1ae5c491-970a-4062-8301-6336e69f9026
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/f2c3e52e-3667-4e8a-bf11-20b9eaccdc8c
platformId: 5f4962e3-773d-360d-c225-2091a5e12744
---

# Microsoft Zero Trust Workshop - Identity | Microsoft Learn

In a Zero Trust framework, identity is the foundational control plane. Every access decision to a device, application, or data resource begins with verifying who the user is, what their privileges are, and whether their context meets policy.

The Identity pillar in the Zero Trust Workshop ensures that organizations align with Zero Trust principles (verify explicitly, enforce least privilege, and assume breach) across all identities. It provides a **prioritized and actionable implementation backlog** for modernizing identity capabilities.

Identity pillar workshop guidance focuses on assessing your current identity posture, identifying gaps, and defining prioritized actions to modernize identity controls, reduce risk, and enable secure, seamless access across your environment.

## Workshop implementation

The Identity workshop covers the implementation areas summarized in the table.

| **Area** | **Details** |
| --- | --- |
| **Inventory and understand identity assets** | Compile a complete inventory of users, applications, service principals, groups, and identity attributes.Assign ownership, define accountability, and classify critical identity assets to establish governance and visibility across the identity estate. |
| **Establish a strong Conditional Access foundation** | Implement a comprehensive Conditional Access strategy that continuously evaluates identity, device state, risk signals, and session context. Define and enforce consistent access policies across users, applications, and scenarios, including workforce, guests, and legacy access paths. |
| **Modernize authentication and eliminate legacy protocols** | Standardize on modern authentication across all applications and services.Eliminate legacy authentication methods and migrate existing systems to secure, standards-based authentication protocols to reduce exposure to credential-based attacks. |
| **Transform application and identity infrastructure** | Reduce dependency on on-premises identity systems by migrating applications to Microsoft Entra ID-based authentication and single sign-on (SSO). Decommission legacy federation and web access management infrastructure.Modernize application access patterns to support Zero Trust. |
| **Enforce least privilege and role-based access** | Assign access based on job function using role-based access control (RBAC) and access packages. Define role models, enforce least privilege, and continuously validate access through access reviews and policy-based governance to ensure users only have the permissions they require. |
| **Protect privileged and workload identities** | Secure administrative and high-risk accounts using just-in-time access, Privileged Identity Management (PIM), strong authentication, and hardened access paths.Extend governance and protections to workload identities and service principals to reduce risk from overprivileged or unmanaged identities. |
| **Establish identity data governance and provisioning flows** | Define authoritative identity data sources, attribute schemas, and data flows across systems. Implement provisioning pipelines and connectors to ensure identity data is consistent, accurate, and reliably synchronized across applications and services. |
| **Automate identity lifecycle and provisioning** | Implement automated provisioning and lifecycle workflows (joiner, mover, leaver) across authoritative systems such as HR platforms. Ensure access is granted, updated, and removed automatically based on lifecycle events, with monitoring and validation of provisioning processes. |
| **Strengthen credential security with passwordless authentication** | Reduce reliance on passwords by implementing password protection and deploying phishing-resistant, passwordless authentication methods such as FIDO2, Windows Hello for Business, and Microsoft Authenticator. Drive adoption of strong authentication methods across the organization. |
| **Govern external and partner identities** | Establish controlled onboarding, access assignment, and lifecycle processes for external users and partner organizations. Implement access packages, sponsorship models, and monitoring to ensure external identities are properly governed and aligned with organizational policy. |
| **Clean up and remediate existing access** | Identify and remediate overprivileged accounts, unused identities, and stale group memberships.Conduct access reviews and implement ongoing governance processes to maintain least privilege and reduce accumulated identity risk over time. |
| **Enable identity security monitoring and response (SecOps)** | Integrate identity signals into security operations by incorporating identity protection, threat detection, and centralized logging. Monitor identity health, detect suspicious activity, and investigate and respond to identity-based threats using security analytics and operational playbooks. |

## Assess identity

The Zero Trust Assessment tool can assess your identity configuration against a range of security best practices. [Learn more](/en-us/security/zero-trust/assessment/overview).