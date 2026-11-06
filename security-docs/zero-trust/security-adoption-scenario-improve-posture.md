---
layout: Conceptual
title: Strengthen security posture and compliance | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-scenario-improve-posture
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Use the Microsoft security adoption model to improve security posture based on Zero Trust principles and security best practices.
ms.date: 2026-11-06T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 161d942c-541e-a600-8def-966d6007eeb4
document_version_independent_id: 161d942c-541e-a600-8def-966d6007eeb4
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-adoption-scenario-improve-posture.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-adoption-scenario-improve-posture
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-adoption-scenario-improve-posture.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/439169bb-ca98-4939-bfdf-143f64c492d8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/27ece40b-27ae-490b-850a-e99fc3e2c052
platformId: 82702794-db25-bb0e-ab0f-cb28d2176ab3
---

# Strengthen security posture and compliance | Microsoft Learn

This article explains how to strengthen posture and compliance using Zero Trust principles, as part of the Microsoft [security adoption model]((security-adoption-model.md).

This business scenario helps you achieve the following outcome:

**Continuously improve security posture and compliance**

As a business leader, you must meet your fiduciary duty to protect against security risk. Protection must cover security incidents from evolving threats, and meet regulatory compliance requirements, often with the same limited resources.

This business scenario is part of our [structured adoption model](security-adoption-model) that helps you to achieve business goals using a modern security approach grounded in Zero Trust principles.

This guidance helps your organization improve security posture and maintain compliance by continuously identifying risk, prioritizing remediation, and strengthening protection across the organization.

## How this guidance works

This article is part of a [structured adoption model](security-adoption-model) that connects security strategy to implementation:

- Start with a [business scenario](security-adoption-business-scenarios-overview) like this one to define the outcome you want to achieve.
- Identity the [security disciplines](security-adoption-discipline-overview) that apply to this scenario.

    Use those disciplines to define the required strategy, architecture, processes, and controls for the scenario. Work through each discipline to understand what needs to be planned, designed, and implemented across the organization.
- Use [technical solutions](implement-overview) to implement those requirements using Microsoft technologies, applying controls across [technology pillars](deploy/overview) such as identity and data.

This approach ensures that security posture improvement and compliance are continuously maintained as part of your overall Zero Trust architecture, rather than as a separate effort.

## Why security posture requires a new approach

Organizations face two intersecting challenges: defending against increasingly sophisticated threats while meeting expanding regulatory and compliance obligations.

- **Security posture**: Your security posture represents your organization’s overall ability to prevent, detect, and respond to cyber threats. A strong security posture is measurable, quantifiable, and continuously improving as risks and technologies evolve.
- **Regulatory compliance**: Regulatory compliance requires adherement to laws, regulations, and industry standards such as GDPR, CCPA, HIPAA, and data residency requirements. Compliance isn't a one‑time effort—it requires sustained controls, evidence, and operational discipline.

You can meet both of these requirements with:

- A systematic approach to implementing security controls
- Built-in capabilities that often exceed compliance requirements
- Integrated tools that reduce complexity and operational costs
- Measurable progress tracking and reporting

## Business value

The value of continuously improving security posture and compliance benefits the entire organization, but is different for different roles.

| **Roles** | **Value** |
| --- | --- |
| **Business leadership** | Operate with integrated security that aligns to business outcomes without introducing unnecessary friction. Reduce recovery time after security incidents while meeting regulatory and legislative requirements. Limit financial, legal, and reputational impact from security and compliance failures. |
| **Technology roles** | Establish a standardized security posture with automated compliance, predictable costs, and reduced operational friction while meeting technology and security requirements. |
| **Security roles** | Gain improved visibility and control over organizational risk. Incrementally increase attack friction to reduce attacker return on investment (ROI) and limit blast radius and exposed attack surfaces. |

## Align security disciplines

Security disciplines represent the structured areas of accountability required to deliver this business scenario.

- Planning and oversight disciplines define the strategy, governance, and cross‑organization coordination required.
- Technical strategy disciplines define the architectural, operational, and control capabilities required.
- Operational disciplines ensure that security controls remain effective over time through monitoring, response, and continuous improvement. They detect misuse, respond to threats, and drive ongoing security posture improvements.

### Planning and oversight disciplines

| **Discipline** | **Action** |
| --- | --- |
| **[Strategy, integration, and governance](security-adoption-discipline-strategy)** | Establish governance processes that define security posture and compliance goals, priorities, and risk tolerance. Set measurable objectives and track progress toward security maturity. |
| **[End-to-end security architecture](security-adoption-discipline-architecture)** | Implement security controls and monitoring across the entire technology estate. Integrate these controls into a unified view for asset owners and managers, and design architectures that are secure by default while supporting compliance requirements. |

### Technical strategy disciplines

| **Discipline** | **Action** |
| --- | --- |
| **[Access and identities](security-adoption-discipline-identity-access)** | Ensure the organization has an intentional and sound approach to managing access to assets. Implement identity-based security controls that support Zero Trust principles and provide visibility into access patterns. |
| [**Infrastructure security**](security-adoption-discipline-infrastructure) | Consistently and effectively apply monitor and apply security controls across all infrastructure assets in the technical estate, including all clouds, on-premises datacenters, and legacy systems. Establish, monitor, and enforce secure baselines and configuration standards across common operating systems, devices, applications, and other components. |
| [**Development security**](security-adoption-discipline-development) | Consistently and effectively apply security controls across existing software and new development. Integrate and automate the inclusion of security controls into development processes. Establish processes to rapidly correct security flaws that are found anytime during the software lifecycle including after release. |
| [**Data security**](security-adoption-discipline-data) | Consistently and effectively apply security controls to ensure security and privacy assurances for data assets that store intellectual property, trade secrets, regulated data, and other sensitive data. Implement controls that meet regulatory requirements and protect against data loss. |
| [**OT and IoT security**](security-adoption-discipline-iot) | Ensure the organization has an intentional and sound approach for OT/IoT devices that interact with physical processes and the physical world. |

### Operational disciplines

| **Discipline** | **Action** |
| --- | --- |
| [**SecOps**](security-adoption-discipline-security-operations) | Prioritize monitoring and mitigation based on the most frequent and impactful security incidents, using threat intelligence from SecOps and external sources. Continuously improve detection and response capabilities. |
| [**Security posture management**](security-adoption-discipline-posture) | Continuously assess, measure, and improve security posture across the organization. Implement tools like [Microsoft Security Exposure Management](/en-us/security-exposure-management/microsoft-security-exposure-management) and Secure Score to track progress. Prioritize remediation based on risk and business impact. |

## Required technology pillars

Technology pillars represent the core Microsoft security capabilities that support this business scenario.

| **Pillar** | **Security Exposure Management** | **GitHub Advanced Security** | **Priva** |
| --- | --- | --- | --- |
| **Identity** | Microsoft Security Exposure Management identifies identity-related risks including overprivileged accounts, stale credentials, and attack paths that use identity misconfigurations. | GitHub Advanced Security detects hard‑coded credentials and API keys in source code to reduce identity‑based risk caused by credential exposure. Integration with repository access controls ensures only authorized users can modify sensitive code. | Microsoft Priva integrates with Microsoft Entra to track which identities access personal data and supports subject rights requests to help individuals exercise control over their personal information. |
| **Endpoints** | Microsoft Security Exposure Management aggregates endpoint vulnerabilities, misconfigurations, and exposure risks, providing a unified view of device security posture. | NA | Microsoft Priva monitors personal data handling on endpoints and helps identify privacy risks from data stored on user devices. |
| **Networks** | Microsoft Security Exposure Management maps network attack surfaces, identifies exposed services, and highlights network segmentation gaps that could enable lateral movement. | NA | Microsoft Priva helps identify when personal data moves across network boundaries and supports data transfer assessments for cross-border compliance. |
| **Apps** | Microsoft Security Exposure Management discovers application vulnerabilities, risky configurations, and shadow IT to help secure the application attack surface. | Code scanning (SAST) in GitHub Advanced Security identifies security vulnerabilities and coding errors before release, reducing the number of exploitable flaws in deployed applications. Security campaigns and Copilot Autofix help teams remediate issues at scale, supporting consistent application security standards. | Microsoft Priva discovers personal data across Microsoft 365 applications and provides visibility into how personal information is used within collaboration tools. |
| **Data** | Microsoft Security Exposure Management identifies data exposure risks including overshared files, sensitive data in vulnerable locations, and data-related attack paths. | Secret scanning detects exposed credentials, tokens, and connection strings in repositories, while push protection helps prevent new leaks before they're committed. This reduces the risk of data access via leaked secrets and supports compliance with data protection requirements. | Microsoft Priva provides privacy-focused capabilities including personal data discovery, privacy risk management, subject rights request automation, and consent management. |
| **Infrastructure** | Microsoft Security Exposure Management provides visibility into cloud and on-premises infrastructure vulnerabilities, misconfigurations, and compliance gaps across multicloud environments. | Dependency scanning and dependency review identify known vulnerabilities in open‑source components and configuration files before infrastructure or applications are deployed, reducing inherited risk and supporting secure‑by‑default infrastructure posture. | Microsoft Priva extends privacy visibility to data stored across cloud infrastructure, helping organizations maintain privacy compliance in multicloud environments. |
| **AI** | Microsoft Security Exposure Management applies AI to model attack paths, prioritize risks based on exploitability and business impact, and provide intelligent recommendations for posture improvements. | GitHub Advanced Security scans AI‑assisted and human‑written code alike, helping teams maintain security standards as AI accelerates development. AI‑assisted remediation accelerates fixing vulnerabilities without bypassing security controls. | Microsoft Priva supports privacy compliance for AI workloads by helping organizations understand how personal data is used in AI training and inference scenarios. |