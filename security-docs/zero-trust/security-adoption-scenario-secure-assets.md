---
layout: Conceptual
title: Identify and protect critical business assets | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-scenario-secure-assets
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Use the Microsoft security adoption model to secure critical assets based on Zero Trust principles and security best practices.
ms.date: 2026-05-24T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: f9342012-890d-c4cd-7167-42bdd94f2f29
document_version_independent_id: f9342012-890d-c4cd-7167-42bdd94f2f29
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-adoption-scenario-secure-assets.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-adoption-scenario-secure-assets
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-adoption-scenario-secure-assets.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
platformId: cc4fb7ee-b68a-bfbe-01ff-f195fa5c4b45
---

# Identify and protect critical business assets | Microsoft Learn

This article explains how to identify and protect critical business assets using Zero Trust principles, as part of the [Microsoft security adoption model](security-adoption-model).

This business scenario helps you achieve the following outcome:

**Identify and protect critical business assets**

As a business leader, you must ensure that the systems, data, and operations that drive your organization are protected against targeted and high-impact threats. Not all assets carry equal importance—some represent concentrated risk and require stronger, more focused protection.

A key outcome of protecting critical business assets is securing the privileged access that controls them. Privileged identities and access pathways represent concentrated risk because they provide administrative control over critical systems and data. If compromised, they can enable widespread impact across the organization.

This scenario focuses on ensuring that critical assets are protected and that access to those assets is tightly governed and consistently controlled, so that only trusted and authorized access is allowed.

This enables your organization to reduce the risk of high-impact attacks, protecting business operations, revenue, and reputation from disruption or compromise.

## How this guidance works

This article is part of a [structured adoption model](security-adoption-model) that connects security strategy to implementation:

- Start with a [business scenarios](security-adoption-business-scenarios-overview) like this one to define the outcome you want to achieve.
- Identity the [security disciplines](security-adoption-discipline-overview) that apply to this scenario.

    Use those disciplines to define the required strategy, architecture, processes, and controls for the scenario. Work through each discipline to understand what needs to be planned, designed, and implemented across the organization.
- Use [technical solutions](implement-overview) to implement those requirements using Microsoft technologies, applying controls across [technology pillars](deploy/overview) such as identity and data.

This approach ensures that security investments are focused on the assets that matter most to the business while access to those assets is consistently governed, reducing the risk of high-impact compromise and strengthening overall organizational resilience.

## Why critical asset protection requires a new approach

Organizations rely on the availability, integrity, and confidentiality of their business systems and data to run their business operations, accept customer revenue, fulfill their mission, and more. When threat actors (cybersecurity attackers) compromise the assurances of these system and data assets, organizations face direct costs as well as risks to life, safety, mission, revenue, reputation, market share, and more.

This diagram illustrates how these business critical assets must be secured at a level greater than others.

