---
layout: Conceptual
title: Align business outcomes and scenarios with Microsoft technologies | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-business-scenarios-technologies
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn how business security outcomes are enabled with Microsoft security technologies.
ms.date: 2026-05-24T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 7f8d918e-5b04-2a98-098c-79b5f92dcaa0
document_version_independent_id: 7f8d918e-5b04-2a98-098c-79b5f92dcaa0
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-adoption-business-scenarios-technologies.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-adoption-business-scenarios-technologies
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-adoption-business-scenarios-technologies.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
- https://authoring-docs-microsoft.poolparty.biz/devrel/8a94907f-2511-4271-b5ca-ec7f2e75067c
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/a72e95ff-4b4f-4cc1-90c6-7dcba67ff05f
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
- https://authoring-docs-microsoft.poolparty.biz/devrel/bffa8e88-f633-409d-a24d-083bdbc68872
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/24dc3ccd-591a-4415-a1fe-8759afafcb12
platformId: 0d4e49a2-6e21-6318-79bb-b7074607e4db
---

# Align business outcomes and scenarios with Microsoft technologies | Microsoft Learn

This article shows how [business scenarios](security-adoption-business-scenarios-overview) are implemented with Microsoft technologies.

We capture the business outcome for each scenario, the disciplines responsible for delivering the outcomes, and the Microsoft technologies that enable it.

## Minimize business damage

### Outcome

Minimize business damage by detecting, investigating, and responding to security incidents quickly and consistently across the enterprise.

### Primary discipline

Security operations (SecOps). [Learn more](security-adoption-discipline-security-operations).

### Primary technologies

Primary technologies for this business solution are Microsoft Defender XDR services, and Microsoft Sentinel.

#### Microsoft Defender

Defender and other security services align under the Defender portal. Defender XDR is the unifying threat detection and response layer for SecOps. It brings together signals, alerts, and response actions from a range of Defender technologies, enabling coordinated detection, investigation, and response across the digital estate.

