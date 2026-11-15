---
layout: Conceptual
title: Microsoft Zero Trust Workshop - Identity | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/workshop-zero-trust-identity
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Learn about the Identity pillar in the Microsoft Zero Trust Workshop
ms.date: 2026-11-12T00:00:00.0000000Z
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
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: 5f4962e3-773d-360d-c225-2091a5e12744
---

# Microsoft Zero Trust Workshop - Identity | Microsoft Learn

Identity is the foundational control plane for Zero Trust. Every access decision begins by verifying the identity, evaluating the request context, and enforcing the least privilege required to access an application, device, workload, or data resource.

The Identity workshop pillar helps organizations assess their current identity posture, identify gaps, and create a prioritized implementation roadmap across workforce, external, privileged, and workload identities.

The Identity workshop pillar corresponds to the Identity technology defined in the [Microsoft Security Adoption Framework (SAF)](deploy/overview).

## Why focus on identity?

Strong identity controls reduce the risk of credential theft, excessive permissions, unmanaged access, and identity-based attacks. The Identity Workshop applies the Zero Trust principles of verify explicitly, use least privilege, and assume breach to human and non-human identities across cloud and hybrid environments.

The expected output is an actionable backlog of identity projects prioritized into First, Then, and Next based on organizational risk, dependencies, implementation effort, user impact, and readiness.

## Identity implementation areas

| **Area** | **Details** |
| --- | --- |
| **Inventory and understand identity assets** | Inventory users, groups, applications, service principals, managed identities, privileged and emergency access accounts, external identities, resources, and hybrid identity infrastructure. Establish ownership and accountability for critical identity assets. |
| **Establish a strong Conditional Access foundation** | Design and implement Conditional Access policies that evaluate identity, authentication strength, device state, risk, network context, application, and session conditions. Address workforce, guest, privileged, application, and legacy access scenarios, and use Conditional Access for workload identities where supported and applicable. |
| **Modernize authentication and legacy access** | Standardize on modern authentication. Identify and remediate dependencies on legacy authentication, then block or retire legacy protocols through a controlled, phased approach. Use authentication strengths to require appropriate methods for higher-risk users, resources, and actions. |
| **Transform application and hybrid identity infrastructure** | Modernize application authentication and single sign-on with Microsoft Entra. Inventory dependencies before migrating or retiring federation, web access management, directory, synchronization, connector, and other hybrid identity infrastructure. |
| **Modernize and govern groups** | Establish ownership, lifecycle, expiration, access reviews, and usage policies for cloud and on-premises groups. Move toward cloud-managed authorization and provisioning where appropriate while supporting required hybrid dependencies. |
| **Enforce least privilege and role-based access** | Define role models and assign access by job function using role-based access control, access packages, approval policies, and recurring access reviews. Continuously validate that access remains necessary. |
| **Protect privileged and workload identities** | Use separate privileged accounts, strong authentication, Privileged Identity Management, just-in-time controls, access reviews, and hardened administrative workstations. Create, protect, monitor, and regularly test cloud-only emergency access accounts. Protect service principals and managed identities with least privilege, strong credentials, monitoring, and Conditional Access for workload identities where supported. |
| **Establish identity data governance and provisioning flows** | Define authoritative identity data sources, attribute schemas, ownership, and data flows. Implement and monitor connectors and provisioning pipelines so identity information remains accurate and consistent across cloud and on-premises systems. |
| **Automate identity lifecycle and access provisioning** | Automate joiner, mover, and leaver processes, credential onboarding, application provisioning, entitlement assignment, reconciliation, and deprovisioning. Monitor workflows and address failed or inconsistent updates. |
| **Strengthen credential security and move toward passwordless authentication** | Develop a credential strategy that reduces password reliance and supports secure registration, recovery, and adoption. Prioritize phishing-resistant authentication methods, such as passkeys (FIDO2) and Windows Hello for Business, for sensitive scenarios, while using other passwordless and multifactor methods according to their capabilities and risk. |
| **Govern external and partner identities** | Standardize partner onboarding, connected organizations, sponsorship, access packages, Conditional Access, access reviews, monitoring, and timely removal of external access. |
| **Remediate existing access and identity debt** | Identify stale identities, unused groups, excessive permissions, unmanaged guests, and unsupported access paths. Prioritize remediation, verify ownership, and establish recurring governance to prevent reaccumulation. |
| **Enable identity security monitoring and response** | Integrate Microsoft Entra and Microsoft Defender for Identity signals, logs, health alerts, and incidents with security operations and SIEM workflows. Monitor hybrid identity infrastructure, investigate suspicious activity, tune detections, and maintain response playbooks. |

These areas summarize the Identity workshop pillar. Use the detailed Identity project guidance to review individual projects and implementation considerations.

## How to use the Identity Workshop

Use the web-based Workshop with identity, security, application, infrastructure, endpoint, HR, help desk, and security operations stakeholders. For each relevant project:

- Review the project objective and applicability to your environment.
- Record the current status, notes, decisions, owners, and known dependencies.
- Consider licensing, implementation effort, user impact, technical prerequisites, and cross-pillar dependencies.
- Prioritize the project into First, Then, or Next and incorporate it into the implementation roadmap.

[Open the Zero Trust Workshop](https://aka.ms/ztworkshop) and select the Identity pillar.

[Review the detailed Identity project guidance](https://microsoft.github.io/zerotrustassessment/docs/category/identity) for project-level information.

## Assess your identity posture

The Microsoft Zero Trust Assessment can provide programmatically generated findings for supported Microsoft Entra configuration and activity data. Assessment results can help identify technical gaps and inform Workshop discussions, but the Assessment is complementary and is not required to conduct the Identity Workshop. It does not evaluate every Identity Workshop project.

[Learn about the Zero Trust Assessment](/en-us/security/zero-trust/assessment/overview) or [get started with an assessment](/en-us/security/zero-trust/assessment/get-started).

## Who should participate?

- Identity, access, and identity-governance teams.
- Security architecture, security operations, and incident response teams.
- Application, cloud, infrastructure, endpoint, and network teams.
- HR, compliance, risk, help desk, resource owners, and business stakeholders.