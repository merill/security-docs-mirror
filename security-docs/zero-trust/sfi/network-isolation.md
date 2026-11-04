---
layout: Conceptual
title: Network isolation | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/network-isolation
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Network isolation is part of the protect networks pillar of the Secure Future Initiative (SFI)and aligns with the Zero Trust principles of Verify Explicitly, Least Privilege, and Assume Breach to ensure that corporate and cloud networks are secured against unauthorized internal access and external intrusions.
ms.date: 2025-10-03T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
locale: en-us
document_id: a25b5ccc-9145-c6e4-631f-ccbbb572eeb8
document_version_independent_id: a25b5ccc-9145-c6e4-631f-ccbbb572eeb8
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/network-isolation.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/network-isolation
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/network-isolation.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/20ed8455-bc18-4537-87a4-83784e7b2a39
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/9a7f703b-30bb-4d62-9eb4-97213f571849
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
platformId: e94d49b0-9f53-eff8-20ca-2b301e147e44
---

# Network isolation | Microsoft Learn

**Pillar name: Protect networks** **Pattern name: Network isolation**

## Context and problem

Modern threat actors exploit weak network boundaries to move laterally and escalate privileges. Common attack paths include stolen credentials, protocol abuse, and token replay. Once inside, adversaries often exploit poor segmentation, overly permissive permissions, or shared infrastructure to access sensitive workloads. 

Traditional flat networks make it difficult to enforce *Least Privilege* access and often leave resources broadly reachable. Without clear isolation, both internal and external threats can quickly compromise multiple systems. The challenge is to standardize network segmentation, enforce perimeters, and ensure traffic flows are strictly controlled to prevent lateral movement and contain breaches.

## Solution

Network isolation secures networks by dividing and isolating networks into segments and controlling network access to them. It combines identity-aware network security solutions and improvements in visibility, monitoring and detection capabilities. Core practices include: 

- Network segmentation and software-defined perimeters: Assume Breach and limit lateral movement with network partitioning and dynamic, risk-based access. Enforce Least Privilege with scoped access and Verify Explicitly with identity-based access controls.
- SASE and ZTNA: Use Secure Access Service Edge (SASE) and Zero Trust Network Access (ZTNA) architectures to integrate security and networking. Align Zero Trust principles by granting and restricting access based on context, identity, and conditional access controls.
- Encryption and communication: Assume Breach by protecting data in transit and limiting data tampering risk with strong, modern encryption and communication, and blocking of weak protocols.
- Visibility and threat detection: *Assume Breach* with continuous visibility and monitoring, and logging of network activity. Enforce *Least Privilege* and *Verify Explicitly* with access controls and threat detection to find and surface anomalies. Enforce Zero Trust by automating deployment, management, and allocation of networking resources and controls at scale. Without automation, delays, inconsistencies and gaps can quickly arise.
- Policy-driven controls: *Verify Explicitly* and apply *Least Privilege* with granular, adaptive identity-centered, conditional access policy controls. Assume Breach with deny-by-default, and constantly reevaluating risk.
- Cloud and hybrid network security: *Assume Breach* and *Verify Explicitly* in multicloud and hybrid environments by isolating cloud workloads into protected micro-perimeters, and by using Identity-aware proxies and Cloud Security Access Broker (CASB) solutions for SaaS and PaaS apps. Apply Zero Trust principles with unified security policies across cloud and on-premises, secure hybrid connection mechanisms, improvement of cloud/hybrid security posture, and centralized security monitoring.

## Guidance

Organizations can adopt a similar pattern using the following actionable practices: 

| Use case | Recommended action | Resource |
| --- | --- | --- |
| Micro-segmentation | - Use network security groups (NSGs) and ACLs to enforce least overview privilege access between workloads. | [Azure network security groups overview](/en-us/azure/virtual-network/network-security-groups-overview) |
| Isolate virtual networks | - Use tools like Microsoft Defender Vulnerability Management to scan systems and prioritize CVEs | [Isolating VNets - Azure Virtual networks](/en-us/azure/virtual-wan/scenario-isolate-vnets) |
| Perimeter protection for PaaS resources | - Use Azure Network Security secure access to services like Storage, SQL, and Key Vault. | [What is a network security perimeter](/en-us/azure/private-link/network-security-perimeter-concepts) |
| Secure connectivity to virtual machines | - Use Azure Bastion to establish secure RDP/SSH connectivity to virtual machines without exposing resources to the internet. | [About Azure Bastion](/en-us/azure/bastion/bastion-overview) |
| Restrict outbound virtual access | - Remove default outbound internet access and apply least privilege Network for service egress. | [Default Outbound Access in Azure - Azure Virtual Network](/en-us/azure/virtual-network/ip-services/default-outbound-access) |
| Layered perimeter defense | - Apply firewalls, service tags, NSGs, and DDoS protection to enforce multi-layer security. | [Azure DDoS Protection Overview](/en-us/azure/ddos-protection/ddos-protection-overview) |
| Centralized policy management | - Use Azure Virtual Network Manager with security admin rules to centrally manage network isolation policies. | [Security admin rules in Azure Virtual Network Manager](/en-us/azure/virtual-network-manager/concept-security-admins) |

## Outcomes

### Benefits

- Resiliency: Limits the blast radius of an intrusion.
- Scalability: Standardized network isolation supports enterprise-scale environments.
- Visibility: Service tagging and monitoring provide clearer attribution of traffic flows.
- Regulatory alignment: Supports compliance with frameworks requiring strict segregation of sensitive resources.

### Trade-offs

- Operational overhead: Designing and maintaining segmented networks requires planning and ongoing updates.
- Complexity: More segmentation may introduce additional management layers and require automation to scale.
- Performance considerations: Some isolation measures may slightly increase latency.

## Key success factors

To track success, measure the following: 

- Number of workloads deployed in isolated virtual networks with no direct internet exposure.
- Percentage of services governed by centralized security admin rules.
- Reduction in lateral movement paths identified during red-team testing.
- Compliance with least privileged policies across environments.
- Time to detect and remediate anomalous network activity.

## Summary

Network isolation is a foundational strategy for preventing lateral movement and protecting sensitive workloads. By segmenting resources, enforcing perimeters, and applying layered defenses, organizations reduce their attack surface and build resilience against modern adversaries.

Isolating networks is no longer optional---it is a necessary control for safeguarding cloud and hybrid environments. The Network isolation objective provides a clear framework for reducing lateral movement, aligning with Zero Trust, and protecting enterprise-scale environments. 

Additionally, all network, identity, and device activity should be continuously monitored. Centralize logging and correlate security alerts using extended detection and response (XDR) solutions and SIEM tools to effectively detect anomalies and threats. Pair detection with behavioral analytics, deep packet inspection, and automated threat response to quickly contain suspicious activity, and support efficient incident response.

**Evaluate your current network topology and implement segmentation and perimeter controls to align with the network isolation objective.**