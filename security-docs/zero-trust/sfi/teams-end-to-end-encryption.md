---
layout: Conceptual
title: 'Secure your data with Microsoft Teams Encryption: Enforce layered encryption with selective end-to-end encryption | Microsoft Learn'
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/teams-end-to-end-encryption
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: v-cjwoodling
author: cjwoodling6
description: Customers should adopt a default encryption model with policy-governed exceptions for E2EE, anchored in identity and compliance controls.
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
ms.date: 2026-09-25T00:00:00.0000000Z
ms.custom: msecd-doc-authoring-1028
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
ai-usage: ai-generated
locale: en-us
document_id: c36985cc-2e20-641c-a3dc-7a3daba81873
document_version_independent_id: c36985cc-2e20-641c-a3dc-7a3daba81873
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/teams-end-to-end-encryption.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/teams-end-to-end-encryption
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/teams-end-to-end-encryption.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: be21cacd-fea1-8bcd-947f-da4c07b8031d
---

# Secure your data with Microsoft Teams Encryption: Enforce layered encryption with selective end-to-end encryption | Microsoft Learn

**Pillar name: Protect networks**

**Pattern name: Apply Layered Encryption for Sensitive Collaboration**

Modern collaboration platforms like Microsoft Teams are central to enterprise productivity, handling sensitive communications across chats, calls, meetings, and shared content. While encryption is broadly implemented, inconsistent application and ungoverned use of end-to-end encryption (E2EE) introduces governance gaps, reduces visibility for security controls, and limits compliance capabilities.

This pattern outlines how Microsoft applies a layered encryption model that balances strong data protection with operational visibility, enabling organizations to secure collaboration workloads by default while selectively isolating high-sensitivity scenarios.

## Context and problem

Enterprise collaboration platforms handle sensitive communications across chats, calls, meetings, and shared content. Teams applies standard encryption by default, but external or legacy communication segments require separate assessment. In particular, overuse of end-to-end encryption (E2EE) can reduce visibility, break compliance controls, and introduce governance gaps.

Challenges for using encryption on these platforms include:

- Attackers exploiting weak or legacy communication paths (for example, public switched telephone networks (PSTN) or short message service (SMS) without encryption)
- End-to-end encryption limits service-side inspection of protected audio, video, and video-based screen sharing in supported calls and meetings. E2EE doesn't cover chat messages or shared files.
- Lack of centralized policy leading to inconsistent encryption usage across workloads
- Lack of monitoring of E2EE usage, policy exceptions, and configuration changes can create governance blind spots and hinder compliance oversight.

These encryption challenges create security gaps in these widely-used collaboration platforms that can affect extensive parts of critical business systems.

## Solution

Microsoft uses a layered encryption model that defaults to service-managed encryption and enables selective use of E2EE for high-sensitivity scenarios only. This model protects data within supported Teams services, but it doesn't extend Teams encryption guarantees to external or legacy communication segments. This model works by:

- Encrypting data in transit by using Transport Layer Security (TLS) and Secure Real-Time Transport Protocol (SRTP) across client and service communications
- Encrypting data at rest by using Microsoft-managed encryption controls for stored messages, files, recordings, and related collaboration data
- Enforcing encryption by default for all Teams workloads, including chat, meetings, and calls
- Centralizing identity enforcement by using Microsoft Entra ID with MFA and Conditional Access
- Restricting privileged access through Microsoft service-operation controls, including Zero Standing Access and just-in-time privileged access, to limit persistent administrative permissions
- Retaining service-side decryption for indexing, DLP, electronic evidence discovery (eDiscovery), and monitoring capabilities
- Enabling E2EE only for approved, supported calls and meetings that require strict confidentiality with no service-side processing of protected media
- Governing E2EE usage through tenant policies and role-based controls
- Extending encryption ownership through Customer Key for customer-managed encryption at rest

E2EE is available for eligible one-to-one VoIP calls and supported meetings configured to require it, but not for PSTN calls. For supported communication types and feature limitations, see [Encryption in Microsoft Teams](/en-us/microsoftteams/teams-encryption).

## Guidance

Adopt a default encryption model with policy-governed exceptions for E2EE, anchored in identity and compliance controls.

| **Use case** | **Recommended action** | **Resource** |
| --- | --- | --- |
| Standard enterprise collaboration | Enforce default encryption Retain service-side processing Enable audit and monitoring | [Microsoft Teams Security Guide](/en-us/microsoftteams/teams-security-guide) |
| High-sensitivity meetings or calls | Enable E2EE selectively Restrict to approved users Validate feature limitations | [Require end-to-end encryption for Teams meetings](/en-us/microsoftteams/end-to-end-encrypted-meetings) |
| Identity and access protection | Enforce MFA Apply Conditional Access Require compliant devices | [Zero Trust deployment with Microsoft 365](../microsoft-365-zero-trust)[Plan a Microsoft Entra ID protection deployment](/en-us/entra/id-protection/how-to-deploy-identity-protection) |
| Data protection and compliance | Enable DLP and retention Apply sensitivity labels Govern collaboration workspaces | [Protect data with Microsoft Purview](/en-us/purview/zero-trust-purview-protect-data) |
| Encryption key ownership | Deploy Customer Key Manage encryption keys Validate regulatory requirements | [Protect secrets best practices](/en-us/azure/security/fundamentals/secrets-best-practices) |
| E2EE policy configuration | Define policies in Teams admin center Control who can enable E2EE Validate client support | [End-to-end encryption for Teams](/en-us/microsoftteams/teams-end-to-end-encryption) |

## Outcomes

### Benefits

- Protects Teams data in transit and at rest by default within supported services.
- Maintains visibility for compliance, monitoring, and threat detection through service-managed encryption.
- Enables secure handling of highly sensitive scenarios through controlled E2EE usage.
- Reduces risk of unauthorized access through strong identity enforcement and least privilege access.
- Aligns collaboration security with Zero Trust principles and regulatory requirements.

### Trade-offs

- E2EE makes recording, transcription, and related Microsoft 365 Copilot capabilities unavailable for protected calls and meetings. It prevents service-side inspection of protected media but doesn't extend to chat messages or shared files, and it doesn't disable their data loss prevention (DLP) policies.
- Not all clients and platforms support E2EE, limiting interoperability.
- Managing multiple encryption modes introduces operational complexity.
- User experience can degrade due to missing collaboration features in E2EE sessions.
- Governance requires coordination across security, compliance, and IT teams.

## Key success factors

Successful implementation depends on consistent governance, identity enforcement, and monitoring. Focus on these success factors:

- Organizational alignment on when collaboration workloads should use default encryption versus E2EE
- Coverage of MFA and Conditional Access across all users
- Percentage of collaboration data governed by DLP and retention policies
- Reduction in unmanaged or inappropriate end-to-end encryption (E2EE) usage through centralized policy enforcement
- Number of approved versus unapproved E2EE usage scenarios
- Frequency of encryption policy audits and updates

## Summary

Securing modern collaboration requires applying the right controls across identities, configurations, and communication pathways. A layered encryption approach that defaults to service-managed encryption and governs end-to-end encryption (E2EE) as an exception helps protect supported Teams communications. Standard encryption preserves service-side capabilities, while E2EE limits inspection of protected media. External and legacy communication segments require separate assessment and controls.

By integrating strong identity protection, enforcing centralized policies to reduce misconfigurations, and maintaining oversight of encrypted traffic, organizations can minimize risks from unauthorized access, phishing, and blind spots.