[![Diagram illustrating two categories of business critical assets: high-value assets with intrinsic business value, and privileged access accounts and systems that control those assets.](media/security-adoption-protect-critical.png)](media/security-adoption-protect-critical.png#lightbox)

Not all systems and data carry equal business impact. Business‑critical assets fall into two categories:

- **High value assets** - High‑value assets are systems and data whose compromise could cause severe financial or operational damage, up to and including bankruptcy or insolvency. These assets are often targeted for theft, extortion, or destruction.
- **Privileged access** - Privileged access represents concentrated risk—identities, accounts, and tools that control high‑value assets. Compromise of privileged access (via IT admin accounts, workstations, and other systems) enables widespread impact and must be protected at the same level or above the level of high‑value assets.

## Business value

The value of securing critical assets benefits the entire organization, but differs by role.

| **Roles** | **Value** |
| --- | --- |
| **Business leadership** | Protect the most valuable organizational assets that drive revenue, mission success, and competitive advantage.Minimize business impact from attacks targeting high-value systems and data. Ensure privileged access is secured to prevent unauthorized control of critical assets. |
| **Technology roles** | Focus security investments on the assets that matter most to the business. Reduce the blast radius of breaches by securing privileged access pathways. Implement standardized protections for identified critical assets across the technical estate. |
| **Security roles** | Prioritize security efforts based on business impact rather than technical complexity. Establish clear visibility into critical assets and privileged access pathways. Implement defense-in-depth controls for high-value targets most likely to be attacked. |

## Align security disciplines

Security disciplines represent the structured areas of accountability required to deliver this business scenario.

- Planning and oversight disciplines define the strategy, governance, and cross‑organization coordination required.
- Technical strategy disciplines define the architectural, operational, and control capabilities required.
- Operational disciplines ensure that security controls remain effective over time through monitoring, response, and continuous improvement. They detect misuse, respond to threats, and drive ongoing security posture improvements.

### Planning and oversight disciplines

| **Discipline** | **Action** |
| --- | --- |
| **[Strategy, integration, and governance](security-adoption-discipline-strategy)** | Establish clear strategy, governance, policy, and processes to guide teams on identifying and prioritizing business critical assets and privileged access.Drive a continuous learning approach to continuously improve your ability to identify, protect, detect, respond, recover, and govern business critical assets and privileged access. Ensure governance drives and monitors cross-team processes to ensure a coordinated approach across security, technology, and business teams. |
| **[End-to-end security architecture](security-adoption-discipline-architecture)** | Ensure that security architectures explicitly require, include, and prioritize security of privileged access and high value business critical assets. Ensure technical controls and capabilities are sufficient to mitigate risk across the full security lifecycle (identify, protect, detect, respond, recover, and govern). Drive an integrated approach across technology teams to prioritize business critical assets and rapidly apply learnings to keep up with attacker evolution. |

### Technical strategy disciplines

| **Discipline** | **Action** |
| --- | --- |
| **[Access and identities](security-adoption-discipline-identity-access)** | Implement privileged access management with just-in-time and just-enough-access principles. Secure administrative accounts with phishing-resistant credentials and enhanced monitoring Ensure critical systems require strong authentication and enforce least-privilege access.  Establish clear visibility into who has privileged access to critical assets. |
| [**Infrastructure security**](security-adoption-discipline-infrastructure) | Harden and closely monitor infrastructure hosting critical business applications and data. Implement network segmentation to isolate high-value assets. Deploy enhanced logging and anomaly detection for privileged access to critical infrastructure.  Establish secure baselines and configuration management for critical systems. |
| [**Development security**](security-adoption-discipline-development) | Prioritize security testing and threat modeling for applications that process or access critical business data. Implement secure development practices and supply chain security for business-critical applications. Establish application-level controls to protect sensitive data and prevent unauthorized access. |
| [**Data security**](security-adoption-discipline-data) | Classify and label critical business data to enable appropriate protection controls.Implement data loss prevention, encryption, and access controls aligned with data criticality. 3. Monitor for unusual data access patterns and potential exfiltration of high-value information. |
| [**OT and IoT security**](security-adoption-discipline-iot) | Identify IoT and OT systems that are business critical or can impact physical safety. Implement network segmentation and enhanced monitoring for these systems. Secure privileged access to operational technology management platforms. |

### Operational disciplines

| **Discipline** | **Action** |
| --- | --- |
| [**SecOps**](security-adoption-discipline-security-operations) | Prioritize monitoring and response for critical assets and privileged access. Implement enhanced threat hunting and detection for attacks targeting high-value systems. Establish accelerated incident response procedures for breaches involving critical assets. Use threat intelligence to anticipate attacks on valuable targets. |
| [**Security posture management**](security-adoption-discipline-posture) | Continuously assess security posture of critical assets and privileged access pathways. Prioritize vulnerability remediation based on asset criticality and business impact. Monitor compliance with security baselines for high-value systems. Track and report on the security status of business-critical assets to leadership. |

## Required technology pillars

Technology pillars represent the core Microsoft security capabilities that support this business scenario.

| **Pillar** | **Purview** | **Entra** |
| --- | --- | --- |
| **Identity** | Microsoft Purview integrates with Conditional Access to enforce identity-based access controls on sensitive data through sensitivity labels and data loss prevention policies. | Microsoft Entra provides Conditional Access, and identity governance to ensure that only authorized users and services can access sensitive data. |
| **Endpoints** | Microsoft Purview Endpoint DLP extends data protection policies to endpoints, preventing unauthorized data transfers and ensuring sensitive information stays protected on devices. | Microsoft Entra Enforces device-based access controls, ensuring only compliant and trusted devices can access protected data. |
| **Networks** | Microsoft Purview monitors data movement across network boundaries and integrates with network security tools to detect and prevent data exfiltration. | Microsoft Entra applies location and network-based access conditions through Conditional Access policies. |
| **Apps** | Microsoft Purview applies sensitivity labels and DLP policies across Microsoft 365 apps, SaaS applications, and on-premises file shares to ensure consistent data protection. | Microsoft Entra controls access to applications using single sign-on (SSO), application registration, and access policies. |
| **Data** | Microsoft Purview provides the core data security capabilities including sensitivity labeling, data classification, data loss prevention, information barriers, and records management. | Microsoft Entra enforces access decisions using RBAC, Privileged Identity Management (PIM), and just-in-time access for sensitive operations. |
| **Infrastructure** | Microsoft Purview extends data governance and protection to cloud infrastructure through integration with Azure services, multicloud environments, and on-premises data stores. | Microsoft Entra governs administrative access to cloud resources through role assignments, access reviews, and privileged role protections. |
| **AI** | Microsoft Purview provides AI security and governance capabilities including AI Hub for visibility into AI usage, sensitivity labels for AI-generated content, and compliance controls for Copilot and other AI services. | Microsoft Entra secures access to AI services by enforcing identity verification, access policies, and governance over who can access and configure AI workloads. |