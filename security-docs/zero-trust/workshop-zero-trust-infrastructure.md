---
layout: Conceptual
title: Microsoft Zero Trust Workshop - Infrastructure | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/workshop-zero-trust-infrastructure
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn about the Infrastructure pillar in the Microsoft Zero Trust Workshop
ms.date: 2026-11-06T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: b1820328-8f20-bf36-707f-43963622d83f
document_version_independent_id: b1820328-8f20-bf36-707f-43963622d83f
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/workshop-zero-trust-infrastructure.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/workshop-zero-trust-infrastructure
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/workshop-zero-trust-infrastructure.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/2ed91286-6cf7-4b83-810d-75d0ee3b09dd
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/6735bd7e-4f7b-457d-b58c-29e6f0198677
platformId: ee2a94db-2d4a-a7b9-e779-8fd8ba1ba683
---

# Microsoft Zero Trust Workshop - Infrastructure | Microsoft Learn

In a Zero Trust architecture, infrastructure security focuses on protecting the foundational compute and platform resources that host applications and services across multicloud and on-premises environments. Rather than implicitly trusting infrastructure, this pillar ensures that servers, containers, storage, and platform services are continuously assessed, hardened, and monitored under an assume-breach mindset.

Infrastructure pillar guidance focuses on managing security posture, protecting workloads at runtime, governing infrastructure configurations, controlling administrative access, and integrating infrastructure signals into security operations.

## Workshop implementation

The Infrastructure workshop covers the implementation areas summarized in the table.

| **Area** | **Details** |
| --- | --- |
| **Establish infrastructure security posture management** | Continuously assess infrastructure resources for misconfigurations, policy violations, and exposure risks. Use posture management capabilities to identify configuration drift, enforce governance policies, and prioritize remediation across cloud and hybrid environments. |
| **Protect compute workloads across virtual machines and containers** | Secure multicloud virtual machines, container environments, and hybrid environments using workload protection capabilities.Continuously monitor security posture, detect threats, and remediate vulnerabilities affecting compute workloads. |
| **Secure and govern platform services and control planes** | Apply security controls to platform services such as storage, databases, and application services. Govern access, configurations, and exposure of platform resources to reduce risk across cloud control planes. |
| **Assess and manage vulnerabilities** | Continuously scan infrastructure resources for vulnerabilities and configuration issues.Prioritize and remediate findings based on risk, and tune alerts to reduce noise while maintaining visibility. |
| **Control access to infrastructure resources** | Enforce least-privilege access using role-based access control (RBAC) and just-in-time (JIT) access.Integrate identity-based access controls to ensure administrative access is granted only when required and scoped appropriately. |
| **Harden configurations and enforce security baselines** | Define and apply secure configuration baselines across infrastructure resources.Standardize settings for compute, networking, and platform services to prevent misconfigurations and ensure consistent protection. |
| **Monitor workloads and detect threats at runtime** | Continuously monitor infrastructure for suspicious activity and security threats.Use runtime protection and analytics to detect attacks targeting virtual machines, containers, and platform services. |
| **Integrate infrastructure signals into security operations (SecOps)** | Stream posture findings, runtime alerts, and threat signals into centralized monitoring and response systems. Correlate infrastructure data with identity, device, network, and data signals to support investigation and response. |