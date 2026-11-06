---
layout: Conceptual
title: Microsoft Zero Trust Workshop - Networking | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/workshop-zero-trust-networking
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn about the Networking pillar in the Microsoft Zero Trust Workshop
ms.date: 2026-11-06T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: bd7ea033-1178-7ede-81b2-455b7e5dd7ed
document_version_independent_id: bd7ea033-1178-7ede-81b2-455b7e5dd7ed
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/workshop-zero-trust-networking.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/workshop-zero-trust-networking
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/workshop-zero-trust-networking.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: 06a75e37-71e0-0f0b-13d5-b4c5586b290c
---

# Microsoft Zero Trust Workshop - Networking | Microsoft Learn

In a Zero Trust architecture, the network is no longer treated as a trusted boundary. Instead, it becomes a transport layer where every connection must be explicitly verified, authorized, and continuously monitored. The Network pillar focuses on securing access to applications and resources by enforcing identity- and context-aware controls, segmenting connectivity, and minimizing the ability for attackers to move laterally.

Network pillar guidance focuses on moving access control away from the perimeter and closer to applications and resources. It emphasizes verifying every connection using identity and device signals, enforcing least-privilege access through segmentation, and assuming breach by limiting exposure and restricting lateral movement.

## Workshop implementation

The Network workshop covers the implementation areas summarized in the table.

| **Area** | **Details** |
| --- | --- |
| **Implement Zero Trust network access (ZTNA) for applications** | Replace implicit trust in the corporate network with identity and context-based access decisions. Connect users directly to applications using identity-aware access controls, and continuously evaluate sessions based on identity, device posture, risk signals, and location. |
| **Enable secure private access to internal applications** | Provide access to internal and private applications without exposing them to the public internet. Use application proxies and identity-aware gateways to eliminate broad network-level access and reduce attack surface. |
| **Secure outbound internet access** | Use a secure web gateway (SWG) or similar cloud-delivered controls to inspect, filter, and control outbound traffic. Apply policies based on user identity, device state, and risk to prevent access to malicious or inappropriate destinations. |
| **Protect internet-facing applications and endpoints** | Reduce exposure of public-facing applications and services by applying layered protections against volumetric, protocol, and application-layer attacks. Use traffic filtering, request inspection, rate controls, and automated mitigation to improve resilience and availability. |
| **Segment networks and application access** | Implement segmentation and micro-segmentation across on-premises and cloud environments to limit connectivity between users, devices, and applications. Restrict lateral movement by granting access only to explicitly authorized resources. |
| **Encrypt and protect all network traffic** | Ensure that all traffic—internal, external, and east-west—is encrypted in transit. Use secure protocols and identity-aware gateways to maintain confidentiality and integrity of communications. |
| **Move enforcement closer to applications and data** | Shift enforcement from traditional perimeter controls to application-level and identity-aware controls. Use reverse proxies, application gateways, and session-based controls to enforce policy at the point of access. |
| **Improve network visibility and continuous monitoring** | Gain visibility into network traffic, application access patterns, and user activity. Continuously monitor sessions and analyze logs from network controls, gateways, and segmentation boundaries to detect anomalies and support investigation. |
| **Integrate network signals into security operations (SecOps)** | Feed network telemetry, access events, and traffic analytics into centralized monitoring and response systems. Correlate network activity with identity, device, data, and infrastructure signals to detect threats, investigate incidents, and respond to suspicious behavior. |

## Assess networking posture

The Zero Trust Assessment tool can assess your networking configuration against a range of security best practices. [Learn more](/en-us/security/zero-trust/assessment/overview).