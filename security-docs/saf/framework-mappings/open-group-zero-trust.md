---
layout: Conceptual
title: Map The Open Group Zero Trust model to SAF | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/saf/framework-mappings/open-group-zero-trust
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Map The Open Group Zero Trust capabilities, security roles, and Architecture Building Blocks to Microsoft Security Adoption Framework work and Microsoft technology examples.
ms.date: 2026-11-09T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 04110cd3-5038-a9a1-d0d6-4acc53d95042
document_version_independent_id: 04110cd3-5038-a9a1-d0d6-4acc53d95042
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/saf/framework-mappings/open-group-zero-trust.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../../zero-trust/toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: saf/framework-mappings/open-group-zero-trust
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/saf/framework-mappings/open-group-zero-trust.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: 2c6216ab-8f80-9e99-35ef-a69f40a236ad
---

# Map The Open Group Zero Trust model to SAF | Microsoft Learn

The Open Group Security Forum develops security and Zero Trust guidance that describes security capabilities, architecture principles, roles, and Architecture Building Blocks (ABBs). These provide a useful external reference model for connecting business and security outcomes to architecture, security work, and technology.

The Microsoft Security Adoption Framework (SAF) connects this material to SAF business scenarios, security disciplines, technologies, and roles, and then to Microsoft architecture and implementation guidance.

Important

The Open Group remains the authoritative source for its standards and reference models. Some Zero Trust material is published as standards, while other material is available as evolving Snapshots. The guidance on this page is Microsoft-authored and doesn't change or extend The Open Group publications.

## Map Zero Trust capabilities to SAF

The Open Group Zero Trust model describes capabilities that combine people, processes, and technology to achieve security outcomes across governance, asset management, prevention, detection, response, recovery, and continuous improvement.

