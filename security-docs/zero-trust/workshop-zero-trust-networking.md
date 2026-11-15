---
layout: Conceptual
title: Microsoft Zero Trust Workshop - Networking | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/workshop-zero-trust-networking
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Learn about the Networking pillar in the Microsoft Zero Trust Workshop
ms.date: 2026-11-12T00:00:00.0000000Z
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

In a Zero Trust architecture, the network is not treated as a trusted boundary. It becomes a transport layer where each connection to an application or resource is explicitly verified, authorized, protected, and continuously monitored using identity, device, risk, application, and network context.

The Networking workshop pillar helps organizations modernize private and internet access, reduce public exposure, segment connectivity, protect cloud and hybrid traffic, and integrate network signals into security operations. The Workshop turns these capabilities into a prioritized implementation roadmap across users, applications, branch locations, datacenters, cloud networks, and internet-facing services.

The Networking workshop pillar corresponds to the Network technology defined in the [Microsoft Security Adoption Framework (SAF)](deploy/overview).

## Why focus on networking?

Traditional perimeter controls and broad network access can create excessive trust and allow attackers to move laterally after an initial compromise. Networking controls should minimize implicit trust, enforce least-privilege connectivity close to applications and resources, protect traffic in transit, and provide the telemetry needed to detect and contain suspicious activity.

The expected output is an actionable backlog of Networking projects prioritized into First, Then, and Next based on organizational risk, dependencies, implementation effort, user impact, licensing, and readiness.

## Networking implementation areas

| **Area** | **Details** |
| --- | --- |
| **Establish networking strategy and governance** | Inventory network environments, application access paths, public endpoints, remote and branch connectivity, security controls, and accountable owners. Define target architecture, policies, standards, exception processes, metrics, and an implementation roadmap. |
| **Implement Zero Trust Network Access for private applications** | Replace broad network-level access with per-application, identity-aware access. Use Microsoft Entra Private Access, Application Proxy, or appropriate alternatives to publish private applications, apply Conditional Access, support private DNS, and progressively reduce VPN dependency. |
| **Modernize remote and branch connectivity** | Onboard managed endpoints and remote networks to cloud-delivered access controls, evaluate SD-WAN integration, define traffic steering and resiliency, and monitor connector, client, and remote-network health. |
| **Secure internet and SaaS access** | Use secure web gateway capabilities such as Microsoft Entra Internet Access to inspect and control outbound access. Apply identity-, device-, location-, and risk-aware policies, URL and content filtering, threat-intelligence protections, and appropriate controls for agentless networks. |
| **Protect Microsoft 365 and cross-tenant access** | Use compliant-network signals, tenant restrictions, Conditional Access integration, and guest or partner controls to reduce data exfiltration and unauthorized tenant access while supporting approved collaboration. |
| **Segment networks and application access** | Define segmentation requirements based on business sensitivity, identity, application, workload, and environment. Apply macro- and micro-segmentation across cloud, on-premises, and hybrid networks to restrict lateral movement and allow only explicitly authorized connectivity. |
| **Control inbound, outbound, and east-west traffic** | Evaluate network flows and use centralized or distributed firewalls and application-aware rules to explicitly allow required traffic. Route and inspect traffic consistently, govern policy changes, and automate compliance where practical. |
| **Protect internet-facing applications and public endpoints** | Discover public exposure and apply layered protections with Azure DDoS Protection, Azure Web Application Firewall, Azure Front Door, Azure Application Gateway, rate limiting, bot protections, and current managed rulesets. |
| **Implement network threat protection** | Use threat-intelligence filtering, intrusion detection and prevention, application-layer controls, and automated response to detect and block malicious inbound, outbound, and east-west activity. |
| **Encrypt and inspect network traffic** | Require secure protocols and encryption in transit. Assess encrypted traffic, certificate and privacy requirements, exclusions, performance, and legal considerations before using TLS inspection for appropriate outbound, inbound, or east-west scenarios. |
| **Move policy enforcement closer to applications and data** | Use identity-aware proxies, application gateways, session controls, application segmentation, and resource-level policy to enforce decisions at the point of access rather than relying solely on network location. |
| **Improve network visibility and operational monitoring** | Enable traffic, audit, health, firewall, DDoS, and web application firewall logging and metrics. Use Azure Monitor workbooks and other dashboards to track coverage, health, policy effectiveness, capacity, and anomalies. |
| **Integrate network signals into security operations** | Export relevant telemetry to Microsoft Sentinel or another SIEM, correlate it with identity, device, data, application, and infrastructure signals, establish investigation and response playbooks, and automate high-confidence containment actions. |
| **Protect emerging AI and agent traffic** | Apply secure web, application, and cloud firewall controls to generative AI applications and agents where supported. Review AI-related traffic and insights, protect prompts and endpoints, and monitor emerging protocols and agent communication such as MCP traffic. |

These areas summarize the Networking workshop pillar. Use the detailed Networking project guidance to review individual projects, dependencies, licensing considerations, and implementation guidance.

## How to use the Networking Workshop

Use the web-based Workshop with networking, identity, endpoint, application, cloud, infrastructure, data protection, and security operations stakeholders. For each relevant project:

- Review the project objective and applicability to your environment.
- Record the current status, notes, decisions, owners, and known dependencies.
- Consider licensing, implementation effort, user impact, technical prerequisites, resiliency, coverage, and cross-pillar dependencies.
- Prioritize the project into First, Then, or Next and incorporate it into the implementation roadmap.

[Open the Zero Trust Workshop](https://aka.ms/ztworkshop) and select the Network pillar.

[Review the detailed Networking project guidance](https://microsoft.github.io/zerotrustassessment/docs/category/network) for project-level information.

## Assess your networking posture

The Microsoft Zero Trust Assessment complements the Workshop by evaluating supported networking configurations against security best practices. Use its findings as an additional input when validating the current state and prioritizing Networking projects. Assessment results do not replace the stakeholder review, dependency analysis, and roadmap decisions completed in the Workshop.

[Learn about the Zero Trust Assessment](/en-us/security/zero-trust/assessment/overview).

## Who should participate?

- Network architecture, network engineering, telecommunications, and connectivity teams.
- Identity, endpoint management, application, cloud platform, infrastructure, and enterprise architecture teams.
- Security architecture, cloud security, application security, security operations, and incident response teams.
- Business application owners, data protection, governance, risk, compliance, privacy, and service-management stakeholders.