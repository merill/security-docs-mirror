---
layout: Conceptual
title: Microsoft security products and platforms | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-platform
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Learn how Microsoft security products and platforms provide capabilities that help organizations implement security across identities, endpoints, applications, data, infrastructure, networks, AI, and security operations.
ms.date: 2026-11-09T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: edcbeeba-990f-bd80-cf68-f7b7a06870f4
document_version_independent_id: edcbeeba-990f-bd80-cf68-f7b7a06870f4
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-platform.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-platform
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-platform.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
platformId: 58c66ac8-6631-7c5b-4bce-f4f9face7de1
---

# Microsoft security products and platforms | Microsoft Learn

Microsoft security products and platforms provide capabilities to protect identities, endpoints, applications, data, infrastructure, networks, and AI and to support security operations across these environments. These products work together by sharing signals and context and integrating protection, policy, detection, investigation, and response capabilities.

The [Security Adoption Framework (SAF)](security-adoption-model) provides a durable model for organizing desired outcomes, security work, technologies, and technical implementation. Microsoft products and platforms provide capabilities that help organizations implement and operate that security.

A Microsoft security product can support multiple SAF areas, and implementing a security outcome frequently requires capabilities from multiple products and platforms.

## Explore Microsoft security products and platforms

Use the following product families to find Microsoft implementation and product guidance relevant to your security requirements. The SAF relationship identifies where each product family most directly connects to SAF. These are primary relationships, not exclusive mappings. Many products support multiple SAF technologies, security disciplines, business scenarios, and technical solutions.

| Primary SAF relationship | Microsoft products and platforms | Capabilities |
| --- | --- | --- |
| **Technology: Identity** | Microsoft Entra, Microsoft Defender for Identity | Manage identities and access, govern privileges, evaluate identity and access risk, and detect attacks against identity infrastructure. |
| **Technology: Endpoints** | Microsoft Intune, Microsoft Defender for Endpoint | Manage and assess device configuration and compliance, protect endpoints, detect threats, and support investigation and response. |
| **Technologies: Applications and Data** | Microsoft Defender for Office 365 | Protect email and collaboration services from phishing, malicious content, business email compromise, and other threats. |
| **Technology: Applications** | Microsoft Defender for Cloud Apps | Discover and protect cloud applications, assess application activity and risk, and apply controls to cloud application sessions. |
| **Technology: Data** | Microsoft Purview | Discover, classify, protect, and govern data and reduce risks such as inappropriate access, data loss, and insider threats. |
| **Technology: Infrastructure** | Microsoft Defender for Cloud, Azure security capabilities | Improve cloud security posture and protect cloud and hybrid infrastructure and workloads. |
| **Technology: Network** | Azure network security services | Segment, connect, monitor, and protect network traffic and network-access paths across cloud and hybrid environments. |
| **Discipline: Security Posture** | Microsoft Security Exposure Management | Identify and prioritize exposure across identities, devices, applications, and cloud resources and help teams focus remediation on material risks. |
| **Discipline: SecOps/SOC** | Microsoft Defender XDR, Microsoft Sentinel | Support security monitoring, detection, triage, investigation, hunting, automation, incident response, and coordinated response across Microsoft and third-party environments. |
| **Discipline: Development Security** | GitHub Advanced Security, Microsoft Defender for Cloud | Integrate security into software development and DevOps workflows to identify and reduce risk in code, dependencies, pipelines, and cloud applications. |
| **Cross-cutting security work** | Microsoft Security Copilot | Use AI to assist security analysis, investigation, threat intelligence, and response while people maintain appropriate judgment, oversight, and accountability. |

For detailed configuration, deployment, and operational guidance, use the documentation for the relevant Microsoft product or platform. Product documentation is the authoritative source for current product capabilities and implementation procedures.

## How Microsoft products support SAF

SAF and Microsoft product families serve different purposes. SAF organizes security around why security improvement is needed, what outcomes organizations are trying to achieve, what security work must be performed, what technologies must be protected, and how security capabilities are implemented and operated.

Microsoft security products and platforms provide technical capabilities that help implement this work. The relationship is many-to-many: a product can support multiple SAF technologies, disciplines, business scenarios, and technical solutions, while a security outcome typically requires capabilities from multiple products and platforms.

For example, protecting access to business resources can require identity controls from Microsoft Entra, device state from Microsoft Intune and Microsoft Defender for Endpoint, data protection from Microsoft Purview, detections from Microsoft Defender, and monitoring and response through Microsoft Sentinel.

Use SAF to determine the security outcomes, security work, and technology requirements you need to address. Use Microsoft product guidance to plan, configure, deploy, and operate the capabilities that help implement them.

## An integrated security platform

Microsoft security products can share security signals and context across identities, devices, applications, data, infrastructure, and cloud services. These integrations help organizations coordinate prevention, protection, detection, investigation, and response across environments.

Common integration patterns include:

- **Security signals and telemetry** that provide visibility across identities, endpoints, applications, data, and infrastructure.
- **Identity and device context** that informs access and security decisions.
- **Security posture and exposure information** that helps teams prioritize risks and improvements.
- **Data context and classification** that informs protection and investigation.
- **Correlated alerts and incidents** that help security operations teams investigate activity across multiple technology areas.
- **Automation and AI-assisted workflows** that can perform appropriate repeatable analysis, investigation, and response at machine speed while people provide judgment, expertise, oversight, and accountability where required.

These integrations support the organization's broader security architecture and operating model while enabling capabilities to work together across Microsoft products and platforms.