[![Illustration of how Microsoft Defender aligns to the business scenario.](media/security-adoption-defender-map.png)](media/security-adoption-defender-map.png#lightbox)

#### Microsoft Sentinel

Microsoft Sentinel is a primary enabler for this business scenario.

- It provides centralized visibility across your entire digital estate, enabling rapid detection and response to threats before they cause significant damage.
- Automated playbooks and SOAR capabilities accelerate incident response, reducing mean time to remediation.
- Microsoft Sentinel is the primary technology to enable a unified and effective security operations discipline that provides comprehensive threat detection, investigation, and response capabilities across technology pillars.

[![Illustration of how Microsoft Sentinel aligns to the business scenario.](media/security-adoption-sentinel-map.png)](media/security-adoption-sentinel-map.png#lightbox)

Review the business scenario [Minimizing business damage from security incidents](security-adoption-scenario-minimize-impact).

## Enable secure work from anywhere

### Outcome

Enable productivity while enforcing Zero Trust access decisions based on identity, device health, risk, and data sensitivity.

### Primary discipline

Access and identities. [Learn more](security-adoption-discipline-identity-access).

### Primary technologies

Primary technologies for this business solution are Microsoft Entra and Microsoft Intune.

#### Microsoft Entra

Microsoft Entra technologies are a primary enabler for this business scenario. It provides the identities necessary to secure remote access from anywhere. Technologies like Microsoft Entra Private Access allow you to replace legacy VPNs and Microsoft Entra Conditional Access is the policy engine to enforce compliance with Zero Trust policy.

[![Illustration of how Microsoft Entra aligns to the business scenario.](media/security-adoption-entra-map.png)](media/security-adoption-entra-map.png#lightbox)

#### Microsoft Intune

Microsoft Intune technologies are a primary enabler for this business scenario. It provides cloud-based unified endpoint management across multiple operating systems, cloud, on-premises, mobile, desktop, and virtualized endpoints. Intune provides the device compliance foundation for Zero Trust access: MFA + compliant device + risk evaluation when paired with Microsoft Entra Conditional Access. Only secure devices can reach SaaS, apps, and data.

[![Illustration of how Microsoft Intune aligns to the business scenario.](media/security-adoption-intune-map.png)](media/security-adoption-intune-map.png#lightbox)

Review the business scenario [Enabling people to do their job securely](security-adoption-scenario-remote-work).

## Continuously improve posture and compliance

### Outcome

Reduce exposure and improve compliance by providing clear visibility into attack paths, misconfigurations, and vulnerabilities across the digital estate.

### Primary discipline

- Posture management: Continuous visibility, risk assessment, prioritization, and improvement tracking. [Learn more](security-adoption-discipline-posture).
- Development security: Effective identification and remediation of vulnerabilities across the development lifecycle. [Learn more](security-adoption-discipline-development).
- Data security: Protect sensitive and personal data. [Learn more](security-adoption-discipline-data).

### Primary technologies

Primary technologies for this business solution are Microsoft Security Exposure Management, GitHub Advanced Security, and Microsoft Priva.

#### Microsoft Security Exposure Management

Microsoft Security Exposure Management is a primary enabler for this business scenario. It provides a unified view of your security posture, enabling you to identify attack paths, prioritize vulnerabilities based on business impact, and track security improvements over time.

[![Graphic shows how Microsoft Security Exposure Management aligns to the business scenario.](media/security-adoption-security-exposure-map.png)](media/security-adoption-security-exposure-map.png#lightbox)

#### GitHub Advanced Security

Security posture isn't only about deployed assets—it's also shaped by how software is built. Shifting security earlier in the development lifecycle reduces downstream exposure, lowers remediation cost, and improves overall risk posture.

GitHub Advanced Security is a primary enabler for this business scenario. It shifts security left by integrating security scanning directly into the development workflow, enabling developers to identify and fix vulnerabilities before code reaches production. It improves security posture by:

- Preventing vulnerabilities from entering production environments.
- Reducing exposure that would otherwise appear later in posture tools.
- Supporting compliance by enforcing consistent security standards in code.
- Lowering remediation cost and risk compared to post‑deployment fixes.

[![Illustration of how GitHub advanced security aligns to the business scenario.](media/security-adoption-github-map.png)](media/security-adoption-github-map.png#lightbox)

#### Microsoft Priva

Microsoft Priva is a primary enabler for this business scenario. It helps organizations discover personal data across their environment, automate privacy risk assessments, and demonstrate compliance with privacy regulations such as GDPR, CCPA, and other data protection requirements.

Review the business scenario [Continuously improving security posture and compliance](security-adoption-scenario-improve-posture).

## Protect critical assets

### Outcome

Identify where sensitive data resides and applying appropriate protection controls throughout its lifecycle.

### Primary discipline

Data security: Provide comprehensive data governance, protection, and compliance. [Learn more](security-adoption-discipline-data)

### Primary technologies

Primary technologies for this business solution are Microsoft Purview, and Microsoft Entra for privileged access.

#### Microsoft Purview

Microsoft Purview is a primary enabler for this business scenario. It provides comprehensive data discovery, classification, and protection capabilities that help organizations identify where sensitive data resides and apply appropriate protection controls throughout its lifecycle.

[![Graphic shows how Microsoft Purview aligns to the business scenario.](media/security-adoption-purview-map.png)](media/security-adoption-purview-map.png#lightbox)

#### Microsoft Entra

Microsoft Entra partners with Purview to provide the identity control plane for this business scenario, ensuring that access to sensitive data is governed, verified, and continuously monitored. It enforces least-privilege access and secures privileged roles that can access or modify critical assets.

Review the business scenario [Identifying and protecting critical business assets](security-adoption-scenario-secure-assets).

## Rapidly and securely adopt AI

### Outcome

Enable teams to innovate with AI quickly while protecting data, code, and intellectual property.

### Primary discipline

Data security: Control data used by and produced through AI. Include discovery, classification, sensitivity labels, DLP, and governance for AI interactions. Enable teams to innovate with AI quickly while protecting data, code, and intellectual property.

### Primary technologies

Primary technologies for this business solution are Microsoft Purview, and GitHub Advanced Security.

#### Microsoft Purview

Microsoft Purview is a primary enabler for this business scenario. It provides comprehensive data discovery, classification, and protection capabilities that help organizations identify where sensitive data resides and apply appropriate protection controls throughout its lifecycle.

Review the business scenario [Rapidly and securely adopt AI](security-adoption-scenario-secure-ai).