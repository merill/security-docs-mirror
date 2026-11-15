---
layout: Conceptual
title: Microsoft security best practices | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-best-practices-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Explore Microsoft security best practices for Zero Trust, security adoption, secure baselines, assessments, technologies, standards and frameworks, and secure engineering.
ms.date: 2026-11-08T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: fa58daad-4451-5d5b-4dae-9eae4aed5195
document_version_independent_id: fa58daad-4451-5d5b-4dae-9eae4aed5195
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-best-practices-overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-best-practices-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-best-practices-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/97159432-14a9-4307-a469-d2f2c75f0e33
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/a72e95ff-4b4f-4cc1-90c6-7dcba67ff05f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/50565c62-5f6b-4687-be38-323113c72c2e
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/24dc3ccd-591a-4415-a1fe-8759afafcb12
platformId: e3b70a1a-fbec-5350-af1d-5660151738d3
---

# Microsoft security best practices | Microsoft Learn

**Security best practices apply at many levels.** They help organizations make informed decisions about managing security risk and improving resilience. Best practices can address people, processes, and technology across strategy, governance, architecture, implementation, and operations.

**Microsoft security guidance includes many forms of best practices.** These range from strategic principles and organizational practices to security standards and frameworks, secure configuration baselines and benchmarks, architecture, assessments, technology guidance, and implementation practices. These forms of guidance provide different perspectives and levels of detail and are designed to work together rather than as a single checklist or prescribed approach.

**Standards and frameworks provide established security practices.** They organize security objectives, practices, controls, or requirements into structures that organizations can use to guide security programs, assess progress, and communicate alignment. Microsoft guidance helps organizations connect these frameworks to practical security work and technology implementation.

**Best practices must be adapted to organizational context.** Business priorities, risk, regulatory and policy requirements, threat environment, technology estate, existing capabilities, resources, and organizational structure can affect which practices are most important and how they should be implemented.

Use the following resources based on what you are trying to accomplish.

## Establish a security foundation with Zero Trust

Use [Zero Trust](zero-trust-overview) as a security foundation for designing, implementing, and operating security controls across your organization.

Zero Trust applies three principles across business, security, and technology decisions: verify explicitly, use least privilege access, and assume breach.

## Organize and improve your security program with SAF

Use the [Microsoft Security Adoption Framework (SAF)](security-adoption-model) to connect business priorities and risk to coordinated security work and technology implementation.

SAF helps business, technology, and security roles collaborate across business scenarios, security disciplines, technologies, and technical solutions.

## Use established security baselines and benchmarks

**Security baselines provide tested starting points.** They help organizations apply established security recommendations consistently rather than developing every security configuration from the beginning.

Microsoft provides security baselines and benchmarks for different technologies and environments, including:

- **Microsoft Cloud Security Benchmark (MCSB):** Provides security recommendations for improving the security of cloud workloads, data, and services. See [Overview of the Microsoft cloud security benchmark](/en-us/security/benchmark/azure/overview).
- **Windows and Windows Server security baselines:** Provide Microsoft-recommended configuration settings for securing Windows devices and servers. See [Windows security baselines](/en-us/windows/security/operating-system-security/device-management/windows-security-configuration-framework/windows-security-baselines) and [configure security baselines for Windows Server 2025](/en-us/windows-server/security/osconfig/osconfig-how-to-configure-security-baselines).
- **Microsoft 365 Apps for enterprise security baseline:** Provides recommended configuration settings for Microsoft 365 Apps and guidance for balancing security with productivity requirements. See [Security baseline for Microsoft 365 Apps for enterprise](/en-us/microsoft-365-apps/security/security-baseline).
- **Microsoft Edge security baseline:** Provides recommended security configuration settings for Microsoft Edge. See [Microsoft Edge security baseline settings reference for Microsoft Intune](/en-us/intune/device-security/security-baselines/ref-v2-edge-settings).
- **Microsoft Intune security baselines:** Provide deployable groups of recommended security settings for Windows devices and supported security technologies managed with Intune. See [Use security baselines to help secure Windows devices you manage with Microsoft Intune](/en-us/intune/device-security/security-baselines/overview).

**A security baseline is a starting point, not a universal configuration.** Evaluate and adapt baselines based on organizational risk, regulatory and policy requirements, technology dependencies, operational needs, and productivity requirements.

## Assess your Zero Trust implementation

Use the [Zero Trust assessment](assessment/overview) to evaluate your current implementation, identify security gaps, and prioritize improvements across Zero Trust technology controls.

Assessment results can provide a practical starting point for prioritizing improvements and measuring progress over time.

## Secure specific technologies

Use [technology security guidance](deploy/overview) when you need to secure a particular part of your technology environment.

The guidance applies Zero Trust principles across identities, endpoints, applications, data, infrastructure, networks, and AI and connects to more detailed implementation guidance.

## Apply security standards and frameworks

Use [Security standards and frameworks](security-standards-and-frameworks) when your organization uses an established security standard or framework to structure security objectives, practices, controls, or requirements.

Standards and frameworks capture and organize security practices from different authorities, communities, and areas of expertise. Organizations can use them to structure security programs, establish common expectations, assess progress, and communicate alignment.

Microsoft mappings connect framework objectives to SAF guidance, security capabilities, technology implementation, and relevant Microsoft product guidance. Organizations can use these mappings to help align security work with framework objectives and requirements without treating framework alignment or compliance as the complete measure of security success.

## Learn from Microsoft's security engineering practices

Use the [Microsoft Secure Future Initiative (SFI)](sfi/secure-future-initiative-overview) to learn from security engineering practices, patterns, and lessons from Microsoft's efforts to strengthen the security of its products and services.

SFI complements SAF and other Microsoft security guidance with engineering practices and lessons that organizations can consider as they improve their own security programs.