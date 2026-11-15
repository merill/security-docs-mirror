---
layout: Conceptual
title: Microsoft Zero Trust Workshop - DevSecOps | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/workshop-zero-trust-devsecops
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Learn about the DevSecOps pillar in the Microsoft Zero Trust Workshop
ms.date: 2026-11-12T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 0cbe66fb-9701-4e7e-28e5-2493c941d8f9
document_version_independent_id: 0cbe66fb-9701-4e7e-28e5-2493c941d8f9
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/workshop-zero-trust-devsecops.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/workshop-zero-trust-devsecops
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/workshop-zero-trust-devsecops.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/64b65f6c-101f-411a-9b83-9f577fab52d0
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/1a667fd1-8145-4b11-af0f-9f5de205a6e5
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 431288ef-272e-d83c-2796-418297409786
---

# Microsoft Zero Trust Workshop - DevSecOps | Microsoft Learn

DevSecOps integrates security into the people, processes, platforms, code, pipelines, and infrastructure used to build and deliver software. The DevSecOps workshop pillar helps organizations reduce implicit trust across the software development lifecycle by governing identities and repositories, securing code and dependencies, hardening CI/CD pipelines, and protecting the software supply chain.

The DevSecOps workshop pillar helps organizations identify security gaps and create a prioritized implementation roadmap across developer platforms, source code, pipelines, build infrastructure, deployment environments, and security operations.

The DevSecOps workshop pillar corresponds to the SAF [Development Security](security-adoption-discipline-development-security) discipline rather than to an SAF technology.

## Why focus on DevSecOps?

Compromised developer accounts, exposed secrets, vulnerable dependencies, untrusted pipeline components, insecure build runners, and weak release controls can provide paths from source code to production. The DevSecOps Workshop applies the Zero Trust principles of verify explicitly, use least privilege, and assume breach throughout the software development lifecycle.

The expected output is an actionable backlog of DevSecOps projects prioritized into First, Then, and Next based on organizational risk, dependencies, implementation effort, developer impact, coverage, and readiness.

## DevSecOps implementation areas

| **Area** | **Details** |
| --- | --- |
| **Establish DevSecOps strategy, ownership, and governance** | Define accountable owners, operating responsibilities, security requirements, metrics, remediation service-level objectives, exception processes, maturity reviews, and compliance evidence across engineering and security teams. |
| **Inventory and govern developer platforms and repositories** | Discover source repositories, DevOps organizations, build infrastructure, accounts, privileged groups, and service connections across platforms. Assign ownership, establish secure defaults, and prioritize onboarding into governance and security tooling. |
| **Secure developer identities and access** | Integrate supported developer platforms with Microsoft Entra ID, apply Conditional Access, govern privileged groups and administrative roles, use access reviews and time-bound access where appropriate, and maintain tested emergency-access procedures. |
| **Protect credentials and workload identities** | Detect and block exposed secrets, eliminate plaintext credentials, rotate existing secrets, and migrate pipelines and applications toward managed identities or workload identity federation. Scope permissions to the minimum required resources and operations. |
| **Establish repository and code-review protections** | Apply organization-wide repository baselines, branch protections, CODEOWNERS or equivalent ownership controls, peer-review and approval requirements, protected environments, and controls for untrusted contributions and fork-based workflows. |
| **Implement application security testing** | Integrate static, dynamic, API, and organization-specific security testing into developer workflows and CI/CD. Tune findings, surface feedback in pull requests or work items, and use third-party tools where they provide necessary coverage. |
| **Secure dependencies and open-source usage** | Enable dependency inventory, alerts, updates, and pull-request review. Govern approved packages and registries, assess software composition and license risks, and prioritize vulnerable dependencies based on severity, exploitability, reachability, and business impact. |
| **Protect the software supply chain** | Generate software bills of materials, establish artifact signing and build provenance, verify integrity at deployment boundaries, govern trusted publishing, use approved base images, and secure AI or machine-learning model artifacts where applicable. |
| **Harden CI/CD pipelines and build infrastructure** | Use version-controlled pipeline definitions, pin third-party actions and tasks to trusted immutable references, protect reusable templates, apply least privilege, use ephemeral or hardened runners where appropriate, and evaluate pipeline risks against recognized practices such as the OWASP CI/CD Top 10. |
| **Secure infrastructure as code and deployment controls** | Scan infrastructure-as-code changes in pull requests and pipelines, define approved modules and security baselines, deploy policy as code, monitor configuration drift, and require approvals and security gates for protected environments and releases. |
| **Protect containers and cloud-native delivery** | Scan container images in pipelines and registries, govern approved base images, sign and verify images where appropriate, protect registries and clusters, and integrate runtime container protection with build and deployment controls. |
| **Manage findings, vulnerabilities, and remediation** | Create a unified triage process for code, secret, dependency, pipeline, infrastructure, and cloud findings. Assign owners, apply risk-based remediation timelines, manage exceptions, clear existing backlogs, and track progress through centralized dashboards. |
| **Integrate DevSecOps signals into security operations** | Connect developer platforms and cloud security services to centralized monitoring and SIEM workflows. Establish code-to-cloud traceability, attack-path analysis, DevOps-specific incident-response playbooks, and coordinated vulnerability-disclosure processes. |
| **Build secure engineering practices and culture** | Embed security requirements in backlogs and design reviews, establish threat modeling, provide role-based secure-development training, support security champions, govern AI-assisted development tools and data handling, and continuously improve using measurable outcomes. |

These areas summarize the DevSecOps workshop pillar. Use the detailed DevSecOps project guidance to review individual projects and implementation considerations.

## How to use the DevSecOps Workshop

Use the web-based Workshop with development, platform engineering, application security, cloud security, identity, infrastructure, data protection, compliance, and security operations stakeholders. For each relevant project:

- Review the project objective and applicability to your environment.
- Record the current status, notes, decisions, owners, and known dependencies.
- Consider licensing, implementation effort, developer impact, technical prerequisites, coverage, and cross-pillar dependencies.
- Prioritize the project into First, Then, or Next and incorporate it into the implementation roadmap.

[Open the Zero Trust Workshop](https://aka.ms/ztworkshop) and select the DevSecOps pillar.

[Review the detailed DevSecOps project guidance](https://microsoft.github.io/zerotrustassessment/docs/category/devsecops) for project-level information.

## Assess your DevSecOps posture

The Microsoft Zero Trust Assessment does not currently assess the DevSecOps pillar. Use the DevSecOps Workshop and detailed project guidance to evaluate your development platforms, repositories, pipelines, software supply chain, deployment controls, and operational processes. Findings from other assessed pillars can still provide useful cross-pillar context.

[Learn about the Zero Trust Assessment](/en-us/security/zero-trust/assessment/overview) and its current pillar coverage.

## Who should participate?

- Software engineering, application architecture, and engineering leadership teams.
- Platform engineering, DevOps, site reliability engineering, cloud platform, and release-management teams.
- Application security, product security, cloud security, identity, data protection, security operations, and incident response teams.
- Governance, risk, compliance, legal, procurement, open-source program, and business or application owners.