[![The Open Group Zero Trust capabilities mapped across the NIST Cybersecurity Framework functions Govern, Identify, Protect, Detect, Respond, and Recover.](media/open-group-zero-trust-capabilities-nist.png)](media/open-group-zero-trust-capabilities-nist.png#lightbox)

The capability model provides a useful bridge to SAF because both models organize security around durable outcomes and security work rather than individual products.

[![Detailed view of The Open Group Zero Trust capabilities for asset-centric security.](media/open-group-zero-trust-capabilities.png)](media/open-group-zero-trust-capabilities.png#lightbox)

The following mapping identifies the primary SAF discipline for each capability.

| The Open Group capability | Primary SAF disciplines | Typical role actions |
| --- | --- | --- |
| **Integrated Defense and Risk Management** | Strategy, Integration, and Governance; Security Architecture; Security Posture Management; SecOps/SOC | Accountable business leaders set risk appetite and priorities with security leadership. Security and technology leaders and practitioners translate that direction into security strategy and execution, coordinate work across disciplines, and measure results. |
| **Security Strategy, Integration, and Governance (SIG)** | Strategy, Integration, and Governance; Security Architecture | The CISO leads security strategy and governance with Security Directors and Security Business Architects/Analysts. They coordinate with technology executives, business and product leaders, risk and compliance stakeholders, and other accountable decision-makers to align security priorities with business objectives and risk, establish direction, and translate it into policy, roadmaps, architecture, measures, and oversight. |
| **Secure Asset Management** | Security Architecture; Security Posture Management | Product Owners and Business Architects/Analysts identify business operations, assets, criticality, and owners. Technical roles maintain lifecycle state. Architects define protection patterns. Security Posture Management measures exposure and control coverage. |
| **Security Posture Management** | Security Posture Management | Security Posture Management identifies exposures and attack paths, prioritizes improvement, and verifies remediation. Product and technology owners implement or authorize treatment. |
| **Asset-Centric Security Operations** | SecOps/SOC | SecOps Platform and Data Engineers provide data and platforms. Detection Engineers and Threat Intelligence improve coverage. Triage, Investigation, Threat Hunting, Forensics, Reverse Engineering, Incident Coordination, and technical owners detect, respond, and recover. |
| **Identity and Adaptive Access Management** | Access and Identity | Access Architects define policy and enforcement patterns. Identity, Network, User Endpoint, Application, and Platform roles implement them. Product Owners authorize business access. Security Posture Management and SecOps/SOC monitor effectiveness and abuse. |
| **Data Security** | Data Security; Access and Identity | Data Officer/Data Governance and Product Owners define value and obligations. Data and Access Architects design controls. Data, Identity, Application, and Platform roles implement them. |
| **Security Zones** | Security Architecture; Infrastructure Security; Access and Identity | Security, Access, and Infrastructure Architects define boundaries and enforcement. Network, Infrastructure/Platform, Identity, and Security Engineers implement segmentation and monitor policy. |
| **Privileged Access and High Value Assets** | Access and Identity; Security Architecture | Business and product leaders identify high-value assets and accountable owners. Access and Security Architects define privileged pathways. Identity, Endpoint, Network, and Platform roles implement them. SecOps/SOC monitors attack paths and activity. |
| **Software and DevSecOps** | Development Security; Security Architecture | Software/Application Architects, Software Security Engineers, Developers, Software Testers, Software Testing/Quality Managers, and DevOps Leads build and operate secure development and delivery practices. |

## Map security roles to SAF

The Open Group Security Roles and Glossary provides a common vocabulary for describing security work and distinguishes accountability for security outcomes from responsibility for performing security work.

SAF uses this role model to connect security outcomes and disciplines to the people who make decisions and perform the work. Organizations can combine responsibilities across people, teams, service providers, automation, and agents while preserving appropriate accountability and decision authority.

[![Current security accountability and responsibility role groups across an organization, including leadership, business, architecture, development, engineering and operations, governance, and SecOps roles.](media/open-group-security-roles.png)](media/open-group-security-roles.png#lightbox)

For the SAF role model and guidance, see [Security roles and responsibilities in SAF](/en-us/security/zero-trust/security-adoption-roles).

## Map Architecture Building Blocks to Microsoft technologies

The Open Group Zero Trust Reference Model uses Architecture Building Blocks (ABBs) to describe process and technology capabilities used to implement Zero Trust.

The following mappings connect selected ABBs to Microsoft technologies that can provide corresponding capabilities. These are Microsoft-authored implementation examples, not part of The Open Group model.

### Asset-Centric Security Operations Platform (ACSOP)

[![Microsoft technology mapping to Asset-Centric Security Operations Platform Architecture Building Blocks ACSOP-1.3 through ACSOP-1.3.10.](media/open-group-acsop-abb-microsoft.png)](media/open-group-acsop-abb-microsoft.png#lightbox)

| ABB number | Architecture Building Block | Level | Microsoft technology examples |
| --- | --- | --- | --- |
| **ACSOP-1.3** | SecOps Data Analysis and Automation Platform | 2 | All Level 3 ABBs below |
| **ACSOP-1.3.1** | Case Management Platform | 3 | Microsoft Defender XDR; Microsoft Sentinel |
| **ACSOP-1.3.2** | SecOps Business Intelligence (BI) Platform | 3 | Microsoft Power BI |
| **ACSOP-1.3.3** | Extended Detection and Response (XDR) | 3 | Microsoft Defender XDR; Microsoft Agent 365; Microsoft Defender for Cloud |
| **ACSOP-1.3.4** | Security Information and Event Management (SIEM) | 3 | Microsoft Sentinel |
| **ACSOP-1.3.5** | Security Data Lake | 3 | Microsoft Sentinel data lake |
| **ACSOP-1.3.6** | SecOps Automation Platform (SOAR) | 3 | Microsoft Defender XDR (AutoIR); Microsoft Sentinel |
| **ACSOP-1.3.7** | Technical Anomaly Platform (machine learning, reverse engineering, and related analytics) | 3 | Microsoft Defender; Microsoft Defender for Cloud |
| **ACSOP-1.3.8** | Behavior Anomaly Platform (UEBA) | 3 | Microsoft Defender; Microsoft Sentinel |
| **ACSOP-1.3.9** | Threat Intelligence Platform (TIP) | 3 | Microsoft Defender Threat Intelligence; Microsoft Security Copilot |
| **ACSOP-1.3.10** | SecOps AI and Agent Platform | 3 | Microsoft Security Copilot; Project Perception (preview) |

The Microsoft Security Architecture Design Session for SecOps/SOC also includes guidance related to ACSOP-1.1 SecOps Core Reactive Processes and ACSOP-1.2 SecOps Proactive Processes ABBs.

### Identity and Adaptive Access Management Platform (IAAMP)

[![Microsoft technology mapping to Identity and Adaptive Access Management Platform Architecture Building Blocks IAAMP-1.2 through IAAMP-1.3.7.](media/open-group-iaamp-abb-microsoft.png)](media/open-group-iaamp-abb-microsoft.png#lightbox)

| ABB number | Architecture Building Block | Level | Microsoft technology examples |
| --- | --- | --- | --- |
| **IAAMP-1.2** | Adaptive Access Control Platform | 2 | Microsoft Entra |
| **IAAMP-1.2.1** | Adaptive Policy Information Point (PIP) | 3 | Microsoft Entra ID Protection; Microsoft Defender XDR; Microsoft Intune; Microsoft Purview |
| **IAAMP-1.2.2** | Adaptive Policy Decision Point (PDP) | 3 | Microsoft Entra Conditional Access |
| **IAAMP-1.2.3** | Adaptive Policy Enforcement Point (PEP) | 3 | Microsoft Entra Conditional Access; Microsoft Entra Private Access and Internet Access; Microsoft Intune; Microsoft Purview Information Protection and Data Loss Prevention |
| **IAAMP-1.2.4** | Adaptive Policy Manager | 3 | Microsoft Entra Conditional Access |
| **IAAMP-1.2.5** | Policy Signal Source | 3 | Microsoft Entra ID and Microsoft Entra ID Protection; Microsoft Intune; Microsoft Defender XDR |
| **IAAMP-1.3** | Identity, Key, and Access Management Platform | 2 | Microsoft Entra |
| **IAAMP-1.3.1** | Identity Provider (IDP) | 3 | Microsoft Entra ID; Active Directory |
| **IAAMP-1.3.2** | Identity Lifecycle Management Platform | 3 | Microsoft Entra ID Governance; Microsoft Agent 365 |
| **IAAMP-1.3.3** | Application Consent Management Platform | 3 | Microsoft Entra ID |
| **IAAMP-1.3.4** | Personal Data Consent Management Platform | 3 | Microsoft Priva Consent Management |
| **IAAMP-1.3.5** | Certificate and Key Management Platform | 3 | Azure Key Vault; Active Directory Certificate Services; Microsoft Identity Manager Certificate Manager |
| **IAAMP-1.3.6** | Authenticated Network Access Control Platform | 3 | Microsoft Entra Private Access and Internet Access; Azure VPN |
| **IAAMP-1.3.7** | Workload and Agent Authorization Mechanisms | 3 | Microsoft Azure; Microsoft 365; Microsoft Dynamics 365; Microsoft Entra Agent ID; custom workload and agent RBAC, ABAC, and permission models |

Use these mappings to connect The Open Group architecture to SAF security work and then to applicable Microsoft architecture, technical solutions, and product guidance. Because the Zero Trust Reference Model is currently published as a Snapshot, review these mappings as The Open Group publishes updated material.