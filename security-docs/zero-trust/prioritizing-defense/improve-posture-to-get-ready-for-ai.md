---
layout: Conceptual
title: Improve posture to get ready for AI | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/prioritizing-defense/improve-posture-to-get-ready-for-ai
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Improve AI readiness by managing devices, reducing reachable exposure, securing software, and connecting prioritized implementation work to SAF.
ms.date: 2026-11-06T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
ms.custom: msecd-doc-authoring-1028
ai-usage: ai-assisted
locale: en-us
document_id: 996e97b9-a8b4-cbeb-2a53-9e5b0764dcc6
document_version_independent_id: 996e97b9-a8b4-cbeb-2a53-9e5b0764dcc6
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/prioritizing-defense/improve-posture-to-get-ready-for-ai.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/prioritizing-defense/improve-posture-to-get-ready-for-ai
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/prioritizing-defense/improve-posture-to-get-ready-for-ai.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e9e4163d-5abc-4b31-8602-bd8826f5d740
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/062d60c9-ee0f-402e-a046-b4e67c3572d6
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/a225912b-c498-48b4-a85f-d3e64981cbdc
- https://authoring-docs-microsoft.poolparty.biz/devrel/17d3b3f6-a66e-4c69-9774-14a73c38e669
platformId: 9468f777-9d7a-e6c6-ecd3-0912a652c45d
---

# Improve posture to get ready for AI | Microsoft Learn

Improving posture to get ready for AI means establishing a defensible device, application, data, software, and infrastructure baseline before AI systems and agents inherit the environment. The work reduces reachable attack surface, closes common control gaps, and prioritizes remediation where it reduces the most business risk.

This guidance provides detailed implementation continuity for work described in the [Secure your foundations](/en-us/security/saf/scenarios/ai-security/security-foundations) AI security transformation theme. Use the [Microsoft Security Adoption Framework (SAF)](../security-adoption-model) to coordinate this work across business scenarios, security disciplines, roles, technologies, and technical solutions.

## Why this work matters

AI gives attackers new ways to discover, analyze, and chain vulnerabilities at greater speed. Many of the weaknesses they exploit remain familiar:

- unmanaged or noncompliant devices;
- organizational data leaving managed applications;
- unnecessary internet-facing exposure and attack paths to critical assets;
- unpatched software and operating systems;
- vulnerable open-source dependencies and software supply chains;
- weaknesses in application and infrastructure code; and
- unmanaged identities, credentials, and secrets.

AI adoption raises the stakes because AI systems and agents can inherit the posture of the devices, identities, services, data, software, and infrastructure they can reach. Strengthening these foundations reduces risk before AI increases scale and connectivity.

## Prioritize posture improvements

Use [Secure Now](https://aka.ms/SecureNow) and [Microsoft Security Exposure Management](/en-us/security-exposure-management/microsoft-security-exposure-management) to review current recommendations, prioritize work, and track progress. Connect the implementation work to SAF so priorities, ownership, and measures are sustained after an individual initiative is complete.

| Initiative | Durable outcome | Primary SAF connection | Implementation resource |
| --- | --- | --- | --- |
| Manage organizational devices | Devices that access organizational resources are known, managed, monitored, and assigned to accountable owners. | [Security posture management](../security-adoption-discipline-posture), [endpoints](../deploy/endpoints) | [Manage devices with Intune](../manage-devices-with-intune-overview) |
| Implement device compliance requirements | Access decisions include device health and policy compliance instead of relying on identity alone. | [Access and identities](../security-adoption-discipline-identity-access), [endpoints](../deploy/endpoints) | [Set up compliance policies](../manage-devices-with-intune-compliance-policies) and [require device compliance](../manage-devices-with-intune-require-compliance) |
| Protect organizational data in managed applications | Work data remains protected in approved applications, including on devices the organization does not manage. | [Data security](../security-adoption-discipline-data), [endpoints](../deploy/endpoints) | [Protect apps](../manage-devices-with-intune-app-protection) and [implement data loss prevention](../manage-devices-with-intune-dlp-mip) |
| Reduce internet-facing exposure | Unnecessary exposure and reachable attack paths to critical assets are removed or controlled. | [Security posture management](../security-adoption-discipline-posture), [infrastructure](../deploy/infrastructure), [networks](../deploy/networks) | [Microsoft Security Exposure Management](/en-us/security-exposure-management/microsoft-security-exposure-management) |
| Improve patching and vulnerability management | Remediation is prioritized by asset criticality, reachability, exploitability, and business impact. | [Security posture management](../security-adoption-discipline-posture), [infrastructure security](../security-adoption-discipline-infrastructure) | [Secure Now](https://aka.ms/SecureNow) |
| Secure the software supply chain | Dependencies, build systems, artifacts, and publishing processes use approved, observable security controls. | [Development security](../security-adoption-discipline-development), [development security implementation patterns](/en-us/security/saf/disciplines/development/implementation-patterns) | [Microsoft Security Development Lifecycle](https://www.microsoft.com/securityengineering/sdl/) and [protect the software supply chain](../sfi/protect-software-supply-chain) |
| Scan and remediate code | Security weaknesses are found and fixed through repeatable engineering workflows before and after deployment. | [Development security](../security-adoption-discipline-development), [applications](../deploy/applications) | [Secure source code with GitHub Advanced Security](../sfi/secure-source-code-github-advanced-security) |

## Coordinate the work through SAF

Treat the initiatives as connected parts of the security program:

- Use [Strengthen posture and compliance](../security-adoption-scenario-improve-posture) to define the overall business outcome and measures.
- Use [Adopt and secure AI](../security-adoption-scenario-secure-ai) to connect foundation work to AI adoption and AI-specific risk.
- Use [Security posture management](../security-adoption-discipline-posture) to maintain inventory, exposure analysis, prioritization, remediation, and verification.
- Use [Security roles and responsibilities](../security-adoption-roles) to assign accountable owners and cross-team decision rights.
- Use [technologies](../deploy/overview) and [technical solutions](../implement-overview) to reach canonical implementation guidance.
- Use the [AI security workshop](../workshop-zero-trust-ai-security) to assess implementation areas and create a roadmap.

## Outcomes and measures

Expected outcomes include:

- managed and compliant devices use an approved security baseline;
- data remains protected in managed applications and approved repositories;
- attack paths from internet-facing systems to critical assets trend down;
- vulnerability and patch work is prioritized according to business risk;
- software dependencies, pipelines, code, and artifacts use repeatable security controls; and
- AI systems and agents inherit a governed, measured foundation rather than unmanaged exposure.

Consider measures such as:

- percentage of critical assets with a named accountable owner;
- percentage of corporate devices enrolled in management and compliant with policy;
- percentage of applicable users covered by application protection policies;
- number of reachable attack paths from internet-facing assets to critical assets;
- patch and vulnerability remediation performance by asset criticality and service-level objective;
- percentage of production builds that use approved pipelines, code scanning, dependency controls, and software bills of materials; and
- Secure Now or exposure-management initiative progress compared with the organization's target and baseline.